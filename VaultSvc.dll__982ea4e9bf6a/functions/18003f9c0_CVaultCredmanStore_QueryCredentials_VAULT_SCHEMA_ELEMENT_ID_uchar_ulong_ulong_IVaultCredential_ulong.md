# CVaultCredmanStore::QueryCredentials(VAULT_SCHEMA_ELEMENT_ID,uchar *,ulong,ulong,IVaultCredential * * *,ulong *)

- ea: `0x18003f9c0`
- end: `0x18003ff75`
- name: `?QueryCredentials@CVaultCredmanStore@@UEAAKW4VAULT_SCHEMA_ELEMENT_ID@@PEAEKKPEAPEAPEAUIVaultCredential@@PEAK@Z`
- size: `1461`
- prototype: `__int64 __fastcall(struct _RTL_RESOURCE *, unsigned int, const WCHAR *, __int64, __int64, struct IVaultCredential ***, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003140`
- `0x18002e2e0`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003b9ac`
- `0x18003de28`
- `0x18003f9c0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003fc83`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003fc83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fbed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fbed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003fdc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003fdc2`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18003fb12`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18003fbdf`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18003fca0`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18003fb12`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18003fbdf`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18003fca0`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18003fa04`
- `ntdll!RtlReleaseResource` at `0x18003faf4`
- `ntdll!RtlReleaseResource` at `0x18003fb9e`
- `ntdll!RtlReleaseResource` at `0x18003fda6`
- `ntdll!RtlReleaseResource` at `0x18003fe06`
- `ntdll!RtlReleaseResource` at `0x18003ff58`
- `ntdll!RtlReleaseResource` at `0x18003faf4`
- `ntdll!RtlReleaseResource` at `0x18003fb9e`
- `ntdll!RtlReleaseResource` at `0x18003fda6`
- `ntdll!RtlReleaseResource` at `0x18003fe06`
- `ntdll!RtlReleaseResource` at `0x18003ff58`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVaultCredmanStore::QueryCredentials(
        struct _RTL_RESOURCE *a1,
        unsigned int a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        struct IVaultCredential ***a6,
        unsigned int *a7)
{
  unsigned int v10; // r15d
  DWORD LastError; // eax
  DWORD v13; // edi
  DWORD v14; // eax
  DWORD v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // edi
  struct IVaultCredential **v19; // rax
  struct IVaultCredential **v20; // r12
  unsigned int v21; // eax
  unsigned int v22; // r14d
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int i; // ebx
  struct IVaultCredential *v27; // rcx
  PRTL_RESOURCE Resource; // [rsp+20h] [rbp-71h] BYREF
  char v29; // [rsp+28h] [rbp-69h]
  void (__stdcall *v30)(PVOID); // [rsp+30h] [rbp-61h] BYREF
  PCREDENTIALW v31; // [rsp+38h] [rbp-59h] BYREF
  int v32; // [rsp+40h] [rbp-51h]
  void (__stdcall *v33)(PVOID); // [rsp+48h] [rbp-49h] BYREF
  PCREDENTIALW v34; // [rsp+50h] [rbp-41h] BYREF
  int v35; // [rsp+58h] [rbp-39h]
  void (__stdcall *v36)(PVOID); // [rsp+60h] [rbp-31h] BYREF
  PCREDENTIALW Credential; // [rsp+68h] [rbp-29h] BYREF
  int v38; // [rsp+70h] [rbp-21h]
  __int64 v39; // [rsp+78h] [rbp-19h] BYREF
  struct IVaultCredential **v40; // [rsp+80h] [rbp-11h]
  int v41; // [rsp+88h] [rbp-9h]

  CVaultRtlLock::CVaultRtlLock((__int64)&Resource, a1 + 2, 0);
  v10 = 0;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  v36 = CredFree;
  Credential = 0;
  v38 = 0;
  v33 = CredFree;
  v34 = 0;
  v35 = 0;
  v30 = CredFree;
  v31 = 0;
  v32 = 0;
  if ( a2 != 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, a2);
LABEL_10:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v30);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v33);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v39);
    if ( v29 )
      RtlReleaseResource(Resource);
    return 87;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids);
    goto LABEL_10;
  }
  if ( !CredReadW(a3, 2u, 0, &Credential) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError != 1168 && LastError != 87 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, LastError);
LABEL_19:
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v30);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v33);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v36);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v39);
      if ( v29 )
        RtlReleaseResource(Resource);
      return v13;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, a3);
  }
  if ( !CredReadW(a3, 3u, 0, &v34) )
  {
    v14 = GetLastError();
    v13 = v14;
    if ( v14 != 1168 && v14 != 87 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v14);
      goto LABEL_19;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, a3);
  }
  if ( wcschr(a3, 0x3Au) && !CredReadW(a3, 6u, 0, &v31) )
  {
    v15 = GetLastError();
    v13 = v15;
    if ( v15 == 1168 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v17 = 48;
        goto LABEL_49;
      }
    }
    else
    {
      if ( v15 != 87 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v15);
        goto LABEL_19;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v17 = 47;
LABEL_49:
        WPP_SF_S(v16[2], v17, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, a3);
      }
    }
  }
  v18 = Credential != 0;
  if ( v34 )
    ++v18;
  if ( v31 )
    ++v18;
  if ( !v18 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v30);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v33);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v39);
    if ( v29 )
      RtlReleaseResource(Resource);
    return 1168;
  }
  v19 = (struct IVaultCredential **)LocalAlloc(0x40u, 8 * v18);
  v20 = v19;
  v40 = v19;
  if ( !v19 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v30);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v33);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v39);
    if ( v29 )
      RtlReleaseResource(Resource);
    return 14;
  }
  if ( Credential )
  {
    v21 = CVaultCredmanStore::ConvertCredmanToVaultCredential((CVaultCredmanStore *)a1, Credential, v19);
    v22 = v21;
    if ( v21 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v24 = 49;
LABEL_67:
        WPP_SF_d(v23[2], v24, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v21);
        goto LABEL_75;
      }
      goto LABEL_75;
    }
    v10 = 1;
  }
  else
  {
    v22 = 0;
  }
  if ( v34 )
  {
    v25 = CVaultCredmanStore::ConvertCredmanToVaultCredential((CVaultCredmanStore *)a1, v34, &v20[v10]);
    v22 = v25;
    if ( v25 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v25);
      goto LABEL_75;
    }
    ++v10;
  }
  if ( v31 )
  {
    v21 = CVaultCredmanStore::ConvertCredmanToVaultCredential((CVaultCredmanStore *)a1, v31, &v20[v10]);
    v22 = v21;
    if ( v21 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v24 = 51;
        goto LABEL_67;
      }
LABEL_75:
      for ( i = 0; i < v18; ++i )
      {
        v27 = v20[i];
        if ( v27 )
          (*(void (__fastcall **)(struct IVaultCredential *))(*(_QWORD *)v27 + 8LL))(v27);
      }
      goto LABEL_87;
    }
  }
  *a6 = v20;
  *a7 = v18;
  v40 = 0;
LABEL_87:
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v30);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v33);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v36);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v39);
  if ( v29 )
    RtlReleaseResource(Resource);
  return v22;
}

```

