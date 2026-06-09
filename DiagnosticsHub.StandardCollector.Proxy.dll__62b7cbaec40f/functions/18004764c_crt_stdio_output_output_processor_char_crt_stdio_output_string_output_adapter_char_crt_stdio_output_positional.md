# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x18004764c`
- end: `0x18004776d`
- name: `?state_case_normal_common@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007b48`
- `0x18001512c`
- `0x18004764c`

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
0x18004764c  mov     [rsp+arg_0], rbx
0x180047651  push    rdi
0x180047652  sub     rsp, 30h
0x180047656  mov     rdi, [rcx+8]
0x18004765a  mov     rbx, rcx
0x18004765d  mov     byte ptr [rcx+4Ch], 0
0x180047661  cmp     byte ptr [rdi+28h], 0
0x180047665  jnz     short loc_18004766F
0x180047667  mov     rcx, rdi; this
0x18004766a  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18004766f  movsx   r8, byte ptr [rbx+39h]
0x180047674  or      r9d, 0FFFFFFFFh
0x180047678  cmp     r8d, r9d
0x18004767b  jl      loc_180047720
0x180047681  mov     rax, [rdi+18h]
0x180047685  mov     rcx, [rax]
0x180047688  mov     eax, 8000h
0x18004768d  test    [rcx+r8*2], ax
0x180047692  jz      loc_180047720
0x180047698  mov     rcx, [rbx+460h]
0x18004769f  mov     rax, [rcx+8]
0x1800476a3  cmp     [rcx+10h], rax
0x1800476a7  jnz     short loc_1800476BA
0x1800476a9  cmp     byte ptr [rcx+18h], 0
0x1800476ad  jz      short loc_1800476B4
0x1800476af  inc     dword ptr [rbx+20h]
0x1800476b2  jmp     short loc_1800476D8
0x1800476b4  mov     [rbx+20h], r9d
0x1800476b8  jmp     short loc_1800476D8
0x1800476ba  inc     dword ptr [rbx+20h]
0x1800476bd  inc     qword ptr [rcx+10h]
0x1800476c1  mov     rax, [rbx+460h]
0x1800476c8  mov     rcx, [rax]
0x1800476cb  mov     [rcx], r8b
0x1800476ce  mov     rax, [rbx+460h]
0x1800476d5  inc     qword ptr [rax]
0x1800476d8  mov     rax, [rbx+10h]
0x1800476dc  mov     r8b, [rax]
0x1800476df  inc     rax
0x1800476e2  mov     [rbx+10h], rax
0x1800476e6  mov     [rbx+39h], r8b
0x1800476ea  test    r8b, r8b
0x1800476ed  jnz     short loc_180047720
0x1800476ef  mov     rax, [rbx+8]
0x1800476f3  xor     r9d, r9d; LineNo
0x1800476f6  xor     r8d, r8d; FileName
0x1800476f9  xor     edx, edx; FunctionName
0x1800476fb  xor     ecx, ecx; Expression
0x1800476fd  mov     byte ptr [rax+30h], 1
0x180047701  mov     dword ptr [rax+2Ch], 16h
0x180047708  mov     rax, [rbx+8]
0x18004770c  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x180047711  and     [rsp+38h+var_18], 0
0x180047717  call    _invalid_parameter_internal
0x18004771c  xor     al, al
0x18004771e  jmp     short loc_180047762
0x180047720  mov     rcx, [rbx+460h]
0x180047727  mov     rax, [rcx+8]
0x18004772b  cmp     [rcx+10h], rax
0x18004772f  jnz     short loc_180047742
0x180047731  cmp     byte ptr [rcx+18h], 0
0x180047735  jz      short loc_18004773C
0x180047737  inc     dword ptr [rbx+20h]
0x18004773a  jmp     short loc_180047760
0x18004773c  mov     [rbx+20h], r9d
0x180047740  jmp     short loc_180047760
0x180047742  inc     dword ptr [rbx+20h]
0x180047745  inc     qword ptr [rcx+10h]
0x180047749  mov     rcx, [rbx+460h]
0x180047750  mov     rdx, [rcx]
0x180047753  mov     [rdx], r8b
0x180047756  mov     rcx, [rbx+460h]
0x18004775d  inc     qword ptr [rcx]
0x180047760  mov     al, 1
0x180047762  mov     rbx, [rsp+38h+arg_0]
0x180047767  add     rsp, 30h
0x18004776b  pop     rdi
0x18004776c  retn
```
