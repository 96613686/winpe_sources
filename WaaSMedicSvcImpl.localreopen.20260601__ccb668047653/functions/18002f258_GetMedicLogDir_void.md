# GetMedicLogDir(void)

- ea: `0x18002f258`
- end: `0x18002f40d`
- name: `?GetMedicLogDir@@YAPEBGXZ`
- size: `437`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800384a0`

## callees

- `0x1800050a0`
- `0x180005564`
- `0x180005bbc`
- `0x180008aac`
- `0x180008b14`
- `0x180008d99`
- `0x18000ea1c`
- `0x18002f258`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18002f314`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18002f314`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002f2ee`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002f2ee`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002f346`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002f346`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x18002f32e`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x18002f32e`

## string_xrefs

- `0x18002f2e7`: `WaaSMedicLogDirectory`

## pseudocode

```c
void **GetMedicLogDir(void)
{
  unsigned __int64 v0; // rbx
  void **v1; // rsi
  void **v2; // rdi
  size_t v3; // rbx
  WCHAR Buffer[264]; // [rsp+40h] [rbp-248h] BYREF

  v0 = -1;
  if ( dword_1800A5AC0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_1800A5AC0);
    if ( dword_1800A5AC0 == -1 )
    {
      atexit(GetMedicLogDir_::_2_::_dynamic_atexit_destructor_for__s_szLogDir__);
      Init_thread_footer(&dword_1800A5AC0);
    }
  }
  v1 = &qword_1800A4C40;
  if ( !qword_1800A4C50 )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( (int)RtlGetPersistedStateLocation(L"WaaSMedicLogDirectory", 0, 0, 1, Buffer, 520, 0) < 0 )
    {
      if ( GetWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x102
        || PathCchStripPrefix(Buffer, 0x104u) < 0
        || PathCchAppend(Buffer, 0x104u, L"logs\\waasmedic") < 0 )
      {
        goto LABEL_15;
      }
      do
        ++v0;
      while ( Buffer[v0] );
    }
    else
    {
      do
        ++v0;
      while ( Buffer[v0] );
    }
    if ( v0 > qword_1800A4C58 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(&qword_1800A4C40);
    }
    else
    {
      qword_1800A4C50 = v0;
      v2 = &qword_1800A4C40;
      if ( (unsigned __int64)qword_1800A4C58 > 7 )
        v2 = (void **)qword_1800A4C40;
      v3 = 2 * v0;
      memmove_0(v2, Buffer, v3);
      *(_WORD *)((char *)v2 + v3) = 0;
    }
  }
LABEL_15:
  if ( (unsigned __int64)qword_1800A4C58 > 7 )
    return (void **)qword_1800A4C40;
  return v1;
}

