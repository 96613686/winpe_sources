# CompareFunction

- ea: `0x180007d90`
- end: `0x180007dd6`
- name: `CompareFunction`
- size: `70`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007d90`
- `0x18001bc72`

## pseudocode

```c
__int64 __fastcall CompareFunction(_QWORD **a1, _QWORD **a2)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rbx
  __int64 result; // rax
  int v5; // edx

  v2 = *a2;
  v3 = *a1;
  result = av_compare_ts();
  v5 = 0;
  if ( !(_DWORD)result )
  {
    LOBYTE(v5) = *v3 < *v2;
    return (unsigned int)(*v3 > *v2) - v5;
  }
  return result;
}

```

## disassembly

```asm
0x180007d90  mov     [rsp+arg_0], rbx
0x180007d95  push    rdi
0x180007d96  sub     rsp, 20h
0x180007d9a  mov     rdi, [rdx]
0x180007d9d  mov     rbx, [rcx]
0x180007da0  mov     r9, [rdi+8]
0x180007da4  mov     r8, [rdi+10h]
0x180007da8  mov     rdx, [rbx+8]
0x180007dac  mov     rcx, [rbx+10h]
0x180007db0  call    av_compare_ts
0x180007db5  xor     edx, edx
0x180007db7  test    eax, eax
0x180007db9  jnz     short loc_180007DCB
0x180007dbb  mov     rcx, [rdi]
0x180007dbe  mov     eax, edx
0x180007dc0  cmp     [rbx], rcx
0x180007dc3  setnle  al
0x180007dc6  setl    dl
0x180007dc9  sub     eax, edx
0x180007dcb  mov     rbx, [rsp+28h+arg_0]
0x180007dd0  add     rsp, 20h
0x180007dd4  pop     rdi
0x180007dd5  retn
```
