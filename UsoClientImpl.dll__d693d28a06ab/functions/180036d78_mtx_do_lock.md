# mtx_do_lock

- ea: `0x180036d78`
- end: `0x180036dee`
- name: `mtx_do_lock`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x1800105d8`
- `0x18001174c`
- `0x1800120a0`
- `0x180019598`
- `0x180019ae0`
- `0x180019c80`
- `0x180019e60`
- `0x18001a000`
- `0x18001b644`
- `0x18001b78c`
- `0x18001c634`
- `0x18001c834`
- `0x18001df80`
- `0x18001e160`
- `0x180023ad0`
- `0x1800297c8`
- `0x18002a780`
- `0x18002ad50`
- `0x18002c6a4`
- `0x18002cbb4`
- `0x18002cccc`
- `0x180033020`
- `0x180033150`
- `0x1800332c0`
- `0x180037ffc`
- `0x1800380d0`
- `0x18003a47c`
- `0x18003ef00`
- `0x180040210`
- `0x180040bd0`
- `0x180040cd0`

## callees

- `0x180036d78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036da1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036db8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036da1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036db8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036d85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036d85`

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
0x180036d78  mov     [rsp+arg_0], rbx
0x180036d7d  push    rdi
0x180036d7e  sub     rsp, 20h
0x180036d82  mov     rbx, rcx
0x180036d85  call    cs:__imp_GetCurrentThreadId
0x180036d8b  mov     edx, [rbx]
0x180036d8d  mov     edi, eax
0x180036d8f  btr     edx, 8
0x180036d93  cmp     edx, 1
0x180036d96  jnz     short loc_180036DAF
0x180036d98  cmp     [rbx+48h], eax
0x180036d9b  jz      short loc_180036DAA
0x180036d9d  lea     rcx, [rbx+10h]; SRWLock
0x180036da1  call    cs:__imp_AcquireSRWLockExclusive
0x180036da7  mov     [rbx+48h], edi
0x180036daa  inc     dword ptr [rbx+4Ch]
0x180036dad  jmp     short loc_180036DE1
0x180036daf  cmp     [rbx+48h], edi
0x180036db2  jz      short loc_180036DBE
0x180036db4  lea     rcx, [rbx+10h]; SRWLock
0x180036db8  call    cs:__imp_AcquireSRWLockExclusive
0x180036dbe  mov     ecx, [rbx+4Ch]
0x180036dc1  lea     eax, [rcx+1]
0x180036dc4  mov     [rbx+4Ch], eax
0x180036dc7  cmp     eax, 1
0x180036dca  jle     short loc_180036DDE
0x180036dcc  test    dword ptr [rbx], 100h
0x180036dd2  jnz     short loc_180036DE1
0x180036dd4  mov     [rbx+4Ch], ecx
0x180036dd7  mov     eax, 3
0x180036ddc  jmp     short loc_180036DE3
0x180036dde  mov     [rbx+48h], edi
0x180036de1  xor     eax, eax
0x180036de3  mov     rbx, [rsp+28h+arg_0]
0x180036de8  add     rsp, 20h
0x180036dec  pop     rdi
0x180036ded  retn
```
