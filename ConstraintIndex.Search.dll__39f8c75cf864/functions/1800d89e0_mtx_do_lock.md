# mtx_do_lock

- ea: `0x1800d89e0`
- end: `0x1800d8a56`
- name: `mtx_do_lock`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014a00`

## callees

- `0x1800d89e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d89ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d89ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d8a09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d8a20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d8a09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d8a20`

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
0x1800d89e0  mov     [rsp+arg_0], rbx
0x1800d89e5  push    rdi
0x1800d89e6  sub     rsp, 20h
0x1800d89ea  mov     rbx, rcx
0x1800d89ed  call    cs:__imp_GetCurrentThreadId
0x1800d89f3  mov     edx, [rbx]
0x1800d89f5  mov     edi, eax
0x1800d89f7  btr     edx, 8
0x1800d89fb  cmp     edx, 1
0x1800d89fe  jnz     short loc_1800D8A17
0x1800d8a00  cmp     [rbx+48h], eax
0x1800d8a03  jz      short loc_1800D8A12
0x1800d8a05  lea     rcx, [rbx+10h]; SRWLock
0x1800d8a09  call    cs:__imp_AcquireSRWLockExclusive
0x1800d8a0f  mov     [rbx+48h], edi
0x1800d8a12  inc     dword ptr [rbx+4Ch]
0x1800d8a15  jmp     short loc_1800D8A49
0x1800d8a17  cmp     [rbx+48h], edi
0x1800d8a1a  jz      short loc_1800D8A26
0x1800d8a1c  lea     rcx, [rbx+10h]; SRWLock
0x1800d8a20  call    cs:__imp_AcquireSRWLockExclusive
0x1800d8a26  mov     ecx, [rbx+4Ch]
0x1800d8a29  lea     eax, [rcx+1]
0x1800d8a2c  mov     [rbx+4Ch], eax
0x1800d8a2f  cmp     eax, 1
0x1800d8a32  jle     short loc_1800D8A46
0x1800d8a34  test    dword ptr [rbx], 100h
0x1800d8a3a  jnz     short loc_1800D8A49
0x1800d8a3c  mov     [rbx+4Ch], ecx
0x1800d8a3f  mov     eax, 3
0x1800d8a44  jmp     short loc_1800D8A4B
0x1800d8a46  mov     [rbx+48h], edi
0x1800d8a49  xor     eax, eax
0x1800d8a4b  mov     rbx, [rsp+28h+arg_0]
0x1800d8a50  add     rsp, 20h
0x1800d8a54  pop     rdi
0x1800d8a55  retn
```
