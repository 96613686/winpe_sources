# WmiThread<ulong>::GetThread(void)

- ea: `0x1400263c0`
- end: `0x140026454`
- name: `?GetThread@?$WmiThread@K@@CAPEAV1@XZ`
- size: `148`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140026368`
- `0x14002d860`
- `0x14002d9d0`

## callees

- `0x140009c70`
- `0x1400263c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002641e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002641e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400263cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400263cc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140026447`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140026447`

## pseudocode

```c
__int64 WmiThread<unsigned long>::GetThread()
{
  __int64 v0; // rbx
  DWORD CurrentThreadId; // edi
  __int64 *i; // rcx

  v0 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( byte_1400616F0
    && !CriticalSection::acquire_write((CriticalSection *)&WmiThread<unsigned long>::s_CriticalSection) )
  {
    while ( !CriticalSection::acquire_write((CriticalSection *)&WmiThread<unsigned long>::s_CriticalSection) )
      Sleep(0x3E8u);
  }
  for ( i = *(__int64 **)WmiThread<unsigned long>::s_ThreadContainer;
        i;
        i = *(__int64 **)((char *)i + (-(__int64)(CurrentThreadId < *((_DWORD *)i + 2)) & 0xFFFFFFFFFFFFFFF8uLL) + 24) )
  {
    if ( CurrentThreadId == *((_DWORD *)i + 2) )
    {
      v0 = *i;
      break;
    }
  }
  if ( byte_1400616F0 )
    LeaveCriticalSection(&WmiThread<unsigned long>::s_CriticalSection);
  return v0;
}

```

## disassembly

```asm
0x1400263c0  mov     [rsp+arg_0], rbx
0x1400263c5  push    rdi
0x1400263c6  sub     rsp, 20h
0x1400263ca  xor     ebx, ebx
0x1400263cc  call    cs:__imp_GetCurrentThreadId
0x1400263d2  cmp     cs:byte_1400616F0, bl
0x1400263d8  mov     edi, eax
0x1400263da  jz      short loc_1400263EC
0x1400263dc  lea     rcx, ?s_CriticalSection@?$WmiThread@K@@0VCriticalSection@@A; this
0x1400263e3  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x1400263e8  test    al, al
0x1400263ea  jz      short loc_140026432
0x1400263ec  mov     rax, cs:?s_ThreadContainer@?$WmiThread@K@@0PEAV?$WmiBasicTree@KPEAV?$WmiThread@K@@@@EA; WmiBasicTree<ulong,WmiThread<ulong> *> * WmiThread<ulong>::s_ThreadContainer
0x1400263f3  mov     rcx, [rax]
0x1400263f6  test    rcx, rcx
0x1400263f9  jz      short loc_14002640E
0x1400263fb  cmp     edi, [rcx+8]
0x1400263fe  jz      short loc_14002644F
0x140026400  sbb     rax, rax
0x140026403  and     rax, 0FFFFFFFFFFFFFFF8h
0x140026407  mov     rcx, [rax+rcx+18h]
0x14002640c  jmp     short loc_1400263F6
0x14002640e  cmp     cs:byte_1400616F0, 0
0x140026415  jz      short loc_140026424
0x140026417  lea     rcx, ?s_CriticalSection@?$WmiThread@K@@0VCriticalSection@@A; lpCriticalSection
0x14002641e  call    cs:__imp_LeaveCriticalSection
0x140026424  mov     rax, rbx
0x140026427  mov     rbx, [rsp+28h+arg_0]
0x14002642c  add     rsp, 20h
0x140026430  pop     rdi
0x140026431  retn
0x140026432  lea     rcx, ?s_CriticalSection@?$WmiThread@K@@0VCriticalSection@@A; this
0x140026439  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x14002643e  test    al, al
0x140026440  jnz     short loc_1400263EC
0x140026442  mov     ecx, 3E8h; dwMilliseconds
0x140026447  call    cs:__imp_Sleep
0x14002644d  jmp     short loc_140026432
0x14002644f  mov     rbx, [rcx]
0x140026452  jmp     short loc_14002640E
```
