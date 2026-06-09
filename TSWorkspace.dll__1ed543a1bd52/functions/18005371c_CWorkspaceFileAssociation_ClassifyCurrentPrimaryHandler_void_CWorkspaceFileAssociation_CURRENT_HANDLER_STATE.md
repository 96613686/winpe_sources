# CWorkspaceFileAssociation::ClassifyCurrentPrimaryHandler(void *,CWorkspaceFileAssociation::CURRENT_HANDLER_STATE *)

- ea: `0x18005371c`
- end: `0x180053bf7`
- name: `?ClassifyCurrentPrimaryHandler@CWorkspaceFileAssociation@@IEAAJPEAXPEAW4CURRENT_HANDLER_STATE@1@@Z`
- size: `1243`
- prototype: `int(CWorkspaceFileAssociation *__hidden this, void *, enum CWorkspaceFileAssociation::CURRENT_HANDLER_STATE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180054b64`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x180020bf0`
- `0x18003ce1c`
- `0x18005371c`
- `0x1800a3010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180053bbd`
- `ole32!CoTaskMemFree` at `0x180053bbd`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x18005395f`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x18005395f`
- `ADVAPI32!RegGetValueW` at `0x180053a75`
- `ADVAPI32!RegGetValueW` at `0x180053a75`
- `ADVAPI32!RegCloseKey` at `0x180053ba6`
- `ADVAPI32!RegCloseKey` at `0x180053ba6`
- `SHELL32!SHCreateAssociationRegistration` at `0x1800537e4`
- `SHELL32!SHCreateAssociationRegistration` at `0x1800537e4`

## string_xrefs

- `0x180053825`: `SHCreateAssociationRegistration failed`

## pseudocode

```c
__int64 __fastcall CWorkspaceFileAssociation::ClassifyCurrentPrimaryHandler(
        CWorkspaceFileAssociation *this,
        void *a2,
        enum CWorkspaceFileAssociation::CURRENT_HANDLER_STATE *a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  int ValueW; // ebx
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  char *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rbx
  unsigned int v15; // eax
  __int64 v16; // rbx
  unsigned int v17; // eax
  unsigned int v18; // esi
  unsigned int v19; // eax
  __int64 v20; // rdx
  LPCWSTR v21; // rdi
  __int64 v22; // rbx
  LPCWSTR v23; // rdi
  __int64 v24; // rbx
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-20h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-18h] BYREF
  void *ppv; // [rsp+50h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+28h] BYREF
  int pvData; // [rsp+98h] [rbp+38h] BYREF

  hkey = 0;
  ppv = 0;
  lpSubKey = 0;
  if ( a2 == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 73;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147024809);
LABEL_7:
    ValueW = -2147024809;
    goto LABEL_67;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 74;
    goto LABEL_6;
  }
  ValueW = SHCreateAssociationRegistration(&GUID_4e530b0a_e611_4c77_a3ac_9031d022281b, &ppv);
  if ( ValueW < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 75;
      v11 = "SHCreateAssociationRegistration failed";
LABEL_18:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
        v9,
        (__int64)v11,
        ValueW);
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  v12 = (char *)this + 48;
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  ValueW = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, __int64, LPCWSTR *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             v13,
             0,
             2,
             &lpSubKey);
  if ( ValueW == -2147023741 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
        v15,
        v14);
    }
    *(_DWORD *)a3 = 0;
