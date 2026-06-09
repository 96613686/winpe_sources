# FveBackupMonitor::GetAdminMSAUsersCountImpl(ulong *)

- ea: `0x18006ff08`
- end: `0x180070371`
- name: `?GetAdminMSAUsersCountImpl@FveBackupMonitor@@CAJPEAK@Z`
- size: `1129`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006fde8`

## callees

- `0x180009f60`
- `0x18001d09c`
- `0x18006ff08`
- `0x180070cd0`
- `0x180070cfc`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070261`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070323`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070323`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006ffc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006ffc1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800700d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180070333`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800700d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180070333`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800701e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800701e9`

## pseudocode

```c
__int64 __fastcall FveBackupMonitor::GetAdminMSAUsersCountImpl(unsigned int *a1)
{
  signed int v2; // ebx
  unsigned int v3; // eax
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, _QWORD, _QWORD, _QWORD, __int64 *); // rbx
  unsigned int v6; // eax
  unsigned int v7; // r12d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *); // rbx
  int v10; // eax
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rdi
  unsigned int v13; // eax
  unsigned int v14; // eax
  PVOID *v15; // rcx
  __int64 i; // rdi
  unsigned int IsAdminAccountBySID; // eax
  signed int LastError; // eax
  __int64 v19; // rdx
  bool v21; // [rsp+30h] [rbp-50h] BYREF
  __int64 v22; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-40h] BYREF
  int v24; // [rsp+48h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-30h] BYREF
  __int64 v26; // [rsp+58h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-20h] BYREF
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v29; // [rsp+78h] [rbp-8h]

  v24 = 0;
  ppv = 0;
  v26 = 0;
  v29 = 0;
  v21 = 0;
  hMem = 0;
  *(_OWORD *)pvar = 0;
  if ( a1 )
  {
    *a1 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v3 = CoCreateInstance(
           &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
           0,
           0x17u,
           &GUID_df586fa5_6f35_44f1_b209_b38e169772eb,
           &ppv);
    v2 = v3;
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_929186be452536e5252128d48ffaedab_Traceguids, v3);
      if ( v2 < 0 )
        goto LABEL_63;
    }
    v4 = ppv;
    v5 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 56LL);
    Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(&v26);
    v6 = v5(v4, 0, 0, 0, &v26);
    v2 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_929186be452536e5252128d48ffaedab_Traceguids, v6);
      if ( v2 < 0 )
        goto LABEL_63;
    }
    v7 = 0;
LABEL_16:
    v8 = v26;
    v23 = 0;
    v22 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v26 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v10 = v9(v8, 1, &v23, &v24);
    if ( v10 < 0 || v10 == 1 || !v24 )
    {
      v2 = 0;
      if ( v10 != 1 )
        v2 = v10;
      Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(&v22);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      if ( !v2 )
        goto LABEL_62;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          WPP_929186be452536e5252128d48ffaedab_Traceguids,
          (unsigned int)v2);
      if ( v2 >= 0 )
LABEL_62:
        *a1 = v7;
      goto LABEL_63;
    }
    PropVariantClear(pvar);
    v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
    v12 = **v23;
    Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(&v22);
    v13 = v12(v11, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v22);
    v2 = v13;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_929186be452536e5252128d48ffaedab_Traceguids, v13);
      if ( v2 < 0 )
        goto LABEL_29;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v22 + 40LL))(
            v22,
            &PKEY_Identity_ProviderData,
            pvar);
    v2 = v14;
    if ( v14 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_929186be452536e5252128d48ffaedab_Traceguids, v14);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 < 0 )
        goto LABEL_29;
    }
    else
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( LOWORD(pvar[0]) == 4127 )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= LODWORD(pvar[1]) )
          goto LABEL_45;
        if ( hMem )
        {
          LocalFree(hMem);
          hMem = 0;
        }
        if ( !ConvertStringSidToSidW(*(LPCWSTR *)(v29 + 8 * i), &hMem) )
          break;
        IsAdminAccountBySID = FveBackupMonitor::IsAdminAccountBySID(hMem, &v21);
        v2 = IsAdminAccountBySID;
        if ( IsAdminAccountBySID )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              65,
              WPP_929186be452536e5252128d48ffaedab_Traceguids,
              IsAdminAccountBySID);
          if ( v2 < 0 )
            goto LABEL_29;
        }
        if ( v21 )
        {
          ++v7;
LABEL_45:
          Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(&v22);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          goto LABEL_16;
        }
      }
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_29;
      v19 = 64;
    }
    else
    {
      v2 = -2147418113;
      if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 )
        goto LABEL_29;
      v19 = 63;
    }
    WPP_SF_d(v15[2], v19, WPP_929186be452536e5252128d48ffaedab_Traceguids, (unsigned int)v2);
