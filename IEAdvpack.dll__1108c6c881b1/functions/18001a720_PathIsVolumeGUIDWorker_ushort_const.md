# PathIsVolumeGUIDWorker(ushort const *)

- ea: `0x18001a720`
- end: `0x18001a758`
- name: `?PathIsVolumeGUIDWorker@@YA_NPEBG@Z`
- size: `56`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a688`
- `0x18001b524`
- `0x18001b634`

## callees

- `0x18001a720`
- `0x18001ac8c`
- `0x18001ace4`

## pseudocode

```c
bool __fastcall PathIsVolumeGUIDWorker(const unsigned __int16 *a1)
{
  return StrIsEqualCaseInsensitive(a1, L"\\\\?\\Volume", 10) && StringIsGUIDWorker(a1 + 10);
}

```

## disassembly

```asm
0x18001a720  push    rbx
0x18001a722  sub     rsp, 20h
0x18001a726  mov     r8d, 0Ah; int
0x18001a72c  lea     rdx, aVolume; "\\\\?\\Volume"
0x18001a733  mov     rbx, rcx
0x18001a736  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x18001a73b  test    al, al
0x18001a73d  jz      short loc_18001A750
0x18001a73f  lea     rcx, [rbx+14h]; unsigned __int16 *
0x18001a743  call    ?StringIsGUIDWorker@@YA_NPEBG@Z; StringIsGUIDWorker(ushort const *)
0x18001a748  test    al, al
0x18001a74a  jz      short loc_18001A750
0x18001a74c  mov     al, 1
0x18001a74e  jmp     short loc_18001A752
0x18001a750  xor     al, al
0x18001a752  add     rsp, 20h
0x18001a756  pop     rbx
0x18001a757  retn
```
