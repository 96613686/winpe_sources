# win_dox::OpcPartUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::OpcUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>>>::ComparePartUri_Safe(IOpcPartUri *,int *)

- ea: `0x18001a25c`
- end: `0x18001a808`
- name: `?ComparePartUri_Safe@?$OpcPartUriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$OpcUriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@@win_dox@@@win_dox@@AEAAXPEAUIOpcPartUri@@PEAH@Z`
- size: `1452`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180019884`

## callees

- `0x180005d50`
- `0x18000d4d8`
- `0x18001a25c`
- `0x18001a900`
- `0x18001aaa0`
- `0x18001c5d0`
- `0x18001ca9c`
- `0x18005ab90`
- `0x1800cce54`
- `0x1800cdb60`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001a3c1`
- `msvcrt!memcpy_s` at `0x18001a614`
- `msvcrt!memcpy_s` at `0x18001a3c1`
- `msvcrt!memcpy_s` at `0x18001a614`

## string_xrefs

- `0x18001a73e`: `partUri`
- `0x18001a74a`: `ComparePartUri`
- `0x18001a786`: `ComparePartUri`
- `0x18001a77a`: `comparison`
- `0x18001a756`: `OpcPartUriCom`
- `0x18001a792`: `OpcPartUriCom`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall win_dox::OpcPartUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::OpcUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>>>::ComparePartUri_Safe(
        __int64 a1,
        __int64 a2,
        int *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rdx
  _QWORD *v8; // r12
  int v9; // r14d
  __int64 v10; // rbx
  unsigned __int64 v11; // rdi
  _QWORD *v12; // r8
  void **v13; // rcx
  void **v14; // rcx
  void **v15; // rcx
  void **v16; // rcx
  void **v17; // rax
  __int16 v18; // r8
  unsigned __int64 v19; // r8
  void **v20; // rdx
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdi
  __int64 Path; // rdx
  __int64 NormalizedPartNameInternal; // rax
  __int64 v28; // rsi
  unsigned __int64 v29; // rdi
  _QWORD *v30; // r8
  unsigned __int64 v31; // rdx
  void **v32; // rsi
  void *v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // [rsp+48h] [rbp-99h] BYREF
  __int64 v36; // [rsp+50h] [rbp-91h] BYREF
  __int64 v37; // [rsp+58h] [rbp-89h] BYREF
  __int64 v38; // [rsp+60h] [rbp-81h] BYREF
  _QWORD v39[3]; // [rsp+68h] [rbp-79h] BYREF
  char v40[8]; // [rsp+80h] [rbp-61h] BYREF
  void *Destination[2]; // [rsp+88h] [rbp-59h] BYREF
  unsigned __int64 v42; // [rsp+98h] [rbp-49h]
  unsigned __int64 v43; // [rsp+A0h] [rbp-41h]
  char v44[8]; // [rsp+A8h] [rbp-39h] BYREF
  void *v45; // [rsp+B0h] [rbp-31h]
  __int64 v46; // [rsp+C0h] [rbp-21h]
  unsigned __int64 v47; // [rsp+C8h] [rbp-19h]
  char v48[8]; // [rsp+D0h] [rbp-11h] BYREF
  void *Block; // [rsp+D8h] [rbp-9h]
  unsigned __int64 v50; // [rsp+F0h] [rbp+Fh]

  v39[1] = -2;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 180, L"OpcPartUriCom", L"ComparePartUri", L"partUri", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 181, L"OpcPartUriCom", L"ComparePartUri", L"comparison", 0);
  v6 = *(_QWORD *)win_dox::to_interface<IReceiver>::resolve(&v36, a2);
  v7 = *(_QWORD *)win_dox::to_interface<IReceiver>::resolve(&v35, v6);
  win_dox::to_interface<IReceiver>::resolve(&v37, v7);
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  win_dox::to_interface<IReceiver>::resolve(&v38, v6);
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  win_dox::to_interface<IReceiver>::resolve(v39, a2);
  v8 = *(_QWORD **)(a1 + 16);
  v9 = -1;
  if ( !v8[5] )
  {
    v24 = 0;
    v35 = 0;
    v25 = *v8;
    if ( *v8 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25 + 8LL))(*v8);
      v24 = v35;
    }
    else
    {
      v25 = 0;
    }
    v35 = v25;
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v39[2] = &v35;
    win_dox::to_interface<IByteReceiver>::resolve(&v36, &v35);
    if ( v35 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v35 = 0;
    }
    Path = win_dox::Uri::GetPath(&v36, v48);
    NormalizedPartNameInternal = win_dox::GetNormalizedPartNameInternal(v44, Path);
    v28 = NormalizedPartNameInternal;
    v29 = *(_QWORD *)(NormalizedPartNameInternal + 24);
    if ( v8 + 2 == (_QWORD *)NormalizedPartNameInternal )
    {
      std::wstring::erase(v8 + 2, *(_QWORD *)(NormalizedPartNameInternal + 24), -1);
      std::wstring::erase(v8 + 2, 0, 0);
    }
    else
    {
      if ( v29 > 0x7FFFFFFFFFFFFFFELL )
        std::_String_base::_Xlen();
      if ( v8[6] >= v29 )
      {
        if ( !v29 )
        {
          v34 = v8 + 3;
          if ( v8[6] >= 8u )
            v34 = (_QWORD *)*v34;
          v8[5] = 0;
          *(_WORD *)v34 = 0;
          goto LABEL_67;
        }
        goto LABEL_60;
      }
      std::wstring::_Copy(v8 + 2, v29, v8[5]);
      if ( v29 )
      {
LABEL_60:
        v30 = (_QWORD *)(v28 + 8);
        if ( *(_QWORD *)(v28 + 32) >= 8u )
          v30 = (_QWORD *)*v30;
        v31 = v8[6];
        v32 = (void **)(v8 + 3);
        if ( v31 < 8 )
          v33 = v8 + 3;
        else
          v33 = *v32;
        memcpy_s(v33, 2 * v31, v30, 2 * v29);
        if ( v8[6] >= 8u )
          v32 = (void **)*v32;
        v8[5] = v29;
        *((_WORD *)v32 + v29) = 0;
      }
    }
