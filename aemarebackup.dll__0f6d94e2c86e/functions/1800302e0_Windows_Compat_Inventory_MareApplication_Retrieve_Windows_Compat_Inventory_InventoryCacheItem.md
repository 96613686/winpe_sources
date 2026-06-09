# Windows::Compat::Inventory::MareApplication::Retrieve(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x1800302e0`
- end: `0x1800307f5`
- name: `?Retrieve@MareApplication@Inventory@Compat@Windows@@UEAAKPEAVInventoryCacheItem@234@@Z`
- size: `1301`
- prototype: `unsigned int __fastcall(Windows::Compat::Inventory::MareApplication *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002eb20`

## callees

- `0x180004ea0`
- `0x18000529c`
- `0x180005914`
- `0x18000702c`
- `0x18000712e`
- `0x180010640`
- `0x180011fcc`
- `0x1800134b8`
- `0x18002756c`
- `0x180027714`
- `0x18002bd20`
- `0x1800302e0`
- `0x180030d70`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180030744`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180030744`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003071b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003071b`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800307e8`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800307e8`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800307da`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800307da`

## string_xrefs

- `0x180030363`: `InventoryCacheItem::GetItemProperty failed [%#x]`
- `0x1800303fb`: `InventoryCacheItem::GetItemProperty failed [%#x]`
- `0x180030374`: `Windows::Compat::Inventory::MareApplication::Retrieve`
- `0x180030421`: `Windows::Compat::Inventory::MareApplication::Retrieve`
- `0x180030524`: `Windows::Compat::Inventory::MareApplication::Retrieve`
- `0x1800306dc`: `Windows::Compat::Inventory::MareApplication::Retrieve`
- `0x1800306cf`: `Unexpected sidStatePair "%ls" [%#x]`
- `0x180030500`: `SidState`
- `0x180030580`: `SidState`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Compat::Inventory::MareApplication::Retrieve(
        Windows::Compat::Inventory::MareApplication *this,
        struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  void *v3; // rbx
  int v4; // eax
  unsigned __int16 v5; // r15
  __int64 v6; // r8
  const struct std::nothrow_t *v7; // rdx
  int v9; // eax
  void *v10; // r15
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rdi
  __int64 v13; // r8
  void **v14; // rcx
  unsigned __int64 v15; // rdx
  char *v16; // r15
  __int64 v17; // rdi
  int v18; // eax
  unsigned __int64 v19; // rdi
  const struct std::nothrow_t *v20; // rdx
  __int64 v21; // r8
  void **v22; // rsi
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // rdi
  __int64 v26; // r13
  __int64 v27; // rax
  const wchar_t *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  wchar_t *v32; // rsi
  _DWORD *v33; // r14
  int v34; // eax
  __int64 *v35; // rsi
  __int64 v36; // r14
  __int64 v37; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+30h] [rbp-D0h] BYREF
  int v39; // [rsp+34h] [rbp-CCh]
  wchar_t *EndPtr; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v41; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h]
  int v43; // [rsp+58h] [rbp-A8h] BYREF
  void *v44; // [rsp+60h] [rbp-A0h]
  __int64 *v45; // [rsp+68h] [rbp-98h]
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h]
  _BYTE v48[32]; // [rsp+88h] [rbp-78h] BYREF
  void *v49[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v50; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v51; // [rsp+C0h] [rbp-40h]
  char *v52[4]; // [rsp+C8h] [rbp-38h] BYREF
  char *v53[4]; // [rsp+E8h] [rbp-18h] BYREF

  v45 = (__int64 *)this;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  v51 = 7;
  LOWORD(v49[0]) = 0;
  v41 = 0;
  v42 = 0;
  v3 = 0;
  v44 = 0;
  v4 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, const wchar_t *, char *))(*(_QWORD *)a2 + 72LL))(
         a2,
         L"Hash",
         (char *)this + 256);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 600;
