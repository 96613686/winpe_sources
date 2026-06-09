# ServiceManager::GetCopyrightString(ushort * *,bool *)

- ea: `0x180016240`
- end: `0x18001635b`
- name: `?GetCopyrightString@ServiceManager@@UEAAJPEAPEAGPEA_N@Z`
- size: `283`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, unsigned __int16 **, bool *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180003410`
- `0x180006ea8`
- `0x1800079d4`
- `0x180008110`
- `0x18000816c`
- `0x180015b40`
- `0x180016240`
- `0x180025010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001629e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001629e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800162e3`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800162e3`

## string_xrefs

- `0x180016295`: `ServiceManager::GetCopyrightString`
- `0x1800162d9`: `ServiceManager::GetCopyrightString`

## pseudocode

```c
__int64 __fastcall ServiceManager::GetCopyrightString(ServiceManager *this, unsigned __int16 **a2, bool *a3)
{
  int CopyrightString; // eax
  unsigned __int16 *v7; // rbx
  unsigned int v8; // eax
  unsigned int v9; // edi
  unsigned __int64 v10; // rsi
  int v11; // r8d
  int v12; // ecx
  const unsigned __int16 *v13; // rax
  int v14; // eax
  bool v16; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v17[16]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-40h]

  std::wstring::wstring((__int64)v17);
  v16 = 0;
  CopyrightString = ServiceManager::FetchCopyrightString(this, (__int64)v17, &v16);
  if ( CopyrightString >= 0 )
  {
    v10 = v18 + 1;
    v7 = (unsigned __int16 *)(**(__int64 (__fastcall ***)(__int64, __int64))qword_180035648)(
                               qword_180035648,
                               2 * (v18 + 1));
    if ( v7 )
    {
      v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v14 = StringCchCopyW(v7, v10, v13);
      if ( v14 >= 0 )
      {
        v9 = 0;
        *a2 = v7;
        v7 = 0;
        *a3 = v16;
        goto LABEL_10;
      }
      v11 = 2975;
      v12 = v14;
    }
    else
    {
      v11 = 2974;
      v12 = -2147024882;
    }
    v8 = ZTraceReportOrigination(v12, "ServiceManager::GetCopyrightString", v11, this);
  }
  else
  {
    v7 = 0;
    v8 = ZTraceReportPropagation(CopyrightString, "ServiceManager::GetCopyrightString", 2971, this);
  }
  v9 = v8;
LABEL_10:
  (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)qword_180035648 + 8LL))(qword_180035648, v7);
  std::wstring::_Tidy_deallocate((__int64)v17);
  return v9;
}

```

## disassembly

```asm
0x180016240  push    rbx
0x180016242  push    rsi
0x180016243  push    rdi
0x180016244  push    r14
0x180016246  push    r15
0x180016248  sub     rsp, 50h
0x18001624c  mov     rax, cs:__security_cookie
0x180016253  xor     rax, rsp
0x180016256  mov     [rsp+78h+var_30], rax
0x18001625b  mov     r15, r8
0x18001625e  mov     r14, rdx
0x180016261  mov     rdi, rcx
0x180016264  lea     rcx, [rsp+78h+var_50]
0x180016269  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001626e  nop
0x18001626f  mov     [rsp+78h+var_58], 0
0x180016274  lea     r8, [rsp+78h+var_58]
0x180016279  lea     rdx, [rsp+78h+var_50]
0x18001627e  mov     rcx, rdi
0x180016281  call    ?FetchCopyrightString@ServiceManager@@AEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z; ServiceManager::FetchCopyrightString(std::wstring *,bool *)
0x180016286  test    eax, eax
0x180016288  jns     short loc_1800162A8
0x18001628a  xor     ebx, ebx
0x18001628c  mov     r9, rdi
0x18001628f  mov     r8d, 0B9Bh
0x180016295  lea     rdx, aServicemanager_26; "ServiceManager::GetCopyrightString"
0x18001629c  mov     ecx, eax
0x18001629e  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800162a4  mov     edi, eax
0x1800162a6  jmp     short loc_18001631F
0x1800162a8  mov     rsi, [rsp+78h+var_40]
0x1800162ad  inc     rsi
0x1800162b0  mov     rcx, cs:qword_180035648
0x1800162b7  mov     rax, [rcx]
0x1800162ba  lea     rdx, [rsi+rsi]
0x1800162be  mov     rax, [rax]
0x1800162c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162c6  mov     rbx, rax
0x1800162c9  test    rax, rax
0x1800162cc  jnz     short loc_1800162EB
0x1800162ce  mov     r8d, 0B9Eh
0x1800162d4  mov     ecx, 8007000Eh
0x1800162d9  lea     rdx, aServicemanager_26; "ServiceManager::GetCopyrightString"
0x1800162e0  mov     r9, rdi
0x1800162e3  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800162e9  jmp     short loc_1800162A4
0x1800162eb  lea     rcx, [rsp+78h+var_50]
0x1800162f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800162f5  mov     r8, rax; unsigned __int16 *
0x1800162f8  mov     rdx, rsi; unsigned __int64
0x1800162fb  mov     rcx, rbx; unsigned __int16 *
0x1800162fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016303  test    eax, eax
0x180016305  jns     short loc_180016311
0x180016307  mov     r8d, 0B9Fh
0x18001630d  mov     ecx, eax
0x18001630f  jmp     short loc_1800162D9
0x180016311  xor     edi, edi
0x180016313  mov     [r14], rbx
0x180016316  xor     ebx, ebx
0x180016318  mov     al, [rsp+78h+var_58]
0x18001631c  mov     [r15], al
0x18001631f  mov     rcx, cs:qword_180035648
0x180016326  mov     rax, [rcx]
0x180016329  mov     rdx, rbx
0x18001632c  mov     rax, [rax+8]
0x180016330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016335  nop
0x180016336  lea     rcx, [rsp+78h+var_50]
0x18001633b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016340  mov     eax, edi
0x180016342  mov     rcx, [rsp+78h+var_30]
0x180016347  xor     rcx, rsp; StackCookie
0x18001634a  call    __security_check_cookie
0x18001634f  add     rsp, 50h
0x180016353  pop     r15
0x180016355  pop     r14
0x180016357  pop     rdi
0x180016358  pop     rsi
0x180016359  pop     rbx
0x18001635a  retn
```
