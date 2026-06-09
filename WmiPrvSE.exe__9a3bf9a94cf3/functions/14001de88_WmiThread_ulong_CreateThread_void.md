# WmiThread<ulong>::CreateThread(void)

- ea: `0x14001de88`
- end: `0x14001df5e`
- name: `?CreateThread@?$WmiThread@K@@AEAA?AW4WmiStatusCode@@XZ`
- size: `214`
- prototype: `__int64 __fastcall(DWORD *lpParameter)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001de20`

## callees

- `0x140009c70`
- `0x14001de88`
- `0x14001e03c`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001df18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001df18`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001dec7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001dec7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001df56`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001df56`

## pseudocode

```c
__int64 __fastcall WmiThread<unsigned long>::CreateThread(DWORD *lpParameter)
{
  HANDLE Thread; // rax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  DWORD *v6; // [rsp+40h] [rbp+8h] BYREF
  char v7; // [rsp+48h] [rbp+10h] BYREF

  (*(void (__fastcall **)(DWORD *))(*(_QWORD *)lpParameter + 24LL))(lpParameter);
  Thread = CreateThread(0, lpParameter[34], WmiThread<unsigned long>::ThreadProc, lpParameter, 0, lpParameter + 32);
  *((_QWORD *)lpParameter + 15) = Thread;
  if ( Thread )
  {
    if ( byte_1400616F0
      && !CriticalSection::acquire_write((CriticalSection *)&WmiThread<unsigned long>::s_CriticalSection) )
    {
      while ( !CriticalSection::acquire_write((CriticalSection *)&WmiThread<unsigned long>::s_CriticalSection) )
        Sleep(0x3E8u);
    }
    v6 = lpParameter;
    v4 = WmiBasicTree<unsigned long,WmiThread<unsigned long> *>::Insert(v3, lpParameter + 32, &v6, &v7);
    if ( byte_1400616F0 )
      LeaveCriticalSection(&WmiThread<unsigned long>::s_CriticalSection);
  }
  else
  {
    (*(void (__fastcall **)(DWORD *))(*(_QWORD *)lpParameter + 32LL))(lpParameter);
    return (unsigned int)-2147483647;
  }
  return v4;
}

```

## disassembly

```asm
0x14001de88  mov     [rsp+arg_10], rbx
0x14001de8d  push    rdi
0x14001de8e  sub     rsp, 30h
0x14001de92  mov     rax, [rcx]
0x14001de95  mov     rbx, rcx
0x14001de98  mov     rax, [rax+18h]
0x14001de9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dea1  mov     edx, [rbx+88h]; dwStackSize
0x14001dea7  lea     rdi, [rbx+80h]
0x14001deae  mov     [rsp+38h+lpThreadId], rdi; lpThreadId
0x14001deb3  lea     r8, ?ThreadProc@?$WmiThread@K@@CAKPEAX@Z; lpStartAddress
0x14001deba  mov     r9, rbx; lpParameter
0x14001debd  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14001dec5  xor     ecx, ecx; lpThreadAttributes
0x14001dec7  call    cs:__imp_CreateThread
0x14001decd  mov     [rbx+78h], rax
0x14001ded1  test    rax, rax
0x14001ded4  jz      short loc_14001DF2B
0x14001ded6  cmp     cs:byte_1400616F0, 0
0x14001dedd  jz      short loc_14001DEEF
0x14001dedf  lea     rcx, ?s_CriticalSection@?$WmiThread@K@@0VCriticalSection@@A; this
0x14001dee6  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x14001deeb  test    al, al
0x14001deed  jz      short loc_14001DF41
0x14001deef  lea     r9, [rsp+38h+arg_8]
0x14001def4  mov     [rsp+38h+arg_0], rbx
0x14001def9  lea     r8, [rsp+38h+arg_0]
0x14001defe  mov     rdx, rdi
0x14001df01  call    ?Insert@?$WmiBasicTree@KPEAV?$WmiThread@K@@@@QEAA?AW4WmiStatusCode@@AEBKAEBQEAV?$WmiThread@K@@AEAVIterator@1@@Z; WmiBasicTree<ulong,WmiThread<ulong> *>::Insert(ulong const &,WmiThread<ulong> * const &,WmiBasicTree<ulong,WmiThread<ulong> *>::Iterator &)
0x14001df06  cmp     cs:byte_1400616F0, 0
0x14001df0d  mov     ebx, eax
0x14001df0f  jz      short loc_14001DF1E
0x14001df11  lea     rcx, ?s_CriticalSection@?$WmiThread@K@@0VCriticalSection@@A; lpCriticalSection
0x14001df18  call    cs:__imp_LeaveCriticalSection
0x14001df1e  mov     eax, ebx
0x14001df20  mov     rbx, [rsp+38h+arg_10]
0x14001df25  add     rsp, 30h
0x14001df29  pop     rdi
0x14001df2a  retn
0x14001df2b  mov     rax, [rbx]
0x14001df2e  mov     rcx, rbx
0x14001df31  mov     rax, [rax+20h]
0x14001df35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001df3a  mov     ebx, 80000001h
0x14001df3f  jmp     short loc_14001DF1E
0x14001df41  lea     rcx, ?s_CriticalSection@?$WmiThread@K@@0VCriticalSection@@A; this
0x14001df48  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x14001df4d  test    al, al
0x14001df4f  jnz     short loc_14001DEEF
0x14001df51  mov     ecx, 3E8h; dwMilliseconds
0x14001df56  call    cs:__imp_Sleep
0x14001df5c  jmp     short loc_14001DF41
```
