# FileProvCbQueryStreamSize

- ea: `0x14003ba20`
- end: `0x14003ba45`
- name: `FileProvCbQueryStreamSize`
- size: `37`
- prototype: `__int64 __fastcall(__int64, _QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140023150`
- `0x14003ba20`

## pseudocode

```c
__int64 __fastcall FileProvCbQueryStreamSize(__int64 a1, _QWORD *a2, char a3)
{
  __int64 v4; // rdx

  v4 = *(_QWORD *)(a1 + 8);
  if ( a3 )
    RtlWriteULong64ToUser(a2, v4);
  else
    *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x14003ba20  sub     rsp, 28h
0x14003ba24  mov     rax, rdx
0x14003ba27  mov     rdx, [rcx+8]
0x14003ba2b  test    r8b, r8b
0x14003ba2e  jz      short loc_14003BA40
0x14003ba30  mov     rcx, rax
0x14003ba33  call    RtlWriteULong64ToUser
0x14003ba38  xor     eax, eax
0x14003ba3a  add     rsp, 28h
0x14003ba3e  retn
0x14003ba40  mov     [rax], rdx
0x14003ba43  jmp     short loc_14003BA38
```