LABEL_67:
    if ( v47 >= 8 )
      operator delete(v45);
    v47 = 7;
    v46 = 0;
    LOWORD(v45) = 0;
    if ( v50 >= 8 )
      operator delete(Block);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v10 = win_dox::Uri::GetPath(&v37, v48);
  v43 = 7;
  v42 = 0;
  LOWORD(Destination[0]) = 0;
  v11 = *(_QWORD *)(v10 + 24);
  if ( v40 == (char *)v10 )
  {
    std::wstring::erase(v40, v11, -1);
    std::wstring::erase(v40, 0, 0);
  }
  else
  {
    if ( v11 > 0x7FFFFFFFFFFFFFFELL )
      std::_String_base::_Xlen();
    if ( v43 < v11 )
    {
      std::wstring::_Copy(v40, v11, v42);
      if ( v11 )
        goto LABEL_12;
    }
    else
    {
      if ( v11 )
      {
LABEL_12:
        v12 = (_QWORD *)(v10 + 8);
        if ( *(_QWORD *)(v10 + 32) >= 8u )
          v12 = (_QWORD *)*v12;
        v13 = Destination;
        if ( v43 >= 8 )
          v13 = (void **)Destination[0];
        memcpy_s(v13, 2 * v43, v12, 2 * v11);
        v14 = Destination;
        if ( v43 >= 8 )
          v14 = (void **)Destination[0];
        v42 = v11;
        *((_WORD *)v14 + v11) = 0;
        goto LABEL_19;
      }
      v42 = 0;
      LOWORD(Destination[0]) = 0;
    }
  }
LABEL_19:
  v15 = Destination;
  if ( v43 >= 8 )
    v15 = (void **)Destination[0];
  v16 = (void **)((char *)v15 + 2 * v42);
  v17 = Destination;
  if ( v43 >= 8 )
    v17 = (void **)Destination[0];
  while ( v17 != v16 )
  {
    v18 = *(_WORD *)v17;
    if ( (unsigned __int16)(*(_WORD *)v17 - 97) <= 0x19u )
      v18 -= 32;
    *(_WORD *)v17 = v18;
    v17 = (void **)((char *)v17 + 2);
  }
  if ( v50 >= 8 )
    operator delete(Block);
  v19 = v42;
  v20 = Destination;
  if ( v43 >= 8 )
    v20 = (void **)Destination[0];
  v21 = v8[5];
  v22 = v42;
  if ( v21 < v42 )
    v22 = v8[5];
  v23 = v8 + 3;
  if ( v8[6] >= 8u )
    v23 = (_QWORD *)*v23;
  while ( v22 )
  {
    if ( *(_WORD *)v23 != *(_WORD *)v20 )
    {
      v9 = *(_WORD *)v23 < *(_WORD *)v20 ? -1 : 1;
      goto LABEL_39;
    }
    v23 = (_QWORD *)((char *)v23 + 2);
    v20 = (void **)((char *)v20 + 2);
    --v22;
  }
  if ( v21 >= v42 )
    v9 = v21 != v42;
