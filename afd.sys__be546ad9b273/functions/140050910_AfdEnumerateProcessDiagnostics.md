# AfdEnumerateProcessDiagnostics

- ea: `0x140050910`
- end: `0x140050c22`
- name: `AfdEnumerateProcessDiagnostics`
- size: `786`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140050910`
- `0x140072840`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140050a1b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140050a1b`
- `ntoskrnl!PsGetProcessId` at `0x140050ab0`
- `ntoskrnl!PsGetProcessId` at `0x140050ab0`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140050aec`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140050aec`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140050b11`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140050b11`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140050974`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140050974`
- `ntoskrnl!RtlCreateHashTableEx` at `0x1400509b8`
- `ntoskrnl!RtlCreateHashTableEx` at `0x1400509b8`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140050b71`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140050b71`
- `ntoskrnl!RtlDeleteHashTable` at `0x140050bdd`
- `ntoskrnl!RtlDeleteHashTable` at `0x140050bdd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050ba2`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050ba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050bf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050bf3`
- `ntoskrnl!ExAllocatePool2` at `0x1400509df`
- `ntoskrnl!ExAllocatePool2` at `0x1400509df`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140050a95`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140050a95`
- `NETIO!NetioGetCompartmentNamespace` at `0x140050a6c`
- `NETIO!NetioGetCompartmentNamespace` at `0x140050a6c`
- `NETIO!NetioGetThreadCompartmentInfo` at `0x140050a08`
- `NETIO!NetioGetThreadCompartmentInfo` at `0x140050a08`

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
0x140050910  push    rbp
0x140050912  push    rbx
0x140050913  push    rsi
0x140050914  push    rdi
0x140050915  push    r12
0x140050917  push    r13
0x140050919  push    r14
0x14005091b  push    r15
0x14005091d  lea     rbp, [rsp-1Fh]
0x140050922  sub     rsp, 0A8h
0x140050929  mov     rax, cs:__security_cookie
0x140050930  xor     rax, rsp
0x140050933  mov     [rbp+57h+var_48], rax
0x140050937  mov     rbx, rcx
0x14005093a  mov     [rbp+57h+var_A0], rcx
0x14005093e  mov     ecx, [rcx+20h]
0x140050941  mov     [rbp+57h+HashTable], 0
0x140050949  test    ecx, ecx
0x14005094b  jz      loc_140050BFF
0x140050951  cmp     ecx, 1
0x140050954  jnz     loc_140050BFF
0x14005095a  mov     r15d, [rbx+58h]
0x14005095e  xor     edi, edi
0x140050960  xor     r8d, r8d; SystemInformationLength
0x140050963  test    r15d, r15d
0x140050966  jnz     short loc_140050999
0x140050968  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x14005096c  mov     [rbp+57h+ReturnLength], edi
0x14005096f  xor     edx, edx; SystemInformation
0x140050971  lea     ecx, [rdi+5]; SystemInformationClass
0x140050974  call    cs:__imp_ZwQuerySystemInformation
0x14005097b  nop     dword ptr [rax+rax+00h]
0x140050980  cmp     eax, 0C0000004h
0x140050985  jnz     loc_140050BD4
0x14005098b  mov     eax, [rbp+57h+ReturnLength]
0x14005098e  shr     eax, 8
0x140050991  mov     [rbx+58h], eax
0x140050994  jmp     loc_140050BD4
0x140050999  mov     rsi, [rbx+10h]
0x14005099d  lea     rcx, [rbp+57h+HashTable]
0x1400509a1  mov     r12, [rbx+38h]
0x1400509a5  xor     r9d, r9d
0x1400509a8  mov     edx, 400h
0x1400509ad  mov     [rbp+57h+var_98], rsi
0x1400509b1  mov     [rbp+57h+var_90], r12
0x1400509b5  mov     [rbx+58h], edi
0x1400509b8  call    cs:__imp_RtlCreateHashTableEx
0x1400509bf  nop     dword ptr [rax+rax+00h]
0x1400509c4  test    al, al
0x1400509c6  jz      loc_140050BD4
0x1400509cc  lea     rdx, [r15+r15*4]
0x1400509d0  mov     ecx, 40h ; '@'
0x1400509d5  shl     rdx, 3
0x1400509d9  mov     r8d, 64646641h
0x1400509df  call    cs:__imp_ExAllocatePool2
0x1400509e6  nop     dword ptr [rax+rax+00h]
0x1400509eb  mov     rdi, rax
0x1400509ee  test    rax, rax
0x1400509f1  jz      loc_140050BD4
0x1400509f7  xorps   xmm0, xmm0
0x1400509fa  lea     rcx, [rbp+57h+var_70]
0x1400509fe  xor     eax, eax
0x140050a00  movups  [rbp+57h+var_70], xmm0
0x140050a04  mov     [rbp+57h+var_60], rax
0x140050a08  call    cs:__imp_NetioGetThreadCompartmentInfo
0x140050a0f  nop     dword ptr [rax+rax+00h]
0x140050a14  mov     rcx, cs:AfdGlobalData; Resource
0x140050a1b  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x140050a22  nop     dword ptr [rax+rax+00h]
0x140050a27  mov     r14, cs:AfdEndpointListHead
0x140050a2e  lea     rax, AfdEndpointListHead
0x140050a35  cmp     r14, rax
0x140050a38  jz      loc_140050B9B
0x140050a3e  mov     rsi, [r14-0E0h]
0x140050a45  test    rsi, rsi
0x140050a48  jz      short loc_140050A4F
0x140050a4a  mov     esi, [rsi+10h]
0x140050a4d  jmp     short loc_140050A54
0x140050a4f  mov     esi, 1
0x140050a54  xorps   xmm0, xmm0
0x140050a57  lea     r8, [rbp+57h+var_58]
0x140050a5b  movups  [rbp+57h+var_58], xmm0
0x140050a5f  mov     r13d, [r14-130h]
0x140050a66  lea     rdx, [rbp+57h+var_70]
0x140050a6a  mov     ecx, esi
0x140050a6c  call    cs:__imp_NetioGetCompartmentNamespace
0x140050a73  nop     dword ptr [rax+rax+00h]
0x140050a78  test    eax, eax
0x140050a7a  js      loc_140050B7D
0x140050a80  lea     rax, [rbp+57h+var_70]
0x140050a84  xor     r9d, r9d
0x140050a87  mov     r8b, 1
0x140050a8a  mov     [rsp+0E0h+var_C0], rax
0x140050a8f  lea     rdx, [rbp+57h+var_58]
0x140050a93  mov     ecx, esi
0x140050a95  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x140050a9c  nop     dword ptr [rax+rax+00h]
0x140050aa1  test    al, al
0x140050aa3  jz      loc_140050B7D
0x140050aa9  mov     rcx, [r14-108h]; Process
0x140050ab0  call    cs:__imp_PsGetProcessId
0x140050ab7  nop     dword ptr [rax+rax+00h]
0x140050abc  mov     ecx, 80000000h
0x140050ac1  mov     [rbp+57h+Context.Signature], 0
0x140050ac9  mov     r12, rax
0x140050acc  lea     r8, [rbp+57h+Context]; Context
0x140050ad0  mov     rax, [rbp+57h+HashTable]
0x140050ad4  xorps   xmm0, xmm0
0x140050ad7  mov     esi, r12d
0x140050ada  or      rsi, rcx
0x140050add  mov     qword ptr [rbp+57h+ReturnLength], rax
0x140050ae1  mov     rdx, rsi; Signature
0x140050ae4  mov     rcx, rax; HashTable
0x140050ae7  movdqu  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x140050aec  call    cs:__imp_RtlLookupEntryHashTable
0x140050af3  nop     dword ptr [rax+rax+00h]
0x140050af8  test    rax, rax
0x140050afb  jz      short loc_140050B35
0x140050afd  mov     rbx, qword ptr [rbp+57h+ReturnLength]
0x140050b01  lea     rsi, [rax-10h]
0x140050b05  cmp     [rsi], r12d
0x140050b08  jz      short loc_140050B22
0x140050b0a  lea     rdx, [rbp+57h+Context]; Context
0x140050b0e  mov     rcx, rbx; HashTable
0x140050b11  call    cs:__imp_RtlGetNextEntryHashTable
0x140050b18  nop     dword ptr [rax+rax+00h]
0x140050b1d  test    rax, rax
0x140050b20  jnz     short loc_140050B01
0x140050b22  inc     dword ptr [rsi+4]
0x140050b25  mov     rbx, [rbp+57h+var_A0]
0x140050b29  bt      r13d, 0Bh
0x140050b2e  jnb     short loc_140050B7D
0x140050b30  inc     dword ptr [rsi+8]
0x140050b33  jmp     short loc_140050B7D
0x140050b35  mov     edx, [rbx+58h]
0x140050b38  cmp     edx, r15d
0x140050b3b  jnb     short loc_140050B93
0x140050b3d  lea     eax, [rdx+1]
0x140050b40  mov     [rbx+58h], eax
0x140050b43  mov     eax, 1
0x140050b48  lea     rcx, [rdx+rdx*4]
0x140050b4c  mov     [rdi+rcx*8+4], eax
0x140050b50  bt      r13d, 0Bh
0x140050b55  jnb     short loc_140050B5B
0x140050b57  mov     [rdi+rcx*8+8], eax
0x140050b5b  mov     [rdi+rcx*8], r12d
0x140050b5f  xor     r9d, r9d; Context
0x140050b62  add     rcx, 2
0x140050b66  mov     r8, rsi; Signature
0x140050b69  lea     rdx, [rdi+rcx*8]; Entry
0x140050b6d  mov     rcx, [rbp+57h+HashTable]; HashTable
0x140050b71  call    cs:__imp_RtlInsertEntryHashTable
0x140050b78  nop     dword ptr [rax+rax+00h]
0x140050b7d  mov     rax, [r14]
0x140050b80  lea     rcx, AfdEndpointListHead
0x140050b87  mov     r14, rax
0x140050b8a  cmp     rax, rcx
0x140050b8d  jnz     loc_140050A3E
0x140050b93  mov     rsi, [rbp+57h+var_98]
0x140050b97  mov     r12, [rbp+57h+var_90]
0x140050b9b  mov     rcx, cs:AfdGlobalData; Resource
0x140050ba2  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140050ba9  nop     dword ptr [rax+rax+00h]
0x140050bae  xor     r8d, r8d
0x140050bb1  cmp     [rbx+58h], r8d
0x140050bb5  jbe     short loc_140050BD4
0x140050bb7  lea     rcx, [r8+r8*4]
0x140050bbb  mov     eax, [rdi+rcx*8]
0x140050bbe  mov     [rsi+r8*4], eax
0x140050bc2  mov     rax, [rdi+rcx*8+4]
0x140050bc7  mov     [r12+r8*8], rax
0x140050bcb  inc     r8d
0x140050bce  cmp     r8d, [rbx+58h]
0x140050bd2  jb      short loc_140050BB7
0x140050bd4  mov     rcx, [rbp+57h+HashTable]; HashTable
0x140050bd8  test    rcx, rcx
0x140050bdb  jz      short loc_140050BE9
0x140050bdd  call    cs:__imp_RtlDeleteHashTable
0x140050be4  nop     dword ptr [rax+rax+00h]
0x140050be9  test    rdi, rdi
0x140050bec  jz      short loc_140050BFF
0x140050bee  xor     edx, edx; Tag
0x140050bf0  mov     rcx, rdi; P
0x140050bf3  call    cs:__imp_ExFreePoolWithTag
0x140050bfa  nop     dword ptr [rax+rax+00h]
0x140050bff  xor     eax, eax
0x140050c01  mov     rcx, [rbp+57h+var_48]
0x140050c05  xor     rcx, rsp; StackCookie
0x140050c08  call    __security_check_cookie
0x140050c0d  add     rsp, 0A8h
0x140050c14  pop     r15
0x140050c16  pop     r14
0x140050c18  pop     r13
0x140050c1a  pop     r12
0x140050c1c  pop     rdi
0x140050c1d  pop     rsi
0x140050c1e  pop     rbx
0x140050c1f  pop     rbp
0x140050c20  retn
```
