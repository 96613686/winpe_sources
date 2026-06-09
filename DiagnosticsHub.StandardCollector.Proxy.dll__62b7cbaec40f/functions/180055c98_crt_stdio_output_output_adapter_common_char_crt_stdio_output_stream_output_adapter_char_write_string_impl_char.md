# __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)

- ea: `0x180055c98`
- end: `0x180055d67`
- name: `?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z`
- size: `207`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180049714`
- `0x180049c4c`
- `0x18004a19c`
- `0x18005420c`
- `0x1800543f8`
- `0x1800545e4`
- `0x180055afc`

## callees

- `0x180055c98`
- `0x180058d24`

## pseudocode

```c
void __fastcall __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(
        _QWORD *a1,
        char *a2,
        int a3,
        _DWORD *a4,
        __int64 a5)
{
  char *v6; // r14
  char *v7; // rbp
  __int64 v9; // rbx

  v6 = a2;
  v7 = &a2[a3];
  v9 = *(_QWORD *)(a5 + 44);
  if ( a2 != v7 )
  {
    do
    {
      if ( (*(_DWORD *)(*a1 + 20LL) & 0x1000) != 0 && !*(_QWORD *)(*a1 + 8LL)
        || (unsigned int)fputc_nolock_internal((unsigned int)*v6, *a1, a5) != -1 )
      {
        goto LABEL_10;
      }
      if ( !*(_BYTE *)(a5 + 48) || *(_DWORD *)(a5 + 44) != 42 )
      {
        *a4 = -1;
        break;
      }
      if ( ((*(_DWORD *)(*a1 + 20LL) & 0x1000) == 0 || *(_QWORD *)(*a1 + 8LL))
        && (unsigned int)fputc_nolock_internal(63, *a1, a5) == -1 )
      {
        *a4 = -1;
      }
      else
      {
LABEL_10:
        ++*a4;
      }
      ++v6;
    }
    while ( v6 != v7 );
  }
  *(_QWORD *)(a5 + 44) = v9;
}

```

## disassembly

```asm
0x180055c98  mov     [rsp+arg_0], rbx
0x180055c9d  mov     [rsp+arg_8], rbp
0x180055ca2  mov     [rsp+arg_10], rsi
0x180055ca7  push    rdi
0x180055ca8  push    r14
0x180055caa  push    r15
0x180055cac  sub     rsp, 20h
0x180055cb0  mov     rsi, [rsp+38h+arg_20]
0x180055cb5  mov     rdi, r9
0x180055cb8  movsxd  rbp, r8d
0x180055cbb  mov     r14, rdx
0x180055cbe  add     rbp, rdx
0x180055cc1  mov     r15, rcx
0x180055cc4  mov     rbx, [rsi+2Ch]
0x180055cc8  cmp     rdx, rbp
0x180055ccb  jz      short loc_180055D4A
0x180055ccd  mov     rax, [r15]
0x180055cd0  movsx   edx, byte ptr [r14]
0x180055cd4  mov     ecx, [rax+14h]
0x180055cd7  nop
0x180055cd8  shr     ecx, 0Ch
0x180055cdb  test    cl, 1
0x180055cde  jz      short loc_180055CEA
0x180055ce0  mov     rax, [r15]
0x180055ce3  cmp     qword ptr [rax+8], 0
0x180055ce8  jz      short loc_180055D36
0x180055cea  mov     ecx, edx
0x180055cec  mov     r8, rsi
0x180055cef  mov     rdx, [r15]
0x180055cf2  call    _fputc_nolock_internal
0x180055cf7  cmp     eax, 0FFFFFFFFh
0x180055cfa  jnz     short loc_180055D36
0x180055cfc  cmp     byte ptr [rsi+30h], 0
0x180055d00  jz      short loc_180055D47
0x180055d02  cmp     dword ptr [rsi+2Ch], 2Ah ; '*'
0x180055d06  jnz     short loc_180055D47
0x180055d08  mov     rax, [r15]
0x180055d0b  mov     ecx, [rax+14h]
0x180055d0e  nop
0x180055d0f  shr     ecx, 0Ch
0x180055d12  test    cl, 1
0x180055d15  jz      short loc_180055D21
0x180055d17  mov     rax, [r15]
0x180055d1a  cmp     qword ptr [rax+8], 0
0x180055d1f  jz      short loc_180055D36
0x180055d21  mov     rdx, [r15]
0x180055d24  mov     r8, rsi
0x180055d27  mov     ecx, 3Fh ; '?'
0x180055d2c  call    _fputc_nolock_internal
0x180055d31  cmp     eax, 0FFFFFFFFh
0x180055d34  jz      short loc_180055D3A
0x180055d36  inc     dword ptr [rdi]
0x180055d38  jmp     short loc_180055D3D
0x180055d3a  or      dword ptr [rdi], 0FFFFFFFFh
0x180055d3d  inc     r14
0x180055d40  cmp     r14, rbp
0x180055d43  jnz     short loc_180055CCD
0x180055d45  jmp     short loc_180055D4A
0x180055d47  or      dword ptr [rdi], 0FFFFFFFFh
0x180055d4a  mov     rbp, [rsp+38h+arg_8]
0x180055d4f  mov     [rsi+2Ch], rbx
0x180055d53  mov     rbx, [rsp+38h+arg_0]
0x180055d58  mov     rsi, [rsp+38h+arg_10]
0x180055d5d  add     rsp, 20h
0x180055d61  pop     r15
0x180055d63  pop     r14
0x180055d65  pop     rdi
0x180055d66  retn
```
