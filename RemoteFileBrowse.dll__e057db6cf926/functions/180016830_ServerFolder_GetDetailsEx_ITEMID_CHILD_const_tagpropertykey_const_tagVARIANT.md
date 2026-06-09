# ServerFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x180016830`
- end: `0x180016b97`
- name: `?GetDetailsEx@ServerFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(ServerFolder *this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002030`
- `0x18000591c`
- `0x180006870`
- `0x1800070cc`
- `0x180016830`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180016942`
- `OLEAUT32!__imp_SysAllocString` at `0x1800169bb`
- `OLEAUT32!__imp_SysAllocString` at `0x180016a34`
- `OLEAUT32!__imp_SysAllocString` at `0x180016aad`
- `OLEAUT32!__imp_SysAllocString` at `0x180016942`
- `OLEAUT32!__imp_SysAllocString` at `0x1800169bb`
- `OLEAUT32!__imp_SysAllocString` at `0x180016a34`
- `OLEAUT32!__imp_SysAllocString` at `0x180016aad`
- `OLEAUT32!__imp_VariantInit` at `0x180016958`
- `OLEAUT32!__imp_VariantInit` at `0x1800169d1`
- `OLEAUT32!__imp_VariantInit` at `0x180016a4a`
- `OLEAUT32!__imp_VariantInit` at `0x180016abf`
- `OLEAUT32!__imp_VariantInit` at `0x180016958`
- `OLEAUT32!__imp_VariantInit` at `0x1800169d1`
- `OLEAUT32!__imp_VariantInit` at `0x180016a4a`
- `OLEAUT32!__imp_VariantInit` at `0x180016abf`

## string_xrefs

- `0x180016a2d`: `prop:*System.PercentFull;System.Computer.DecoratedFreeSpace;System.Volume.FileSystem;`

## pseudocode

```c
__int64 __fastcall ServerFolder::GetDetailsEx(
        ServerFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  DWORD pid; // ecx
  BSTR v7; // rax
  BSTR v9; // rax
  BSTR v10; // rax
  BSTR v11; // rax
  int v12; // [rsp+20h] [rbp-38h]
  _OWORD v13[2]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a2 && a3 && a4 )
  {
    if ( *(_WORD *)a2 && *(_DWORD *)((char *)a2 + 2) == 1 )
    {
      v13[0] = 0;
      v13[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v13[0]) = 0;
      RfbPidlHelper<ServerFixedData>::GetStringData(a2, v13);
      pid = a3->pid;
      if ( pid == PKEY_Volume_IsRoot.pid
        && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Volume_IsRoot.fmtid.Data1
        && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_Volume_IsRoot.fmtid.Data4 )
      {
        a4->vt = 11;
        a4->iVal = -1;
LABEL_34:
        std::wstring::~wstring((char **)v13);
        return 0;
      }
      if ( pid == PKEY_PerceivedType.pid
        && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PerceivedType.fmtid.Data1
        && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PerceivedType.fmtid.Data4 )
      {
        a4->vt = 3;
        a4->lVal = -1;
        goto LABEL_34;
      }
      if ( pid == PKEY_PropList_PreviewTitle.pid
        && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewTitle.fmtid.Data1
        && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_PreviewTitle.fmtid.Data4 )
      {
        a4->vt = 8;
        v7 = SysAllocString(L"prop:System.DisplayName;");
        a4->llVal = (LONGLONG)v7;
        if ( !v7 )
        {
          VariantInit(a4);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x142,
            (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\serverfolder.cpp",
            (const char *)0x8007000ELL,
            v12);
          std::wstring::~wstring((char **)v13);
          return 2147942414LL;
        }
        goto LABEL_34;
      }
      if ( pid == PKEY_PropList_PreviewDetails.pid
        && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1
        && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4 )
      {
        a4->vt = 8;
        v9 = SysAllocString(L"prop:*System.PercentFull;System.FreeSpace;System.Capacity;System.Volume.FileSystem;");
        a4->llVal = (LONGLONG)v9;
        if ( !v9 )
        {
          VariantInit(a4);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14C,
            (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\serverfolder.cpp",
            (const char *)0x8007000ELL,
            v12);
          std::wstring::~wstring((char **)v13);
          return 2147942414LL;
        }
        goto LABEL_34;
      }
      if ( pid == PKEY_PropList_TileInfo.pid
        && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_TileInfo.fmtid.Data1
        && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_TileInfo.fmtid.Data4 )
      {
        a4->vt = 8;
        v10 = SysAllocString(L"prop:*System.PercentFull;System.Computer.DecoratedFreeSpace;System.Volume.FileSystem;");
        a4->llVal = (LONGLONG)v10;
        if ( !v10 )
        {
          VariantInit(a4);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x155,
            (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\serverfolder.cpp",
            (const char *)0x8007000ELL,
            v12);
          std::wstring::~wstring((char **)v13);
          return 2147942414LL;
        }
        goto LABEL_34;
      }
      if ( pid == PKEY_PropList_InfoTip.pid
        && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_InfoTip.fmtid.Data1
        && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_InfoTip.fmtid.Data4 )
      {
        a4->vt = 8;
        v11 = SysAllocString(L"prop:System.FreeSpace;System.Capacity;");
        a4->llVal = (LONGLONG)v11;
        if ( !v11 )
        {
          VariantInit(a4);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15D,
            (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\serverfolder.cpp",
            (const char *)0x8007000ELL,
            v12);
          std::wstring::~wstring((char **)v13);
          return 2147942414LL;
        }
        goto LABEL_34;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\serverfolder.cpp",
        (const char *)0x80004001LL,
        v12);
      std::wstring::~wstring((char **)v13);
      return 2147500033LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\serverfolder.cpp",
        (const char *)0x80070057LL,
        v12);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\serverfolder.cpp",
      (const char *)0x80070057LL,
      v12);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180016830  mov     [rsp+arg_0], rbx
