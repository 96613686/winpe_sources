# Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateClassicAppCompatKey(ushort const *,int)

- ea: `0x180020360`
- end: `0x180020b33`
- name: `?ValidateClassicAppCompatKey@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAA_NPEBGH@Z`
- size: `2003`
- prototype: `bool(Appx::Packaging::Manifest::AppxManifestReaderImpl *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c8a8`

## callees

- `0x180020360`
- `0x18004afdc`
- `0x1800992a0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020600`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002062a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002065a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002068d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800206b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020954`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020983`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800209b3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800209e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020a34`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020a5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020a87`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020600`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002062a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002065a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002068d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800206b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020954`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020983`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800209b3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800209e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020a34`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020a5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020a87`

## pseudocode

```c
bool __fastcall Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateClassicAppCompatKey(
        Appx::Packaging::Manifest::AppxManifestReaderImpl *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  unsigned int v6; // r9d
  unsigned __int16 *v7; // r8
  WCHAR v8[8]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String2[20]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v10[16]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t v11[28]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR v12[24]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v13[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v14; // [rsp+100h] [rbp+0h]
  __int128 v15; // [rsp+110h] [rbp+10h]
  __int128 v16; // [rsp+120h] [rbp+20h]
  __int64 v17; // [rsp+130h] [rbp+30h]
  _OWORD v18[6]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v19[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR v20[56]; // [rsp+1E0h] [rbp+E0h] BYREF
  WCHAR v21[40]; // [rsp+250h] [rbp+150h] BYREF
  _OWORD v22[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _OWORD v23[6]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v24[8]; // [rsp+380h] [rbp+280h] BYREF
  __int128 v25; // [rsp+390h] [rbp+290h]
  __int128 v26; // [rsp+3A0h] [rbp+2A0h]
  __int128 v27; // [rsp+3B0h] [rbp+2B0h]
  __int128 v28; // [rsp+3C0h] [rbp+2C0h]
  __int128 v29; // [rsp+3D0h] [rbp+2D0h]
  __int128 v30; // [rsp+3E0h] [rbp+2E0h]
  _OWORD v31[2]; // [rsp+3F0h] [rbp+2F0h]
  WCHAR v32[88]; // [rsp+410h] [rbp+310h] BYREF
  _OWORD v33[5]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _OWORD v34[2]; // [rsp+510h] [rbp+410h]
  WCHAR v35[72]; // [rsp+530h] [rbp+430h] BYREF

  wcscpy(String2, L"hkey_current_user");
  wcscpy(v8, L"hkcu");
  wcscpy(v11, L"hkey_local_machine\\software");
  *(_OWORD *)v10 = *(_OWORD *)L"hklm\\software";
  *(_OWORD *)&v10[6] = *(_OWORD *)L"oftware";
  wcscpy(v21, L"hkey_local_machine\\software\\crosoft");
  wcscpy(v12, L"hklm\\software\\microsoft");
  wcscpy((wchar_t *)v23, L"hkey_local_machine\\software\\micros\\office");
  wcscpy((wchar_t *)v19, L"hklm\\software\\microsof\\office");
  wcscpy(v35, L"hkey_local_machine\\software\\microsoft\\fusion\\publisherpolidefault");
  v33[0] = *(_OWORD *)L"hklm\\software\\microsoft\\fusion\\publisherpolicy\\default";
  v33[2] = *(_OWORD *)L"crosoft\\fusion\\publisherpolicy\\default";
  v33[1] = *(_OWORD *)L"tware\\microsoft\\fusion\\publisherpolicy\\default";
  v33[4] = *(_OWORD *)L"ublisherpolicy\\default";
  v33[3] = *(_OWORD *)L"fusion\\publisherpolicy\\default";
  v34[0] = *(_OWORD *)L"policy\\default";
  *(_OWORD *)((char *)v34 + 14) = *(_OWORD *)L"default";
  if ( a3 < 0x11 )
  {
    if ( a3 < 4 )
      goto LABEL_26;
  }
  else if ( CompareStringOrdinal(a2, 17, String2, 17, 1) == 2 )
  {
    return 1;
  }
  if ( CompareStringOrdinal(a2, 4, v8, 4, 1) == 2 )
    return 1;
  if ( a3 >= 0x1B && CompareStringOrdinal(a2, 27, v11, 27, 1) == 2 )
  {
LABEL_6:
    if ( a3 < 0x25 )
    {
      if ( a3 < 0x17 )
      {
LABEL_9:
        wcscpy(v20, L"hkey_local_machine\\software\\wow6432node\\microsoft");
        *(_OWORD *)v13 = *(_OWORD *)L"hklm\\software\\wow6432node\\microsoft";
        v14 = *(_OWORD *)L"tware\\wow6432node\\microsoft";
        v15 = *(_OWORD *)L"w6432node\\microsoft";
        v16 = *(_OWORD *)L"e\\microsoft";
        v17 = *(_QWORD *)L"oft";
        wcscpy((wchar_t *)v22, L"hkey_local_machine\\software\\wow6432node\\microsoft\\office");
        wcscpy((wchar_t *)v18, L"hklm\\software\\wow6432node\\microsoft\\ofice");
        wcscpy(v32, L"hkey_local_machine\\software\\wow6432node\\microsoft\\fusion\\publisherpolicy\\default");
        *(_OWORD *)v24 = *(_OWORD *)L"hklm\\software\\wow6432node\\microsoft\\fusion\\publisherpolicy\\default";
        v25 = *(_OWORD *)L"tware\\wow6432node\\microsoft\\fusion\\publisherpolicy\\default";
        v26 = *(_OWORD *)L"w6432node\\microsoft\\fusion\\publisherpolicy\\default";
        v27 = *(_OWORD *)L"e\\microsoft\\fusion\\publisherpolicy\\default";
        v29 = *(_OWORD *)L"on\\publisherpolicy\\default";
        v28 = *(_OWORD *)L"oft\\fusion\\publisherpolicy\\default";
        v31[0] = *(_OWORD *)L"cy\\default";
        *(_QWORD *)((char *)v31 + 14) = *(_QWORD *)L"ult";
        v30 = *(_OWORD *)L"sherpolicy\\default";
        if ( (a3 < 0x31 || CompareStringOrdinal(a2, 49, v20, 49, 1) != 2)
          && !(unsigned int)Common::String::CaseInsensitiveStartsWith(a2, a3, v13, 0x23u) )
        {
          return 1;
        }
        if ( a3 < 0x38 )
        {
          if ( a3 < 0x2A )
          {
LABEL_32:
            v6 = 66;
            v7 = v24;
            return (unsigned int)Common::String::CaseInsensitiveStartsWith(a2, a3, v7, v6) != 0;
          }
        }
        else if ( CompareStringOrdinal(a2, 56, (LPCWCH)v22, 56, 1) == 2 )
        {
          return 1;
        }
        if ( CompareStringOrdinal(a2, 42, (LPCWCH)v18, 42, 1) == 2
          || a3 >= 0x50 && CompareStringOrdinal(a2, 80, v32, 80, 1) == 2 )
        {
          return 1;
        }
        goto LABEL_32;
      }
    }
    else if ( CompareStringOrdinal(a2, 37, v21, 37, 1) == 2 )
    {
      goto LABEL_19;
    }
    if ( CompareStringOrdinal(a2, 23, v12, 23, 1) != 2 )
      goto LABEL_9;
LABEL_19:
    if ( a3 < 0x2C )
    {
      if ( a3 < 0x1E )
      {
LABEL_24:
        v6 = 54;
        v7 = (unsigned __int16 *)v33;
        return (unsigned int)Common::String::CaseInsensitiveStartsWith(a2, a3, v7, v6) != 0;
      }
    }
    else if ( CompareStringOrdinal(a2, 44, (LPCWCH)v23, 44, 1) == 2 )
    {
      return 1;
    }
    if ( CompareStringOrdinal(a2, 30, (LPCWCH)v19, 30, 1) == 2
      || a3 >= 0x44 && CompareStringOrdinal(a2, 68, v35, 68, 1) == 2 )
    {
      return 1;
    }
    goto LABEL_24;
  }
LABEL_26:
  if ( (unsigned int)Common::String::CaseInsensitiveStartsWith(a2, a3, v10, 0xDu) )
    goto LABEL_6;
  return 0;
}

```

## disassembly

```asm
0x180020360  push    rbp
0x180020362  push    rbx
0x180020363  push    rsi
0x180020364  push    rdi
0x180020365  lea     rbp, [rsp-4D8h]
0x18002036d  sub     rsp, 5D8h
0x180020374  mov     rax, cs:__security_cookie
0x18002037b  xor     rax, rsp
0x18002037e  mov     [rbp+4F0h+var_30], rax
0x180020385  movups  xmm0, xmmword ptr cs:aHkeyCurrentUse; "hkey_current_user"
0x18002038c  mov     eax, dword ptr cs:aHkeyCurrentUse+20h; "r"
0x180020392  mov     edi, r8d
0x180020395  movups  xmm1, xmmword ptr cs:aHkeyCurrentUse+10h; "rent_user"
0x18002039c  mov     [rsp+5F0h+var_590], eax
0x1800203a0  mov     rbx, rdx
0x1800203a3  movzx   eax, word ptr cs:aHkcu+8; ""
0x1800203aa  movups  xmmword ptr [rsp+5F0h+String2], xmm0
0x1800203af  mov     [rsp+5F0h+var_5B8], ax
0x1800203b4  movsd   xmm0, qword ptr cs:aHkcu; "hkcu"
0x1800203bc  movsd   qword ptr [rsp+5F0h+var_5C0], xmm0
0x1800203c2  movups  xmm0, xmmword ptr cs:aHkeyLocalMachi; "hkey_local_machine\\software"
0x1800203c9  movups  [rsp+5F0h+var_5A0], xmm1
0x1800203ce  movups  xmm1, xmmword ptr cs:aHkeyLocalMachi+10h; "al_machine\\software"
0x1800203d5  movups  xmmword ptr [rbp+4F0h+var_568], xmm0
0x1800203d9  movups  xmm0, xmmword ptr cs:aHkeyLocalMachi+20h; "ne\\software"
0x1800203e0  movups  xmmword ptr [rbp+4F0h+var_568+10h], xmm1
0x1800203e4  movsd   xmm1, qword ptr cs:aHkeyLocalMachi+30h; "are"
0x1800203ec  movups  [rbp+4F0h+var_548], xmm0
0x1800203f0  movups  xmm0, xmmword ptr cs:aHklmSoftware; "hklm\\software"
0x1800203f7  movsd   [rbp+4F0h+var_538], xmm1
0x1800203fc  movups  xmm1, xmmword ptr cs:aHklmSoftware+0Ch; "oftware"
0x180020403  movups  xmmword ptr [rsp+5F0h+var_588], xmm0
0x180020408  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_3; "hkey_local_machine\\software\\microsoft"
0x18002040f  movups  xmmword ptr [rsp+5F0h+var_588+0Ch], xmm1
0x180020414  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_3+10h; "al_machine\\software\\microsoft"
0x18002041b  movaps  xmmword ptr [rbp+4F0h+var_3A0], xmm0
0x180020422  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_3+20h; "ne\\software\\microsoft"
0x180020429  movaps  xmmword ptr [rbp+160h], xmm1
0x180020430  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_3+30h; "are\\microsoft"
0x180020437  movaps  [rbp+4F0h+var_380], xmm0
0x18002043e  movups  xmm0, xmmword ptr cs:aHkeyLocalMachi_3+3Ch; "crosoft"
0x180020445  movaps  [rbp+4F0h+var_370], xmm1
0x18002044c  movups  xmm1, xmmword ptr cs:aHklmSoftwareMi_1; "hklm\\software\\microsoft"
0x180020453  movups  [rbp+4F0h+var_370+0Ch], xmm0
0x18002045a  movups  xmm0, xmmword ptr cs:aHklmSoftwareMi_1+10h; "tware\\microsoft"
0x180020461  movups  xmmword ptr [rbp+4F0h+var_530], xmm1
0x180020465  movups  xmm1, xmmword ptr cs:aHklmSoftwareMi_1+20h; "crosoft"
0x18002046c  movups  [rbp+4F0h+var_520], xmm0
0x180020470  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_4; "hkey_local_machine\\software\\microsoft"...
0x180020477  movups  [rbp+4F0h+var_510], xmm1
0x18002047b  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_4+10h; "al_machine\\software\\microsoft\\office"
0x180020482  movaps  xmmword ptr [rbp+4F0h+var_2D0], xmm0
0x180020489  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_4+20h; "ne\\software\\microsoft\\office"
0x180020490  movaps  xmmword ptr [rbp+4F0h+var_2D0+10h], xmm1
0x180020497  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_4+30h; "are\\microsoft\\office"
0x18002049e  movaps  xmmword ptr [rbp+4F0h+var_2D0+20h], xmm0
0x1800204a5  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_4+40h; "osoft\\office"
0x1800204ac  movaps  [rbp+4F0h+var_290], xmm0
0x1800204b3  movups  xmm0, xmmword ptr cs:aHklmSoftwareMi; "hklm\\software\\microsoft\\office"
0x1800204ba  movaps  [rbp+4F0h+var_2A0], xmm1
0x1800204c1  movups  xmm1, xmmword ptr cs:aHkeyLocalMachi_4+4Ah; "\\office"
0x1800204c8  movups  xmmword ptr [rbp+4F0h+var_450], xmm0
0x1800204cf  movups  xmm0, xmmword ptr cs:aHklmSoftwareMi+20h; "crosoft\\office"
0x1800204d6  movups  [rbp+4F0h+var_290+0Ah], xmm1
0x1800204dd  movups  xmm1, xmmword ptr cs:aHklmSoftwareMi+10h; "tware\\microsoft\\office"
0x1800204e4  movups  [rbp+4F0h+var_430], xmm0
0x1800204eb  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_0; "hkey_local_machine\\software\\microsoft"...
0x1800204f2  movups  xmmword ptr [rbp+4F0h+var_450+10h], xmm1
0x1800204f9  movups  xmm1, xmmword ptr cs:aHklmSoftwareMi+2Eh; "\\office"
0x180020500  movups  xmmword ptr [rbp+4F0h+var_C0], xmm0
0x180020507  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_0+20h; "ne\\software\\microsoft\\fusion\\publis"...
0x18002050e  movups  [rbp+4F0h+var_430+0Eh], xmm1
0x180020515  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_0+10h; "al_machine\\software\\microsoft\\fusion"...
0x18002051c  movups  xmmword ptr [rbp+440h], xmm1
0x180020523  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_0+30h; "are\\microsoft\\fusion\\publisherpolicy"...
0x18002052a  movups  xmmword ptr [rbp+450h], xmm0
0x180020531  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_0+40h; "osoft\\fusion\\publisherpolicy\\default"
0x180020538  movups  xmmword ptr [rbp+460h], xmm1
0x18002053f  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_0+50h; "sion\\publisherpolicy\\default"
0x180020546  movups  [rbp+4F0h+var_80], xmm0
0x18002054d  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_0+60h; "lisherpolicy\\default"
0x180020554  movups  [rbp+4F0h+var_70], xmm1
0x18002055b  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_0+70h; "licy\\default"
0x180020562  movups  [rbp+4F0h+var_60], xmm0
0x180020569  movups  xmm0, xmmword ptr cs:aHkeyLocalMachi_0+7Ah; "default"
0x180020570  movups  [rbp+4F0h+var_50], xmm1
0x180020577  movaps  xmm1, xmmword ptr cs:aHklmSoftwareMi_0; "hklm\\software\\microsoft\\fusion\\publ"...
0x18002057e  movups  [rbp+4F0h+var_50+0Ah], xmm0
0x180020585  movaps  xmm0, xmmword ptr cs:aHklmSoftwareMi_0+10h; "tware\\microsoft\\fusion\\publisherpoli"...
0x18002058c  movaps  [rbp+4F0h+var_130], xmm1
0x180020593  movaps  xmm1, xmmword ptr cs:aHklmSoftwareMi_0+20h; "crosoft\\fusion\\publisherpolicy\\defau"...
0x18002059a  mov     esi, 1
0x18002059f  movaps  [rbp+4F0h+var_110], xmm1
0x1800205a6  movaps  xmm1, xmmword ptr cs:aHklmSoftwareMi_0+40h; "ublisherpolicy\\default"
0x1800205ad  movaps  [rbp+4F0h+var_120], xmm0
0x1800205b4  movaps  xmm0, xmmword ptr cs:aHklmSoftwareMi_0+30h; "fusion\\publisherpolicy\\default"
0x1800205bb  lea     edx, [rsi+10h]; cchCount1
0x1800205be  movaps  [rbp+4F0h+var_F0], xmm1
0x1800205c5  movaps  [rbp+4F0h+var_100], xmm0
0x1800205cc  movaps  xmm0, xmmword ptr cs:aHklmSoftwareMi_0+50h; "policy\\default"
0x1800205d3  movaps  xmmword ptr [rbp+4F0h+var_E0], xmm0
0x1800205da  movups  xmm1, xmmword ptr cs:aHklmSoftwareMi_0+5Eh; "default"
0x1800205e1  movups  xmmword ptr [rbp+4F0h+var_E0+0Eh], xmm1
0x1800205e8  cmp     r8d, edx
0x1800205eb  jb      loc_180020AAB
0x1800205f1  mov     r9d, edx; cchCount2
0x1800205f4  mov     [rsp+5F0h+bIgnoreCase], esi; bIgnoreCase
0x1800205f8  lea     r8, [rsp+5F0h+String2]; lpString2
0x1800205fd  mov     rcx, rbx; lpString1
0x180020600  call    cs:__imp_CompareStringOrdinal
0x180020607  nop     dword ptr [rax+rax+00h]
0x18002060c  cmp     eax, 2
0x18002060f  jz      loc_1800209F7
0x180020615  mov     r9d, 4; cchCount2
0x18002061b  mov     [rsp+5F0h+bIgnoreCase], esi; bIgnoreCase
0x18002061f  mov     edx, r9d; cchCount1
0x180020622  lea     r8, [rsp+5F0h+var_5C0]; lpString2
0x180020627  mov     rcx, rbx; lpString1
0x18002062a  call    cs:__imp_CompareStringOrdinal
0x180020631  nop     dword ptr [rax+rax+00h]
0x180020636  cmp     eax, 2
0x180020639  jz      loc_1800209F7
0x18002063f  mov     edx, 1Bh; cchCount1
0x180020644  cmp     edi, edx
0x180020646  jb      loc_180020AB4
0x18002064c  mov     r9d, edx; cchCount2
0x18002064f  mov     [rsp+5F0h+bIgnoreCase], esi; bIgnoreCase
0x180020653  lea     r8, [rbp+4F0h+var_568]; lpString2
0x180020657  mov     rcx, rbx; lpString1
0x18002065a  call    cs:__imp_CompareStringOrdinal
0x180020661  nop     dword ptr [rax+rax+00h]
0x180020666  cmp     eax, 2
0x180020669  jnz     loc_180020AB4
0x18002066f  mov     edx, 25h ; '%'; cchCount1
0x180020674  cmp     edi, edx
0x180020676  jb      loc_180020AD8
0x18002067c  mov     r9d, edx; cchCount2
0x18002067f  mov     [rsp+5F0h+bIgnoreCase], esi; bIgnoreCase
0x180020683  lea     r8, [rbp+4F0h+var_3A0]; lpString2
0x18002068a  mov     rcx, rbx; lpString1
0x18002068d  call    cs:__imp_CompareStringOrdinal
0x180020694  nop     dword ptr [rax+rax+00h]
0x180020699  cmp     eax, 2
0x18002069c  jz      loc_180020A16
0x1800206a2  mov     r9d, 17h; cchCount2
0x1800206a8  mov     [rsp+5F0h+bIgnoreCase], esi; bIgnoreCase
0x1800206ac  mov     edx, r9d; cchCount1
0x1800206af  lea     r8, [rbp+4F0h+var_530]; lpString2
0x1800206b3  mov     rcx, rbx; lpString1
0x1800206b6  call    cs:__imp_CompareStringOrdinal
0x1800206bd  nop     dword ptr [rax+rax+00h]
0x1800206c2  cmp     eax, 2
0x1800206c5  jz      loc_180020A16
0x1800206cb  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_1; "hkey_local_machine\\software\\wow6432no"...
0x1800206d2  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_1+10h; "al_machine\\software\\wow6432node\\micr"...
0x1800206d9  mov     eax, dword ptr cs:aHkeyLocalMachi_1+60h; "t"
0x1800206df  movaps  xmmword ptr [rbp+4F0h+var_410], xmm0
0x1800206e6  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_1+20h; "ne\\software\\wow6432node\\microsoft"
0x1800206ed  movaps  xmmword ptr [rbp+0F0h], xmm1
0x1800206f4  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_1+30h; "are\\wow6432node\\microsoft"
0x1800206fb  movaps  xmmword ptr [rbp+100h], xmm0
0x180020702  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_1+40h; "432node\\microsoft"
0x180020709  movaps  [rbp+4F0h+var_3E0], xmm1
0x180020710  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_1+50h; "microsoft"
0x180020717  movaps  [rbp+4F0h+var_3D0], xmm0
0x18002071e  movaps  xmm0, xmmword ptr cs:aHklmSoftwareWo_0; "hklm\\software\\wow6432node\\microsoft"
0x180020725  movaps  [rbp+4F0h+var_3C0], xmm1
0x18002072c  movaps  xmm1, xmmword ptr cs:aHklmSoftwareWo_0+10h; "tware\\wow6432node\\microsoft"
0x180020733  movaps  xmmword ptr [rbp+4F0h+var_500], xmm0
0x180020737  movaps  xmm0, xmmword ptr cs:aHklmSoftwareWo_0+20h; "w6432node\\microsoft"
0x18002073e  movaps  [rbp+4F0h+var_4F0], xmm1
0x180020742  movaps  xmm1, xmmword ptr cs:aHklmSoftwareWo_0+30h; "e\\microsoft"
0x180020749  movaps  [rbp+4F0h+var_4E0], xmm0
0x18002074d  movsd   xmm0, qword ptr cs:aHklmSoftwareWo_0+40h; "oft"
0x180020755  movaps  [rbp+4F0h+var_4D0], xmm1
0x180020759  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_5; "hkey_local_machine\\software\\wow6432no"...
0x180020760  movsd   [rbp+4F0h+var_4C0], xmm0
0x180020765  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_5+10h; "al_machine\\software\\wow6432node\\micr"...
0x18002076c  movaps  xmmword ptr [rbp+4F0h+var_350], xmm1
0x180020773  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_5+20h; "ne\\software\\wow6432node\\microsoft\\o"...
0x18002077a  movaps  xmmword ptr [rbp+4F0h+var_350+10h], xmm0
0x180020781  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_5+30h; "are\\wow6432node\\microsoft\\office"
0x180020788  movaps  xmmword ptr [rbp+4F0h+var_350+20h], xmm1
0x18002078f  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_5+40h; "432node\\microsoft\\office"
0x180020796  movaps  xmmword ptr [rbp+4F0h+var_350+30h], xmm0
0x18002079d  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_5+50h; "microsoft\\office"
0x1800207a4  movaps  [rbp+4F0h+var_310], xmm1
0x1800207ab  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_5+60h; "t\\office"
0x1800207b2  movaps  [rbp+4F0h+var_300], xmm0
0x1800207b9  movaps  xmm0, xmmword ptr cs:aHklmSoftwareWo; "hklm\\software\\wow6432node\\microsoft"...
0x1800207c0  movaps  [rbp+4F0h+var_2F0], xmm1
0x1800207c7  movaps  xmm1, xmmword ptr cs:aHklmSoftwareWo+10h; "tware\\wow6432node\\microsoft\\office"
0x1800207ce  movaps  xmmword ptr [rbp+4F0h+var_4B0], xmm0
0x1800207d2  movaps  xmm0, xmmword ptr cs:aHklmSoftwareWo+20h; "w6432node\\microsoft\\office"
0x1800207d9  movaps  xmmword ptr [rbp+4F0h+var_4B0+10h], xmm1
0x1800207dd  movaps  xmm1, xmmword ptr cs:aHklmSoftwareWo+30h; "e\\microsoft\\office"
0x1800207e4  movaps  xmmword ptr [rbp+4F0h+var_4B0+20h], xmm0
0x1800207e8  movaps  xmm0, xmmword ptr cs:aHklmSoftwareWo+40h; "oft\\office"
0x1800207ef  movaps  [rbp+4F0h+var_480], xmm1
0x1800207f3  movsd   xmm1, qword ptr cs:aHklmSoftwareWo+4Eh; "ice"
0x1800207fb  movaps  [rbp+4F0h+var_470], xmm0
0x180020802  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_2; "hkey_local_machine\\software\\wow6432no"...
0x180020809  movsd   qword ptr [rbp+4F0h+var_470+0Eh], xmm1
0x180020811  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_2+10h; "al_machine\\software\\wow6432node\\micr"...
0x180020818  movups  xmmword ptr [rbp+4F0h+var_1E0], xmm0
0x18002081f  mov     [rbp+4F0h+var_3B0], eax
0x180020825  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_2+20h; "ne\\software\\wow6432node\\microsoft\\f"...
0x18002082c  movzx   eax, word ptr cs:aHkeyLocalMachi_5+70h; ""
0x180020833  movups  xmmword ptr [rbp+320h], xmm1
0x18002083a  mov     [rbp+4F0h+var_2E0], ax
0x180020841  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_2+30h; "are\\wow6432node\\microsoft\\fusion\\pu"...
0x180020848  movzx   eax, word ptr cs:aHkeyLocalMachi_2+0A0h; ""
0x18002084f  movups  xmmword ptr [rbp+330h], xmm0
0x180020856  mov     [rbp+4F0h+var_140], ax
0x18002085d  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_2+40h; "432node\\microsoft\\fusion\\publisherpo"...
0x180020864  movups  xmmword ptr [rbp+340h], xmm1
0x18002086b  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_2+50h; "microsoft\\fusion\\publisherpolicy\\def"...
0x180020872  movups  xmmword ptr [rbp+350h], xmm0
0x180020879  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_2+60h; "t\\fusion\\publisherpolicy\\default"
0x180020880  movups  [rbp+4F0h+var_190], xmm1
0x180020887  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_2+70h; "\\publisherpolicy\\default"
0x18002088e  movups  [rbp+4F0h+var_180], xmm0
0x180020895  movaps  xmm0, xmmword ptr cs:aHkeyLocalMachi_2+80h; "erpolicy\\default"
0x18002089c  movups  [rbp+4F0h+var_170], xmm1
0x1800208a3  movaps  xmm1, xmmword ptr cs:aHkeyLocalMachi_2+90h; "\\default"
0x1800208aa  movups  [rbp+4F0h+var_160], xmm0
0x1800208b1  movaps  xmm0, xmmword ptr cs:aHklmSoftwareWo_1; "hklm\\software\\wow6432node\\microsoft"...
0x1800208b8  movups  [rbp+4F0h+var_150], xmm1
0x1800208bf  movaps  xmm1, xmmword ptr cs:aHklmSoftwareWo_1+10h; "tware\\wow6432node\\microsoft\\fusion\\"...
0x1800208c6  movups  xmmword ptr [rbp+4F0h+var_270], xmm0
0x1800208cd  movaps  xmm0, xmmword ptr cs:aHklmSoftwareWo_1+20h; "w6432node\\microsoft\\fusion\\publisher"...
0x1800208d4  movups  [rbp+4F0h+var_260], xmm1
0x1800208db  movaps  xmm1, xmmword ptr cs:aHklmSoftwareWo_1+30h; "e\\microsoft\\fusion\\publisherpolicy\\"...
0x1800208e2  movups  [rbp+4F0h+var_250], xmm0
0x1800208e9  movaps  xmm0, xmmword ptr cs:aHklmSoftwareWo_1+40h; "oft\\fusion\\publisherpolicy\\default"
0x1800208f0  mov     edx, 31h ; '1'; cchCount1
0x1800208f5  mov     rax, qword ptr cs:aHklmSoftwareWo_1+7Eh; "ult"
0x1800208fc  movups  [rbp+4F0h+var_240], xmm1
0x180020903  movaps  xmm1, xmmword ptr cs:aHklmSoftwareWo_1+50h; "on\\publisherpolicy\\default"
0x18002090a  movups  [rbp+4F0h+var_220], xmm1
0x180020911  movaps  xmm1, xmmword ptr cs:aHklmSoftwareWo_1+70h; "cy\\default"
0x180020918  movups  [rbp+4F0h+var_230], xmm0
0x18002091f  movaps  xmm0, xmmword ptr cs:aHklmSoftwareWo_1+60h; "sherpolicy\\default"
0x180020926  movups  xmmword ptr [rbp+4F0h+var_200], xmm1
0x18002092d  mov     qword ptr [rbp+4F0h+var_200+0Eh], rax
0x180020934  movups  [rbp+4F0h+var_210], xmm0
0x18002093b  cmp     edi, edx
0x18002093d  jb      loc_180020B12
0x180020943  mov     r9d, edx; cchCount2
0x180020946  mov     [rsp+5F0h+bIgnoreCase], esi; bIgnoreCase
0x18002094a  lea     r8, [rbp+4F0h+var_410]; lpString2
0x180020951  mov     rcx, rbx; lpString1
0x180020954  call    cs:__imp_CompareStringOrdinal
0x18002095b  nop     dword ptr [rax+rax+00h]
0x180020960  cmp     eax, 2
0x180020963  jnz     loc_180020B12
0x180020969  mov     edx, 38h ; '8'; cchCount1
0x18002096e  cmp     edi, edx
0x180020970  jb      short loc_180020996
0x180020972  mov     r9d, edx; cchCount2
0x180020975  mov     [rsp+5F0h+bIgnoreCase], esi; bIgnoreCase
0x180020979  lea     r8, [rbp+4F0h+var_350]; lpString2
0x180020980  mov     rcx, rbx; lpString1
0x180020983  call    cs:__imp_CompareStringOrdinal
0x18002098a  nop     dword ptr [rax+rax+00h]
0x18002098f  cmp     eax, 2
0x180020992  jz      short loc_1800209F7
0x180020994  jmp     short loc_18002099F
0x180020996  cmp     edi, 2Ah ; '*'
0x180020999  jb      loc_180020AF1
0x18002099f  mov     r9d, 2Ah ; '*'; cchCount2
0x1800209a5  mov     [rsp+5F0h+bIgnoreCase], esi; bIgnoreCase
0x1800209a9  mov     edx, r9d; cchCount1
0x1800209ac  lea     r8, [rbp+4F0h+var_4B0]; lpString2
0x1800209b0  mov     rcx, rbx; lpString1
0x1800209b3  call    cs:__imp_CompareStringOrdinal
0x1800209ba  nop     dword ptr [rax+rax+00h]
0x1800209bf  cmp     eax, 2
0x1800209c2  jz      short loc_1800209F7
0x1800209c4  mov     edx, 50h ; 'P'; cchCount1
0x1800209c9  cmp     edi, edx
0x1800209cb  jb      loc_180020AF1
0x1800209d1  mov     r9d, edx; cchCount2
0x1800209d4  mov     [rsp+5F0h+bIgnoreCase], esi; bIgnoreCase
0x1800209d8  lea     r8, [rbp+4F0h+var_1E0]; lpString2
0x1800209df  mov     rcx, rbx; lpString1
0x1800209e2  call    cs:__imp_CompareStringOrdinal
0x1800209e9  nop     dword ptr [rax+rax+00h]
0x1800209ee  cmp     eax, 2
0x1800209f1  jnz     loc_180020AF1
0x1800209f7  mov     al, sil
0x1800209fa  mov     rcx, [rbp+4F0h+var_30]
0x180020a01  xor     rcx, rsp; StackCookie
0x180020a04  call    __security_check_cookie
0x180020a09  add     rsp, 5D8h
0x180020a10  pop     rdi
0x180020a11  pop     rsi
0x180020a12  pop     rbx
0x180020a13  pop     rbp
0x180020a14  retn
  ... truncated ...
```
