# GetConditionalAce

- ea: `0x180030448`
- end: `0x1800304ed`
- name: `GetConditionalAce`
- size: `165`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002c448`

## callees

- `0x180018530`
- `0x1800271fc`
- `0x180030448`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003045f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003045f`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x1800304a8`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x1800304a8`

## string_xrefs

- `0x1800304c9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
             (void *)0x18C6,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             (const char *)StringForCondition,
             0);
  else
    return 0;
}

```

## disassembly

```asm
0x180030448  mov     [rsp+arg_0], rbx
0x18003044d  push    rdi
0x18003044e  sub     rsp, 60h
0x180030452  mov     rbx, rcx
0x180030455  mov     rdi, rdx
0x180030458  mov     rcx, [rcx]
0x18003045b  add     rcx, 8; pSid
0x18003045f  call    cs:__imp_GetLengthSid
0x180030466  nop     dword ptr [rax+rax+00h]
0x18003046b  mov     rcx, [rbx]
0x18003046e  lea     r8, [rsp+68h+var_20]
0x180030473  mov     [rsp+68h+var_28], rdi
0x180030478  xor     r9d, r9d
0x18003047b  xor     edi, edi
0x18003047d  mov     [rsp+68h+var_18], 1
0x180030482  mov     [rsp+68h+var_38], dil
0x180030487  movzx   edx, word ptr [rcx+2]
0x18003048b  add     rcx, 8
0x18003048f  sub     edx, eax
0x180030491  mov     [rsp+68h+var_40], rdi
0x180030496  mov     eax, eax
0x180030498  sub     edx, 8
0x18003049b  add     rcx, rax
0x18003049e  mov     [rsp+68h+var_20], rdi
0x1800304a3  mov     qword ptr [rsp+68h+var_48], rdi; unsigned int
0x1800304a8  call    cs:__imp_LocalGetStringForCondition
0x1800304af  nop     dword ptr [rax+rax+00h]
0x1800304b4  lea     rcx, [rsp+68h+var_28]
0x1800304b9  mov     ebx, eax
0x1800304bb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800304c0  test    ebx, ebx
0x1800304c2  jz      short loc_1800304DF
0x1800304c4  mov     rcx, [rsp+68h]; this
0x1800304c9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800304d0  mov     r9d, ebx; char *
0x1800304d3  mov     edx, 18C6h; void *
0x1800304d8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800304dd  jmp     short loc_1800304E1
0x1800304df  xor     eax, eax
0x1800304e1  mov     rbx, [rsp+68h+arg_0]
0x1800304e6  add     rsp, 60h
0x1800304ea  pop     rdi
0x1800304eb  retn
```
