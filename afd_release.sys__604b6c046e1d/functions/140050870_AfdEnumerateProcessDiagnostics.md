# AfdEnumerateProcessDiagnostics

- ea: `0x140050870`
- end: `0x140050b82`
- name: `AfdEnumerateProcessDiagnostics`
- size: `786`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140050870`
- `0x1400726a0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005097b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005097b`
- `ntoskrnl!PsGetProcessId` at `0x140050a10`
- `ntoskrnl!PsGetProcessId` at `0x140050a10`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140050a4c`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140050a4c`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140050a71`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140050a71`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400508d4`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400508d4`
- `ntoskrnl!RtlCreateHashTableEx` at `0x140050918`
- `ntoskrnl!RtlCreateHashTableEx` at `0x140050918`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140050ad1`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140050ad1`
- `ntoskrnl!RtlDeleteHashTable` at `0x140050b3d`
- `ntoskrnl!RtlDeleteHashTable` at `0x140050b3d`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050b02`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050b02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050b53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050b53`
- `ntoskrnl!ExAllocatePool2` at `0x14005093f`
- `ntoskrnl!ExAllocatePool2` at `0x14005093f`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400509f5`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400509f5`
- `NETIO!NetioGetCompartmentNamespace` at `0x1400509cc`
- `NETIO!NetioGetCompartmentNamespace` at `0x1400509cc`
- `NETIO!NetioGetThreadCompartmentInfo` at `0x140050968`
- `NETIO!NetioGetThreadCompartmentInfo` at `0x140050968`

## pseudocode

```c
__int64 __fastcall AfdEnumerateProcessDiagnostics(__int64 a1)
{
  __int64 v1; // rbx
  int v2; // ecx
  __int64 v3; // r15
  _DWORD *Pool2; // rdi
  __int64 v5; // rsi
  __int64 v6; // r12
  __int64 *v7; // r14
  __int64 v8; // rsi
  unsigned int v9; // esi
  int v10; // r13d
  __int64 v11; // r8
  unsigned int ProcessId; // r12d
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rax
  struct _LIST_ENTRY **p_Blink; // rsi
  __int64 v15; // rdx
  __int64 i; // r8
  ULONG ReturnLength[2]; // [rsp+30h] [rbp-59h] BYREF
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+38h] [rbp-51h] BYREF
  __int64 v20; // [rsp+40h] [rbp-49h]
  __int64 v21; // [rsp+48h] [rbp-41h]
  __int64 v22; // [rsp+50h] [rbp-39h]
  _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+58h] [rbp-31h] BYREF
  __int128 v24; // [rsp+70h] [rbp-19h] BYREF
  __int64 v25; // [rsp+80h] [rbp-9h]
  __int128 v26; // [rsp+88h] [rbp-1h] BYREF

  v1 = a1;
  v20 = a1;
  v2 = *(_DWORD *)(a1 + 32);
  HashTable = 0;
  if ( v2 == 1 )
  {
    v3 = *(unsigned int *)(v1 + 88);
    Pool2 = 0;
    if ( (_DWORD)v3 )
    {
      v5 = *(_QWORD *)(v1 + 16);
      v6 = *(_QWORD *)(v1 + 56);
      v21 = v5;
      v22 = v6;
      *(_DWORD *)(v1 + 88) = 0;
      if ( (unsigned __int8)RtlCreateHashTableEx(&HashTable, 1024, 0, 0) )
      {
        Pool2 = (_DWORD *)ExAllocatePool2(64, 40 * v3, 1684301377);
        if ( Pool2 )
        {
          v24 = 0;
          v25 = 0;
          NetioGetThreadCompartmentInfo(&v24);
          ExEnterCriticalRegionAndAcquireResourceShared(AfdGlobalData);
          v7 = (__int64 *)AfdEndpointListHead;
          if ( (__int64 *)AfdEndpointListHead != &AfdEndpointListHead )
          {
            do
            {
              v8 = *(v7 - 28);
              if ( v8 )
                v9 = *(_DWORD *)(v8 + 16);
              else
                v9 = 1;
              v26 = 0;
              v10 = *((_DWORD *)v7 - 76);
              if ( (int)NetioGetCompartmentNamespace(v9, &v24, &v26) >= 0 )
              {
                LOBYTE(v11) = 1;
                if ( (unsigned __int8)NetioIsCompartmentAccessibleByThread(v9, &v26, v11, 0, &v24) )
                {
                  ProcessId = (unsigned int)PsGetProcessId((PEPROCESS)*(v7 - 33));
                  *(_QWORD *)ReturnLength = HashTable;
                  memset(&Context, 0, sizeof(Context));
                  NextEntryHashTable = RtlLookupEntryHashTable(HashTable, ProcessId | 0x80000000LL, &Context);
                  if ( NextEntryHashTable )
                  {
                    do
                    {
                      p_Blink = &NextEntryHashTable[-1].Linkage.Blink;
                      if ( LODWORD(NextEntryHashTable[-1].Linkage.Blink) == ProcessId )
                        break;
                      NextEntryHashTable = RtlGetNextEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)ReturnLength, &Context);
                    }
                    while ( NextEntryHashTable );
                    ++*((_DWORD *)p_Blink + 1);
                    v1 = v20;
                    if ( (v10 & 0x800) != 0 )
                      ++*((_DWORD *)p_Blink + 2);
                  }
                  else
                  {
                    v15 = *(unsigned int *)(v1 + 88);
                    if ( (unsigned int)v15 >= (unsigned int)v3 )
                      break;
                    *(_DWORD *)(v1 + 88) = v15 + 1;
                    Pool2[10 * v15 + 1] = 1;
                    if ( (v10 & 0x800) != 0 )
                      Pool2[10 * v15 + 2] = 1;
                    Pool2[10 * v15] = ProcessId;
                    RtlInsertEntryHashTable(
                      HashTable,
                      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)&Pool2[10 * v15 + 4],
                      ProcessId | 0x80000000LL,
                      0);
                  }
                }
              }
              v7 = (__int64 *)*v7;
            }
            while ( v7 != &AfdEndpointListHead );
            v5 = v21;
            v6 = v22;
          }
          ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
          for ( i = 0; (unsigned int)i < *(_DWORD *)(v1 + 88); i = (unsigned int)(i + 1) )
          {
            *(_DWORD *)(v5 + 4 * i) = Pool2[10 * i];
            *(_QWORD *)(v6 + 8 * i) = *(_QWORD *)&Pool2[10 * i + 1];
          }
        }
      }
    }
    else
    {
      ReturnLength[0] = 0;
      if ( ZwQuerySystemInformation(SystemProcessInformation, 0, 0, ReturnLength) == -1073741820 )
        *(_DWORD *)(v1 + 88) = ReturnLength[0] >> 8;
    }
    if ( HashTable )
      RtlDeleteHashTable(HashTable);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140050870  push    rbp
