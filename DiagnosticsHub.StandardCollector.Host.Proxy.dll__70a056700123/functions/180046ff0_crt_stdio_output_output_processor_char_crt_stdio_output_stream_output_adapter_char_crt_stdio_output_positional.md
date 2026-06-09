# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x180046ff0`
- end: `0x180047119`
- name: `?state_case_normal_common@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800073e8`
- `0x1800149cc`
- `0x180046ff0`
- `0x180058a44`

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
0x180046ff0  mov     [rsp+arg_0], rbx
0x180046ff5  push    rdi
0x180046ff6  sub     rsp, 30h
0x180046ffa  mov     rdi, [rcx+8]
0x180046ffe  mov     rbx, rcx
0x180047001  mov     byte ptr [rcx+4Ch], 0
0x180047005  cmp     byte ptr [rdi+28h], 0
0x180047009  jnz     short loc_180047013
0x18004700b  mov     rcx, rdi; this
0x18004700e  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180047013  movsx   r8, byte ptr [rbx+39h]
0x180047018  mov     r9, r8
0x18004701b  cmp     r8d, 0FFFFFFFFh
0x18004701f  jl      loc_1800470C6
0x180047025  mov     rax, [rdi+18h]
0x180047029  mov     rcx, [rax]
0x18004702c  mov     eax, 8000h
0x180047031  test    [rcx+r8*2], ax
0x180047036  jz      loc_1800470C6
0x18004703c  mov     rax, [rbx+460h]
0x180047043  mov     r8, [rbx+8]
0x180047047  mov     edx, [rax+14h]
0x18004704a  nop
0x18004704b  shr     edx, 0Ch
0x18004704e  test    dl, 1
0x180047051  jz      short loc_180047061
0x180047053  mov     rax, [rbx+460h]
0x18004705a  cmp     qword ptr [rax+8], 0
0x18004705f  jz      short loc_180047075
0x180047061  mov     rdx, [rbx+460h]
0x180047068  mov     ecx, r9d
0x18004706b  call    _fputc_nolock_internal
0x180047070  cmp     eax, 0FFFFFFFFh
0x180047073  jz      short loc_18004707A
0x180047075  inc     dword ptr [rbx+20h]
0x180047078  jmp     short loc_18004707E
0x18004707a  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18004707e  mov     rax, [rbx+10h]
0x180047082  mov     r8b, [rax]
0x180047085  inc     rax
0x180047088  mov     [rbx+10h], rax
0x18004708c  mov     [rbx+39h], r8b
0x180047090  test    r8b, r8b
0x180047093  jnz     short loc_1800470C6
0x180047095  mov     rax, [rbx+8]
0x180047099  xor     r9d, r9d; LineNo
0x18004709c  xor     r8d, r8d; FileName
0x18004709f  xor     edx, edx; FunctionName
0x1800470a1  xor     ecx, ecx; Expression
0x1800470a3  mov     byte ptr [rax+30h], 1
0x1800470a7  mov     dword ptr [rax+2Ch], 16h
0x1800470ae  mov     rax, [rbx+8]
0x1800470b2  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x1800470b7  and     [rsp+38h+var_18], 0
0x1800470bd  call    _invalid_parameter_internal
0x1800470c2  xor     al, al
0x1800470c4  jmp     short loc_18004710E
0x1800470c6  mov     rax, [rbx+460h]
0x1800470cd  mov     rdx, [rbx+8]
0x1800470d1  mov     ecx, [rax+14h]
0x1800470d4  nop
0x1800470d5  shr     ecx, 0Ch
0x1800470d8  test    cl, 1
0x1800470db  jz      short loc_1800470EB
0x1800470dd  mov     rax, [rbx+460h]
0x1800470e4  cmp     qword ptr [rax+8], 0
0x1800470e9  jz      short loc_180047103
0x1800470eb  movsx   ecx, r8b
0x1800470ef  mov     r8, rdx
0x1800470f2  mov     rdx, [rbx+460h]
0x1800470f9  call    _fputc_nolock_internal
0x1800470fe  cmp     eax, 0FFFFFFFFh
0x180047101  jz      short loc_180047108
0x180047103  inc     dword ptr [rbx+20h]
0x180047106  jmp     short loc_18004710C
0x180047108  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18004710c  mov     al, 1
0x18004710e  mov     rbx, [rsp+38h+arg_0]
0x180047113  add     rsp, 30h
0x180047117  pop     rdi
0x180047118  retn
```
