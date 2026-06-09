# read_buf

- ea: `0x180004dd0`
- end: `0x180004e70`
- name: `read_buf`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800021f0`
- `0x180004920`

## callees

- `0x180004dd0`
- `0x180004e80`
- `0x180005230`
- `0x180007739`

## pseudocode

```c
__int64 __fastcall read_buf(__int64 a1, void *a2, unsigned int a3)
{
  unsigned int v3; // eax
  unsigned int v5; // edi
  __int64 result; // rax
  const void *v8; // rdx
  int v9; // ecx
  int v10; // eax

  v3 = *(_DWORD *)(a1 + 8);
  v5 = v3;
  if ( v3 > a3 )
    v5 = a3;
  if ( !v5 )
    return 0;
  v8 = *(const void **)a1;
  *(_DWORD *)(a1 + 8) = v3 - v5;
  memcpy_0(a2, v8, v5);
  v9 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 44LL);
  if ( v9 == 1 )
  {
    v10 = adler32(*(unsigned int *)(a1 + 76), a2, v5);
LABEL_9:
    *(_DWORD *)(a1 + 76) = v10;
    goto LABEL_10;
  }
  if ( v9 == 2 )
  {
    v10 = crc32(*(unsigned int *)(a1 + 76), a2, v5);
    goto LABEL_9;
  }
LABEL_10:
  *(_QWORD *)a1 += v5;
  result = v5;
  *(_DWORD *)(a1 + 12) += v5;
  return result;
}

```

## disassembly

```asm
0x180004dd0  mov     [rsp+arg_8], rbx
0x180004dd5  mov     [rsp+arg_10], rsi
0x180004dda  push    rdi
0x180004ddb  sub     rsp, 20h
0x180004ddf  mov     eax, [rcx+8]
0x180004de2  mov     rsi, rdx
0x180004de5  cmp     eax, r8d
0x180004de8  mov     edi, eax
0x180004dea  mov     rbx, rcx
0x180004ded  cmova   edi, r8d
0x180004df1  test    edi, edi
0x180004df3  jnz     short loc_180004E07
0x180004df5  xor     eax, eax
0x180004df7  mov     rbx, [rsp+28h+arg_8]
0x180004dfc  mov     rsi, [rsp+28h+arg_10]
0x180004e01  add     rsp, 20h
0x180004e05  pop     rdi
0x180004e06  retn
0x180004e07  mov     rdx, [rcx]; Src
0x180004e0a  sub     eax, edi
0x180004e0c  mov     [rcx+8], eax
0x180004e0f  mov     rcx, rsi; void *
0x180004e12  mov     [rsp+28h+arg_0], rbp
0x180004e17  mov     r8d, edi; Size
0x180004e1a  mov     ebp, edi
0x180004e1c  call    memcpy_0
0x180004e21  mov     rax, [rbx+28h]
0x180004e25  mov     ecx, [rax+2Ch]
0x180004e28  cmp     ecx, 1
0x180004e2b  jnz     short loc_180004E3D
0x180004e2d  mov     ecx, [rbx+4Ch]
0x180004e30  mov     r8d, edi
0x180004e33  mov     rdx, rsi
0x180004e36  call    adler32
0x180004e3b  jmp     short loc_180004E50
0x180004e3d  cmp     ecx, 2
0x180004e40  jnz     short loc_180004E53
0x180004e42  mov     ecx, [rbx+4Ch]
0x180004e45  mov     r8d, edi
0x180004e48  mov     rdx, rsi
0x180004e4b  call    crc32
0x180004e50  mov     [rbx+4Ch], eax
0x180004e53  add     [rbx], rbp
0x180004e56  mov     eax, edi
0x180004e58  add     [rbx+0Ch], edi
0x180004e5b  mov     rbx, [rsp+28h+arg_8]
0x180004e60  mov     rbp, [rsp+28h+arg_0]
0x180004e65  mov     rsi, [rsp+28h+arg_10]
0x180004e6a  add     rsp, 20h
0x180004e6e  pop     rdi
0x180004e6f  retn
```
