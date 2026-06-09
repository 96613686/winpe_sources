# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x18004736c`
- end: `0x18004748d`
- name: `?state_case_normal_common@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800073e8`
- `0x1800149cc`
- `0x18004736c`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>>::state_case_normal_common(
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
0x18004736c  mov     [rsp+arg_0], rbx
0x180047371  push    rdi
0x180047372  sub     rsp, 30h
0x180047376  mov     rdi, [rcx+8]
0x18004737a  mov     rbx, rcx
0x18004737d  mov     byte ptr [rcx+4Ch], 0
0x180047381  cmp     byte ptr [rdi+28h], 0
0x180047385  jnz     short loc_18004738F
0x180047387  mov     rcx, rdi; this
0x18004738a  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18004738f  movsx   r8, byte ptr [rbx+39h]
0x180047394  or      r9d, 0FFFFFFFFh
0x180047398  cmp     r8d, r9d
0x18004739b  jl      loc_180047440
0x1800473a1  mov     rax, [rdi+18h]
0x1800473a5  mov     rcx, [rax]
0x1800473a8  mov     eax, 8000h
0x1800473ad  test    [rcx+r8*2], ax
0x1800473b2  jz      loc_180047440
0x1800473b8  mov     rcx, [rbx+460h]
0x1800473bf  mov     rax, [rcx+8]
0x1800473c3  cmp     [rcx+10h], rax
0x1800473c7  jnz     short loc_1800473DA
0x1800473c9  cmp     byte ptr [rcx+18h], 0
0x1800473cd  jz      short loc_1800473D4
0x1800473cf  inc     dword ptr [rbx+20h]
0x1800473d2  jmp     short loc_1800473F8
0x1800473d4  mov     [rbx+20h], r9d
0x1800473d8  jmp     short loc_1800473F8
0x1800473da  inc     dword ptr [rbx+20h]
0x1800473dd  inc     qword ptr [rcx+10h]
0x1800473e1  mov     rax, [rbx+460h]
0x1800473e8  mov     rcx, [rax]
0x1800473eb  mov     [rcx], r8b
0x1800473ee  mov     rax, [rbx+460h]
0x1800473f5  inc     qword ptr [rax]
0x1800473f8  mov     rax, [rbx+10h]
0x1800473fc  mov     r8b, [rax]
0x1800473ff  inc     rax
0x180047402  mov     [rbx+10h], rax
0x180047406  mov     [rbx+39h], r8b
0x18004740a  test    r8b, r8b
0x18004740d  jnz     short loc_180047440
0x18004740f  mov     rax, [rbx+8]
0x180047413  xor     r9d, r9d; LineNo
0x180047416  xor     r8d, r8d; FileName
0x180047419  xor     edx, edx; FunctionName
0x18004741b  xor     ecx, ecx; Expression
0x18004741d  mov     byte ptr [rax+30h], 1
0x180047421  mov     dword ptr [rax+2Ch], 16h
0x180047428  mov     rax, [rbx+8]
0x18004742c  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x180047431  and     [rsp+38h+var_18], 0
0x180047437  call    _invalid_parameter_internal
0x18004743c  xor     al, al
0x18004743e  jmp     short loc_180047482
0x180047440  mov     rcx, [rbx+460h]
0x180047447  mov     rax, [rcx+8]
0x18004744b  cmp     [rcx+10h], rax
0x18004744f  jnz     short loc_180047462
0x180047451  cmp     byte ptr [rcx+18h], 0
0x180047455  jz      short loc_18004745C
0x180047457  inc     dword ptr [rbx+20h]
0x18004745a  jmp     short loc_180047480
0x18004745c  mov     [rbx+20h], r9d
0x180047460  jmp     short loc_180047480
0x180047462  inc     dword ptr [rbx+20h]
0x180047465  inc     qword ptr [rcx+10h]
0x180047469  mov     rcx, [rbx+460h]
0x180047470  mov     rdx, [rcx]
0x180047473  mov     [rdx], r8b
0x180047476  mov     rcx, [rbx+460h]
0x18004747d  inc     qword ptr [rcx]
0x180047480  mov     al, 1
0x180047482  mov     rbx, [rsp+38h+arg_0]
0x180047487  add     rsp, 30h
0x18004748b  pop     rdi
0x18004748c  retn
```