LABEL_3:
    LODWORD(v37) = v4;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareApplication::Retrieve",
      v6,
      "InventoryCacheItem::GetItemProperty failed [%#x]",
      v37);
    goto LABEL_4;
  }
  v38 = 0;
  v9 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, const wchar_t *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         L"Aumids",
         0,
         &v38);
  v10 = 0;
  v11 = -1;
  if ( (_WORD)v9 != 2 )
  {
    if ( v9 < 0 )
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareApplication::Retrieve",
        611,
        "InventoryCacheItem::GetItemProperty failed [%#x]",
        v9);
    v12 = saturated_mul(v38, 2u);
    v3 = operator new[](v12);
    memset_0(v3, 0, v12);
    v44 = v3;
    v4 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, const wchar_t *, void *, unsigned int *))(*(_QWORD *)a2 + 64LL))(
           a2,
           L"Aumids",
           v3,
           &v38);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 617;
      goto LABEL_3;
    }
    v14 = (void **)(v45 + 28);
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v3 + v15) );
    if ( v15 > v45[31] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v14, v15, v13, v3);
    }
    else
    {
      if ( (unsigned __int64)v45[31] <= 7 )
        v16 = (char *)(v45 + 28);
      else
        v16 = (char *)*v14;
      v45[30] = v15;
      v17 = 2 * v15;
      memmove_0(v16, v3, 2 * v15);
      *(_WORD *)&v16[v17] = 0;
    }
    v10 = v3;
  }
  v38 = 0;
  v18 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, const wchar_t *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          L"SidState",
          0,
          &v38);
  if ( v18 < 0 )
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareApplication::Retrieve",
      628,
      "InventoryCacheItem::GetItemProperty failed [%#x]",
      v18);
  v19 = saturated_mul(v38, 2u);
  v3 = operator new[](v19);
  memset_0(v3, 0, v19);
  v44 = v3;
  if ( v10 )
    operator delete(v10, v20);
  v4 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, const wchar_t *, void *, unsigned int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         L"SidState",
         v3,
         &v38);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 634;
    goto LABEL_3;
  }
  do
    ++v11;
  while ( *((_WORD *)v3 + v11) );
  if ( v11 > v51 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v49, v11, v21, v3);
  }
  else
  {
    v22 = v49;
    if ( v51 > 7 )
      v22 = (void **)v49[0];
    v50 = v11;
    memmove_0(v22, v3, 2 * v11);
    *((_WORD *)v22 + v11) = 0;
  }
  v23 = std::wstring::wstring((__int64)v53, (__int64)v49);
  v24 = Windows::Compat::Inventory::SplitString(&v46, v23, 124);
  if ( &v41 == (__int128 *)v24 )
  {
    v26 = *((_QWORD *)&v41 + 1);
    v25 = v41;
  }
  else
  {
    std::vector<std::wstring>::_Tidy(&v41);
    v25 = *(_QWORD *)v24;
    *(_QWORD *)&v41 = *(_QWORD *)v24;
    v26 = *(_QWORD *)(v24 + 8);
    *((_QWORD *)&v41 + 1) = v26;
    v42 = *(_QWORD *)(v24 + 16);
    *(_QWORD *)v24 = 0;
    *(_QWORD *)(v24 + 8) = 0;
    *(_QWORD *)(v24 + 16) = 0;
  }
  std::vector<std::wstring>::_Tidy(&v46);
  while ( v25 != v26 )
  {
    std::wstring::wstring((__int64)v52, v25);
    v27 = std::wstring::wstring((__int64)v48, (__int64)v52);
    Windows::Compat::Inventory::SplitString(&v46, v27, 58);
    if ( ((v47 - v46) & 0xFFFFFFFFFFFFFFE0uLL) == 0x40 )
    {
      std::wstring::wstring((__int64)v53, v46);
      if ( (unsigned __int64)((v47 - v46) >> 5) <= 1 )
        std::vector<std::wstring>::_Xrange();
      v32 = (wchar_t *)(v46 + 32);
      v33 = (_DWORD *)_o__errno(v30, v29, v31);
      if ( *((_QWORD *)v32 + 3) > 7u )
        v32 = *(wchar_t **)v32;
      EndPtr = 0;
      *v33 = 0;
      v34 = wcstol(v32, &EndPtr, 10);
      v39 = v34;
      if ( v32 == EndPtr )
      {
        std::_Xinvalid_argument("invalid stoi argument");
        __debugbreak();
      }
      if ( *v33 == 34 )
      {
        std::_Xout_of_range("stoi argument out of range");
        __debugbreak();
      }
      v43 = v34;
      v35 = v45;
      v36 = v45[10];
      if ( v36 == v45[11] )
      {
        std::vector<std::pair<std::wstring,enum Windows::Compat::Inventory::MareApplication::AppState>>::_Emplace_reallocate<std::wstring &,enum Windows::Compat::Inventory::MareApplication::AppState &>(
          v45 + 9,
          v45[10],
          (__int64)v53,
          &v43);
      }
      else
      {
        std::wstring::wstring(v45[10], (__int64)v53);
        *(_DWORD *)(v36 + 32) = v39;
        v35[10] += 40;
      }
      std::wstring::~wstring(v53);
    }
    else
    {
      v28 = (const wchar_t *)v52;
      if ( v52[3] > (char *)7 )
        v28 = (const wchar_t *)v52[0];
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareApplication::Retrieve",
        646,
        "Unexpected sidStatePair \"%ls\" [%#x]",
        v28,
        -2147418113);
    }
    std::vector<std::wstring>::_Tidy(&v46);
    std::wstring::~wstring(v52);
    v25 += 32;
  }
