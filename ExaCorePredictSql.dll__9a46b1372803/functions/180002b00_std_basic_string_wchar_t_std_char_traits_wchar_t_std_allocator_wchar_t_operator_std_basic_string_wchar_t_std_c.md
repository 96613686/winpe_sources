# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&)

- ea: `0x180002b00`
- end: `0x180002bd0`
- name: `??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002030`

## callees

- `0x180001be0`
- `0x180002b00`
- `0x180003210`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b42`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b59`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b69`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b79`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b86`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b42`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b59`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b69`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b79`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180002b86`

## pseudocode

```c
char **__fastcall std::wstring::operator=(char **a1, char **a2)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rax
  char *v6; // rcx
  char *v7; // rax
  unsigned __int64 v8; // rcx
  char *v9; // rax

  if ( a1 != a2 )
  {
    v4 = (unsigned __int64)a1[3];
    if ( v4 >= 8 )
    {
      v5 = v4 + 1;
      v6 = *a1;
      if ( v5 > 0x7FFFFFFFFFFFFFFFLL )
        _invalid_parameter_noinfo_noreturn();
      if ( 2 * v5 >= 0x1000 )
      {
        if ( ((unsigned __int8)v6 & 0x1F) != 0 )
          _invalid_parameter_noinfo_noreturn();
        v7 = (char *)*((_QWORD *)v6 - 1);
        if ( v7 >= v6 )
          _invalid_parameter_noinfo_noreturn();
        v8 = v6 - v7;
        if ( v8 < 8 )
          _invalid_parameter_noinfo_noreturn();
        if ( v8 > 0x27 )
          _invalid_parameter_noinfo_noreturn();
        v6 = v7;
      }
      operator delete(v6);
    }
    a1[3] = (char *)7;
    a1[2] = 0;
    if ( (unsigned __int64)a1[3] < 8 )
      v9 = (char *)a1;
    else
      v9 = *a1;
    *(_WORD *)v9 = 0;
    std::wstring::_Assign_rv(a1, a2);
  }
  return a1;
}

```

## disassembly

```asm
0x180002b00  push    rdi
0x180002b02  sub     rsp, 30h
0x180002b06  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002b0f  mov     [rsp+38h+arg_0], rbx
0x180002b14  mov     rdi, rdx
0x180002b17  mov     rbx, rcx
0x180002b1a  cmp     rcx, rdx
0x180002b1d  jz      loc_180002BC2
0x180002b23  mov     rax, [rcx+18h]
0x180002b27  cmp     rax, 8
0x180002b2b  jb      short loc_180002B96
0x180002b2d  inc     rax
0x180002b30  mov     rcx, [rcx]
0x180002b33  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180002b3d  cmp     rax, rdx
0x180002b40  jbe     short loc_180002B49
0x180002b42  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180002b49  add     rax, rax
0x180002b4c  cmp     rax, 1000h
0x180002b52  jb      short loc_180002B90
0x180002b54  test    cl, 1Fh
0x180002b57  jz      short loc_180002B60
0x180002b59  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180002b60  mov     rax, [rcx-8]
0x180002b64  cmp     rax, rcx
0x180002b67  jb      short loc_180002B70
0x180002b69  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180002b70  sub     rcx, rax
0x180002b73  cmp     rcx, 8
0x180002b77  jnb     short loc_180002B80
0x180002b79  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180002b80  cmp     rcx, 27h ; '''
0x180002b84  jbe     short loc_180002B8D
0x180002b86  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180002b8d  mov     rcx, rax; void *
0x180002b90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002b95  nop
0x180002b96  mov     qword ptr [rbx+18h], 7
0x180002b9e  xor     ecx, ecx
0x180002ba0  mov     [rbx+10h], rcx
0x180002ba4  cmp     qword ptr [rbx+18h], 8
0x180002ba9  jb      short loc_180002BB0
0x180002bab  mov     rax, [rbx]
0x180002bae  jmp     short loc_180002BB3
0x180002bb0  mov     rax, rbx
0x180002bb3  mov     [rax], cx
0x180002bb6  mov     rdx, rdi
0x180002bb9  mov     rcx, rbx
0x180002bbc  call    ?_Assign_rv@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX$$QEAV12@@Z; std::wstring::_Assign_rv(std::wstring &&)
0x180002bc1  nop
0x180002bc2  mov     rax, rbx
0x180002bc5  mov     rbx, [rsp+38h+arg_0]
0x180002bca  add     rsp, 30h
0x180002bce  pop     rdi
0x180002bcf  retn
```