0x180016835  mov     [rsp+arg_10], rsi
0x18001683a  push    rdi
0x18001683b  sub     rsp, 50h
0x18001683f  mov     rax, cs:__security_cookie
0x180016846  xor     rax, rsp
0x180016849  mov     [rsp+58h+var_10], rax
0x18001684e  mov     rbx, r9
0x180016851  mov     rdi, r8
0x180016854  mov     r8, rdx
0x180016857  xor     esi, esi
0x180016859  test    rdx, rdx
0x18001685c  jz      loc_180016B59
0x180016862  test    rdi, rdi
0x180016865  jz      loc_180016B59
0x18001686b  test    rbx, rbx
0x18001686e  jz      loc_180016B59
0x180016874  cmp     [rdx], si
0x180016877  jz      loc_180016B31
0x18001687d  cmp     dword ptr [rdx+2], 1
0x180016881  jnz     loc_180016B31
0x180016887  xorps   xmm0, xmm0
0x18001688a  movups  [rsp+58h+var_30], xmm0
0x18001688f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180016897  movdqu  [rsp+58h+var_20], xmm1
0x18001689d  mov     word ptr [rsp+58h+var_30], si
0x1800168a2  lea     rdx, [rsp+58h+var_30]
0x1800168a7  mov     rcx, r8
0x1800168aa  call    ?GetStringData@?$RfbPidlHelper@UServerFixedData@@@@SAXPEFBU_ITEMIDLIST@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbPidlHelper<ServerFixedData>::GetStringData(_ITEMIDLIST const *,std::wstring &)
0x1800168af  mov     ecx, [rdi+10h]
0x1800168b2  cmp     ecx, cs:PKEY_Volume_IsRoot.pid
0x1800168b8  jnz     short loc_1800168E3
0x1800168ba  mov     rax, [rdi]
0x1800168bd  cmp     rax, qword ptr cs:PKEY_Volume_IsRoot.fmtid.Data1
0x1800168c4  jnz     short loc_1800168E3
0x1800168c6  mov     rax, [rdi+8]
0x1800168ca  cmp     rax, qword ptr cs:PKEY_Volume_IsRoot.fmtid.Data4
0x1800168d1  jnz     short loc_1800168E3
0x1800168d3  mov     word ptr [rbx], 0Bh
0x1800168d8  mov     word ptr [rbx+8], 0FFFFh
0x1800168de  jmp     loc_180016AF5
0x1800168e3  cmp     ecx, cs:PKEY_PerceivedType.pid
0x1800168e9  jnz     short loc_180016915
0x1800168eb  mov     rax, [rdi]
0x1800168ee  cmp     rax, qword ptr cs:PKEY_PerceivedType.fmtid.Data1
0x1800168f5  jnz     short loc_180016915
0x1800168f7  mov     rax, [rdi+8]
0x1800168fb  cmp     rax, qword ptr cs:PKEY_PerceivedType.fmtid.Data4
0x180016902  jnz     short loc_180016915
0x180016904  mov     word ptr [rbx], 3
0x180016909  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x180016910  jmp     loc_180016AF5
0x180016915  cmp     ecx, cs:PKEY_PropList_PreviewTitle.pid
0x18001691b  jnz     short loc_18001698E
0x18001691d  mov     rax, [rdi]
0x180016920  cmp     rax, qword ptr cs:PKEY_PropList_PreviewTitle.fmtid.Data1
0x180016927  jnz     short loc_18001698E
0x180016929  mov     rax, [rdi+8]
0x18001692d  cmp     rax, qword ptr cs:PKEY_PropList_PreviewTitle.fmtid.Data4
0x180016934  jnz     short loc_18001698E
0x180016936  mov     word ptr [rbx], 8
0x18001693b  lea     rcx, psz; "prop:System.DisplayName;"
0x180016942  call    cs:__imp_SysAllocString
0x180016948  mov     [rbx+8], rax
0x18001694c  test    rax, rax
0x18001694f  jnz     loc_180016AF5
0x180016955  mov     rcx, rbx; pvarg
0x180016958  call    cs:__imp_VariantInit
0x18001695e  mov     rcx, [rsp+58h]; this
0x180016963  mov     ebx, 8007000Eh
0x180016968  mov     r9d, ebx; char *
0x18001696b  lea     r8, aVmUxUiRemotefi_6; "vm\\ux\\ui\\remotefilebrowse\\serverfol"...
0x180016972  mov     edx, 142h; void *
0x180016977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001697c  nop
0x18001697d  lea     rcx, [rsp+58h+var_30]
0x180016982  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016987  mov     eax, ebx
0x180016989  jmp     loc_180016B79
0x18001698e  cmp     ecx, cs:PKEY_PropList_PreviewDetails.pid
0x180016994  jnz     short loc_180016A07
0x180016996  mov     rax, [rdi]
0x180016999  cmp     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data1
0x1800169a0  jnz     short loc_180016A07
0x1800169a2  mov     rax, [rdi+8]
0x1800169a6  cmp     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data4
0x1800169ad  jnz     short loc_180016A07
0x1800169af  mov     word ptr [rbx], 8
0x1800169b4  lea     rcx, aPropSystemPerc; "prop:*System.PercentFull;System.FreeSpa"...
0x1800169bb  call    cs:__imp_SysAllocString
0x1800169c1  mov     [rbx+8], rax
0x1800169c5  test    rax, rax
0x1800169c8  jnz     loc_180016AF5
0x1800169ce  mov     rcx, rbx; pvarg
0x1800169d1  call    cs:__imp_VariantInit
0x1800169d7  mov     rcx, [rsp+58h]; this
0x1800169dc  mov     ebx, 8007000Eh
0x1800169e1  mov     r9d, ebx; char *
0x1800169e4  lea     r8, aVmUxUiRemotefi_6; "vm\\ux\\ui\\remotefilebrowse\\serverfol"...
0x1800169eb  mov     edx, 14Ch; void *
0x1800169f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800169f5  nop
0x1800169f6  lea     rcx, [rsp+58h+var_30]
0x1800169fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016a00  mov     eax, ebx
0x180016a02  jmp     loc_180016B79
0x180016a07  cmp     ecx, cs:PKEY_PropList_TileInfo.pid
0x180016a0d  jnz     short loc_180016A80
0x180016a0f  mov     rax, [rdi]
0x180016a12  cmp     rax, qword ptr cs:PKEY_PropList_TileInfo.fmtid.Data1
0x180016a19  jnz     short loc_180016A80
0x180016a1b  mov     rax, [rdi+8]
0x180016a1f  cmp     rax, qword ptr cs:PKEY_PropList_TileInfo.fmtid.Data4
0x180016a26  jnz     short loc_180016A80
0x180016a28  mov     word ptr [rbx], 8
0x180016a2d  lea     rcx, aPropSystemPerc_0; "prop:*System.PercentFull;System.Compute"...
0x180016a34  call    cs:__imp_SysAllocString
0x180016a3a  mov     [rbx+8], rax
0x180016a3e  test    rax, rax
0x180016a41  jnz     loc_180016AF5
0x180016a47  mov     rcx, rbx; pvarg
0x180016a4a  call    cs:__imp_VariantInit
0x180016a50  mov     rcx, [rsp+58h]; this
0x180016a55  mov     ebx, 8007000Eh
0x180016a5a  mov     r9d, ebx; char *
0x180016a5d  lea     r8, aVmUxUiRemotefi_6; "vm\\ux\\ui\\remotefilebrowse\\serverfol"...
0x180016a64  mov     edx, 155h; void *
0x180016a69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a6e  nop
0x180016a6f  lea     rcx, [rsp+58h+var_30]
0x180016a74  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016a79  mov     eax, ebx
0x180016a7b  jmp     loc_180016B79
0x180016a80  cmp     ecx, cs:PKEY_PropList_InfoTip.pid
0x180016a86  jnz     short loc_180016B04
0x180016a88  mov     rax, [rdi]
0x180016a8b  cmp     rax, qword ptr cs:PKEY_PropList_InfoTip.fmtid.Data1
0x180016a92  jnz     short loc_180016B04
0x180016a94  mov     rax, [rdi+8]
0x180016a98  cmp     rax, qword ptr cs:PKEY_PropList_InfoTip.fmtid.Data4
0x180016a9f  jnz     short loc_180016B04
0x180016aa1  mov     word ptr [rbx], 8
0x180016aa6  lea     rcx, aPropSystemFree; "prop:System.FreeSpace;System.Capacity;"
0x180016aad  call    cs:__imp_SysAllocString
0x180016ab3  mov     [rbx+8], rax
0x180016ab7  test    rax, rax
0x180016aba  jnz     short loc_180016AF5
0x180016abc  mov     rcx, rbx; pvarg
0x180016abf  call    cs:__imp_VariantInit
0x180016ac5  mov     rcx, [rsp+58h]; this
0x180016aca  mov     ebx, 8007000Eh
0x180016acf  mov     r9d, ebx; char *
0x180016ad2  lea     r8, aVmUxUiRemotefi_6; "vm\\ux\\ui\\remotefilebrowse\\serverfol"...
0x180016ad9  mov     edx, 15Dh; void *
0x180016ade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016ae3  nop
0x180016ae4  lea     rcx, [rsp+58h+var_30]
0x180016ae9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016aee  mov     eax, ebx
0x180016af0  jmp     loc_180016B79
0x180016af5  lea     rcx, [rsp+58h+var_30]
0x180016afa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016aff  nop
0x180016b00  xor     eax, eax
0x180016b02  jmp     short loc_180016B79
0x180016b04  mov     rcx, [rsp+58h]; this
0x180016b09  mov     ebx, 80004001h
0x180016b0e  mov     r9d, ebx; char *
0x180016b11  lea     r8, aVmUxUiRemotefi_6; "vm\\ux\\ui\\remotefilebrowse\\serverfol"...
0x180016b18  mov     edx, 161h; void *
0x180016b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b22  nop
0x180016b23  lea     rcx, [rsp+58h+var_30]
0x180016b28  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016b2d  mov     eax, ebx
0x180016b2f  jmp     short loc_180016B79
0x180016b31  mov     rcx, [rsp+58h]; this
0x180016b36  mov     ebx, 80070057h
0x180016b3b  mov     r9d, ebx; char *
0x180016b3e  lea     r8, aVmUxUiRemotefi_6; "vm\\ux\\ui\\remotefilebrowse\\serverfol"...
0x180016b45  mov     edx, 166h; void *
0x180016b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b4f  mov     eax, ebx
0x180016b51  jmp     short loc_180016B79
0x180016b53  mov     eax, [rsp+58h+var_38]
0x180016b57  jmp     short loc_180016B79
0x180016b59  mov     rcx, [rsp+58h]; this
0x180016b5e  mov     ebx, 80070057h
0x180016b63  mov     r9d, ebx; char *
0x180016b66  lea     r8, aVmUxUiRemotefi_6; "vm\\ux\\ui\\remotefilebrowse\\serverfol"...
0x180016b6d  mov     edx, 129h; void *
0x180016b72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b77  mov     eax, ebx
0x180016b79  mov     rcx, [rsp+58h+var_10]
0x180016b7e  xor     rcx, rsp; StackCookie
0x180016b81  call    __security_check_cookie
0x180016b86  mov     rbx, [rsp+58h+arg_0]
0x180016b8b  mov     rsi, [rsp+58h+arg_10]
0x180016b90  add     rsp, 50h
0x180016b94  pop     rdi
0x180016b95  retn
```
