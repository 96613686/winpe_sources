# Windows::Networking::UX::Internal::WlanClient::CreateEapProfileFromTemplate(_GUID const &,HSTRING__ *,uchar,uchar,Windows::Networking::UX::WiFiSecurityType,ushort const *)

- ea: `0x1800139f0`
- end: `0x180013c92`
- name: `?CreateEapProfileFromTemplate@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@PEAUHSTRING__@@EEW4WiFiSecurityType@345@PEBG@Z`
- size: `674`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanClient *, const struct _GUID *, HSTRING, char, char, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003c9c4`

## callees

- `0x180009d4c`
- `0x18000de4c`
- `0x1800131b8`
- `0x1800139f0`
- `0x18001d4d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013b72`
- `wlanapi!WpFreeProfile` at `0x180013c4a`
- `wlanapi!WpFreeProfile` at `0x180013c4a`
- `wlanapi!WlanStringToUtf8Ssid` at `0x180013b7f`
- `wlanapi!WlanStringToUtf8Ssid` at `0x180013b7f`
- `wlanapi!WpParseProfileXml` at `0x180013a5f`
- `wlanapi!WpParseProfileXml` at `0x180013a5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::WlanClient::CreateEapProfileFromTemplate(
        Windows::Networking::UX::Internal::WlanClient *a1,
        const struct _GUID *a2,
        HSTRING a3,
        char a4,
        char a5,
        unsigned int a6,
        __int64 a7)
{
  int v11; // eax
  int v12; // ebx
  PVOID *v13; // rcx
  int v14; // eax
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  int v20; // eax
  __int64 v21; // rbx
  int v22; // ecx
  unsigned int v23; // eax
  int v24; // eax
  int v25; // ecx
  unsigned int v26; // eax
  PCWSTR v27; // rax
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // rcx
  _DWORD *v31; // rax
  DWORD v33; // [rsp+20h] [rbp-58h]
  int v34; // [rsp+30h] [rbp-48h] BYREF
  struct _PM_PROFILE *v35; // [rsp+38h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
  v35 = 0;
  v34 = 0;
  v11 = WpParseProfileXml(a7, &v35, 0, &v34);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 >= 0 )
  {
    if ( a6 <= 0xE
      && (v14 = 19520, _bittest(&v14, a6))
      && (v15 = *((_QWORD *)v35 + 69), (v16 = *(_QWORD *)(v15 + 8)) != 0)
      && *(_DWORD *)(v16 + 8) == 1
      && (v17 = *(_QWORD *)(v15 + 32)) != 0
      && (v18 = *(_QWORD *)(v17 + 424)) != 0
      && *(_DWORD *)(v18 + 16) )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
      v12 = StringCchCopyW((unsigned __int16 *)v35 + 12, 0x100u, StringRawBuffer);
      if ( v12 >= 0 )
      {
        v20 = *(_DWORD *)(v15 + 24);
        v21 = *(_QWORD *)(v15 + 8);
        v22 = v20 | 1;
        v23 = v20 & 0xFFFFFFFE;
        if ( !a4 )
          v22 = v23;
        v24 = v22;
        v25 = v22 | 2;
        v26 = v24 & 0xFFFFFFFD;
        if ( !a5 )
          v25 = v26;
        *(_DWORD *)(v15 + 24) = v25;
        v27 = WindowsGetStringRawBuffer(a3, 0);
        v28 = WlanStringToUtf8Ssid(v27, v21 + 12);
        v12 = v28;
        if ( v28 > 0 )
          v12 = (unsigned __int16)v28 | 0x80070000;
        if ( v12 >= 0 )
        {
          v30 = *(_QWORD *)(*(_QWORD *)(v15 + 32) + 424LL);
          v31 = *(_DWORD **)(v30 + 24);
          switch ( a6 )
          {
            case 0xAu:
              *(_DWORD *)(v30 + 16) = 1;
              *v31 = 1;
              v31[1] = 257;
              break;
            case 0xEu:
              *(_DWORD *)(v30 + 16) = 1;
              *v31 = 11;
              v31[1] = 4;
              break;
            case 0xBu:
              *(_DWORD *)(v30 + 16) = 1;
              *v31 = 8;
              v31[1] = 9;
              break;
          }
          v12 = Windows::Networking::UX::Internal::WlanClient::ApplyProfile(a1, a2, v29, v35, v33);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            85,
            &WPP_21979ef79db039135e573b3136931b8d_Traceguids,
            (unsigned int)v12);
        }
      }
    }
    else
    {
      v12 = -2147024809;
    }
    WpFreeProfile(v35);
    goto LABEL_37;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      84,
      &WPP_21979ef79db039135e573b3136931b8d_Traceguids,
      (unsigned int)v12);
