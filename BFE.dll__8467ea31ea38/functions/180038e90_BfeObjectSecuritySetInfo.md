# BfeObjectSecuritySetInfo

- ea: `0x180038e90`
- end: `0x1800390d3`
- name: `BfeObjectSecuritySetInfo`
- size: `579`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR ParentDescriptor, PSECURITY_DESCRIPTOR pSecurityDescriptor, BOOL IsContainerObject, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR, __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800573b8`
- `0x18006914c`
- `0x18006999c`
- `0x180069b1c`

## callees

- `0x180010360`
- `0x18001236c`
- `0x180012b54`
- `0x180012be0`
- `0x180018b74`
- `0x180038e90`
- `0x1800390dc`
- `0x180058b30`
- `0x180087dcc`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180038fe1`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180038fe1`
- `ntdll!RtlAllocateHeap` at `0x180038ffb`
- `ntdll!RtlAllocateHeap` at `0x180038ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039065`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180038eeb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180038eeb`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180039099`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180039099`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x18003905b`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x18003905b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180038fc2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180038fc2`

## string_xrefs

- `0x180038efb`: `GetSecurityDescriptorControl`
- `0x180038fd2`: `SetSecurityDescriptorControl`
- `0x18003906b`: `SetPrivateObjectSecurityEx`
- `0x1800390a4`: `BfeObjectSecuritySetInfo`

## pseudocode

```c
__int64 __fastcall BfeObjectSecuritySetInfo(
        PSECURITY_DESCRIPTOR ParentDescriptor,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        BOOL IsContainerObject,
        signed int SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptora,
        __int64 a6)
{
  DWORD LastError; // eax
  __int64 v11; // rcx
  const char *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rbx
  SECURITY_DESCRIPTOR_CONTROL v15; // si
  SIZE_T v16; // rbx
  PVOID Heap; // rax
  __int64 v18; // rcx
  HANDLE Token; // [rsp+30h] [rbp-38h]
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+40h] [rbp-28h] BYREF
  WORD pControl[2]; // [rsp+48h] [rbp-20h] BYREF
  DWORD dwRevision; // [rsp+4Ch] [rbp-1Ch] BYREF

  pControl[0] = 0;
  dwRevision = 0;
  ObjectsSecurityDescriptor = 0;
  Token = (HANDLE)BfeSessionGetToken();
  if ( !GetSecurityDescriptorControl(pSecurityDescriptor, pControl, &dwRevision) )
  {
    LastError = GetLastError();
    v12 = "GetSecurityDescriptorControl";
    goto LABEL_3;
  }
  if ( (SecurityInformation & 3) == 0 || (v14 = BfeAccessCheck((char *)pSecurityDescriptor, 0x80000u, 0)) == 0 )
  {
    v15 = 0;
    if ( (SecurityInformation & 4) != 0 )
    {
      v14 = BfeAccessCheck((char *)pSecurityDescriptor, 0x40000u, 0);
      if ( v14 )
        goto LABEL_26;
      if ( SecurityInformation >= 0 )
      {
        if ( (SecurityInformation & 0x20000000) == 0 )
          v15 = pControl[0] & 0x1000;
      }
      else
      {
        v15 = 4096;
      }
    }
    if ( (SecurityInformation & 8) != 0 )
    {
      v14 = BfeAccessCheck((char *)pSecurityDescriptor, 0x1000000u, 0);
      if ( v14 )
        goto LABEL_26;
      if ( (SecurityInformation & 0x40000000) != 0 )
      {
        v15 |= 0x2000u;
      }
      else if ( (SecurityInformation & 0x10000000) == 0 )
      {
        v15 |= pControl[0] & 0x2000;
      }
    }
    if ( SetSecurityDescriptorControl(pSecurityDescriptora, 0x3000u, v15) )
    {
      v16 = RtlLengthSecurityDescriptor(pSecurityDescriptor);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
      ObjectsSecurityDescriptor = Heap;
      if ( !Heap )
      {
        v13 = WfpReportSysErrorAsNtStatus(v18, "RtlAllocateHeap", 3221225495LL);
        goto LABEL_25;
      }
      memcpy_0(Heap, pSecurityDescriptor, v16);
      if ( SetPrivateObjectSecurityEx(
             SecurityInformation,
             pSecurityDescriptora,
             &ObjectsSecurityDescriptor,
             Token != 0 ? 3 : 11,
             (PGENERIC_MAPPING)&GenericMapping,
             Token) )
      {
        v13 = BfeObjectSecurityCreate(ParentDescriptor, ObjectsSecurityDescriptor, IsContainerObject, 0, a6);
        goto LABEL_25;
      }
      LastError = GetLastError();
      v12 = "SetPrivateObjectSecurityEx";
    }
    else
    {
      LastError = GetLastError();
      v12 = "SetSecurityDescriptorControl";
    }
LABEL_3:
    v13 = WfpReportSysErrorAsWinError(v11, v12, LastError);
LABEL_25:
    v14 = v13;
  }
LABEL_26:
  DestroyPrivateObjectSecurity(&ObjectsSecurityDescriptor);
  if ( v14 )
    WfpReportError(v14, "BfeObjectSecuritySetInfo");
  return v14;
}

```

