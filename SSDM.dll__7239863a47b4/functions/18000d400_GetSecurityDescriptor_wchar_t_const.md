# GetSecurityDescriptor(wchar_t const *)

- ea: `0x18000d400`
- end: `0x18000d4a2`
- name: `?GetSecurityDescriptor@@YA?AV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@PEB_W@Z`
- size: `162`
- prototype: `PSECURITY_DESCRIPTOR *__fastcall(PSECURITY_DESCRIPTOR *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c9a8`
- `0x18000cd88`

## callees

- `0x180007468`
- `0x18000d400`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000d455`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000d455`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d47c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d47c`

## pseudocode

```c
PSECURITY_DESCRIPTOR *__fastcall GetSecurityDescriptor(PSECURITY_DESCRIPTOR *a1, __int64 a2)
{
  const char *v3; // r9
  PSECURITY_DESCRIPTOR v4; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-10h] BYREF
  char v8; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  ULONG SecurityDescriptorSize; // [rsp+58h] [rbp+18h] BYREF
  int v11; // [rsp+5Ch] [rbp+1Ch]

  v11 = HIDWORD(a2);
  SecurityDescriptorSize = 0;
  *a1 = 0;
  SecurityDescriptor = 0;
  v8 = 1;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;OICI;GR;;;WD)(A;OICI;GR;;;AC)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB,
      (int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      v3);
  if ( v8 )
  {
    v4 = *a1;
    *a1 = SecurityDescriptor;
    if ( v4 )
      LocalFree(v4);
  }
  return a1;
}

```

## disassembly

```asm
0x18000d400  mov     [rsp-8+arg_10], rbx
0x18000d405  mov     qword ptr [rsp-8+SecurityDescriptorSize], rdx
0x18000d40a  mov     [rsp-8+arg_0], rcx
0x18000d40f  push    rbp
0x18000d410  mov     rbp, rsp
0x18000d413  sub     rsp, 40h
0x18000d417  mov     rbx, rcx
0x18000d41a  mov     [rbp+var_20], 0
0x18000d421  mov     [rbp+SecurityDescriptorSize], 0
0x18000d428  mov     qword ptr [rcx], 0
0x18000d42f  mov     edx, 1; StringSDRevision
0x18000d434  mov     [rbp+var_20], edx
0x18000d437  mov     [rbp+var_18], rcx
0x18000d43b  mov     [rbp+SecurityDescriptor], 0
0x18000d443  mov     [rbp+var_8], dl
0x18000d446  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18000d44a  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000d44e  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;GR;;;WD)(A;OICI;GR;;;AC)"
0x18000d455  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000d45b  mov     rcx, [rbp+8]; this
0x18000d45f  test    eax, eax
0x18000d461  jz      short loc_18000D490
0x18000d463  cmp     [rbp+var_8], 0
0x18000d467  jz      short loc_18000D482
0x18000d469  mov     rdx, [rbp+var_18]
0x18000d46d  mov     rcx, [rdx]; hMem
0x18000d470  mov     rax, [rbp+SecurityDescriptor]
0x18000d474  mov     [rdx], rax
0x18000d477  test    rcx, rcx
0x18000d47a  jz      short loc_18000D482
0x18000d47c  call    cs:__imp_LocalFree
0x18000d482  mov     rax, rbx
0x18000d485  mov     rbx, [rsp+40h+arg_10]
0x18000d48a  add     rsp, 40h
0x18000d48e  pop     rbp
0x18000d48f  retn
0x18000d490  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000d497  mov     edx, 0Bh; void *
0x18000d49c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
