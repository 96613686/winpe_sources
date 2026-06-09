# GetShrinkedSize

- ea: `0x180033c2c`
- end: `0x180033d07`
- name: `GetShrinkedSize`
- size: `219`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800129e0`
- `0x180033d10`
- `0x180033e20`
- `0x180033ea4`
- `0x18003418c`
- `0x180034538`
- `0x18003466c`

## callees

- `0x180033c2c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180033ccc`
- `KERNEL32!SetLastError` at `0x180033ccc`

## pseudocode

```c
__int64 __fastcall GetShrinkedSize(_DWORD *a1, unsigned __int64 *a2)
{
  unsigned __int64 v4; // r8
  unsigned int v5; // ebx
  unsigned int v6; // edi
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // r10d
  __int64 v10; // r10
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  DWORD v13; // ecx

  *a2 = 0;
  if ( *a1 == -1 )
  {
    v7 = 0;
LABEL_17:
    v4 = 4;
  }
  else
  {
    v4 = 0;
    v5 = 0;
    v6 = 0;
    v7 = 0;
    do
    {
      v8 = 8LL * v6;
      v9 = a1[v8 + 6];
      if ( v9 )
      {
        if ( v9 != 1 )
        {
          v13 = 87;
LABEL_14:
          SetLastError(v13);
          return v5;
        }
        v10 = 4;
        v11 = 4;
      }
      else
      {
        v10 = *(_QWORD *)&a1[v8 + 2];
        v11 = *(_QWORD *)&a1[v8 + 4];
      }
      v12 = -(__int64)v11 & (v11 + v7 - 1);
      *a2 = v12;
      if ( v11 <= v4 )
        v11 = v4;
      v4 = v11;
      if ( v12 > 0xFFFFFFFFLL - v10 )
      {
        v13 = 534;
        goto LABEL_14;
      }
      ++v6;
      v7 = v10 + v12;
      *a2 = v7;
    }
    while ( a1[8 * v6] != -1 );
    if ( v11 < 4 )
      goto LABEL_17;
  }
  v5 = 1;
  *a2 = -(__int64)v4 & (v7 + v4 - 1);
  return v5;
}

```

## disassembly

```asm
0x180033c2c  push    rbx
0x180033c2e  push    rbp
0x180033c2f  push    rsi
0x180033c30  push    rdi
0x180033c31  sub     rsp, 28h
0x180033c35  mov     ebp, 0FFFFFFFFh
0x180033c3a  mov     qword ptr [rdx], 0
0x180033c41  mov     r11, rdx
0x180033c44  mov     r9, rcx
0x180033c47  mov     esi, 4
0x180033c4c  cmp     [rcx], ebp
0x180033c4e  jz      loc_180033CE1
0x180033c54  xor     r8d, r8d
0x180033c57  xor     ebx, ebx
0x180033c59  xor     edi, edi
0x180033c5b  xor     edx, edx
0x180033c5d  mov     ecx, edi
0x180033c5f  shl     rcx, 5
0x180033c63  mov     r10d, [rcx+r9+18h]
0x180033c68  test    r10d, r10d
0x180033c6b  jz      short loc_180033C7B
0x180033c6d  cmp     r10d, 1
0x180033c71  jnz     short loc_180033CC7
0x180033c73  mov     r10, rsi
0x180033c76  mov     rcx, rsi
0x180033c79  jmp     short loc_180033C85
0x180033c7b  mov     r10, [rcx+r9+8]
0x180033c80  mov     rcx, [rcx+r9+10h]
0x180033c85  dec     rdx
0x180033c88  mov     rax, rcx
0x180033c8b  neg     rax
0x180033c8e  add     rdx, rcx
0x180033c91  and     rdx, rax
0x180033c94  mov     rax, rbp
0x180033c97  cmp     rcx, r8
0x180033c9a  mov     [r11], rdx
0x180033c9d  cmovbe  rcx, r8
0x180033ca1  sub     rax, r10
0x180033ca4  mov     r8, rcx
0x180033ca7  cmp     rdx, rax
0x180033caa  ja      short loc_180033CDA
0x180033cac  inc     edi
0x180033cae  add     rdx, r10
0x180033cb1  mov     eax, edi
0x180033cb3  shl     rax, 5
0x180033cb7  mov     [r11], rdx
0x180033cba  cmp     [rax+r9], ebp
0x180033cbe  jnz     short loc_180033C5D
0x180033cc0  cmp     rcx, rsi
0x180033cc3  jb      short loc_180033CE3
0x180033cc5  jmp     short loc_180033CE6
0x180033cc7  mov     ecx, 57h ; 'W'; dwErrCode
0x180033ccc  call    cs:__imp_SetLastError
0x180033cd3  nop     dword ptr [rax+rax+00h]
0x180033cd8  jmp     short loc_180033CFB
0x180033cda  mov     ecx, 216h
0x180033cdf  jmp     short loc_180033CCC
0x180033ce1  xor     edx, edx
0x180033ce3  mov     r8, rsi
0x180033ce6  lea     rax, [r8-1]
0x180033cea  mov     ebx, 1
0x180033cef  add     rax, rdx
0x180033cf2  neg     r8
0x180033cf5  and     rax, r8
0x180033cf8  mov     [r11], rax
0x180033cfb  mov     eax, ebx
0x180033cfd  add     rsp, 28h
0x180033d01  pop     rdi
0x180033d02  pop     rsi
0x180033d03  pop     rbp
0x180033d04  pop     rbx
0x180033d05  retn
```
