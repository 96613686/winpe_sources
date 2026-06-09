# __crt_stdio_input::input_processor<wchar_t,__crt_stdio_input::string_input_adapter<wchar_t>>::write_character(char * const,unsigned __int64,char * &,unsigned __int64 &,wchar_t)

- ea: `0x180023a94`
- end: `0x180023b3e`
- name: `?write_character@?$input_processor@_WV?$string_input_adapter@_W@__crt_stdio_input@@@__crt_stdio_input@@AEAA_NQEAD_KAEAPEADAEA_K_W@Z`
- size: `170`
- prototype: `char __fastcall(__int64, _BYTE *, __int64, char **, rsize_t *, wchar_t)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f384`

## callees

- `0x18000bebc`
- `0x1800109b4`
- `0x180023a94`

## pseudocode

```c
char __fastcall __crt_stdio_input::input_processor<wchar_t,__crt_stdio_input::string_input_adapter<wchar_t>>::write_character(
        __int64 a1,
        _BYTE *a2,
        __int64 a3,
        char **a4,
        rsize_t *a5,
        wchar_t a6)
{
  char *v8; // rdx
  errno_t v9; // eax
  __int64 v10; // rcx
  rsize_t *v11; // rax
  rsize_t *v12; // rdi
  __int64 v14; // rax
  int v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = 0;
  v8 = *a4;
  if ( a3 == -1 )
  {
    v9 = wctomb_s(&v15, v8, 5u, a6);
    if ( v9 )
    {
      if ( v9 == 22 || v9 == 34 )
        invoke_watson(0, 0, 0, 0, 0);
    }
    else
    {
      v10 = v15;
      v11 = a5;
      *a4 += v15;
      *v11 -= v10;
    }
  }
  else
  {
    v12 = a5;
    if ( wctomb_s(&v15, v8, *a5, a6) == 34 )
    {
      *a2 = 0;
      return 0;
    }
    v14 = v15;
    if ( v15 > 0 )
    {
      *a4 += v15;
      *v12 -= v14;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180023a94  mov     rax, rsp
0x180023a97  mov     [rax+8], rbx
0x180023a9b  mov     [rax+10h], rsi
0x180023a9f  push    rdi
0x180023aa0  sub     rsp, 30h
0x180023aa4  and     dword ptr [rax+18h], 0
0x180023aa8  lea     rcx, [rax+18h]; SizeConverted
0x180023aac  mov     rbx, r9
0x180023aaf  movzx   r9d, [rsp+38h+arg_28]; WCh
0x180023ab5  mov     rsi, rdx
0x180023ab8  mov     rdx, [rbx]; MbCh
0x180023abb  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180023abf  jnz     short loc_180023AEE
0x180023ac1  mov     r8d, 5; SizeInBytes
0x180023ac7  call    wctomb_s
0x180023acc  test    eax, eax
0x180023ace  jz      short loc_180023ADC
0x180023ad0  cmp     eax, 16h
0x180023ad3  jz      short loc_180023B28
0x180023ad5  cmp     eax, 22h ; '"'
0x180023ad8  jz      short loc_180023B28
0x180023ada  jmp     short loc_180023B16
0x180023adc  movsxd  rcx, [rsp+38h+arg_10]
0x180023ae1  mov     rax, [rsp+38h+arg_20]
0x180023ae6  add     [rbx], rcx
0x180023ae9  sub     [rax], rcx
0x180023aec  jmp     short loc_180023B16
0x180023aee  mov     rdi, [rsp+38h+arg_20]
0x180023af3  mov     r8, [rdi]; SizeInBytes
0x180023af6  call    wctomb_s
0x180023afb  cmp     eax, 22h ; '"'
0x180023afe  jnz     short loc_180023B07
0x180023b00  mov     byte ptr [rsi], 0
0x180023b03  xor     al, al
0x180023b05  jmp     short loc_180023B18
0x180023b07  movsxd  rax, [rsp+38h+arg_10]
0x180023b0c  test    eax, eax
0x180023b0e  jle     short loc_180023B16
0x180023b10  add     [rbx], rax
0x180023b13  sub     [rdi], rax
0x180023b16  mov     al, 1
0x180023b18  mov     rbx, [rsp+38h+arg_0]
0x180023b1d  mov     rsi, [rsp+38h+arg_8]
0x180023b22  add     rsp, 30h
0x180023b26  pop     rdi
0x180023b27  retn
0x180023b28  and     [rsp+38h+var_18], 0
0x180023b2e  xor     r9d, r9d; LineNo
0x180023b31  xor     r8d, r8d; FileName
0x180023b34  xor     edx, edx; FunctionName
0x180023b36  xor     ecx, ecx; Expression
0x180023b38  call    _invoke_watson
```
