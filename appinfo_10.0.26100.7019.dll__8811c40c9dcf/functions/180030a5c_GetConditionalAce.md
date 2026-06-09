# GetConditionalAce

- ea: `0x180030a5c`
- end: `0x180030b01`
- name: `GetConditionalAce`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002d998`

## callees

- `0x180018280`
- `0x18002876c`
- `0x180030a5c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180030a73`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180030a73`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x180030abc`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x180030abc`

## string_xrefs

- `0x180030add`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall GetConditionalAce(__int64 *a1, __int64 a2)
{
  DWORD LengthSid; // eax
  __int64 v5; // rcx
  int v6; // edx
  unsigned int StringForCondition; // ebx
  __int64 v9; // [rsp+40h] [rbp-28h] BYREF
  __int64 v10; // [rsp+48h] [rbp-20h] BYREF
  char v11; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  LengthSid = GetLengthSid((PSID)(*a1 + 8));
  v5 = *a1;
  v9 = a2;
  v11 = 1;
  v6 = *(unsigned __int16 *)(v5 + 2);
  v10 = 0;
  StringForCondition = LocalGetStringForCondition(LengthSid + v5 + 8, v6 - LengthSid - 8, &v10, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v9);
  if ( StringForCondition )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x17C2,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             (const char *)StringForCondition,
             0);
  else
    return 0;
}

```

## disassembly

```asm
0x180030a5c  mov     [rsp+arg_0], rbx
0x180030a61  push    rdi
0x180030a62  sub     rsp, 60h
0x180030a66  mov     rbx, rcx
0x180030a69  mov     rdi, rdx
0x180030a6c  mov     rcx, [rcx]
0x180030a6f  add     rcx, 8; pSid
0x180030a73  call    cs:__imp_GetLengthSid
0x180030a7a  nop     dword ptr [rax+rax+00h]
0x180030a7f  mov     rcx, [rbx]
0x180030a82  lea     r8, [rsp+68h+var_20]
0x180030a87  mov     [rsp+68h+var_28], rdi
0x180030a8c  xor     r9d, r9d
0x180030a8f  xor     edi, edi
0x180030a91  mov     [rsp+68h+var_18], 1
0x180030a96  mov     [rsp+68h+var_38], dil
0x180030a9b  movzx   edx, word ptr [rcx+2]
0x180030a9f  add     rcx, 8
0x180030aa3  sub     edx, eax
0x180030aa5  mov     [rsp+68h+var_40], rdi
0x180030aaa  mov     eax, eax
0x180030aac  sub     edx, 8
0x180030aaf  add     rcx, rax
0x180030ab2  mov     [rsp+68h+var_20], rdi
0x180030ab7  mov     qword ptr [rsp+68h+var_48], rdi; unsigned int
0x180030abc  call    cs:__imp_LocalGetStringForCondition
0x180030ac3  nop     dword ptr [rax+rax+00h]
0x180030ac8  lea     rcx, [rsp+68h+var_28]
0x180030acd  mov     ebx, eax
0x180030acf  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180030ad4  test    ebx, ebx
0x180030ad6  jz      short loc_180030AF3
0x180030ad8  mov     rcx, [rsp+68h]; this
0x180030add  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180030ae4  mov     r9d, ebx; char *
0x180030ae7  mov     edx, 17C2h; void *
0x180030aec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180030af1  jmp     short loc_180030AF5
0x180030af3  xor     eax, eax
0x180030af5  mov     rbx, [rsp+68h+arg_0]
0x180030afa  add     rsp, 60h
0x180030afe  pop     rdi
0x180030aff  retn
```
