# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Tidy(bool,unsigned __int64)

- ea: `0x180007274`
- end: `0x1800072d1`
- name: `?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z`
- size: `93`
- prototype: `__int64 __fastcall(void **, char, void *)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005558`
- `0x1800069e0`
- `0x180006af8`
- `0x18000d764`
- `0x18000d79c`
- `0x18000e0d8`
- `0x18000f4a0`
- `0x18001296c`

## callees

- `0x180007274`
- `0x1800080d4`
- `0x180008976`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(void **a1, char a2, void *a3)
{
  void *v5; // rsi
  __int64 result; // rax

  if ( a2 && (unsigned __int64)a1[3] >= 8 )
  {
    v5 = *a1;
    if ( a3 )
      memcpy_0(a1, *a1, 2LL * (_QWORD)a3);
    operator delete(v5);
  }
  result = 0;
  a1[3] = (void *)7;
  a1[2] = a3;
  *((_WORD *)a1 + (_QWORD)a3) = 0;
  return result;
}

```

## disassembly

```asm
0x180007274  mov     [rsp+arg_0], rbx
0x180007279  mov     [rsp+arg_8], rsi
0x18000727e  push    rdi
0x18000727f  sub     rsp, 20h
0x180007283  mov     rdi, r8
0x180007286  mov     rbx, rcx
0x180007289  test    dl, dl
0x18000728b  jz      short loc_1800072AF
0x18000728d  cmp     qword ptr [rcx+18h], 8
0x180007292  jb      short loc_1800072AF
0x180007294  mov     rsi, [rcx]
0x180007297  test    r8, r8
0x18000729a  jz      short loc_1800072A7
0x18000729c  add     r8, r8; Size
0x18000729f  mov     rdx, rsi; Src
0x1800072a2  call    memcpy_0
0x1800072a7  mov     rcx, rsi; Block
0x1800072aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072af  mov     rsi, [rsp+28h+arg_8]
0x1800072b4  xor     eax, eax
0x1800072b6  mov     qword ptr [rbx+18h], 7
0x1800072be  mov     [rbx+10h], rdi
0x1800072c2  mov     [rbx+rdi*2], ax
0x1800072c6  mov     rbx, [rsp+28h+arg_0]
0x1800072cb  add     rsp, 20h
0x1800072cf  pop     rdi
0x1800072d0  retn
```
