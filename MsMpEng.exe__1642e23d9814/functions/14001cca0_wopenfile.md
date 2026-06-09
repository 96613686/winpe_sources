# _wopenfile

- ea: `0x14001cca0`
- end: `0x14001cd3a`
- name: `_wopenfile`
- size: `154`
- prototype: `__int64 __fastcall(int, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140016ec4`

## callees

- `0x14001c99c`
- `0x14001cca0`
- `0x140022aa8`

## pseudocode

```c
__int64 __fastcall wopenfile(int a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v7; // rax
  __int64 v8; // rbx
  int v9; // eax
  __int64 v11; // [rsp+30h] [rbp-28h]
  __int64 v12; // [rsp+40h] [rbp-18h] BYREF
  int v13; // [rsp+70h] [rbp+18h] BYREF

  v7 = __acrt_stdio_parse_mode<wchar_t>(&v12);
  v8 = 0;
  v11 = *(_QWORD *)v7;
  if ( *(_BYTE *)(v7 + 8) )
  {
    v13 = 0;
    if ( !(unsigned int)sub_140022AA8((unsigned int)&v13, a1, v11, a3, 384) )
    {
      ++dword_14003E5D8;
      _InterlockedOr((volatile signed __int32 *)(a4 + 20), HIDWORD(v11));
      v9 = v13;
      *(_DWORD *)(a4 + 16) = 0;
      *(_QWORD *)(a4 + 40) = 0;
      *(_QWORD *)(a4 + 8) = 0;
      *(_QWORD *)a4 = 0;
      v8 = a4;
      *(_DWORD *)(a4 + 24) = v9;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14001cca0  mov     rax, rsp
0x14001cca3  mov     [rax+8], rbx
0x14001cca7  mov     [rax+10h], rbp
0x14001ccab  mov     [rax+20h], rsi
0x14001ccaf  push    rdi
0x14001ccb0  sub     rsp, 50h
0x14001ccb4  mov     rbp, rcx
0x14001ccb7  mov     rdi, r9
0x14001ccba  lea     rcx, [rax-18h]
0x14001ccbe  mov     esi, r8d
0x14001ccc1  call    ??$__acrt_stdio_parse_mode@_W@@YA?AU__acrt_stdio_stream_mode@@QEB_W@Z
0x14001ccc6  xor     ebx, ebx
0x14001ccc8  movsd   xmm0, qword ptr [rax]
0x14001cccc  movsd   [rsp+58h+var_28], xmm0
0x14001ccd2  cmp     [rax+8], bl
0x14001ccd5  jz      short loc_14001CD22
0x14001ccd7  mov     r8d, dword ptr [rsp+58h+var_28]
0x14001ccdc  lea     rcx, [rsp+58h+arg_10]
0x14001cce1  mov     r9d, esi
0x14001cce4  mov     [rsp+58h+arg_10], ebx
0x14001cce8  mov     rdx, rbp
0x14001cceb  mov     [rsp+58h+var_38], 180h
0x14001ccf3  call    sub_140022AA8
0x14001ccf8  test    eax, eax
0x14001ccfa  jnz     short loc_14001CD22
0x14001ccfc  inc     cs:dword_14003E5D8
0x14001cd02  mov     eax, dword ptr [rsp+58h+var_28+4]
0x14001cd06  lock or [rdi+14h], eax
0x14001cd0a  mov     eax, [rsp+58h+arg_10]
0x14001cd0e  mov     [rdi+10h], ebx
0x14001cd11  mov     [rdi+28h], rbx
0x14001cd15  mov     [rdi+8], rbx
0x14001cd19  mov     [rdi], rbx
0x14001cd1c  mov     rbx, rdi
0x14001cd1f  mov     [rdi+18h], eax
0x14001cd22  mov     rbp, [rsp+58h+arg_8]
0x14001cd27  mov     rax, rbx
0x14001cd2a  mov     rbx, [rsp+58h+arg_0]
0x14001cd2f  mov     rsi, [rsp+58h+arg_18]
0x14001cd34  add     rsp, 50h
0x14001cd38  pop     rdi
0x14001cd39  retn
```
