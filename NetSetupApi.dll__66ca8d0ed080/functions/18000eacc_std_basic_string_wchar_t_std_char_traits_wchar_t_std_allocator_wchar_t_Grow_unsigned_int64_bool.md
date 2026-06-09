# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Grow(unsigned __int64,bool)

- ea: `0x18000eacc`
- end: `0x18000eb2f`
- name: `?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA_N_K_N@Z`
- size: `99`
- prototype: `bool __fastcall(__int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180007528`
- `0x1800076b8`
- `0x180007eb0`
- `0x180007f54`

## callees

- `0x1800069e0`
- `0x180008230`
- `0x18000eacc`

## pseudocode

```c
bool __fastcall std::wstring::_Grow(__int64 a1, unsigned __int64 a2)
{
  bool v3; // zf
  _WORD *v4; // rdx

  if ( a2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( *(_QWORD *)(a1 + 24) < a2 )
  {
    std::wstring::_Copy((const void **)a1, a2, *(const void **)(a1 + 16));
LABEL_10:
    v3 = a2 == 0;
    return !v3;
  }
  v3 = a2 == 0;
  if ( !a2 )
  {
    if ( *(_QWORD *)(a1 + 24) < 8u )
      v4 = (_WORD *)a1;
    else
      v4 = *(_WORD **)a1;
    *(_QWORD *)(a1 + 16) = 0;
    *v4 = 0;
    goto LABEL_10;
  }
  return !v3;
}

```

## disassembly

```asm
0x18000eacc  push    rbx
0x18000eace  sub     rsp, 20h
0x18000ead2  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000eadc  mov     rbx, rdx
0x18000eadf  cmp     rdx, rax
0x18000eae2  jbe     short loc_18000EAF1
0x18000eae4  lea     rcx, aStringTooLong; "string too long"
0x18000eaeb  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000eaf1  cmp     [rcx+18h], rbx
0x18000eaf5  jnb     short loc_18000EB02
0x18000eaf7  mov     r8, [rcx+10h]
0x18000eafb  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000eb00  jmp     short loc_18000EB23
0x18000eb02  test    rbx, rbx
0x18000eb05  jnz     short loc_18000EB26
0x18000eb07  cmp     qword ptr [rcx+18h], 8
0x18000eb0c  jb      short loc_18000EB13
0x18000eb0e  mov     rdx, [rcx]
0x18000eb11  jmp     short loc_18000EB16
0x18000eb13  mov     rdx, rcx
0x18000eb16  xor     eax, eax
0x18000eb18  mov     qword ptr [rcx+10h], 0
0x18000eb20  mov     [rdx], ax
0x18000eb23  test    rbx, rbx
0x18000eb26  setnz   al
0x18000eb29  add     rsp, 20h
0x18000eb2d  pop     rbx
0x18000eb2e  retn
```