LABEL_29:
    Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    goto LABEL_63;
  }
  v2 = -2147467261;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    goto LABEL_65;
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_929186be452536e5252128d48ffaedab_Traceguids, 2147500035LL);
LABEL_63:
  if ( hMem )
    LocalFree(hMem);
LABEL_65:
  PropVariantClear(pvar);
  Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18006ff08  mov     [rsp-28h+arg_8], rbx
0x18006ff0d  mov     [rsp-28h+arg_10], rdi
0x18006ff12  push    rbp
0x18006ff13  push    r12
0x18006ff15  push    r13
0x18006ff17  push    r14
0x18006ff19  push    r15
0x18006ff1b  mov     rbp, rsp
0x18006ff1e  sub     rsp, 80h
0x18006ff25  xor     eax, eax
0x18006ff27  mov     [rbp+var_38], 0
0x18006ff2e  mov     [rbp+var_20], 0
0x18006ff36  xorps   xmm0, xmm0
0x18006ff39  mov     [rbp+var_28], 0
0x18006ff41  mov     r13, rcx
0x18006ff44  mov     [rbp+var_8], rax
0x18006ff48  mov     [rbp+var_50], al
0x18006ff4b  mov     [rbp+hMem], rax
0x18006ff4f  movups  xmmword ptr [rbp+pvar], xmm0
0x18006ff53  test    rcx, rcx
0x18006ff56  jnz     short loc_18006FF99
0x18006ff58  mov     ebx, 80004003h
0x18006ff5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ff64  lea     r14, WPP_GLOBAL_Control
0x18006ff6b  cmp     rcx, r14
0x18006ff6e  jz      loc_18007032F
0x18006ff74  test    byte ptr [rcx+1Ch], 40h
0x18006ff78  jz      loc_18007032F
0x18006ff7e  mov     rcx, [rcx+10h]
0x18006ff82  lea     edx, [rax+3Ah]
0x18006ff85  mov     r9d, ebx
0x18006ff88  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18006ff8f  call    WPP_SF_d
0x18006ff94  jmp     loc_18007031A
0x18006ff99  mov     [rcx], eax
0x18006ff9b  lea     rcx, [rbp+var_20]
0x18006ff9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ffa4  xor     edx, edx; pUnkOuter
0x18006ffa6  lea     rax, [rbp+var_20]
0x18006ffaa  lea     r9, _GUID_df586fa5_6f35_44f1_b209_b38e169772eb; riid
0x18006ffb1  mov     [rsp+80h+ppv], rax; ppv
0x18006ffb6  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x18006ffbd  lea     r8d, [rdx+17h]; dwClsContext
0x18006ffc1  call    cs:__imp_CoCreateInstance
0x18006ffc8  nop     dword ptr [rax+rax+00h]
0x18006ffcd  lea     r14, WPP_GLOBAL_Control
0x18006ffd4  mov     ebx, eax
0x18006ffd6  lea     r15, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18006ffdd  test    eax, eax
0x18006ffdf  jz      short loc_18007000F
0x18006ffe1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ffe8  cmp     rcx, r14
0x18006ffeb  jz      short loc_180070007
0x18006ffed  test    byte ptr [rcx+1Ch], 40h
0x18006fff1  jz      short loc_180070007
0x18006fff3  mov     rcx, [rcx+10h]
0x18006fff7  mov     edx, 3Bh ; ';'
0x18006fffc  mov     r9d, eax
0x18006ffff  mov     r8, r15
0x180070002  call    WPP_SF_d
0x180070007  test    ebx, ebx
0x180070009  js      loc_18007031A
0x18007000f  mov     rdi, [rbp+var_20]
0x180070013  lea     rcx, [rbp+var_28]
0x180070017  mov     rax, [rdi]
0x18007001a  mov     rbx, [rax+38h]
0x18007001e  call    ?InternalRelease@?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(void)
0x180070023  lea     rax, [rbp+var_28]
0x180070027  xor     r9d, r9d
0x18007002a  mov     [rsp+80h+ppv], rax
0x18007002f  xor     r8d, r8d
0x180070032  mov     rax, rbx
0x180070035  xor     edx, edx
0x180070037  mov     rcx, rdi
0x18007003a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007003f  mov     ebx, eax
0x180070041  test    eax, eax
0x180070043  jz      short loc_180070073
0x180070045  mov     rcx, cs:WPP_GLOBAL_Control
0x18007004c  cmp     rcx, r14
0x18007004f  jz      short loc_18007006B
0x180070051  test    byte ptr [rcx+1Ch], 40h
0x180070055  jz      short loc_18007006B
0x180070057  mov     rcx, [rcx+10h]
0x18007005b  mov     edx, 3Ch ; '<'
0x180070060  mov     r9d, eax
0x180070063  mov     r8, r15
0x180070066  call    WPP_SF_d
0x18007006b  test    ebx, ebx
0x18007006d  js      loc_18007031A
0x180070073  xor     r12d, r12d
0x180070076  mov     rdi, [rbp+var_28]
0x18007007a  lea     rcx, [rbp+var_40]
0x18007007e  mov     [rbp+var_40], 0
0x180070086  mov     [rbp+var_48], 0
0x18007008e  mov     rax, [rdi]
0x180070091  mov     rbx, [rax+18h]
0x180070095  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007009a  lea     r9, [rbp+var_38]
0x18007009e  mov     edx, 1
0x1800700a3  lea     r8, [rbp+var_40]
0x1800700a7  mov     rcx, rdi
0x1800700aa  mov     rax, rbx
0x1800700ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800700b2  test    eax, eax
0x1800700b4  js      loc_1800702CE
0x1800700ba  cmp     eax, 1
0x1800700bd  jz      loc_1800702CE
0x1800700c3  cmp     [rbp+var_38], 0
0x1800700c7  jz      loc_1800702CE
0x1800700cd  lea     rcx, [rbp+pvar]; pvar
0x1800700d1  call    cs:__imp_PropVariantClear
0x1800700d8  nop     dword ptr [rax+rax+00h]
0x1800700dd  mov     rbx, [rbp+var_40]
0x1800700e1  lea     rcx, [rbp+var_48]
0x1800700e5  mov     rax, [rbx]
0x1800700e8  mov     rdi, [rax]
0x1800700eb  call    ?InternalRelease@?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(void)
0x1800700f0  lea     r8, [rbp+var_48]
0x1800700f4  mov     rcx, rbx
0x1800700f7  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800700fe  mov     rax, rdi
0x180070101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070106  mov     ebx, eax
0x180070108  test    eax, eax
0x18007010a  jz      short loc_180070136
0x18007010c  mov     rcx, cs:WPP_GLOBAL_Control
0x180070113  cmp     rcx, r14
0x180070116  jz      short loc_180070132
0x180070118  test    byte ptr [rcx+1Ch], 40h
0x18007011c  jz      short loc_180070132
0x18007011e  mov     rcx, [rcx+10h]
0x180070122  mov     edx, 3Dh ; '='
0x180070127  mov     r9d, eax
0x18007012a  mov     r8, r15
0x18007012d  call    WPP_SF_d
0x180070132  test    ebx, ebx
0x180070134  js      short loc_180070188
0x180070136  mov     rcx, [rbp+var_48]
0x18007013a  lea     r8, [rbp+pvar]
0x18007013e  lea     rdx, PKEY_Identity_ProviderData
0x180070145  mov     rax, [rcx]
0x180070148  mov     rax, [rax+28h]
0x18007014c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070151  mov     ebx, eax
0x180070153  test    eax, eax
0x180070155  jz      short loc_18007019F
0x180070157  mov     rcx, cs:WPP_GLOBAL_Control
0x18007015e  cmp     rcx, r14
0x180070161  jz      short loc_180070184
0x180070163  test    byte ptr [rcx+1Ch], 40h
0x180070167  jz      short loc_180070184
0x180070169  mov     rcx, [rcx+10h]
0x18007016d  mov     edx, 3Eh ; '>'
0x180070172  mov     r9d, eax
0x180070175  mov     r8, r15
0x180070178  call    WPP_SF_d
0x18007017d  mov     rcx, cs:WPP_GLOBAL_Control
0x180070184  test    ebx, ebx
0x180070186  jns     short loc_1800701A6
0x180070188  lea     rcx, [rbp+var_48]
0x18007018c  call    ?InternalRelease@?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(void)
0x180070191  lea     rcx, [rbp+var_40]
0x180070195  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007019a  jmp     loc_18007031A
0x18007019f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800701a6  mov     eax, 101Fh
0x1800701ab  cmp     word ptr [rbp+pvar], ax
0x1800701af  jnz     loc_18007029D
0x1800701b5  xor     edi, edi
0x1800701b7  cmp     edi, dword ptr [rbp+pvar+8]
0x1800701ba  jnb     loc_18007024A
0x1800701c0  mov     rcx, [rbp+hMem]; hMem
0x1800701c4  test    rcx, rcx
0x1800701c7  jz      short loc_1800701DD
0x1800701c9  call    cs:__imp_LocalFree
0x1800701d0  nop     dword ptr [rax+rax+00h]
0x1800701d5  mov     [rbp+hMem], 0
0x1800701dd  mov     rcx, [rbp+var_8]
0x1800701e1  lea     rdx, [rbp+hMem]; Sid
0x1800701e5  mov     rcx, [rcx+rdi*8]; StringSid
0x1800701e9  call    cs:__imp_ConvertStringSidToSidW
0x1800701f0  nop     dword ptr [rax+rax+00h]
0x1800701f5  test    eax, eax
0x1800701f7  jz      short loc_180070261
0x1800701f9  mov     rcx, [rbp+hMem]; Sid
0x1800701fd  lea     rdx, [rbp+var_50]; bool *
0x180070201  call    ?IsAdminAccountBySID@FveBackupMonitor@@CAJPEAXPEA_N@Z; FveBackupMonitor::IsAdminAccountBySID(void *,bool *)
0x180070206  mov     ebx, eax
0x180070208  test    eax, eax
0x18007020a  jz      short loc_18007023A
0x18007020c  mov     rcx, cs:WPP_GLOBAL_Control
0x180070213  cmp     rcx, r14
0x180070216  jz      short loc_180070232
0x180070218  test    byte ptr [rcx+1Ch], 40h
0x18007021c  jz      short loc_180070232
0x18007021e  mov     rcx, [rcx+10h]
0x180070222  mov     edx, 41h ; 'A'
0x180070227  mov     r9d, eax
0x18007022a  mov     r8, r15
0x18007022d  call    WPP_SF_d
0x180070232  test    ebx, ebx
0x180070234  js      loc_180070188
0x18007023a  cmp     [rbp+var_50], 0
0x18007023e  jnz     short loc_180070247
0x180070240  inc     edi
0x180070242  jmp     loc_1800701B7
0x180070247  inc     r12d
0x18007024a  lea     rcx, [rbp+var_48]
0x18007024e  call    ?InternalRelease@?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(void)
0x180070253  lea     rcx, [rbp+var_40]
0x180070257  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007025c  jmp     loc_180070076
0x180070261  call    cs:__imp_GetLastError
0x180070268  nop     dword ptr [rax+rax+00h]
0x18007026d  mov     ebx, eax
0x18007026f  test    eax, eax
0x180070271  jle     short loc_18007027C
0x180070273  movzx   ebx, ax
0x180070276  or      ebx, 80070000h
0x18007027c  mov     rcx, cs:WPP_GLOBAL_Control
0x180070283  cmp     rcx, r14
0x180070286  jz      loc_180070188
0x18007028c  test    byte ptr [rcx+1Ch], 40h
0x180070290  jz      loc_180070188
0x180070296  mov     edx, 40h ; '@'
0x18007029b  jmp     short loc_1800702BA
0x18007029d  mov     ebx, 8000FFFFh
0x1800702a2  cmp     rcx, r14
0x1800702a5  jz      loc_180070188
0x1800702ab  test    byte ptr [rcx+1Ch], 40h
0x1800702af  jz      loc_180070188
0x1800702b5  mov     edx, 3Fh ; '?'
0x1800702ba  mov     rcx, [rcx+10h]
0x1800702be  mov     r9d, ebx
0x1800702c1  mov     r8, r15
0x1800702c4  call    WPP_SF_d
0x1800702c9  jmp     loc_180070188
0x1800702ce  xor     ebx, ebx
0x1800702d0  lea     rcx, [rbp+var_48]
0x1800702d4  cmp     eax, 1
0x1800702d7  cmovnz  ebx, eax
0x1800702da  call    ?InternalRelease@?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(void)
0x1800702df  lea     rcx, [rbp+var_40]
0x1800702e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800702e8  test    ebx, ebx
0x1800702ea  jz      short loc_180070316
0x1800702ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800702f3  cmp     rcx, r14
0x1800702f6  jz      short loc_180070312
0x1800702f8  test    byte ptr [rcx+1Ch], 40h
0x1800702fc  jz      short loc_180070312
0x1800702fe  mov     rcx, [rcx+10h]
0x180070302  mov     edx, 42h ; 'B'
0x180070307  mov     r9d, ebx
0x18007030a  mov     r8, r15
0x18007030d  call    WPP_SF_d
0x180070312  test    ebx, ebx
0x180070314  js      short loc_18007031A
0x180070316  mov     [r13+0], r12d
0x18007031a  mov     rcx, [rbp+hMem]; hMem
0x18007031e  test    rcx, rcx
0x180070321  jz      short loc_18007032F
0x180070323  call    cs:__imp_LocalFree
0x18007032a  nop     dword ptr [rax+rax+00h]
0x18007032f  lea     rcx, [rbp+pvar]; pvar
0x180070333  call    cs:__imp_PropVariantClear
0x18007033a  nop     dword ptr [rax+rax+00h]
0x18007033f  lea     rcx, [rbp+var_28]
0x180070343  call    ?InternalRelease@?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyStore>::InternalRelease(void)
0x180070348  lea     rcx, [rbp+var_20]
0x18007034c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070351  lea     r11, [rsp+80h+var_s0]
0x180070359  mov     eax, ebx
0x18007035b  mov     rbx, [r11+38h]
0x18007035f  mov     rdi, [r11+40h]
0x180070363  mov     rsp, r11
0x180070366  pop     r15
0x180070368  pop     r14
0x18007036a  pop     r13
0x18007036c  pop     r12
0x18007036e  pop     rbp
0x18007036f  retn
```
