# AipInitializeSmartlockerTelemetry(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800065a0`
- end: `0x1800067d4`
- name: `?AipInitializeSmartlockerTelemetry@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `564`
- prototype: `__int64 __fastcall(union _RTL_RUN_ONCE *, void *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001bb6`
- `0x1800065a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800065bc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800065bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000663f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000676c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000663f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000676c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006705`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000679d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006705`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000679d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800066eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800066eb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800066c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800066c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000669b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000669b`
- `ADVAPI32!SetSecurityInfo` at `0x18000678f`
- `ADVAPI32!SetSecurityInfo` at `0x18000678f`
- `ADVAPI32!GetSecurityInfo` at `0x18000666f`
- `ADVAPI32!GetSecurityInfo` at `0x18000666f`

## pseudocode

```c
__int64 __fastcall AipInitializeSmartlockerTelemetry(union _RTL_RUN_ONCE *a1, void *a2, void **a3)
{
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  HANDLE CurrentProcess; // rax
  PSECURITY_DESCRIPTOR v5; // rbx
  PSECURITY_DESCRIPTOR v6; // rdi
  PACL v7; // r14
  struct _ACL *v8; // rax
  struct _ACL *v9; // rsi
  HANDLE v11; // rax
  WINBOOL bDaclDefaulted; // [rsp+40h] [rbp-40h] BYREF
  WINBOOL bDaclPresent; // [rsp+44h] [rbp-3Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-38h] BYREF
  PACL ppDacl; // [rsp+50h] [rbp-30h] BYREF
  PACL pDacl[5]; // [rsp+58h] [rbp-28h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+C8h] [rbp+48h] BYREF

  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  if ( !ThreadpoolCleanupGroup )
    return 0;
  dword_1800178F0 = 3;
  qword_1800178F8 = 0;
  xmmword_180017910 = 0;
  qword_180017920 = 0;
  dword_180017928 = 0;
  dword_18001792C = 1;
  dword_180017930 = 72;
  qword_180017900 = (__int64)ThreadpoolCleanupGroup;
  qword_180017908 = (__int64)SmCleanupGroupCancelCallback;
  SmartlockerTpCleanupGroup = ThreadpoolCleanupGroup;
  SmartlockerTpCallbackEnv = (PTP_CALLBACK_ENVIRON)&dword_1800178F0;
  ppDacl = 0;
  SecurityDescriptor = 0;
  CurrentProcess = GetCurrentProcess();
  if ( GetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, &ppDacl, 0, &SecurityDescriptor) )
    return 0;
  v5 = SecurityDescriptor;
  pDacl[1] = (PACL)SecurityDescriptor;
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0x1400;;;WD)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
  {
LABEL_8:
    if ( v5 )
      LocalFree(v5);
    return 0;
  }
  v6 = SecurityDescriptor;
  pDacl[2] = (PACL)SecurityDescriptor;
  pDacl[0] = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, pDacl, &bDaclDefaulted)
    || (v7 = pDacl[0],
        v8 = (struct _ACL *)LocalAlloc(0x40u, pDacl[0][1].AclSize + (unsigned __int64)ppDacl->AclSize),
        v9 = v8,
        (pDacl[3] = v8) == 0) )
  {
LABEL_6:
    if ( v6 )
      LocalFree(v6);
    goto LABEL_8;
  }
  memcpy_0(v8, ppDacl, ppDacl->AclSize);
  memcpy_0((char *)v9 + v9->AclSize, &v7[1], v7[1].AclSize);
  ++v9->AceCount;
  v9->AclSize += v7[1].AclSize;
  v11 = GetCurrentProcess();
  if ( SetSecurityInfo(v11, SE_KERNEL_OBJECT, 4u, 0, 0, v9, 0) )
  {
    LocalFree(v9);
    goto LABEL_6;
  }
  LocalFree(v9);
  if ( v6 )
    LocalFree(v6);
  if ( v5 )
    LocalFree(v5);
  return 1;
}

