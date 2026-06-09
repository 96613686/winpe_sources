# CWSManGroupPolicyManager::QueryRegValue(IRequestContext *,_WSMAN_POLICY_INFO const *,ulong *,ulong,uchar *,ulong *)

- ea: `0x1800a04d0`
- end: `0x1800a0921`
- name: `?QueryRegValue@CWSManGroupPolicyManager@@AEAAJPEAVIRequestContext@@PEBU_WSMAN_POLICY_INFO@@PEAKKPEAE2@Z`
- size: `1105`
- prototype: `int(CWSManGroupPolicyManager *__hidden this, struct IRequestContext *, const struct _WSMAN_POLICY_INFO *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x1800a04d0`
- `0x1801133b0`
- `0x18012a93c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a075d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a089d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a075d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a089d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a05ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a05ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a0644`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a0644`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a0567`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a0567`

## string_xrefs

- `0x1800a0530`: `SOFTWARE\Policies\Microsoft\Windows\WinRM\Service`
- `0x1800a05dd`: `SOFTWARE\Policies\Microsoft\Windows\WinRM\Service\WinRS`
- `0x1800a08f0`: `onecore\admin\wmi\wmx\config\wsmangrouppolicymanager.cpp`
- `0x1800a0910`: `onecore\admin\wmi\wmx\config\wsmangrouppolicymanager.cpp`
- `0x1800a0718`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800a07be`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800a07e8`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800a0812`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800a08ba`: `RegOpenKeyEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWSManGroupPolicyManager::QueryRegValue(
        CWSManGroupPolicyManager *this,
        struct IRequestContext *a2,
        const struct _WSMAN_POLICY_INFO *a3,
        unsigned int *a4,
        DWORD a5,
        LPBYTE lpData,
        unsigned int *a7)
{
  unsigned int *v10; // r13
  BYTE *v11; // r12
  DWORD v12; // esi
  int v13; // eax
  const WCHAR *v14; // rdx
  __int64 v15; // rcx
  LSTATUS v16; // eax
  DWORD v17; // edi
  HKEY v18; // rcx
  HKEY v20; // rdi
  const WCHAR *v21; // rbx
  LSTATUS v22; // eax
  const unsigned __int16 *v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rdx
  const unsigned __int16 *v26; // r8
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+20h] BYREF

  if ( !a4 )
  {
    v17 = 1359;
    v23 = L"1121";
    v24 = 1121;
    goto LABEL_54;
  }
  v10 = a7;
  v11 = lpData;
  v12 = a5;
  if ( !a5 )
    goto LABEL_3;
  if ( !lpData )
  {
    v17 = 1359;
    v23 = L"1124";
    v24 = 1124;
    goto LABEL_54;
  }
  if ( !a7 )
  {
    v17 = 1359;
    v23 = L"1125";
    v24 = 1125;
LABEL_54:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp", v24, v23, 0x54Fu, a2);
    return v17;
  }
LABEL_3:
  if ( !a3 )
  {
    v25 = 1058;
    v26 = L"1058";
LABEL_53:
    v17 = 1359;
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp", v25, v26, 0x54Fu, 0);
    v23 = L"1129";
    v24 = 1129;
    goto LABEL_54;
  }
  v13 = *((_DWORD *)a3 + 5);
  if ( v13 == 1 )
  {
    v14 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRM\\Service";
    goto LABEL_6;
  }
  if ( v13 != 2 )
  {
    if ( v13 == 3 )
    {
      v14 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRM\\Service\\WinRS";
      goto LABEL_6;
    }
    v25 = 1087;
    v26 = L"1087";
    goto LABEL_53;
  }
  v14 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRM\\Client";
