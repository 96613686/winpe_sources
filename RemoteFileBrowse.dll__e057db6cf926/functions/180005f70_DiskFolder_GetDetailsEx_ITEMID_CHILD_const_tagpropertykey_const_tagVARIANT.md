# DiskFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x180005f70`
- end: `0x18000667e`
- name: `?GetDetailsEx@DiskFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `1806`
- prototype: `__int64 __fastcall(DiskFolder *this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002030`
- `0x1800056e0`
- `0x18000591c`
- `0x180005f70`
- `0x1800070cc`
- `0x1800070f0`
- `0x180007150`
- `0x18001724c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000626a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800063d0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000644c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800064c8`
- `OLEAUT32!__imp_SysAllocString` at `0x180006548`
- `OLEAUT32!__imp_SysAllocString` at `0x18000626a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800063d0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000644c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800064c8`
- `OLEAUT32!__imp_SysAllocString` at `0x180006548`
- `OLEAUT32!__imp_VariantInit` at `0x180005fb9`
- `OLEAUT32!__imp_VariantInit` at `0x180006284`
- `OLEAUT32!__imp_VariantInit` at `0x1800063e6`
- `OLEAUT32!__imp_VariantInit` at `0x180006462`
- `OLEAUT32!__imp_VariantInit` at `0x1800064de`
- `OLEAUT32!__imp_VariantInit` at `0x18000655a`
- `OLEAUT32!__imp_VariantInit` at `0x180005fb9`
- `OLEAUT32!__imp_VariantInit` at `0x180006284`
- `OLEAUT32!__imp_VariantInit` at `0x1800063e6`
- `OLEAUT32!__imp_VariantInit` at `0x180006462`
- `OLEAUT32!__imp_VariantInit` at `0x1800064de`
- `OLEAUT32!__imp_VariantInit` at `0x18000655a`
- `PROPSYS!InitVariantFromBuffer` at `0x180006050`
- `PROPSYS!InitVariantFromBuffer` at `0x180006050`
- `PROPSYS!InitVariantFromUInt64Array` at `0x1800061bd`
- `PROPSYS!InitVariantFromUInt64Array` at `0x1800061bd`

## string_xrefs

- `0x1800064c1`: `prop:*System.PercentFull;System.Computer.DecoratedFreeSpace;System.Volume.FileSystem;`

## pseudocode

```c
__int64 __fastcall DiskFolder::GetDetailsEx(
        DiskFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  int v7; // eax
  int v8; // eax
  unsigned __int64 v9; // r8
  LONGLONG v10; // r9
  unsigned __int32 v11; // r10d
  char v12; // dl
  DWORD pid; // ecx
  HRESULT inited; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  __int64 result; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // r8
  HRESULT v20; // eax
  unsigned int v21; // ebx
  __m256i *p_pv; // rbx
  BSTR v23; // rax
  unsigned int v24; // ebx
  BSTR v25; // rax
  BSTR v26; // rax
  BSTR v27; // rax
  BSTR v28; // rax
  unsigned int v29; // eax
  int v30; // [rsp+20h] [rbp-78h]
  char *v31; // [rsp+28h] [rbp-70h]
  __m256i pv; // [rsp+38h] [rbp-60h] BYREF
  _OWORD v33[2]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    if ( a2 && a3 && a4 )
    {
      VariantInit(a4);
      v7 = 4;
      if ( *(_WORD *)a2 && (v7 = *(_DWORD *)((char *)a2 + 2), v7 == 1) )
      {
        if ( *(_WORD *)a2 < 0x32u )
        {
          v29 = wil::verify_hresult<long>(0x80070057);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x118,
            (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\Utility.h",
            (const char *)v29,
            v30);
        }
        v8 = *(_DWORD *)((char *)a2 + 6);
        v9 = *(_QWORD *)((char *)a2 + 18);
        v10 = *(_QWORD *)((char *)a2 + 26);
        v11 = *(_DWORD *)((char *)a2 + 38);
        v12 = *((_BYTE *)a2 + 44);
        v33[0] = 0;
        v33[1] = _mm_load_si128((const __m128i *)&_xmm);
        LODWORD(v33[0]) = v8;
        WORD2(v33[0]) = 0;
        pid = a3->pid;
        if ( pid == PKEY_DescriptionID.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DescriptionID.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_DescriptionID.fmtid.Data4 )
        {
          *(_OWORD *)((char *)pv.m256i_i64 + 4) = 0;
          pv.m256i_i32[0] = v11;
          inited = InitVariantFromBuffer(&pv, 0x14u, a4);
          v15 = inited;
          if ( inited < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x178,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
              (const char *)(unsigned int)inited,
              v30);
            std::wstring::~wstring((char **)v33);
            return v15;
          }
          goto LABEL_82;
        }
        if ( pid == PKEY_Capacity.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Capacity.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_Capacity.fmtid.Data4 )
        {
          if ( v9 )
          {
            a4->vt = 21;
            a4->llVal = v9;
          }
          goto LABEL_82;
        }
        if ( pid == PKEY_FreeSpace.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FreeSpace.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_FreeSpace.fmtid.Data4 )
        {
          if ( v9 )
          {
            a4->vt = 21;
            a4->llVal = v10;
          }
          goto LABEL_82;
        }
        if ( pid == PKEY_PercentFull.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PercentFull.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PercentFull.fmtid.Data4 )
        {
          if ( v10 )
          {
            LODWORD(v18) = 100;
            if ( v9 )
            {
              v19 = 1000 * (v9 - v10) / v9;
              v18 = v19 / 0xA;
              if ( (unsigned int)(v19 / 0xA) < 0x63 && v19 % 0xA >= 5 )
                LODWORD(v18) = v18 + 1;
            }
            a4->vt = 19;
            a4->lVal = v18;
          }
          goto LABEL_82;
        }
        if ( pid == PKEY_Computer_DecoratedFreeSpace.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Computer_DecoratedFreeSpace.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_Computer_DecoratedFreeSpace.fmtid.Data4 )
        {
          if ( v9 )
          {
            pv.m256i_i64[0] = v10;
            pv.m256i_i64[1] = v9;
            v20 = InitVariantFromUInt64Array((const ULONGLONG *)&pv, 2u, a4);
            v21 = v20;
            if ( v20 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A5,
                (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
                (const char *)(unsigned int)v20,
                v30);
              std::wstring::~wstring((char **)v33);
              return v21;
            }
          }
          goto LABEL_82;
        }
        if ( pid == PKEY_ItemTypeText.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_ItemTypeText.fmtid.Data4 )
        {
          *(_OWORD *)pv.m256i_i8 = 0;
          *(__m128i *)&pv.m256i_u64[2] = _mm_load_si128((const __m128i *)&_xmm);
          pv.m256i_i16[0] = 0;
          DiskDataHelper::GetDriveTypeString(v11, *(unsigned int *)((char *)a2 + 34), &pv);
          p_pv = &pv;
          if ( pv.m256i_i64[3] > 7uLL )
            p_pv = (__m256i *)pv.m256i_i64[0];
          a4->vt = 8;
          v23 = SysAllocString((const OLECHAR *)p_pv);
          a4->llVal = (LONGLONG)v23;
          if ( !v23 )
          {
            v24 = p_pv != 0 ? 0xFFFFFFB7 : 0;
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1AF,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
              (const char *)(v24 - 2147024809),
              v30);
            std::wstring::~wstring((char **)&pv);
            std::wstring::~wstring((char **)v33);
            return v24 - 2147024809;
          }
          std::wstring::~wstring((char **)&pv);
          goto LABEL_82;
        }
        if ( pid == PKEY_Volume_IsRoot.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Volume_IsRoot.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_Volume_IsRoot.fmtid.Data4 )
        {
          a4->vt = 11;
          a4->iVal = -1;
LABEL_82:
          std::wstring::~wstring((char **)v33);
          return 0;
        }
        if ( pid == PKEY_SFGAOFlags.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_SFGAOFlags.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_SFGAOFlags.fmtid.Data4 )
        {
          a4->vt = 3;
          a4->lVal = 537133056;
          goto LABEL_82;
        }
        if ( pid == PKEY_Volume_IsMappedDrive.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Volume_IsMappedDrive.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_Volume_IsMappedDrive.fmtid.Data4 )
        {
          a4->vt = 11;
          a4->iVal = -(v12 != 0);
          goto LABEL_82;
        }
        if ( pid == PKEY_PerceivedType.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PerceivedType.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PerceivedType.fmtid.Data4 )
        {
          a4->vt = 3;
          a4->lVal = -1;
          goto LABEL_82;
        }
        if ( pid == PKEY_PropList_PreviewTitle.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewTitle.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_PreviewTitle.fmtid.Data4 )
        {
          a4->vt = 8;
          v25 = SysAllocString(L"prop:System.DisplayName;");
          a4->llVal = (LONGLONG)v25;
          if ( !v25 )
          {
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C5,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
              (const char *)0x8007000ELL,
              v30);
            std::wstring::~wstring((char **)v33);
            return 2147942414LL;
          }
          goto LABEL_82;
        }
        if ( pid == PKEY_PropList_PreviewDetails.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4 )
        {
          a4->vt = 8;
          v26 = SysAllocString(L"prop:*System.PercentFull;System.FreeSpace;System.Capacity;System.Volume.FileSystem;");
          a4->llVal = (LONGLONG)v26;
          if ( !v26 )
          {
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1CE,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
              (const char *)0x8007000ELL,
              v30);
            std::wstring::~wstring((char **)v33);
            return 2147942414LL;
          }
          goto LABEL_82;
        }
        if ( pid == PKEY_PropList_TileInfo.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_TileInfo.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_TileInfo.fmtid.Data4 )
        {
          a4->vt = 8;
          v27 = SysAllocString(L"prop:*System.PercentFull;System.Computer.DecoratedFreeSpace;System.Volume.FileSystem;");
          a4->llVal = (LONGLONG)v27;
          if ( !v27 )
          {
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D6,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
              (const char *)0x8007000ELL,
              v30);
            std::wstring::~wstring((char **)v33);
            return 2147942414LL;
          }
          goto LABEL_82;
        }
        if ( pid == PKEY_PropList_InfoTip.pid
          && *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_InfoTip.fmtid.Data1
          && *(_QWORD *)a3->fmtid.Data4 == *(_QWORD *)PKEY_PropList_InfoTip.fmtid.Data4 )
        {
          a4->vt = 8;
          v28 = SysAllocString(L"prop:System.FreeSpace;System.Capacity;");
          a4->llVal = (LONGLONG)v28;
          if ( !v28 )
          {
            VariantInit(a4);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DD,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
              (const char *)0x8007000ELL,
              v30);
            std::wstring::~wstring((char **)v33);
            return 2147942414LL;
          }
          goto LABEL_82;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E1,
          (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
          (const char *)0x80004001LL,
          v30);
        std::wstring::~wstring((char **)v33);
        result = 2147500033LL;
      }
      else
      {
        LODWORD(v31) = v7;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1E6,
          (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
          (const char *)0x80070057LL,
          (int)"unknown PIDL type %u",
          v31);
        result = 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x164,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
        (const char *)0x80070057LL,
        v30);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1E9,
                           (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180005f70  mov     [rsp+arg_0], rbx
0x180005f75  push    rsi
0x180005f76  push    rdi
0x180005f77  push    r14
0x180005f79  sub     rsp, 80h
0x180005f80  mov     rax, cs:__security_cookie
0x180005f87  xor     rax, rsp
0x180005f8a  mov     [rsp+98h+var_20], rax
0x180005f8f  mov     rdi, r9
0x180005f92  mov     rbx, r8
0x180005f95  mov     rsi, rdx
0x180005f98  xor     r14d, r14d
0x180005f9b  test    rdx, rdx
0x180005f9e  jz      loc_180006611
0x180005fa4  test    rbx, rbx
0x180005fa7  jz      loc_180006611
0x180005fad  test    r9, r9
0x180005fb0  jz      loc_180006611
0x180005fb6  mov     rcx, r9; pvarg
0x180005fb9  call    cs:__imp_VariantInit
0x180005fbf  lea     eax, [r14+4]
0x180005fc3  cmp     [rsi], r14w
0x180005fc7  jz      loc_1800065D5
0x180005fcd  mov     eax, [rsi+2]
0x180005fd0  cmp     eax, 1
0x180005fd3  jnz     loc_1800065D5
0x180005fd9  cmp     word ptr [rsi], 32h ; '2'
0x180005fdd  jb      loc_180006656
0x180005fe3  mov     eax, [rsi+6]
0x180005fe6  mov     r8, [rsi+12h]
0x180005fea  mov     r9, [rsi+1Ah]
0x180005fee  mov     r10d, [rsi+26h]
0x180005ff2  mov     dl, [rsi+2Ch]
0x180005ff5  xorps   xmm0, xmm0
0x180005ff8  movups  [rsp+98h+var_40], xmm0
0x180005ffd  movdqa  xmm1, cs:__xmm@00000000000000070000000000000002
0x180006005  movdqu  [rsp+98h+var_30], xmm1
0x18000600b  mov     dword ptr [rsp+98h+var_40], eax
0x18000600f  mov     word ptr [rsp+98h+var_40+4], r14w
0x180006015  mov     ecx, [rbx+10h]
0x180006018  cmp     ecx, cs:PKEY_DescriptionID.pid
0x18000601e  jnz     short loc_18000608E
0x180006020  mov     rax, [rbx]
0x180006023  cmp     rax, qword ptr cs:PKEY_DescriptionID.fmtid.Data1
0x18000602a  jnz     short loc_18000608E
0x18000602c  mov     rax, [rbx+8]
0x180006030  cmp     rax, qword ptr cs:PKEY_DescriptionID.fmtid.Data4
0x180006037  jnz     short loc_18000608E
0x180006039  movdqu  [rsp+98h+pv+4], xmm0
0x18000603f  mov     dword ptr [rsp+98h+pv], r10d
0x180006044  mov     r8, rdi; pvar
0x180006047  lea     edx, [r14+14h]; cb
0x18000604b  lea     rcx, [rsp+98h+pv]; pv
0x180006050  call    cs:__imp_InitVariantFromBuffer
0x180006056  mov     ebx, eax
0x180006058  test    eax, eax
0x18000605a  jns     loc_180006593
0x180006060  mov     rcx, [rsp+98h]; this
0x180006068  mov     r9d, eax; char *
0x18000606b  lea     r8, aVmUxUiRemotefi_7; "vm\\ux\\ui\\remotefilebrowse\\diskfolde"...
0x180006072  mov     edx, 178h; void *
0x180006077  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000607c  nop
0x18000607d  lea     rcx, [rsp+98h+var_40]
0x180006082  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006087  mov     eax, ebx
0x180006089  jmp     loc_180006635
0x18000608e  cmp     ecx, cs:PKEY_Capacity.pid
0x180006094  jnz     short loc_1800060C6
0x180006096  mov     rax, [rbx]
0x180006099  cmp     rax, qword ptr cs:PKEY_Capacity.fmtid.Data1
0x1800060a0  jnz     short loc_1800060C6
0x1800060a2  mov     rax, [rbx+8]
0x1800060a6  cmp     rax, qword ptr cs:PKEY_Capacity.fmtid.Data4
0x1800060ad  jnz     short loc_1800060C6
0x1800060af  test    r8, r8
0x1800060b2  jz      loc_180006593
0x1800060b8  mov     word ptr [rdi], 15h
0x1800060bd  mov     [rdi+8], r8
0x1800060c1  jmp     loc_180006593
0x1800060c6  cmp     ecx, cs:PKEY_FreeSpace.pid
0x1800060cc  jnz     short loc_1800060FE
0x1800060ce  mov     rax, [rbx]
0x1800060d1  cmp     rax, qword ptr cs:PKEY_FreeSpace.fmtid.Data1
0x1800060d8  jnz     short loc_1800060FE
0x1800060da  mov     rax, [rbx+8]
0x1800060de  cmp     rax, qword ptr cs:PKEY_FreeSpace.fmtid.Data4
0x1800060e5  jnz     short loc_1800060FE
0x1800060e7  test    r8, r8
0x1800060ea  jz      loc_180006593
0x1800060f0  mov     word ptr [rdi], 15h
0x1800060f5  mov     [rdi+8], r9
0x1800060f9  jmp     loc_180006593
0x1800060fe  cmp     ecx, cs:PKEY_PercentFull.pid
0x180006104  jnz     short loc_18000617C
0x180006106  mov     rax, [rbx]
0x180006109  cmp     rax, qword ptr cs:PKEY_PercentFull.fmtid.Data1
0x180006110  jnz     short loc_18000617C
0x180006112  mov     rax, [rbx+8]
0x180006116  cmp     rax, qword ptr cs:PKEY_PercentFull.fmtid.Data4
0x18000611d  jnz     short loc_18000617C
0x18000611f  test    r9, r9
0x180006122  jz      loc_180006593
0x180006128  mov     edx, 64h ; 'd'
0x18000612d  test    r8, r8
0x180006130  jz      short loc_18000616F
0x180006132  mov     rax, r8
0x180006135  sub     rax, r9
0x180006138  imul    rax, 3E8h
0x18000613f  xor     edx, edx
0x180006141  div     r8
0x180006144  mov     r8, rax
0x180006147  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006151  mul     r8
0x180006154  shr     rdx, 3
0x180006158  cmp     edx, 63h ; 'c'
0x18000615b  jnb     short loc_18000616F
0x18000615d  lea     rcx, [rdx+rdx*4]
0x180006161  add     rcx, rcx
0x180006164  sub     r8, rcx
0x180006167  cmp     r8, 5
0x18000616b  jb      short loc_18000616F
0x18000616d  inc     edx
0x18000616f  mov     word ptr [rdi], 13h
0x180006174  mov     [rdi+8], edx
0x180006177  jmp     loc_180006593
0x18000617c  cmp     ecx, cs:PKEY_Computer_DecoratedFreeSpace.pid
0x180006182  jnz     short loc_1800061FB
0x180006184  mov     rax, [rbx]
0x180006187  cmp     rax, qword ptr cs:PKEY_Computer_DecoratedFreeSpace.fmtid.Data1
0x18000618e  jnz     short loc_1800061FB
0x180006190  mov     rax, [rbx+8]
0x180006194  cmp     rax, qword ptr cs:PKEY_Computer_DecoratedFreeSpace.fmtid.Data4
0x18000619b  jnz     short loc_1800061FB
0x18000619d  test    r8, r8
0x1800061a0  jz      loc_180006593
0x1800061a6  mov     qword ptr [rsp+98h+pv], r9
0x1800061ab  mov     qword ptr [rsp+98h+pv+8], r8
0x1800061b0  mov     r8, rdi; pvar
0x1800061b3  mov     edx, 2; cElems
0x1800061b8  lea     rcx, [rsp+98h+pv]; prgn
0x1800061bd  call    cs:__imp_InitVariantFromUInt64Array
0x1800061c3  mov     ebx, eax
0x1800061c5  test    eax, eax
0x1800061c7  jns     loc_180006593
0x1800061cd  mov     rcx, [rsp+98h]; this
0x1800061d5  mov     r9d, eax; char *
0x1800061d8  lea     r8, aVmUxUiRemotefi_7; "vm\\ux\\ui\\remotefilebrowse\\diskfolde"...
0x1800061df  mov     edx, 1A5h; void *
0x1800061e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061e9  nop
0x1800061ea  lea     rcx, [rsp+98h+var_40]
0x1800061ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800061f4  mov     eax, ebx
0x1800061f6  jmp     loc_180006635
0x1800061fb  cmp     ecx, cs:PKEY_ItemTypeText.pid
0x180006201  jnz     loc_1800062DA
0x180006207  mov     rax, [rbx]
0x18000620a  cmp     rax, qword ptr cs:PKEY_ItemTypeText.fmtid.Data1
0x180006211  jnz     loc_1800062DA
0x180006217  mov     rax, [rbx+8]
0x18000621b  cmp     rax, qword ptr cs:PKEY_ItemTypeText.fmtid.Data4
0x180006222  jnz     loc_1800062DA
0x180006228  movups  [rsp+98h+pv], xmm0
0x18000622d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180006235  movdqu  [rsp+98h+var_50], xmm1
0x18000623b  mov     word ptr [rsp+98h+pv], r14w
0x180006241  lea     r8, [rsp+98h+pv]
0x180006246  mov     edx, [rsi+22h]
0x180006249  mov     ecx, r10d
0x18000624c  call    ?GetDriveTypeString@DiskDataHelper@@SAXKHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DiskDataHelper::GetDriveTypeString(ulong,int,std::wstring &)
0x180006251  lea     rbx, [rsp+98h+pv]
0x180006256  cmp     qword ptr [rsp+98h+var_50+8], 7
0x18000625c  cmova   rbx, qword ptr [rsp+98h+pv]
0x180006262  mov     word ptr [rdi], 8
0x180006267  mov     rcx, rbx; psz
0x18000626a  call    cs:__imp_SysAllocString
0x180006270  mov     [rdi+8], rax
0x180006274  test    rax, rax
0x180006277  jnz     short loc_1800062CB
0x180006279  neg     rbx
0x18000627c  sbb     ebx, ebx
0x18000627e  and     ebx, 0FFFFFFB7h
0x180006281  mov     rcx, rdi; pvarg
0x180006284  call    cs:__imp_VariantInit
0x18000628a  mov     rcx, [rsp+98h]; this
0x180006292  lea     r9d, [rbx-7FF8FFA9h]; char *
0x180006299  lea     r8, aVmUxUiRemotefi_7; "vm\\ux\\ui\\remotefilebrowse\\diskfolde"...
0x1800062a0  mov     edx, 1AFh; void *
0x1800062a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062aa  nop
0x1800062ab  lea     rcx, [rsp+98h+pv]
0x1800062b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800062b5  nop
0x1800062b6  lea     rcx, [rsp+98h+var_40]
0x1800062bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800062c0  lea     eax, [rbx-7FF8FFA9h]
0x1800062c6  jmp     loc_180006635
0x1800062cb  lea     rcx, [rsp+98h+pv]
0x1800062d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800062d5  jmp     loc_180006593
0x1800062da  cmp     ecx, cs:PKEY_Volume_IsRoot.pid
0x1800062e0  jnz     short loc_18000630B
0x1800062e2  mov     rax, [rbx]
0x1800062e5  cmp     rax, qword ptr cs:PKEY_Volume_IsRoot.fmtid.Data1
0x1800062ec  jnz     short loc_18000630B
0x1800062ee  mov     rax, [rbx+8]
0x1800062f2  cmp     rax, qword ptr cs:PKEY_Volume_IsRoot.fmtid.Data4
0x1800062f9  jnz     short loc_18000630B
0x1800062fb  mov     word ptr [rdi], 0Bh
0x180006300  mov     word ptr [rdi+8], 0FFFFh
0x180006306  jmp     loc_180006593
0x18000630b  cmp     ecx, cs:PKEY_SFGAOFlags.pid
0x180006311  jnz     short loc_18000633D
0x180006313  mov     rax, [rbx]
0x180006316  cmp     rax, qword ptr cs:PKEY_SFGAOFlags.fmtid.Data1
0x18000631d  jnz     short loc_18000633D
0x18000631f  mov     rax, [rbx+8]
0x180006323  cmp     rax, qword ptr cs:PKEY_SFGAOFlags.fmtid.Data4
0x18000632a  jnz     short loc_18000633D
0x18000632c  mov     word ptr [rdi], 3
0x180006331  mov     dword ptr [rdi+8], 20040000h
0x180006338  jmp     loc_180006593
0x18000633d  cmp     ecx, cs:PKEY_Volume_IsMappedDrive.pid
0x180006343  jnz     short loc_180006371
0x180006345  mov     rax, [rbx]
0x180006348  cmp     rax, qword ptr cs:PKEY_Volume_IsMappedDrive.fmtid.Data1
0x18000634f  jnz     short loc_180006371
0x180006351  mov     rax, [rbx+8]
0x180006355  cmp     rax, qword ptr cs:PKEY_Volume_IsMappedDrive.fmtid.Data4
0x18000635c  jnz     short loc_180006371
0x18000635e  mov     word ptr [rdi], 0Bh
0x180006363  neg     dl
0x180006365  sbb     ax, ax
0x180006368  mov     [rdi+8], ax
0x18000636c  jmp     loc_180006593
0x180006371  cmp     ecx, cs:PKEY_PerceivedType.pid
0x180006377  jnz     short loc_1800063A3
0x180006379  mov     rax, [rbx]
0x18000637c  cmp     rax, qword ptr cs:PKEY_PerceivedType.fmtid.Data1
0x180006383  jnz     short loc_1800063A3
0x180006385  mov     rax, [rbx+8]
0x180006389  cmp     rax, qword ptr cs:PKEY_PerceivedType.fmtid.Data4
0x180006390  jnz     short loc_1800063A3
0x180006392  mov     word ptr [rdi], 3
0x180006397  mov     dword ptr [rdi+8], 0FFFFFFFFh
0x18000639e  jmp     loc_180006593
0x1800063a3  cmp     ecx, cs:PKEY_PropList_PreviewTitle.pid
0x1800063a9  jnz     short loc_18000641F
0x1800063ab  mov     rax, [rbx]
0x1800063ae  cmp     rax, qword ptr cs:PKEY_PropList_PreviewTitle.fmtid.Data1
0x1800063b5  jnz     short loc_18000641F
0x1800063b7  mov     rax, [rbx+8]
0x1800063bb  cmp     rax, qword ptr cs:PKEY_PropList_PreviewTitle.fmtid.Data4
0x1800063c2  jnz     short loc_18000641F
0x1800063c4  mov     word ptr [rdi], 8
0x1800063c9  lea     rcx, psz; "prop:System.DisplayName;"
0x1800063d0  call    cs:__imp_SysAllocString
0x1800063d6  mov     [rdi+8], rax
0x1800063da  test    rax, rax
0x1800063dd  jnz     loc_180006593
0x1800063e3  mov     rcx, rdi; pvarg
0x1800063e6  call    cs:__imp_VariantInit
0x1800063ec  mov     rcx, [rsp+98h]; this
0x1800063f4  mov     ebx, 8007000Eh
0x1800063f9  mov     r9d, ebx; char *
0x1800063fc  lea     r8, aVmUxUiRemotefi_7; "vm\\ux\\ui\\remotefilebrowse\\diskfolde"...
0x180006403  mov     edx, 1C5h; void *
0x180006408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000640d  nop
0x18000640e  lea     rcx, [rsp+98h+var_40]
0x180006413  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006418  mov     eax, ebx
0x18000641a  jmp     loc_180006635
0x18000641f  cmp     ecx, cs:PKEY_PropList_PreviewDetails.pid
0x180006425  jnz     short loc_18000649B
0x180006427  mov     rax, [rbx]
0x18000642a  cmp     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data1
0x180006431  jnz     short loc_18000649B
0x180006433  mov     rax, [rbx+8]
0x180006437  cmp     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data4
0x18000643e  jnz     short loc_18000649B
0x180006440  mov     word ptr [rdi], 8
0x180006445  lea     rcx, aPropSystemPerc; "prop:*System.PercentFull;System.FreeSpa"...
0x18000644c  call    cs:__imp_SysAllocString
0x180006452  mov     [rdi+8], rax
0x180006456  test    rax, rax
0x180006459  jnz     loc_180006593
0x18000645f  mov     rcx, rdi; pvarg
0x180006462  call    cs:__imp_VariantInit
0x180006468  mov     rcx, [rsp+98h]; this
0x180006470  mov     ebx, 8007000Eh
0x180006475  mov     r9d, ebx; char *
0x180006478  lea     r8, aVmUxUiRemotefi_7; "vm\\ux\\ui\\remotefilebrowse\\diskfolde"...
0x18000647f  mov     edx, 1CEh; void *
0x180006484  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006489  nop
0x18000648a  lea     rcx, [rsp+98h+var_40]
0x18000648f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006494  mov     eax, ebx
  ... truncated ...
```