```

## disassembly

```asm
0x1800065a0  mov     [rsp-28h+arg_0], rbx
0x1800065a5  mov     [rsp-28h+arg_8], rsi
0x1800065aa  push    rbp
0x1800065ab  push    rdi
0x1800065ac  push    r12
0x1800065ae  push    r14
0x1800065b0  push    r15
0x1800065b2  mov     rbp, rsp
0x1800065b5  sub     rsp, 80h
0x1800065bc  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800065c2  xor     r15d, r15d
0x1800065c5  test    rax, rax
0x1800065c8  jz      loc_18000671A
0x1800065ce  mov     cs:dword_1800178F0, 3
0x1800065d8  mov     cs:qword_1800178F8, r15
0x1800065df  xorps   xmm0, xmm0
0x1800065e2  movdqa  cs:xmmword_180017910, xmm0
0x1800065ea  mov     cs:qword_180017920, r15
0x1800065f1  mov     cs:dword_180017928, r15d
0x1800065f8  lea     r12d, [r15+1]
0x1800065fc  mov     cs:dword_18001792C, r12d
0x180006603  mov     cs:dword_180017930, 48h ; 'H'
0x18000660d  mov     cs:qword_180017900, rax
0x180006614  lea     rcx, ?SmCleanupGroupCancelCallback@@YAXPEAX0@Z; SmCleanupGroupCancelCallback(void *,void *)
0x18000661b  mov     cs:qword_180017908, rcx
0x180006622  mov     cs:?SmartlockerTpCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * SmartlockerTpCleanupGroup
0x180006629  lea     rax, dword_1800178F0
0x180006630  mov     cs:?SmartlockerTpCallbackEnv@@3PEAU_TP_CALLBACK_ENVIRON_V3@@EA, rax; _TP_CALLBACK_ENVIRON_V3 * SmartlockerTpCallbackEnv
0x180006637  mov     [rbp+var_30], r15
0x18000663b  mov     [rbp+SecurityDescriptor], r15
0x18000663f  call    cs:__imp_GetCurrentProcess
0x180006645  mov     rcx, rax; handle
0x180006648  lea     rax, [rbp+SecurityDescriptor]
0x18000664c  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180006651  mov     [rsp+80h+ppSacl], r15; ppSacl
0x180006656  lea     rax, [rbp+var_30]
0x18000665a  mov     [rsp+80h+ppDacl], rax; ppDacl
0x18000665f  mov     [rsp+80h+ppsidGroup], r15; ppsidGroup
0x180006664  xor     r9d, r9d; ppsidOwner
0x180006667  lea     edx, [r15+6]; ObjectType
0x18000666b  lea     r8d, [r15+4]; SecurityInfo
0x18000666f  call    cs:__imp_GetSecurityInfo
0x180006675  test    eax, eax
0x180006677  jnz     loc_18000671A
0x18000667d  mov     rbx, [rbp+SecurityDescriptor]
0x180006681  mov     [rbp+var_20], rbx
0x180006685  mov     [rbp+SecurityDescriptorSize], r15d
0x180006689  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18000668d  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180006691  mov     edx, r12d; StringSDRevision
0x180006694  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x1400;;;WD)"
0x18000669b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800066a1  test    eax, eax
0x1800066a3  jz      short loc_18000670C
0x1800066a5  mov     rdi, [rbp+SecurityDescriptor]
0x1800066a9  mov     [rbp+var_18], rdi
0x1800066ad  mov     [rbp+pDacl], r15
0x1800066b1  mov     [rbp+bDaclPresent], r15d
0x1800066b5  mov     [rbp+bDaclDefaulted], r15d
0x1800066b9  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800066bd  lea     r8, [rbp+pDacl]; pDacl
0x1800066c1  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800066c5  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800066c9  call    cs:__imp_GetSecurityDescriptorDacl
0x1800066cf  test    eax, eax
0x1800066d1  jz      short loc_1800066FD
0x1800066d3  mov     r14, [rbp+pDacl]
0x1800066d7  mov     rax, [rbp+var_30]
0x1800066db  movzx   edx, word ptr [rax+2]
0x1800066df  movzx   eax, word ptr [r14+0Ah]
0x1800066e4  add     rdx, rax; uBytes
0x1800066e7  lea     ecx, [r15+40h]; uFlags
0x1800066eb  call    cs:__imp_LocalAlloc
0x1800066f1  mov     rsi, rax
0x1800066f4  mov     [rbp+var_10], rax
0x1800066f8  test    rax, rax
0x1800066fb  jnz     short loc_180006738
0x1800066fd  test    rdi, rdi
0x180006700  jz      short loc_18000670C
0x180006702  mov     rcx, rdi; hMem
0x180006705  call    cs:__imp_LocalFree
0x18000670b  nop
0x18000670c  test    rbx, rbx
0x18000670f  jz      short loc_18000671A
0x180006711  mov     rcx, rbx; hMem
0x180006714  call    cs:__imp_LocalFree
0x18000671a  xor     eax, eax
0x18000671c  lea     r11, [rsp+80h+var_s0]
0x180006724  mov     rbx, [r11+30h]
0x180006728  mov     rsi, [r11+38h]
0x18000672c  mov     rsp, r11
0x18000672f  pop     r15
0x180006731  pop     r14
0x180006733  pop     r12
0x180006735  pop     rdi
0x180006736  pop     rbp
0x180006737  retn
0x180006738  mov     rdx, [rbp+var_30]; Src
0x18000673c  movzx   r8d, word ptr [rdx+2]; Size
0x180006741  mov     rcx, rsi; void *
0x180006744  call    memcpy_0
0x180006749  movzx   r8d, word ptr [r14+0Ah]; Size
0x18000674e  movzx   ecx, word ptr [rsi+2]
0x180006752  add     rcx, rsi; void *
0x180006755  lea     rdx, [r14+8]; Src
0x180006759  call    memcpy_0
0x18000675e  add     [rsi+4], r12w
0x180006763  movzx   eax, word ptr [r14+0Ah]
0x180006768  add     [rsi+2], ax
0x18000676c  call    cs:__imp_GetCurrentProcess
0x180006772  mov     [rsp+80h+ppSacl], r15; pSacl
0x180006777  mov     [rsp+80h+ppDacl], rsi; pDacl
0x18000677c  mov     [rsp+80h+ppsidGroup], r15; psidGroup
0x180006781  xor     r9d, r9d; psidOwner
0x180006784  lea     edx, [r9+6]; ObjectType
0x180006788  lea     r8d, [r9+4]; SecurityInfo
0x18000678c  mov     rcx, rax; handle
0x18000678f  call    cs:__imp_SetSecurityInfo
0x180006795  nop
0x180006796  mov     rcx, rsi; hMem
0x180006799  test    eax, eax
0x18000679b  jz      short loc_1800067A8
0x18000679d  call    cs:__imp_LocalFree
0x1800067a3  jmp     loc_1800066FD
0x1800067a8  call    cs:__imp_LocalFree
0x1800067ae  nop
0x1800067af  test    rdi, rdi
0x1800067b2  jz      short loc_1800067BE
0x1800067b4  mov     rcx, rdi; hMem
0x1800067b7  call    cs:__imp_LocalFree
0x1800067bd  nop
0x1800067be  test    rbx, rbx
0x1800067c1  jz      short loc_1800067CC
0x1800067c3  mov     rcx, rbx; hMem
0x1800067c6  call    cs:__imp_LocalFree
0x1800067cc  mov     eax, r12d
0x1800067cf  jmp     loc_18000671C
```