LABEL_66:
    ValueW = 0;
    goto LABEL_67;
  }
  if ( ValueW >= 0 )
  {
    ValueW = RegOpenKeyTransactedW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x20019u, &hkey, a2, 0);
    if ( ValueW == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
          v17,
          v16);
      }
      *(_DWORD *)a3 = 1;
      goto LABEL_66;
    }
    if ( ValueW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( ValueW > 0 )
          v18 = (unsigned __int16)ValueW | 0x80070000;
        else
          v18 = ValueW;
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 79;
LABEL_44:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v19, v18);
      }
    }
    else
    {
      pvData = 0;
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"RemoteApp", 0x10u, 0, &pvData, &pcbData);
      if ( ValueW == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v21 = lpSubKey;
          v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, (__int64)v21);
        }
        *(_DWORD *)a3 = 2;
        goto LABEL_66;
      }
      if ( !ValueW )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v23 = lpSubKey;
          v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, (__int64)v23);
        }
        *(_DWORD *)a3 = 3;
        goto LABEL_66;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( ValueW > 0 )
          v18 = (unsigned __int16)ValueW | 0x80070000;
        else
          v18 = ValueW;
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 81;
        goto LABEL_44;
      }
    }
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 77;
    v11 = "IApplicationAssociationRegistration::QueryCurrentDefault failed";
    goto LABEL_18;
  }