## disassembly

```asm
0x18003f9c0  push    rbp
0x18003f9c2  push    rbx
0x18003f9c3  push    rsi
0x18003f9c4  push    rdi
0x18003f9c5  push    r12
0x18003f9c7  push    r13
0x18003f9c9  push    r14
0x18003f9cb  push    r15
0x18003f9cd  lea     rbp, [rsp-7]
0x18003f9d2  sub     rsp, 98h
0x18003f9d9  mov     r14, r8
0x18003f9dc  mov     edi, edx
0x18003f9de  mov     r13, rcx
0x18003f9e1  lea     rdx, [rcx+0C0h]
0x18003f9e8  xor     r8d, r8d
0x18003f9eb  lea     rcx, [rbp+3Fh+Resource]
0x18003f9ef  call    ??0CVaultRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eVaultLock@@@Z; CVaultRtlLock::CVaultRtlLock(_RTL_RESOURCE *,eVaultLock)
0x18003f9f4  nop
0x18003f9f5  xor     r15d, r15d
0x18003f9f8  mov     [rbp+3Fh+var_50], r15
0x18003f9fc  mov     [rbp+3Fh+var_48], r15d
0x18003fa00  mov     [rbp+3Fh+var_58], r15
0x18003fa04  mov     rax, cs:__imp_CredFree
0x18003fa0b  mov     [rbp+3Fh+var_70], rax
0x18003fa0f  mov     [rbp+3Fh+Credential], r15
0x18003fa13  mov     [rbp+3Fh+var_60], r15d
0x18003fa17  mov     [rbp+3Fh+var_88], rax
0x18003fa1b  mov     [rbp+3Fh+var_80], r15
0x18003fa1f  mov     [rbp+3Fh+var_78], r15d
0x18003fa23  mov     [rbp+3Fh+var_A0], rax
0x18003fa27  mov     [rbp+3Fh+var_98], r15
0x18003fa2b  mov     [rbp+3Fh+var_90], r15d
0x18003fa2f  cmp     edi, 1
0x18003fa32  jz      short loc_18003FA8F
0x18003fa34  lea     rbx, WPP_GLOBAL_Control
0x18003fa3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa42  cmp     rcx, rbx
0x18003fa45  jz      short loc_18003FA65
0x18003fa47  test    byte ptr [rcx+1Ch], 2
0x18003fa4b  jz      short loc_18003FA65
0x18003fa4d  lea     edx, [r15+28h]
0x18003fa51  mov     r9d, edi
0x18003fa54  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x18003fa5b  mov     rcx, [rcx+10h]
0x18003fa5f  call    WPP_SF_d
0x18003fa64  nop
0x18003fa65  lea     rcx, [rbp+3Fh+var_A0]
0x18003fa69  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fa6e  nop
0x18003fa6f  lea     rcx, [rbp+3Fh+var_88]
0x18003fa73  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fa78  nop
0x18003fa79  lea     rcx, [rbp+3Fh+var_70]
0x18003fa7d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fa82  nop
0x18003fa83  lea     rcx, [rbp+3Fh+var_58]
0x18003fa87  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fa8c  nop
0x18003fa8d  jmp     short loc_18003FAEA
0x18003fa8f  test    r14, r14
0x18003fa92  jnz     short loc_18003FB04
0x18003fa94  lea     rbx, WPP_GLOBAL_Control
0x18003fa9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003faa2  cmp     rcx, rbx
0x18003faa5  jz      short loc_18003FAC2
0x18003faa7  test    byte ptr [rcx+1Ch], 2
0x18003faab  jz      short loc_18003FAC2
0x18003faad  lea     edx, [r14+29h]
0x18003fab1  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x18003fab8  mov     rcx, [rcx+10h]
0x18003fabc  call    WPP_SF_
0x18003fac1  nop
0x18003fac2  lea     rcx, [rbp+3Fh+var_A0]
0x18003fac6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003facb  nop
0x18003facc  lea     rcx, [rbp+3Fh+var_88]
0x18003fad0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fad5  nop
0x18003fad6  lea     rcx, [rbp+3Fh+var_70]
0x18003fada  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fadf  nop
0x18003fae0  lea     rcx, [rbp+3Fh+var_58]
0x18003fae4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fae9  nop
0x18003faea  cmp     [rbp+3Fh+var_A8], r15b
0x18003faee  jz      short loc_18003FAFA
0x18003faf0  mov     rcx, [rbp+3Fh+Resource]; Resource
0x18003faf4  call    cs:__imp_RtlReleaseResource
0x18003fafa  mov     eax, 57h ; 'W'
0x18003faff  jmp     loc_18003FF61
0x18003fb04  lea     r9, [rbp+3Fh+Credential]; Credential
0x18003fb08  xor     r8d, r8d; Flags
0x18003fb0b  lea     edx, [r8+2]; Type
0x18003fb0f  mov     rcx, r14; TargetName
0x18003fb12  call    cs:__imp_CredReadW
0x18003fb18  lea     rsi, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x18003fb1f  mov     r12b, 4
0x18003fb22  lea     rbx, WPP_GLOBAL_Control
0x18003fb29  test    eax, eax
0x18003fb2b  jnz     loc_18003FBD1
0x18003fb31  call    cs:__imp_GetLastError
0x18003fb37  mov     edi, eax
0x18003fb39  cmp     eax, 490h
0x18003fb3e  jz      short loc_18003FBAB
0x18003fb40  cmp     eax, 57h ; 'W'
0x18003fb43  jz      short loc_18003FBAB
0x18003fb45  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb4c  cmp     rcx, rbx
0x18003fb4f  jz      short loc_18003FB6C
0x18003fb51  test    byte ptr [rcx+1Ch], 2
0x18003fb55  jz      short loc_18003FB6C
0x18003fb57  mov     edx, 2Ah ; '*'
0x18003fb5c  mov     r9d, eax
0x18003fb5f  mov     r8, rsi
0x18003fb62  mov     rcx, [rcx+10h]
0x18003fb66  call    WPP_SF_d
0x18003fb6b  nop
0x18003fb6c  lea     rcx, [rbp+3Fh+var_A0]
0x18003fb70  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fb75  nop
0x18003fb76  lea     rcx, [rbp+3Fh+var_88]
0x18003fb7a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fb7f  nop
0x18003fb80  lea     rcx, [rbp+3Fh+var_70]
0x18003fb84  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fb89  nop
0x18003fb8a  lea     rcx, [rbp+3Fh+var_58]
0x18003fb8e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fb93  nop
0x18003fb94  cmp     [rbp+3Fh+var_A8], r15b
0x18003fb98  jz      short loc_18003FBA4
0x18003fb9a  mov     rcx, [rbp+3Fh+Resource]; Resource
0x18003fb9e  call    cs:__imp_RtlReleaseResource
0x18003fba4  mov     eax, edi
0x18003fba6  jmp     loc_18003FF61
0x18003fbab  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fbb2  cmp     rcx, rbx
0x18003fbb5  jz      short loc_18003FBD1
0x18003fbb7  test    [rcx+1Ch], r12b
0x18003fbbb  jz      short loc_18003FBD1
0x18003fbbd  mov     edx, 2Bh ; '+'
0x18003fbc2  mov     r9, r14
0x18003fbc5  mov     r8, rsi
0x18003fbc8  mov     rcx, [rcx+10h]
0x18003fbcc  call    WPP_SF_S
0x18003fbd1  lea     r9, [rbp+3Fh+var_80]; Credential
0x18003fbd5  xor     r8d, r8d; Flags
0x18003fbd8  lea     edx, [r8+3]; Type
0x18003fbdc  mov     rcx, r14; TargetName
0x18003fbdf  call    cs:__imp_CredReadW
0x18003fbe5  test    eax, eax
0x18003fbe7  jnz     loc_18003FC7B
0x18003fbed  call    cs:__imp_GetLastError
0x18003fbf3  mov     edi, eax
0x18003fbf5  cmp     eax, 490h
0x18003fbfa  jz      short loc_18003FC55
0x18003fbfc  cmp     eax, 57h ; 'W'
0x18003fbff  jz      short loc_18003FC55
0x18003fc01  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fc08  cmp     rcx, rbx
0x18003fc0b  jz      short loc_18003FC28
0x18003fc0d  test    byte ptr [rcx+1Ch], 2
0x18003fc11  jz      short loc_18003FC28
0x18003fc13  mov     edx, 2Ch ; ','
0x18003fc18  mov     r9d, eax
0x18003fc1b  mov     r8, rsi
0x18003fc1e  mov     rcx, [rcx+10h]
0x18003fc22  call    WPP_SF_d
0x18003fc27  nop
0x18003fc28  lea     rcx, [rbp+3Fh+var_A0]
0x18003fc2c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fc31  nop
0x18003fc32  lea     rcx, [rbp+3Fh+var_88]
0x18003fc36  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fc3b  nop
0x18003fc3c  lea     rcx, [rbp+3Fh+var_70]
0x18003fc40  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fc45  nop
0x18003fc46  lea     rcx, [rbp+3Fh+var_58]
0x18003fc4a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fc4f  nop
0x18003fc50  jmp     loc_18003FB94
0x18003fc55  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fc5c  cmp     rcx, rbx
0x18003fc5f  jz      short loc_18003FC7B
0x18003fc61  test    [rcx+1Ch], r12b
0x18003fc65  jz      short loc_18003FC7B
0x18003fc67  mov     edx, 2Dh ; '-'
0x18003fc6c  mov     r9, r14
0x18003fc6f  mov     r8, rsi
0x18003fc72  mov     rcx, [rcx+10h]
0x18003fc76  call    WPP_SF_S
0x18003fc7b  mov     edx, 3Ah ; ':'; Ch
0x18003fc80  mov     rcx, r14; Str
0x18003fc83  call    cs:__imp_wcschr
0x18003fc89  test    rax, rax
0x18003fc8c  jz      loc_18003FD55
0x18003fc92  lea     r9, [rbp+3Fh+var_98]; Credential
0x18003fc96  xor     r8d, r8d; Flags
0x18003fc99  lea     edx, [r8+6]; Type
0x18003fc9d  mov     rcx, r14; TargetName
0x18003fca0  call    cs:__imp_CredReadW
0x18003fca6  test    eax, eax
0x18003fca8  jnz     loc_18003FD55
0x18003fcae  call    cs:__imp_GetLastError
0x18003fcb4  mov     edi, eax
0x18003fcb6  cmp     eax, 490h
0x18003fcbb  jz      short loc_18003FD2F
0x18003fcbd  cmp     eax, 57h ; 'W'
0x18003fcc0  jz      short loc_18003FD16
0x18003fcc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fcc9  cmp     rcx, rbx
0x18003fccc  jz      short loc_18003FCE9
0x18003fcce  test    byte ptr [rcx+1Ch], 2
0x18003fcd2  jz      short loc_18003FCE9
0x18003fcd4  mov     edx, 2Eh ; '.'
0x18003fcd9  mov     r9d, eax
0x18003fcdc  mov     r8, rsi
0x18003fcdf  mov     rcx, [rcx+10h]
0x18003fce3  call    WPP_SF_d
0x18003fce8  nop
0x18003fce9  lea     rcx, [rbp+3Fh+var_A0]
0x18003fced  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fcf2  nop
0x18003fcf3  lea     rcx, [rbp+3Fh+var_88]
0x18003fcf7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fcfc  nop
0x18003fcfd  lea     rcx, [rbp+3Fh+var_70]
0x18003fd01  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fd06  nop
0x18003fd07  lea     rcx, [rbp+3Fh+var_58]
0x18003fd0b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fd10  nop
0x18003fd11  jmp     loc_18003FB94
0x18003fd16  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fd1d  cmp     rcx, rbx
0x18003fd20  jz      short loc_18003FD55
0x18003fd22  test    [rcx+1Ch], r12b
0x18003fd26  jz      short loc_18003FD55
0x18003fd28  mov     edx, 2Fh ; '/'
0x18003fd2d  jmp     short loc_18003FD46
0x18003fd2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fd36  cmp     rcx, rbx
0x18003fd39  jz      short loc_18003FD55
0x18003fd3b  test    [rcx+1Ch], r12b
0x18003fd3f  jz      short loc_18003FD55
0x18003fd41  mov     edx, 30h ; '0'
0x18003fd46  mov     r9, r14
0x18003fd49  mov     r8, rsi
0x18003fd4c  mov     rcx, [rcx+10h]
0x18003fd50  call    WPP_SF_S
0x18003fd55  mov     edi, r15d
0x18003fd58  cmp     [rbp+3Fh+Credential], r15
0x18003fd5c  setnz   dil
0x18003fd60  cmp     [rbp+3Fh+var_80], r15
0x18003fd64  jz      short loc_18003FD68
0x18003fd66  inc     edi
0x18003fd68  cmp     [rbp+3Fh+var_98], r15
0x18003fd6c  jz      short loc_18003FD70
0x18003fd6e  inc     edi
0x18003fd70  test    edi, edi
0x18003fd72  jnz     short loc_18003FDB6
0x18003fd74  lea     rcx, [rbp+3Fh+var_A0]
0x18003fd78  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fd7d  nop
0x18003fd7e  lea     rcx, [rbp+3Fh+var_88]
0x18003fd82  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fd87  nop
0x18003fd88  lea     rcx, [rbp+3Fh+var_70]
0x18003fd8c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fd91  nop
0x18003fd92  lea     rcx, [rbp+3Fh+var_58]
0x18003fd96  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fd9b  nop
0x18003fd9c  cmp     [rbp+3Fh+var_A8], r15b
0x18003fda0  jz      short loc_18003FDAC
0x18003fda2  mov     rcx, [rbp+3Fh+Resource]; Resource
0x18003fda6  call    cs:__imp_RtlReleaseResource
0x18003fdac  mov     eax, 490h
0x18003fdb1  jmp     loc_18003FF61
0x18003fdb6  lea     edx, ds:0[rdi*8]; uBytes
0x18003fdbd  mov     ecx, 40h ; '@'; uFlags
0x18003fdc2  call    cs:__imp_LocalAlloc
0x18003fdc8  mov     r12, rax
0x18003fdcb  mov     [rbp+3Fh+var_50], rax
0x18003fdcf  test    rax, rax
0x18003fdd2  jnz     short loc_18003FE16
0x18003fdd4  lea     rcx, [rbp+3Fh+var_A0]
0x18003fdd8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fddd  nop
0x18003fdde  lea     rcx, [rbp+3Fh+var_88]
0x18003fde2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fde7  nop
0x18003fde8  lea     rcx, [rbp+3Fh+var_70]
0x18003fdec  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fdf1  nop
0x18003fdf2  lea     rcx, [rbp+3Fh+var_58]
0x18003fdf6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003fdfb  nop
0x18003fdfc  cmp     [rbp+3Fh+var_A8], r15b
  ... truncated ...
```
