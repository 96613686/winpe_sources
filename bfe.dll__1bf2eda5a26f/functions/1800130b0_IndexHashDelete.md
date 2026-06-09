# IndexHashDelete

- ea: `0x1800130b0`
- end: `0x18001317e`
- name: `IndexHashDelete`
- size: `206`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180012b54`
- `0x1800130b0`
- `0x180018b74`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1800130d1`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800130d1`
- `ntdll!RtlExpandHashTable` at `0x180013157`
- `ntdll!RtlExpandHashTable` at `0x180013157`
- `ntdll!RtlContractHashTable` at `0x180013143`
- `ntdll!RtlContractHashTable` at `0x180013143`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800130fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013124`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800130fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013124`

## string_xrefs

- `0x180013112`: `RtlRemoveEntryHashTable`
- `0x18001316d`: `IndexHashDelete`

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
0x1800130b0  mov     [rsp+arg_8], rbx
0x1800130b5  push    rdi
0x1800130b6  sub     rsp, 20h
0x1800130ba  mov     rdi, [rdx+20h]
0x1800130be  mov     rbx, rcx
0x1800130c1  call    cs:__imp_EnterCriticalSection
0x1800130c7  mov     rcx, [rbx+38h]
0x1800130cb  xor     r8d, r8d
0x1800130ce  mov     rdx, rdi
0x1800130d1  call    cs:__imp_RtlRemoveEntryHashTable
0x1800130d7  test    al, al
0x1800130d9  jz      short loc_18001310C
0x1800130db  mov     [rsp+28h+arg_0], rsi
0x1800130e0  mov     rsi, [rbx+38h]
0x1800130e4  mov     ecx, [rsi+8]
0x1800130e7  mov     edi, [rsi+14h]
0x1800130ea  lea     eax, [rcx+rcx*2]
0x1800130ed  cmp     edi, eax
0x1800130ef  ja      short loc_180013154
0x1800130f1  cmp     edi, ecx
0x1800130f3  jb      short loc_180013140
0x1800130f5  add     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFE0h
0x1800130fa  mov     rcx, rbx; lpCriticalSection
0x1800130fd  call    cs:__imp_LeaveCriticalSection
0x180013103  mov     rsi, [rsp+28h+arg_0]
0x180013108  xor     eax, eax
0x18001310a  jmp     short loc_180013132
0x18001310c  mov     r8d, 0C0000001h
0x180013112  lea     rdx, aRtlremoveentry; "RtlRemoveEntryHashTable"
0x180013119  call    WfpReportSysErrorAsNtStatus
0x18001311e  mov     rdi, rax
0x180013121  mov     rcx, rbx; lpCriticalSection
0x180013124  call    cs:__imp_LeaveCriticalSection
0x18001312a  test    rdi, rdi
0x18001312d  jnz     short loc_18001316D
0x18001312f  mov     rax, rdi
0x180013132  mov     rbx, [rsp+28h+arg_8]
0x180013137  add     rsp, 20h
0x18001313b  pop     rdi
0x18001313c  retn
0x180013140  mov     rcx, rsi
0x180013143  call    cs:__imp_RtlContractHashTable
0x180013149  test    al, al
0x18001314b  jz      short loc_1800130F5
0x18001314d  cmp     edi, [rsi+8]
0x180013150  jb      short loc_180013140
0x180013152  jmp     short loc_1800130F5
0x180013154  mov     rcx, rsi
0x180013157  call    cs:__imp_RtlExpandHashTable
0x18001315d  test    al, al
0x18001315f  jz      short loc_1800130F5
0x180013161  mov     eax, [rsi+8]
0x180013164  lea     ecx, [rax+rax*2]
0x180013167  cmp     edi, ecx
0x180013169  jbe     short loc_1800130F5
0x18001316b  jmp     short loc_180013154
0x18001316d  lea     rdx, aIndexhashdelet; "IndexHashDelete"
0x180013174  mov     rcx, rdi
0x180013177  call    WfpReportError
0x18001317c  jmp     short loc_18001312F
```
