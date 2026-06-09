# __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)

- ea: `0x180055a88`
- end: `0x180055b69`
- name: `?write_string_impl@?$output_adapter_common@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z`
- size: `225`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004b184`
- `0x18004b780`
- `0x18004bdb8`
- `0x1800549d0`
- `0x180054c60`
- `0x180054ef0`
- `0x180055844`

## callees

- `0x180055a88`
- `0x1800585c8`

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
0x180055a88  mov     [rsp+arg_0], rbx
0x180055a8d  mov     [rsp+arg_8], rbp
0x180055a92  mov     [rsp+arg_10], rsi
0x180055a97  push    rdi
0x180055a98  push    r14
0x180055a9a  push    r15
0x180055a9c  sub     rsp, 20h
0x180055aa0  mov     rsi, [rsp+38h+arg_20]
0x180055aa5  mov     rdi, r9
0x180055aa8  movsxd  rax, r8d
0x180055aab  mov     r14, rdx
0x180055aae  mov     r15, rcx
0x180055ab1  mov     rbx, [rsi+2Ch]
0x180055ab5  lea     rbp, [rdx+rax*2]
0x180055ab9  cmp     rdx, rbp
0x180055abc  jz      loc_180055B4C
0x180055ac2  mov     rax, [r15]
0x180055ac5  movzx   ecx, word ptr [r14]
0x180055ac9  mov     edx, [rax+14h]
0x180055acc  nop
0x180055acd  shr     edx, 0Ch
0x180055ad0  test    dl, 1
0x180055ad3  jz      short loc_180055ADF
0x180055ad5  mov     rax, [r15]
0x180055ad8  cmp     qword ptr [rax+8], 0
0x180055add  jz      short loc_180055B33
0x180055adf  mov     rdx, [r15]
0x180055ae2  mov     r8, rsi
0x180055ae5  call    _fputwc_nolock_internal
0x180055aea  mov     ecx, 0FFFFh
0x180055aef  cmp     ax, cx
0x180055af2  jnz     short loc_180055B33
0x180055af4  cmp     byte ptr [rsi+30h], 0
0x180055af8  jz      short loc_180055B49
0x180055afa  cmp     dword ptr [rsi+2Ch], 2Ah ; '*'
0x180055afe  jnz     short loc_180055B49
0x180055b00  mov     rax, [r15]
0x180055b03  mov     ecx, [rax+14h]
0x180055b06  nop
0x180055b07  shr     ecx, 0Ch
0x180055b0a  test    cl, 1
0x180055b0d  jz      short loc_180055B19
0x180055b0f  mov     rax, [r15]
0x180055b12  cmp     qword ptr [rax+8], 0
0x180055b17  jz      short loc_180055B33
0x180055b19  mov     rdx, [r15]
0x180055b1c  mov     ecx, 3Fh ; '?'
0x180055b21  mov     r8, rsi
0x180055b24  call    _fputwc_nolock_internal
0x180055b29  mov     ecx, 0FFFFh
0x180055b2e  cmp     ax, cx
0x180055b31  jz      short loc_180055B37
0x180055b33  inc     dword ptr [rdi]
0x180055b35  jmp     short loc_180055B3A
0x180055b37  or      dword ptr [rdi], 0FFFFFFFFh
0x180055b3a  add     r14, 2
0x180055b3e  cmp     r14, rbp
0x180055b41  jnz     loc_180055AC2
0x180055b47  jmp     short loc_180055B4C
0x180055b49  or      dword ptr [rdi], 0FFFFFFFFh
0x180055b4c  mov     rbp, [rsp+38h+arg_8]
0x180055b51  mov     [rsi+2Ch], rbx
0x180055b55  mov     rbx, [rsp+38h+arg_0]
0x180055b5a  mov     rsi, [rsp+38h+arg_10]
0x180055b5f  add     rsp, 20h
0x180055b63  pop     r15
0x180055b65  pop     r14
0x180055b67  pop     rdi
0x180055b68  retn
```
