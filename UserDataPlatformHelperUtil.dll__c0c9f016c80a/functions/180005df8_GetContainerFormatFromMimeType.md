# GetContainerFormatFromMimeType

- ea: `0x180005df8`
- end: `0x1800061d2`
- name: `GetContainerFormatFromMimeType`
- size: `986`
- prototype: `__int64 __fastcall(unsigned int, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800068f0`

## callees

- `0x18000116c`
- `0x180001178`
- `0x180005df8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180005f91`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180005f91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005e3c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005e3c`

## pseudocode

```c
__int64 __fastcall GetContainerFormatFromMimeType(unsigned int a1, const WCHAR *a2, __int64 a3)
{
  HRESULT v5; // eax
  LPVOID v6; // rcx
  int v7; // ebx
  void (*v8)(void); // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  void *v12; // rax
  void *v13; // rbx
  int v14; // edi
  void (*v15)(void); // rax
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h] BYREF
  __int64 v20; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v21; // [rsp+70h] [rbp+20h] BYREF
  int v22; // [rsp+88h] [rbp+38h] BYREF

  v21 = a1;
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  v6 = ppv;
  v7 = v5;
  if ( v5 < 0 )
  {
    if ( ppv )
      goto LABEL_58;
    return (unsigned int)v7;
  }
  v20 = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)ppv + 184LL))(ppv, 2, 0, &v20);
  if ( v7 < 0 )
  {
    if ( v20 )
    {
      v8 = *(void (**)(void))(*(_QWORD *)v20 + 16LL);
LABEL_56:
      v8();
    }
    goto LABEL_57;
  }
  while ( 1 )
  {
    v19 = 0;
    v22 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v20 + 24LL))(v20, 1, &v19, &v22);
    v7 = v9;
    if ( v9 < 0 )
      goto LABEL_52;
    if ( v9 == 1 )
    {
      if ( v19 )
        (*(void (**)(void))(*(_QWORD *)v19 + 16LL))();
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return 2147500037LL;
    }
    v18 = 0;
    v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(
            v19,
            &GUID_e87a44c4_b76e_4c47_8b09_298eb12a2714,
            &v18);
    v11 = v18;
    v7 = v10;
    if ( v10 < 0 )
      goto LABEL_50;
    v21 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v18 + 128LL))(v18, 0, 0, &v21);
    if ( v7 < 0 )
      break;
    v12 = operator new[](saturated_mul(v21, 2u));
    v13 = v12;
    if ( !v12 )
    {
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return 2147942414LL;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *, unsigned int *))(*(_QWORD *)v18 + 128LL))(
            v18,
            v21,
            v12,
            &v21);
    if ( v14 < 0 )
    {
      operator delete(v13);
      if ( v18 )
      {
        v15 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
LABEL_32:
        v15();
      }
LABEL_33:
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v14;
    }
    if ( StrStrIW((PCWSTR)v13, a2) )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 88LL))(v18, a3);
      if ( v14 >= 0 )
      {
        operator delete(v13);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return 0;
      }
      operator delete(v13);
      if ( v18 )
      {
        v15 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
        goto LABEL_32;
      }
      goto LABEL_33;
    }
    operator delete(v13);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v11 = v18;
LABEL_50:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_52:
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 )
  {
    v8 = *(void (**)(void))(*(_QWORD *)v20 + 16LL);
    goto LABEL_56;
  }
LABEL_57:
  v6 = ppv;
  if ( ppv )
