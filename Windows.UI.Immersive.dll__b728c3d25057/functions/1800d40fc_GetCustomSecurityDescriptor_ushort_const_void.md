# GetCustomSecurityDescriptor(ushort const *,void *)

- ea: `0x1800d40fc`
- end: `0x1800d4254`
- name: `?GetCustomSecurityDescriptor@@YAJPEBGPEAX@Z`
- size: `344`
- prototype: `int(const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c994`
- `0x1800d3d80`

## callees

- `0x18003aa84`
- `0x1800d3b04`
- `0x1800d3c54`
- `0x1800d3f2c`
- `0x1800d40fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d4222`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d423c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d4222`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d423c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800d4205`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800d4205`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800d41e5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800d41e5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800d41c2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800d41c2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800d4163`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800d4163`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800d4124`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800d4124`

## pseudocode

```c
__int64 __fastcall GetCustomSecurityDescriptor(const unsigned __int16 *a1, void *a2)
{
  int Error; // ebx
  int v4; // r9d
  void *v5; // rdx
  unsigned int v6; // edx
  CAceList *v8; // [rsp+20h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+28h] [rbp-18h] BYREF
  PACL v10; // [rsp+30h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+60h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+68h] [rbp+28h] BYREF

  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a1, 1u, &SecurityDescriptor, 0)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    pDacl = 0;
    bDaclDefaulted = 0;
    bDaclPresent = 0;
    if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_17;
    }
    v8 = 0;
    Error = CAceList::CreateInstance(pDacl, SecurityDescriptor, &v8, v4);
    if ( Error < 0 )
      goto LABEL_17;
    v10 = 0;
    Error = CAceList::GetAclForExplicitEntries(v8, v5, &v10);
    if ( Error >= 0 )
    {
      if ( !InitializeSecurityDescriptor(a2, 1u) )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_14;
      }
      if ( !SetSecurityDescriptorDacl(a2, 1, v10, 0) )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_14;
      }
      if ( SetSecurityDescriptorControl(a2, 0x1000u, 0x1000u) )
      {
        Error = 0;
        goto LABEL_15;
      }
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
LABEL_14:
        LocalFree(v10);
    }
LABEL_15:
    if ( v8 )
      CAceList::`scalar deleting destructor'(v8, v6);
LABEL_17:
    LocalFree(SecurityDescriptor);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d40fc  mov     [rsp-8+arg_0], rbx
0x1800d4101  mov     [rsp-8+arg_8], rsi
0x1800d4106  push    rbp
0x1800d4107  mov     rbp, rsp
0x1800d410a  sub     rsp, 40h
0x1800d410e  xor     r9d, r9d; SecurityDescriptorSize
0x1800d4111  mov     [rbp+SecurityDescriptor], 0
0x1800d4119  mov     rsi, rdx
0x1800d411c  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800d4120  lea     edx, [r9+1]; StringSDRevision
0x1800d4124  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800d412a  test    eax, eax
0x1800d412c  jnz     short loc_1800D413D
0x1800d412e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d4133  mov     ebx, eax
0x1800d4135  test    eax, eax
0x1800d4137  js      loc_1800D4242
0x1800d413d  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800d4141  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800d4145  lea     r8, [rbp+pDacl]; pDacl
0x1800d4149  mov     [rbp+pDacl], 0
0x1800d4151  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800d4155  mov     [rbp+bDaclDefaulted], 0
0x1800d415c  mov     [rbp+bDaclPresent], 0
0x1800d4163  call    cs:__imp_GetSecurityDescriptorDacl
0x1800d4169  test    eax, eax
0x1800d416b  jnz     short loc_1800D417C
0x1800d416d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d4172  mov     ebx, eax
0x1800d4174  test    eax, eax
0x1800d4176  js      loc_1800D4238
0x1800d417c  mov     rdx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800d4180  lea     r8, [rbp+var_20]; struct CAceList **
0x1800d4184  mov     rcx, [rbp+pDacl]; struct _ACL *
0x1800d4188  mov     [rbp+var_20], 0
0x1800d4190  call    ?CreateInstance@CAceList@@SAJPEAU_ACL@@PEAXPEAPEAV1@H@Z; CAceList::CreateInstance(_ACL *,void *,CAceList * *,int)
0x1800d4195  mov     ebx, eax
0x1800d4197  test    eax, eax
0x1800d4199  js      loc_1800D4238
0x1800d419f  mov     rcx, [rbp+var_20]; this
0x1800d41a3  lea     r8, [rbp+var_10]; struct _ACL **
0x1800d41a7  mov     [rbp+var_10], 0
0x1800d41af  call    ?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z; CAceList::GetAclForExplicitEntries(void *,_ACL * *)
0x1800d41b4  mov     ebx, eax
0x1800d41b6  test    eax, eax
0x1800d41b8  js      short loc_1800D4228
0x1800d41ba  mov     edx, 1; dwRevision
0x1800d41bf  mov     rcx, rsi; pSecurityDescriptor
0x1800d41c2  call    cs:__imp_InitializeSecurityDescriptor
0x1800d41c8  test    eax, eax
0x1800d41ca  jnz     short loc_1800D41D7
0x1800d41cc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d41d1  mov     ebx, eax
0x1800d41d3  test    eax, eax
0x1800d41d5  js      short loc_1800D421E
0x1800d41d7  mov     r8, [rbp+var_10]; pDacl
0x1800d41db  xor     r9d, r9d; bDaclDefaulted
0x1800d41de  mov     rcx, rsi; pSecurityDescriptor
0x1800d41e1  lea     edx, [r9+1]; bDaclPresent
0x1800d41e5  call    cs:__imp_SetSecurityDescriptorDacl
0x1800d41eb  test    eax, eax
0x1800d41ed  jnz     short loc_1800D41FA
0x1800d41ef  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d41f4  mov     ebx, eax
0x1800d41f6  test    eax, eax
0x1800d41f8  js      short loc_1800D421E
0x1800d41fa  mov     edx, 1000h; ControlBitsOfInterest
0x1800d41ff  mov     rcx, rsi; pSecurityDescriptor
0x1800d4202  mov     r8d, edx; ControlBitsToSet
0x1800d4205  call    cs:__imp_SetSecurityDescriptorControl
0x1800d420b  test    eax, eax
0x1800d420d  jz      short loc_1800D4213
0x1800d420f  xor     ebx, ebx
0x1800d4211  jmp     short loc_1800D4228
0x1800d4213  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d4218  mov     ebx, eax
0x1800d421a  test    eax, eax
0x1800d421c  jns     short loc_1800D4228
0x1800d421e  mov     rcx, [rbp+var_10]; hMem
0x1800d4222  call    cs:__imp_LocalFree
0x1800d4228  cmp     [rbp+var_20], 0
0x1800d422d  jz      short loc_1800D4238
0x1800d422f  mov     rcx, [rbp+var_20]; this
0x1800d4233  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x1800d4238  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800d423c  call    cs:__imp_LocalFree
0x1800d4242  mov     rsi, [rsp+40h+arg_8]
0x1800d4247  mov     eax, ebx
0x1800d4249  mov     rbx, [rsp+40h+arg_0]
0x1800d424e  add     rsp, 40h
0x1800d4252  pop     rbp
0x1800d4253  retn
```
