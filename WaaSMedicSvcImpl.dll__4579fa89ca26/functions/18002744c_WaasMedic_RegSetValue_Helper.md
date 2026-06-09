# WaasMedic::RegSetValue_Helper

- ea: `0x18002744c`
- end: `0x1800276d1`
- name: `WaasMedic::RegSetValue_Helper`
- size: `645`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18002271c`
- `0x180027110`
- `0x180027150`
- `0x1800271a4`
- `0x180068f58`

## callees

- `0x180001718`
- `0x1800050a0`
- `0x18000d04c`
- `0x18002555c`
- `0x18002744c`
- `0x18002e81c`
- `0x1800358d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800274cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800274cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002753e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002753e`

## string_xrefs

- `0x18002750f`: `RegSetValue_Helper - error applying protection to registry key - 0x%08X`
- `0x180027555`: `RegUtil: Error when attempting to set registry value. Parent key: [%s] Sub key: [%s] Value name: [%s] Value type [%d]. hr=0x%08X`
- `0x18002751d`: `RegSetValue_Helper - error applying protection to registry key due to invalid key handle - 0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegSetValue_Helper(
        HKEY a1,
        const WCHAR *a2,
        __int64 a3,
        const WCHAR *a4,
        DWORD dwType,
        BYTE *a6,
        DWORD a7,
        char a8)
{
  const OLECHAR *v9; // r15
  signed int KeyHelperPrivate; // ebx
  int v11; // esi
  LSTATUS v12; // eax
  __int64 v13; // r10
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // ecx
  __int64 v17; // rcx
  int lpData; // [rsp+20h] [rbp-D9h]
  DWORD cbData[2]; // [rsp+28h] [rbp-D1h]
  HKEY hKey; // [rsp+40h] [rbp-B9h] BYREF
  BYTE *v22; // [rsp+48h] [rbp-B1h] BYREF
  _QWORD v23[9]; // [rsp+50h] [rbp-A9h] BYREF
  int v24; // [rsp+98h] [rbp-61h]
  int v25; // [rsp+9Ch] [rbp-5Dh]
  const OLECHAR *v26; // [rsp+A0h] [rbp-59h]
  int v27; // [rsp+A8h] [rbp-51h]
  int v28; // [rsp+ACh] [rbp-4Dh]
  const OLECHAR *v29; // [rsp+B0h] [rbp-49h]
  __int64 v30; // [rsp+B8h] [rbp-41h]
  const WCHAR *v31; // [rsp+C0h] [rbp-39h]
  int v32; // [rsp+C8h] [rbp-31h]
  int v33; // [rsp+CCh] [rbp-2Dh]
  HKEY *p_hKey; // [rsp+D0h] [rbp-29h]
  __int64 v35; // [rsp+D8h] [rbp-21h]
  BYTE **v36; // [rsp+E0h] [rbp-19h]
  __int64 v37; // [rsp+E8h] [rbp-11h]

  v22 = a6;
  v9 = a2;
  hKey = 0;
  KeyHelperPrivate = WaasMedic::RegCreateKeyHelperPrivate(a1, a2, lpData);
  v11 = 2;
  if ( KeyHelperPrivate >= 0 )
  {
    v12 = RegSetValueExW(0, a4, 0, dwType, v22, a7);
    if ( v12 )
    {
      if ( v12 > 0 )
        KeyHelperPrivate = (unsigned __int16)v12 | 0x80070000;
      else
        KeyHelperPrivate = v12;
    }
    else if ( a8 )
    {
      KeyHelperPrivate = -2147024890;
      LogLevelW(
        2u,
        L"RegSetValue_Helper - error applying protection to registry key due to invalid key handle - 0x%08X",
        2147942406LL);
    }
  }
  if ( KeyHelperPrivate < 0 )
  {
    cbData[0] = dwType;
    LogLevelW(
      2u,
      L"RegUtil: Error when attempting to set registry value. Parent key: [%s] Sub key: [%s] Value name: [%s] Value type [%d]. hr=0x%08X",
      v9,
      0,
      a4,
      *(_QWORD *)cbData,
      KeyHelperPrivate);
    v13 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v13 > 5u
      && (*(_QWORD *)(v13 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v13 + 24) & 0x400000000000LL) == *(_QWORD *)(v13 + 24) )
    {
      LODWORD(v22) = KeyHelperPrivate;
      v36 = &v22;
      LODWORD(hKey) = dwType;
      p_hKey = &hKey;
      v14 = -1;
      v23[0] = 0x1000000;
      v37 = 4;
      v35 = 4;
      if ( a4 )
      {
        v15 = -1;
        do
          ++v15;
        while ( a4[v15] );
        v16 = 2 * v15 + 2;
      }
      else
      {
        a4 = &word_180073298;
        v16 = 2;
      }
      v31 = a4;
      v32 = v16;
      v33 = 0;
      v29 = &word_180073298;
      v30 = 2;
      if ( v9 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v9[v17] );
        v11 = 2 * v17 + 2;
      }
      else
      {
        v9 = &word_180073298;
      }
      v26 = v9;
      v27 = v11;
      v28 = 0;
      do
        ++v14;
      while ( *(&gc_pszVersionString + v14) );
      v23[8] = &gc_pszVersionString;
      v24 = 2 * v14 + 2;
      v25 = 0;
      v23[6] = v23;
      v23[7] = 8;
      tlgWriteTransfer_EventWriteTransfer(v13, &unk_180092EF8, 0);
    }
  }
  return (unsigned int)KeyHelperPrivate;
}

