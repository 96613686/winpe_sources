# CWorkspaceInstaller::GetSubscriptionInformation(__MIDL___MIDL_itf_workspacenotify_0000_0002_0001,ushort *,ushort * *)

- ea: `0x180073f10`
- end: `0x180074399`
- name: `?GetSubscriptionInformation@CWorkspaceInstaller@@UEAAJW4__MIDL___MIDL_itf_workspacenotify_0000_0002_0001@@PEAGPEAPEAG@Z`
- size: `1161`
- prototype: `int __high(enum __MIDL___MIDL_itf_workspacenotify_0000_0002_0001, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003108`
- `0x1800058d4`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x1800107e8`
- `0x180020bf0`
- `0x18002f810`
- `0x1800300fc`
- `0x180073f10`
- `0x18007921c`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18007434b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18007434b`
- `ole32!CLSIDFromString` at `0x180074062`
- `ole32!CLSIDFromString` at `0x180074062`
- `OLEAUT32!__imp_SysFreeString` at `0x18007436f`
- `OLEAUT32!__imp_SysFreeString` at `0x18007436f`

## string_xrefs

- `0x1800740a0`: `CLSIDFromString failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkspaceInstaller::GetSubscriptionInformation(__int64 a1, int a2, const OLECHAR *a3, OLECHAR **a4)
{
  OLECHAR *v7; // rbx
  CWorkspaceManager *Instance; // r14
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HRESULT WorkspaceFromID; // edi
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned __int16 *v15; // r14
  unsigned int v16; // eax
  int v17; // r15d
  struct CWorkspace *v18; // r15
  UINT v19; // edx
  const unsigned __int16 *v20; // rax
  int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  OLECHAR *v24; // rax
  unsigned int v25; // eax
  HRESULT v27; // ebx
  unsigned int v28; // eax
  __int64 v29; // [rsp+20h] [rbp-78h]
  __int64 v30; // [rsp+28h] [rbp-70h]
  struct CWorkspace *v31; // [rsp+30h] [rbp-68h] BYREF
  OLECHAR *v32; // [rsp+38h] [rbp-60h] BYREF
  HRESULT v33; // [rsp+40h] [rbp-58h]
  HRESULT v34; // [rsp+44h] [rbp-54h] BYREF
  unsigned __int16 *v35; // [rsp+48h] [rbp-50h]
  __int64 v36; // [rsp+50h] [rbp-48h]
  GUID pclsid; // [rsp+58h] [rbp-40h] BYREF

  v36 = -2;
  v31 = 0;
  pclsid = 0;
  v7 = 0;
  v32 = 0;
  Instance = CWorkspaceManager::GetInstance();
  if ( !Instance )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147418113);
    }
    WorkspaceFromID = -2147418113;
    goto LABEL_59;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
        v11,
        -2147024809);
    }
    WorkspaceFromID = -2147024809;
    goto LABEL_59;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
      v12,
      (__int64)a3);
  }
  WorkspaceFromID = CLSIDFromString(a3, &pclsid);
  if ( WorkspaceFromID < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
        v13,
        (__int64)"CLSIDFromString failed",
        WorkspaceFromID);
    }
    goto LABEL_59;
  }
  WorkspaceFromID = CWorkspaceManager::GetWorkspaceFromID(Instance, &pclsid, &v31);
  if ( WorkspaceFromID < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
        v14,
        (__int64)"GetWorkspaceFromID failed",
        WorkspaceFromID);
    }
    goto LABEL_57;
  }
  v15 = (unsigned __int16 *)operator new[](0x5004u, (const struct std::nothrow_t *)&std::nothrow);
  v35 = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
        v16,
        -2147024882);
    }
    WorkspaceFromID = -2147024882;
    goto LABEL_57;
  }
  if ( a2 )
  {
    v17 = a2 - 1;
    if ( !v17 )
    {
      v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v31 + 296);
      v21 = StringCchCopyW(v15, 0x2802u, v20);
      goto LABEL_40;
    }
    if ( v17 != 1 )
      goto LABEL_65;
    v18 = v31;
    v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v31 + 680);
    v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v18 + 648);
    v19 = 15821;
  }
  else
  {
    LODWORD(v30) = *((_DWORD *)v31 + 151);
    LODWORD(v29) = *((_DWORD *)v31 + 150);
    v19 = 15820;
  }
  v21 = TSWFormatString(g_hinst, v19, v15, 0x2802u, v29, v30);
LABEL_40:
  WorkspaceFromID = v21;
  if ( v21 < 0 )
  {
    if ( v21 != -2147024774 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
          v25,
          WorkspaceFromID);
      }
      goto LABEL_56;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids, v22);
    }
    WorkspaceFromID = 0;
  }
LABEL_65:
  try
  {
    ATL::CComBSTR::operator=(&v32, v15);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids,
        v23,
        (__int64)v15);
    }
    v24 = v32;
    v7 = 0;
    v32 = 0;
    *a4 = v24;
  }
  catch ( ATL::CAtlException v34 )
  {
    v27 = v34;
    v33 = v34;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids, v28, v27);
    }
    WorkspaceFromID = v33;
    v15 = v35;
    v7 = v32;
  }
LABEL_56:
  operator delete[](v15);
LABEL_57:
  if ( v31 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 4) + 16LL))(*((_QWORD *)v31 + 4));
LABEL_59:
  SysFreeString(v7);
  return (unsigned int)WorkspaceFromID;
}

```