LABEL_37:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
    WPP_SF_d(v13[2], 86, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800139f0  push    rbx
0x1800139f2  push    rbp
0x1800139f3  push    rsi
0x1800139f4  push    rdi
0x1800139f5  push    r12
0x1800139f7  push    r14
0x1800139f9  push    r15
0x1800139fb  sub     rsp, 40h
0x1800139ff  mov     r12b, r9b
0x180013a02  mov     rbp, r8
0x180013a05  mov     r14, rdx
0x180013a08  mov     r15, rcx
0x180013a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a12  lea     rdi, WPP_GLOBAL_Control
0x180013a19  cmp     rcx, rdi
0x180013a1c  jz      short loc_180013A39
0x180013a1e  test    byte ptr [rcx+1Ch], 8
0x180013a22  jz      short loc_180013A39
0x180013a24  mov     rcx, [rcx+10h]
0x180013a28  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013a2f  mov     edx, 53h ; 'S'
0x180013a34  call    WPP_SF_
0x180013a39  mov     rcx, [rsp+78h+arg_30]
0x180013a41  lea     r9, [rsp+78h+var_48]
0x180013a46  xor     r8d, r8d
0x180013a49  mov     [rsp+78h+var_40], 0
0x180013a52  lea     rdx, [rsp+78h+var_40]
0x180013a57  mov     [rsp+78h+var_48], 0
0x180013a5f  call    cs:__imp_WpParseProfileXml
0x180013a65  mov     ebx, eax
0x180013a67  test    eax, eax
0x180013a69  jle     short loc_180013A74
0x180013a6b  movzx   ebx, ax
0x180013a6e  or      ebx, 80070000h
0x180013a74  test    ebx, ebx
0x180013a76  jns     short loc_180013AAF
0x180013a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a7f  cmp     rcx, rdi
0x180013a82  jz      loc_180013C81
0x180013a88  test    byte ptr [rcx+1Ch], 2
0x180013a8c  jz      loc_180013C5E
0x180013a92  mov     rcx, [rcx+10h]
0x180013a96  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013a9d  mov     edx, 54h ; 'T'
0x180013aa2  mov     r9d, ebx
0x180013aa5  call    WPP_SF_d
0x180013aaa  jmp     loc_180013C57
0x180013aaf  mov     edi, [rsp+78h+arg_28]
0x180013ab6  cmp     edi, 0Eh
0x180013ab9  ja      loc_180013C40
0x180013abf  mov     eax, 4C40h
0x180013ac4  bt      eax, edi
0x180013ac7  jnb     loc_180013C40
0x180013acd  mov     rax, [rsp+78h+var_40]
0x180013ad2  mov     rsi, [rax+228h]
0x180013ad9  mov     rax, [rsi+8]
0x180013add  test    rax, rax
0x180013ae0  jz      loc_180013C40
0x180013ae6  cmp     dword ptr [rax+8], 1
0x180013aea  jnz     loc_180013C40
0x180013af0  mov     rax, [rsi+20h]
0x180013af4  test    rax, rax
0x180013af7  jz      loc_180013C40
0x180013afd  mov     rcx, [rax+1A8h]
0x180013b04  test    rcx, rcx
0x180013b07  jz      loc_180013C40
0x180013b0d  cmp     dword ptr [rcx+10h], 0
0x180013b11  jbe     loc_180013C40
0x180013b17  xor     edx, edx; length
0x180013b19  mov     rcx, rbp; string
0x180013b1c  call    cs:__imp_WindowsGetStringRawBuffer
0x180013b22  mov     rcx, [rsp+78h+var_40]
0x180013b27  mov     edx, 100h; unsigned __int64
0x180013b2c  add     rcx, 18h; unsigned __int16 *
0x180013b30  mov     r8, rax; unsigned __int16 *
0x180013b33  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013b38  mov     ebx, eax
0x180013b3a  test    eax, eax
0x180013b3c  js      loc_180013C45
0x180013b42  mov     ecx, [rsi+18h]
0x180013b45  mov     eax, ecx
0x180013b47  mov     rbx, [rsi+8]
0x180013b4b  or      ecx, 1
0x180013b4e  and     eax, 0FFFFFFFEh
0x180013b51  test    r12b, r12b
0x180013b54  cmovz   ecx, eax
0x180013b57  mov     eax, ecx
0x180013b59  or      ecx, 2
0x180013b5c  and     eax, 0FFFFFFFDh
0x180013b5f  cmp     [rsp+78h+arg_20], 0
0x180013b67  cmovz   ecx, eax
0x180013b6a  xor     edx, edx; length
0x180013b6c  mov     [rsi+18h], ecx
0x180013b6f  mov     rcx, rbp; string
0x180013b72  call    cs:__imp_WindowsGetStringRawBuffer
0x180013b78  mov     rcx, rax
0x180013b7b  lea     rdx, [rbx+0Ch]
0x180013b7f  call    cs:__imp_WlanStringToUtf8Ssid
0x180013b85  mov     ebx, eax
0x180013b87  test    eax, eax
0x180013b89  jle     short loc_180013B94
0x180013b8b  movzx   ebx, ax
0x180013b8e  or      ebx, 80070000h
0x180013b94  test    ebx, ebx
0x180013b96  jns     short loc_180013BD3
0x180013b98  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b9f  lea     rax, WPP_GLOBAL_Control
0x180013ba6  cmp     rcx, rax
0x180013ba9  jz      loc_180013C45
0x180013baf  test    byte ptr [rcx+1Ch], 2
0x180013bb3  jz      loc_180013C45
0x180013bb9  mov     rcx, [rcx+10h]
0x180013bbd  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013bc4  mov     edx, 55h ; 'U'
0x180013bc9  mov     r9d, ebx
0x180013bcc  call    WPP_SF_d
0x180013bd1  jmp     short loc_180013C45
0x180013bd3  mov     rax, [rsi+20h]
0x180013bd7  mov     rcx, [rax+1A8h]
0x180013bde  mov     rax, [rcx+18h]
0x180013be2  cmp     edi, 0Ah
0x180013be5  jnz     short loc_180013BF8
0x180013be7  lea     edx, [rdi-9]
0x180013bea  mov     [rcx+10h], edx
0x180013bed  mov     [rax], edx
0x180013bef  mov     dword ptr [rax+4], 101h
0x180013bf6  jmp     short loc_180013C2C
0x180013bf8  cmp     edi, 0Eh
0x180013bfb  jnz     short loc_180013C13
0x180013bfd  mov     dword ptr [rcx+10h], 1
0x180013c04  mov     dword ptr [rax], 0Bh
0x180013c0a  mov     dword ptr [rax+4], 4
0x180013c11  jmp     short loc_180013C2C
0x180013c13  cmp     edi, 0Bh
0x180013c16  jnz     short loc_180013C2C
0x180013c18  mov     dword ptr [rcx+10h], 1
0x180013c1f  mov     dword ptr [rax], 8
0x180013c25  mov     dword ptr [rax+4], 9
0x180013c2c  mov     r9, [rsp+78h+var_40]; struct _PM_PROFILE *
0x180013c31  mov     rdx, r14; struct _GUID *
0x180013c34  mov     rcx, r15; this
0x180013c37  call    ?ApplyProfile@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@KPEAU_PM_PROFILE@@_N@Z; Windows::Networking::UX::Internal::WlanClient::ApplyProfile(_GUID const &,ulong,_PM_PROFILE *,bool)
0x180013c3c  mov     ebx, eax
0x180013c3e  jmp     short loc_180013C45
0x180013c40  mov     ebx, 80070057h
0x180013c45  mov     rcx, [rsp+78h+var_40]
0x180013c4a  call    cs:__imp_WpFreeProfile
0x180013c50  lea     rdi, WPP_GLOBAL_Control
0x180013c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c5e  cmp     rcx, rdi
0x180013c61  jz      short loc_180013C81
0x180013c63  test    byte ptr [rcx+1Ch], 8
0x180013c67  jz      short loc_180013C81
0x180013c69  mov     rcx, [rcx+10h]
0x180013c6d  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013c74  mov     edx, 56h ; 'V'
0x180013c79  mov     r9d, ebx
0x180013c7c  call    WPP_SF_d
0x180013c81  mov     eax, ebx
0x180013c83  add     rsp, 40h
0x180013c87  pop     r15
0x180013c89  pop     r14
0x180013c8b  pop     r12
0x180013c8d  pop     rdi
0x180013c8e  pop     rsi
0x180013c8f  pop     rbp
0x180013c90  pop     rbx
0x180013c91  retn
```
