# BaseSrvUpdateVDMEntry

- ea: `0x18000c620`
- end: `0x18000c671`
- name: `BaseSrvUpdateVDMEntry`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000b704`
- `0x18000c434`
- `0x18000c620`
- `0x18000c820`

## pseudocode

```c
__int64 __fastcall BaseSrvUpdateVDMEntry(__int64 a1)
{
  __int64 v3; // rcx
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( (int)BaseSrvGetVdmSequence(*(_QWORD *)(a1 + 8), &v4) < 0 )
    return 3221225485LL;
  v3 = a1 + 64;
  if ( *(_DWORD *)(a1 + 68) == 32 )
    return BaseSrvUpdateWOWEntry(v3, v4);
  else
    return BaseSrvUpdateDOSEntry(v3, v4);
}

```

## disassembly

```asm
0x18000c620  push    rbx
0x18000c622  sub     rsp, 20h
0x18000c626  mov     rbx, rcx
0x18000c629  mov     [rsp+28h+arg_0], 0
0x18000c631  mov     rcx, [rcx+8]
0x18000c635  lea     rdx, [rsp+28h+arg_0]
0x18000c63a  call    BaseSrvGetVdmSequence
0x18000c63f  test    eax, eax
0x18000c641  jns     short loc_18000C64F
0x18000c643  mov     eax, 0C000000Dh
0x18000c648  add     rsp, 20h
0x18000c64c  pop     rbx
0x18000c64d  retn
0x18000c64f  mov     edx, [rsp+28h+arg_0]
0x18000c653  lea     rcx, [rbx+40h]
0x18000c657  cmp     dword ptr [rcx+4], 20h ; ' '
0x18000c65b  jnz     short loc_18000C667
0x18000c65d  add     rsp, 20h
0x18000c661  pop     rbx
0x18000c662  jmp     BaseSrvUpdateWOWEntry
0x18000c667  add     rsp, 20h
0x18000c66b  pop     rbx
0x18000c66c  jmp     BaseSrvUpdateDOSEntry
```