## disassembly

```asm
0x180073f10  mov     r11, rsp
0x180073f13  push    rsi
0x180073f14  push    rdi
0x180073f15  push    r12
0x180073f17  push    r14
0x180073f19  push    r15
0x180073f1b  sub     rsp, 70h
0x180073f1f  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x180073f27  mov     [r11+8], rbx
0x180073f2b  mov     rax, cs:__security_cookie
0x180073f32  xor     rax, rsp
0x180073f35  mov     [rsp+98h+var_30], rax
0x180073f3a  mov     r12, r9
0x180073f3d  mov     rdi, r8
0x180073f40  mov     r15d, edx
0x180073f43  mov     qword ptr [r11-68h], 0
0x180073f4b  xorps   xmm0, xmm0
0x180073f4e  movups  xmmword ptr [rsp+98h+pclsid.Data1], xmm0
0x180073f53  xor     ebx, ebx
0x180073f55  mov     [rsp+98h+var_60], rbx
0x180073f5a  call    ?GetInstance@CWorkspaceManager@@SAPEAV1@XZ; CWorkspaceManager::GetInstance(void)
0x180073f5f  mov     r14, rax
0x180073f62  test    rax, rax
0x180073f65  jnz     short loc_180073FBA
0x180073f67  lea     rsi, WPP_GLOBAL_Control
0x180073f6e  mov     rax, cs:WPP_GLOBAL_Control
0x180073f75  cmp     rax, rsi
0x180073f78  jz      short loc_180073FB0
0x180073f7a  test    byte ptr [rax+1Ch], 8
0x180073f7e  jz      short loc_180073FB0
0x180073f80  cmp     byte ptr [rax+19h], 2
0x180073f84  jb      short loc_180073FB0
0x180073f86  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180073f8b  lea     edx, [rbx+14h]
0x180073f8e  mov     dword ptr [rsp+98h+var_78], 8000FFFFh
0x180073f96  mov     r9d, eax
0x180073f99  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x180073fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180073fa7  mov     rcx, [rcx+10h]
0x180073fab  call    WPP_SF_Dd
0x180073fb0  mov     edi, 8000FFFFh
0x180073fb5  jmp     loc_18007436C
0x180073fba  test    rdi, rdi
0x180073fbd  jnz     short loc_180074012
0x180073fbf  lea     rsi, WPP_GLOBAL_Control
0x180073fc6  mov     rax, cs:WPP_GLOBAL_Control
0x180073fcd  cmp     rax, rsi
0x180073fd0  jz      short loc_180074008
0x180073fd2  test    byte ptr [rax+1Ch], 8
0x180073fd6  jz      short loc_180074008
0x180073fd8  cmp     byte ptr [rax+19h], 2
0x180073fdc  jb      short loc_180074008
0x180073fde  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180073fe3  lea     edx, [rdi+15h]
0x180073fe6  mov     dword ptr [rsp+98h+var_78], 80070057h
0x180073fee  mov     r9d, eax
0x180073ff1  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x180073ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180073fff  mov     rcx, [rcx+10h]
0x180074003  call    WPP_SF_Dd
0x180074008  mov     edi, 80070057h
0x18007400d  jmp     loc_18007436C
0x180074012  lea     rsi, WPP_GLOBAL_Control
0x180074019  mov     rax, cs:WPP_GLOBAL_Control
0x180074020  cmp     rax, rsi
0x180074023  jz      short loc_18007405A
0x180074025  test    byte ptr [rax+1Ch], 1
0x180074029  jz      short loc_18007405A
0x18007402b  cmp     byte ptr [rax+19h], 4
0x18007402f  jb      short loc_18007405A
0x180074031  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074036  mov     edx, 16h
0x18007403b  mov     [rsp+98h+var_78], rdi
0x180074040  mov     r9d, eax
0x180074043  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x18007404a  mov     rcx, cs:WPP_GLOBAL_Control
0x180074051  mov     rcx, [rcx+10h]
0x180074055  call    WPP_SF_DS
0x18007405a  lea     rdx, [rsp+98h+pclsid]; pclsid
0x18007405f  mov     rcx, rdi; lpsz
0x180074062  call    cs:__imp_CLSIDFromString
0x180074068  mov     edi, eax
0x18007406a  test    eax, eax
0x18007406c  jns     short loc_1800740CB
0x18007406e  mov     rax, cs:WPP_GLOBAL_Control
0x180074075  cmp     rax, rsi
0x180074078  jz      loc_18007436C
0x18007407e  test    byte ptr [rax+1Ch], 8
0x180074082  jz      loc_18007436C
0x180074088  cmp     byte ptr [rax+19h], 2
0x18007408c  jb      loc_18007436C
0x180074092  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074097  mov     edx, 17h
0x18007409c  mov     dword ptr [rsp+98h+var_70], edi
0x1800740a0  lea     rcx, aClsidfromstrin; "CLSIDFromString failed"
0x1800740a7  mov     [rsp+98h+var_78], rcx
0x1800740ac  mov     r9d, eax
0x1800740af  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x1800740b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800740bd  mov     rcx, [rcx+10h]
0x1800740c1  call    WPP_SF_DsD
0x1800740c6  jmp     loc_18007436C
0x1800740cb  lea     r8, [rsp+98h+var_68]; struct CWorkspace **
0x1800740d0  lea     rdx, [rsp+98h+pclsid]; struct _GUID *
0x1800740d5  mov     rcx, r14; this
0x1800740d8  call    ?GetWorkspaceFromID@CWorkspaceManager@@QEAAJAEAU_GUID@@PEAPEAVCWorkspace@@@Z; CWorkspaceManager::GetWorkspaceFromID(_GUID &,CWorkspace * *)
0x1800740dd  mov     edi, eax
0x1800740df  test    eax, eax
0x1800740e1  jns     short loc_180074140
0x1800740e3  mov     rax, cs:WPP_GLOBAL_Control
0x1800740ea  cmp     rax, rsi
0x1800740ed  jz      loc_180074351
0x1800740f3  test    byte ptr [rax+1Ch], 8
0x1800740f7  jz      loc_180074351
0x1800740fd  cmp     byte ptr [rax+19h], 2
0x180074101  jb      loc_180074351
0x180074107  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007410c  mov     edx, 18h
0x180074111  mov     dword ptr [rsp+98h+var_70], edi
0x180074115  lea     rcx, aGetworkspacefr_1; "GetWorkspaceFromID failed"
0x18007411c  mov     [rsp+98h+var_78], rcx
0x180074121  mov     r9d, eax
0x180074124  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x18007412b  mov     rcx, cs:WPP_GLOBAL_Control
0x180074132  mov     rcx, [rcx+10h]
0x180074136  call    WPP_SF_DsD
0x18007413b  jmp     loc_180074351
0x180074140  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180074147  mov     ecx, 5004h; unsigned __int64
0x18007414c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180074151  mov     r14, rax
0x180074154  mov     [rsp+98h+var_50], rax
0x180074159  test    rax, rax
0x18007415c  jnz     short loc_1800741AB
0x18007415e  mov     rax, cs:WPP_GLOBAL_Control
0x180074165  cmp     rax, rsi
0x180074168  jz      short loc_1800741A1
0x18007416a  test    byte ptr [rax+1Ch], 8
0x18007416e  jz      short loc_1800741A1
0x180074170  cmp     byte ptr [rax+19h], 2
0x180074174  jb      short loc_1800741A1
0x180074176  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007417b  lea     edx, [r14+19h]
0x18007417f  mov     dword ptr [rsp+98h+var_78], 8007000Eh
0x180074187  mov     r9d, eax
0x18007418a  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x180074191  mov     rcx, cs:WPP_GLOBAL_Control
0x180074198  mov     rcx, [rcx+10h]
0x18007419c  call    WPP_SF_Dd
0x1800741a1  mov     edi, 8007000Eh
0x1800741a6  jmp     loc_180074351
0x1800741ab  test    r15d, r15d
0x1800741ae  jz      short loc_180074214
0x1800741b0  sub     r15d, 1
0x1800741b4  jz      short loc_1800741F1
0x1800741b6  cmp     r15d, 1
0x1800741ba  jnz     loc_180074298
0x1800741c0  mov     r15, [rsp+98h+var_68]
0x1800741c5  lea     rcx, [r15+2A8h]
0x1800741cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800741d1  mov     rdi, rax
0x1800741d4  lea     rcx, [r15+288h]
0x1800741db  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800741e0  mov     [rsp+98h+var_70], rdi
0x1800741e5  mov     [rsp+98h+var_78], rax
0x1800741ea  mov     edx, 3DCDh
0x1800741ef  jmp     short loc_180074234
0x1800741f1  mov     rcx, [rsp+98h+var_68]
0x1800741f6  add     rcx, 128h
0x1800741fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180074202  mov     r8, rax; unsigned __int16 *
0x180074205  mov     edx, 2802h; unsigned __int64
0x18007420a  mov     rcx, r14; unsigned __int16 *
0x18007420d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180074212  jmp     short loc_180074249
0x180074214  mov     r15, [rsp+98h+var_68]
0x180074219  mov     eax, [r15+25Ch]
0x180074220  mov     dword ptr [rsp+98h+var_70], eax
0x180074224  mov     eax, [r15+258h]
0x18007422b  mov     dword ptr [rsp+98h+var_78], eax
0x18007422f  mov     edx, 3DCCh; uID
0x180074234  mov     r9d, 2802h; unsigned __int64
0x18007423a  mov     r8, r14; unsigned __int16 *
0x18007423d  mov     rcx, cs:g_hinst; hInstance
0x180074244  call    ?TSWFormatString@@YAJPEAUHINSTANCE__@@HPEAG_KZZ; TSWFormatString(HINSTANCE__ *,int,ushort *,unsigned __int64,...)
0x180074249  mov     edi, eax
0x18007424b  test    eax, eax
0x18007424d  jns     short loc_180074298
0x18007424f  cmp     eax, 8007007Ah
0x180074254  jnz     loc_1800742F8
0x18007425a  mov     rax, cs:WPP_GLOBAL_Control
0x180074261  cmp     rax, rsi
0x180074264  jz      short loc_180074296
0x180074266  test    byte ptr [rax+1Ch], 1
0x18007426a  jz      short loc_180074296
0x18007426c  cmp     byte ptr [rax+19h], 2
0x180074270  jb      short loc_180074296
0x180074272  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074277  mov     edx, 1Ah
0x18007427c  mov     r9d, eax
0x18007427f  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x180074286  mov     rcx, cs:WPP_GLOBAL_Control
0x18007428d  mov     rcx, [rcx+10h]
0x180074291  call    WPP_SF_D
0x180074296  xor     edi, edi
0x180074298  mov     rdx, r14
0x18007429b  lea     rcx, [rsp+98h+var_60]
0x1800742a0  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800742a5  mov     rax, cs:WPP_GLOBAL_Control
0x1800742ac  cmp     rax, rsi
0x1800742af  jz      short loc_1800742E6
0x1800742b1  test    byte ptr [rax+1Ch], 1
0x1800742b5  jz      short loc_1800742E6
0x1800742b7  cmp     byte ptr [rax+19h], 4
0x1800742bb  jb      short loc_1800742E6
0x1800742bd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800742c2  mov     edx, 1Ch
0x1800742c7  mov     [rsp+98h+var_78], r14
0x1800742cc  mov     r9d, eax
0x1800742cf  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x1800742d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800742dd  mov     rcx, [rcx+10h]
0x1800742e1  call    WPP_SF_DS
0x1800742e6  mov     rax, [rsp+98h+var_60]
0x1800742eb  xor     ebx, ebx
0x1800742ed  mov     [rsp+98h+var_60], rbx
0x1800742f2  mov     [r12], rax
0x1800742f6  jmp     short loc_180074348
0x1800742f8  mov     rax, cs:WPP_GLOBAL_Control
0x1800742ff  cmp     rax, rsi
0x180074302  jz      short loc_180074348
0x180074304  test    byte ptr [rax+1Ch], 1
0x180074308  jz      short loc_180074348
0x18007430a  cmp     byte ptr [rax+19h], 2
0x18007430e  jb      short loc_180074348
0x180074310  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074315  mov     edx, 1Bh
0x18007431a  mov     dword ptr [rsp+98h+var_78], edi
0x18007431e  mov     r9d, eax
0x180074321  lea     r8, WPP_ade15f0eaedf37353131ff6d54782f0d_Traceguids
0x180074328  mov     rcx, cs:WPP_GLOBAL_Control
0x18007432f  mov     rcx, [rcx+10h]
0x180074333  call    WPP_SF_Dd
0x180074338  jmp     short loc_180074348
0x18007433a  mov     edi, [rsp+98h+var_58]
0x18007433e  mov     r14, [rsp+98h+var_50]
0x180074343  mov     rbx, [rsp+98h+var_60]
0x180074348  mov     rcx, r14
0x18007434b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180074351  mov     r15, [rsp+98h+var_68]
0x180074356  test    r15, r15
0x180074359  jz      short loc_18007436C
0x18007435b  mov     rcx, [r15+20h]
0x18007435f  mov     rax, [rcx]
0x180074362  mov     rax, [rax+10h]
0x180074366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007436b  nop
0x18007436c  mov     rcx, rbx; bstrString
0x18007436f  call    cs:__imp_SysFreeString
0x180074375  mov     eax, edi
0x180074377  mov     rcx, [rsp+98h+var_30]
0x18007437c  xor     rcx, rsp; StackCookie
0x18007437f  call    __security_check_cookie
0x180074384  mov     rbx, [rsp+98h+arg_0]
0x18007438c  add     rsp, 70h
0x180074390  pop     r15
0x180074392  pop     r14
0x180074394  pop     r12
0x180074396  pop     rdi
0x180074397  pop     rsi
0x180074398  retn
```
