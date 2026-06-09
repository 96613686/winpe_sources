# AuthHostWebInstance::OnNewWindow(WebPlatformHlinkNavigationFlags,IBindCtx *,ushort const *,IUri *,IUri *,uchar const *,ulong,ushort const *,ushort const *,int *,IWebPlatform * *)

- ea: `0x14000ad80`
- end: `0x14000b0be`
- name: `?OnNewWindow@AuthHostWebInstance@@UEAAJW4WebPlatformHlinkNavigationFlags@@PEAUIBindCtx@@PEBGPEAUIUri@@3PEBEK22PEAHPEAPEAUIWebPlatform@@@Z`
- size: `830`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140002c70`
- `0x140002c98`
- `0x14000429c`
- `0x1400066dc`
- `0x1400067a0`
- `0x140009214`
- `0x14000ad80`
- `0x14000bf78`
- `0x14000cbf4`
- `0x140012f60`
- `0x140014010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14000aed1`
- `msvcrt!_wcsnicmp` at `0x14000aeeb`
- `msvcrt!_wcsnicmp` at `0x14000aed1`
- `msvcrt!_wcsnicmp` at `0x14000aeeb`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b08b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b096`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b08b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b096`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AuthHostWebInstance::OnNewWindow(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _DWORD *a11,
        _QWORD *a12)
{
  _DWORD *v13; // r15
  unsigned int v14; // r14d
  int v15; // eax
  unsigned int v16; // edi
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  wchar_t *v19; // rdi
  BSTR v20; // r12
  PVOID v21; // rcx
  const wchar_t *v22; // r14
  PVOID v23; // rcx
  int v24; // eax
  BSTR bstrString; // [rsp+48h] [rbp-49h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-41h] BYREF
  _QWORD *v28; // [rsp+58h] [rbp-39h]
  _QWORD v29[4]; // [rsp+60h] [rbp-31h] BYREF

  v13 = a11;
  v28 = a12;
  v14 = 0;
  String1 = 0;
  bstrString = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)a6 + 56LL))(a6, &String1);
  v16 = v15;
  if ( v15 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      v18 = 46;
LABEL_6:
      WPP_SF_d(v17[7], v18, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, (unsigned int)v15);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a5 + 56LL))(a5, &bstrString);
  v16 = v15;
  if ( v15 >= 0 )
  {
    v19 = String1;
    v20 = bstrString;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        48,
        (unsigned int)&WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
        (_DWORD)String1,
        (__int64)bstrString);
    }
    if ( _wcsnicmp(v19, L"https:", 6u) && _wcsnicmp(v19, L"http:", 5u) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
      }
    }
    else
    {
      if ( *(_DWORD *)(a1 + 208) )
      {
        v22 = L"enableAll";
LABEL_30:
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v29, v19);
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v22);
        }
        if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
          McTemplateU0zz_EventWriteTransfer(v23, NewWindowLaunchUrlEvent, v19, v20);
        v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 96) + 128LL))(*(_QWORD *)(a1 + 96), v29[0]);
        goto LABEL_41;
      }
      while ( v14 < *(_DWORD *)(a1 + 212) )
      {
        if ( (unsigned int)IsMatchingTerminateUrl(v19, *(wchar_t **)(a1 + 8LL * v14 + 216)) )
        {
          v22 = *(const wchar_t **)(a1 + 8LL * v14 + 216);
LABEL_29:
          v13 = a11;
          goto LABEL_30;
        }
        ++v14;
      }
      v22 = L"EnableTestAllNewWindow";
      if ( (unsigned int)GetAuthHostRegDWORDValue(L"EnableTestAllNewWindow") )
        goto LABEL_29;
      v13 = a11;
    }
    if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
      McTemplateU0zz_EventWriteTransfer(v21, NewWindowEvent, v19, v20);
    v24 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))(**(_QWORD **)(a1 + 72)
                                                                                               + 64LL))(
            *(_QWORD *)(a1 + 72),
            v19,
            0,
            0,
            0,
            0,
            0);
LABEL_41:
    v16 = v24;
    if ( v24 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        51,
        &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
        (unsigned int)v24);
    }
    *v28 = 0;
    *v13 = 1;
    goto LABEL_47;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    v18 = 47;
    goto LABEL_6;
  }
LABEL_47:
  SysFreeString(bstrString);
  SysFreeString(String1);
  return v16;
}

```

## disassembly

