# __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)

- ea: `0x180055d68`
- end: `0x180055e49`
- name: `?write_string_impl@?$output_adapter_common@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z`
- size: `225`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004b464`
- `0x18004ba60`
- `0x18004c098`
- `0x180054cb0`
- `0x180054f40`
- `0x1800551d0`
- `0x180055b24`

## callees

- `0x180055d68`
- `0x1800588a8`

## pseudocode

```c
__int64 __fastcall __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(
        __int64 *a1,
        unsigned __int16 *a2,
        int a3,
        _DWORD *a4,
        __int64 a5)
{
  __int64 result; // rax
  unsigned __int16 *v7; // r14
  __int64 v9; // rbx
  unsigned __int16 *v10; // rbp

  result = a3;
  v7 = a2;
  v9 = *(_QWORD *)(a5 + 44);
  v10 = &a2[a3];
  if ( a2 != v10 )
  {
    do
    {
      if ( (*(_DWORD *)(*a1 + 20) & 0x1000) != 0 )
      {
        result = *a1;
        if ( !*(_QWORD *)(*a1 + 8) )
          goto LABEL_10;
      }
      result = fputwc_nolock_internal(*v7, *a1, a5);
      if ( (_WORD)result != 0xFFFF )
        goto LABEL_10;
      if ( !*(_BYTE *)(a5 + 48) || *(_DWORD *)(a5 + 44) != 42 )
      {
        *a4 = -1;
        break;
      }
      if ( ((*(_DWORD *)(*a1 + 20) & 0x1000) == 0 || (result = *a1, *(_QWORD *)(*a1 + 8)))
        && (result = fputwc_nolock_internal(63, *a1, a5), (_WORD)result == 0xFFFF) )
      {
        *a4 = -1;
      }
      else
      {
LABEL_10:
        ++*a4;
      }
      ++v7;
    }
    while ( v7 != v10 );
  }
  *(_QWORD *)(a5 + 44) = v9;
  return result;
}

```

## disassembly

```asm
0x180055d68  mov     [rsp+arg_0], rbx
0x180055d6d  mov     [rsp+arg_8], rbp
0x180055d72  mov     [rsp+arg_10], rsi
0x180055d77  push    rdi
0x180055d78  push    r14
0x180055d7a  push    r15
0x180055d7c  sub     rsp, 20h
0x180055d80  mov     rsi, [rsp+38h+arg_20]
0x180055d85  mov     rdi, r9
0x180055d88  movsxd  rax, r8d
0x180055d8b  mov     r14, rdx
0x180055d8e  mov     r15, rcx
0x180055d91  mov     rbx, [rsi+2Ch]
0x180055d95  lea     rbp, [rdx+rax*2]
0x180055d99  cmp     rdx, rbp
0x180055d9c  jz      loc_180055E2C
0x180055da2  mov     rax, [r15]
0x180055da5  movzx   ecx, word ptr [r14]
0x180055da9  mov     edx, [rax+14h]
0x180055dac  nop
0x180055dad  shr     edx, 0Ch
0x180055db0  test    dl, 1
0x180055db3  jz      short loc_180055DBF
0x180055db5  mov     rax, [r15]
0x180055db8  cmp     qword ptr [rax+8], 0
0x180055dbd  jz      short loc_180055E13
0x180055dbf  mov     rdx, [r15]
0x180055dc2  mov     r8, rsi
0x180055dc5  call    _fputwc_nolock_internal
0x180055dca  mov     ecx, 0FFFFh
0x180055dcf  cmp     ax, cx
0x180055dd2  jnz     short loc_180055E13
0x180055dd4  cmp     byte ptr [rsi+30h], 0
0x180055dd8  jz      short loc_180055E29
0x180055dda  cmp     dword ptr [rsi+2Ch], 2Ah ; '*'
0x180055dde  jnz     short loc_180055E29
0x180055de0  mov     rax, [r15]
0x180055de3  mov     ecx, [rax+14h]
0x180055de6  nop
0x180055de7  shr     ecx, 0Ch
0x180055dea  test    cl, 1
0x180055ded  jz      short loc_180055DF9
0x180055def  mov     rax, [r15]
0x180055df2  cmp     qword ptr [rax+8], 0
0x180055df7  jz      short loc_180055E13
0x180055df9  mov     rdx, [r15]
0x180055dfc  mov     ecx, 3Fh ; '?'
0x180055e01  mov     r8, rsi
0x180055e04  call    _fputwc_nolock_internal
0x180055e09  mov     ecx, 0FFFFh
0x180055e0e  cmp     ax, cx
0x180055e11  jz      short loc_180055E17
0x180055e13  inc     dword ptr [rdi]
0x180055e15  jmp     short loc_180055E1A
0x180055e17  or      dword ptr [rdi], 0FFFFFFFFh
0x180055e1a  add     r14, 2
0x180055e1e  cmp     r14, rbp
0x180055e21  jnz     loc_180055DA2
0x180055e27  jmp     short loc_180055E2C
0x180055e29  or      dword ptr [rdi], 0FFFFFFFFh
0x180055e2c  mov     rbp, [rsp+38h+arg_8]
0x180055e31  mov     [rsi+2Ch], rbx
0x180055e35  mov     rbx, [rsp+38h+arg_0]
0x180055e3a  mov     rsi, [rsp+38h+arg_10]
0x180055e3f  add     rsp, 20h
0x180055e43  pop     r15
0x180055e45  pop     r14
0x180055e47  pop     rdi
0x180055e48  retn
```
