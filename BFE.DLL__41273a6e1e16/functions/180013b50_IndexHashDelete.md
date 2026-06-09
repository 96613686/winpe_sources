# IndexHashDelete

- ea: `0x180013b50`
- end: `0x180013c58`
- name: `IndexHashDelete`
- size: `264`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800135ac`
- `0x180013b50`
- `0x1800197d0`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180013b77`
- `ntdll!RtlRemoveEntryHashTable` at `0x180013b77`
- `ntdll!RtlExpandHashTable` at `0x180013c23`
- `ntdll!RtlExpandHashTable` at `0x180013c23`
- `ntdll!RtlContractHashTable` at `0x180013c03`
- `ntdll!RtlContractHashTable` at `0x180013c03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013b61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013b61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013bad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013bda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013bad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013bda`

## string_xrefs

- `0x180013bc8`: `RtlRemoveEntryHashTable`
- `0x180013c47`: `IndexHashDelete`

## pseudocode

```c
__int64 __fastcall IndexHashDelete(LPCRITICAL_SECTION lpCriticalSection, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rcx
  _DWORD *OwningThread; // rsi
  unsigned int v6; // ecx
  unsigned int v7; // edi
  __int64 v9; // rdi

  v2 = *(_QWORD *)(a2 + 32);
  EnterCriticalSection(lpCriticalSection);
  if ( (unsigned __int8)RtlRemoveEntryHashTable(lpCriticalSection[1].OwningThread, v2, 0) )
  {
    OwningThread = lpCriticalSection[1].OwningThread;
    v6 = OwningThread[2];
    v7 = OwningThread[5];
    if ( v7 > 3 * v6 )
    {
      while ( (unsigned __int8)RtlExpandHashTable(OwningThread) && v7 > 3 * OwningThread[2] )
        ;
    }
    else if ( v7 < v6 )
    {
      while ( (unsigned __int8)RtlContractHashTable(OwningThread) && v7 < OwningThread[2] )
        ;
    }
    lpCriticalSection[1].LockSemaphore = (char *)lpCriticalSection[1].LockSemaphore - 32;
    LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
  else
  {
    v9 = WfpReportSysErrorAsNtStatus(v4, "RtlRemoveEntryHashTable", 3221225473LL);
    LeaveCriticalSection(lpCriticalSection);
    if ( v9 )
      WfpReportError(v9, "IndexHashDelete");
    return v9;
  }
}

```

## disassembly

```asm
0x180013b50  mov     [rsp+arg_8], rbx
0x180013b55  push    rdi
0x180013b56  sub     rsp, 20h
0x180013b5a  mov     rdi, [rdx+20h]
0x180013b5e  mov     rbx, rcx
0x180013b61  call    cs:__imp_EnterCriticalSection
0x180013b68  nop     dword ptr [rax+rax+00h]
0x180013b6d  mov     rcx, [rbx+38h]
0x180013b71  xor     r8d, r8d
0x180013b74  mov     rdx, rdi
0x180013b77  call    cs:__imp_RtlRemoveEntryHashTable
0x180013b7e  nop     dword ptr [rax+rax+00h]
0x180013b83  test    al, al
0x180013b85  jz      short loc_180013BC2
0x180013b87  mov     [rsp+28h+arg_0], rsi
0x180013b8c  mov     rsi, [rbx+38h]
0x180013b90  mov     ecx, [rsi+8]
0x180013b93  mov     edi, [rsi+14h]
0x180013b96  lea     eax, [rcx+rcx*2]
0x180013b99  cmp     edi, eax
0x180013b9b  ja      loc_180013C20
0x180013ba1  cmp     edi, ecx
0x180013ba3  jb      short loc_180013C00
0x180013ba5  add     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFE0h
0x180013baa  mov     rcx, rbx; lpCriticalSection
0x180013bad  call    cs:__imp_LeaveCriticalSection
0x180013bb4  nop     dword ptr [rax+rax+00h]
0x180013bb9  mov     rsi, [rsp+28h+arg_0]
0x180013bbe  xor     eax, eax
0x180013bc0  jmp     short loc_180013BEE
0x180013bc2  mov     r8d, 0C0000001h
0x180013bc8  lea     rdx, aRtlremoveentry; "RtlRemoveEntryHashTable"
0x180013bcf  call    WfpReportSysErrorAsNtStatus
0x180013bd4  mov     rdi, rax
0x180013bd7  mov     rcx, rbx; lpCriticalSection
0x180013bda  call    cs:__imp_LeaveCriticalSection
0x180013be1  nop     dword ptr [rax+rax+00h]
0x180013be6  test    rdi, rdi
0x180013be9  jnz     short loc_180013C47
0x180013beb  mov     rax, rdi
0x180013bee  mov     rbx, [rsp+28h+arg_8]
0x180013bf3  add     rsp, 20h
0x180013bf7  pop     rdi
0x180013bf8  retn
0x180013c00  mov     rcx, rsi
0x180013c03  call    cs:__imp_RtlContractHashTable
0x180013c0a  nop     dword ptr [rax+rax+00h]
0x180013c0f  test    al, al
0x180013c11  jz      short loc_180013BA5
0x180013c13  cmp     edi, [rsi+8]
0x180013c16  jb      short loc_180013C00
0x180013c18  jmp     short loc_180013BA5
0x180013c20  mov     rcx, rsi
0x180013c23  call    cs:__imp_RtlExpandHashTable
0x180013c2a  nop     dword ptr [rax+rax+00h]
0x180013c2f  test    al, al
0x180013c31  jz      loc_180013BA5
0x180013c37  mov     eax, [rsi+8]
0x180013c3a  lea     ecx, [rax+rax*2]
0x180013c3d  cmp     edi, ecx
0x180013c3f  jbe     loc_180013BA5
0x180013c45  jmp     short loc_180013C20
0x180013c47  lea     rdx, aIndexhashdelet; "IndexHashDelete"
0x180013c4e  mov     rcx, rdi
0x180013c51  call    WfpReportError
0x180013c56  jmp     short loc_180013BEB
```
