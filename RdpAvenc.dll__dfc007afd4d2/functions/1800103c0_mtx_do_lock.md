# mtx_do_lock

- ea: `0x1800103c0`
- end: `0x180010436`
- name: `mtx_do_lock`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `51`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ba24`
- `0x18000f9d0`
- `0x180013b4c`
- `0x1800238a0`
- `0x180023a28`
- `0x180024ee0`
- `0x180025884`
- `0x180026410`
- `0x1800268b0`
- `0x18002bc04`
- `0x18002d1bc`
- `0x18003d4d4`
- `0x1800457c4`
- `0x180046944`
- `0x180048f2c`
- `0x180048fc4`
- `0x180049198`
- `0x1800495c4`
- `0x180049af8`
- `0x18004a030`
- `0x18004a6f0`
- `0x18004c050`
- `0x18004c5f0`
- `0x18004ea70`
- `0x18004edb0`
- `0x18004f404`
- `0x180050518`
- `0x180050758`
- `0x180050c50`
- `0x1800514c0`
- `0x180052284`
- `0x180052d10`
- `0x1800530c0`
- `0x1800532c8`
- `0x1800533d0`
- `0x1800536f0`
- `0x180053890`
- `0x180053a30`
- `0x180053c34`
- `0x180056760`
- `0x18005af04`
- `0x18005b5c4`
- `0x18005b6f4`
- `0x18005b8f4`
- `0x18005bd40`
- `0x1800602ac`
- `0x180060520`
- `0x180063db0`
- `0x180064d90`
- `0x180067508`

## callees

- `0x1800103c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800103e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010400`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800103e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010400`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103cd`

## pseudocode

```c
__int64 __fastcall mtx_do_lock(__int64 a1)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // edi
  int v4; // ecx

  CurrentThreadId = GetCurrentThreadId();
  v3 = CurrentThreadId;
  if ( (*(_DWORD *)a1 & 0xFFFFFEFF) == 1 )
  {
    if ( *(_DWORD *)(a1 + 72) != CurrentThreadId )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
      *(_DWORD *)(a1 + 72) = v3;
    }
    ++*(_DWORD *)(a1 + 76);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 72) != CurrentThreadId )
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
    v4 = *(_DWORD *)(a1 + 76);
    *(_DWORD *)(a1 + 76) = v4 + 1;
    if ( v4 + 1 <= 1 )
    {
      *(_DWORD *)(a1 + 72) = v3;
    }
    else if ( (*(_DWORD *)a1 & 0x100) == 0 )
    {
      *(_DWORD *)(a1 + 76) = v4;
      return 3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800103c0  mov     [rsp+arg_0], rbx
0x1800103c5  push    rdi
0x1800103c6  sub     rsp, 20h
0x1800103ca  mov     rbx, rcx
0x1800103cd  call    cs:__imp_GetCurrentThreadId
0x1800103d3  mov     edx, [rbx]
0x1800103d5  mov     edi, eax
0x1800103d7  btr     edx, 8
0x1800103db  cmp     edx, 1
0x1800103de  jnz     short loc_1800103F7
0x1800103e0  cmp     [rbx+48h], eax
0x1800103e3  jz      short loc_1800103F2
0x1800103e5  lea     rcx, [rbx+10h]; SRWLock
0x1800103e9  call    cs:__imp_AcquireSRWLockExclusive
0x1800103ef  mov     [rbx+48h], edi
0x1800103f2  inc     dword ptr [rbx+4Ch]
0x1800103f5  jmp     short loc_180010429
0x1800103f7  cmp     [rbx+48h], edi
0x1800103fa  jz      short loc_180010406
0x1800103fc  lea     rcx, [rbx+10h]; SRWLock
0x180010400  call    cs:__imp_AcquireSRWLockExclusive
0x180010406  mov     ecx, [rbx+4Ch]
0x180010409  lea     eax, [rcx+1]
0x18001040c  mov     [rbx+4Ch], eax
0x18001040f  cmp     eax, 1
0x180010412  jle     short loc_180010426
0x180010414  test    dword ptr [rbx], 100h
0x18001041a  jnz     short loc_180010429
0x18001041c  mov     [rbx+4Ch], ecx
0x18001041f  mov     eax, 3
0x180010424  jmp     short loc_18001042B
0x180010426  mov     [rbx+48h], edi
0x180010429  xor     eax, eax
0x18001042b  mov     rbx, [rsp+28h+arg_0]
0x180010430  add     rsp, 20h
0x180010434  pop     rdi
0x180010435  retn
```