LABEL_39:
  if ( v43 >= 8 )
    operator delete(Destination[0]);
  *a3 = v9;
  if ( v39[0] )
    (*(void (__fastcall **)(_QWORD, void **, unsigned __int64))(*(_QWORD *)v39[0] + 16LL))(v39[0], v20, v19);
  if ( v38 )
    (*(void (__fastcall **)(__int64, void **, unsigned __int64))(*(_QWORD *)v38 + 16LL))(v38, v20, v19);
  if ( v37 )
    (*(void (__fastcall **)(__int64, void **, unsigned __int64))(*(_QWORD *)v37 + 16LL))(v37, v20, v19);
}

```

## disassembly

```asm
0x18001a25c  mov     rax, rsp
0x18001a25f  push    rbp
0x18001a260  push    rsi
0x18001a261  push    rdi
0x18001a262  push    r12
0x18001a264  push    r13
0x18001a266  push    r14
0x18001a268  push    r15
0x18001a26a  lea     rbp, [rax-5Fh]
0x18001a26e  sub     rsp, 100h
0x18001a275  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18001a27d  mov     [rax+20h], rbx
0x18001a281  mov     rax, cs:__security_cookie
0x18001a288  xor     rax, rsp
0x18001a28b  mov     [rbp+57h+var_40], rax
0x18001a28f  mov     r13, r8
0x18001a292  mov     rbx, rdx
0x18001a295  mov     rsi, rcx
0x18001a298  xor     r15d, r15d
0x18001a29b  test    rdx, rdx
0x18001a29e  jz      loc_18001A739
0x18001a2a4  test    r8, r8
0x18001a2a7  jz      loc_18001A775
0x18001a2ad  lea     rcx, [rsp+130h+var_E8]
0x18001a2b2  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x18001a2b7  nop
0x18001a2b8  mov     rdi, [rax]
0x18001a2bb  mov     rdx, rdi
0x18001a2be  lea     rcx, [rsp+130h+var_F0]
0x18001a2c3  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x18001a2c8  nop
0x18001a2c9  mov     rdx, [rax]
0x18001a2cc  lea     rcx, [rsp+130h+var_E0]
0x18001a2d1  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x18001a2d6  nop
0x18001a2d7  mov     rcx, [rsp+130h+var_F0]
0x18001a2dc  test    rcx, rcx
0x18001a2df  jz      short loc_18001A2F2
0x18001a2e1  mov     rax, [rcx]
0x18001a2e4  mov     rax, [rax+10h]
0x18001a2e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2ed  mov     [rsp+130h+var_F0], r15
0x18001a2f2  mov     rdx, rdi
0x18001a2f5  lea     rcx, [rsp+130h+var_D8]
0x18001a2fa  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x18001a2ff  nop
0x18001a300  mov     rcx, [rsp+130h+var_E8]
0x18001a305  test    rcx, rcx
0x18001a308  jz      short loc_18001A31B
0x18001a30a  mov     rax, [rcx]
0x18001a30d  mov     rax, [rax+10h]
0x18001a311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a316  mov     [rsp+130h+var_E8], r15
0x18001a31b  mov     rdx, rbx
0x18001a31e  lea     rcx, [rbp+57h+var_D0]
0x18001a322  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x18001a327  nop
0x18001a328  mov     r12, [rsi+10h]
0x18001a32c  lea     rbx, [r12+10h]
0x18001a331  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001a335  mov     rsi, 7FFFFFFFFFFFFFFEh
0x18001a33f  cmp     [rbx+18h], r15
0x18001a343  jz      loc_18001A537
0x18001a349  lea     rdx, [rbp+57h+var_68]
0x18001a34d  lea     rcx, [rsp+130h+var_E0]
0x18001a352  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x18001a357  mov     rbx, rax
0x18001a35a  mov     [rbp+57h+var_98], 7
0x18001a362  mov     [rbp+57h+var_A0], r15
0x18001a366  mov     word ptr [rbp+57h+Destination], r15w
0x18001a36b  mov     rdi, [rax+18h]
0x18001a36f  lea     rax, [rbp+57h+var_B8]
0x18001a373  cmp     rax, rbx
0x18001a376  jz      loc_18001A7DB
0x18001a37c  cmp     rdi, rsi
0x18001a37f  ja      loc_18001A7FD
0x18001a385  cmp     [rbp+57h+var_98], rdi
0x18001a389  jb      loc_18001A519
0x18001a38f  test    rdi, rdi
0x18001a392  jz      loc_18001A67B
0x18001a398  lea     r8, [rbx+8]
0x18001a39c  cmp     qword ptr [rbx+20h], 8
0x18001a3a1  jb      short loc_18001A3A6
0x18001a3a3  mov     r8, [r8]; Source
0x18001a3a6  mov     rdx, [rbp+57h+var_98]
0x18001a3aa  lea     rcx, [rbp+57h+Destination]
0x18001a3ae  cmp     rdx, 8
0x18001a3b2  cmovnb  rcx, [rbp+57h+Destination]; Destination
0x18001a3b7  lea     rbx, [rdi+rdi]
0x18001a3bb  add     rdx, rdx; DestinationSize
0x18001a3be  mov     r9, rbx; SourceSize
0x18001a3c1  call    cs:__imp_memcpy_s
0x18001a3c7  lea     rcx, [rbp+57h+Destination]
0x18001a3cb  cmp     [rbp+57h+var_98], 8
0x18001a3d0  cmovnb  rcx, [rbp+57h+Destination]
0x18001a3d5  mov     [rbp+57h+var_A0], rdi
0x18001a3d9  mov     [rbx+rcx], r15w
0x18001a3de  lea     rcx, [rbp+57h+Destination]
0x18001a3e2  cmp     [rbp+57h+var_98], 8
0x18001a3e7  cmovnb  rcx, [rbp+57h+Destination]
0x18001a3ec  mov     rax, [rbp+57h+var_A0]
0x18001a3f0  lea     rcx, [rcx+rax*2]
0x18001a3f4  lea     rax, [rbp+57h+Destination]
0x18001a3f8  cmovnb  rax, [rbp+57h+Destination]
0x18001a3fd  cmp     rax, rcx
0x18001a400  jz      short loc_18001A41A
0x18001a402  movzx   r8d, word ptr [rax]
0x18001a406  lea     edx, [r8-61h]
0x18001a40a  cmp     dx, 19h
0x18001a40e  jbe     short loc_18001A476
0x18001a410  mov     [rax], r8w
0x18001a414  add     rax, 2
0x18001a418  jmp     short loc_18001A3FD
0x18001a41a  cmp     [rbp+57h+var_48], 8
0x18001a41f  jnb     loc_18001A4FD
0x18001a425  mov     r8, [rbp+57h+var_A0]
0x18001a429  lea     rdx, [rbp+57h+Destination]
0x18001a42d  cmp     [rbp+57h+var_98], 8
0x18001a432  cmovnb  rdx, [rbp+57h+Destination]
0x18001a437  mov     r9, [r12+28h]
0x18001a43c  mov     rcx, r8
0x18001a43f  cmp     r9, r8
0x18001a442  cmovb   rcx, r9
0x18001a446  lea     rax, [r12+18h]
0x18001a44b  cmp     qword ptr [r12+30h], 8
0x18001a451  jb      short loc_18001A456
0x18001a453  mov     rax, [rax]
0x18001a456  test    rcx, rcx
0x18001a459  jz      loc_18001A722
0x18001a45f  movzx   r10d, word ptr [rax]
0x18001a463  cmp     r10w, [rdx]
0x18001a467  jnz     short loc_18001A47D
0x18001a469  add     rax, 2
0x18001a46d  add     rdx, 2
0x18001a471  dec     rcx
0x18001a474  jmp     short loc_18001A456
0x18001a476  sub     r8w, 20h ; ' '
0x18001a47b  jmp     short loc_18001A410
0x18001a47d  sbb     r14d, r14d
0x18001a480  and     r14d, 0FFFFFFFEh
0x18001a484  inc     r14d
0x18001a487  cmp     [rbp+57h+var_98], 8
0x18001a48c  jnb     short loc_18001A50B
0x18001a48e  mov     [r13+0], r14d
0x18001a492  mov     rcx, [rbp+57h+var_D0]
0x18001a496  test    rcx, rcx
0x18001a499  jz      short loc_18001A4A8
0x18001a49b  mov     rax, [rcx]
0x18001a49e  mov     rax, [rax+10h]
0x18001a4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4a7  nop
0x18001a4a8  mov     rcx, [rsp+130h+var_D8]
0x18001a4ad  test    rcx, rcx
0x18001a4b0  jz      short loc_18001A4BF
0x18001a4b2  mov     rax, [rcx]
0x18001a4b5  mov     rax, [rax+10h]
0x18001a4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4be  nop
0x18001a4bf  mov     rcx, [rsp+130h+var_E0]
0x18001a4c4  test    rcx, rcx
0x18001a4c7  jz      short loc_18001A4D6
0x18001a4c9  mov     rax, [rcx]
0x18001a4cc  mov     rax, [rax+10h]
0x18001a4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4d5  nop
0x18001a4d6  mov     rcx, [rbp+57h+var_40]
0x18001a4da  xor     rcx, rsp; StackCookie
0x18001a4dd  call    __security_check_cookie
0x18001a4e2  mov     rbx, [rsp+130h+arg_18]
0x18001a4ea  add     rsp, 100h
0x18001a4f1  pop     r15
0x18001a4f3  pop     r14
0x18001a4f5  pop     r13
0x18001a4f7  pop     r12
0x18001a4f9  pop     rdi
0x18001a4fa  pop     rsi
0x18001a4fb  pop     rbp
0x18001a4fc  retn
0x18001a4fd  mov     rcx, [rbp+57h+Block]; Block
0x18001a501  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a506  jmp     loc_18001A425
0x18001a50b  mov     rcx, [rbp+57h+Destination]; Block
0x18001a50f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a514  jmp     loc_18001A48E
0x18001a519  mov     r8, [rbp+57h+var_A0]
0x18001a51d  mov     rdx, rdi
0x18001a520  lea     rcx, [rbp+57h+var_B8]
0x18001a524  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001a529  test    rdi, rdi
0x18001a52c  jz      loc_18001A3DE
0x18001a532  jmp     loc_18001A398
0x18001a537  mov     rcx, r15
0x18001a53a  mov     [rsp+130h+var_F0], rcx
0x18001a53f  mov     rdi, [r12]
0x18001a543  test    rdi, rdi
0x18001a546  jz      loc_18001A6AC
0x18001a54c  mov     rax, [rdi]
0x18001a54f  mov     rcx, rdi
0x18001a552  mov     rax, [rax+8]
0x18001a556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a55b  mov     rcx, [rsp+130h+var_F0]
0x18001a560  mov     [rsp+130h+var_F0], rdi
0x18001a565  test    rcx, rcx
0x18001a568  jnz     loc_18001A6B4
0x18001a56e  lea     rax, [rsp+130h+var_F0]
0x18001a573  mov     [rbp+57h+var_C0], rax
0x18001a577  lea     rdx, [rsp+130h+var_F0]
0x18001a57c  lea     rcx, [rsp+130h+var_E8]
0x18001a581  call    ?resolve@?$to_interface@UIByteReceiver@@@win_dox@@SA?AV?$scope@PEAUIByteReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBV34@@Z; win_dox::to_interface<IByteReceiver>::resolve(win_scope::scope<IByteReceiver *,win_scope::const_policies<win_scope::com_policies>> const &)
0x18001a586  nop
0x18001a587  mov     rcx, [rsp+130h+var_F0]
0x18001a58c  test    rcx, rcx
0x18001a58f  jnz     loc_18001A696
0x18001a595  lea     rdx, [rbp+57h+var_68]
0x18001a599  lea     rcx, [rsp+130h+var_E8]
0x18001a59e  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x18001a5a3  nop
0x18001a5a4  mov     rdx, rax
0x18001a5a7  lea     rcx, [rbp+57h+var_90]
0x18001a5ab  call    ?GetNormalizedPartNameInternal@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV23@@Z; win_dox::GetNormalizedPartNameInternal(std::wstring const &)
0x18001a5b0  mov     rsi, rax
0x18001a5b3  mov     rdi, [rax+18h]
0x18001a5b7  cmp     rbx, rax
0x18001a5ba  jz      loc_18001A7B1
0x18001a5c0  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001a5ca  cmp     rdi, rax
0x18001a5cd  ja      loc_18001A7D1
0x18001a5d3  cmp     [rbx+20h], rdi
0x18001a5d7  jb      loc_18001A6E1
0x18001a5dd  test    rdi, rdi
0x18001a5e0  jz      loc_18001A706
0x18001a5e6  lea     r8, [rsi+8]
0x18001a5ea  cmp     qword ptr [rsi+20h], 8
0x18001a5ef  jb      short loc_18001A5F4
0x18001a5f1  mov     r8, [r8]; Source
0x18001a5f4  mov     rdx, [rbx+20h]
0x18001a5f8  lea     rsi, [r12+18h]
0x18001a5fd  cmp     rdx, 8
0x18001a601  jb      loc_18001A6FE
0x18001a607  mov     rcx, [rsi]; Destination
0x18001a60a  lea     r15, [rdi+rdi]
0x18001a60e  add     rdx, rdx; DestinationSize
0x18001a611  mov     r9, r15; SourceSize
0x18001a614  call    cs:__imp_memcpy_s
0x18001a61a  cmp     qword ptr [rbx+20h], 8
0x18001a61f  jb      short loc_18001A624
0x18001a621  mov     rsi, [rsi]
0x18001a624  mov     [rbx+18h], rdi
0x18001a628  xor     eax, eax
0x18001a62a  mov     [r15+rsi], ax
0x18001a62f  xor     r15d, r15d
0x18001a632  cmp     [rbp+57h+var_70], 8
0x18001a637  jnb     loc_18001A6C5
0x18001a63d  mov     [rbp+57h+var_70], 7
0x18001a645  mov     [rbp+57h+var_78], r15
0x18001a649  mov     word ptr [rbp+57h+var_88], r15w
0x18001a64e  cmp     [rbp+57h+var_48], 8
0x18001a653  jnb     short loc_18001A6D3
0x18001a655  mov     rcx, [rsp+130h+var_E8]
0x18001a65a  test    rcx, rcx
0x18001a65d  jz      short loc_18001A66C
0x18001a65f  mov     rax, [rcx]
0x18001a662  mov     rax, [rax+10h]
0x18001a666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a66b  nop
0x18001a66c  mov     rsi, 7FFFFFFFFFFFFFFEh
0x18001a676  jmp     loc_18001A349
0x18001a67b  lea     rcx, [rbp+57h+Destination]
0x18001a67f  cmp     [rbp+57h+var_98], 8
0x18001a684  cmovnb  rcx, [rbp+57h+Destination]
0x18001a689  mov     [rbp+57h+var_A0], r15
0x18001a68d  mov     [rcx], r15w
0x18001a691  jmp     loc_18001A3DE
0x18001a696  mov     rax, [rcx]
0x18001a699  mov     rax, [rax+10h]
0x18001a69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6a2  mov     [rsp+130h+var_F0], r15
0x18001a6a7  jmp     loc_18001A595
0x18001a6ac  mov     rdi, r15
0x18001a6af  jmp     loc_18001A560
0x18001a6b4  mov     rax, [rcx]
0x18001a6b7  mov     rax, [rax+10h]
0x18001a6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6c0  jmp     loc_18001A56E
0x18001a6c5  mov     rcx, [rbp+57h+var_88]; Block
0x18001a6c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a6ce  jmp     loc_18001A63D
0x18001a6d3  mov     rcx, [rbp+57h+Block]; Block
0x18001a6d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a6dc  jmp     loc_18001A655
0x18001a6e1  mov     r8, [rbx+18h]
0x18001a6e5  mov     rdx, rdi
0x18001a6e8  mov     rcx, rbx
0x18001a6eb  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001a6f0  test    rdi, rdi
0x18001a6f3  jz      loc_18001A632
0x18001a6f9  jmp     loc_18001A5E6
0x18001a6fe  mov     rcx, rsi
0x18001a701  jmp     loc_18001A60A
0x18001a706  lea     rcx, [r12+18h]
  ... truncated ...
```
