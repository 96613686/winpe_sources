# WaasMedic::RegSetValue_Helper

- ea: `0x180029500`
- end: `0x180029777`
- name: `WaasMedic::RegSetValue_Helper`
- size: `631`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180029168`
- `0x1800291a8`
- `0x180029214`
- `0x180029260`

## callees

- `0x1800017ac`
- `0x180003bb0`
- `0x180016c9c`
- `0x18002543c`
- `0x180027644`
- `0x180029500`
- `0x180032094`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029573`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029573`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800295eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800295eb`

## string_xrefs

- `0x1800295cb`: `RegSetValue_Helper - error applying protection to registry key due to invalid key handle - 0x%08X`
- `0x1800295b6`: `RegSetValue_Helper - error applying protection to registry key - 0x%08X`
- `0x1800295fd`: `RegUtil: Error when attempting to set registry value. Parent key: [%s] Sub key: [%s] Value name: [%s] Value type [%d]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegSetValue_Helper(
        __int64 a1,
        const OLECHAR *a2,
        __int64 a3,
        const WCHAR *a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD a7,
        char a8)
{
  const OLECHAR *v9; // r15
  signed int v10; // ebx
  HKEY v11; // rdi
  int v12; // esi
  LSTATUS v13; // eax
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  const struct _tlgProvider_t *v16; // rax
  const struct _tlgProvider_t *v17; // r10
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  DWORD cbData[2]; // [rsp+28h] [rbp-D1h]
  HKEY hKey; // [rsp+40h] [rbp-B9h] BYREF
  signed int v25; // [rsp+48h] [rbp-B1h] BYREF
  __int64 v26; // [rsp+50h] [rbp-A9h] BYREF
  char v27[32]; // [rsp+60h] [rbp-99h] BYREF
  __int64 *v28; // [rsp+80h] [rbp-79h]
  __int64 v29; // [rsp+88h] [rbp-71h]
  unsigned __int16 *v30; // [rsp+90h] [rbp-69h]
  int v31; // [rsp+98h] [rbp-61h]
  int v32; // [rsp+9Ch] [rbp-5Dh]
  const OLECHAR *v33; // [rsp+A0h] [rbp-59h]
  int v34; // [rsp+A8h] [rbp-51h]
  int v35; // [rsp+ACh] [rbp-4Dh]
  const OLECHAR *v36; // [rsp+B0h] [rbp-49h]
  __int64 v37; // [rsp+B8h] [rbp-41h]
  const WCHAR *v38; // [rsp+C0h] [rbp-39h]
  int v39; // [rsp+C8h] [rbp-31h]
  int v40; // [rsp+CCh] [rbp-2Dh]
  HKEY *p_hKey; // [rsp+D0h] [rbp-29h]
  __int64 v42; // [rsp+D8h] [rbp-21h]
  signed int *v43; // [rsp+E0h] [rbp-19h]
  __int64 v44; // [rsp+E8h] [rbp-11h]

  hKey = 0;
  v9 = a2;
  v10 = WaasMedic::RegCreateKeyHelperPrivate(a1, a2, a3, &hKey);
  v11 = hKey;
  v12 = 2;
  if ( v10 >= 0 )
  {
    v13 = RegSetValueExW(hKey, a4, 0, dwType, lpData, a7);
    if ( v13 )
    {
      if ( v13 > 0 )
        v10 = (unsigned __int16)v13 | 0x80070000;
      else
        v10 = v13;
    }
    else if ( a8 )
    {
      if ( v11 == HKEY_LOCAL_MACHINE || !v11 )
      {
        v10 = -2147024890;
        LogLevelW(
          2u,
          L"RegSetValue_Helper - error applying protection to registry key due to invalid key handle - 0x%08X",
          2147942406LL);
      }
      else
      {
        v15 = WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(v11, v14);
        v10 = v15;
        if ( v15 < 0 )
          LogLevelW(2u, L"RegSetValue_Helper - error applying protection to registry key - 0x%08X", (unsigned int)v15);
      }
    }
  }
  if ( v11 != HKEY_LOCAL_MACHINE && v11 )
    RegCloseKey(v11);
  if ( v10 < 0 )
  {
    cbData[0] = dwType;
    LogLevelW(
      2u,
      L"RegUtil: Error when attempting to set registry value. Parent key: [%s] Sub key: [%s] Value name: [%s] Value type [%d]. hr=0x%08X",
      v9,
      0,
      a4,
      *(_QWORD *)cbData,
      v10);
    v16 = WaasMedic::TelemetryProvider::Provider();
    v17 = v16;
    if ( *(_DWORD *)v16 > 5u
      && (*((_QWORD *)v16 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v16 + 3) & 0x400000000000LL) == *((_QWORD *)v16 + 3) )
    {
      v25 = v10;
      v43 = &v25;
      LODWORD(hKey) = dwType;
      p_hKey = &hKey;
      v18 = -1;
      v26 = 0x1000000;
      v44 = 4;
      v42 = 4;
      if ( a4 )
      {
        v19 = -1;
        do
          ++v19;
        while ( a4[v19] );
        v20 = 2 * v19 + 2;
      }
      else
      {
        a4 = &word_18006939C;
        v20 = 2;
      }
      v38 = a4;
      v39 = v20;
      v40 = 0;
      v36 = &word_18006939C;
      v37 = 2;
      if ( v9 )
      {
        v21 = -1;
        do
          ++v21;
        while ( v9[v21] );
        v12 = 2 * v21 + 2;
      }
      else
      {
        v9 = &word_18006939C;
      }
      v33 = v9;
      v34 = v12;
      v35 = 0;
      do
        ++v18;
      while ( *(&gc_pszVersionString + v18) );
      v30 = &gc_pszVersionString;
      v31 = 2 * v18 + 2;
      v32 = 0;
      v28 = &v26;
      v29 = 8;
      tlgWriteTransfer_EventWriteTransfer(v17, byte_1800893E5, 0, 0, 9, v27);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180029500  mov     [rsp-8+arg_0], rbx
0x180029505  push    rbp
0x180029506  push    rsi
0x180029507  push    rdi
0x180029508  push    r12
0x18002950a  push    r13
0x18002950c  push    r14
0x18002950e  push    r15
0x180029510  lea     rbp, [rsp-7]
0x180029515  sub     rsp, 100h
0x18002951c  mov     rax, cs:__security_cookie
0x180029523  xor     rax, rsp
0x180029526  mov     [rbp+37h+var_40], rax
0x18002952a  mov     r12, [rbp+37h+arg_28]
0x18002952e  mov     r14, r9
0x180029531  lea     r9, [rsp+130h+hKey]
0x180029536  mov     [rsp+130h+hKey], 0
0x18002953f  mov     r15, rdx
0x180029542  call    WaasMedic__RegCreateKeyHelperPrivate
0x180029547  mov     r13d, [rbp+37h+dwType]
0x18002954b  mov     ebx, eax
0x18002954d  mov     rdi, [rsp+130h+hKey]
0x180029552  mov     esi, 2
0x180029557  test    eax, eax
0x180029559  js      short loc_1800295D7
0x18002955b  mov     ecx, [rbp+37h+arg_30]
0x18002955e  mov     r9d, r13d; dwType
0x180029561  mov     [rsp+130h+cbData], ecx; cbData
0x180029565  xor     r8d, r8d; Reserved
0x180029568  mov     rcx, rdi; hKey
0x18002956b  mov     [rsp+130h+lpData], r12; lpData
0x180029570  mov     rdx, r14; lpValueName
0x180029573  call    cs:__imp_RegSetValueExW
0x180029579  xor     r12d, r12d
0x18002957c  test    eax, eax
0x18002957e  jz      short loc_180029591
0x180029580  jg      short loc_180029586
0x180029582  mov     ebx, eax
0x180029584  jmp     short loc_1800295DA
0x180029586  movzx   ebx, ax
0x180029589  or      ebx, 80070000h
0x18002958f  jmp     short loc_1800295DA
0x180029591  cmp     [rbp+37h+arg_38], r12b
0x180029595  jz      short loc_1800295DA
0x180029597  cmp     rdi, 0FFFFFFFF80000002h
0x18002959e  jz      short loc_1800295C6
0x1800295a0  test    rdi, rdi
0x1800295a3  jz      short loc_1800295C6
0x1800295a5  mov     rcx, rdi; handle
0x1800295a8  call    ?ApplySecurityDescriptorOnRegistrySubkey@CProtectionUtil@WaasMedic@@CAJPEAUHKEY__@@PEBG@Z; WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(HKEY__ *,ushort const *)
0x1800295ad  mov     ebx, eax
0x1800295af  test    eax, eax
0x1800295b1  jns     short loc_1800295DA
0x1800295b3  mov     r8d, eax
0x1800295b6  lea     rdx, aRegsetvalueHel_0; "RegSetValue_Helper - error applying pro"...
0x1800295bd  mov     ecx, esi; unsigned __int8
0x1800295bf  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800295c4  jmp     short loc_1800295DA
0x1800295c6  mov     ebx, 80070006h
0x1800295cb  lea     rdx, aRegsetvalueHel; "RegSetValue_Helper - error applying pro"...
0x1800295d2  mov     r8d, ebx
0x1800295d5  jmp     short loc_1800295BD
0x1800295d7  xor     r12d, r12d
0x1800295da  cmp     rdi, 0FFFFFFFF80000002h
0x1800295e1  jz      short loc_1800295F1
0x1800295e3  test    rdi, rdi
0x1800295e6  jz      short loc_1800295F1
0x1800295e8  mov     rcx, rdi; hKey
0x1800295eb  call    cs:__imp_RegCloseKey
0x1800295f1  test    ebx, ebx
0x1800295f3  jns     loc_18002974E
0x1800295f9  mov     [rsp+130h+var_100], ebx
0x1800295fd  lea     rdx, aRegutilErrorWh_2; "RegUtil: Error when attempting to set r"...
0x180029604  mov     [rsp+130h+cbData], r13d
0x180029609  xor     r9d, r9d
0x18002960c  mov     r8, r15
0x18002960f  mov     [rsp+130h+lpData], r14
0x180029614  mov     ecx, esi; unsigned __int8
0x180029616  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002961b  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180029620  mov     r10, rax
0x180029623  mov     ecx, [rax]
0x180029625  cmp     ecx, 5
0x180029628  jbe     loc_18002974E
0x18002962e  mov     rdx, [rax+18h]
0x180029632  mov     rcx, [rax+10h]
0x180029636  mov     rax, 400000000000h
0x180029640  test    rax, rcx
0x180029643  jz      loc_18002974E
0x180029649  mov     rcx, rdx
0x18002964c  and     rcx, rax
0x18002964f  cmp     rcx, rdx
0x180029652  jnz     loc_18002974E
0x180029658  lea     rax, [rsp+130h+var_E8]
0x18002965d  mov     [rsp+130h+var_E8], ebx
0x180029661  mov     [rbp+37h+var_50], rax
0x180029665  lea     rdx, word_18006939C
0x18002966c  lea     rax, [rsp+130h+hKey]
0x180029671  mov     dword ptr [rsp+130h+hKey], r13d
0x180029676  mov     [rbp+37h+var_60], rax
0x18002967a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002967e  mov     [rsp+130h+var_E0], 1000000h
0x180029687  mov     [rbp+37h+var_48], 4
0x18002968f  mov     [rbp+37h+var_58], 4
0x180029697  test    r14, r14
0x18002969a  jz      short loc_1800296B2
0x18002969c  mov     rcx, rax
0x18002969f  inc     rcx
0x1800296a2  cmp     [r14+rcx*2], r12w
0x1800296a7  jnz     short loc_18002969F
0x1800296a9  lea     ecx, ds:2[rcx*2]
0x1800296b0  jmp     short loc_1800296B7
0x1800296b2  mov     r14, rdx
0x1800296b5  mov     ecx, esi
0x1800296b7  mov     [rbp+37h+var_70], r14
0x1800296bb  mov     [rbp+37h+var_68], ecx
0x1800296be  mov     [rbp+37h+var_64], r12d
0x1800296c2  mov     [rbp+37h+var_80], rdx
0x1800296c6  mov     [rbp+37h+var_78], rsi
0x1800296ca  test    r15, r15
0x1800296cd  jz      short loc_1800296E5
0x1800296cf  mov     rcx, rax
0x1800296d2  inc     rcx
0x1800296d5  cmp     [r15+rcx*2], r12w
0x1800296da  jnz     short loc_1800296D2
0x1800296dc  lea     esi, ds:2[rcx*2]
0x1800296e3  jmp     short loc_1800296E8
0x1800296e5  mov     r15, rdx
0x1800296e8  mov     [rbp+37h+var_90], r15
0x1800296ec  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800296f3  mov     [rbp+37h+var_88], esi
0x1800296f6  mov     [rbp+37h+var_84], r12d
0x1800296fa  inc     rax
0x1800296fd  cmp     [rcx+rax*2], r12w
0x180029702  jnz     short loc_1800296FA
0x180029704  lea     eax, ds:2[rax*2]
0x18002970b  mov     [rbp+37h+var_A0], rcx
0x18002970f  mov     [rbp+37h+var_98], eax
0x180029712  lea     rdx, byte_1800893E5
0x180029719  lea     rax, [rsp+130h+var_E0]
0x18002971e  mov     [rbp+37h+var_94], r12d
0x180029722  mov     [rbp+37h+var_B0], rax
0x180029726  xor     r9d, r9d
0x180029729  lea     rax, [rsp+130h+var_D0]
0x18002972e  mov     [rbp+37h+var_A8], 8
0x180029736  mov     qword ptr [rsp+130h+cbData], rax
0x18002973b  xor     r8d, r8d
0x18002973e  mov     rcx, r10
0x180029741  mov     dword ptr [rsp+130h+lpData], 9
0x180029749  call    _tlgWriteTransfer_EventWriteTransfer
0x18002974e  mov     eax, ebx
0x180029750  mov     rcx, [rbp+37h+var_40]
0x180029754  xor     rcx, rsp; StackCookie
0x180029757  call    __security_check_cookie
0x18002975c  mov     rbx, [rsp+130h+arg_0]
0x180029764  add     rsp, 100h
0x18002976b  pop     r15
0x18002976d  pop     r14
0x18002976f  pop     r13
0x180029771  pop     r12
0x180029773  pop     rdi
0x180029774  pop     rsi
0x180029775  pop     rbp
0x180029776  retn
```
