# AudMigLibCopyEndpointUpgradeProperties(IPropertyStore *,IPropertyStore *,IPropertyStore *,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009,int)

- ea: `0x180012acc`
- end: `0x180012e6e`
- name: `?AudMigLibCopyEndpointUpgradeProperties@@YAJPEAUIPropertyStore@@00W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009@@H@Z`
- size: `930`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013144`
- `0x18004f474`

## callees

- `0x180010dd0`
- `0x180012acc`
- `0x180012e80`
- `0x1800137e0`
- `0x18001f230`
- `0x180029024`
- `0x18003e920`
- `0x18003f780`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180012d36`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180012d36`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180012cef`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180012cef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012d09`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012d09`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012b65`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012dac`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012b65`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012dac`

## string_xrefs

- `0x180012de9`: `Failed to create key string at %d\n`
- `0x180012e5d`: `AudMigLibCopyEndpointUpgradeProperties: hResult: 0x%08x\n`

## pseudocode

```c
__int64 __fastcall AudMigLibCopyEndpointUpgradeProperties(__int64 a1, __int64 *a2, __int64 a3, unsigned int a4, int a5)
{
  __int64 v6; // rax
  unsigned int v7; // edi
  __int64 (__fastcall *v8)(__int64 *, unsigned int *); // rax
  __int64 v9; // rsi
  int v10; // ebx
  unsigned int i; // r15d
  __int64 v12; // rcx
  __int128 *p_Buf2; // r12
  __int64 v15; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+28h] [rbp-D8h]
  __int64 v17; // [rsp+30h] [rbp-D0h]
  __int64 v18; // [rsp+38h] [rbp-C8h]
  __int64 v19; // [rsp+40h] [rbp-C0h]
  __int64 v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  unsigned int v26; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v27; // [rsp+84h] [rbp-7Ch]
  __int128 *v28; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h]
  PROPVARIANT pvar[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-58h]
  __int64 v32; // [rsp+B0h] [rbp-50h]
  __int128 Buf2; // [rsp+B8h] [rbp-48h] BYREF
  int v34; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v35[128]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszIconFile[272]; // [rsp+1D0h] [rbp+D0h] BYREF
  WCHAR Dst[272]; // [rsp+3F0h] [rbp+2F0h] BYREF

  v32 = a1;
  v34 = 0;
  v31 = 0;
  v6 = *a2;
  v27 = a4;
  v29 = a3;
  v7 = a4;
  v26 = 0;
  v8 = *(__int64 (__fastcall **)(__int64 *, unsigned int *))(v6 + 24);
  v9 = a3;
  Buf2 = 0;
  *(_OWORD *)pvar = 0;
  v10 = v8(a2, &v26);
  if ( v10 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= v26 )
        goto LABEL_27;
      v28 = 0;
      PropVariantClear(pvar);
      v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int128 *))(*a2 + 32))(a2, i, &Buf2);
      if ( v10 < 0 )
      {
        AudMigLibSetupLog(L"Failed to get key at %d, continuing\r\n", i);
        v10 = 0;
      }
      else
      {
        if ( a5 )
        {
          p_Buf2 = &Buf2;
LABEL_7:
          LODWORD(v25) = v34;
          LODWORD(v24) = HIBYTE(Buf2);
          LODWORD(v23) = BYTE14(Buf2);
          LODWORD(v22) = BYTE13(Buf2);
          LODWORD(v21) = BYTE12(Buf2);
          LODWORD(v20) = BYTE11(Buf2);
          LODWORD(v19) = BYTE10(Buf2);
          LODWORD(v18) = BYTE9(Buf2);
          LODWORD(v17) = BYTE8(Buf2);
          LODWORD(v16) = WORD3(Buf2);
          LODWORD(v15) = WORD2(Buf2);
          v10 = StringCchPrintfW(
                  v35,
                  0x80u,
                  L"{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x},%d",
                  (unsigned int)Buf2,
                  v15,
                  v16,
                  v17,
                  v18,
                  v19,
                  v20,
                  v21,
                  v22,
                  v23,
                  v24,
                  v25);
          if ( v10 < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids);
LABEL_30:
            AudMigLibSetupLog(L"Failed to create key string at %d\r\n", i);
            goto LABEL_27;
          }
          if ( v10 < 0 )
            goto LABEL_30;
          v10 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, PROPVARIANT *))(*a2 + 40))(a2, &Buf2, pvar);
          if ( v10 < 0 )
          {
            AudMigLibSetupLog(L"Failed to get %s property at %d\r\n", v35, i);
            goto LABEL_27;
          }
          if ( v34 != 12 || memcmp_0(&PKEY_DeviceClass_IconPath, &Buf2, 0x10u) )
            goto LABEL_11;
          if ( LOWORD(pvar[0]) == 31
            && (int)StringCbCopyW(pszIconFile, 0x21Cu, (const unsigned __int16 *)pvar[1]) >= 0
            && ((PathParseIconLocationW(pszIconFile), ExpandEnvironmentStringsW(pszIconFile, Dst, 0x10Eu))
             || (int)StringCbCopyW(Dst, 0x21Cu, pszIconFile) >= 0) )
          {
            if ( !PathFileExistsW(Dst) )
            {
              AudMigLibSetupLog(L"Icon %s skipped for migration because it was not found\r\n", Dst);
              goto LABEL_23;
            }
LABEL_11:
            v10 = (*(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v32 + 48LL))(
                    v32,
                    p_Buf2,
                    pvar);
            if ( v10 < 0 )
            {
              AudMigLibSetupLog(L"Failed to set %s property at %d\r\n", v35, i);
              goto LABEL_27;
            }
            AudMigLibSetupLog(L"Migrated %s property at %d\r\n", v35, i);
          }
          else
          {
LABEL_23:
            AudMigLibSetupLog(L"Property %s skipped for migration because it was found to no longer be valid\r\n", v35);
          }
          v9 = v29;
          v7 = v27;
          continue;
        }
        if ( (unsigned int)IsEndpointUpgradeProperty(v12, v9, &Buf2, v7, &v28) )
        {
          p_Buf2 = v28;
          goto LABEL_7;
        }
      }
    }
  }
  AudMigLibSetupLog(L"No properties to migrate\r\n");
  v10 = 0;
LABEL_27:
  PropVariantClear(pvar);
  if ( v10 < 0 )
    AudMigLibSetupLog(L"AudMigLibCopyEndpointUpgradeProperties: hResult: 0x%08x\r\n", (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180012acc  mov     [rsp-8+arg_18], rbx
0x180012ad1  push    rbp
0x180012ad2  push    rsi
0x180012ad3  push    rdi
0x180012ad4  push    r12
0x180012ad6  push    r13
0x180012ad8  push    r14
0x180012ada  push    r15
0x180012adc  lea     rbp, [rsp-520h]
0x180012ae4  sub     rsp, 620h
0x180012aeb  mov     rax, cs:__security_cookie
0x180012af2  xor     rax, rsp
0x180012af5  mov     [rbp+550h+var_40], rax
0x180012afc  xor     eax, eax
0x180012afe  mov     [rbp+550h+var_5A0], rcx
0x180012b02  mov     [rbp+550h+var_588], eax
0x180012b05  mov     r13, rdx
0x180012b08  mov     [rbp+550h+var_5A8], rax
0x180012b0c  xorps   xmm0, xmm0
0x180012b0f  mov     rax, [rdx]
0x180012b12  xorps   xmm1, xmm1
0x180012b15  lea     rdx, [rbp+550h+var_5D0]
0x180012b19  mov     [rbp+550h+var_5CC], r9d
0x180012b1d  mov     rcx, r13
0x180012b20  mov     [rbp+550h+var_5C0], r8
0x180012b24  mov     edi, r9d
0x180012b27  mov     [rbp+550h+var_5D0], 0
0x180012b2e  mov     rax, [rax+18h]
0x180012b32  mov     rsi, r8
0x180012b35  movups  [rbp+550h+Buf2], xmm0
0x180012b39  movups  xmmword ptr [rbp+550h+pvar], xmm1
0x180012b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b42  mov     ebx, eax
0x180012b44  test    eax, eax
0x180012b46  js      loc_180012DF7
0x180012b4c  xor     r15d, r15d
0x180012b4f  cmp     r15d, [rbp+550h+var_5D0]
0x180012b53  jnb     loc_180012DA8
0x180012b59  lea     rcx, [rbp+550h+pvar]; pvar
0x180012b5d  mov     [rbp+550h+var_5C8], 0
0x180012b65  call    cs:__imp_PropVariantClear
0x180012b6b  mov     rax, [r13+0]
0x180012b6f  lea     r8, [rbp+550h+Buf2]
0x180012b73  mov     edx, r15d
0x180012b76  mov     rcx, r13
0x180012b79  mov     rax, [rax+20h]
0x180012b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b82  mov     ebx, eax
0x180012b84  test    eax, eax
0x180012b86  js      loc_180012C97
0x180012b8c  cmp     [rbp+550h+arg_20], 0
0x180012b93  jz      loc_180012D6C
0x180012b99  lea     r12, [rbp+550h+Buf2]
0x180012b9d  movzx   ecx, byte ptr [rbp+550h+Buf2+0Fh]
0x180012ba1  movzx   edx, byte ptr [rbp+550h+Buf2+0Eh]
0x180012ba5  movzx   r8d, byte ptr [rbp+550h+Buf2+0Dh]
0x180012baa  movzx   r9d, byte ptr [rbp+550h+Buf2+0Ch]
0x180012baf  mov     eax, [rbp+550h+var_588]
0x180012bb2  movzx   r10d, byte ptr [rbp+550h+Buf2+0Bh]
0x180012bb7  movzx   r11d, byte ptr [rbp+550h+Buf2+0Ah]
0x180012bbc  movzx   ebx, byte ptr [rbp+550h+Buf2+9]
0x180012bc0  movzx   edi, byte ptr [rbp+550h+Buf2+8]
0x180012bc4  movzx   esi, word ptr [rbp+550h+Buf2+6]
0x180012bc8  movzx   r14d, word ptr [rbp+550h+Buf2+4]
0x180012bcd  mov     [rsp+650h+var_5E0], eax
0x180012bd1  mov     dword ptr [rsp+650h+var_5E8], ecx
0x180012bd5  lea     rcx, [rbp+550h+var_580]; unsigned __int16 *
0x180012bd9  mov     dword ptr [rsp+650h+var_5F0], edx
0x180012bdd  mov     edx, 80h; unsigned __int64
0x180012be2  mov     dword ptr [rsp+650h+var_5F8], r8d
0x180012be7  lea     r8, a08x04x04x02x02; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x180012bee  mov     dword ptr [rsp+650h+var_600], r9d
0x180012bf3  mov     r9d, dword ptr [rbp+550h+Buf2]
0x180012bf7  mov     dword ptr [rsp+650h+var_608], r10d
0x180012bfc  mov     dword ptr [rsp+650h+var_610], r11d
0x180012c01  mov     dword ptr [rsp+650h+var_618], ebx
0x180012c05  mov     dword ptr [rsp+650h+var_620], edi
0x180012c09  mov     dword ptr [rsp+650h+var_628], esi
0x180012c0d  mov     dword ptr [rsp+650h+var_630], r14d
0x180012c12  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012c17  mov     ebx, eax
0x180012c19  test    eax, eax
0x180012c1b  js      loc_180012E07
0x180012c21  test    ebx, ebx
0x180012c23  js      loc_180012DE6
0x180012c29  mov     rax, [r13+0]
0x180012c2d  lea     r8, [rbp+550h+pvar]
0x180012c31  lea     rdx, [rbp+550h+Buf2]
0x180012c35  mov     rcx, r13
0x180012c38  mov     rax, [rax+28h]
0x180012c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c41  mov     ebx, eax
0x180012c43  test    eax, eax
0x180012c45  js      loc_180012D95
0x180012c4b  cmp     [rbp+550h+var_588], 0Ch
0x180012c4f  jz      short loc_180012CAA
0x180012c51  mov     rdi, [rbp+550h+var_5A0]
0x180012c55  lea     r8, [rbp+550h+pvar]
0x180012c59  mov     rdx, r12
0x180012c5c  mov     rcx, rdi
0x180012c5f  mov     rax, [rdi]
0x180012c62  mov     rax, [rax+30h]
0x180012c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c6b  lea     rdx, [rbp+550h+var_580]
0x180012c6f  mov     ebx, eax
0x180012c71  mov     r8d, r15d
0x180012c74  test    eax, eax
0x180012c76  js      loc_180012E4F
0x180012c7c  lea     rcx, aMigratedSPrope; "Migrated %s property at %d\r\n"
0x180012c83  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180012c88  mov     rsi, [rbp+550h+var_5C0]
0x180012c8c  mov     edi, [rbp+550h+var_5CC]
0x180012c8f  inc     r15d
0x180012c92  jmp     loc_180012B4F
0x180012c97  mov     edx, r15d
0x180012c9a  lea     rcx, aFailedToGetKey; "Failed to get key at %d, continuing\r\n"
0x180012ca1  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180012ca6  xor     ebx, ebx
0x180012ca8  jmp     short loc_180012C8F
0x180012caa  mov     r8d, 10h; Size
0x180012cb0  lea     rdx, [rbp+550h+Buf2]; Buf2
0x180012cb4  lea     rcx, PKEY_DeviceClass_IconPath; Buf1
0x180012cbb  call    memcmp_0
0x180012cc0  test    eax, eax
0x180012cc2  jnz     short loc_180012C51
0x180012cc4  cmp     word ptr [rbp+550h+pvar], 1Fh
0x180012cc9  jnz     loc_180012D57
0x180012ccf  mov     r8, [rbp+550h+pvar+8]; unsigned __int16 *
0x180012cd3  lea     rcx, [rbp+550h+pszIconFile]; unsigned __int16 *
0x180012cda  mov     edx, 21Ch; unsigned __int64
0x180012cdf  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180012ce4  test    eax, eax
0x180012ce6  js      short loc_180012D57
0x180012ce8  lea     rcx, [rbp+550h+pszIconFile]; pszIconFile
0x180012cef  call    cs:__imp_PathParseIconLocationW
0x180012cf5  mov     r8d, 10Eh; nSize
0x180012cfb  lea     rdx, [rbp+550h+Dst]; lpDst
0x180012d02  lea     rcx, [rbp+550h+pszIconFile]; lpSrc
0x180012d09  call    cs:__imp_ExpandEnvironmentStringsW
0x180012d0f  test    eax, eax
0x180012d11  jnz     short loc_180012D2F
0x180012d13  lea     r8, [rbp+550h+pszIconFile]; unsigned __int16 *
0x180012d1a  mov     edx, 21Ch; unsigned __int64
0x180012d1f  lea     rcx, [rbp+550h+Dst]; unsigned __int16 *
0x180012d26  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180012d2b  test    eax, eax
0x180012d2d  js      short loc_180012D57
0x180012d2f  lea     rcx, [rbp+550h+Dst]; pszPath
0x180012d36  call    cs:__imp_PathFileExistsW
0x180012d3c  test    eax, eax
0x180012d3e  jnz     loc_180012C51
0x180012d44  lea     rdx, [rbp+550h+Dst]
0x180012d4b  lea     rcx, aIconSSkippedFo; "Icon %s skipped for migration because i"...
0x180012d52  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180012d57  lea     rdx, [rbp+550h+var_580]
0x180012d5b  lea     rcx, aPropertySSkipp; "Property %s skipped for migration becau"...
0x180012d62  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180012d67  jmp     loc_180012C88
0x180012d6c  lea     rax, [rbp+550h+var_5C8]
0x180012d70  mov     r9d, edi
0x180012d73  lea     r8, [rbp+550h+Buf2]
0x180012d77  mov     [rsp+650h+var_630], rax
0x180012d7c  mov     rdx, rsi
0x180012d7f  call    ?IsEndpointUpgradeProperty@@YAHPEAUIPropertyStore@@0PEBU_tagpropertykey@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009@@PEAPEBU2@@Z; IsEndpointUpgradeProperty(IPropertyStore *,IPropertyStore *,_tagpropertykey const *,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0009,_tagpropertykey const * *)
0x180012d84  test    eax, eax
0x180012d86  jz      loc_180012C8F
0x180012d8c  mov     r12, [rbp+550h+var_5C8]
0x180012d90  jmp     loc_180012B9D
0x180012d95  mov     r8d, r15d
0x180012d98  lea     rdx, [rbp+550h+var_580]
0x180012d9c  lea     rcx, aFailedToGetSPr; "Failed to get %s property at %d\r\n"
0x180012da3  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180012da8  lea     rcx, [rbp+550h+pvar]; pvar
0x180012dac  call    cs:__imp_PropVariantClear
0x180012db2  test    ebx, ebx
0x180012db4  js      loc_180012E5B
0x180012dba  mov     eax, ebx
0x180012dbc  mov     rcx, [rbp+550h+var_40]
0x180012dc3  xor     rcx, rsp; StackCookie
0x180012dc6  call    __security_check_cookie
0x180012dcb  mov     rbx, [rsp+650h+arg_18]
0x180012dd3  add     rsp, 620h
0x180012dda  pop     r15
0x180012ddc  pop     r14
0x180012dde  pop     r13
0x180012de0  pop     r12
0x180012de2  pop     rdi
0x180012de3  pop     rsi
0x180012de4  pop     rbp
0x180012de5  retn
0x180012de6  mov     edx, r15d
0x180012de9  lea     rcx, aFailedToCreate_0; "Failed to create key string at %d\r\n"
0x180012df0  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180012df5  jmp     short loc_180012DA8
0x180012df7  lea     rcx, aNoPropertiesTo; "No properties to migrate\r\n"
0x180012dfe  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180012e03  xor     ebx, ebx
0x180012e05  jmp     short loc_180012DA8
0x180012e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e0e  lea     rax, WPP_GLOBAL_Control
0x180012e15  cmp     rcx, rax
0x180012e18  jz      loc_180012C21
0x180012e1e  test    dword ptr [rcx+1Ch], 80000h
0x180012e25  jz      loc_180012C21
0x180012e2b  cmp     byte ptr [rcx+19h], 2
0x180012e2f  jb      loc_180012C21
0x180012e35  mov     rcx, [rcx+10h]
0x180012e39  lea     r8, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids
0x180012e40  mov     edx, 0Ah
0x180012e45  mov     r9d, ebx
0x180012e48  call    WPP_SF_d
0x180012e4d  jmp     short loc_180012DE6
0x180012e4f  lea     rcx, aFailedToSetSPr; "Failed to set %s property at %d\r\n"
0x180012e56  jmp     loc_180012DA3
0x180012e5b  mov     edx, ebx
0x180012e5d  lea     rcx, aAudmiglibcopye; "AudMigLibCopyEndpointUpgradeProperties:"...
0x180012e64  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180012e69  jmp     loc_180012DBA
```
