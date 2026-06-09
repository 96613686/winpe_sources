# PortListSearchAndRemoveRequest

- ea: `0x14000facc`
- end: `0x14000faf6`
- name: `PortListSearchAndRemoveRequest`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f9f0`

## callees

- `0x14000b060`
- `0x14000facc`

## pseudocode

```c
char __fastcall PortListSearchAndRemoveRequest(_QWORD **a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // rax
  char v5; // r9

  v4 = *a1;
  v5 = 0;
  while ( v4 != a1 )
  {
    if ( v4 == a2 )
    {
      LOBYTE(a4) = 1;
      PortListRemoveRequest(a1, a2, a3, a4);
      return v5;
    }
    v4 = (_QWORD *)*v4;
  }
  return v5;
}

```

## disassembly

```asm
0x14000facc  sub     rsp, 28h
0x14000fad0  mov     rax, [rcx]
0x14000fad3  xor     r9b, r9b
0x14000fad6  cmp     rax, rcx
0x14000fad9  jz      short loc_14000FAED
0x14000fadb  cmp     rax, rdx
0x14000fade  jz      short loc_14000FAE5
0x14000fae0  mov     rax, [rax]
0x14000fae3  jmp     short loc_14000FAD6
0x14000fae5  mov     r9b, 1
0x14000fae8  call    PortListRemoveRequest
0x14000faed  mov     al, r9b
0x14000faf0  add     rsp, 28h
0x14000faf4  retn
```
