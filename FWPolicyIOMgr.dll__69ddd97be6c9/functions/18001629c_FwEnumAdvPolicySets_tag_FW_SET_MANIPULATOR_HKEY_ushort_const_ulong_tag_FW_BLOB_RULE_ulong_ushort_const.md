# FwEnumAdvPolicySets(_tag_FW_SET_MANIPULATOR *,HKEY__ *,ushort const *,ulong *,_tag_FW_BLOB_RULE * *,ulong,ushort const *)

- ea: `0x18001629c`
- end: `0x1800165e1`
- name: `?FwEnumAdvPolicySets@@YAJPEAU_tag_FW_SET_MANIPULATOR@@PEAUHKEY__@@PEBGPEAKPEAPEAU_tag_FW_BLOB_RULE@@K2@Z`
- size: `837`
- prototype: `__int64 __fastcall(struct _tag_FW_SET_MANIPULATOR *, HKEY, const unsigned __int16 *, unsigned int *, struct _tag_FW_BLOB_RULE **, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015f00`

## callees

- `0x1800042c4`
- `0x18001629c`
- `0x180016f9c`
- `0x1800179e4`
- `0x18001e9ac`
- `0x18001ec98`
- `0x18001f650`
- `0x180031008`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001649a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001649a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016445`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016445`
- `fwbase!FwFree` at `0x1800165ab`
- `fwbase!FwFree` at `0x1800165ab`
- `fwbase!FwNtStatusToHResult` at `0x180016506`
- `fwbase!FwNtStatusToHResult` at `0x180016506`
- `fwbase!FwRegOpenKey` at `0x18001632b`
- `fwbase!FwRegOpenKey` at `0x18001632b`
- `fwbase!FwRegCloseKey` at `0x1800165b6`
- `fwbase!FwRegCloseKey` at `0x1800165b6`
- `fwbase!FwFieldNameMatchStringBegining` at `0x180016487`
- `fwbase!FwFieldNameMatchStringBegining` at `0x180016487`

## pseudocode