## disassembly

```asm
0x180038e90  push    rbp
0x180038e92  push    rbx
0x180038e93  push    rsi
0x180038e94  push    rdi
0x180038e95  push    r12
0x180038e97  push    r13
0x180038e99  push    r14
0x180038e9b  push    r15
0x180038e9d  mov     rbp, rsp
0x180038ea0  sub     rsp, 68h
0x180038ea4  mov     rax, cs:__security_cookie
0x180038eab  xor     rax, rsp
0x180038eae  mov     [rbp+var_18], rax
0x180038eb2  mov     rax, [rbp+arg_28]
0x180038eb6  mov     edi, r9d
0x180038eb9  mov     r15, [rbp+pSecurityDescriptor]
0x180038ebd  mov     r13d, r8d
0x180038ec0  mov     [rbp+var_30], rax
0x180038ec4  mov     r14, rdx
0x180038ec7  xor     eax, eax
0x180038ec9  mov     r12, rcx
0x180038ecc  mov     [rbp+pControl], ax
0x180038ed0  mov     [rbp+dwRevision], eax
0x180038ed3  mov     [rbp+ObjectsSecurityDescriptor], rax
0x180038ed7  call    BfeSessionGetToken
0x180038edc  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180038ee0  mov     [rbp+var_38], rax
0x180038ee4  lea     rdx, [rbp+pControl]; pControl
0x180038ee8  mov     rcx, r14; pSecurityDescriptor
0x180038eeb  call    cs:__imp_GetSecurityDescriptorControl
0x180038ef1  test    eax, eax
0x180038ef3  jnz     short loc_180038F0F
0x180038ef5  call    cs:__imp_GetLastError
0x180038efb  lea     rdx, aGetsecuritydes; "GetSecurityDescriptorControl"
0x180038f02  mov     r8d, eax
0x180038f05  call    WfpReportSysErrorAsWinError
0x180038f0a  jmp     loc_180039092
0x180038f0f  test    dil, 3
0x180038f13  jz      short loc_180038F31
0x180038f15  xor     r8d, r8d
0x180038f18  mov     edx, 80000h
0x180038f1d  mov     rcx, r14; pSecurityDescriptor
0x180038f20  call    BfeAccessCheck
0x180038f25  mov     rbx, rax
0x180038f28  test    rax, rax
0x180038f2b  jnz     loc_180039095
0x180038f31  xor     esi, esi
0x180038f33  test    dil, 4
0x180038f37  jz      short loc_180038F72
0x180038f39  xor     r8d, r8d
0x180038f3c  mov     edx, 40000h
0x180038f41  mov     rcx, r14; pSecurityDescriptor
0x180038f44  call    BfeAccessCheck
0x180038f49  mov     rbx, rax
0x180038f4c  test    rax, rax
0x180038f4f  jnz     loc_180039095
0x180038f55  test    edi, edi
0x180038f57  jns     short loc_180038F60
0x180038f59  mov     esi, 1000h
0x180038f5e  jmp     short loc_180038F72
0x180038f60  bt      edi, 1Dh
0x180038f64  jb      short loc_180038F72
0x180038f66  movzx   esi, [rbp+pControl]
0x180038f6a  mov     ecx, 1000h
0x180038f6f  and     si, cx
0x180038f72  test    dil, 8
0x180038f76  jz      short loc_180038FB6
0x180038f78  xor     r8d, r8d
0x180038f7b  mov     edx, 1000000h
0x180038f80  mov     rcx, r14; pSecurityDescriptor
0x180038f83  call    BfeAccessCheck
0x180038f88  mov     rbx, rax
0x180038f8b  test    rax, rax
0x180038f8e  jnz     loc_180039095
0x180038f94  bt      edi, 1Eh
0x180038f98  jnb     short loc_180038FA1
0x180038f9a  or      si, 2000h
0x180038f9f  jmp     short loc_180038FB6
0x180038fa1  bt      edi, 1Ch
0x180038fa5  jb      short loc_180038FB6
0x180038fa7  movzx   eax, [rbp+pControl]
0x180038fab  mov     ecx, 2000h
0x180038fb0  and     ax, cx
0x180038fb3  or      si, ax
0x180038fb6  mov     edx, 3000h; ControlBitsOfInterest
0x180038fbb  movzx   r8d, si; ControlBitsToSet
0x180038fbf  mov     rcx, r15; pSecurityDescriptor
0x180038fc2  call    cs:__imp_SetSecurityDescriptorControl
0x180038fc8  test    eax, eax
0x180038fca  jnz     short loc_180038FDE
0x180038fcc  call    cs:__imp_GetLastError
0x180038fd2  lea     rdx, aSetsecuritydes; "SetSecurityDescriptorControl"
0x180038fd9  jmp     loc_180038F02
0x180038fde  mov     rcx, r14; SecurityDescriptor
0x180038fe1  call    cs:__imp_RtlLengthSecurityDescriptor
0x180038fe7  mov     rcx, gs:60h
0x180038ff0  xor     edx, edx; Flags
0x180038ff2  mov     r8d, eax; Size
0x180038ff5  mov     ebx, eax
0x180038ff7  mov     rcx, [rcx+30h]; HeapHandle
0x180038ffb  call    cs:__imp_RtlAllocateHeap
0x180039001  mov     [rbp+ObjectsSecurityDescriptor], rax
0x180039005  test    rax, rax
0x180039008  jnz     short loc_18003901E
0x18003900a  mov     r8d, 0C0000017h
0x180039010  lea     rdx, aRtlallocatehea; "RtlAllocateHeap"
0x180039017  call    WfpReportSysErrorAsNtStatus
0x18003901c  jmp     short loc_180039092
0x18003901e  mov     r8, rbx; Size
0x180039021  mov     rdx, r14; Src
0x180039024  mov     rcx, rax; void *
0x180039027  call    memcpy_0
0x18003902c  mov     rcx, [rbp+var_38]
0x180039030  lea     r8, [rbp+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x180039034  mov     rax, rcx
0x180039037  mov     [rsp+68h+Token], rcx; Token
0x18003903c  neg     rax
0x18003903f  mov     rdx, r15; ModificationDescriptor
0x180039042  lea     rax, GenericMapping
0x180039049  mov     ecx, edi; SecurityInformation
0x18003904b  sbb     r9d, r9d
0x18003904e  mov     [rsp+68h+GenericMapping], rax; GenericMapping
0x180039053  and     r9d, 0FFFFFFF8h
0x180039057  add     r9d, 0Bh; AutoInheritFlags
0x18003905b  call    cs:__imp_SetPrivateObjectSecurityEx
0x180039061  test    eax, eax
0x180039063  jnz     short loc_180039077
0x180039065  call    cs:__imp_GetLastError
0x18003906b  lea     rdx, aSetprivateobje; "SetPrivateObjectSecurityEx"
0x180039072  jmp     loc_180038F02
0x180039077  mov     rax, [rbp+var_30]
0x18003907b  xor     r9d, r9d; Token
0x18003907e  mov     rdx, [rbp+ObjectsSecurityDescriptor]; CreatorDescriptor
0x180039082  mov     r8d, r13d; IsContainerObject
0x180039085  mov     rcx, r12; ParentDescriptor
0x180039088  mov     [rsp+68h+GenericMapping], rax; __int64
0x18003908d  call    BfeObjectSecurityCreate
0x180039092  mov     rbx, rax
0x180039095  lea     rcx, [rbp+ObjectsSecurityDescriptor]; ObjectDescriptor
0x180039099  call    cs:__imp_DestroyPrivateObjectSecurity
0x18003909f  test    rbx, rbx
0x1800390a2  jz      short loc_1800390B3
0x1800390a4  lea     rdx, aBfeobjectsecur_2; "BfeObjectSecuritySetInfo"
0x1800390ab  mov     rcx, rbx
0x1800390ae  call    WfpReportError
0x1800390b3  mov     rax, rbx
0x1800390b6  mov     rcx, [rbp+var_18]
0x1800390ba  xor     rcx, rsp; StackCookie
0x1800390bd  call    __security_check_cookie
0x1800390c2  add     rsp, 68h
0x1800390c6  pop     r15
0x1800390c8  pop     r14
0x1800390ca  pop     r13
0x1800390cc  pop     r12
0x1800390ce  pop     rdi
0x1800390cf  pop     rsi
0x1800390d0  pop     rbx
0x1800390d1  pop     rbp
0x1800390d2  retn
```
