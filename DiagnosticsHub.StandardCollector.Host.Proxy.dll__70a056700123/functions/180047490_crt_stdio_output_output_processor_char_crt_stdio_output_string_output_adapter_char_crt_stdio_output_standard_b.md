# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x180047490`
- end: `0x1800475b1`
- name: `?state_case_normal_common@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800073e8`
- `0x1800149cc`
- `0x180047490`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::state_case_normal_common(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // r8
  __int64 v4; // rcx
  _BYTE *v5; // rax
  __int64 v6; // rax
  __int64 v8; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  *(_BYTE *)(a1 + 76) = 0;
  if ( !*(_BYTE *)(v1 + 40) )
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)v1);
  v3 = *(char *)(a1 + 57);
  if ( (int)v3 < -1 || *(__int16 *)(**(_QWORD **)(v1 + 24) + 2 * v3) >= 0 )
    goto LABEL_12;
  v4 = *(_QWORD *)(a1 + 1120);
  if ( *(_QWORD *)(v4 + 16) == *(_QWORD *)(v4 + 8) )
  {
    if ( *(_BYTE *)(v4 + 24) )
      ++*(_DWORD *)(a1 + 32);
    else
      *(_DWORD *)(a1 + 32) = -1;
  }
  else
  {
    ++*(_DWORD *)(a1 + 32);
    ++*(_QWORD *)(v4 + 16);
    *(_BYTE *)(**(_QWORD **)(a1 + 1120))++ = v3;
  }
  v5 = *(_BYTE **)(a1 + 16);
  LOBYTE(v3) = *v5;
  *(_QWORD *)(a1 + 16) = v5 + 1;
  *(_BYTE *)(a1 + 57) = v3;
  if ( (_BYTE)v3 )
  {
LABEL_12:
    v8 = *(_QWORD *)(a1 + 1120);
    if ( *(_QWORD *)(v8 + 16) == *(_QWORD *)(v8 + 8) )
    {
      if ( *(_BYTE *)(v8 + 24) )
        ++*(_DWORD *)(a1 + 32);
      else
        *(_DWORD *)(a1 + 32) = -1;
    }
    else
    {
      ++*(_DWORD *)(a1 + 32);
      ++*(_QWORD *)(v8 + 16);
      *(_BYTE *)(**(_QWORD **)(a1 + 1120))++ = v3;
    }
    return 1;
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 8);
    *(_BYTE *)(v6 + 48) = 1;
    *(_DWORD *)(v6 + 44) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, *(__crt_cached_ptd_host **)(a1 + 8));
    return 0;
  }
}

```

## disassembly

```asm
0x180047490  mov     [rsp+arg_0], rbx
0x180047495  push    rdi
0x180047496  sub     rsp, 30h
0x18004749a  mov     rdi, [rcx+8]
0x18004749e  mov     rbx, rcx
0x1800474a1  mov     byte ptr [rcx+4Ch], 0
0x1800474a5  cmp     byte ptr [rdi+28h], 0
0x1800474a9  jnz     short loc_1800474B3
0x1800474ab  mov     rcx, rdi; this
0x1800474ae  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800474b3  movsx   r8, byte ptr [rbx+39h]
0x1800474b8  or      r9d, 0FFFFFFFFh
0x1800474bc  cmp     r8d, r9d
0x1800474bf  jl      loc_180047564
0x1800474c5  mov     rax, [rdi+18h]
0x1800474c9  mov     rcx, [rax]
0x1800474cc  mov     eax, 8000h
0x1800474d1  test    [rcx+r8*2], ax
0x1800474d6  jz      loc_180047564
0x1800474dc  mov     rcx, [rbx+460h]
0x1800474e3  mov     rax, [rcx+8]
0x1800474e7  cmp     [rcx+10h], rax
0x1800474eb  jnz     short loc_1800474FE
0x1800474ed  cmp     byte ptr [rcx+18h], 0
0x1800474f1  jz      short loc_1800474F8
0x1800474f3  inc     dword ptr [rbx+20h]
0x1800474f6  jmp     short loc_18004751C
0x1800474f8  mov     [rbx+20h], r9d
0x1800474fc  jmp     short loc_18004751C
0x1800474fe  inc     dword ptr [rbx+20h]
0x180047501  inc     qword ptr [rcx+10h]
0x180047505  mov     rax, [rbx+460h]
0x18004750c  mov     rcx, [rax]
0x18004750f  mov     [rcx], r8b
0x180047512  mov     rax, [rbx+460h]
0x180047519  inc     qword ptr [rax]
0x18004751c  mov     rax, [rbx+10h]
0x180047520  mov     r8b, [rax]
0x180047523  inc     rax
0x180047526  mov     [rbx+10h], rax
0x18004752a  mov     [rbx+39h], r8b
0x18004752e  test    r8b, r8b
0x180047531  jnz     short loc_180047564
0x180047533  mov     rax, [rbx+8]
0x180047537  xor     r9d, r9d; LineNo
0x18004753a  xor     r8d, r8d; FileName
0x18004753d  xor     edx, edx; FunctionName
0x18004753f  xor     ecx, ecx; Expression
0x180047541  mov     byte ptr [rax+30h], 1
0x180047545  mov     dword ptr [rax+2Ch], 16h
0x18004754c  mov     rax, [rbx+8]
0x180047550  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x180047555  and     [rsp+38h+var_18], 0
0x18004755b  call    _invalid_parameter_internal
0x180047560  xor     al, al
0x180047562  jmp     short loc_1800475A6
0x180047564  mov     rcx, [rbx+460h]
0x18004756b  mov     rax, [rcx+8]
0x18004756f  cmp     [rcx+10h], rax
0x180047573  jnz     short loc_180047586
0x180047575  cmp     byte ptr [rcx+18h], 0
0x180047579  jz      short loc_180047580
0x18004757b  inc     dword ptr [rbx+20h]
0x18004757e  jmp     short loc_1800475A4
0x180047580  mov     [rbx+20h], r9d
0x180047584  jmp     short loc_1800475A4
0x180047586  inc     dword ptr [rbx+20h]
0x180047589  inc     qword ptr [rcx+10h]
0x18004758d  mov     rcx, [rbx+460h]
0x180047594  mov     rdx, [rcx]
0x180047597  mov     [rdx], r8b
0x18004759a  mov     rcx, [rbx+460h]
0x1800475a1  inc     qword ptr [rcx]
0x1800475a4  mov     al, 1
0x1800475a6  mov     rbx, [rsp+38h+arg_0]
0x1800475ab  add     rsp, 30h
0x1800475af  pop     rdi
0x1800475b0  retn
```
