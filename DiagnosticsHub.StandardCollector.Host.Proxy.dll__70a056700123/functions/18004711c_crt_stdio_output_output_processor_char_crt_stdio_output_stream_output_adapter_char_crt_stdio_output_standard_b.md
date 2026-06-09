# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::stream_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x18004711c`
- end: `0x180047245`
- name: `?state_case_normal_common@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800073e8`
- `0x1800149cc`
- `0x18004711c`
- `0x180058a44`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::stream_output_adapter<char>>>::state_case_normal_common(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // r8
  _BYTE *v4; // rax
  __int64 v5; // rax

  v1 = *(_QWORD *)(a1 + 8);
  *(_BYTE *)(a1 + 76) = 0;
  if ( !*(_BYTE *)(v1 + 40) )
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)v1);
  v3 = *(char *)(a1 + 57);
  if ( (int)v3 < -1
    || *(__int16 *)(**(_QWORD **)(v1 + 24) + 2 * v3) >= 0
    || (((*(_DWORD *)(*(_QWORD *)(a1 + 1120) + 20LL) & 0x1000) == 0 || *(_QWORD *)(*(_QWORD *)(a1 + 1120) + 8LL))
     && (unsigned int)fputc_nolock_internal((unsigned int)v3, *(_QWORD *)(a1 + 1120), *(_QWORD *)(a1 + 8)) == -1
      ? (*(_DWORD *)(a1 + 32) = -1)
      : ++*(_DWORD *)(a1 + 32),
        v4 = *(_BYTE **)(a1 + 16),
        LOBYTE(v3) = *v4,
        *(_QWORD *)(a1 + 16) = v4 + 1,
        (*(_BYTE *)(a1 + 57) = v3) != 0) )
  {
    if ( ((*(_DWORD *)(*(_QWORD *)(a1 + 1120) + 20LL) & 0x1000) == 0 || *(_QWORD *)(*(_QWORD *)(a1 + 1120) + 8LL))
      && (unsigned int)fputc_nolock_internal((unsigned int)(char)v3, *(_QWORD *)(a1 + 1120), *(_QWORD *)(a1 + 8)) == -1 )
    {
      *(_DWORD *)(a1 + 32) = -1;
    }
    else
    {
      ++*(_DWORD *)(a1 + 32);
    }
    return 1;
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 8);
    *(_BYTE *)(v5 + 48) = 1;
    *(_DWORD *)(v5 + 44) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, *(__crt_cached_ptd_host **)(a1 + 8));
    return 0;
  }
}

```

## disassembly

```asm
0x18004711c  mov     [rsp+arg_0], rbx
0x180047121  push    rdi
0x180047122  sub     rsp, 30h
0x180047126  mov     rdi, [rcx+8]
0x18004712a  mov     rbx, rcx
0x18004712d  mov     byte ptr [rcx+4Ch], 0
0x180047131  cmp     byte ptr [rdi+28h], 0
0x180047135  jnz     short loc_18004713F
0x180047137  mov     rcx, rdi; this
0x18004713a  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18004713f  movsx   r8, byte ptr [rbx+39h]
0x180047144  mov     r9, r8
0x180047147  cmp     r8d, 0FFFFFFFFh
0x18004714b  jl      loc_1800471F2
0x180047151  mov     rax, [rdi+18h]
0x180047155  mov     rcx, [rax]
0x180047158  mov     eax, 8000h
0x18004715d  test    [rcx+r8*2], ax
0x180047162  jz      loc_1800471F2
0x180047168  mov     rax, [rbx+460h]
0x18004716f  mov     r8, [rbx+8]
0x180047173  mov     edx, [rax+14h]
0x180047176  nop
0x180047177  shr     edx, 0Ch
0x18004717a  test    dl, 1
0x18004717d  jz      short loc_18004718D
0x18004717f  mov     rax, [rbx+460h]
0x180047186  cmp     qword ptr [rax+8], 0
0x18004718b  jz      short loc_1800471A1
0x18004718d  mov     rdx, [rbx+460h]
0x180047194  mov     ecx, r9d
0x180047197  call    _fputc_nolock_internal
0x18004719c  cmp     eax, 0FFFFFFFFh
0x18004719f  jz      short loc_1800471A6
0x1800471a1  inc     dword ptr [rbx+20h]
0x1800471a4  jmp     short loc_1800471AA
0x1800471a6  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800471aa  mov     rax, [rbx+10h]
0x1800471ae  mov     r8b, [rax]
0x1800471b1  inc     rax
0x1800471b4  mov     [rbx+10h], rax
0x1800471b8  mov     [rbx+39h], r8b
0x1800471bc  test    r8b, r8b
0x1800471bf  jnz     short loc_1800471F2
0x1800471c1  mov     rax, [rbx+8]
0x1800471c5  xor     r9d, r9d; LineNo
0x1800471c8  xor     r8d, r8d; FileName
0x1800471cb  xor     edx, edx; FunctionName
0x1800471cd  xor     ecx, ecx; Expression
0x1800471cf  mov     byte ptr [rax+30h], 1
0x1800471d3  mov     dword ptr [rax+2Ch], 16h
0x1800471da  mov     rax, [rbx+8]
0x1800471de  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x1800471e3  and     [rsp+38h+var_18], 0
0x1800471e9  call    _invalid_parameter_internal
0x1800471ee  xor     al, al
0x1800471f0  jmp     short loc_18004723A
0x1800471f2  mov     rax, [rbx+460h]
0x1800471f9  mov     rdx, [rbx+8]
0x1800471fd  mov     ecx, [rax+14h]
0x180047200  nop
0x180047201  shr     ecx, 0Ch
0x180047204  test    cl, 1
0x180047207  jz      short loc_180047217
0x180047209  mov     rax, [rbx+460h]
0x180047210  cmp     qword ptr [rax+8], 0
0x180047215  jz      short loc_18004722F
0x180047217  movsx   ecx, r8b
0x18004721b  mov     r8, rdx
0x18004721e  mov     rdx, [rbx+460h]
0x180047225  call    _fputc_nolock_internal
0x18004722a  cmp     eax, 0FFFFFFFFh
0x18004722d  jz      short loc_180047234
0x18004722f  inc     dword ptr [rbx+20h]
0x180047232  jmp     short loc_180047238
0x180047234  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180047238  mov     al, 1
0x18004723a  mov     rbx, [rsp+38h+arg_0]
0x18004723f  add     rsp, 30h
0x180047243  pop     rdi
0x180047244  retn
```