LABEL_4:
  if ( v3 )
    operator delete(v3, v7);
  std::vector<std::wstring>::_Tidy(&v41);
  std::wstring::~wstring((char **)v49);
  return v5;
}

```

## disassembly

```asm
0x1800302e0  mov     [rsp-8+arg_10], rbx
0x1800302e5  mov     [rsp-8+arg_18], rsi
0x1800302ea  push    rbp
0x1800302eb  push    rdi
0x1800302ec  push    r13
0x1800302ee  push    r14
0x1800302f0  push    r15
0x1800302f2  lea     rbp, [rsp-10h]
0x1800302f7  sub     rsp, 110h
0x1800302fe  mov     rax, cs:__security_cookie
0x180030305  xor     rax, rsp
0x180030308  mov     [rbp+30h+var_28], rax
0x18003030c  mov     r13, rdx
0x18003030f  mov     [rsp+130h+var_C8], rcx
0x180030314  xorps   xmm0, xmm0
0x180030317  movups  xmmword ptr [rbp+30h+var_88], xmm0
0x18003031b  xor     edi, edi
0x18003031d  mov     [rbp+30h+var_78], rdi
0x180030321  mov     [rbp+30h+var_70], 7
0x180030329  mov     word ptr [rbp+30h+var_88], di
0x18003032d  movdqu  [rsp+130h+var_F0], xmm0
0x180030333  mov     [rsp+130h+var_E0], rdi
0x180030338  mov     ebx, edi
0x18003033a  mov     [rsp+130h+var_D0], rbx
0x18003033f  mov     rax, [rdx]
0x180030342  lea     r8, [rcx+100h]
0x180030349  lea     rdx, aHash; "Hash"
0x180030350  mov     rcx, r13
0x180030353  mov     rax, [rax+48h]
0x180030357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003035c  mov     r15d, eax
0x18003035f  test    eax, eax
0x180030361  jns     short loc_1800303D5
0x180030363  lea     r9, aInventorycache_7; "InventoryCacheItem::GetItemProperty fai"...
0x18003036a  mov     r8d, 258h
0x180030370  mov     dword ptr [rsp+130h+var_110], eax
0x180030374  lea     rdx, aWindowsCompatI_38; "Windows::Compat::Inventory::MareApplica"...
0x18003037b  mov     ecx, 1
0x180030380  call    AslLogCallPrintf
0x180030385  movzx   edi, r15w
0x180030389  test    rbx, rbx
0x18003038c  jz      short loc_180030397
0x18003038e  mov     rcx, rbx; void *
0x180030391  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030396  nop
0x180030397  lea     rcx, [rsp+130h+var_F0]
0x18003039c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800303a1  nop
0x1800303a2  lea     rcx, [rbp+30h+var_88]
0x1800303a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800303ab  mov     eax, edi
0x1800303ad  mov     rcx, [rbp+30h+var_28]
0x1800303b1  xor     rcx, rsp; StackCookie
0x1800303b4  call    __security_check_cookie
0x1800303b9  lea     r11, [rsp+130h+var_20]
0x1800303c1  mov     rbx, [r11+40h]
0x1800303c5  mov     rsi, [r11+48h]
0x1800303c9  mov     rsp, r11
0x1800303cc  pop     r15
0x1800303ce  pop     r14
0x1800303d0  pop     r13
0x1800303d2  pop     rdi
0x1800303d3  pop     rbp
0x1800303d4  retn
0x1800303d5  mov     [rsp+130h+var_100], edi
0x1800303d9  mov     rax, [r13+0]
0x1800303dd  lea     r9, [rsp+130h+var_100]
0x1800303e2  xor     r8d, r8d
0x1800303e5  lea     rdx, aAumids; "Aumids"
0x1800303ec  mov     rcx, r13
0x1800303ef  mov     rax, [rax+40h]
0x1800303f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303f8  mov     r15, rdi
0x1800303fb  lea     rsi, aInventorycache_7; "InventoryCacheItem::GetItemProperty fai"...
0x180030402  or      r14, 0FFFFFFFFFFFFFFFFh
0x180030406  cmp     ax, 2
0x18003040a  jz      loc_1800304F0
0x180030410  test    eax, eax
0x180030412  jns     short loc_180030431
0x180030414  mov     dword ptr [rsp+130h+var_110], eax
0x180030418  mov     r9, rsi
0x18003041b  mov     r8d, 263h
0x180030421  lea     rdx, aWindowsCompatI_38; "Windows::Compat::Inventory::MareApplica"...
0x180030428  lea     ecx, [r14+2]
0x18003042c  call    AslLogCallPrintf
0x180030431  mov     ecx, [rsp+130h+var_100]
0x180030435  mov     eax, 2
0x18003043a  mul     rcx
0x18003043d  mov     rdi, rax
0x180030440  cmovb   rdi, r14
0x180030444  mov     rcx, rdi; unsigned __int64
0x180030447  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003044c  mov     rbx, rax
0x18003044f  mov     r8, rdi; Size
0x180030452  xor     edx, edx; Val
0x180030454  mov     rcx, rax; void *
0x180030457  call    memset_0
0x18003045c  mov     [rsp+130h+var_D0], rbx
0x180030461  mov     rax, [r13+0]
0x180030465  lea     r9, [rsp+130h+var_100]
0x18003046a  mov     r8, rbx
0x18003046d  lea     rdx, aAumids; "Aumids"
0x180030474  mov     rcx, r13
0x180030477  mov     rax, [rax+40h]
0x18003047b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030480  mov     r15d, eax
0x180030483  xor     edi, edi
0x180030485  test    eax, eax
0x180030487  jns     short loc_180030497
0x180030489  mov     r9, rsi
0x18003048c  mov     r8d, 269h
0x180030492  jmp     loc_180030370
0x180030497  mov     rcx, [rsp+130h+var_C8]
0x18003049c  add     rcx, 0E0h
0x1800304a3  mov     rdx, r14
0x1800304a6  inc     rdx
0x1800304a9  cmp     [rbx+rdx*2], di
0x1800304ad  jnz     short loc_1800304A6
0x1800304af  cmp     rdx, [rcx+18h]
0x1800304b3  ja      short loc_1800304E5
0x1800304b5  cmp     qword ptr [rcx+18h], 7
0x1800304ba  jbe     short loc_1800304C1
0x1800304bc  mov     r15, [rcx]
0x1800304bf  jmp     short loc_1800304C4
0x1800304c1  mov     r15, rcx
0x1800304c4  mov     [rcx+10h], rdx
0x1800304c8  lea     rdi, [rdx+rdx]
0x1800304cc  mov     r8, rdi; Size
0x1800304cf  mov     rdx, rbx; Src
0x1800304d2  mov     rcx, r15; void *
0x1800304d5  call    memmove_0
0x1800304da  xor     eax, eax
0x1800304dc  mov     [rdi+r15], ax
0x1800304e1  xor     edi, edi
0x1800304e3  jmp     short loc_1800304ED
0x1800304e5  mov     r9, rbx
0x1800304e8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800304ed  mov     r15, rbx
0x1800304f0  mov     [rsp+130h+var_100], edi
0x1800304f4  mov     rax, [r13+0]
0x1800304f8  lea     r9, [rsp+130h+var_100]
0x1800304fd  xor     r8d, r8d
0x180030500  lea     rdx, aSidstate; "SidState"
0x180030507  mov     rcx, r13
0x18003050a  mov     rax, [rax+40h]
0x18003050e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030513  test    eax, eax
0x180030515  jns     short loc_180030535
0x180030517  mov     dword ptr [rsp+130h+var_110], eax
0x18003051b  mov     r9, rsi
0x18003051e  mov     r8d, 274h
0x180030524  lea     rdx, aWindowsCompatI_38; "Windows::Compat::Inventory::MareApplica"...
0x18003052b  mov     ecx, 1
0x180030530  call    AslLogCallPrintf
0x180030535  mov     ecx, [rsp+130h+var_100]
0x180030539  mov     eax, 2
0x18003053e  mul     rcx
0x180030541  mov     rdi, rax
0x180030544  cmovb   rdi, r14
0x180030548  mov     rcx, rdi; unsigned __int64
0x18003054b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180030550  mov     rbx, rax
0x180030553  mov     r8, rdi; Size
0x180030556  xor     edx, edx; Val
0x180030558  mov     rcx, rax; void *
0x18003055b  call    memset_0
0x180030560  mov     [rsp+130h+var_D0], rbx
0x180030565  xor     edi, edi
0x180030567  test    r15, r15
0x18003056a  jz      short loc_180030574
0x18003056c  mov     rcx, r15; void *
0x18003056f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030574  mov     rax, [r13+0]
0x180030578  lea     r9, [rsp+130h+var_100]
0x18003057d  mov     r8, rbx
0x180030580  lea     rdx, aSidstate; "SidState"
0x180030587  mov     rcx, r13
0x18003058a  mov     rax, [rax+40h]
0x18003058e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030593  mov     r15d, eax
0x180030596  test    eax, eax
0x180030598  jns     short loc_1800305A8
0x18003059a  mov     r9, rsi
0x18003059d  mov     r8d, 27Ah
0x1800305a3  jmp     loc_180030370
0x1800305a8  inc     r14
0x1800305ab  cmp     [rbx+r14*2], di
0x1800305b0  jnz     short loc_1800305A8
0x1800305b2  cmp     r14, [rbp+30h+var_70]
0x1800305b6  ja      short loc_1800305E6
0x1800305b8  lea     rsi, [rbp+30h+var_88]
0x1800305bc  cmp     [rbp+30h+var_70], 7
0x1800305c1  cmova   rsi, [rbp+30h+var_88]
0x1800305c6  mov     [rbp+30h+var_78], r14
0x1800305ca  lea     rdi, [r14+r14]
0x1800305ce  mov     r8, rdi; Size
0x1800305d1  mov     rdx, rbx; Src
0x1800305d4  mov     rcx, rsi; void *
0x1800305d7  call    memmove_0
0x1800305dc  xor     r14d, r14d
0x1800305df  mov     [rdi+rsi], r14w
0x1800305e4  jmp     short loc_1800305F8
0x1800305e6  mov     r9, rbx
0x1800305e9  mov     rdx, r14
0x1800305ec  lea     rcx, [rbp+30h+var_88]
0x1800305f0  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800305f5  xor     r14d, r14d
0x1800305f8  lea     rdx, [rbp+30h+var_88]
0x1800305fc  lea     rcx, [rbp+30h+var_48]
0x180030600  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180030605  mov     r8d, 7Ch ; '|'
0x18003060b  mov     rdx, rax
0x18003060e  lea     rcx, [rsp+130h+var_C0]
0x180030613  call    ?SplitString@Inventory@Compat@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@G@Z; Windows::Compat::Inventory::SplitString(std::wstring,ushort)
0x180030618  mov     rsi, rax
0x18003061b  lea     rax, [rsp+130h+var_F0]
0x180030620  cmp     rax, rsi
0x180030623  jz      short loc_180030656
0x180030625  lea     rcx, [rsp+130h+var_F0]
0x18003062a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18003062f  mov     rdi, [rsi]
0x180030632  mov     qword ptr [rsp+130h+var_F0], rdi
0x180030637  mov     r13, [rsi+8]
0x18003063b  mov     qword ptr [rsp+130h+var_F0+8], r13
0x180030640  mov     rcx, [rsi+10h]
0x180030644  mov     [rsp+130h+var_E0], rcx
0x180030649  mov     [rsi], r14
0x18003064c  mov     [rsi+8], r14
0x180030650  mov     [rsi+10h], r14
0x180030654  jmp     short loc_180030660
0x180030656  mov     r13, qword ptr [rsp+130h+var_F0+8]
0x18003065b  mov     rdi, qword ptr [rsp+130h+var_F0]
0x180030660  lea     rcx, [rsp+130h+var_C0]
0x180030665  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18003066a  jmp     loc_1800307C5
0x18003066f  mov     rdx, rdi
0x180030672  lea     rcx, [rbp+30h+var_68]
0x180030676  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003067b  nop
0x18003067c  lea     rdx, [rbp+30h+var_68]
0x180030680  lea     rcx, [rbp+30h+var_A8]
0x180030684  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180030689  mov     r8d, 3Ah ; ':'
0x18003068f  mov     rdx, rax
0x180030692  lea     rcx, [rsp+130h+var_C0]
0x180030697  call    ?SplitString@Inventory@Compat@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@G@Z; Windows::Compat::Inventory::SplitString(std::wstring,ushort)
0x18003069c  nop
0x18003069d  mov     rax, [rsp+130h+var_B8]
0x1800306a2  mov     rdx, [rsp+130h+var_C0]
0x1800306a7  sub     rax, rdx
0x1800306aa  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800306ae  cmp     rax, 40h ; '@'
0x1800306b2  jz      short loc_1800306F2
0x1800306b4  lea     rax, [rbp+30h+var_68]
0x1800306b8  cmp     [rbp+30h+var_50], 7
0x1800306bd  cmova   rax, [rbp+30h+var_68]
0x1800306c2  mov     [rsp+130h+var_108], 8000FFFFh
0x1800306ca  mov     [rsp+130h+var_110], rax
0x1800306cf  lea     r9, aUnexpectedSids; "Unexpected sidStatePair \"%ls\" [%#x]"
0x1800306d6  mov     r8d, 286h
0x1800306dc  lea     rdx, aWindowsCompatI_38; "Windows::Compat::Inventory::MareApplica"...
0x1800306e3  mov     ecx, 1
0x1800306e8  call    AslLogCallPrintf
0x1800306ed  jmp     loc_1800307AD
0x1800306f2  lea     rcx, [rbp+30h+var_48]
0x1800306f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800306fb  nop
0x1800306fc  mov     rax, [rsp+130h+var_B8]
0x180030701  mov     rsi, [rsp+130h+var_C0]
0x180030706  sub     rax, rsi
0x180030709  sar     rax, 5
0x18003070d  cmp     rax, 1
0x180030711  jbe     loc_1800307EF
0x180030717  add     rsi, 20h ; ' '
0x18003071b  call    cs:__imp__o__errno
0x180030721  mov     r14, rax
0x180030724  cmp     qword ptr [rsi+18h], 7
0x180030729  jbe     short loc_18003072E
0x18003072b  mov     rsi, [rsi]
0x18003072e  xor     eax, eax
0x180030730  mov     [rsp+130h+EndPtr], rax
0x180030735  mov     [r14], eax
0x180030738  lea     r8d, [rax+0Ah]; Radix
0x18003073c  lea     rdx, [rsp+130h+EndPtr]; EndPtr
0x180030741  mov     rcx, rsi; String
0x180030744  call    cs:__imp_wcstol
0x18003074a  mov     [rsp+130h+var_FC], eax
0x18003074e  cmp     rsi, [rsp+130h+EndPtr]
0x180030753  jz      loc_1800307E1
0x180030759  cmp     dword ptr [r14], 22h ; '"'
0x18003075d  jz      short loc_1800307D3
0x18003075f  mov     [rsp+130h+var_D8], eax
0x180030763  mov     rsi, [rsp+130h+var_C8]
0x180030768  mov     r14, [rsi+50h]
0x18003076c  cmp     r14, [rsi+58h]
0x180030770  jz      short loc_18003078D
0x180030772  lea     rdx, [rbp+30h+var_48]
0x180030776  mov     rcx, r14
0x180030779  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003077e  mov     eax, [rsp+130h+var_FC]
  ... truncated ...
```