```c
__int64 __fastcall FwEnumAdvPolicySets(
        struct _tag_FW_SET_MANIPULATOR *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        struct _tag_FW_BLOB_RULE **a5,
        unsigned int a6,
        unsigned __int16 *a7)
{
  int MergedGPODefaultID; // eax
  signed int v11; // ebx
  LPCOLESTR v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  DWORD i; // esi
  int v17; // edi
  LSTATUS v18; // eax
  int v19; // edi
  const unsigned __int16 *v20; // rcx
  signed int Set; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpString1; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+68h] [rbp-98h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v29[3]; // [rsp+74h] [rbp-8Ch] BYREF
  WCHAR Name[256]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  cSubKeys = 0;
  cchName = 0;
  v26 = 0;
  v29[0] = 0;
  lpString1 = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  MergedGPODefaultID = FwRegOpenKey(a2, a3, 9, &hKey, &v26);
  v11 = MergedGPODefaultID;
  if ( MergedGPODefaultID < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      goto LABEL_51;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_48;
    v13 = 40;
    goto LABEL_7;
  }
  if ( !v26 )
    return 0;
  MergedGPODefaultID = FwGetMergedGPODefaultID(hKey, a7, (unsigned __int16 **)&lpString1);
  v11 = MergedGPODefaultID;
  if ( MergedGPODefaultID < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      goto LABEL_51;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_48;
    v13 = 41;
    goto LABEL_7;
  }
  MergedGPODefaultID = FwAdvPolicyRegQueryNumKeys(hKey, &cSubKeys);
  v11 = MergedGPODefaultID;
  if ( MergedGPODefaultID < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      goto LABEL_51;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_48;
    v13 = 42;
LABEL_7:
    v14 = (unsigned int)MergedGPODefaultID;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids, v14);
    goto LABEL_47;
  }
  for ( i = 0; ; ++i )
  {
    v17 = v11;
    if ( i >= cSubKeys )
      break;
    cchName = 255;
    v18 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    v11 = v18;
    if ( v18 == 259 )
      break;
    if ( v18 > 0 )
      v11 = (unsigned __int16)v18 | 0x80070000;
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
        goto LABEL_51;
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 43;
        goto LABEL_40;
      }
      goto LABEL_48;
    }
    v19 = 0;
    if ( lpString1 )
    {
      v25 = 0;
      if ( (unsigned int)FwFieldNameMatchStringBegining(a7, Name, &v25) )
      {
        if ( lstrcmpiW(lpString1, Name) )
          continue;
        v19 = 1;
      }
    }
    v20 = a7;
    if ( v19 != 1 )
      v20 = 0;
    Set = FwAdvPolicyLoadSet(a1, hKey, Name, a5, v29, a6, v20);
    v11 = Set;
    if ( Set == -2147467263
      || Set == -2147418113
      || Set == -2147024809
      || Set == -2147024883
      || Set == (unsigned int)FwNtStatusToHResult(3221225485LL) )
    {
      v11 = 0;
    }
    else if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
        goto LABEL_51;
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 44;
LABEL_40:
        v14 = (unsigned int)v11;
        goto LABEL_8;
      }
      goto LABEL_48;
    }
  }
  *a4 = v29[0];
  v11 = v17;
  if ( v17 >= 0 )
    goto LABEL_51;
LABEL_47:
  v12 = WPP_GLOBAL_Control;
LABEL_48:
  if ( v12 != (LPCOLESTR)&WPP_GLOBAL_Control && (v12[14] & 1) != 0 )
    WPP_SF_Sd(*((_QWORD *)v12 + 2), 45, (unsigned int)WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids, (_DWORD)a3, v11);
LABEL_51:
  FwFree(lpString1);
  FwRegCloseKey(hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001629c  push    rbp
0x18001629e  push    rbx
0x18001629f  push    rsi
0x1800162a0  push    rdi
0x1800162a1  push    r12
0x1800162a3  push    r13
0x1800162a5  push    r14
0x1800162a7  push    r15
0x1800162a9  lea     rbp, [rsp-198h]
0x1800162b1  sub     rsp, 298h
0x1800162b8  mov     rax, cs:__security_cookie
0x1800162bf  xor     rax, rsp
0x1800162c2  mov     [rbp+1D0h+var_50], rax
0x1800162c9  mov     rax, [rbp+1D0h+arg_20]
0x1800162d0  xor     edi, edi
0x1800162d2  mov     r14, [rbp+1D0h+arg_30]
0x1800162d9  mov     r12, r9
0x1800162dc  mov     [rsp+2D0h+var_288], rcx
0x1800162e1  mov     r13, r8
0x1800162e4  mov     [rsp+2D0h+var_290], rax
0x1800162e9  mov     rbx, rdx
0x1800162ec  mov     [rsp+2D0h+hKey], rdi
0x1800162f1  mov     [rsp+2D0h+cSubKeys], edi
0x1800162f5  mov     [rsp+2D0h+cchName], edi
0x1800162f9  mov     [rsp+2D0h+var_268], edi
0x1800162fd  mov     [rsp+2D0h+var_25C], edi
0x180016301  mov     [rsp+2D0h+lpString1], rdi
0x180016306  test    rdx, rdx
0x180016309  jnz     short loc_180016310
0x18001630b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016310  lea     rax, [rsp+2D0h+var_268]
0x180016315  mov     r8d, 9
0x18001631b  lea     r9, [rsp+2D0h+hKey]
0x180016320  mov     [rsp+2D0h+lpReserved], rax
0x180016325  mov     rdx, r13
0x180016328  mov     rcx, rbx
0x18001632b  call    cs:__imp_FwRegOpenKey
0x180016331  mov     ebx, eax
0x180016333  test    eax, eax
0x180016335  jns     short loc_180016375
0x180016337  mov     rcx, cs:WPP_GLOBAL_Control
0x18001633e  lea     rdi, WPP_GLOBAL_Control
0x180016345  cmp     rcx, rdi
0x180016348  jz      loc_1800165A6
0x18001634e  test    byte ptr [rcx+1Ch], 1
0x180016352  jz      loc_18001657F
0x180016358  mov     edx, 28h ; '('
0x18001635d  mov     r9d, eax
0x180016360  mov     rcx, [rcx+10h]
0x180016364  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x18001636b  call    WPP_SF_d
0x180016370  jmp     loc_180016578
0x180016375  cmp     [rsp+2D0h+var_268], edi
0x180016379  jnz     short loc_180016382
0x18001637b  xor     eax, eax
0x18001637d  jmp     loc_1800165BE
0x180016382  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x180016387  lea     r8, [rsp+2D0h+lpString1]; unsigned __int16 **
0x18001638c  mov     rdx, r14; unsigned __int16 *
0x18001638f  call    ?FwGetMergedGPODefaultID@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; FwGetMergedGPODefaultID(HKEY__ *,ushort const *,ushort * *)
0x180016394  mov     ebx, eax
0x180016396  test    eax, eax
0x180016398  jns     short loc_1800163C2
0x18001639a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163a1  lea     rdi, WPP_GLOBAL_Control
0x1800163a8  cmp     rcx, rdi
0x1800163ab  jz      loc_1800165A6
0x1800163b1  test    byte ptr [rcx+1Ch], 1
0x1800163b5  jz      loc_18001657F
0x1800163bb  mov     edx, 29h ; ')'
0x1800163c0  jmp     short loc_18001635D
0x1800163c2  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800163c7  lea     rdx, [rsp+2D0h+cSubKeys]; lpcSubKeys
0x1800163cc  call    FwAdvPolicyRegQueryNumKeys
0x1800163d1  mov     ebx, eax
0x1800163d3  test    eax, eax
0x1800163d5  jns     short loc_180016402
0x1800163d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163de  lea     rdi, WPP_GLOBAL_Control
0x1800163e5  cmp     rcx, rdi
0x1800163e8  jz      loc_1800165A6
0x1800163ee  test    byte ptr [rcx+1Ch], 1
0x1800163f2  jz      loc_18001657F
0x1800163f8  mov     edx, 2Ah ; '*'
0x1800163fd  jmp     loc_18001635D
0x180016402  mov     r15d, [rbp+1D0h+arg_28]
0x180016409  mov     esi, edi
0x18001640b  mov     edi, ebx
0x18001640d  cmp     esi, [rsp+2D0h+cSubKeys]
0x180016411  jnb     loc_180016563
0x180016417  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001641c  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x180016421  xor     eax, eax
0x180016423  mov     [rsp+2D0h+cchName], 0FFh
0x18001642b  mov     [rsp+2D0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180016430  lea     r8, [rbp+1D0h+Name]; lpName
0x180016434  mov     [rsp+2D0h+lpcchClass], rax; lpcchClass
0x180016439  mov     edx, esi; dwIndex
0x18001643b  mov     [rsp+2D0h+lpClass], rax; lpClass
0x180016440  mov     [rsp+2D0h+lpReserved], rax; lpReserved
0x180016445  call    cs:__imp_RegEnumKeyExW
0x18001644b  mov     ebx, eax
0x18001644d  cmp     eax, 103h
0x180016452  jz      loc_180016563
0x180016458  test    eax, eax
0x18001645a  jle     short loc_180016465
0x18001645c  movzx   ebx, ax
0x18001645f  or      ebx, 80070000h
0x180016465  test    ebx, ebx
0x180016467  js      loc_180016543
0x18001646d  xor     edi, edi
0x18001646f  cmp     [rsp+2D0h+lpString1], rdi
0x180016474  jz      short loc_1800164AB
0x180016476  lea     r8, [rsp+2D0h+var_270]
0x18001647b  mov     [rsp+2D0h+var_270], rdi
0x180016480  lea     rdx, [rbp+1D0h+Name]
0x180016484  mov     rcx, r14
0x180016487  call    cs:__imp_FwFieldNameMatchStringBegining
0x18001648d  test    eax, eax
0x18001648f  jz      short loc_1800164AB
0x180016491  mov     rcx, [rsp+2D0h+lpString1]; lpString1
0x180016496  lea     rdx, [rbp+1D0h+Name]; lpString2
0x18001649a  call    cs:__imp_lstrcmpiW
0x1800164a0  test    eax, eax
0x1800164a2  jnz     loc_18001653C
0x1800164a8  lea     edi, [rax+1]
0x1800164ab  mov     r9, [rsp+2D0h+var_290]; struct _tag_FW_BLOB_RULE **
0x1800164b0  lea     r8, [rbp+1D0h+Name]; unsigned __int16 *
0x1800164b4  mov     rdx, [rsp+2D0h+hKey]; HKEY
0x1800164b9  xor     eax, eax
0x1800164bb  cmp     edi, 1
0x1800164be  mov     rcx, r14
0x1800164c1  cmovnz  rcx, rax
0x1800164c5  lea     rax, [rsp+2D0h+var_25C]
0x1800164ca  mov     [rsp+2D0h+lpcchClass], rcx; unsigned __int16 *
0x1800164cf  mov     rcx, [rsp+2D0h+var_288]; struct _tag_FW_SET_MANIPULATOR *
0x1800164d4  mov     dword ptr [rsp+2D0h+lpClass], r15d; unsigned int
0x1800164d9  mov     [rsp+2D0h+lpReserved], rax; unsigned int *
0x1800164de  call    ?FwAdvPolicyLoadSet@@YAJPEAU_tag_FW_SET_MANIPULATOR@@PEAUHKEY__@@PEBGPEAPEAU_tag_FW_BLOB_RULE@@PEAKK2@Z; FwAdvPolicyLoadSet(_tag_FW_SET_MANIPULATOR *,HKEY__ *,ushort const *,_tag_FW_BLOB_RULE * *,ulong *,ulong,ushort const *)
0x1800164e3  mov     ebx, eax
0x1800164e5  cmp     eax, 80004001h
0x1800164ea  jz      short loc_18001653A
0x1800164ec  cmp     eax, 8000FFFFh
0x1800164f1  jz      short loc_18001653A
0x1800164f3  cmp     eax, 80070057h
0x1800164f8  jz      short loc_18001653A
0x1800164fa  cmp     eax, 8007000Dh
0x1800164ff  jz      short loc_18001653A
0x180016501  mov     ecx, 0C000000Dh
0x180016506  call    cs:__imp_FwNtStatusToHResult
0x18001650c  cmp     ebx, eax
0x18001650e  jz      short loc_18001653A
0x180016510  test    ebx, ebx
0x180016512  jns     short loc_18001653C
0x180016514  mov     rcx, cs:WPP_GLOBAL_Control
0x18001651b  lea     rdi, WPP_GLOBAL_Control
0x180016522  cmp     rcx, rdi
0x180016525  jz      short loc_1800165A6
0x180016527  test    byte ptr [rcx+1Ch], 1
0x18001652b  jz      short loc_18001657F
0x18001652d  mov     edx, 2Ch ; ','
0x180016532  mov     r9d, ebx
0x180016535  jmp     loc_180016360
0x18001653a  xor     ebx, ebx
0x18001653c  inc     esi
0x18001653e  jmp     loc_18001640B
0x180016543  mov     rcx, cs:WPP_GLOBAL_Control
0x18001654a  lea     rdi, WPP_GLOBAL_Control
0x180016551  cmp     rcx, rdi
0x180016554  jz      short loc_1800165A6
0x180016556  test    byte ptr [rcx+1Ch], 1
0x18001655a  jz      short loc_18001657F
0x18001655c  mov     edx, 2Bh ; '+'
0x180016561  jmp     short loc_180016532
0x180016563  mov     eax, [rsp+2D0h+var_25C]
0x180016567  mov     [r12], eax
0x18001656b  mov     ebx, edi
0x18001656d  test    edi, edi
0x18001656f  jns     short loc_1800165A6
0x180016571  lea     rdi, WPP_GLOBAL_Control
0x180016578  mov     rcx, cs:WPP_GLOBAL_Control
0x18001657f  cmp     rcx, rdi
0x180016582  jz      short loc_1800165A6
0x180016584  test    byte ptr [rcx+1Ch], 1
0x180016588  jz      short loc_1800165A6
0x18001658a  mov     rcx, [rcx+10h]
0x18001658e  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x180016595  mov     edx, 2Dh ; '-'
0x18001659a  mov     dword ptr [rsp+2D0h+lpReserved], ebx
0x18001659e  mov     r9, r13
0x1800165a1  call    WPP_SF_Sd
0x1800165a6  mov     rcx, [rsp+2D0h+lpString1]
0x1800165ab  call    cs:__imp_FwFree
0x1800165b1  mov     rcx, [rsp+2D0h+hKey]
0x1800165b6  call    cs:__imp_FwRegCloseKey
0x1800165bc  mov     eax, ebx
0x1800165be  mov     rcx, [rbp+1D0h+var_50]
0x1800165c5  xor     rcx, rsp; StackCookie
0x1800165c8  call    __security_check_cookie
0x1800165cd  add     rsp, 298h
0x1800165d4  pop     r15
0x1800165d6  pop     r14
0x1800165d8  pop     r13
0x1800165da  pop     r12
0x1800165dc  pop     rdi
0x1800165dd  pop     rsi
0x1800165de  pop     rbx
0x1800165df  pop     rbp
0x1800165e0  retn
```
