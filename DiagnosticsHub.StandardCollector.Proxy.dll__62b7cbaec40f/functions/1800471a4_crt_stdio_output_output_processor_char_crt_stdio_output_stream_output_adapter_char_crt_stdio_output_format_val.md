# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::stream_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x1800471a4`
- end: `0x1800472cd`
- name: `?state_case_normal_common@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007b48`
- `0x18001512c`
- `0x1800471a4`
- `0x180058d24`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::stream_output_adapter<char>>>::state_case_normal_common(
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
0x1800471a4  mov     [rsp+arg_0], rbx
0x1800471a9  push    rdi
0x1800471aa  sub     rsp, 30h
0x1800471ae  mov     rdi, [rcx+8]
0x1800471b2  mov     rbx, rcx
0x1800471b5  mov     byte ptr [rcx+4Ch], 0
0x1800471b9  cmp     byte ptr [rdi+28h], 0
0x1800471bd  jnz     short loc_1800471C7
0x1800471bf  mov     rcx, rdi; this
0x1800471c2  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800471c7  movsx   r8, byte ptr [rbx+39h]
0x1800471cc  mov     r9, r8
0x1800471cf  cmp     r8d, 0FFFFFFFFh
0x1800471d3  jl      loc_18004727A
0x1800471d9  mov     rax, [rdi+18h]
0x1800471dd  mov     rcx, [rax]
0x1800471e0  mov     eax, 8000h
0x1800471e5  test    [rcx+r8*2], ax
0x1800471ea  jz      loc_18004727A
0x1800471f0  mov     rax, [rbx+460h]
0x1800471f7  mov     r8, [rbx+8]
0x1800471fb  mov     edx, [rax+14h]
0x1800471fe  nop
0x1800471ff  shr     edx, 0Ch
0x180047202  test    dl, 1
0x180047205  jz      short loc_180047215
0x180047207  mov     rax, [rbx+460h]
0x18004720e  cmp     qword ptr [rax+8], 0
0x180047213  jz      short loc_180047229
0x180047215  mov     rdx, [rbx+460h]
0x18004721c  mov     ecx, r9d
0x18004721f  call    _fputc_nolock_internal
0x180047224  cmp     eax, 0FFFFFFFFh
0x180047227  jz      short loc_18004722E
0x180047229  inc     dword ptr [rbx+20h]
0x18004722c  jmp     short loc_180047232
0x18004722e  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180047232  mov     rax, [rbx+10h]
0x180047236  mov     r8b, [rax]
0x180047239  inc     rax
0x18004723c  mov     [rbx+10h], rax
0x180047240  mov     [rbx+39h], r8b
0x180047244  test    r8b, r8b
0x180047247  jnz     short loc_18004727A
0x180047249  mov     rax, [rbx+8]
0x18004724d  xor     r9d, r9d; LineNo
0x180047250  xor     r8d, r8d; FileName
0x180047253  xor     edx, edx; FunctionName
0x180047255  xor     ecx, ecx; Expression
0x180047257  mov     byte ptr [rax+30h], 1
0x18004725b  mov     dword ptr [rax+2Ch], 16h
0x180047262  mov     rax, [rbx+8]
0x180047266  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x18004726b  and     [rsp+38h+var_18], 0
0x180047271  call    _invalid_parameter_internal
0x180047276  xor     al, al
0x180047278  jmp     short loc_1800472C2
0x18004727a  mov     rax, [rbx+460h]
0x180047281  mov     rdx, [rbx+8]
0x180047285  mov     ecx, [rax+14h]
0x180047288  nop
0x180047289  shr     ecx, 0Ch
0x18004728c  test    cl, 1
0x18004728f  jz      short loc_18004729F
0x180047291  mov     rax, [rbx+460h]
0x180047298  cmp     qword ptr [rax+8], 0
0x18004729d  jz      short loc_1800472B7
0x18004729f  movsx   ecx, r8b
0x1800472a3  mov     r8, rdx
0x1800472a6  mov     rdx, [rbx+460h]
0x1800472ad  call    _fputc_nolock_internal
0x1800472b2  cmp     eax, 0FFFFFFFFh
0x1800472b5  jz      short loc_1800472BC
0x1800472b7  inc     dword ptr [rbx+20h]
0x1800472ba  jmp     short loc_1800472C0
0x1800472bc  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800472c0  mov     al, 1
0x1800472c2  mov     rbx, [rsp+38h+arg_0]
0x1800472c7  add     rsp, 30h
0x1800472cb  pop     rdi
0x1800472cc  retn
```
