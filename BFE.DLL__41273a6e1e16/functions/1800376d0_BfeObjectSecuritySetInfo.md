# BfeObjectSecuritySetInfo

- ea: `0x1800376d0`
- end: `0x18003794d`
- name: `BfeObjectSecuritySetInfo`
- size: `637`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR ParentDescriptor, PSECURITY_DESCRIPTOR pSecurityDescriptor, BOOL IsContainerObject, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR, __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800590dc`
- `0x18006b6f0`
- `0x18006bf70`
- `0x18006c100`

## callees

- `0x180010d60`
- `0x180012d8c`
- `0x1800135ac`
- `0x180013640`
- `0x1800197d0`
- `0x1800376d0`
- `0x180037954`
- `0x18005aa60`
- `0x18008ad6c`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180037839`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180037839`
- `ntdll!RtlAllocateHeap` at `0x180037859`
- `ntdll!RtlAllocateHeap` at `0x180037859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003773b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003781e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003773b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003781e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378d2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18003772b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18003772b`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18003790c`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18003790c`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1800378c2`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1800378c2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18003780e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18003780e`

## string_xrefs

- `0x180037747`: `GetSecurityDescriptorControl`
- `0x18003782a`: `SetSecurityDescriptorControl`
- `0x1800378de`: `SetPrivateObjectSecurityEx`
- `0x18003791d`: `BfeObjectSecuritySetInfo`

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
  if ( (SecurityInformation & 3) == 0 || (v14 = BfeAccessCheck(pSecurityDescriptor)) == 0 )
  {
    v15 = 0;
    if ( (SecurityInformation & 4) != 0 )
    {
      v14 = BfeAccessCheck(pSecurityDescriptor);
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
      v14 = BfeAccessCheck(pSecurityDescriptor);
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
0x1800376d0  push    rbp
0x1800376d2  push    rbx
0x1800376d3  push    rsi
0x1800376d4  push    rdi
0x1800376d5  push    r12
0x1800376d7  push    r13
0x1800376d9  push    r14
0x1800376db  push    r15
0x1800376dd  mov     rbp, rsp
0x1800376e0  sub     rsp, 68h
0x1800376e4  mov     rax, cs:__security_cookie
0x1800376eb  xor     rax, rsp
0x1800376ee  mov     [rbp+var_18], rax
0x1800376f2  mov     rax, [rbp+arg_28]
0x1800376f6  mov     edi, r9d
0x1800376f9  mov     r15, [rbp+pSecurityDescriptor]
0x1800376fd  mov     r13d, r8d
0x180037700  mov     [rbp+var_30], rax
0x180037704  mov     r14, rdx
0x180037707  xor     eax, eax
0x180037709  mov     r12, rcx
0x18003770c  mov     [rbp+pControl], ax
0x180037710  mov     [rbp+dwRevision], eax
0x180037713  mov     [rbp+ObjectsSecurityDescriptor], rax
0x180037717  call    BfeSessionGetToken
0x18003771c  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180037720  mov     [rbp+var_38], rax
0x180037724  lea     rdx, [rbp+pControl]; pControl
0x180037728  mov     rcx, r14; pSecurityDescriptor
0x18003772b  call    cs:__imp_GetSecurityDescriptorControl
0x180037732  nop     dword ptr [rax+rax+00h]
0x180037737  test    eax, eax
0x180037739  jnz     short loc_18003775B
0x18003773b  call    cs:__imp_GetLastError
0x180037742  nop     dword ptr [rax+rax+00h]
0x180037747  lea     rdx, aGetsecuritydes; "GetSecurityDescriptorControl"
0x18003774e  mov     r8d, eax
0x180037751  call    WfpReportSysErrorAsWinError
0x180037756  jmp     loc_180037905
0x18003775b  test    dil, 3
0x18003775f  jz      short loc_18003777D
0x180037761  xor     r8d, r8d
0x180037764  mov     edx, 80000h
0x180037769  mov     rcx, r14; pSecurityDescriptor
0x18003776c  call    BfeAccessCheck
0x180037771  mov     rbx, rax
0x180037774  test    rax, rax
0x180037777  jnz     loc_180037908
0x18003777d  xor     esi, esi
0x18003777f  test    dil, 4
0x180037783  jz      short loc_1800377BE
0x180037785  xor     r8d, r8d
0x180037788  mov     edx, 40000h
0x18003778d  mov     rcx, r14; pSecurityDescriptor
0x180037790  call    BfeAccessCheck
0x180037795  mov     rbx, rax
0x180037798  test    rax, rax
0x18003779b  jnz     loc_180037908
0x1800377a1  test    edi, edi
0x1800377a3  jns     short loc_1800377AC
0x1800377a5  mov     esi, 1000h
0x1800377aa  jmp     short loc_1800377BE
0x1800377ac  bt      edi, 1Dh
0x1800377b0  jb      short loc_1800377BE
0x1800377b2  movzx   esi, [rbp+pControl]
0x1800377b6  mov     ecx, 1000h
0x1800377bb  and     si, cx
0x1800377be  test    dil, 8
0x1800377c2  jz      short loc_180037802
0x1800377c4  xor     r8d, r8d
0x1800377c7  mov     edx, 1000000h
0x1800377cc  mov     rcx, r14; pSecurityDescriptor
0x1800377cf  call    BfeAccessCheck
0x1800377d4  mov     rbx, rax
0x1800377d7  test    rax, rax
0x1800377da  jnz     loc_180037908
0x1800377e0  bt      edi, 1Eh
0x1800377e4  jnb     short loc_1800377ED
0x1800377e6  or      si, 2000h
0x1800377eb  jmp     short loc_180037802
0x1800377ed  bt      edi, 1Ch
0x1800377f1  jb      short loc_180037802
0x1800377f3  movzx   eax, [rbp+pControl]
0x1800377f7  mov     ecx, 2000h
0x1800377fc  and     ax, cx
0x1800377ff  or      si, ax
0x180037802  mov     edx, 3000h; ControlBitsOfInterest
0x180037807  movzx   r8d, si; ControlBitsToSet
0x18003780b  mov     rcx, r15; pSecurityDescriptor
0x18003780e  call    cs:__imp_SetSecurityDescriptorControl
0x180037815  nop     dword ptr [rax+rax+00h]
0x18003781a  test    eax, eax
0x18003781c  jnz     short loc_180037836
0x18003781e  call    cs:__imp_GetLastError
0x180037825  nop     dword ptr [rax+rax+00h]
0x18003782a  lea     rdx, aSetsecuritydes; "SetSecurityDescriptorControl"
0x180037831  jmp     loc_18003774E
0x180037836  mov     rcx, r14; SecurityDescriptor
0x180037839  call    cs:__imp_RtlLengthSecurityDescriptor
0x180037840  nop     dword ptr [rax+rax+00h]
0x180037845  mov     rcx, gs:60h
0x18003784e  xor     edx, edx; Flags
0x180037850  mov     r8d, eax; Size
0x180037853  mov     ebx, eax
0x180037855  mov     rcx, [rcx+30h]; HeapHandle
0x180037859  call    cs:__imp_RtlAllocateHeap
0x180037860  nop     dword ptr [rax+rax+00h]
0x180037865  mov     [rbp+ObjectsSecurityDescriptor], rax
0x180037869  test    rax, rax
0x18003786c  jnz     short loc_180037885
0x18003786e  mov     r8d, 0C0000017h
0x180037874  lea     rdx, aRtlallocatehea; "RtlAllocateHeap"
0x18003787b  call    WfpReportSysErrorAsNtStatus
0x180037880  jmp     loc_180037905
0x180037885  mov     r8, rbx; Size
0x180037888  mov     rdx, r14; Src
0x18003788b  mov     rcx, rax; void *
0x18003788e  call    memcpy_0
0x180037893  mov     rcx, [rbp+var_38]
0x180037897  lea     r8, [rbp+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x18003789b  mov     rax, rcx
0x18003789e  mov     [rsp+68h+Token], rcx; Token
0x1800378a3  neg     rax
0x1800378a6  mov     rdx, r15; ModificationDescriptor
0x1800378a9  lea     rax, GenericMapping
0x1800378b0  mov     ecx, edi; SecurityInformation
0x1800378b2  sbb     r9d, r9d
0x1800378b5  mov     [rsp+68h+GenericMapping], rax; GenericMapping
0x1800378ba  and     r9d, 0FFFFFFF8h
0x1800378be  add     r9d, 0Bh; AutoInheritFlags
0x1800378c2  call    cs:__imp_SetPrivateObjectSecurityEx
0x1800378c9  nop     dword ptr [rax+rax+00h]
0x1800378ce  test    eax, eax
0x1800378d0  jnz     short loc_1800378EA
0x1800378d2  call    cs:__imp_GetLastError
0x1800378d9  nop     dword ptr [rax+rax+00h]
0x1800378de  lea     rdx, aSetprivateobje; "SetPrivateObjectSecurityEx"
0x1800378e5  jmp     loc_18003774E
0x1800378ea  mov     rax, [rbp+var_30]
0x1800378ee  xor     r9d, r9d; Token
0x1800378f1  mov     rdx, [rbp+ObjectsSecurityDescriptor]; CreatorDescriptor
0x1800378f5  mov     r8d, r13d; IsContainerObject
0x1800378f8  mov     rcx, r12; ParentDescriptor
0x1800378fb  mov     [rsp+68h+GenericMapping], rax; __int64
0x180037900  call    BfeObjectSecurityCreate
0x180037905  mov     rbx, rax
0x180037908  lea     rcx, [rbp+ObjectsSecurityDescriptor]; ObjectDescriptor
0x18003790c  call    cs:__imp_DestroyPrivateObjectSecurity
0x180037913  nop     dword ptr [rax+rax+00h]
0x180037918  test    rbx, rbx
0x18003791b  jz      short loc_18003792C
0x18003791d  lea     rdx, aBfeobjectsecur_2; "BfeObjectSecuritySetInfo"
0x180037924  mov     rcx, rbx
0x180037927  call    WfpReportError
0x18003792c  mov     rax, rbx
0x18003792f  mov     rcx, [rbp+var_18]
0x180037933  xor     rcx, rsp; StackCookie
0x180037936  call    __security_check_cookie
0x18003793b  add     rsp, 68h
0x18003793f  pop     r15
0x180037941  pop     r14
0x180037943  pop     r13
0x180037945  pop     r12
0x180037947  pop     rdi
0x180037948  pop     rsi
0x180037949  pop     rbx
0x18003794a  pop     rbp
0x18003794b  retn
```
