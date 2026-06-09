# __crt_stdio_input::input_processor<char,__crt_stdio_input::string_input_adapter<char>>::write_character(wchar_t * const,unsigned __int64,wchar_t * &,unsigned __int64 &,char)

- ea: `0x1800239fc`
- end: `0x180023a92`
- name: `?write_character@?$input_processor@DV?$string_input_adapter@D@__crt_stdio_input@@@__crt_stdio_input@@AEAA_NQEFA_W_KAEAPEFA_WAEA_KD@Z`
- size: `150`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int16 SrcCh)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f564`

## callees

- `0x180010690`
- `0x180014700`
- `0x1800239fc`

## pseudocode

```c
char __fastcall __crt_stdio_input::input_processor<char,__crt_stdio_input::string_input_adapter<char>>::write_character(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _WORD **a4,
        _QWORD *a5,
        __int16 SrcCh)
{
  __int16 v6; // di
  char *v9; // rax
  char v10; // cl
  __crt_locale_pointers *v11; // r9
  _QWORD *v12; // rax
  wchar_t DstCh; // [rsp+30h] [rbp+8h] BYREF

  v6 = (char)SrcCh;
  HIBYTE(SrcCh) = 0;
  if ( (_pctype_func()[(unsigned __int8)v6] & 0x8000u) != 0 )
  {
    v9 = (char *)a1[3];
    if ( v9 == (char *)a1[2] )
    {
      v10 = -1;
    }
    else
    {
      v10 = *v9;
      a1[3] = v9 + 1;
    }
    HIBYTE(SrcCh) = v10;
  }
  v11 = (__crt_locale_pointers *)a1[15];
  DstCh = 63;
  mbtowc_l(&DstCh, (const char *)&SrcCh, *((int *)v11->locinfo + 2), v11);
  **a4 = v6;
  v12 = a5;
  ++*a4;
  --*v12;
  return 1;
}

```

## disassembly

```asm
0x1800239fc  mov     rax, rsp
0x1800239ff  mov     [rax+10h], rbx
0x180023a03  mov     [rax+18h], rsi
0x180023a07  push    rdi
0x180023a08  sub     rsp, 20h
0x180023a0c  movsx   edi, [rsp+28h+SrcCh]
0x180023a11  mov     rsi, r9
0x180023a14  mov     [rax+30h], dil
0x180023a18  mov     rbx, rcx
0x180023a1b  mov     byte ptr [rax+31h], 0
0x180023a1f  call    __pctype_func
0x180023a24  movzx   edx, dil
0x180023a28  cmp     word ptr [rax+rdx*2], 0
0x180023a2d  jge     short loc_180023A4A
0x180023a2f  mov     rax, [rbx+18h]
0x180023a33  cmp     rax, [rbx+10h]
0x180023a37  jnz     short loc_180023A3D
0x180023a39  mov     cl, 0FFh
0x180023a3b  jmp     short loc_180023A46
0x180023a3d  mov     cl, [rax]
0x180023a3f  inc     rax
0x180023a42  mov     [rbx+18h], rax
0x180023a46  mov     [rsp+28h+arg_29], cl
0x180023a4a  mov     r9, [rbx+78h]; Locale
0x180023a4e  lea     rdx, [rsp+28h+SrcCh]; SrcCh
0x180023a53  mov     eax, 3Fh ; '?'
0x180023a58  lea     rcx, [rsp+28h+DstCh]; DstCh
0x180023a5d  mov     [rsp+28h+DstCh], ax
0x180023a62  mov     rax, [r9]
0x180023a65  movsxd  r8, dword ptr [rax+8]; SrcSizeInBytes
0x180023a69  call    _mbtowc_l
0x180023a6e  mov     rax, [rsi]
0x180023a71  mov     rbx, [rsp+28h+arg_8]
0x180023a76  mov     [rax], di
0x180023a79  mov     rax, [rsp+28h+arg_20]
0x180023a7e  add     qword ptr [rsi], 2
0x180023a82  mov     rsi, [rsp+28h+arg_10]
0x180023a87  dec     qword ptr [rax]
0x180023a8a  mov     al, 1
0x180023a8c  add     rsp, 20h
0x180023a90  pop     rdi
0x180023a91  retn
```