LABEL_58:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005df8  mov     [rsp-18h+arg_8], rbx
0x180005dfd  mov     [rsp-18h+arg_10], rsi
0x180005e02  mov     [rsp-18h+arg_0], ecx
0x180005e06  push    rbp
0x180005e07  push    rdi
0x180005e08  push    r14
0x180005e0a  mov     rbp, rsp
0x180005e0d  sub     rsp, 50h
0x180005e11  mov     rsi, rdx
0x180005e14  mov     [rbp+var_20], 0
0x180005e1c  xor     edx, edx; pUnkOuter
0x180005e1e  lea     rax, [rbp+var_20]
0x180005e22  mov     r14, r8
0x180005e25  mov     [rsp+50h+ppv], rax; ppv
0x180005e2a  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180005e31  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180005e38  lea     r8d, [rdx+1]; dwClsContext
0x180005e3c  call    cs:__imp_CoCreateInstance
0x180005e42  mov     rcx, [rbp+var_20]
0x180005e46  mov     ebx, eax
0x180005e48  test    eax, eax
0x180005e4a  jns     short loc_180005E61
0x180005e4c  test    rcx, rcx
0x180005e4f  jz      loc_180006179
0x180005e55  mov     rdx, [rcx]
0x180005e58  mov     rax, [rdx+10h]
0x180005e5c  jmp     loc_180006174
0x180005e61  mov     [rbp+var_8], 0
0x180005e69  lea     r9, [rbp+var_8]
0x180005e6d  mov     rax, [rcx]
0x180005e70  xor     r8d, r8d
0x180005e73  mov     rax, [rax+0B8h]
0x180005e7a  lea     edx, [r8+2]
0x180005e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e83  mov     ebx, eax
0x180005e85  test    eax, eax
0x180005e87  jns     short loc_180005EA2
0x180005e89  mov     rcx, [rbp+var_8]
0x180005e8d  test    rcx, rcx
0x180005e90  jz      loc_180006164
0x180005e96  mov     rdx, [rcx]
0x180005e99  mov     rax, [rdx+10h]
0x180005e9d  jmp     loc_18000615F
0x180005ea2  mov     rcx, [rbp+var_8]
0x180005ea6  lea     r9, [rbp+arg_18]
0x180005eaa  mov     [rbp+var_10], 0
0x180005eb2  lea     r8, [rbp+var_10]
0x180005eb6  mov     [rbp+arg_18], 0
0x180005ebd  mov     edx, 1
0x180005ec2  mov     rax, [rcx]
0x180005ec5  mov     rax, [rax+18h]
0x180005ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ece  mov     ebx, eax
0x180005ed0  test    eax, eax
0x180005ed2  js      loc_18000613A
0x180005ed8  mov     rcx, [rbp+var_10]
0x180005edc  cmp     eax, 1
0x180005edf  jz      loc_180006190
0x180005ee5  mov     [rbp+var_18], 0
0x180005eed  lea     r8, [rbp+var_18]
0x180005ef1  mov     rax, [rcx]
0x180005ef4  lea     rdx, _GUID_e87a44c4_b76e_4c47_8b09_298eb12a2714
0x180005efb  mov     rax, [rax]
0x180005efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f03  mov     rcx, [rbp+var_18]
0x180005f07  mov     ebx, eax
0x180005f09  test    eax, eax
0x180005f0b  js      loc_180006129
0x180005f11  mov     [rbp+arg_0], 0
0x180005f18  lea     r9, [rbp+arg_0]
0x180005f1c  mov     rax, [rcx]
0x180005f1f  xor     r8d, r8d
0x180005f22  xor     edx, edx
0x180005f24  mov     rax, [rax+80h]
0x180005f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f30  mov     ebx, eax
0x180005f32  test    eax, eax
0x180005f34  js      loc_180006125
0x180005f3a  mov     ecx, [rbp+arg_0]
0x180005f3d  mov     eax, 2
0x180005f42  mul     rcx
0x180005f45  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005f4c  cmovb   rax, rcx
0x180005f50  mov     rcx, rax; unsigned __int64
0x180005f53  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005f58  mov     rcx, [rbp+var_18]
0x180005f5c  mov     rbx, rax
0x180005f5f  test    rax, rax
0x180005f62  jz      loc_1800060CE
0x180005f68  mov     rax, [rcx]
0x180005f6b  lea     r9, [rbp+arg_0]
0x180005f6f  mov     edx, [rbp+arg_0]
0x180005f72  mov     r8, rbx
0x180005f75  mov     rax, [rax+80h]
0x180005f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f81  mov     edi, eax
0x180005f83  mov     rcx, rbx; Block
0x180005f86  test    eax, eax
0x180005f88  js      loc_18000606E
0x180005f8e  mov     rdx, rsi; pszSrch
0x180005f91  call    cs:__imp_StrStrIW
0x180005f97  test    rax, rax
0x180005f9a  jnz     short loc_180005FD7
0x180005f9c  mov     rcx, rbx; Block
0x180005f9f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005fa4  mov     rcx, [rbp+var_18]
0x180005fa8  test    rcx, rcx
0x180005fab  jz      short loc_180005FB9
0x180005fad  mov     rax, [rcx]
0x180005fb0  mov     rax, [rax+10h]
0x180005fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fb9  mov     rcx, [rbp+var_10]
0x180005fbd  test    rcx, rcx
0x180005fc0  jz      loc_180005EA2
0x180005fc6  mov     rax, [rcx]
0x180005fc9  mov     rax, [rax+10h]
0x180005fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd2  jmp     loc_180005EA2
0x180005fd7  mov     rcx, [rbp+var_18]
0x180005fdb  mov     rdx, r14
0x180005fde  mov     rax, [rcx]
0x180005fe1  mov     rax, [rax+58h]
0x180005fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fea  mov     edi, eax
0x180005fec  mov     rcx, rbx; Block
0x180005fef  test    eax, eax
0x180005ff1  jns     short loc_18000600E
0x180005ff3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005ff8  mov     rcx, [rbp+var_18]
0x180005ffc  test    rcx, rcx
0x180005fff  jz      loc_180006088
0x180006005  mov     rdx, [rcx]
0x180006008  mov     rax, [rdx+10h]
0x18000600c  jmp     short loc_180006083
0x18000600e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006013  mov     rcx, [rbp+var_18]
0x180006017  test    rcx, rcx
0x18000601a  jz      short loc_180006028
0x18000601c  mov     rax, [rcx]
0x18000601f  mov     rax, [rax+10h]
0x180006023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006028  mov     rcx, [rbp+var_10]
0x18000602c  test    rcx, rcx
0x18000602f  jz      short loc_18000603D
0x180006031  mov     rax, [rcx]
0x180006034  mov     rax, [rax+10h]
0x180006038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000603d  mov     rcx, [rbp+var_8]
0x180006041  test    rcx, rcx
0x180006044  jz      short loc_180006052
0x180006046  mov     rax, [rcx]
0x180006049  mov     rax, [rax+10h]
0x18000604d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006052  mov     rcx, [rbp+var_20]
0x180006056  test    rcx, rcx
0x180006059  jz      short loc_180006067
0x18000605b  mov     rax, [rcx]
0x18000605e  mov     rax, [rax+10h]
0x180006062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006067  xor     eax, eax
0x180006069  jmp     loc_18000617B
0x18000606e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006073  mov     rcx, [rbp+var_18]
0x180006077  test    rcx, rcx
0x18000607a  jz      short loc_180006088
0x18000607c  mov     rax, [rcx]
0x18000607f  mov     rax, [rax+10h]
0x180006083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006088  mov     rcx, [rbp+var_10]
0x18000608c  test    rcx, rcx
0x18000608f  jz      short loc_18000609D
0x180006091  mov     rax, [rcx]
0x180006094  mov     rax, [rax+10h]
0x180006098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000609d  mov     rcx, [rbp+var_8]
0x1800060a1  test    rcx, rcx
0x1800060a4  jz      short loc_1800060B2
0x1800060a6  mov     rax, [rcx]
0x1800060a9  mov     rax, [rax+10h]
0x1800060ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b2  mov     rcx, [rbp+var_20]
0x1800060b6  test    rcx, rcx
0x1800060b9  jz      short loc_1800060C7
0x1800060bb  mov     rax, [rcx]
0x1800060be  mov     rax, [rax+10h]
0x1800060c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c7  mov     eax, edi
0x1800060c9  jmp     loc_18000617B
0x1800060ce  test    rcx, rcx
0x1800060d1  jz      short loc_1800060DF
0x1800060d3  mov     rax, [rcx]
0x1800060d6  mov     rax, [rax+10h]
0x1800060da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060df  mov     rcx, [rbp+var_10]
0x1800060e3  test    rcx, rcx
0x1800060e6  jz      short loc_1800060F4
0x1800060e8  mov     rax, [rcx]
0x1800060eb  mov     rax, [rax+10h]
0x1800060ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f4  mov     rcx, [rbp+var_8]
0x1800060f8  test    rcx, rcx
0x1800060fb  jz      short loc_180006109
0x1800060fd  mov     rax, [rcx]
0x180006100  mov     rax, [rax+10h]
0x180006104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006109  mov     rcx, [rbp+var_20]
0x18000610d  test    rcx, rcx
0x180006110  jz      short loc_18000611E
0x180006112  mov     rax, [rcx]
0x180006115  mov     rax, [rax+10h]
0x180006119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000611e  mov     eax, 8007000Eh
0x180006123  jmp     short loc_18000617B
0x180006125  mov     rcx, [rbp+var_18]
0x180006129  test    rcx, rcx
0x18000612c  jz      short loc_18000613A
0x18000612e  mov     rax, [rcx]
0x180006131  mov     rax, [rax+10h]
0x180006135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000613a  mov     rcx, [rbp+var_10]
0x18000613e  test    rcx, rcx
0x180006141  jz      short loc_18000614F
0x180006143  mov     rax, [rcx]
0x180006146  mov     rax, [rax+10h]
0x18000614a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000614f  mov     rcx, [rbp+var_8]
0x180006153  test    rcx, rcx
0x180006156  jz      short loc_180006164
0x180006158  mov     rax, [rcx]
0x18000615b  mov     rax, [rax+10h]
0x18000615f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006164  mov     rcx, [rbp+var_20]
0x180006168  test    rcx, rcx
0x18000616b  jz      short loc_180006179
0x18000616d  mov     rax, [rcx]
0x180006170  mov     rax, [rax+10h]
0x180006174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006179  mov     eax, ebx
0x18000617b  lea     r11, [rsp+50h+var_s0]
0x180006180  mov     rbx, [r11+28h]
0x180006184  mov     rsi, [r11+30h]
0x180006188  mov     rsp, r11
0x18000618b  pop     r14
0x18000618d  pop     rdi
0x18000618e  pop     rbp
0x18000618f  retn
0x180006190  test    rcx, rcx
0x180006193  jz      short loc_1800061A1
0x180006195  mov     rax, [rcx]
0x180006198  mov     rax, [rax+10h]
0x18000619c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a1  mov     rcx, [rbp+var_8]
0x1800061a5  test    rcx, rcx
0x1800061a8  jz      short loc_1800061B6
0x1800061aa  mov     rax, [rcx]
0x1800061ad  mov     rax, [rax+10h]
0x1800061b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b6  mov     rcx, [rbp+var_20]
0x1800061ba  test    rcx, rcx
0x1800061bd  jz      short loc_1800061CB
0x1800061bf  mov     rax, [rcx]
0x1800061c2  mov     rax, [rax+10h]
0x1800061c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061cb  mov     eax, 80004005h
0x1800061d0  jmp     short loc_18000617B
```
