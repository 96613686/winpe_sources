# Dynamo::WnfGenerator::GetStateName(void)

- ea: `0x140047340`
- end: `0x1400473f5`
- name: `?GetStateName@WnfGenerator@Dynamo@@UEAA?AU_WNF_STATE_NAME@@XZ`
- size: `181`
- prototype: `struct _WNF_STATE_NAME __fastcall(Dynamo::WnfGenerator *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14003eaa8`
- `0x140047340`
- `0x1400473fc`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x1400473a5`
- `ntdll!NtCreateWnfStateName` at `0x1400473a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400473be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400473be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140047373`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140047373`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _WNF_STATE_NAME __fastcall Dynamo::WnfGenerator::GetStateName(Dynamo::WnfGenerator *this, _QWORD *a2)
{
  const char *v3; // r9
  int WnfStateName; // eax
  unsigned int v5; // r8d
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  ULONG v8; // [rsp+60h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+20h] BYREF

  *a2 = 0;
  v8 = 0;
  hMem = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;;GA;;;BA)(A;;GA;;;SY)", 1u, &hMem, &v8) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xD,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\wnfgenerator.cpp",
      v3);
  WnfStateName = NtCreateWnfStateName(a2, 1, 0);
  if ( WnfStateName < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0xE, v5, (const char *)(unsigned int)WnfStateName, 0);
  if ( hMem )
    LocalFree(hMem);
  return (struct _WNF_STATE_NAME)a2;
}

```

## disassembly

```asm
0x140047340  mov     r11, rsp
0x140047343  mov     [r11+8], rbx
0x140047347  push    rdi
0x140047348  sub     rsp, 40h
0x14004734c  mov     rbx, rdx
0x14004734f  xor     eax, eax
0x140047351  mov     [rdx], rax
0x140047354  mov     [rsp+48h+arg_10], eax
0x140047358  mov     [r11+20h], rax
0x14004735c  mov     rdi, [rsp+48h]
0x140047361  lea     r9, [r11+18h]; SecurityDescriptorSize
0x140047365  lea     r8, [r11+20h]; SecurityDescriptor
0x140047369  lea     edx, [rax+1]; StringSDRevision
0x14004736c  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;BA)(A;;GA;;;SY)"
0x140047373  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140047379  test    eax, eax
0x14004737b  jz      short loc_1400473E0
0x14004737d  mov     rax, [rsp+48h+hMem]
0x140047382  mov     [rsp+48h+var_18], rax
0x140047387  mov     [rsp+48h+var_20], 1000h
0x14004738f  mov     qword ptr [rsp+48h+var_28], 0; int
0x140047398  xor     r9d, r9d
0x14004739b  xor     r8d, r8d
0x14004739e  lea     edx, [r9+1]
0x1400473a2  mov     rcx, rbx
0x1400473a5  call    cs:__imp_NtCreateWnfStateName
0x1400473ab  mov     rcx, [rsp+48h]; this
0x1400473b0  test    eax, eax
0x1400473b2  js      short loc_1400473D2
0x1400473b4  mov     rcx, [rsp+48h+hMem]; hMem
0x1400473b9  test    rcx, rcx
0x1400473bc  jz      short loc_1400473C4
0x1400473be  call    cs:__imp_LocalFree
0x1400473c4  mov     rax, rbx
0x1400473c7  mov     rbx, [rsp+48h+arg_0]
0x1400473cc  add     rsp, 40h
0x1400473d0  pop     rdi
0x1400473d1  retn
0x1400473d2  mov     r9d, eax; char *
0x1400473d5  mov     edx, 0Eh; void *
0x1400473da  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400473e0  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400473e7  mov     edx, 0Dh; void *
0x1400473ec  mov     rcx, rdi; this
0x1400473ef  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
