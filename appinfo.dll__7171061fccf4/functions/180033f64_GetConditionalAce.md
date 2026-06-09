# GetConditionalAce

- ea: `0x180033f64`
- end: `0x180033ffc`
- name: `GetConditionalAce`
- size: `152`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180018ed0`

## callees

- `0x180018dbc`
- `0x18002afd8`
- `0x180033f64`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033f7b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033f7b`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x180033fbe`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x180033fbe`

## string_xrefs

- `0x180033fd9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
             (void *)0x1B0E,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             (const char *)StringForCondition,
             0);
  else
    return 0;
}

```

## disassembly

```asm
0x180033f64  mov     [rsp+arg_0], rbx
0x180033f69  push    rdi
0x180033f6a  sub     rsp, 60h
0x180033f6e  mov     rbx, rcx
0x180033f71  mov     rdi, rdx
0x180033f74  mov     rcx, [rcx]
0x180033f77  add     rcx, 8; pSid
0x180033f7b  call    cs:__imp_GetLengthSid
0x180033f81  mov     rcx, [rbx]
0x180033f84  lea     r8, [rsp+68h+var_20]
0x180033f89  mov     [rsp+68h+var_28], rdi
0x180033f8e  xor     r9d, r9d
0x180033f91  xor     edi, edi
0x180033f93  mov     [rsp+68h+var_18], 1
0x180033f98  mov     [rsp+68h+var_38], dil
0x180033f9d  movzx   edx, word ptr [rcx+2]
0x180033fa1  add     rcx, 8
0x180033fa5  sub     edx, eax
0x180033fa7  mov     [rsp+68h+var_40], rdi
0x180033fac  mov     eax, eax
0x180033fae  sub     edx, 8
0x180033fb1  add     rcx, rax
0x180033fb4  mov     [rsp+68h+var_20], rdi
0x180033fb9  mov     qword ptr [rsp+68h+var_48], rdi; unsigned int
0x180033fbe  call    cs:__imp_LocalGetStringForCondition
0x180033fc4  lea     rcx, [rsp+68h+var_28]
0x180033fc9  mov     ebx, eax
0x180033fcb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180033fd0  test    ebx, ebx
0x180033fd2  jz      short loc_180033FEF
0x180033fd4  mov     rcx, [rsp+68h]; this
0x180033fd9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180033fe0  mov     r9d, ebx; char *
0x180033fe3  mov     edx, 1B0Eh; void *
0x180033fe8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033fed  jmp     short loc_180033FF1
0x180033fef  xor     eax, eax
0x180033ff1  mov     rbx, [rsp+68h+arg_0]
0x180033ff6  add     rsp, 60h
0x180033ffa  pop     rdi
0x180033ffb  retn
```
