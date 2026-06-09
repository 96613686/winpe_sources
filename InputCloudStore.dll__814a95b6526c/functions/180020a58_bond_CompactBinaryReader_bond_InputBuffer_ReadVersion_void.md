# bond::CompactBinaryReader<bond::InputBuffer>::ReadVersion(void)

- ea: `0x180020a58`
- end: `0x180020aa6`
- name: `?ReadVersion@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAA_NXZ`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800181fc`
- `0x1800184c0`
- `0x180018778`
- `0x180018a50`
- `0x180018d24`
- `0x180018f98`
- `0x180019250`

## callees

- `0x18000ce44`
- `0x180020a58`

## pseudocode

```c
bool __fastcall bond::CompactBinaryReader<bond::InputBuffer>::ReadVersion(__int64 a1)
{
  __int16 v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  bond::InputBuffer::Read<unsigned short>(a1, &v3);
  bond::InputBuffer::Read<unsigned short>(a1, (_WORD *)(a1 + 40));
  return v3 == 16963 && *(_WORD *)(a1 + 40) <= 2u;
}

```

## disassembly

```asm
0x180020a58  mov     [rsp+arg_8], rbx
0x180020a5d  push    rdi
0x180020a5e  sub     rsp, 20h
0x180020a62  xor     eax, eax
0x180020a64  lea     rdx, [rsp+28h+arg_0]
0x180020a69  mov     [rsp+28h+arg_0], ax
0x180020a6e  mov     rbx, rcx
0x180020a71  call    ??$Read@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::Read<ushort>(ushort &)
0x180020a76  lea     rdx, [rbx+28h]
0x180020a7a  mov     rcx, rbx
0x180020a7d  call    ??$Read@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::Read<ushort>(ushort &)
0x180020a82  mov     eax, 4243h
0x180020a87  cmp     [rsp+28h+arg_0], ax
0x180020a8c  jnz     short loc_180020A99
0x180020a8e  cmp     word ptr [rbx+28h], 2
0x180020a93  ja      short loc_180020A99
0x180020a95  mov     al, 1
0x180020a97  jmp     short loc_180020A9B
0x180020a99  xor     al, al
0x180020a9b  mov     rbx, [rsp+28h+arg_8]
0x180020aa0  add     rsp, 20h
0x180020aa4  pop     rdi
0x180020aa5  retn
```
