# BaseSrvUpdateVDMEntry

- ea: `0x18000c250`
- end: `0x18000c29e`
- name: `BaseSrvUpdateVDMEntry`
- size: `78`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000b458`
- `0x18000c088`
- `0x18000c250`
- `0x18000c454`

## pseudocode

```c
__int64 __fastcall BaseSrvUpdateVDMEntry(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  v1 = a1 + 64;
  if ( (int)BaseSrvGetVdmSequence(*(_QWORD *)(a1 + 8), &v3) < 0 )
    return 3221225485LL;
  if ( *(_DWORD *)(v1 + 4) == 32 )
    return BaseSrvUpdateWOWEntry(v1, v3);
  return BaseSrvUpdateDOSEntry(v1, v3);
}

```

## disassembly

```asm
0x18000c250  push    rbx
0x18000c252  sub     rsp, 20h
0x18000c256  and     [rsp+28h+arg_0], 0
0x18000c25b  lea     rbx, [rcx+40h]
0x18000c25f  mov     rcx, [rcx+8]
0x18000c263  lea     rdx, [rsp+28h+arg_0]
0x18000c268  call    BaseSrvGetVdmSequence
0x18000c26d  test    eax, eax
0x18000c26f  jns     short loc_18000C27D
0x18000c271  mov     eax, 0C000000Dh
0x18000c276  add     rsp, 20h
0x18000c27a  pop     rbx
0x18000c27b  retn
0x18000c27d  cmp     dword ptr [rbx+4], 20h ; ' '
0x18000c281  mov     rcx, rbx
0x18000c284  mov     edx, [rsp+28h+arg_0]
0x18000c288  jnz     short loc_18000C294
0x18000c28a  add     rsp, 20h
0x18000c28e  pop     rbx
0x18000c28f  jmp     BaseSrvUpdateWOWEntry
0x18000c294  add     rsp, 20h
0x18000c298  pop     rbx
0x18000c299  jmp     BaseSrvUpdateDOSEntry
```
