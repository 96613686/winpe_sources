# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::stream_output_adapter<char>>>::state_case_normal_common(void)

- ea: `0x180046ec4`
- end: `0x180046fed`
- name: `?state_case_normal_common@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_NXZ`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800073e8`
- `0x1800149cc`
- `0x180046ec4`
- `0x180058a44`

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
0x180046ec4  mov     [rsp+arg_0], rbx
0x180046ec9  push    rdi
0x180046eca  sub     rsp, 30h
0x180046ece  mov     rdi, [rcx+8]
0x180046ed2  mov     rbx, rcx
0x180046ed5  mov     byte ptr [rcx+4Ch], 0
0x180046ed9  cmp     byte ptr [rdi+28h], 0
0x180046edd  jnz     short loc_180046EE7
0x180046edf  mov     rcx, rdi; this
0x180046ee2  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180046ee7  movsx   r8, byte ptr [rbx+39h]
0x180046eec  mov     r9, r8
0x180046eef  cmp     r8d, 0FFFFFFFFh
0x180046ef3  jl      loc_180046F9A
0x180046ef9  mov     rax, [rdi+18h]
0x180046efd  mov     rcx, [rax]
0x180046f00  mov     eax, 8000h
0x180046f05  test    [rcx+r8*2], ax
0x180046f0a  jz      loc_180046F9A
0x180046f10  mov     rax, [rbx+460h]
0x180046f17  mov     r8, [rbx+8]
0x180046f1b  mov     edx, [rax+14h]
0x180046f1e  nop
0x180046f1f  shr     edx, 0Ch
0x180046f22  test    dl, 1
0x180046f25  jz      short loc_180046F35
0x180046f27  mov     rax, [rbx+460h]
0x180046f2e  cmp     qword ptr [rax+8], 0
0x180046f33  jz      short loc_180046F49
0x180046f35  mov     rdx, [rbx+460h]
0x180046f3c  mov     ecx, r9d
0x180046f3f  call    _fputc_nolock_internal
0x180046f44  cmp     eax, 0FFFFFFFFh
0x180046f47  jz      short loc_180046F4E
0x180046f49  inc     dword ptr [rbx+20h]
0x180046f4c  jmp     short loc_180046F52
0x180046f4e  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180046f52  mov     rax, [rbx+10h]
0x180046f56  mov     r8b, [rax]
0x180046f59  inc     rax
0x180046f5c  mov     [rbx+10h], rax
0x180046f60  mov     [rbx+39h], r8b
0x180046f64  test    r8b, r8b
0x180046f67  jnz     short loc_180046F9A
0x180046f69  mov     rax, [rbx+8]
0x180046f6d  xor     r9d, r9d; LineNo
0x180046f70  xor     r8d, r8d; FileName
0x180046f73  xor     edx, edx; FunctionName
0x180046f75  xor     ecx, ecx; Expression
0x180046f77  mov     byte ptr [rax+30h], 1
0x180046f7b  mov     dword ptr [rax+2Ch], 16h
0x180046f82  mov     rax, [rbx+8]
0x180046f86  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x180046f8b  and     [rsp+38h+var_18], 0
0x180046f91  call    _invalid_parameter_internal
0x180046f96  xor     al, al
0x180046f98  jmp     short loc_180046FE2
0x180046f9a  mov     rax, [rbx+460h]
0x180046fa1  mov     rdx, [rbx+8]
0x180046fa5  mov     ecx, [rax+14h]
0x180046fa8  nop
0x180046fa9  shr     ecx, 0Ch
0x180046fac  test    cl, 1
0x180046faf  jz      short loc_180046FBF
0x180046fb1  mov     rax, [rbx+460h]
0x180046fb8  cmp     qword ptr [rax+8], 0
0x180046fbd  jz      short loc_180046FD7
0x180046fbf  movsx   ecx, r8b
0x180046fc3  mov     r8, rdx
0x180046fc6  mov     rdx, [rbx+460h]
0x180046fcd  call    _fputc_nolock_internal
0x180046fd2  cmp     eax, 0FFFFFFFFh
0x180046fd5  jz      short loc_180046FDC
0x180046fd7  inc     dword ptr [rbx+20h]
0x180046fda  jmp     short loc_180046FE0
0x180046fdc  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180046fe0  mov     al, 1
0x180046fe2  mov     rbx, [rsp+38h+arg_0]
0x180046fe7  add     rsp, 30h
0x180046feb  pop     rdi
0x180046fec  retn
```
