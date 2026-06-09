# ServiceManager::UpdateCachedCopyright(void)

- ea: `0x18001d9a0`
- end: `0x18001da7b`
- name: `?UpdateCachedCopyright@ServiceManager@@AEAAJXZ`
- size: `219`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180016b60`

## callees

- `0x180003410`
- `0x1800079d4`
- `0x180008110`
- `0x18000816c`
- `0x180015b40`
- `0x18001d9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001da10`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001da10`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001da4a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001da4a`

## string_xrefs

- `0x18001da41`: `ServiceManager::UpdateCachedCopyright`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::UpdateCachedCopyright(ServiceManager *this)
{
  int CopyrightString; // eax
  unsigned int v3; // edi
  unsigned int i; // ebx
  int v5; // r8d
  bool v7; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v8[16]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v9; // [rsp+38h] [rbp-20h]

  std::wstring::wstring((__int64)v8);
  v7 = 0;
  CopyrightString = ServiceManager::FetchCopyrightString(this, (__int64)v8, &v7);
  if ( CopyrightString < 0 )
  {
    v5 = 1888;
LABEL_9:
    v3 = ZTraceReportPropagation(CopyrightString, "ServiceManager::UpdateCachedCopyright", v5, this);
  }
  else
  {
    v3 = 0;
    for ( i = 0; !v7 && i < 0xA; ++i )
    {
      v9 = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
      Sleep(0x12Cu);
      CopyrightString = ServiceManager::FetchCopyrightString(this, (__int64)v8, &v7);
      if ( CopyrightString < 0 )
      {
        v5 = 1893;
        goto LABEL_9;
      }
    }
  }
  std::wstring::_Tidy_deallocate((__int64)v8);
  return v3;
}

```

## disassembly

```asm
0x18001d9a0  mov     [rsp+arg_8], rbx
0x18001d9a5  mov     [rsp+arg_10], rsi
0x18001d9aa  push    rdi
0x18001d9ab  sub     rsp, 50h
0x18001d9af  mov     rax, cs:__security_cookie
0x18001d9b6  xor     rax, rsp
0x18001d9b9  mov     [rsp+58h+var_10], rax
0x18001d9be  mov     rsi, rcx
0x18001d9c1  lea     rcx, [rsp+58h+var_30]
0x18001d9c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d9cb  nop
0x18001d9cc  mov     [rsp+58h+var_38], 0
0x18001d9d1  lea     r8, [rsp+58h+var_38]
0x18001d9d6  lea     rdx, [rsp+58h+var_30]
0x18001d9db  mov     rcx, rsi
0x18001d9de  call    ?FetchCopyrightString@ServiceManager@@AEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z; ServiceManager::FetchCopyrightString(std::wstring *,bool *)
0x18001d9e3  test    eax, eax
0x18001d9e5  js      short loc_18001DA38
0x18001d9e7  xor     edi, edi
0x18001d9e9  xor     ebx, ebx
0x18001d9eb  cmp     [rsp+58h+var_38], dil
0x18001d9f0  jnz     short loc_18001DA52
0x18001d9f2  cmp     ebx, 0Ah
0x18001d9f5  jnb     short loc_18001DA52
0x18001d9f7  mov     [rsp+58h+var_20], rdi
0x18001d9fc  lea     rcx, [rsp+58h+var_30]
0x18001da01  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001da06  xor     ecx, ecx
0x18001da08  mov     [rax], cx
0x18001da0b  mov     ecx, 12Ch; dwMilliseconds
0x18001da10  call    cs:__imp_Sleep
0x18001da16  lea     r8, [rsp+58h+var_38]
0x18001da1b  lea     rdx, [rsp+58h+var_30]
0x18001da20  mov     rcx, rsi
0x18001da23  call    ?FetchCopyrightString@ServiceManager@@AEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z; ServiceManager::FetchCopyrightString(std::wstring *,bool *)
0x18001da28  test    eax, eax
0x18001da2a  js      short loc_18001DA30
0x18001da2c  inc     ebx
0x18001da2e  jmp     short loc_18001D9EB
0x18001da30  mov     r8d, 765h
0x18001da36  jmp     short loc_18001DA3E
0x18001da38  mov     r8d, 760h
0x18001da3e  mov     r9, rsi
0x18001da41  lea     rdx, aServicemanager_12; "ServiceManager::UpdateCachedCopyright"
0x18001da48  mov     ecx, eax
0x18001da4a  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001da50  mov     edi, eax
0x18001da52  lea     rcx, [rsp+58h+var_30]
0x18001da57  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001da5c  mov     eax, edi
0x18001da5e  mov     rcx, [rsp+58h+var_10]
0x18001da63  xor     rcx, rsp; StackCookie
0x18001da66  call    __security_check_cookie
0x18001da6b  mov     rbx, [rsp+58h+arg_8]
0x18001da70  mov     rsi, [rsp+58h+arg_10]
0x18001da75  add     rsp, 50h
0x18001da79  pop     rdi
0x18001da7a  retn
```
