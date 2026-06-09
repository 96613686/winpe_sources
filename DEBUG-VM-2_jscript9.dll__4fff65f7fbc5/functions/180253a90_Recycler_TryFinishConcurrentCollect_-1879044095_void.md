# Recycler::TryFinishConcurrentCollect<-1879044095>(void)

- ea: `0x180253a90`
- end: `0x180253b14`
- name: `??$TryFinishConcurrentCollect@$0?GPPPOPPP@@Recycler@@AEAAHXZ`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1801a80e0`
- `0x1802537a8`

## callees

- `0x1801892d8`
- `0x180253a90`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180253af4`
- `KERNEL32!SetThreadPriority` at `0x180253af4`
- `KERNEL32!GetTickCount` at `0x180253ac1`
- `KERNEL32!GetTickCount` at `0x180253ac1`

## pseudocode

```c
__int64 __fastcall Recycler::TryFinishConcurrentCollect<-1879044095>(__int64 a1)
{
  bool v2; // zf
  DWORD TickCount; // eax
  void *v4; // rcx

  v2 = *(_QWORD *)(a1 + 12952) == 0;
  *(_BYTE *)(a1 + 12893) = 1;
  if ( v2 || (*(_DWORD *)a1 & 0x4000) == 0 )
    return Recycler::FinishConcurrentCollectWrapped(a1, 2415923201LL);
  if ( !*(_BYTE *)(a1 + 12910) )
  {
    TickCount = GetTickCount();
    if ( *(_QWORD *)(a1 + 488) > (unsigned __int64)qword_18043CF78 || TickCount - *(_DWORD *)(a1 + 12960) > 0x1388 )
    {
      v4 = *(void **)(a1 + 12952);
      *(_BYTE *)(a1 + 12910) = 1;
      SetThreadPriority(v4, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180253a90  mov     [rsp+arg_0], rcx
0x180253a95  push    rbx
0x180253a96  sub     rsp, 20h
0x180253a9a  mov     rbx, [rsp+28h+arg_0]
0x180253a9f  cmp     qword ptr [rbx+3298h], 0
0x180253aa7  mov     byte ptr [rbx+325Dh], 1
0x180253aae  jz      short loc_180253B02
0x180253ab0  test    dword ptr [rbx], 4000h
0x180253ab6  jz      short loc_180253B02
0x180253ab8  cmp     byte ptr [rbx+326Eh], 0
0x180253abf  jnz     short loc_180253AFA
0x180253ac1  call    cs:__imp_GetTickCount
0x180253ac7  mov     rcx, cs:qword_18043CF78
0x180253ace  cmp     [rbx+1E8h], rcx
0x180253ad5  ja      short loc_180253AE4
0x180253ad7  sub     eax, [rbx+32A0h]
0x180253add  cmp     eax, 1388h
0x180253ae2  jbe     short loc_180253AFA
0x180253ae4  mov     rcx, [rbx+3298h]; hThread
0x180253aeb  xor     edx, edx; nPriority
0x180253aed  mov     byte ptr [rbx+326Eh], 1
0x180253af4  call    cs:__imp_SetThreadPriority
0x180253afa  xor     eax, eax
0x180253afc  add     rsp, 20h
0x180253b00  pop     rbx
0x180253b01  retn
0x180253b02  mov     edx, 90001001h
0x180253b07  mov     rcx, rbx
0x180253b0a  add     rsp, 20h
0x180253b0e  pop     rbx
0x180253b0f  jmp     ?FinishConcurrentCollectWrapped@Recycler@@AEAAHW4CollectionFlags@@@Z; Recycler::FinishConcurrentCollectWrapped(CollectionFlags)
```
