# FaxGetSenderInformation

- ea: `0x18002a650`
- end: `0x18002aa7b`
- name: `FaxGetSenderInformation`
- size: `1067`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000abe4`
- `0x18002a650`
- `0x18002bb58`
- `0x18002bea8`
- `0x18002c064`
- `0x18002d224`
- `0x18002d854`
- `0x18003d4ca`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002aa4b`
- `ADVAPI32!RegCloseKey` at `0x18002aa4b`

## string_xrefs

- `0x18002a79e`: `Company`

## pseudocode

```c
__int64 __fastcall FaxGetSenderInformation(__int64 a1)
{
  unsigned __int16 *CurrentUserName; // r14
  unsigned __int16 *RegisteredOrganization; // rbp
  _DWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // esi
  HKEY v7; // rax
  const unsigned __int16 *v8; // r9
  HKEY v9; // rdi
  BYTE *RegistryStringValue; // rax
  BYTE *v11; // rax
  const unsigned __int16 *v12; // r9
  BYTE *v13; // rax
  BYTE *v14; // rax
  BYTE *v15; // rax
  BYTE *v16; // rax
  BYTE *v17; // rax
  BYTE *v18; // rax
  BYTE *v19; // rax
  BYTE *v20; // rax
  BYTE *v21; // rax
  BYTE *v22; // rax
  BYTE *v23; // rax
  BYTE *v24; // rax
  BYTE *v25; // rax
  BYTE *v26; // rax
  DWORD v28; // [rsp+20h] [rbp-58h]
  DWORD v29; // [rsp+20h] [rbp-58h]
  DWORD v30; // [rsp+20h] [rbp-58h]
  DWORD v31; // [rsp+20h] [rbp-58h]
  DWORD v32; // [rsp+20h] [rbp-58h]
  DWORD v33; // [rsp+20h] [rbp-58h]
  DWORD v34; // [rsp+20h] [rbp-58h]
  DWORD v35; // [rsp+20h] [rbp-58h]
  DWORD v36; // [rsp+20h] [rbp-58h]
  DWORD v37; // [rsp+20h] [rbp-58h]
  DWORD v38; // [rsp+20h] [rbp-58h]
  DWORD v39; // [rsp+20h] [rbp-58h]
  DWORD v40; // [rsp+20h] [rbp-58h]
  DWORD v41; // [rsp+20h] [rbp-58h]
  DWORD v42; // [rsp+20h] [rbp-58h]
  DWORD v43; // [rsp+20h] [rbp-58h]

  CurrentUserName = 0;
  RegisteredOrganization = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v4 == (_DWORD *)&WPP_GLOBAL_Control || (v4[7] & 0x1000) == 0 || *((_BYTE *)v4 + 25) < 2u )
      goto LABEL_11;
    v5 = 16;
LABEL_10:
    WPP_SF_(*((_QWORD *)v4 + 2), v5, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids);
LABEL_11:
    v6 = -2147024809;
    goto LABEL_44;
  }
  if ( *(_DWORD *)a1 != 136 )
  {
    if ( v4 == (_DWORD *)&WPP_GLOBAL_Control || (v4[7] & 0x1000) == 0 || *((_BYTE *)v4 + 25) < 2u )
      goto LABEL_11;
    v5 = 17;
    goto LABEL_10;
  }
  memset_0((void *)(a1 + 4), 0, 0x84u);
  *(_DWORD *)a1 = 136;
  CurrentUserName = GetCurrentUserNameEx();
  RegisteredOrganization = (unsigned __int16 *)GetRegisteredOrganization();
  v7 = OpenRegistryKey(HKEY_CURRENT_USER, L"Software\\Microsoft\\Fax\\UserInfo", 0, 0x20019u);
  v8 = &qword_1800435E8;
  if ( CurrentUserName )
    v8 = CurrentUserName;
  v9 = v7;
  RegistryStringValue = GetRegistryStringValue(v7, 1u, L"FullName", v8, v28);
  *(_QWORD *)(a1 + 8) = RegistryStringValue;
  if ( !RegistryStringValue )
    goto LABEL_39;
  v11 = GetRegistryStringValue(v9, 1u, L"FaxNumber", &qword_1800435E8, v29);
  *(_QWORD *)(a1 + 16) = v11;
  if ( !v11 )
    goto LABEL_39;
  v12 = &qword_1800435E8;
  if ( RegisteredOrganization )
    v12 = RegisteredOrganization;
  v13 = GetRegistryStringValue(v9, 1u, L"Company", v12, v30);
  *(_QWORD *)(a1 + 24) = v13;
  if ( !v13 )
    goto LABEL_39;
  v14 = GetRegistryStringValue(v9, 1u, L"Address", &qword_1800435E8, v31);
  *(_QWORD *)(a1 + 32) = v14;
  if ( !v14 )
    goto LABEL_39;
  v15 = GetRegistryStringValue(v9, 1u, L"City", &qword_1800435E8, v32);
  *(_QWORD *)(a1 + 40) = v15;
  if ( !v15 )
    goto LABEL_39;
  v16 = GetRegistryStringValue(v9, 1u, L"State", &qword_1800435E8, v33);
  *(_QWORD *)(a1 + 48) = v16;
  if ( !v16 )
    goto LABEL_39;
  v17 = GetRegistryStringValue(v9, 1u, L"ZIP", &qword_1800435E8, v34);
  *(_QWORD *)(a1 + 56) = v17;
  if ( !v17 )
    goto LABEL_39;
  v18 = GetRegistryStringValue(v9, 1u, L"Country", &qword_1800435E8, v35);
  *(_QWORD *)(a1 + 64) = v18;
  if ( !v18 )
    goto LABEL_39;
  v19 = GetRegistryStringValue(v9, 1u, L"Title", &qword_1800435E8, v36);
  *(_QWORD *)(a1 + 72) = v19;
  if ( !v19 )
    goto LABEL_39;
  v20 = GetRegistryStringValue(v9, 1u, L"Department", &qword_1800435E8, v37);
  *(_QWORD *)(a1 + 80) = v20;
  if ( !v20 )
    goto LABEL_39;
  v21 = GetRegistryStringValue(v9, 1u, L"Office", &qword_1800435E8, v38);
  *(_QWORD *)(a1 + 88) = v21;
  if ( !v21 )
    goto LABEL_39;
  v22 = GetRegistryStringValue(v9, 1u, L"HomePhone", &qword_1800435E8, v39);
  *(_QWORD *)(a1 + 96) = v22;
  if ( !v22 )
    goto LABEL_39;
  v23 = GetRegistryStringValue(v9, 1u, L"OfficePhone", &qword_1800435E8, v40);
  *(_QWORD *)(a1 + 104) = v23;
  if ( !v23
    || (v24 = GetRegistryStringValue(v9, 1u, L"BillingCode", &qword_1800435E8, v41), (*(_QWORD *)(a1 + 120) = v24) == 0)
    || (v25 = GetRegistryStringValue(v9, 1u, L"Mailbox", &qword_1800435E8, v42), (*(_QWORD *)(a1 + 112) = v25) == 0)
    || (v6 = 0, v26 = GetRegistryStringValue(v9, 1u, L"TSID", &qword_1800435E8, v43), (*(_QWORD *)(a1 + 128) = v26) == 0) )
  {
LABEL_39:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids);
    }
    v6 = -2147024888;
    pMemFree(*(LPVOID *)(a1 + 8));
    pMemFree(*(LPVOID *)(a1 + 16));
    pMemFree(*(LPVOID *)(a1 + 24));
    pMemFree(*(LPVOID *)(a1 + 32));
    pMemFree(*(LPVOID *)(a1 + 40));
    pMemFree(*(LPVOID *)(a1 + 48));
    pMemFree(*(LPVOID *)(a1 + 56));
    pMemFree(*(LPVOID *)(a1 + 64));
    pMemFree(*(LPVOID *)(a1 + 72));
    pMemFree(*(LPVOID *)(a1 + 80));
    pMemFree(*(LPVOID *)(a1 + 88));
    pMemFree(*(LPVOID *)(a1 + 96));
    pMemFree(*(LPVOID *)(a1 + 104));
    pMemFree(*(LPVOID *)(a1 + 120));
    pMemFree(*(LPVOID *)(a1 + 112));
    pMemFree(*(LPVOID *)(a1 + 128));
  }
  if ( v9 )
    RegCloseKey(v9);
LABEL_44:
  pMemFree(CurrentUserName);
  pMemFree(RegisteredOrganization);
  return v6;
}

```