0x140050872  push    rbx
0x140050873  push    rsi
0x140050874  push    rdi
0x140050875  push    r12
0x140050877  push    r13
0x140050879  push    r14
0x14005087b  push    r15
0x14005087d  lea     rbp, [rsp-1Fh]
0x140050882  sub     rsp, 0A8h
0x140050889  mov     rax, cs:__security_cookie
0x140050890  xor     rax, rsp
0x140050893  mov     [rbp+57h+var_48], rax
0x140050897  mov     rbx, rcx
0x14005089a  mov     [rbp+57h+var_A0], rcx
0x14005089e  mov     ecx, [rcx+20h]
0x1400508a1  mov     [rbp+57h+HashTable], 0
0x1400508a9  test    ecx, ecx
0x1400508ab  jz      loc_140050B5F
0x1400508b1  cmp     ecx, 1
0x1400508b4  jnz     loc_140050B5F
0x1400508ba  mov     r15d, [rbx+58h]
0x1400508be  xor     edi, edi
0x1400508c0  xor     r8d, r8d; SystemInformationLength
0x1400508c3  test    r15d, r15d
0x1400508c6  jnz     short loc_1400508F9
0x1400508c8  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x1400508cc  mov     [rbp+57h+ReturnLength], edi
0x1400508cf  xor     edx, edx; SystemInformation
0x1400508d1  lea     ecx, [rdi+5]; SystemInformationClass
0x1400508d4  call    cs:__imp_ZwQuerySystemInformation
0x1400508db  nop     dword ptr [rax+rax+00h]
0x1400508e0  cmp     eax, 0C0000004h
0x1400508e5  jnz     loc_140050B34
0x1400508eb  mov     eax, [rbp+57h+ReturnLength]
0x1400508ee  shr     eax, 8
0x1400508f1  mov     [rbx+58h], eax
0x1400508f4  jmp     loc_140050B34
0x1400508f9  mov     rsi, [rbx+10h]
0x1400508fd  lea     rcx, [rbp+57h+HashTable]
0x140050901  mov     r12, [rbx+38h]
0x140050905  xor     r9d, r9d
0x140050908  mov     edx, 400h
0x14005090d  mov     [rbp+57h+var_98], rsi
0x140050911  mov     [rbp+57h+var_90], r12
0x140050915  mov     [rbx+58h], edi
0x140050918  call    cs:__imp_RtlCreateHashTableEx
0x14005091f  nop     dword ptr [rax+rax+00h]
0x140050924  test    al, al
0x140050926  jz      loc_140050B34
0x14005092c  lea     rdx, [r15+r15*4]
0x140050930  mov     ecx, 40h ; '@'
0x140050935  shl     rdx, 3
0x140050939  mov     r8d, 64646641h
0x14005093f  call    cs:__imp_ExAllocatePool2
0x140050946  nop     dword ptr [rax+rax+00h]
0x14005094b  mov     rdi, rax
0x14005094e  test    rax, rax
0x140050951  jz      loc_140050B34
0x140050957  xorps   xmm0, xmm0
0x14005095a  lea     rcx, [rbp+57h+var_70]
0x14005095e  xor     eax, eax
0x140050960  movups  [rbp+57h+var_70], xmm0
0x140050964  mov     [rbp+57h+var_60], rax
0x140050968  call    cs:__imp_NetioGetThreadCompartmentInfo
0x14005096f  nop     dword ptr [rax+rax+00h]
0x140050974  mov     rcx, cs:AfdGlobalData; Resource
0x14005097b  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x140050982  nop     dword ptr [rax+rax+00h]
0x140050987  mov     r14, cs:AfdEndpointListHead
0x14005098e  lea     rax, AfdEndpointListHead
0x140050995  cmp     r14, rax
0x140050998  jz      loc_140050AFB
0x14005099e  mov     rsi, [r14-0E0h]
0x1400509a5  test    rsi, rsi
0x1400509a8  jz      short loc_1400509AF
0x1400509aa  mov     esi, [rsi+10h]
0x1400509ad  jmp     short loc_1400509B4
0x1400509af  mov     esi, 1
0x1400509b4  xorps   xmm0, xmm0
0x1400509b7  lea     r8, [rbp+57h+var_58]
0x1400509bb  movups  [rbp+57h+var_58], xmm0
0x1400509bf  mov     r13d, [r14-130h]
0x1400509c6  lea     rdx, [rbp+57h+var_70]
0x1400509ca  mov     ecx, esi
0x1400509cc  call    cs:__imp_NetioGetCompartmentNamespace
0x1400509d3  nop     dword ptr [rax+rax+00h]
0x1400509d8  test    eax, eax
0x1400509da  js      loc_140050ADD
0x1400509e0  lea     rax, [rbp+57h+var_70]
0x1400509e4  xor     r9d, r9d
0x1400509e7  mov     r8b, 1
0x1400509ea  mov     [rsp+0E0h+var_C0], rax
0x1400509ef  lea     rdx, [rbp+57h+var_58]
0x1400509f3  mov     ecx, esi
0x1400509f5  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1400509fc  nop     dword ptr [rax+rax+00h]
0x140050a01  test    al, al
0x140050a03  jz      loc_140050ADD
0x140050a09  mov     rcx, [r14-108h]; Process
0x140050a10  call    cs:__imp_PsGetProcessId
0x140050a17  nop     dword ptr [rax+rax+00h]
0x140050a1c  mov     ecx, 80000000h
0x140050a21  mov     [rbp+57h+Context.Signature], 0
0x140050a29  mov     r12, rax
0x140050a2c  lea     r8, [rbp+57h+Context]; Context
0x140050a30  mov     rax, [rbp+57h+HashTable]
0x140050a34  xorps   xmm0, xmm0
0x140050a37  mov     esi, r12d
0x140050a3a  or      rsi, rcx
0x140050a3d  mov     qword ptr [rbp+57h+ReturnLength], rax
0x140050a41  mov     rdx, rsi; Signature
0x140050a44  mov     rcx, rax; HashTable
0x140050a47  movdqu  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x140050a4c  call    cs:__imp_RtlLookupEntryHashTable
0x140050a53  nop     dword ptr [rax+rax+00h]
0x140050a58  test    rax, rax
0x140050a5b  jz      short loc_140050A95
0x140050a5d  mov     rbx, qword ptr [rbp+57h+ReturnLength]
0x140050a61  lea     rsi, [rax-10h]
0x140050a65  cmp     [rsi], r12d
0x140050a68  jz      short loc_140050A82
0x140050a6a  lea     rdx, [rbp+57h+Context]; Context
0x140050a6e  mov     rcx, rbx; HashTable
0x140050a71  call    cs:__imp_RtlGetNextEntryHashTable
0x140050a78  nop     dword ptr [rax+rax+00h]
0x140050a7d  test    rax, rax
0x140050a80  jnz     short loc_140050A61
0x140050a82  inc     dword ptr [rsi+4]
0x140050a85  mov     rbx, [rbp+57h+var_A0]
0x140050a89  bt      r13d, 0Bh
0x140050a8e  jnb     short loc_140050ADD
0x140050a90  inc     dword ptr [rsi+8]
0x140050a93  jmp     short loc_140050ADD
0x140050a95  mov     edx, [rbx+58h]
0x140050a98  cmp     edx, r15d
0x140050a9b  jnb     short loc_140050AF3
0x140050a9d  lea     eax, [rdx+1]
0x140050aa0  mov     [rbx+58h], eax
0x140050aa3  mov     eax, 1
0x140050aa8  lea     rcx, [rdx+rdx*4]
0x140050aac  mov     [rdi+rcx*8+4], eax
0x140050ab0  bt      r13d, 0Bh
0x140050ab5  jnb     short loc_140050ABB
0x140050ab7  mov     [rdi+rcx*8+8], eax
0x140050abb  mov     [rdi+rcx*8], r12d
0x140050abf  xor     r9d, r9d; Context
0x140050ac2  add     rcx, 2
0x140050ac6  mov     r8, rsi; Signature
0x140050ac9  lea     rdx, [rdi+rcx*8]; Entry
0x140050acd  mov     rcx, [rbp+57h+HashTable]; HashTable
0x140050ad1  call    cs:__imp_RtlInsertEntryHashTable
0x140050ad8  nop     dword ptr [rax+rax+00h]
0x140050add  mov     rax, [r14]
0x140050ae0  lea     rcx, AfdEndpointListHead
0x140050ae7  mov     r14, rax
0x140050aea  cmp     rax, rcx
0x140050aed  jnz     loc_14005099E
0x140050af3  mov     rsi, [rbp+57h+var_98]
0x140050af7  mov     r12, [rbp+57h+var_90]
0x140050afb  mov     rcx, cs:AfdGlobalData; Resource
0x140050b02  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140050b09  nop     dword ptr [rax+rax+00h]
0x140050b0e  xor     r8d, r8d
0x140050b11  cmp     [rbx+58h], r8d
0x140050b15  jbe     short loc_140050B34
0x140050b17  lea     rcx, [r8+r8*4]
0x140050b1b  mov     eax, [rdi+rcx*8]
0x140050b1e  mov     [rsi+r8*4], eax
0x140050b22  mov     rax, [rdi+rcx*8+4]
0x140050b27  mov     [r12+r8*8], rax
0x140050b2b  inc     r8d
0x140050b2e  cmp     r8d, [rbx+58h]
0x140050b32  jb      short loc_140050B17
0x140050b34  mov     rcx, [rbp+57h+HashTable]; HashTable
0x140050b38  test    rcx, rcx
0x140050b3b  jz      short loc_140050B49
0x140050b3d  call    cs:__imp_RtlDeleteHashTable
0x140050b44  nop     dword ptr [rax+rax+00h]
0x140050b49  test    rdi, rdi
0x140050b4c  jz      short loc_140050B5F
0x140050b4e  xor     edx, edx; Tag
0x140050b50  mov     rcx, rdi; P
0x140050b53  call    cs:__imp_ExFreePoolWithTag
0x140050b5a  nop     dword ptr [rax+rax+00h]
0x140050b5f  xor     eax, eax
0x140050b61  mov     rcx, [rbp+57h+var_48]
0x140050b65  xor     rcx, rsp; StackCookie
0x140050b68  call    __security_check_cookie
0x140050b6d  add     rsp, 0A8h
0x140050b74  pop     r15
0x140050b76  pop     r14
0x140050b78  pop     r13
0x140050b7a  pop     r12
0x140050b7c  pop     rdi
0x140050b7d  pop     rsi
0x140050b7e  pop     rbx
0x140050b7f  pop     rbp
0x140050b80  retn
```