LABEL_6:
  hKey = 0;
  v15 = *((_QWORD *)this + 26);
  if ( !v15 )
    v15 = -2147483646;
  v16 = RegOpenKeyExW((HKEY)v15, v14, 0, 0x20119u, &hKey);
  v17 = v16;
  if ( v16 )
  {
    if ( v16 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
          *((_QWORD *)a3 + 1));
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          (unsigned int)WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
          v16,
          *((_QWORD *)a3 + 1));
      SetLastError(v17);
      if ( a2 )
        (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
          a2,
          1077134176,
          L"RegOpenKeyEx",
          v17);
    }
    goto LABEL_13;
  }
  if ( !v12 )
  {
LABEL_20:
    v20 = hKey;
    if ( hKey )
    {
      v21 = (const WCHAR *)*((_QWORD *)a3 + 1);
      if ( v21 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, v21);
        cbData = v12;
        v22 = RegQueryValueExW(v20, v21, 0, a4, v11, &cbData);
        v17 = v22;
        if ( v22 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
              v22,
              (__int64)v21);
        }
        else
        {
          *v10 = cbData;
          if ( !v11 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, v21);
            v17 = 122;
            SetLastError(0x7Au);
          }
        }
      }
      else
      {
        v17 = 1359;
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 509, L"509", 0x54Fu, a2);
      }
    }
    else
    {
      v17 = 1359;
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 508, L"508", 0x54Fu, a2);
    }
    goto LABEL_13;
  }
  if ( v11 )
  {
    if ( v10 )
      goto LABEL_20;
    v17 = 1359;
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 506, L"506", 0x54Fu, a2);
  }
  else
  {
    v17 = 1359;
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 505, L"505", 0x54Fu, a2);
  }
LABEL_13:
  v18 = hKey;
  hKey = 0;
  if ( v18 )
    RegCloseKey(v18);
  return v17;
}

