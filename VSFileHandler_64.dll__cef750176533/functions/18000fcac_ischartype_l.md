# _ischartype_l

- ea: `0x18000fcac`
- end: `0x18000fd22`
- name: `_ischartype_l`
- size: `118`
- prototype: `int __cdecl(const int C, const int Mask, const _locale_t Locale)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e8b8`
- `0x18000f264`
- `0x18001b7e8`
- `0x18001e320`
- `0x18001f908`

## callees

- `0x18000fcac`
- `0x180014700`
- `0x18001479c`

## pseudocode

```c
int __cdecl ischartype_l(const int C, const int Mask, const _locale_t Locale)
{
  __int64 v3; // rdi
  int v4; // ebx
  unsigned __int16 v5; // si
  unsigned int v6; // ebp
  struct __crt_locale_data *locinfo; // rax
  const unsigned __int16 *v9; // rax

  v3 = C;
  v4 = 0;
  v5 = Mask;
  v6 = C + 1;
  if ( Locale )
  {
    locinfo = Locale->locinfo;
    if ( v6 > 0x100 )
    {
      if ( *((int *)locinfo + 2) <= 1 )
        return 0;
      else
        return isctype_l(C, (unsigned __int16)Mask, Locale);
    }
    else
    {
      return (unsigned __int16)Mask & *(_WORD *)(*(_QWORD *)locinfo + 2LL * C);
    }
  }
  else
  {
    v9 = _pctype_func();
    if ( v6 <= 0x100 )
      return v5 & v9[v3];
    return v4;
  }
}

```

## disassembly

```asm
0x18000fcac  mov     [rsp+arg_0], rbx
0x18000fcb1  mov     [rsp+arg_8], rbp
0x18000fcb6  mov     [rsp+arg_10], rsi
0x18000fcbb  push    rdi
0x18000fcbc  sub     rsp, 20h
0x18000fcc0  movsxd  rdi, ecx
0x18000fcc3  xor     ebx, ebx
0x18000fcc5  mov     esi, edx
0x18000fcc7  lea     ebp, [rdi+1]
0x18000fcca  test    r8, r8
0x18000fccd  jz      short loc_18000FCF8
0x18000fccf  mov     rax, [r8]
0x18000fcd2  cmp     ebp, 100h
0x18000fcd8  ja      short loc_18000FCE5
0x18000fcda  mov     rax, [rax]
0x18000fcdd  movzx   eax, word ptr [rax+rdi*2]
0x18000fce1  and     eax, edx
0x18000fce3  jmp     short loc_18000FD0D
0x18000fce5  cmp     dword ptr [rax+8], 1
0x18000fce9  jle     short loc_18000FCF4
0x18000fceb  mov     ecx, edi; C
0x18000fced  call    _isctype_l
0x18000fcf2  jmp     short loc_18000FD0D
0x18000fcf4  xor     eax, eax
0x18000fcf6  jmp     short loc_18000FD0D
0x18000fcf8  call    __pctype_func
0x18000fcfd  cmp     ebp, 100h
0x18000fd03  ja      short loc_18000FD0B
0x18000fd05  movzx   ebx, word ptr [rax+rdi*2]
0x18000fd09  and     ebx, esi
0x18000fd0b  mov     eax, ebx
0x18000fd0d  mov     rbx, [rsp+28h+arg_0]
0x18000fd12  mov     rbp, [rsp+28h+arg_8]
0x18000fd17  mov     rsi, [rsp+28h+arg_10]
0x18000fd1c  add     rsp, 20h
0x18000fd20  pop     rdi
0x18000fd21  retn
```
