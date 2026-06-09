# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::string_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x180047248`
- end: `0x180047369`
- name: `?state_case_normal_common@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800073e8`
- `0x1800149cc`
- `0x180047248`

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
0x180047248  mov     [rsp+arg_0], rbx
0x18004724d  push    rdi
0x18004724e  sub     rsp, 30h
0x180047252  mov     rdi, [rcx+8]
0x180047256  mov     rbx, rcx
0x180047259  mov     byte ptr [rcx+4Ch], 0
0x18004725d  cmp     byte ptr [rdi+28h], 0
0x180047261  jnz     short loc_18004726B
0x180047263  mov     rcx, rdi; this
0x180047266  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18004726b  movsx   r8, byte ptr [rbx+39h]
0x180047270  or      r9d, 0FFFFFFFFh
0x180047274  cmp     r8d, r9d
0x180047277  jl      loc_18004731C
0x18004727d  mov     rax, [rdi+18h]
0x180047281  mov     rcx, [rax]
0x180047284  mov     eax, 8000h
0x180047289  test    [rcx+r8*2], ax
0x18004728e  jz      loc_18004731C
0x180047294  mov     rcx, [rbx+460h]
0x18004729b  mov     rax, [rcx+8]
0x18004729f  cmp     [rcx+10h], rax
0x1800472a3  jnz     short loc_1800472B6
0x1800472a5  cmp     byte ptr [rcx+18h], 0
0x1800472a9  jz      short loc_1800472B0
0x1800472ab  inc     dword ptr [rbx+20h]
0x1800472ae  jmp     short loc_1800472D4
0x1800472b0  mov     [rbx+20h], r9d
0x1800472b4  jmp     short loc_1800472D4
0x1800472b6  inc     dword ptr [rbx+20h]
0x1800472b9  inc     qword ptr [rcx+10h]
0x1800472bd  mov     rax, [rbx+460h]
0x1800472c4  mov     rcx, [rax]
0x1800472c7  mov     [rcx], r8b
0x1800472ca  mov     rax, [rbx+460h]
0x1800472d1  inc     qword ptr [rax]
0x1800472d4  mov     rax, [rbx+10h]
0x1800472d8  mov     r8b, [rax]
0x1800472db  inc     rax
0x1800472de  mov     [rbx+10h], rax
0x1800472e2  mov     [rbx+39h], r8b
0x1800472e6  test    r8b, r8b
0x1800472e9  jnz     short loc_18004731C
0x1800472eb  mov     rax, [rbx+8]
0x1800472ef  xor     r9d, r9d; LineNo
0x1800472f2  xor     r8d, r8d; FileName
0x1800472f5  xor     edx, edx; FunctionName
0x1800472f7  xor     ecx, ecx; Expression
0x1800472f9  mov     byte ptr [rax+30h], 1
0x1800472fd  mov     dword ptr [rax+2Ch], 16h
0x180047304  mov     rax, [rbx+8]
0x180047308  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x18004730d  and     [rsp+38h+var_18], 0
0x180047313  call    _invalid_parameter_internal
0x180047318  xor     al, al
0x18004731a  jmp     short loc_18004735E
0x18004731c  mov     rcx, [rbx+460h]
0x180047323  mov     rax, [rcx+8]
0x180047327  cmp     [rcx+10h], rax
0x18004732b  jnz     short loc_18004733E
0x18004732d  cmp     byte ptr [rcx+18h], 0
0x180047331  jz      short loc_180047338
0x180047333  inc     dword ptr [rbx+20h]
0x180047336  jmp     short loc_18004735C
0x180047338  mov     [rbx+20h], r9d
0x18004733c  jmp     short loc_18004735C
0x18004733e  inc     dword ptr [rbx+20h]
0x180047341  inc     qword ptr [rcx+10h]
0x180047345  mov     rcx, [rbx+460h]
0x18004734c  mov     rdx, [rcx]
0x18004734f  mov     [rdx], r8b
0x180047352  mov     rcx, [rbx+460h]
0x180047359  inc     qword ptr [rcx]
0x18004735c  mov     al, 1
0x18004735e  mov     rbx, [rsp+38h+arg_0]
0x180047363  add     rsp, 30h
0x180047367  pop     rdi
0x180047368  retn
```
