# LZX_DecodeNewGroup

- ea: `0x180007bfc`
- end: `0x180007c8b`
- name: `LZX_DecodeNewGroup`
- size: `143`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a9c`
- `0x180007b4c`

## callees

- `0x180001cae`

## pseudocode

```c
__int64 __fastcall LZX_DecodeNewGroup(__int64 a1)
{
  __int64 result; // rax

  memset_0((void *)(a1 + 2684), 0, (unsigned int)(8 * *(_DWORD *)(a1 + 52) + 256));
  memset_0((void *)(a1 + 28320), 0, (unsigned int)(8 * *(_DWORD *)(a1 + 52) + 256));
  memset_0((void *)(a1 + 5268), 0, 0xF9u);
  memset_0((void *)(a1 + 30904), 0, 0xF9u);
  result = 1;
  *(_DWORD *)(a1 + 112) = 1;
  *(_DWORD *)(a1 + 116) = 1;
  *(_DWORD *)(a1 + 120) = 1;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 92) = 1;
  *(_QWORD *)(a1 + 84) = 0;
  *(_QWORD *)(a1 + 56) = 1;
  *(_QWORD *)(a1 + 72) = 0;
  return result;
}

```

## disassembly

```asm
0x180007bfc  push    rbx
0x180007bfe  sub     rsp, 20h
0x180007c02  mov     eax, [rcx+34h]
0x180007c05  mov     rbx, rcx
0x180007c08  add     rcx, 0A7Ch; void *
0x180007c0f  xor     edx, edx; Val
0x180007c11  lea     r8d, ds:100h[rax*8]; Size
0x180007c19  call    memset_0
0x180007c1e  mov     eax, [rbx+34h]
0x180007c21  lea     rcx, [rbx+6EA0h]; void *
0x180007c28  xor     edx, edx; Val
0x180007c2a  lea     r8d, ds:100h[rax*8]; Size
0x180007c32  call    memset_0
0x180007c37  lea     rcx, [rbx+1494h]; void *
0x180007c3e  xor     edx, edx; Val
0x180007c40  mov     r8d, 0F9h; Size
0x180007c46  call    memset_0
0x180007c4b  lea     rcx, [rbx+78B8h]; void *
0x180007c52  xor     edx, edx; Val
0x180007c54  mov     r8d, 0F9h; Size
0x180007c5a  call    memset_0
0x180007c5f  mov     eax, 1
0x180007c64  xor     ecx, ecx
0x180007c66  mov     [rbx+70h], eax
0x180007c69  mov     [rbx+74h], eax
0x180007c6c  mov     [rbx+78h], eax
0x180007c6f  mov     [rbx+40h], rcx
0x180007c73  mov     [rbx+30h], ecx
0x180007c76  mov     [rbx+5Ch], eax
0x180007c79  mov     [rbx+54h], rcx
0x180007c7d  mov     [rbx+38h], rax
0x180007c81  mov     [rbx+48h], rcx
0x180007c85  add     rsp, 20h
0x180007c89  pop     rbx
0x180007c8a  retn
```
