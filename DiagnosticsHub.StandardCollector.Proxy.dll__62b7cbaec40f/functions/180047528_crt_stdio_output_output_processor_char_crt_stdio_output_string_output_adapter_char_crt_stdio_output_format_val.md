# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::string_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x180047528`
- end: `0x180047649`
- name: `?state_case_normal_common@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007b48`
- `0x18001512c`
- `0x180047528`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::string_output_adapter<char>>>::state_case_normal_common(
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
0x180047528  mov     [rsp+arg_0], rbx
0x18004752d  push    rdi
0x18004752e  sub     rsp, 30h
0x180047532  mov     rdi, [rcx+8]
0x180047536  mov     rbx, rcx
0x180047539  mov     byte ptr [rcx+4Ch], 0
0x18004753d  cmp     byte ptr [rdi+28h], 0
0x180047541  jnz     short loc_18004754B
0x180047543  mov     rcx, rdi; this
0x180047546  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18004754b  movsx   r8, byte ptr [rbx+39h]
0x180047550  or      r9d, 0FFFFFFFFh
0x180047554  cmp     r8d, r9d
0x180047557  jl      loc_1800475FC
0x18004755d  mov     rax, [rdi+18h]
0x180047561  mov     rcx, [rax]
0x180047564  mov     eax, 8000h
0x180047569  test    [rcx+r8*2], ax
0x18004756e  jz      loc_1800475FC
0x180047574  mov     rcx, [rbx+460h]
0x18004757b  mov     rax, [rcx+8]
0x18004757f  cmp     [rcx+10h], rax
0x180047583  jnz     short loc_180047596
0x180047585  cmp     byte ptr [rcx+18h], 0
0x180047589  jz      short loc_180047590
0x18004758b  inc     dword ptr [rbx+20h]
0x18004758e  jmp     short loc_1800475B4
0x180047590  mov     [rbx+20h], r9d
0x180047594  jmp     short loc_1800475B4
0x180047596  inc     dword ptr [rbx+20h]
0x180047599  inc     qword ptr [rcx+10h]
0x18004759d  mov     rax, [rbx+460h]
0x1800475a4  mov     rcx, [rax]
0x1800475a7  mov     [rcx], r8b
0x1800475aa  mov     rax, [rbx+460h]
0x1800475b1  inc     qword ptr [rax]
0x1800475b4  mov     rax, [rbx+10h]
0x1800475b8  mov     r8b, [rax]
0x1800475bb  inc     rax
0x1800475be  mov     [rbx+10h], rax
0x1800475c2  mov     [rbx+39h], r8b
0x1800475c6  test    r8b, r8b
0x1800475c9  jnz     short loc_1800475FC
0x1800475cb  mov     rax, [rbx+8]
0x1800475cf  xor     r9d, r9d; LineNo
0x1800475d2  xor     r8d, r8d; FileName
0x1800475d5  xor     edx, edx; FunctionName
0x1800475d7  xor     ecx, ecx; Expression
0x1800475d9  mov     byte ptr [rax+30h], 1
0x1800475dd  mov     dword ptr [rax+2Ch], 16h
0x1800475e4  mov     rax, [rbx+8]
0x1800475e8  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x1800475ed  and     [rsp+38h+var_18], 0
0x1800475f3  call    _invalid_parameter_internal
0x1800475f8  xor     al, al
0x1800475fa  jmp     short loc_18004763E
0x1800475fc  mov     rcx, [rbx+460h]
0x180047603  mov     rax, [rcx+8]
0x180047607  cmp     [rcx+10h], rax
0x18004760b  jnz     short loc_18004761E
0x18004760d  cmp     byte ptr [rcx+18h], 0
0x180047611  jz      short loc_180047618
0x180047613  inc     dword ptr [rbx+20h]
0x180047616  jmp     short loc_18004763C
0x180047618  mov     [rbx+20h], r9d
0x18004761c  jmp     short loc_18004763C
0x18004761e  inc     dword ptr [rbx+20h]
0x180047621  inc     qword ptr [rcx+10h]
0x180047625  mov     rcx, [rbx+460h]
0x18004762c  mov     rdx, [rcx]
0x18004762f  mov     [rdx], r8b
0x180047632  mov     rcx, [rbx+460h]
0x180047639  inc     qword ptr [rcx]
0x18004763c  mov     al, 1
0x18004763e  mov     rbx, [rsp+38h+arg_0]
0x180047643  add     rsp, 30h
0x180047647  pop     rdi
0x180047648  retn
```
