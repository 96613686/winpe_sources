# CrackPartGlobalId(ushort const *,ushort * *,uint *)

- ea: `0x18005e858`
- end: `0x18005e98d`
- name: `?CrackPartGlobalId@@YAJPEBGPEAPEAGPEAI@Z`
- size: `309`
- prototype: `__int64 __fastcall(char *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c5c0`

## callees

- `0x1800076f0`
- `0x180010da8`
- `0x18003e520`
- `0x18005e858`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18005e90d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18005e90d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e942`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e942`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CrackPartGlobalId(char *a1, unsigned __int16 **a2, unsigned int *a3)
{
  __int64 v4; // rax
  __int64 v7; // rax
  const unsigned __int16 *v8; // rbx
  __int64 last_trivial_2; // rax
  const char *v10; // r9
  unsigned __int64 v11; // rdi
  unsigned __int16 *v12; // rbx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  int v15; // eax
  int v17; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF
  wchar_t *EndPtr; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&a1[2 * v4] );
  if ( !v4 )
    goto LABEL_13;
  v7 = v4 - 1;
  if ( v7 == -1 )
    v7 = -1;
  v8 = (const unsigned __int16 *)&a1[2 * v7 + 2];
  last_trivial_2 = _std_find_last_trivial_2(a1, v8, 47);
  if ( (const unsigned __int16 *)last_trivial_2 == v8 || (v11 = (last_trivial_2 - (__int64)a1) >> 1, v11 == -1) )
  {
LABEL_13:
    v13 = -2147024773;
    v14 = 20;
    goto LABEL_14;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pv,
    a1,
    v11,
    v10);
  v12 = (unsigned __int16 *)pv;
  if ( !pv )
  {
    v13 = -2147024882;
    v14 = 23;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\devicetopologyutil.cpp",
      (const char *)v13,
      v17);
    return v13;
  }
  EndPtr = 0;
  v15 = wcstol((const wchar_t *)&a1[2 * v11 + 2], &EndPtr, 16);
  if ( ((v15 - 0x7FFFFFFF) & 0xFFFFFFFE) != 0 )
  {
    *a2 = v12;
    *a3 = v15;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\devicetopologyutil.cpp",
      (const char *)0x80004005LL,
      v17);
    CoTaskMemFree(v12);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18005e858  mov     [rsp+arg_10], rbx
0x18005e85d  mov     [rsp+arg_18], rbp
0x18005e862  push    rsi
0x18005e863  push    rdi
0x18005e864  push    r12
0x18005e866  push    r14
0x18005e868  push    r15; int
0x18005e86a  sub     rsp, 20h
0x18005e86e  xor     ebp, ebp
0x18005e870  mov     r15, r8
0x18005e873  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005e877  mov     [rdx], rbp
0x18005e87a  mov     rax, r12
0x18005e87d  mov     r14, rdx
0x18005e880  mov     rsi, rcx
0x18005e883  inc     rax
0x18005e886  cmp     [rcx+rax*2], bp
0x18005e88a  jnz     short loc_18005E883
0x18005e88c  test    rax, rax
0x18005e88f  jz      loc_18005E956
0x18005e895  dec     rax
0x18005e898  mov     r8d, 2Fh ; '/'
0x18005e89e  cmp     rax, r12
0x18005e8a1  cmovnb  rax, r12
0x18005e8a5  inc     rax
0x18005e8a8  lea     rbx, [rcx+rax*2]
0x18005e8ac  mov     rdx, rbx
0x18005e8af  call    __std_find_last_trivial_2
0x18005e8b4  mov     rdi, rax
0x18005e8b7  cmp     rax, rbx
0x18005e8ba  jz      loc_18005E956
0x18005e8c0  sub     rdi, rsi
0x18005e8c3  sar     rdi, 1
0x18005e8c6  cmp     rdi, r12
0x18005e8c9  jz      loc_18005E956
0x18005e8cf  mov     r8, rdi
0x18005e8d2  lea     rcx, [rsp+48h+pv]
0x18005e8d7  mov     rdx, rsi
0x18005e8da  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005e8df  mov     rbx, [rsp+48h+pv]
0x18005e8e4  test    rbx, rbx
0x18005e8e7  jnz     short loc_18005E8F5
0x18005e8e9  mov     ebx, 8007000Eh
0x18005e8ee  mov     edx, 17h
0x18005e8f3  jmp     short loc_18005E960
0x18005e8f5  lea     rcx, [rsi+2]
0x18005e8f9  mov     [rsp+48h+EndPtr], rbp
0x18005e8fe  lea     rcx, [rcx+rdi*2]; String
0x18005e902  mov     r8d, 10h; Radix
0x18005e908  lea     rdx, [rsp+48h+EndPtr]; EndPtr
0x18005e90d  call    cs:__imp_wcstol
0x18005e913  lea     ecx, [rax-7FFFFFFFh]
0x18005e919  test    ecx, 0FFFFFFFEh
0x18005e91f  jnz     short loc_18005E94C
0x18005e921  mov     rcx, [rsp+48h]; this
0x18005e926  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\server\\lib\\audioen"...
0x18005e92d  mov     edi, 80004005h
0x18005e932  mov     edx, 1Bh; void *
0x18005e937  mov     r9d, edi; char *
0x18005e93a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e93f  mov     rcx, rbx; pv
0x18005e942  call    cs:__imp_CoTaskMemFree
0x18005e948  mov     eax, edi
0x18005e94a  jmp     short loc_18005E976
0x18005e94c  mov     [r14], rbx
0x18005e94f  mov     [r15], eax
0x18005e952  xor     eax, eax
0x18005e954  jmp     short loc_18005E976
0x18005e956  mov     ebx, 8007007Bh
0x18005e95b  mov     edx, 14h; void *
0x18005e960  mov     rcx, [rsp+48h]; this
0x18005e965  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\server\\lib\\audioen"...
0x18005e96c  mov     r9d, ebx; char *
0x18005e96f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e974  mov     eax, ebx
0x18005e976  mov     rbx, [rsp+48h+arg_10]
0x18005e97b  mov     rbp, [rsp+48h+arg_18]
0x18005e980  add     rsp, 20h
0x18005e984  pop     r15
0x18005e986  pop     r14
0x18005e988  pop     r12
0x18005e98a  pop     rdi
0x18005e98b  pop     rsi
0x18005e98c  retn
```
