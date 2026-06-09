# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x180047770`
- end: `0x180047891`
- name: `?state_case_normal_common@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007b48`
- `0x18001512c`
- `0x180047770`

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
0x180047770  mov     [rsp+arg_0], rbx
0x180047775  push    rdi
0x180047776  sub     rsp, 30h
0x18004777a  mov     rdi, [rcx+8]
0x18004777e  mov     rbx, rcx
0x180047781  mov     byte ptr [rcx+4Ch], 0
0x180047785  cmp     byte ptr [rdi+28h], 0
0x180047789  jnz     short loc_180047793
0x18004778b  mov     rcx, rdi; this
0x18004778e  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180047793  movsx   r8, byte ptr [rbx+39h]
0x180047798  or      r9d, 0FFFFFFFFh
0x18004779c  cmp     r8d, r9d
0x18004779f  jl      loc_180047844
0x1800477a5  mov     rax, [rdi+18h]
0x1800477a9  mov     rcx, [rax]
0x1800477ac  mov     eax, 8000h
0x1800477b1  test    [rcx+r8*2], ax
0x1800477b6  jz      loc_180047844
0x1800477bc  mov     rcx, [rbx+460h]
0x1800477c3  mov     rax, [rcx+8]
0x1800477c7  cmp     [rcx+10h], rax
0x1800477cb  jnz     short loc_1800477DE
0x1800477cd  cmp     byte ptr [rcx+18h], 0
0x1800477d1  jz      short loc_1800477D8
0x1800477d3  inc     dword ptr [rbx+20h]
0x1800477d6  jmp     short loc_1800477FC
0x1800477d8  mov     [rbx+20h], r9d
0x1800477dc  jmp     short loc_1800477FC
0x1800477de  inc     dword ptr [rbx+20h]
0x1800477e1  inc     qword ptr [rcx+10h]
0x1800477e5  mov     rax, [rbx+460h]
0x1800477ec  mov     rcx, [rax]
0x1800477ef  mov     [rcx], r8b
0x1800477f2  mov     rax, [rbx+460h]
0x1800477f9  inc     qword ptr [rax]
0x1800477fc  mov     rax, [rbx+10h]
0x180047800  mov     r8b, [rax]
0x180047803  inc     rax
0x180047806  mov     [rbx+10h], rax
0x18004780a  mov     [rbx+39h], r8b
0x18004780e  test    r8b, r8b
0x180047811  jnz     short loc_180047844
0x180047813  mov     rax, [rbx+8]
0x180047817  xor     r9d, r9d; LineNo
0x18004781a  xor     r8d, r8d; FileName
0x18004781d  xor     edx, edx; FunctionName
0x18004781f  xor     ecx, ecx; Expression
0x180047821  mov     byte ptr [rax+30h], 1
0x180047825  mov     dword ptr [rax+2Ch], 16h
0x18004782c  mov     rax, [rbx+8]
0x180047830  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x180047835  and     [rsp+38h+var_18], 0
0x18004783b  call    _invalid_parameter_internal
0x180047840  xor     al, al
0x180047842  jmp     short loc_180047886
0x180047844  mov     rcx, [rbx+460h]
0x18004784b  mov     rax, [rcx+8]
0x18004784f  cmp     [rcx+10h], rax
0x180047853  jnz     short loc_180047866
0x180047855  cmp     byte ptr [rcx+18h], 0
0x180047859  jz      short loc_180047860
0x18004785b  inc     dword ptr [rbx+20h]
0x18004785e  jmp     short loc_180047884
0x180047860  mov     [rbx+20h], r9d
0x180047864  jmp     short loc_180047884
0x180047866  inc     dword ptr [rbx+20h]
0x180047869  inc     qword ptr [rcx+10h]
0x18004786d  mov     rcx, [rbx+460h]
0x180047874  mov     rdx, [rcx]
0x180047877  mov     [rdx], r8b
0x18004787a  mov     rcx, [rbx+460h]
0x180047881  inc     qword ptr [rcx]
0x180047884  mov     al, 1
0x180047886  mov     rbx, [rsp+38h+arg_0]
0x18004788b  add     rsp, 30h
0x18004788f  pop     rdi
0x180047890  retn
```