```

## disassembly

```asm
0x18002f258  push    rbx
0x18002f25a  push    rbp
0x18002f25b  push    rsi
0x18002f25c  push    rdi
0x18002f25d  sub     rsp, 268h
0x18002f264  mov     rax, cs:__security_cookie
0x18002f26b  xor     rax, rsp
0x18002f26e  mov     [rsp+288h+var_38], rax
0x18002f276  mov     ecx, cs:_tls_index
0x18002f27c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f280  mov     rax, gs:58h
0x18002f289  mov     edx, 10h
0x18002f28e  mov     rax, [rax+rcx*8]
0x18002f292  mov     eax, [rdx+rax]
0x18002f295  cmp     cs:dword_1800A5AC0, eax
0x18002f29b  jg      loc_18002F3D8
0x18002f2a1  xor     ebp, ebp
0x18002f2a3  lea     rsi, qword_1800A4C40
0x18002f2aa  cmp     cs:qword_1800A4C50, rbp
0x18002f2b1  jnz     loc_18002F3A9
0x18002f2b7  mov     edi, 208h
0x18002f2bc  lea     rcx, [rsp+288h+Buffer]; void *
0x18002f2c1  mov     r8d, edi; Size
0x18002f2c4  xor     edx, edx; Val
0x18002f2c6  call    memset_0
0x18002f2cb  lea     rax, [rsp+288h+Buffer]
0x18002f2d0  mov     [rsp+288h+var_258], rbp
0x18002f2d5  mov     [rsp+288h+var_260], edi
0x18002f2d9  lea     r9d, [rbp+1]
0x18002f2dd  xor     r8d, r8d
0x18002f2e0  mov     [rsp+288h+var_268], rax
0x18002f2e5  xor     edx, edx
0x18002f2e7  lea     rcx, aWaasmediclogdi; "WaaSMedicLogDirectory"
0x18002f2ee  call    cs:__imp_RtlGetPersistedStateLocation
0x18002f2f4  test    eax, eax
0x18002f2f6  js      short loc_18002F308
0x18002f2f8  lea     rax, [rsp+288h+Buffer]
0x18002f2fd  inc     rbx
0x18002f300  cmp     [rax+rbx*2], bp
0x18002f304  jnz     short loc_18002F2FD
0x18002f306  jmp     short loc_18002F35E
0x18002f308  mov     edi, 104h
0x18002f30d  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x18002f312  mov     edx, edi; uSize
0x18002f314  call    cs:__imp_GetWindowsDirectoryW
0x18002f31a  dec     eax
0x18002f31c  cmp     eax, 102h
0x18002f321  ja      loc_18002F3A9
0x18002f327  mov     edx, edi; cchPath
0x18002f329  lea     rcx, [rsp+288h+Buffer]; pszPath
0x18002f32e  call    cs:__imp_PathCchStripPrefix
0x18002f334  test    eax, eax
0x18002f336  js      short loc_18002F3A9
0x18002f338  lea     r8, pszMore; "logs\\waasmedic"
0x18002f33f  mov     edx, edi; cchPath
0x18002f341  lea     rcx, [rsp+288h+Buffer]; pszPath
0x18002f346  call    cs:__imp_PathCchAppend
0x18002f34c  test    eax, eax
0x18002f34e  js      short loc_18002F3A9
0x18002f350  lea     rax, [rsp+288h+Buffer]
0x18002f355  inc     rbx
0x18002f358  cmp     [rax+rbx*2], bp
0x18002f35c  jnz     short loc_18002F355
0x18002f35e  mov     rax, cs:qword_1800A4C58
0x18002f365  cmp     rbx, rax
0x18002f368  ja      short loc_18002F399
0x18002f36a  cmp     rax, 7
0x18002f36e  mov     cs:qword_1800A4C50, rbx
0x18002f375  mov     rdi, rsi
0x18002f378  lea     rdx, [rsp+288h+Buffer]; Src
0x18002f37d  cmova   rdi, cs:qword_1800A4C40
0x18002f385  add     rbx, rbx
0x18002f388  mov     r8, rbx; Size
0x18002f38b  mov     rcx, rdi; void *
0x18002f38e  call    memmove_0
0x18002f393  mov     [rbx+rdi], bp
0x18002f397  jmp     short loc_18002F3A9
0x18002f399  lea     r9, [rsp+288h+Buffer]
0x18002f39e  mov     rdx, rbx
0x18002f3a1  mov     rcx, rsi
0x18002f3a4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002f3a9  cmp     cs:qword_1800A4C58, 7
0x18002f3b1  cmova   rsi, cs:qword_1800A4C40
0x18002f3b9  mov     rax, rsi
0x18002f3bc  mov     rcx, [rsp+288h+var_38]
0x18002f3c4  xor     rcx, rsp; StackCookie
0x18002f3c7  call    __security_check_cookie
0x18002f3cc  add     rsp, 268h
0x18002f3d3  pop     rdi
0x18002f3d4  pop     rsi
0x18002f3d5  pop     rbp
0x18002f3d6  pop     rbx
0x18002f3d7  retn
0x18002f3d8  lea     rcx, dword_1800A5AC0
0x18002f3df  call    _Init_thread_header
0x18002f3e4  cmp     cs:dword_1800A5AC0, ebx
0x18002f3ea  jnz     loc_18002F2A1
0x18002f3f0  lea     rcx, _GetMedicLogDir____2____dynamic_atexit_destructor_for__s_szLogDir__; void (__cdecl *)()
0x18002f3f7  call    atexit
0x18002f3fc  lea     rcx, dword_1800A5AC0
0x18002f403  call    _Init_thread_footer
0x18002f408  jmp     loc_18002F2A1
```
