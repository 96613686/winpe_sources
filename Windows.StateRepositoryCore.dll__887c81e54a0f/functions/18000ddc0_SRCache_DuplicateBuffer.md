# SRCache_DuplicateBuffer

- ea: `0x18000ddc0`
- end: `0x18000de30`
- name: `SRCache_DuplicateBuffer`
- size: `112`
- prototype: `__int64 __fastcall(size_t Size, void *Src, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000940c`
- `0x18000be7c`
- `0x18000ddc0`
- `0x180010070`

## string_xrefs

- `0x18000ddf7`: `onecore\base\appmodel\staterepository\core\lib\srcache.cpp`

## pseudocode

```c
__int64 __fastcall SRCache_DuplicateBuffer(size_t Size, void *Src, _QWORD *a3)
{
  size_t v5; // rsi
  void *v6; // rbx
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *v10; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  if ( (_DWORD)Size )
  {
    v5 = (unsigned int)Size;
    wil::make_unique_nothrow<unsigned char [0]>(&v10, (unsigned int)Size);
    v6 = v10;
    if ( !v10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcache.cpp",
        (const char *)0x8007000ELL,
        v8);
      return 2147942414LL;
    }
    memcpy_0(v10, Src, v5);
    *a3 = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x18000ddc0  push    rbx
0x18000ddc2  push    rbp
0x18000ddc3  push    rsi
0x18000ddc4  push    rdi
0x18000ddc5  sub     rsp, 28h
0x18000ddc9  mov     qword ptr [r8], 0
0x18000ddd0  mov     rdi, r8
0x18000ddd3  mov     rbp, rdx
0x18000ddd6  test    ecx, ecx
0x18000ddd8  jz      short loc_18000DE25
0x18000ddda  mov     esi, ecx
0x18000dddc  mov     edx, ecx
0x18000ddde  lea     rcx, [rsp+48h+arg_10]
0x18000dde3  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18000dde8  mov     rbx, [rsp+48h+arg_10]
0x18000dded  test    rbx, rbx
0x18000ddf0  jnz     short loc_18000DE14
0x18000ddf2  mov     rcx, [rsp+48h]; this
0x18000ddf7  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18000ddfe  mov     ebx, 8007000Eh
0x18000de03  mov     edx, 4Ch ; 'L'; void *
0x18000de08  mov     r9d, ebx; char *
0x18000de0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de10  mov     eax, ebx
0x18000de12  jmp     short loc_18000DE27
0x18000de14  mov     r8, rsi; Size
0x18000de17  mov     rdx, rbp; Src
0x18000de1a  mov     rcx, rbx; void *
0x18000de1d  call    memcpy_0
0x18000de22  mov     [rdi], rbx
0x18000de25  xor     eax, eax
0x18000de27  add     rsp, 28h
0x18000de2b  pop     rdi
0x18000de2c  pop     rsi
0x18000de2d  pop     rbp
0x18000de2e  pop     rbx
0x18000de2f  retn
```