```

## disassembly

```asm
0x1800a04d0  mov     [rsp+arg_0], rbx
0x1800a04d5  mov     [rsp+arg_8], rdx
0x1800a04da  push    rbp
0x1800a04db  push    rsi
0x1800a04dc  push    rdi
0x1800a04dd  push    r12
0x1800a04df  push    r13
0x1800a04e1  push    r14
0x1800a04e3  push    r15
0x1800a04e5  sub     rsp, 40h
0x1800a04e9  mov     rbp, r9
0x1800a04ec  mov     rbx, r8
0x1800a04ef  mov     r15, rdx
0x1800a04f2  test    r9, r9
0x1800a04f5  jz      loc_1800A0768
0x1800a04fb  mov     r13, [rsp+78h+arg_30]
0x1800a0503  mov     r12, [rsp+78h+lpData]
0x1800a050b  mov     esi, [rsp+78h+arg_20]
0x1800a0512  test    esi, esi
0x1800a0514  jnz     loc_1800A06C5
0x1800a051a  test    rbx, rbx
0x1800a051d  jz      loc_1800A0794
0x1800a0523  mov     eax, [r8+14h]
0x1800a0527  cmp     eax, 1
0x1800a052a  jnz     loc_1800A05CB
0x1800a0530  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800a0537  xor     r14d, r14d
0x1800a053a  mov     [rsp+78h+hKey], r14
0x1800a053f  mov     rcx, [rcx+0D0h]
0x1800a0546  mov     rax, 0FFFFFFFF80000002h
0x1800a054d  test    rcx, rcx
0x1800a0550  cmovz   rcx, rax; hKey
0x1800a0554  lea     rax, [rsp+78h+hKey]
0x1800a0559  mov     [rsp+78h+phkResult], rax; phkResult
0x1800a055e  mov     r9d, 20119h; samDesired
0x1800a0564  xor     r8d, r8d; ulOptions
0x1800a0567  call    cs:__imp_RegOpenKeyExW
0x1800a056d  mov     edi, eax
0x1800a056f  test    eax, eax
0x1800a0571  jz      short loc_1800A05E9
0x1800a0573  cmp     eax, 2
0x1800a0576  jnz     loc_1800A085E
0x1800a057c  lea     r15, WPP_GLOBAL_Control
0x1800a0583  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a058a  cmp     rcx, r15
0x1800a058d  jz      short loc_1800A059C
0x1800a058f  test    dword ptr [rcx+1Ch], 400000h
0x1800a0596  jnz     loc_1800A0840
0x1800a059c  mov     rcx, [rsp+78h+hKey]; hKey
0x1800a05a1  mov     [rsp+78h+hKey], r14
0x1800a05a6  test    rcx, rcx
0x1800a05a9  jz      short loc_1800A05B1
0x1800a05ab  call    cs:__imp_RegCloseKey
0x1800a05b1  mov     eax, edi
0x1800a05b3  mov     rbx, [rsp+78h+arg_0]
0x1800a05bb  add     rsp, 40h
0x1800a05bf  pop     r15
0x1800a05c1  pop     r14
0x1800a05c3  pop     r13
0x1800a05c5  pop     r12
0x1800a05c7  pop     rdi
0x1800a05c8  pop     rsi
0x1800a05c9  pop     rbp
0x1800a05ca  retn
0x1800a05cb  cmp     eax, 2
0x1800a05ce  jz      loc_1800A06B9
0x1800a05d4  cmp     eax, 3
0x1800a05d7  jnz     loc_1800A08D4
0x1800a05dd  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800a05e4  jmp     loc_1800A0537
0x1800a05e9  test    esi, esi
0x1800a05eb  jnz     loc_1800A06ED
0x1800a05f1  mov     rdi, [rsp+78h+hKey]
0x1800a05f6  test    rdi, rdi
0x1800a05f9  jz      loc_1800A07CF
0x1800a05ff  mov     rbx, [rbx+8]
0x1800a0603  test    rbx, rbx
0x1800a0606  jz      loc_1800A07F9
0x1800a060c  lea     r15, WPP_GLOBAL_Control
0x1800a0613  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a061a  cmp     rcx, r15
0x1800a061d  jnz     short loc_1800A0693
0x1800a061f  mov     [rsp+78h+cbData], esi
0x1800a0626  lea     rax, [rsp+78h+cbData]
0x1800a062e  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800a0633  mov     [rsp+78h+phkResult], r12; lpData
0x1800a0638  mov     r9, rbp; lpType
0x1800a063b  xor     r8d, r8d; lpReserved
0x1800a063e  mov     rdx, rbx; lpValueName
0x1800a0641  mov     rcx, rdi; hKey
0x1800a0644  call    cs:__imp_RegQueryValueExW
0x1800a064a  mov     edi, eax
0x1800a064c  test    eax, eax
0x1800a064e  jz      loc_1800A0729
0x1800a0654  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a065b  cmp     rcx, r15
0x1800a065e  jz      loc_1800A059C
0x1800a0664  test    dword ptr [rcx+1Ch], 400000h
0x1800a066b  jz      loc_1800A059C
0x1800a0671  mov     edx, 1Fh
0x1800a0676  mov     [rsp+78h+phkResult], rbx
0x1800a067b  mov     r9d, eax
0x1800a067e  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800a0685  mov     rcx, [rcx+10h]
0x1800a0689  call    WPP_SF_dS
0x1800a068e  jmp     loc_1800A059C
0x1800a0693  test    dword ptr [rcx+1Ch], 200000h
0x1800a069a  jz      short loc_1800A061F
0x1800a069c  mov     edx, 1Dh
0x1800a06a1  mov     r9, rbx
0x1800a06a4  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800a06ab  mov     rcx, [rcx+10h]
0x1800a06af  call    WPP_SF_S
0x1800a06b4  jmp     loc_1800A061F
0x1800a06b9  lea     rdx, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800a06c0  jmp     loc_1800A0537
0x1800a06c5  test    r12, r12
0x1800a06c8  jz      loc_1800A077E
0x1800a06ce  test    r13, r13
0x1800a06d1  jnz     loc_1800A051A
0x1800a06d7  mov     edi, 54Fh
0x1800a06dc  lea     r8, a1125; "1125"
0x1800a06e3  mov     edx, 465h
0x1800a06e8  jmp     loc_1800A0908
0x1800a06ed  test    r12, r12
0x1800a06f0  jz      loc_1800A07A5
0x1800a06f6  test    r13, r13
0x1800a06f9  jnz     loc_1800A05F1
0x1800a06ff  mov     [rsp+78h+phkResult], r15; struct IRequestContext *
0x1800a0704  mov     edi, 54Fh
0x1800a0709  mov     r9d, edi; unsigned int
0x1800a070c  lea     r8, a506; "506"
0x1800a0713  mov     edx, 1FAh; unsigned int
0x1800a0718  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800a071f  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800a0724  jmp     loc_1800A059C
0x1800a0729  mov     eax, [rsp+78h+cbData]
0x1800a0730  mov     [r13+0], eax
0x1800a0734  test    r12, r12
0x1800a0737  jnz     loc_1800A059C
0x1800a073d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0744  cmp     rcx, r15
0x1800a0747  jz      short loc_1800A0756
0x1800a0749  test    dword ptr [rcx+1Ch], 400000h
0x1800a0750  jnz     loc_1800A0823
0x1800a0756  mov     edi, 7Ah ; 'z'
0x1800a075b  mov     ecx, edi; dwErrCode
0x1800a075d  call    cs:__imp_SetLastError
0x1800a0763  jmp     loc_1800A059C
0x1800a0768  mov     edi, 54Fh
0x1800a076d  lea     r8, a1121; "1121"
0x1800a0774  mov     edx, 461h
0x1800a0779  jmp     loc_1800A0908
0x1800a077e  mov     edi, 54Fh
0x1800a0783  lea     r8, a1124; "1124"
0x1800a078a  mov     edx, 464h
0x1800a078f  jmp     loc_1800A0908
0x1800a0794  mov     edx, 422h
0x1800a0799  lea     r8, a1058; "1058"
0x1800a07a0  jmp     loc_1800A08E0
0x1800a07a5  mov     [rsp+78h+phkResult], r15; struct IRequestContext *
0x1800a07aa  mov     edi, 54Fh
0x1800a07af  mov     r9d, edi; unsigned int
0x1800a07b2  lea     r8, a505; "505"
0x1800a07b9  mov     edx, 1F9h; unsigned int
0x1800a07be  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800a07c5  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800a07ca  jmp     loc_1800A059C
0x1800a07cf  mov     [rsp+78h+phkResult], r15; struct IRequestContext *
0x1800a07d4  mov     edi, 54Fh
0x1800a07d9  mov     r9d, edi; unsigned int
0x1800a07dc  lea     r8, a508; "508"
0x1800a07e3  mov     edx, 1FCh; unsigned int
0x1800a07e8  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800a07ef  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800a07f4  jmp     loc_1800A059C
0x1800a07f9  mov     [rsp+78h+phkResult], r15; struct IRequestContext *
0x1800a07fe  mov     edi, 54Fh
0x1800a0803  mov     r9d, edi; unsigned int
0x1800a0806  lea     r8, a509; "509"
0x1800a080d  mov     edx, 1FDh; unsigned int
0x1800a0812  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800a0819  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800a081e  jmp     loc_1800A059C
0x1800a0823  mov     edx, 1Eh
0x1800a0828  mov     r9, rbx
0x1800a082b  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800a0832  mov     rcx, [rcx+10h]
0x1800a0836  call    WPP_SF_S
0x1800a083b  jmp     loc_1800A0756
0x1800a0840  mov     edx, 37h ; '7'
0x1800a0845  mov     r9, [rbx+8]
0x1800a0849  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800a0850  mov     rcx, [rcx+10h]
0x1800a0854  call    WPP_SF_S
0x1800a0859  jmp     loc_1800A059C
0x1800a085e  lea     r15, WPP_GLOBAL_Control
0x1800a0865  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a086c  cmp     rcx, r15
0x1800a086f  jz      short loc_1800A089B
0x1800a0871  test    dword ptr [rcx+1Ch], 400000h
0x1800a0878  jz      short loc_1800A089B
0x1800a087a  mov     edx, 38h ; '8'
0x1800a087f  mov     rax, [rbx+8]
0x1800a0883  mov     [rsp+78h+phkResult], rax
0x1800a0888  mov     r9d, edi
0x1800a088b  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800a0892  mov     rcx, [rcx+10h]
0x1800a0896  call    WPP_SF_dS
0x1800a089b  mov     ecx, edi; dwErrCode
0x1800a089d  call    cs:__imp_SetLastError
0x1800a08a3  mov     rcx, [rsp+78h+arg_8]
0x1800a08ab  test    rcx, rcx
0x1800a08ae  jz      loc_1800A059C
0x1800a08b4  mov     rax, [rcx]
0x1800a08b7  mov     r9d, edi
0x1800a08ba  lea     r8, aRegopenkeyex; "RegOpenKeyEx"
0x1800a08c1  mov     edx, 4033C360h
0x1800a08c6  mov     rax, [rax+58h]
0x1800a08ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a08cf  jmp     loc_1800A059C
0x1800a08d4  mov     edx, 43Fh; unsigned int
0x1800a08d9  lea     r8, a1087; "1087"
0x1800a08e0  mov     edi, 54Fh
0x1800a08e5  xor     r14d, r14d
0x1800a08e8  mov     r9d, edi; unsigned int
0x1800a08eb  mov     [rsp+78h+phkResult], r14; struct IRequestContext *
0x1800a08f0  lea     rcx, aOnecoreAdminWm_41; "onecore\\admin\\wmi\\wmx\\config\\wsman"...
0x1800a08f7  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800a08fc  lea     r8, a1129; "1129"
0x1800a0903  mov     edx, 469h; unsigned int
0x1800a0908  mov     [rsp+78h+phkResult], r15; struct IRequestContext *
0x1800a090d  mov     r9d, edi; unsigned int
0x1800a0910  lea     rcx, aOnecoreAdminWm_41; "onecore\\admin\\wmi\\wmx\\config\\wsman"...
0x1800a0917  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800a091c  jmp     loc_1800A05B1
```