LABEL_67:
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( lpSubKey )
  {
    CoTaskMemFree((LPVOID)lpSubKey);
    lpSubKey = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x18005371c  mov     [rsp-18h+arg_0], rbx
0x180053721  mov     [rsp-18h+arg_10], rsi
0x180053726  push    rbp
0x180053727  push    rdi
0x180053728  push    r14
0x18005372a  mov     rbp, rsp
0x18005372d  sub     rsp, 60h
0x180053731  mov     [rbp+hkey], 0
0x180053739  mov     rsi, r8
0x18005373c  mov     [rbp+ppv], 0
0x180053744  mov     rdi, rdx
0x180053747  mov     [rbp+lpSubKey], 0
0x18005374f  mov     r14, rcx
0x180053752  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180053756  jnz     short loc_1800537AB
0x180053758  mov     rcx, cs:WPP_GLOBAL_Control
0x18005375f  lea     rax, WPP_GLOBAL_Control
0x180053766  cmp     rcx, rax
0x180053769  jz      short loc_1800537A1
0x18005376b  test    byte ptr [rcx+1Ch], 8
0x18005376f  jz      short loc_1800537A1
0x180053771  cmp     byte ptr [rcx+19h], 2
0x180053775  jb      short loc_1800537A1
0x180053777  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005377c  lea     edx, [rdi+4Ah]
0x18005377f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053786  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x18005378d  mov     r9d, eax
0x180053790  mov     dword ptr [rsp+60h+phkResult], 80070057h
0x180053798  mov     rcx, [rcx+10h]
0x18005379c  call    WPP_SF_Dd
0x1800537a1  mov     ebx, 80070057h
0x1800537a6  jmp     loc_180053B9D
0x1800537ab  test    rsi, rsi
0x1800537ae  jnz     short loc_1800537D9
0x1800537b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800537b7  lea     rax, WPP_GLOBAL_Control
0x1800537be  cmp     rcx, rax
0x1800537c1  jz      short loc_1800537A1
0x1800537c3  test    byte ptr [rcx+1Ch], 8
0x1800537c7  jz      short loc_1800537A1
0x1800537c9  cmp     byte ptr [rcx+19h], 2
0x1800537cd  jb      short loc_1800537A1
0x1800537cf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800537d4  lea     edx, [rsi+4Ah]
0x1800537d7  jmp     short loc_18005377F
0x1800537d9  lea     rdx, [rbp+ppv]; ppv
0x1800537dd  lea     rcx, _GUID_4e530b0a_e611_4c77_a3ac_9031d022281b; riid
0x1800537e4  call    cs:__imp_SHCreateAssociationRegistration
0x1800537ea  mov     ebx, eax
0x1800537ec  test    eax, eax
0x1800537ee  jns     short loc_180053854
0x1800537f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800537f7  lea     rax, WPP_GLOBAL_Control
0x1800537fe  cmp     rcx, rax
0x180053801  jz      loc_180053B9D
0x180053807  test    byte ptr [rcx+1Ch], 8
0x18005380b  jz      loc_180053B9D
0x180053811  cmp     byte ptr [rcx+19h], 2
0x180053815  jb      loc_180053B9D
0x18005381b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053820  mov     edx, 4Bh ; 'K'
0x180053825  lea     rcx, aShcreateassoci; "SHCreateAssociationRegistration failed"
0x18005382c  mov     dword ptr [rsp+60h+hTransaction], ebx
0x180053830  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180053837  mov     [rsp+60h+phkResult], rcx
0x18005383c  mov     r9d, eax
0x18005383f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053846  mov     rcx, [rcx+10h]
0x18005384a  call    WPP_SF_DsD
0x18005384f  jmp     loc_180053B9D
0x180053854  add     r14, 30h ; '0'
0x180053858  mov     rcx, r14
0x18005385b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053860  mov     rcx, [rbp+ppv]
0x180053864  mov     r10, rax
0x180053867  mov     r9d, 2
0x18005386d  xor     r8d, r8d
0x180053870  mov     rdx, [rcx]
0x180053873  mov     rax, [rdx+18h]
0x180053877  lea     rdx, [rbp+lpSubKey]
0x18005387b  mov     [rsp+60h+phkResult], rdx
0x180053880  mov     rdx, r10
0x180053883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053888  mov     ebx, eax
0x18005388a  cmp     eax, 80070483h
0x18005388f  jnz     short loc_1800538EF
0x180053891  mov     rdx, cs:WPP_GLOBAL_Control
0x180053898  lea     rax, WPP_GLOBAL_Control
0x18005389f  cmp     rdx, rax
0x1800538a2  jz      short loc_1800538E4
0x1800538a4  test    byte ptr [rdx+1Ch], 1
0x1800538a8  jz      short loc_1800538E4
0x1800538aa  cmp     byte ptr [rdx+19h], 4
0x1800538ae  jb      short loc_1800538E4
0x1800538b0  mov     rcx, r14
0x1800538b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800538b8  mov     rbx, rax
0x1800538bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800538c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538c7  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x1800538ce  mov     edx, 4Ch ; 'L'
0x1800538d3  mov     [rsp+60h+phkResult], rbx
0x1800538d8  mov     r9d, eax
0x1800538db  mov     rcx, [rcx+10h]
0x1800538df  call    WPP_SF_DS
0x1800538e4  mov     dword ptr [rsi], 0
0x1800538ea  jmp     loc_180053B9B
0x1800538ef  test    ebx, ebx
0x1800538f1  jns     short loc_180053934
0x1800538f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538fa  lea     rax, WPP_GLOBAL_Control
0x180053901  cmp     rcx, rax
0x180053904  jz      loc_180053B9D
0x18005390a  test    byte ptr [rcx+1Ch], 8
0x18005390e  jz      loc_180053B9D
0x180053914  cmp     byte ptr [rcx+19h], 2
0x180053918  jb      loc_180053B9D
0x18005391e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053923  mov     edx, 4Dh ; 'M'
0x180053928  lea     rcx, aIapplicationas; "IApplicationAssociationRegistration::Qu"...
0x18005392f  jmp     loc_18005382C
0x180053934  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180053938  lea     rax, [rbp+hkey]
0x18005393c  mov     [rsp+60h+pExtendedParemeter], 0; pExtendedParemeter
0x180053945  mov     r9d, 20019h; samDesired
0x18005394b  mov     [rsp+60h+hTransaction], rdi; hTransaction
0x180053950  xor     r8d, r8d; ulOptions
0x180053953  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18005395a  mov     [rsp+60h+phkResult], rax; phkResult
0x18005395f  call    cs:__imp_RegOpenKeyTransactedW
0x180053965  mov     ebx, eax
0x180053967  cmp     eax, 2
0x18005396a  jnz     short loc_1800539CA
0x18005396c  mov     rcx, cs:WPP_GLOBAL_Control
0x180053973  lea     rax, WPP_GLOBAL_Control
0x18005397a  cmp     rcx, rax
0x18005397d  jz      short loc_1800539BF
0x18005397f  test    byte ptr [rcx+1Ch], 1
0x180053983  jz      short loc_1800539BF
0x180053985  cmp     byte ptr [rcx+19h], 4
0x180053989  jb      short loc_1800539BF
0x18005398b  mov     rcx, r14
0x18005398e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053993  mov     rbx, rax
0x180053996  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005399b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539a2  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x1800539a9  mov     edx, 4Eh ; 'N'
0x1800539ae  mov     [rsp+60h+phkResult], rbx
0x1800539b3  mov     r9d, eax
0x1800539b6  mov     rcx, [rcx+10h]
0x1800539ba  call    WPP_SF_DS
0x1800539bf  mov     dword ptr [rsi], 1
0x1800539c5  jmp     loc_180053B9B
0x1800539ca  test    ebx, ebx
0x1800539cc  jz      short loc_180053A39
0x1800539ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539d5  lea     rax, WPP_GLOBAL_Control
0x1800539dc  mov     edi, 80070000h
0x1800539e1  cmp     rcx, rax
0x1800539e4  jz      short loc_180053A27
0x1800539e6  test    byte ptr [rcx+1Ch], 8
0x1800539ea  jz      short loc_180053A27
0x1800539ec  cmp     byte ptr [rcx+19h], 2
0x1800539f0  jb      short loc_180053A27
0x1800539f2  test    ebx, ebx
0x1800539f4  jg      short loc_1800539FA
0x1800539f6  mov     esi, ebx
0x1800539f8  jmp     short loc_1800539FF
0x1800539fa  movzx   esi, bx
0x1800539fd  or      esi, edi
0x1800539ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053a04  mov     edx, 4Fh ; 'O'
0x180053a09  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a10  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180053a17  mov     r9d, eax
0x180053a1a  mov     dword ptr [rsp+60h+phkResult], esi
0x180053a1e  mov     rcx, [rcx+10h]
0x180053a22  call    WPP_SF_Dd
0x180053a27  test    ebx, ebx
0x180053a29  jle     loc_180053B9D
0x180053a2f  movzx   ebx, bx
0x180053a32  or      ebx, edi
0x180053a34  jmp     loc_180053B9D
0x180053a39  mov     rcx, [rbp+hkey]; hkey
0x180053a3d  lea     rax, [rbp+pcbData]
0x180053a41  mov     [rsp+60h+pExtendedParemeter], rax; pcbData
0x180053a46  lea     r8, aRemoteapp; "RemoteApp"
0x180053a4d  lea     rax, [rbp+pvData]
0x180053a51  mov     [rbp+pvData], 0
0x180053a58  mov     [rsp+60h+hTransaction], rax; pvData
0x180053a5d  mov     r9d, 10h; dwFlags
0x180053a63  xor     edx, edx; lpSubKey
0x180053a65  mov     [rsp+60h+phkResult], 0; pdwType
0x180053a6e  mov     [rbp+pcbData], 4
0x180053a75  call    cs:__imp_RegGetValueW
0x180053a7b  mov     ebx, eax
0x180053a7d  cmp     eax, 2
0x180053a80  jnz     short loc_180053AE9
0x180053a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a89  lea     rax, WPP_GLOBAL_Control
0x180053a90  cmp     rcx, rax
0x180053a93  jz      short loc_180053ADE
0x180053a95  test    byte ptr [rcx+1Ch], 1
0x180053a99  jz      short loc_180053ADE
0x180053a9b  cmp     byte ptr [rcx+19h], 4
0x180053a9f  jb      short loc_180053ADE
0x180053aa1  mov     rdi, [rbp+lpSubKey]
0x180053aa5  mov     rcx, r14
0x180053aa8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053aad  mov     rbx, rax
0x180053ab0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x180053abc  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180053ac3  mov     edx, 50h ; 'P'
0x180053ac8  mov     [rsp+60h+hTransaction], rdi; __int64
0x180053acd  mov     r9d, eax
0x180053ad0  mov     [rsp+60h+phkResult], rbx; __int64
0x180053ad5  mov     rcx, [rcx+10h]; LoggerHandle
0x180053ad9  call    WPP_SF_DSS
0x180053ade  mov     dword ptr [rsi], 2
0x180053ae4  jmp     loc_180053B9B
0x180053ae9  test    ebx, ebx
0x180053aeb  jz      short loc_180053B39
0x180053aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180053af4  lea     rax, WPP_GLOBAL_Control
0x180053afb  mov     edi, 80070000h
0x180053b00  cmp     rcx, rax
0x180053b03  jz      loc_180053A27
0x180053b09  test    byte ptr [rcx+1Ch], 8
0x180053b0d  jz      loc_180053A27
0x180053b13  cmp     byte ptr [rcx+19h], 2
0x180053b17  jb      loc_180053A27
0x180053b1d  test    ebx, ebx
0x180053b1f  jg      short loc_180053B25
0x180053b21  mov     esi, ebx
0x180053b23  jmp     short loc_180053B2A
0x180053b25  movzx   esi, bx
0x180053b28  or      esi, edi
0x180053b2a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053b2f  mov     edx, 51h ; 'Q'
0x180053b34  jmp     loc_180053A09
0x180053b39  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b40  lea     rax, WPP_GLOBAL_Control
0x180053b47  cmp     rcx, rax
0x180053b4a  jz      short loc_180053B95
0x180053b4c  test    byte ptr [rcx+1Ch], 1
0x180053b50  jz      short loc_180053B95
0x180053b52  cmp     byte ptr [rcx+19h], 4
0x180053b56  jb      short loc_180053B95
0x180053b58  mov     rdi, [rbp+lpSubKey]
0x180053b5c  mov     rcx, r14
0x180053b5f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053b64  mov     rbx, rax
0x180053b67  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180053b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b73  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180053b7a  mov     edx, 52h ; 'R'
0x180053b7f  mov     [rsp+60h+hTransaction], rdi; __int64
0x180053b84  mov     r9d, eax
0x180053b87  mov     [rsp+60h+phkResult], rbx; __int64
0x180053b8c  mov     rcx, [rcx+10h]; LoggerHandle
0x180053b90  call    WPP_SF_DSS
0x180053b95  mov     dword ptr [rsi], 3
0x180053b9b  xor     ebx, ebx
0x180053b9d  mov     rcx, [rbp+hkey]; hKey
0x180053ba1  test    rcx, rcx
0x180053ba4  jz      short loc_180053BB4
0x180053ba6  call    cs:__imp_RegCloseKey
0x180053bac  mov     [rbp+hkey], 0
0x180053bb4  mov     rcx, [rbp+lpSubKey]; pv
0x180053bb8  test    rcx, rcx
0x180053bbb  jz      short loc_180053BCB
0x180053bbd  call    cs:__imp_CoTaskMemFree
0x180053bc3  mov     [rbp+lpSubKey], 0
0x180053bcb  mov     rcx, [rbp+ppv]
0x180053bcf  test    rcx, rcx
0x180053bd2  jz      short loc_180053BE0
0x180053bd4  mov     rax, [rcx]
0x180053bd7  mov     rax, [rax+10h]
0x180053bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053be0  lea     r11, [rsp+60h+var_s0]
0x180053be5  mov     eax, ebx
0x180053be7  mov     rbx, [r11+20h]
0x180053beb  mov     rsi, [r11+30h]
0x180053bef  mov     rsp, r11
0x180053bf2  pop     r14
0x180053bf4  pop     rdi
0x180053bf5  pop     rbp
0x180053bf6  retn
```
