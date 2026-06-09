# CVaultSecurable::CreateSecurityDescriptor(CVaultSid *)

- ea: `0x180003810`
- end: `0x180003c9d`
- name: `?CreateSecurityDescriptor@CVaultSecurable@@QEAAKPEAVCVaultSid@@@Z`
- size: `1165`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *this, struct CVaultSid *)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003ca4`
- `0x1800052f8`
- `0x180006324`
- `0x180006680`
- `0x18001a640`
- `0x18004b17c`

## callees

- `0x180003140`
- `0x180003810`
- `0x1800311e0`
- `0x18003b674`
- `0x18003b7d8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000388a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800038a2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800038ba`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800038d3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000388a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800038a2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800038ba`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800038d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b62`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000397f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003aa1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000397f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003aa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000383a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c80`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003b58`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003b58`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800038f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800038f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180003bf2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180003c5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180003bf2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180003c5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CVaultSecurable::CreateSecurityDescriptor(PSECURITY_DESCRIPTOR *this, struct CVaultSid *a2)
{
  struct CVaultSid *v2; // r14
  wchar_t *v4; // rdi
  _DWORD *v5; // rsi
  void *v6; // rbx
  const WCHAR *v7; // rbx
  DWORD LastError; // eax
  DWORD v9; // ebx
  __int64 v11; // rax
  size_t v12; // rbx
  wchar_t *v13; // rax
  DWORD v14; // eax
  SIZE_T v15; // rax
  wchar_t *v16; // rdx
  LPWSTR v17; // rbx
  __int64 v18; // rax
  SIZE_T v19; // rax
  _BYTE *v20; // rcx
  HLOCAL (__stdcall *v21)(HLOCAL); // [rsp+20h] [rbp-49h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-41h] BYREF
  unsigned int v23; // [rsp+30h] [rbp-39h]
  __int64 (__fastcall *v24)(__int64); // [rsp+38h] [rbp-31h] BYREF
  _DWORD *v25; // [rsp+40h] [rbp-29h]
  int v26; // [rsp+48h] [rbp-21h]
  __int64 v27; // [rsp+50h] [rbp-19h] BYREF
  wchar_t *v28; // [rsp+58h] [rbp-11h]
  int v29; // [rsp+60h] [rbp-9h]
  __int64 (__fastcall *v30)(__int64); // [rsp+68h] [rbp-1h] BYREF
  __int64 v31; // [rsp+70h] [rbp+7h]
  int v32; // [rsp+78h] [rbp+Fh]

  v2 = a2;
  StringSid = 0;
  v23 = 0;
  v21 = LocalFree;
  v4 = 0;
  v28 = 0;
  v29 = 0;
  v27 = 0;
  v5 = 0;
  v25 = 0;
  v26 = 0;
  v24 = AutoDereference<IVaultKeyManager>;
  if ( !a2 )
  {
    v7 = L"O:WDG:WDD:(A;;GA;;;WD)S:(ML;;NWNRNX;;;ME)";
LABEL_29:
    v31 = 0;
    v32 = 0;
    v30 = AutoDereference<IVaultKeyManager>;
    v5 = LocalAlloc(0x40u, 0x18u);
    if ( !v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, 14);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
      return 14;
    }
    *(_QWORD *)v5 = &CVaultSid::`vftable';
    v5[2] = 1;
    *((_QWORD *)v5 + 2) = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
    v31 = 0;
    v25 = v5;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
    v2 = (struct CVaultSid *)v5;
    goto LABEL_35;
  }
  v6 = (void *)*((_QWORD *)a2 + 2);
  if ( v6 && !EqualSid(v6, pSid2) && !EqualSid(v6, qword_18005F730) && !EqualSid(v6, qword_18005F728) )
  {
    if ( EqualSid(pSid1, *((PSID *)v2 + 2)) )
    {
      v7 = L"O:WDG:WDD:(A;;GA;;;WD)S:(ML;;NWNRNX;;;LW)";
    }
    else
    {
      if ( !ConvertSidToStringSidW(*((PSID *)v2 + 2), &StringSid) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, LastError);
        goto LABEL_12;
      }
      v11 = -1;
      do
        ++v11;
      while ( StringSid[v11] );
      v12 = (unsigned int)(v11 + 52);
      v13 = (wchar_t *)LocalAlloc(0x40u, 2 * v12);
      v4 = v13;
      v28 = v13;
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, 14);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
        return 14;
      }
      if ( swprintf_s(v13, v12, L"O:WDG:WDD:(A;;GA;;;WD)(A;;WD;;;%s)S:(ML;;NWNRNX;;;LW)", StringSid) != (_DWORD)v12 - 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, 87);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
        return 87;
      }
      v7 = v4;
    }
    goto LABEL_35;
  }
  v7 = L"O:WDG:WDD:(A;;GA;;;WD)S:(ML;;NWNRNX;;;ME)";
  if ( *((_QWORD *)v2 + 2) )
    goto LABEL_29;
LABEL_35:
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, this + 5, 0) )
  {
    v14 = GetLastError();
    v9 = v14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, v14);
LABEL_12:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
    return v9;
  }
  (**(void (__fastcall ***)(struct CVaultSid *))v2)(v2);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(this + 7);
  this[8] = v2;
  if ( v5 )
    AutoDereference<IVaultKeyManager>((__int64)v5);
  if ( v4 )
  {
    v15 = LocalSize(v4);
    if ( v15 )
    {
      v16 = v4;
      do
      {
        *(_BYTE *)v16 = 0;
        v16 = (wchar_t *)((char *)v16 + 1);
        --v15;
      }
      while ( v15 );
    }
    LocalFree(v4);
  }
  v17 = StringSid;
  if ( StringSid )
  {
    v18 = v23;
    if ( v23 )
    {
      do
      {
        *(_BYTE *)v17 = 0;
        v17 = (LPWSTR)((char *)v17 + 1);
        --v18;
      }
      while ( v18 );
      v17 = StringSid;
    }
    if ( v21 )
    {
      ((void (__fastcall *)(LPWSTR))v21)(v17);
    }
    else if ( v17 )
    {
      v19 = LocalSize(v17);
      if ( v19 )
      {
        v20 = v17;
        do
        {
          *v20++ = 0;
          --v19;
        }
        while ( v19 );
      }
      LocalFree(v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003810  push    rbp
0x180003812  push    rbx
0x180003813  push    rsi
0x180003814  push    rdi
0x180003815  push    r12
0x180003817  push    r13
0x180003819  push    r14
0x18000381b  push    r15
0x18000381d  lea     rbp, [rsp-1Fh]
0x180003822  sub     rsp, 88h
0x180003829  mov     r14, rdx
0x18000382c  mov     r13, rcx
0x18000382f  xor     r15d, r15d
0x180003832  mov     [rbp+57h+StringSid], r15
0x180003836  mov     [rbp+57h+var_90], r15d
0x18000383a  mov     rax, cs:__imp_LocalFree
0x180003841  mov     [rbp+57h+var_A0], rax
0x180003845  mov     edi, r15d
0x180003848  mov     [rbp+57h+var_68], r15
0x18000384c  mov     [rbp+57h+var_60], r15d
0x180003850  mov     [rbp+57h+var_70], r15
0x180003854  mov     esi, r15d
0x180003857  mov     [rbp+57h+var_80], r15
0x18000385b  mov     [rbp+57h+var_78], r15d
0x18000385f  lea     r12, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180003866  mov     [rbp+57h+var_88], r12
0x18000386a  test    rdx, rdx
0x18000386d  jz      loc_180003A84
0x180003873  mov     rbx, [rdx+10h]
0x180003877  test    rbx, rbx
0x18000387a  jz      loc_180003A70
0x180003880  mov     rdx, cs:pSid2; pSid2
0x180003887  mov     rcx, rbx; pSid1
0x18000388a  call    cs:__imp_EqualSid
0x180003890  test    eax, eax
0x180003892  jnz     loc_180003A70
0x180003898  mov     rdx, cs:qword_18005F730; pSid2
0x18000389f  mov     rcx, rbx; pSid1
0x1800038a2  call    cs:__imp_EqualSid
0x1800038a8  test    eax, eax
0x1800038aa  jnz     loc_180003A70
0x1800038b0  mov     rdx, cs:qword_18005F728; pSid2
0x1800038b7  mov     rcx, rbx; pSid1
0x1800038ba  call    cs:__imp_EqualSid
0x1800038c0  test    eax, eax
0x1800038c2  jnz     loc_180003A70
0x1800038c8  mov     rdx, [r14+10h]; pSid2
0x1800038cc  mov     rcx, cs:pSid1; pSid1
0x1800038d3  call    cs:__imp_EqualSid
0x1800038d9  test    eax, eax
0x1800038db  jz      short loc_1800038E9
0x1800038dd  lea     rbx, aOWdgWddAGaWdSM; "O:WDG:WDD:(A;;GA;;;WD)S:(ML;;NWNRNX;;;L"...
0x1800038e4  jmp     loc_180003B49
0x1800038e9  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800038ed  mov     rcx, [r14+10h]; Sid
0x1800038f1  call    cs:__imp_ConvertSidToStringSidW
0x1800038f7  test    eax, eax
0x1800038f9  jnz     short loc_18000395A
0x1800038fb  call    cs:__imp_GetLastError
0x180003901  mov     ebx, eax
0x180003903  lea     rdx, WPP_GLOBAL_Control
0x18000390a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003911  cmp     rcx, rdx
0x180003914  jz      short loc_180003935
0x180003916  test    byte ptr [rcx+1Ch], 2
0x18000391a  jz      short loc_180003935
0x18000391c  mov     edx, 0Ah
0x180003921  mov     r9d, eax
0x180003924  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18000392b  mov     rcx, [rcx+10h]
0x18000392f  call    WPP_SF_d
0x180003934  nop
0x180003935  lea     rcx, [rbp+57h+var_88]
0x180003939  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000393e  nop
0x18000393f  lea     rcx, [rbp+57h+var_70]
0x180003943  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003948  nop
0x180003949  lea     rcx, [rbp+57h+var_A0]
0x18000394d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003952  nop
0x180003953  mov     eax, ebx
0x180003955  jmp     loc_180003C89
0x18000395a  mov     rcx, [rbp+57h+StringSid]
0x18000395e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003965  lea     rax, [rax+1]
0x180003969  cmp     word ptr [rcx+rax*2], 0
0x18000396e  jnz     short loc_180003965
0x180003970  lea     ebx, [rax+34h]
0x180003973  mov     r15d, ebx
0x180003976  lea     rdx, [rbx+rbx]; uBytes
0x18000397a  mov     ecx, 40h ; '@'; uFlags
0x18000397f  call    cs:__imp_LocalAlloc
0x180003985  mov     rdi, rax
0x180003988  mov     [rbp+57h+var_68], rax
0x18000398c  test    rax, rax
0x18000398f  jnz     short loc_1800039EE
0x180003991  lea     rdx, WPP_GLOBAL_Control
0x180003998  mov     rcx, cs:WPP_GLOBAL_Control
0x18000399f  cmp     rcx, rdx
0x1800039a2  jz      short loc_1800039C6
0x1800039a4  test    byte ptr [rcx+1Ch], 2
0x1800039a8  jz      short loc_1800039C6
0x1800039aa  mov     edx, 0Bh
0x1800039af  mov     r9d, 0Eh
0x1800039b5  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x1800039bc  mov     rcx, [rcx+10h]
0x1800039c0  call    WPP_SF_d
0x1800039c5  nop
0x1800039c6  lea     rcx, [rbp+57h+var_88]
0x1800039ca  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800039cf  nop
0x1800039d0  lea     rcx, [rbp+57h+var_70]
0x1800039d4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800039d9  nop
0x1800039da  lea     rcx, [rbp+57h+var_A0]
0x1800039de  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800039e3  nop
0x1800039e4  mov     eax, 0Eh
0x1800039e9  jmp     loc_180003C89
0x1800039ee  mov     r9, [rbp+57h+StringSid]
0x1800039f2  lea     r8, aOWdgWddAGaWdAW; "O:WDG:WDD:(A;;GA;;;WD)(A;;WD;;;%s)S:(ML"...
0x1800039f9  mov     rdx, r15; BufferCount
0x1800039fc  mov     rcx, rdi; Buffer
0x1800039ff  call    swprintf_s
0x180003a04  lea     ecx, [rbx-1]
0x180003a07  cmp     eax, ecx
0x180003a09  jz      short loc_180003A68
0x180003a0b  lea     rdx, WPP_GLOBAL_Control
0x180003a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a19  cmp     rcx, rdx
0x180003a1c  jz      short loc_180003A40
0x180003a1e  test    byte ptr [rcx+1Ch], 2
0x180003a22  jz      short loc_180003A40
0x180003a24  mov     edx, 0Ch
0x180003a29  mov     r9d, 57h ; 'W'
0x180003a2f  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180003a36  mov     rcx, [rcx+10h]
0x180003a3a  call    WPP_SF_d
0x180003a3f  nop
0x180003a40  lea     rcx, [rbp+57h+var_88]
0x180003a44  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003a49  nop
0x180003a4a  lea     rcx, [rbp+57h+var_70]
0x180003a4e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003a53  nop
0x180003a54  lea     rcx, [rbp+57h+var_A0]
0x180003a58  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003a5d  nop
0x180003a5e  mov     eax, 57h ; 'W'
0x180003a63  jmp     loc_180003C89
0x180003a68  mov     rbx, rdi
0x180003a6b  jmp     loc_180003B49
0x180003a70  lea     rbx, aOWdgWddAGaWdSM_0; "O:WDG:WDD:(A;;GA;;;WD)S:(ML;;NWNRNX;;;M"...
0x180003a77  cmp     qword ptr [r14+10h], 0
0x180003a7c  jz      loc_180003B49
0x180003a82  jmp     short loc_180003A8B
0x180003a84  lea     rbx, aOWdgWddAGaWdSM_0; "O:WDG:WDD:(A;;GA;;;WD)S:(ML;;NWNRNX;;;M"...
0x180003a8b  mov     [rbp+57h+var_50], r15
0x180003a8f  mov     [rbp+57h+var_48], r15d
0x180003a93  mov     [rbp+57h+var_58], r12
0x180003a97  mov     edx, 18h; uBytes
0x180003a9c  mov     ecx, 40h ; '@'; uFlags
0x180003aa1  call    cs:__imp_LocalAlloc
0x180003aa7  mov     rsi, rax
0x180003aaa  test    rax, rax
0x180003aad  jnz     short loc_180003B16
0x180003aaf  lea     rdx, WPP_GLOBAL_Control
0x180003ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180003abd  cmp     rcx, rdx
0x180003ac0  jz      short loc_180003AE4
0x180003ac2  test    byte ptr [rcx+1Ch], 2
0x180003ac6  jz      short loc_180003AE4
0x180003ac8  mov     edx, 2Ah ; '*'
0x180003acd  mov     r9d, 0Eh
0x180003ad3  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180003ada  mov     rcx, [rcx+10h]
0x180003ade  call    WPP_SF_d
0x180003ae3  nop
0x180003ae4  lea     rcx, [rbp+57h+var_58]
0x180003ae8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003aed  nop
0x180003aee  lea     rcx, [rbp+57h+var_88]
0x180003af2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003af7  nop
0x180003af8  lea     rcx, [rbp+57h+var_70]
0x180003afc  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003b01  nop
0x180003b02  lea     rcx, [rbp+57h+var_A0]
0x180003b06  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003b0b  nop
0x180003b0c  mov     eax, 0Eh
0x180003b11  jmp     loc_180003C89
0x180003b16  lea     rax, ??_7CVaultSid@@6B@; const CVaultSid::`vftable'
0x180003b1d  mov     [rsi], rax
0x180003b20  mov     dword ptr [rsi+8], 1
0x180003b27  mov     [rsi+10h], r15
0x180003b2b  lea     rcx, [rbp+57h+var_58]
0x180003b2f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003b34  mov     [rbp+57h+var_50], r15
0x180003b38  mov     [rbp+57h+var_80], rsi
0x180003b3c  lea     rcx, [rbp+57h+var_58]
0x180003b40  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003b45  nop
0x180003b46  mov     r14, rsi
0x180003b49  lea     r8, [r13+28h]; SecurityDescriptor
0x180003b4d  xor     r9d, r9d; SecurityDescriptorSize
0x180003b50  mov     edx, 1; StringSDRevision
0x180003b55  mov     rcx, rbx; StringSecurityDescriptor
0x180003b58  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180003b5e  test    eax, eax
0x180003b60  jnz     short loc_180003BC1
0x180003b62  call    cs:__imp_GetLastError
0x180003b68  mov     ebx, eax
0x180003b6a  lea     rdx, WPP_GLOBAL_Control
0x180003b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b78  cmp     rcx, rdx
0x180003b7b  jz      short loc_180003B9C
0x180003b7d  test    byte ptr [rcx+1Ch], 2
0x180003b81  jz      short loc_180003B9C
0x180003b83  mov     edx, 0Dh
0x180003b88  mov     r9d, eax
0x180003b8b  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180003b92  mov     rcx, [rcx+10h]
0x180003b96  call    WPP_SF_d
0x180003b9b  nop
0x180003b9c  lea     rcx, [rbp+57h+var_88]
0x180003ba0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003ba5  nop
0x180003ba6  lea     rcx, [rbp+57h+var_70]
0x180003baa  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003baf  nop
0x180003bb0  lea     rcx, [rbp+57h+var_A0]
0x180003bb4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003bb9  nop
0x180003bba  mov     eax, ebx
0x180003bbc  jmp     loc_180003C89
0x180003bc1  mov     rax, [r14]
0x180003bc4  mov     rcx, r14
0x180003bc7  mov     rax, [rax]
0x180003bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bcf  lea     rcx, [r13+38h]
0x180003bd3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003bd8  mov     [r13+40h], r14
0x180003bdc  test    rsi, rsi
0x180003bdf  jz      short loc_180003BEA
0x180003be1  mov     rcx, rsi
0x180003be4  call    ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180003be9  nop
0x180003bea  test    rdi, rdi
0x180003bed  jz      short loc_180003C17
0x180003bef  mov     rcx, rdi; hMem
0x180003bf2  call    cs:__imp_LocalSize
0x180003bf8  test    rax, rax
0x180003bfb  jz      short loc_180003C0D
0x180003bfd  mov     rdx, rdi
0x180003c00  mov     byte ptr [rdx], 0
0x180003c03  lea     rdx, [rdx+1]
0x180003c07  sub     rax, 1
0x180003c0b  jnz     short loc_180003C00
0x180003c0d  mov     rcx, rdi; hMem
0x180003c10  call    cs:__imp_LocalFree
0x180003c16  nop
0x180003c17  mov     rbx, [rbp+57h+StringSid]
0x180003c1b  test    rbx, rbx
0x180003c1e  jz      short loc_180003C87
0x180003c20  mov     eax, [rbp+57h+var_90]
0x180003c23  test    eax, eax
0x180003c25  jz      short loc_180003C42
0x180003c27  test    rbx, rbx
0x180003c2a  jz      short loc_180003C42
0x180003c2c  test    rax, rax
0x180003c2f  jz      short loc_180003C42
0x180003c31  mov     byte ptr [rbx], 0
0x180003c34  lea     rbx, [rbx+1]
0x180003c38  sub     rax, 1
0x180003c3c  jnz     short loc_180003C31
0x180003c3e  mov     rbx, [rbp+57h+StringSid]
0x180003c42  mov     rax, [rbp+57h+var_A0]
0x180003c46  test    rax, rax
0x180003c49  jz      short loc_180003C55
0x180003c4b  mov     rcx, rbx
0x180003c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c53  jmp     short loc_180003C87
0x180003c55  test    rbx, rbx
0x180003c58  jz      short loc_180003C87
0x180003c5a  mov     rcx, rbx; hMem
0x180003c5d  call    cs:__imp_LocalSize
0x180003c63  test    rax, rax
0x180003c66  jz      short loc_180003C7D
0x180003c68  mov     rcx, rbx
0x180003c6b  nop     dword ptr [rax+rax+00h]
0x180003c70  mov     byte ptr [rcx], 0
0x180003c73  lea     rcx, [rcx+1]
0x180003c77  sub     rax, 1
0x180003c7b  jnz     short loc_180003C70
0x180003c7d  mov     rcx, rbx; hMem
0x180003c80  call    cs:__imp_LocalFree
0x180003c86  nop
0x180003c87  xor     eax, eax
  ... truncated ...
```