```

## disassembly

```asm
0x18002744c  mov     [rsp-8+arg_10], rbx
0x180027451  push    rbp
0x180027452  push    rsi
0x180027453  push    rdi
0x180027454  push    r12
0x180027456  push    r13
0x180027458  push    r14
0x18002745a  push    r15
0x18002745c  lea     rbp, [rsp-7]
0x180027461  sub     rsp, 100h
0x180027468  mov     rax, cs:__security_cookie
0x18002746f  xor     rax, rsp
0x180027472  mov     [rbp+37h+var_40], rax
0x180027476  mov     rax, [rbp+37h+arg_28]
0x18002747a  mov     r14, r9
0x18002747d  lea     r9, [rsp+130h+hKey]
0x180027482  mov     [rsp+130h+var_E8], rax
0x180027487  mov     r15, rdx
0x18002748a  mov     [rsp+130h+hKey], 0
0x180027493  mov     r12, rcx
0x180027496  call    WaasMedic__RegCreateKeyHelperPrivate
0x18002749b  mov     r13d, [rbp+37h+dwType]
0x18002749f  mov     ebx, eax
0x1800274a1  mov     rdi, [rsp+130h+hKey]
0x1800274a6  mov     esi, 2
0x1800274ab  test    eax, eax
0x1800274ad  js      short loc_18002752E
0x1800274af  mov     ecx, [rbp+37h+arg_30]
0x1800274b2  mov     r9d, r13d; dwType
0x1800274b5  mov     rax, [rsp+130h+var_E8]
0x1800274ba  xor     r8d, r8d; Reserved
0x1800274bd  mov     [rsp+130h+cbData], ecx; cbData
0x1800274c1  mov     rdx, r14; lpValueName
0x1800274c4  mov     rcx, rdi; hKey
0x1800274c7  mov     [rsp+130h+lpData], rax; lpData
0x1800274cc  call    cs:__imp_RegSetValueExW
0x1800274d2  test    eax, eax
0x1800274d4  jz      short loc_1800274E7
0x1800274d6  jg      short loc_1800274DC
0x1800274d8  mov     ebx, eax
0x1800274da  jmp     short loc_18002752E
0x1800274dc  movzx   ebx, ax
0x1800274df  or      ebx, 80070000h
0x1800274e5  jmp     short loc_18002752E
0x1800274e7  cmp     [rbp+37h+arg_38], 0
0x1800274eb  jz      short loc_18002752E
0x1800274ed  cmp     r12, rdi
0x1800274f0  jz      short loc_180027518
0x1800274f2  test    rdi, rdi
0x1800274f5  jz      short loc_180027518
0x1800274f7  lea     rdx, aSAiTlKrS119512; "S:AI(TL;;KR;;;S-1-19-512-4096)"
0x1800274fe  mov     rcx, rdi; handle
0x180027501  call    ?ApplySecurityDescriptorOnRegistrySubkey@CProtectionUtil@WaasMedic@@CAJPEAUHKEY__@@PEBG@Z; WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(HKEY__ *,ushort const *)
0x180027506  mov     ebx, eax
0x180027508  test    eax, eax
0x18002750a  jns     short loc_18002752E
0x18002750c  mov     r8d, eax
0x18002750f  lea     rdx, aRegsetvalueHel_0; "RegSetValue_Helper - error applying pro"...
0x180027516  jmp     short loc_180027527
0x180027518  mov     ebx, 80070006h
0x18002751d  lea     rdx, aRegsetvalueHel; "RegSetValue_Helper - error applying pro"...
0x180027524  mov     r8d, ebx
0x180027527  mov     ecx, esi; unsigned __int8
0x180027529  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002752e  cmp     r12, rdi
0x180027531  jz      short loc_180027546
0x180027533  xor     r12d, r12d
0x180027536  test    rdi, rdi
0x180027539  jz      short loc_180027549
0x18002753b  mov     rcx, rdi; hKey
0x18002753e  call    cs:__imp_RegCloseKey
0x180027544  jmp     short loc_180027549
0x180027546  xor     r12d, r12d
0x180027549  test    ebx, ebx
0x18002754b  jns     loc_1800276A8
0x180027551  mov     [rsp+130h+var_100], ebx
0x180027555  lea     rdx, aRegutilErrorWh_2; "RegUtil: Error when attempting to set r"...
0x18002755c  mov     [rsp+130h+cbData], r13d
0x180027561  xor     r9d, r9d
0x180027564  mov     r8, r15
0x180027567  mov     [rsp+130h+lpData], r14
0x18002756c  mov     ecx, esi; unsigned __int8
0x18002756e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027573  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180027578  mov     r10, [rax+8]
0x18002757c  mov     eax, [r10]
0x18002757f  cmp     eax, 5
0x180027582  jbe     loc_1800276A8
0x180027588  mov     rcx, [r10+18h]
0x18002758c  mov     rdx, 400000000000h
0x180027596  mov     rax, [r10+10h]
0x18002759a  test    rdx, rax
0x18002759d  jz      loc_1800276A8
0x1800275a3  mov     rax, rcx
0x1800275a6  and     rax, rdx
0x1800275a9  cmp     rax, rcx
0x1800275ac  jnz     loc_1800276A8
0x1800275b2  lea     rax, [rsp+130h+var_E8]
0x1800275b7  mov     dword ptr [rsp+130h+var_E8], ebx
0x1800275bb  mov     [rbp+37h+var_50], rax
0x1800275bf  lea     rdx, word_180073298
0x1800275c6  lea     rax, [rsp+130h+hKey]
0x1800275cb  mov     dword ptr [rsp+130h+hKey], r13d
0x1800275d0  mov     [rbp+37h+var_60], rax
0x1800275d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800275d8  mov     [rsp+130h+var_E0], 1000000h
0x1800275e1  mov     [rbp+37h+var_48], 4
0x1800275e9  mov     [rbp+37h+var_58], 4
0x1800275f1  test    r14, r14
0x1800275f4  jz      short loc_18002760C
0x1800275f6  mov     rcx, rax
0x1800275f9  inc     rcx
0x1800275fc  cmp     [r14+rcx*2], r12w
0x180027601  jnz     short loc_1800275F9
0x180027603  lea     ecx, ds:2[rcx*2]
0x18002760a  jmp     short loc_180027611
0x18002760c  mov     r14, rdx
0x18002760f  mov     ecx, esi
0x180027611  mov     [rbp+37h+var_70], r14
0x180027615  mov     [rbp+37h+var_68], ecx
0x180027618  mov     [rbp+37h+var_64], r12d
0x18002761c  mov     [rbp+37h+var_80], rdx
0x180027620  mov     [rbp+37h+var_78], rsi
0x180027624  test    r15, r15
0x180027627  jz      short loc_18002763F
0x180027629  mov     rcx, rax
0x18002762c  inc     rcx
0x18002762f  cmp     [r15+rcx*2], r12w
0x180027634  jnz     short loc_18002762C
0x180027636  lea     esi, ds:2[rcx*2]
0x18002763d  jmp     short loc_180027642
0x18002763f  mov     r15, rdx
0x180027642  mov     [rbp+37h+var_90], r15
0x180027646  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18002764d  mov     [rbp+37h+var_88], esi
0x180027650  mov     [rbp+37h+var_84], r12d
0x180027654  inc     rax
0x180027657  cmp     [rcx+rax*2], r12w
0x18002765c  jnz     short loc_180027654
0x18002765e  lea     eax, ds:2[rax*2]
0x180027665  mov     [rbp+37h+var_A0], rcx
0x180027669  mov     [rbp+37h+var_98], eax
0x18002766c  lea     rdx, unk_180092EF8
0x180027673  lea     rax, [rsp+130h+var_E0]
0x180027678  mov     [rbp+37h+var_94], r12d
0x18002767c  mov     [rbp+37h+var_B0], rax
0x180027680  xor     r9d, r9d
0x180027683  lea     rax, [rsp+130h+var_D0]
0x180027688  mov     [rbp+37h+var_A8], 8
0x180027690  mov     qword ptr [rsp+130h+cbData], rax
0x180027695  xor     r8d, r8d
0x180027698  mov     rcx, r10
0x18002769b  mov     dword ptr [rsp+130h+lpData], 9
0x1800276a3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800276a8  mov     eax, ebx
0x1800276aa  mov     rcx, [rbp+37h+var_40]
0x1800276ae  xor     rcx, rsp; StackCookie
0x1800276b1  call    __security_check_cookie
0x1800276b6  mov     rbx, [rsp+130h+arg_10]
0x1800276be  add     rsp, 100h
0x1800276c5  pop     r15
0x1800276c7  pop     r14
0x1800276c9  pop     r13
0x1800276cb  pop     r12
0x1800276cd  pop     rdi
0x1800276ce  pop     rsi
0x1800276cf  pop     rbp
0x1800276d0  retn
```
