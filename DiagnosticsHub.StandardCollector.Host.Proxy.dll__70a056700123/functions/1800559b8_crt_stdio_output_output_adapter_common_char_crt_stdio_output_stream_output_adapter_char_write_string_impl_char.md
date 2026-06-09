# __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)

- ea: `0x1800559b8`
- end: `0x180055a87`
- name: `?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z`
- size: `207`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180049434`
- `0x18004996c`
- `0x180049ebc`
- `0x180053f2c`
- `0x180054118`
- `0x180054304`
- `0x18005581c`

## callees

- `0x1800559b8`
- `0x180058a44`

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
0x1800559b8  mov     [rsp+arg_0], rbx
0x1800559bd  mov     [rsp+arg_8], rbp
0x1800559c2  mov     [rsp+arg_10], rsi
0x1800559c7  push    rdi
0x1800559c8  push    r14
0x1800559ca  push    r15
0x1800559cc  sub     rsp, 20h
0x1800559d0  mov     rsi, [rsp+38h+arg_20]
0x1800559d5  mov     rdi, r9
0x1800559d8  movsxd  rbp, r8d
0x1800559db  mov     r14, rdx
0x1800559de  add     rbp, rdx
0x1800559e1  mov     r15, rcx
0x1800559e4  mov     rbx, [rsi+2Ch]
0x1800559e8  cmp     rdx, rbp
0x1800559eb  jz      short loc_180055A6A
0x1800559ed  mov     rax, [r15]
0x1800559f0  movsx   edx, byte ptr [r14]
0x1800559f4  mov     ecx, [rax+14h]
0x1800559f7  nop
0x1800559f8  shr     ecx, 0Ch
0x1800559fb  test    cl, 1
0x1800559fe  jz      short loc_180055A0A
0x180055a00  mov     rax, [r15]
0x180055a03  cmp     qword ptr [rax+8], 0
0x180055a08  jz      short loc_180055A56
0x180055a0a  mov     ecx, edx
0x180055a0c  mov     r8, rsi
0x180055a0f  mov     rdx, [r15]
0x180055a12  call    _fputc_nolock_internal
0x180055a17  cmp     eax, 0FFFFFFFFh
0x180055a1a  jnz     short loc_180055A56
0x180055a1c  cmp     byte ptr [rsi+30h], 0
0x180055a20  jz      short loc_180055A67
0x180055a22  cmp     dword ptr [rsi+2Ch], 2Ah ; '*'
0x180055a26  jnz     short loc_180055A67
0x180055a28  mov     rax, [r15]
0x180055a2b  mov     ecx, [rax+14h]
0x180055a2e  nop
0x180055a2f  shr     ecx, 0Ch
0x180055a32  test    cl, 1
0x180055a35  jz      short loc_180055A41
0x180055a37  mov     rax, [r15]
0x180055a3a  cmp     qword ptr [rax+8], 0
0x180055a3f  jz      short loc_180055A56
0x180055a41  mov     rdx, [r15]
0x180055a44  mov     r8, rsi
0x180055a47  mov     ecx, 3Fh ; '?'
0x180055a4c  call    _fputc_nolock_internal
0x180055a51  cmp     eax, 0FFFFFFFFh
0x180055a54  jz      short loc_180055A5A
0x180055a56  inc     dword ptr [rdi]
0x180055a58  jmp     short loc_180055A5D
0x180055a5a  or      dword ptr [rdi], 0FFFFFFFFh
0x180055a5d  inc     r14
0x180055a60  cmp     r14, rbp
0x180055a63  jnz     short loc_1800559ED
0x180055a65  jmp     short loc_180055A6A
0x180055a67  or      dword ptr [rdi], 0FFFFFFFFh
0x180055a6a  mov     rbp, [rsp+38h+arg_8]
0x180055a6f  mov     [rsi+2Ch], rbx
0x180055a73  mov     rbx, [rsp+38h+arg_0]
0x180055a78  mov     rsi, [rsp+38h+arg_10]
0x180055a7d  add     rsp, 20h
0x180055a81  pop     r15
0x180055a83  pop     r14
0x180055a85  pop     rdi
0x180055a86  retn
```
