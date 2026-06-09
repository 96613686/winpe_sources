# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::stream_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x1800473fc`
- end: `0x180047525`
- name: `?state_case_normal_common@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007b48`
- `0x18001512c`
- `0x1800473fc`
- `0x180058d24`

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
0x1800473fc  mov     [rsp+arg_0], rbx
0x180047401  push    rdi
0x180047402  sub     rsp, 30h
0x180047406  mov     rdi, [rcx+8]
0x18004740a  mov     rbx, rcx
0x18004740d  mov     byte ptr [rcx+4Ch], 0
0x180047411  cmp     byte ptr [rdi+28h], 0
0x180047415  jnz     short loc_18004741F
0x180047417  mov     rcx, rdi; this
0x18004741a  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18004741f  movsx   r8, byte ptr [rbx+39h]
0x180047424  mov     r9, r8
0x180047427  cmp     r8d, 0FFFFFFFFh
0x18004742b  jl      loc_1800474D2
0x180047431  mov     rax, [rdi+18h]
0x180047435  mov     rcx, [rax]
0x180047438  mov     eax, 8000h
0x18004743d  test    [rcx+r8*2], ax
0x180047442  jz      loc_1800474D2
0x180047448  mov     rax, [rbx+460h]
0x18004744f  mov     r8, [rbx+8]
0x180047453  mov     edx, [rax+14h]
0x180047456  nop
0x180047457  shr     edx, 0Ch
0x18004745a  test    dl, 1
0x18004745d  jz      short loc_18004746D
0x18004745f  mov     rax, [rbx+460h]
0x180047466  cmp     qword ptr [rax+8], 0
0x18004746b  jz      short loc_180047481
0x18004746d  mov     rdx, [rbx+460h]
0x180047474  mov     ecx, r9d
0x180047477  call    _fputc_nolock_internal
0x18004747c  cmp     eax, 0FFFFFFFFh
0x18004747f  jz      short loc_180047486
0x180047481  inc     dword ptr [rbx+20h]
0x180047484  jmp     short loc_18004748A
0x180047486  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18004748a  mov     rax, [rbx+10h]
0x18004748e  mov     r8b, [rax]
0x180047491  inc     rax
0x180047494  mov     [rbx+10h], rax
0x180047498  mov     [rbx+39h], r8b
0x18004749c  test    r8b, r8b
0x18004749f  jnz     short loc_1800474D2
0x1800474a1  mov     rax, [rbx+8]
0x1800474a5  xor     r9d, r9d; LineNo
0x1800474a8  xor     r8d, r8d; FileName
0x1800474ab  xor     edx, edx; FunctionName
0x1800474ad  xor     ecx, ecx; Expression
0x1800474af  mov     byte ptr [rax+30h], 1
0x1800474b3  mov     dword ptr [rax+2Ch], 16h
0x1800474ba  mov     rax, [rbx+8]
0x1800474be  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x1800474c3  and     [rsp+38h+var_18], 0
0x1800474c9  call    _invalid_parameter_internal
0x1800474ce  xor     al, al
0x1800474d0  jmp     short loc_18004751A
0x1800474d2  mov     rax, [rbx+460h]
0x1800474d9  mov     rdx, [rbx+8]
0x1800474dd  mov     ecx, [rax+14h]
0x1800474e0  nop
0x1800474e1  shr     ecx, 0Ch
0x1800474e4  test    cl, 1
0x1800474e7  jz      short loc_1800474F7
0x1800474e9  mov     rax, [rbx+460h]
0x1800474f0  cmp     qword ptr [rax+8], 0
0x1800474f5  jz      short loc_18004750F
0x1800474f7  movsx   ecx, r8b
0x1800474fb  mov     r8, rdx
0x1800474fe  mov     rdx, [rbx+460h]
0x180047505  call    _fputc_nolock_internal
0x18004750a  cmp     eax, 0FFFFFFFFh
0x18004750d  jz      short loc_180047514
0x18004750f  inc     dword ptr [rbx+20h]
0x180047512  jmp     short loc_180047518
0x180047514  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180047518  mov     al, 1
0x18004751a  mov     rbx, [rsp+38h+arg_0]
0x18004751f  add     rsp, 30h
0x180047523  pop     rdi
0x180047524  retn
```