## disassembly

```asm
0x18002a650  push    rbx
0x18002a652  push    rbp
0x18002a653  push    rsi
0x18002a654  push    rdi
0x18002a655  push    r12
0x18002a657  push    r13
0x18002a659  push    r14
0x18002a65b  push    r15
0x18002a65d  sub     rsp, 38h
0x18002a661  xor     r14d, r14d
0x18002a664  mov     rbx, rcx
0x18002a667  xor     ebp, ebp
0x18002a669  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a670  lea     rax, WPP_GLOBAL_Control
0x18002a677  mov     r13d, 1000h
0x18002a67d  cmp     rcx, rax
0x18002a680  jz      short loc_18002A6AF
0x18002a682  test    [rcx+1Ch], r13d
0x18002a686  jz      short loc_18002A6AF
0x18002a688  cmp     byte ptr [rcx+19h], 5
0x18002a68c  jb      short loc_18002A6AF
0x18002a68e  mov     rcx, [rcx+10h]
0x18002a692  lea     edx, [rbp+0Fh]
0x18002a695  lea     r8, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids
0x18002a69c  call    WPP_SF_
0x18002a6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6a8  lea     rax, WPP_GLOBAL_Control
0x18002a6af  test    rbx, rbx
0x18002a6b2  jnz     short loc_18002A6E2
0x18002a6b4  cmp     rcx, rax
0x18002a6b7  jz      short loc_18002A6D8
0x18002a6b9  test    [rcx+1Ch], r13d
0x18002a6bd  jz      short loc_18002A6D8
0x18002a6bf  cmp     byte ptr [rcx+19h], 2
0x18002a6c3  jb      short loc_18002A6D8
0x18002a6c5  lea     edx, [rbx+10h]
0x18002a6c8  mov     rcx, [rcx+10h]
0x18002a6cc  lea     r8, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids
0x18002a6d3  call    WPP_SF_
0x18002a6d8  mov     esi, 80070057h
0x18002a6dd  jmp     loc_18002AA57
0x18002a6e2  mov     edi, 88h
0x18002a6e7  cmp     [rbx], edi
0x18002a6e9  jz      short loc_18002A701
0x18002a6eb  cmp     rcx, rax
0x18002a6ee  jz      short loc_18002A6D8
0x18002a6f0  test    [rcx+1Ch], r13d
0x18002a6f4  jz      short loc_18002A6D8
0x18002a6f6  cmp     byte ptr [rcx+19h], 2
0x18002a6fa  jb      short loc_18002A6D8
0x18002a6fc  lea     edx, [rdi-77h]
0x18002a6ff  jmp     short loc_18002A6C8
0x18002a701  lea     rcx, [rbx+4]; void *
0x18002a705  xor     edx, edx; Val
0x18002a707  mov     r8d, 84h; Size
0x18002a70d  call    memset_0
0x18002a712  mov     [rbx], edi
0x18002a714  call    GetCurrentUserNameEx
0x18002a719  mov     r14, rax
0x18002a71c  call    GetRegisteredOrganization
0x18002a721  mov     r9d, 20019h
0x18002a727  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Fax\\UserInfo"
0x18002a72e  xor     r8d, r8d
0x18002a731  mov     rcx, 0FFFFFFFF80000001h
0x18002a738  mov     rbp, rax
0x18002a73b  call    OpenRegistryKey
0x18002a740  lea     r15, qword_1800435E8
0x18002a747  test    r14, r14
0x18002a74a  mov     r9, r15
0x18002a74d  lea     r8, ValueName; "FullName"
0x18002a754  mov     r12d, 1
0x18002a75a  cmovnz  r9, r14; unsigned __int16 *
0x18002a75e  mov     edx, r12d; dwType
0x18002a761  mov     rcx, rax; hKey
0x18002a764  mov     rdi, rax
0x18002a767  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a76c  mov     [rbx+8], rax
0x18002a770  test    rax, rax
0x18002a773  jz      loc_18002A977
0x18002a779  mov     r9, r15; unsigned __int16 *
0x18002a77c  lea     r8, aFaxnumber; "FaxNumber"
0x18002a783  mov     edx, r12d; dwType
0x18002a786  mov     rcx, rdi; hKey
0x18002a789  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a78e  mov     [rbx+10h], rax
0x18002a792  test    rax, rax
0x18002a795  jz      loc_18002A977
0x18002a79b  test    rbp, rbp
0x18002a79e  lea     r8, aCompany; "Company"
0x18002a7a5  mov     r9, r15
0x18002a7a8  mov     edx, r12d; dwType
0x18002a7ab  cmovnz  r9, rbp; unsigned __int16 *
0x18002a7af  mov     rcx, rdi; hKey
0x18002a7b2  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a7b7  mov     [rbx+18h], rax
0x18002a7bb  test    rax, rax
0x18002a7be  jz      loc_18002A977
0x18002a7c4  mov     r9, r15; unsigned __int16 *
0x18002a7c7  lea     r8, aAddress; "Address"
0x18002a7ce  mov     edx, r12d; dwType
0x18002a7d1  mov     rcx, rdi; hKey
0x18002a7d4  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a7d9  mov     [rbx+20h], rax
0x18002a7dd  test    rax, rax
0x18002a7e0  jz      loc_18002A977
0x18002a7e6  mov     r9, r15; unsigned __int16 *
0x18002a7e9  lea     r8, aCity; "City"
0x18002a7f0  mov     edx, r12d; dwType
0x18002a7f3  mov     rcx, rdi; hKey
0x18002a7f6  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a7fb  mov     [rbx+28h], rax
0x18002a7ff  test    rax, rax
0x18002a802  jz      loc_18002A977
0x18002a808  mov     r9, r15; unsigned __int16 *
0x18002a80b  lea     r8, aState; "State"
0x18002a812  mov     edx, r12d; dwType
0x18002a815  mov     rcx, rdi; hKey
0x18002a818  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a81d  mov     [rbx+30h], rax
0x18002a821  test    rax, rax
0x18002a824  jz      loc_18002A977
0x18002a82a  mov     r9, r15; unsigned __int16 *
0x18002a82d  lea     r8, aZip; "ZIP"
0x18002a834  mov     edx, r12d; dwType
0x18002a837  mov     rcx, rdi; hKey
0x18002a83a  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a83f  mov     [rbx+38h], rax
0x18002a843  test    rax, rax
0x18002a846  jz      loc_18002A977
0x18002a84c  mov     r9, r15; unsigned __int16 *
0x18002a84f  lea     r8, aCountry; "Country"
0x18002a856  mov     edx, r12d; dwType
0x18002a859  mov     rcx, rdi; hKey
0x18002a85c  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a861  mov     [rbx+40h], rax
0x18002a865  test    rax, rax
0x18002a868  jz      loc_18002A977
0x18002a86e  mov     r9, r15; unsigned __int16 *
0x18002a871  lea     r8, aTitle; "Title"
0x18002a878  mov     edx, r12d; dwType
0x18002a87b  mov     rcx, rdi; hKey
0x18002a87e  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a883  mov     [rbx+48h], rax
0x18002a887  test    rax, rax
0x18002a88a  jz      loc_18002A977
0x18002a890  mov     r9, r15; unsigned __int16 *
0x18002a893  lea     r8, aDepartment; "Department"
0x18002a89a  mov     edx, r12d; dwType
0x18002a89d  mov     rcx, rdi; hKey
0x18002a8a0  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a8a5  mov     [rbx+50h], rax
0x18002a8a9  test    rax, rax
0x18002a8ac  jz      loc_18002A977
0x18002a8b2  mov     r9, r15; unsigned __int16 *
0x18002a8b5  lea     r8, aOffice; "Office"
0x18002a8bc  mov     edx, r12d; dwType
0x18002a8bf  mov     rcx, rdi; hKey
0x18002a8c2  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a8c7  mov     [rbx+58h], rax
0x18002a8cb  test    rax, rax
0x18002a8ce  jz      loc_18002A977
0x18002a8d4  mov     r9, r15; unsigned __int16 *
0x18002a8d7  lea     r8, aHomephone; "HomePhone"
0x18002a8de  mov     edx, r12d; dwType
0x18002a8e1  mov     rcx, rdi; hKey
0x18002a8e4  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a8e9  mov     [rbx+60h], rax
0x18002a8ed  test    rax, rax
0x18002a8f0  jz      loc_18002A977
0x18002a8f6  mov     r9, r15; unsigned __int16 *
0x18002a8f9  lea     r8, aOfficephone; "OfficePhone"
0x18002a900  mov     edx, r12d; dwType
0x18002a903  mov     rcx, rdi; hKey
0x18002a906  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a90b  mov     [rbx+68h], rax
0x18002a90f  test    rax, rax
0x18002a912  jz      short loc_18002A977
0x18002a914  mov     r9, r15; unsigned __int16 *
0x18002a917  lea     r8, aBillingcode; "BillingCode"
0x18002a91e  mov     edx, r12d; dwType
0x18002a921  mov     rcx, rdi; hKey
0x18002a924  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a929  mov     [rbx+78h], rax
0x18002a92d  test    rax, rax
0x18002a930  jz      short loc_18002A977
0x18002a932  mov     r9, r15; unsigned __int16 *
0x18002a935  lea     r8, aMailbox; "Mailbox"
0x18002a93c  mov     edx, r12d; dwType
0x18002a93f  mov     rcx, rdi; hKey
0x18002a942  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a947  mov     [rbx+70h], rax
0x18002a94b  test    rax, rax
0x18002a94e  jz      short loc_18002A977
0x18002a950  mov     r9, r15; unsigned __int16 *
0x18002a953  lea     r8, aTsid; "TSID"
0x18002a95a  mov     edx, r12d; dwType
0x18002a95d  mov     rcx, rdi; hKey
0x18002a960  xor     esi, esi
0x18002a962  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18002a967  mov     [rbx+80h], rax
0x18002a96e  test    rax, rax
0x18002a971  jnz     loc_18002AA43
0x18002a977  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a97e  lea     rax, WPP_GLOBAL_Control
0x18002a985  cmp     rcx, rax
0x18002a988  jz      short loc_18002A9AB
0x18002a98a  test    [rcx+1Ch], r13d
0x18002a98e  jz      short loc_18002A9AB
0x18002a990  cmp     byte ptr [rcx+19h], 2
0x18002a994  jb      short loc_18002A9AB
0x18002a996  mov     rcx, [rcx+10h]
0x18002a99a  lea     r8, WPP_e8cc5d09478f38214c8caffa112c128f_Traceguids
0x18002a9a1  mov     edx, 12h
0x18002a9a6  call    WPP_SF_
0x18002a9ab  mov     esi, 80070008h
0x18002a9b0  mov     rcx, [rbx+8]; lpMem
0x18002a9b4  call    pMemFree
0x18002a9b9  mov     rcx, [rbx+10h]; lpMem
0x18002a9bd  call    pMemFree
0x18002a9c2  mov     rcx, [rbx+18h]; lpMem
0x18002a9c6  call    pMemFree
0x18002a9cb  mov     rcx, [rbx+20h]; lpMem
0x18002a9cf  call    pMemFree
0x18002a9d4  mov     rcx, [rbx+28h]; lpMem
0x18002a9d8  call    pMemFree
0x18002a9dd  mov     rcx, [rbx+30h]; lpMem
0x18002a9e1  call    pMemFree
0x18002a9e6  mov     rcx, [rbx+38h]; lpMem
0x18002a9ea  call    pMemFree
0x18002a9ef  mov     rcx, [rbx+40h]; lpMem
0x18002a9f3  call    pMemFree
0x18002a9f8  mov     rcx, [rbx+48h]; lpMem
0x18002a9fc  call    pMemFree
0x18002aa01  mov     rcx, [rbx+50h]; lpMem
0x18002aa05  call    pMemFree
0x18002aa0a  mov     rcx, [rbx+58h]; lpMem
0x18002aa0e  call    pMemFree
0x18002aa13  mov     rcx, [rbx+60h]; lpMem
0x18002aa17  call    pMemFree
0x18002aa1c  mov     rcx, [rbx+68h]; lpMem
0x18002aa20  call    pMemFree
0x18002aa25  mov     rcx, [rbx+78h]; lpMem
0x18002aa29  call    pMemFree
0x18002aa2e  mov     rcx, [rbx+70h]; lpMem
0x18002aa32  call    pMemFree
0x18002aa37  mov     rcx, [rbx+80h]; lpMem
0x18002aa3e  call    pMemFree
0x18002aa43  test    rdi, rdi
0x18002aa46  jz      short loc_18002AA57
0x18002aa48  mov     rcx, rdi; hKey
0x18002aa4b  call    cs:__imp_RegCloseKey
0x18002aa52  nop     dword ptr [rax+rax+00h]
0x18002aa57  mov     rcx, r14; lpMem
0x18002aa5a  call    pMemFree
0x18002aa5f  mov     rcx, rbp; lpMem
0x18002aa62  call    pMemFree
0x18002aa67  mov     eax, esi
0x18002aa69  add     rsp, 38h
0x18002aa6d  pop     r15
0x18002aa6f  pop     r14
0x18002aa71  pop     r13
0x18002aa73  pop     r12
0x18002aa75  pop     rdi
0x18002aa76  pop     rsi
0x18002aa77  pop     rbp
0x18002aa78  pop     rbx
0x18002aa79  retn
```
