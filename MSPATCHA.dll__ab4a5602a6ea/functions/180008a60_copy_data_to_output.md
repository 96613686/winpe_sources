# copy_data_to_output

- ea: `0x180008a60`
- end: `0x180008b33`
- name: `copy_data_to_output`
- size: `211`
- prototype: `unsigned __int64 __fastcall(__int64, int, const void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007c94`

## callees

- `0x180008a60`
- `0x180009061`

## pseudocode

```c
unsigned __int64 __fastcall copy_data_to_output(__int64 a1, int a2, const void *a3)
{
  __int64 v3; // rdi
  unsigned __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // r10
  int v8; // esi
  __int16 v9; // bp
  unsigned int v10; // ecx
  unsigned int v11; // r11d
  unsigned int v12; // r9d
  _DWORD *v13; // r8
  unsigned int v14; // edx

  v3 = a2;
  result = (unsigned __int64)memcpy_0(*(void **)(a1 + 40), a3, a2);
  if ( *(_DWORD *)(a1 + 68) && *(_DWORD *)(a1 + 76) < 0x8000u )
  {
    if ( (int)v3 > 6 )
    {
      v6 = *(_QWORD *)(a1 + 40);
      v7 = v6 + v3;
      v8 = *(_DWORD *)(v6 + v3 - 6);
      v9 = *(_WORD *)(v6 + v3 - 2);
      *(_DWORD *)(v7 - 6) = -387389208;
      *(_WORD *)(v7 - 2) = -5912;
      v10 = *(_DWORD *)(a1 + 72);
      v11 = v10 + v3 - 6;
      while ( 1 )
      {
        while ( *(_BYTE *)v6 != 0xE8 )
        {
          ++v6;
          *(_DWORD *)(a1 + 72) = ++v10;
        }
        if ( v10 >= v11 )
          break;
        v12 = *(_DWORD *)(a1 + 68);
        v13 = (_DWORD *)(v6 + 1);
        v14 = *(_DWORD *)(v6 + 1);
        if ( v14 >= v12 )
        {
          if ( -v14 <= v10 )
            *v13 = v14 + v12;
        }
        else
        {
          *v13 = v14 - v10;
        }
        *(_DWORD *)(a1 + 72) += 5;
        v6 += 5;
        v10 = *(_DWORD *)(a1 + 72);
      }
      result = v11 + 6;
      *(_DWORD *)(a1 + 72) = result;
      *(_DWORD *)(v7 - 6) = v8;
      *(_WORD *)(v7 - 2) = v9;
    }
    else
    {
      *(_DWORD *)(a1 + 72) += v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008a60  push    rbx
0x180008a62  push    rbp
0x180008a63  push    rsi
0x180008a64  push    rdi
0x180008a65  sub     rsp, 28h
0x180008a69  mov     rax, r8
0x180008a6c  movsxd  rdi, edx
0x180008a6f  mov     rbx, rcx
0x180008a72  mov     r8, rdi; Size
0x180008a75  mov     rcx, [rcx+28h]; void *
0x180008a79  mov     rdx, rax; Src
0x180008a7c  call    memcpy_0
0x180008a81  cmp     dword ptr [rbx+44h], 0
0x180008a85  jz      loc_180008B2A
0x180008a8b  cmp     dword ptr [rbx+4Ch], 8000h
0x180008a92  jnb     loc_180008B2A
0x180008a98  cmp     edi, 6
0x180008a9b  jg      short loc_180008AA5
0x180008a9d  add     [rbx+48h], edi
0x180008aa0  jmp     loc_180008B2A
0x180008aa5  mov     rax, [rbx+28h]
0x180008aa9  lea     r11d, [rdi-6]
0x180008aad  mov     rcx, 0E8E8E8E8E8E8E8E8h
0x180008ab7  lea     r10, [rax+rdi]
0x180008abb  mov     esi, [r10-6]
0x180008abf  movzx   ebp, word ptr [r10-2]
0x180008ac4  mov     [r10-6], ecx
0x180008ac8  mov     [r10-2], cx
0x180008acd  mov     ecx, [rbx+48h]
0x180008ad0  add     r11d, ecx
0x180008ad3  jmp     short loc_180008ADD
0x180008ad5  inc     rax
0x180008ad8  inc     ecx
0x180008ada  mov     [rbx+48h], ecx
0x180008add  cmp     byte ptr [rax], 0E8h
0x180008ae0  jnz     short loc_180008AD5
0x180008ae2  cmp     ecx, r11d
0x180008ae5  jnb     short loc_180008B1A
0x180008ae7  mov     r9d, [rbx+44h]
0x180008aeb  lea     r8, [rax+1]
0x180008aef  mov     edx, [r8]
0x180008af2  cmp     edx, r9d
0x180008af5  jnb     short loc_180008AFE
0x180008af7  sub     edx, ecx
0x180008af9  mov     [r8], edx
0x180008afc  jmp     short loc_180008B0D
0x180008afe  mov     eax, edx
0x180008b00  neg     eax
0x180008b02  cmp     eax, ecx
0x180008b04  ja      short loc_180008B0D
0x180008b06  lea     eax, [rdx+r9]
0x180008b0a  mov     [r8], eax
0x180008b0d  add     dword ptr [rbx+48h], 5
0x180008b11  lea     rax, [r8+4]
0x180008b15  mov     ecx, [rbx+48h]
0x180008b18  jmp     short loc_180008ADD
0x180008b1a  lea     eax, [r11+6]
0x180008b1e  mov     [rbx+48h], eax
0x180008b21  mov     [r10-6], esi
0x180008b25  mov     [r10-2], bp
0x180008b2a  add     rsp, 28h
0x180008b2e  pop     rdi
0x180008b2f  pop     rsi
0x180008b30  pop     rbp
0x180008b31  pop     rbx
0x180008b32  retn
```
