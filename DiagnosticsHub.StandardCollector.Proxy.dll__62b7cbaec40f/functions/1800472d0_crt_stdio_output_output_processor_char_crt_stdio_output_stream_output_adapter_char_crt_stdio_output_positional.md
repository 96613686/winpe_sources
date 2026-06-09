# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x1800472d0`
- end: `0x1800473f9`
- name: `?state_case_normal_common@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007b48`
- `0x18001512c`
- `0x1800472d0`
- `0x180058d24`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>>::state_case_normal_common(
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
0x1800472d0  mov     [rsp+arg_0], rbx
0x1800472d5  push    rdi
0x1800472d6  sub     rsp, 30h
0x1800472da  mov     rdi, [rcx+8]
0x1800472de  mov     rbx, rcx
0x1800472e1  mov     byte ptr [rcx+4Ch], 0
0x1800472e5  cmp     byte ptr [rdi+28h], 0
0x1800472e9  jnz     short loc_1800472F3
0x1800472eb  mov     rcx, rdi; this
0x1800472ee  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800472f3  movsx   r8, byte ptr [rbx+39h]
0x1800472f8  mov     r9, r8
0x1800472fb  cmp     r8d, 0FFFFFFFFh
0x1800472ff  jl      loc_1800473A6
0x180047305  mov     rax, [rdi+18h]
0x180047309  mov     rcx, [rax]
0x18004730c  mov     eax, 8000h
0x180047311  test    [rcx+r8*2], ax
0x180047316  jz      loc_1800473A6
0x18004731c  mov     rax, [rbx+460h]
0x180047323  mov     r8, [rbx+8]
0x180047327  mov     edx, [rax+14h]
0x18004732a  nop
0x18004732b  shr     edx, 0Ch
0x18004732e  test    dl, 1
0x180047331  jz      short loc_180047341
0x180047333  mov     rax, [rbx+460h]
0x18004733a  cmp     qword ptr [rax+8], 0
0x18004733f  jz      short loc_180047355
0x180047341  mov     rdx, [rbx+460h]
0x180047348  mov     ecx, r9d
0x18004734b  call    _fputc_nolock_internal
0x180047350  cmp     eax, 0FFFFFFFFh
0x180047353  jz      short loc_18004735A
0x180047355  inc     dword ptr [rbx+20h]
0x180047358  jmp     short loc_18004735E
0x18004735a  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18004735e  mov     rax, [rbx+10h]
0x180047362  mov     r8b, [rax]
0x180047365  inc     rax
0x180047368  mov     [rbx+10h], rax
0x18004736c  mov     [rbx+39h], r8b
0x180047370  test    r8b, r8b
0x180047373  jnz     short loc_1800473A6
0x180047375  mov     rax, [rbx+8]
0x180047379  xor     r9d, r9d; LineNo
0x18004737c  xor     r8d, r8d; FileName
0x18004737f  xor     edx, edx; FunctionName
0x180047381  xor     ecx, ecx; Expression
0x180047383  mov     byte ptr [rax+30h], 1
0x180047387  mov     dword ptr [rax+2Ch], 16h
0x18004738e  mov     rax, [rbx+8]
0x180047392  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x180047397  and     [rsp+38h+var_18], 0
0x18004739d  call    _invalid_parameter_internal
0x1800473a2  xor     al, al
0x1800473a4  jmp     short loc_1800473EE
0x1800473a6  mov     rax, [rbx+460h]
0x1800473ad  mov     rdx, [rbx+8]
0x1800473b1  mov     ecx, [rax+14h]
0x1800473b4  nop
0x1800473b5  shr     ecx, 0Ch
0x1800473b8  test    cl, 1
0x1800473bb  jz      short loc_1800473CB
0x1800473bd  mov     rax, [rbx+460h]
0x1800473c4  cmp     qword ptr [rax+8], 0
0x1800473c9  jz      short loc_1800473E3
0x1800473cb  movsx   ecx, r8b
0x1800473cf  mov     r8, rdx
0x1800473d2  mov     rdx, [rbx+460h]
0x1800473d9  call    _fputc_nolock_internal
0x1800473de  cmp     eax, 0FFFFFFFFh
0x1800473e1  jz      short loc_1800473E8
0x1800473e3  inc     dword ptr [rbx+20h]
0x1800473e6  jmp     short loc_1800473EC
0x1800473e8  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800473ec  mov     al, 1
0x1800473ee  mov     rbx, [rsp+38h+arg_0]
0x1800473f3  add     rsp, 30h
0x1800473f7  pop     rdi
0x1800473f8  retn
```