```asm
0x14000ad80  push    rbp
0x14000ad82  push    rbx
0x14000ad83  push    rsi
0x14000ad84  push    rdi
0x14000ad85  push    r12
0x14000ad87  push    r13
0x14000ad89  push    r14
0x14000ad8b  push    r15
0x14000ad8d  lea     rbp, [rsp-7]
0x14000ad92  sub     rsp, 98h
0x14000ad99  mov     rax, cs:__security_cookie
0x14000ada0  xor     rax, rsp
0x14000ada3  mov     [rbp+3Fh+var_50], rax
0x14000ada7  mov     r13, rcx
0x14000adaa  mov     rbx, [rbp+3Fh+arg_20]
0x14000adae  mov     rcx, [rbp+3Fh+arg_28]
0x14000adb2  mov     r15, [rbp+3Fh+arg_50]
0x14000adb9  mov     [rbp+3Fh+var_90], r15
0x14000adbd  mov     rax, [rbp+3Fh+arg_58]
0x14000adc4  mov     [rbp+3Fh+var_78], rax
0x14000adc8  xor     r14d, r14d
0x14000adcb  mov     [rbp+3Fh+String1], r14
0x14000adcf  mov     [rbp+3Fh+bstrString], r14
0x14000add3  mov     rax, [rcx]
0x14000add6  lea     rdx, [rbp+3Fh+String1]
0x14000adda  mov     rax, [rax+38h]
0x14000adde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ade3  mov     edi, eax
0x14000ade5  test    eax, eax
0x14000ade7  jns     short loc_14000AE31
0x14000ade9  lea     rsi, WPP_GLOBAL_Control
0x14000adf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000adf7  cmp     rcx, rsi
0x14000adfa  jz      loc_14000B087
0x14000ae00  mov     bl, 4
0x14000ae02  test    [rcx+44h], bl
0x14000ae05  jz      loc_14000B087
0x14000ae0b  cmp     byte ptr [rcx+41h], 5
0x14000ae0f  jb      loc_14000B087
0x14000ae15  lea     edx, [r14+2Eh]
0x14000ae19  mov     r9d, eax
0x14000ae1c  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000ae23  mov     rcx, [rcx+38h]
0x14000ae27  call    WPP_SF_d
0x14000ae2c  jmp     loc_14000B087
0x14000ae31  mov     rax, [rbx]
0x14000ae34  lea     rdx, [rbp+3Fh+bstrString]
0x14000ae38  mov     rcx, rbx
0x14000ae3b  mov     rax, [rax+38h]
0x14000ae3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae44  mov     edi, eax
0x14000ae46  test    eax, eax
0x14000ae48  jns     short loc_14000AE7D
0x14000ae4a  lea     rsi, WPP_GLOBAL_Control
0x14000ae51  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae58  cmp     rcx, rsi
0x14000ae5b  jz      loc_14000B087
0x14000ae61  mov     bl, 4
0x14000ae63  test    [rcx+44h], bl
0x14000ae66  jz      loc_14000B087
0x14000ae6c  cmp     byte ptr [rcx+41h], 5
0x14000ae70  jb      loc_14000B087
0x14000ae76  mov     edx, 2Fh ; '/'
0x14000ae7b  jmp     short loc_14000AE19
0x14000ae7d  mov     rdi, [rbp+3Fh+String1]
0x14000ae81  mov     r12, [rbp+3Fh+bstrString]
0x14000ae85  lea     rsi, WPP_GLOBAL_Control
0x14000ae8c  mov     bl, 4
0x14000ae8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae95  cmp     rcx, rsi
0x14000ae98  jz      short loc_14000AEC1
0x14000ae9a  test    [rcx+44h], bl
0x14000ae9d  jz      short loc_14000AEC1
0x14000ae9f  cmp     [rcx+41h], bl
0x14000aea2  jb      short loc_14000AEC1
0x14000aea4  mov     edx, 30h ; '0'
0x14000aea9  mov     [rsp+0D0h+var_B0], r12
0x14000aeae  mov     r9, rdi
0x14000aeb1  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000aeb8  mov     rcx, [rcx+38h]
0x14000aebc  call    WPP_SF_SS
0x14000aec1  mov     r8d, 6; MaxCount
0x14000aec7  lea     rdx, aHttps; "https:"
0x14000aece  mov     rcx, rdi; String1
0x14000aed1  call    cs:__imp__wcsnicmp
0x14000aed7  test    eax, eax
0x14000aed9  jz      short loc_14000AF31
0x14000aedb  mov     r8d, 5; MaxCount
0x14000aee1  lea     rdx, aHttp; "http:"
0x14000aee8  mov     rcx, rdi; String1
0x14000aeeb  call    cs:__imp__wcsnicmp
0x14000aef1  test    eax, eax
0x14000aef3  jz      short loc_14000AF31
0x14000aef5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aefc  cmp     rcx, rsi
0x14000aeff  jz      loc_14000B001
0x14000af05  test    [rcx+44h], bl
0x14000af08  jz      loc_14000B001
0x14000af0e  cmp     [rcx+41h], bl
0x14000af11  jb      loc_14000B001
0x14000af17  mov     edx, 31h ; '1'
0x14000af1c  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000af23  mov     rcx, [rcx+38h]
0x14000af27  call    WPP_SF_
0x14000af2c  jmp     loc_14000B001
0x14000af31  cmp     [r13+0D0h], r14d
0x14000af38  jz      short loc_14000AF43
0x14000af3a  lea     r14, aEnableall; "enableAll"
0x14000af41  jmp     short loc_14000AF89
0x14000af43  cmp     r14d, [r13+0D4h]
0x14000af4a  jnb     short loc_14000AF72
0x14000af4c  mov     r15d, r14d
0x14000af4f  mov     rdx, [r13+r15*8+0D8h]; wchar_t *
0x14000af57  mov     rcx, rdi; String1
0x14000af5a  call    _IsMatchingTerminateUrl
0x14000af5f  test    eax, eax
0x14000af61  jnz     short loc_14000AF68
0x14000af63  inc     r14d
0x14000af66  jmp     short loc_14000AF43
0x14000af68  mov     r14, [r13+r15*8+0D8h]
0x14000af70  jmp     short loc_14000AF85
0x14000af72  lea     r14, aEnabletestalln; "EnableTestAllNewWindow"
0x14000af79  mov     rcx, r14; lpValueName
0x14000af7c  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x14000af81  test    eax, eax
0x14000af83  jz      short loc_14000AFFA
0x14000af85  mov     r15, [rbp+3Fh+var_90]
0x14000af89  mov     rdx, rdi; unsigned __int16 *
0x14000af8c  lea     rcx, [rbp+3Fh+var_70]; this
0x14000af90  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x14000af95  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af9c  cmp     rcx, rsi
0x14000af9f  jz      short loc_14000AFC3
0x14000afa1  test    [rcx+44h], bl
0x14000afa4  jz      short loc_14000AFC3
0x14000afa6  cmp     [rcx+41h], bl
0x14000afa9  jb      short loc_14000AFC3
0x14000afab  mov     edx, 32h ; '2'
0x14000afb0  mov     r9, r14
0x14000afb3  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000afba  mov     rcx, [rcx+38h]
0x14000afbe  call    WPP_SF_S
0x14000afc3  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x14000afca  jz      short loc_14000AFDE
0x14000afcc  mov     r9, r12
0x14000afcf  mov     r8, rdi
0x14000afd2  lea     rdx, NewWindowLaunchUrlEvent
0x14000afd9  call    McTemplateU0zz_EventWriteTransfer
0x14000afde  mov     rcx, [r13+60h]
0x14000afe2  mov     rax, [rcx]
0x14000afe5  mov     rdx, [rbp+3Fh+var_70]
0x14000afe9  mov     rax, [rax+80h]
0x14000aff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aff5  xor     r14d, r14d
0x14000aff8  jmp     short loc_14000B044
0x14000affa  mov     r15, [rbp+3Fh+var_90]
0x14000affe  xor     r14d, r14d
0x14000b001  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x14000b008  jz      short loc_14000B01C
0x14000b00a  mov     r9, r12
0x14000b00d  mov     r8, rdi
0x14000b010  lea     rdx, NewWindowEvent
0x14000b017  call    McTemplateU0zz_EventWriteTransfer
0x14000b01c  mov     rcx, [r13+48h]
0x14000b020  mov     rax, [rcx]
0x14000b023  mov     [rsp+0D0h+var_A0], r14
0x14000b028  mov     [rsp+0D0h+var_A8], r14d
0x14000b02d  mov     [rsp+0D0h+var_B0], r14
0x14000b032  xor     r9d, r9d
0x14000b035  xor     r8d, r8d
0x14000b038  mov     rdx, rdi
0x14000b03b  mov     rax, [rax+40h]
0x14000b03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b044  mov     edi, eax
0x14000b046  test    eax, eax
0x14000b048  jns     short loc_14000B079
0x14000b04a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b051  cmp     rcx, rsi
0x14000b054  jz      short loc_14000B079
0x14000b056  test    [rcx+44h], bl
0x14000b059  jz      short loc_14000B079
0x14000b05b  cmp     byte ptr [rcx+41h], 2
0x14000b05f  jb      short loc_14000B079
0x14000b061  mov     edx, 33h ; '3'
0x14000b066  mov     r9d, eax
0x14000b069  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000b070  mov     rcx, [rcx+38h]
0x14000b074  call    WPP_SF_d
0x14000b079  mov     rax, [rbp+3Fh+var_78]
0x14000b07d  mov     [rax], r14
0x14000b080  mov     dword ptr [r15], 1
0x14000b087  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x14000b08b  call    cs:__imp_SysFreeString
0x14000b091  nop
0x14000b092  mov     rcx, [rbp+3Fh+String1]; bstrString
0x14000b096  call    cs:__imp_SysFreeString
0x14000b09c  mov     eax, edi
0x14000b09e  mov     rcx, [rbp+3Fh+var_50]
0x14000b0a2  xor     rcx, rsp; StackCookie
0x14000b0a5  call    __security_check_cookie
0x14000b0aa  add     rsp, 98h
0x14000b0b1  pop     r15
0x14000b0b3  pop     r14
0x14000b0b5  pop     r13
0x14000b0b7  pop     r12
0x14000b0b9  pop     rdi
0x14000b0ba  pop     rsi
0x14000b0bb  pop     rbx
0x14000b0bc  pop     rbp
0x14000b0bd  retn
```
