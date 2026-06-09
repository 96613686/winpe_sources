# CClassContainer::ChangePackageUpgradeInfoIncremental(_GUID,tagUPGRADEINFO,ulong)

- ea: `0x18001f800`
- end: `0x18001fa09`
- name: `?ChangePackageUpgradeInfoIncremental@CClassContainer@@UEAAJU_GUID@@UtagUPGRADEINFO@@K@Z`
- size: `521`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, __int64 *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x18001d130`
- `0x18001ed14`
- `0x18001f800`
- `0x18002350c`
- `0x18002435c`
- `0x1800243f0`
- `0x180024458`
- `0x180024e04`
- `0x180026f3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f8ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f8ce`
- `adsldpc!ADSICloseDSObject` at `0x18001f999`
- `adsldpc!ADSICloseDSObject` at `0x18001f999`
- `adsldpc!ADSISetObjectAttributes` at `0x18001f987`
- `adsldpc!ADSISetObjectAttributes` at `0x18001f987`

## string_xrefs

- `0x18001f962`: `lastUpdateSequence`

## pseudocode

```c
__int64 __fastcall CClassContainer::ChangePackageUpgradeInfoIncremental(
        __int64 a1,
        struct _GUID *a2,
        __int64 *a3,
        int a4)
{
  struct _GUID v4; // xmm0
  const unsigned __int16 *v8; // rdx
  int v9; // ebx
  int v10; // eax
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // ebx
  unsigned __int16 *v15; // rax
  int v16; // ecx
  unsigned int v17; // r9d
  __int64 v18; // rdx
  int v19; // edi
  __int64 i; // rdi
  int v22; // [rsp+38h] [rbp-C8h]
  HLOCAL v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  void *v25; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v26; // [rsp+60h] [rbp-A0h] BYREF
  struct _ads_attr_info v27; // [rsp+70h] [rbp-90h] BYREF
  struct _ads_attr_info v28; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v29[24]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v30[264]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = *a2;
  v25 = 0;
  v23 = 0;
  v26 = v4;
  v24 = 0;
  v9 = CClassContainer::BuildDNFromPackageGuid((CClassContainer *)a1, &v26, &v23);
  if ( v9 >= 0 )
  {
    v10 = (gCsOptions & 1) != 0 ? GetADsOpenObjectFlags() | 0x21 : 101;
    v9 = DSServerOpenDSObject((struct CServerContext *)(a1 + 592), (const unsigned __int16 *)v23, v10, &v25);
    if ( v9 >= 0 )
    {
      StringFromGUID((const struct _GUID *)(a3 + 1), v30);
      v11 = *a3;
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(v11 + 2 * v12) );
      v13 = (unsigned int)(v12 + 44);
      v14 = v13;
      v15 = (unsigned __int16 *)LocalAlloc(0, 2 * v13);
      v16 = a3[5] & 0xF;
      *(_QWORD *)&v26.Data1 = v15;
      v22 = v16;
      v9 = StringCchPrintfW(v15, v14, L"%s%s%s%s%02x", v11, L"\\\\", v30, L":", v22);
      if ( v9 >= 0 )
      {
        PackStrArrToAttrEx(&v27, L"canUpgradeScript", (unsigned __int16 **)&v26, v17, a4 != 0);
        GetCurrentUsn(v29);
        *(_QWORD *)&v26.Data1 = v29;
        PackStrArrToAttr(&v28, L"lastUpdateSequence", (unsigned __int16 **)&v26, 1u);
        v19 = ADSISetObjectAttributes(v25, &v27, 2, &v24);
        if ( v25 )
          ADSICloseDSObject(v25, v18);
        v9 = 0;
        if ( v19 != -2147016691 )
          v9 = v19;
        for ( i = 0; i != 2; ++i )
          LocalFree(*((HLOCAL *)&v27.pADsValues + 4 * i));
      }
    }
  }
  if ( v23 )
    LocalFree(v23);
  return RemapErrorCode(v9, v8);
}

```

## disassembly

```asm
0x18001f800  mov     [rsp-8+arg_18], rbx
0x18001f805  push    rbp
0x18001f806  push    rdi
0x18001f807  push    r12
0x18001f809  push    r14
0x18001f80b  push    r15
0x18001f80d  lea     rbp, [rsp-200h]
0x18001f815  sub     rsp, 300h
0x18001f81c  mov     rax, cs:__security_cookie
0x18001f823  xor     rax, rsp
0x18001f826  mov     [rbp+220h+var_30], rax
0x18001f82d  movups  xmm0, xmmword ptr [rdx]
0x18001f830  xor     r12d, r12d
0x18001f833  lea     rdx, [rsp+320h+var_2C0]; struct _GUID
0x18001f838  mov     rdi, r8
0x18001f83b  mov     [rsp+320h+var_2D0], r12
0x18001f840  lea     r8, [rsp+320h+var_2E0]; unsigned __int16 **
0x18001f845  mov     [rsp+320h+var_2E0], r12
0x18001f84a  movdqu  xmmword ptr [rsp+320h+var_2C0.Data1], xmm0
0x18001f850  mov     r15d, r9d
0x18001f853  mov     [rsp+320h+var_2D8], r12d
0x18001f858  mov     r14, rcx
0x18001f85b  call    ?BuildDNFromPackageGuid@CClassContainer@@QEAAJU_GUID@@PEAPEAG@Z; CClassContainer::BuildDNFromPackageGuid(_GUID,ushort * *)
0x18001f860  mov     ebx, eax
0x18001f862  test    eax, eax
0x18001f864  js      loc_18001F9C9
0x18001f86a  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x18001f871  jz      short loc_18001F87D
0x18001f873  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18001f878  or      eax, 21h
0x18001f87b  jmp     short loc_18001F882
0x18001f87d  mov     eax, 65h ; 'e'
0x18001f882  mov     rdx, [rsp+320h+var_2E0]; unsigned __int16 *
0x18001f887  lea     rcx, [r14+250h]; struct CServerContext *
0x18001f88e  lea     r9, [rsp+320h+var_2D0]; void **
0x18001f893  mov     r8d, eax; int
0x18001f896  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18001f89b  mov     ebx, eax
0x18001f89d  test    eax, eax
0x18001f89f  js      loc_18001F9C9
0x18001f8a5  lea     rcx, [rdi+8]; struct _GUID *
0x18001f8a9  lea     rdx, [rbp+220h+var_240]; unsigned __int16 *
0x18001f8ad  call    ?StringFromGUID@@YAHAEBU_GUID@@PEAG@Z; StringFromGUID(_GUID const &,ushort *)
0x18001f8b2  mov     r14, [rdi]
0x18001f8b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f8b9  inc     rax
0x18001f8bc  cmp     [r14+rax*2], r12w
0x18001f8c1  jnz     short loc_18001F8B9
0x18001f8c3  add     eax, 2Ch ; ','
0x18001f8c6  xor     ecx, ecx; uFlags
0x18001f8c8  mov     ebx, eax
0x18001f8ca  lea     rdx, [rax+rax]; uBytes
0x18001f8ce  call    cs:__imp_LocalAlloc
0x18001f8d4  mov     ecx, [rdi+28h]
0x18001f8d7  lea     r8, aSSSS02x; "%s%s%s%s%02x"
0x18001f8de  and     ecx, 0Fh
0x18001f8e1  mov     qword ptr [rsp+320h+var_2C0.Data1], rax
0x18001f8e6  mov     [rsp+320h+var_2E8], ecx
0x18001f8ea  mov     r9, r14
0x18001f8ed  lea     rcx, asc_180030FE8; ":"
0x18001f8f4  mov     edx, ebx; unsigned __int64
0x18001f8f6  mov     [rsp+320h+var_2F0], rcx
0x18001f8fb  lea     rcx, [rbp+220h+var_240]
0x18001f8ff  mov     [rsp+320h+var_2F8], rcx
0x18001f904  lea     rcx, asc_1800302D4; "\\\\"
0x18001f90b  mov     qword ptr [rsp+320h+var_300], rcx
0x18001f910  mov     rcx, rax; unsigned __int16 *
0x18001f913  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f918  mov     ebx, eax
0x18001f91a  test    eax, eax
0x18001f91c  js      loc_18001F9C9
0x18001f922  mov     eax, r12d
0x18001f925  lea     r8, [rsp+320h+var_2C0]; unsigned __int16 **
0x18001f92a  test    r15d, r15d
0x18001f92d  lea     rdx, aCanupgradescri; "canUpgradeScript"
0x18001f934  lea     rcx, [rsp+320h+var_2B0]; struct _ads_attr_info *
0x18001f939  setnz   al
0x18001f93c  mov     [rsp+320h+var_300], eax; int
0x18001f940  call    ?PackStrArrToAttrEx@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGKH@Z; PackStrArrToAttrEx(_ads_attr_info *,ushort const *,ushort * *,ulong,int)
0x18001f945  lea     rcx, [rbp+220h+var_270]; unsigned __int16 *
0x18001f949  call    ?GetCurrentUsn@@YAXPEAG@Z; GetCurrentUsn(ushort *)
0x18001f94e  lea     rax, [rbp+220h+var_270]
0x18001f952  mov     r9d, 1; unsigned int
0x18001f958  lea     r8, [rsp+320h+var_2C0]; unsigned __int16 **
0x18001f95d  mov     qword ptr [rsp+320h+var_2C0.Data1], rax
0x18001f962  lea     rdx, aLastupdatesequ; "lastUpdateSequence"
0x18001f969  lea     rcx, [rbp+220h+var_290]; struct _ads_attr_info *
0x18001f96d  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18001f972  mov     rcx, [rsp+320h+var_2D0]
0x18001f977  lea     r9, [rsp+320h+var_2D8]
0x18001f97c  mov     r8d, 2
0x18001f982  lea     rdx, [rsp+320h+var_2B0]
0x18001f987  call    cs:__imp_ADSISetObjectAttributes
0x18001f98d  mov     rcx, [rsp+320h+var_2D0]
0x18001f992  mov     edi, eax
0x18001f994  test    rcx, rcx
0x18001f997  jz      short loc_18001F99F
0x18001f999  call    cs:__imp_ADSICloseDSObject
0x18001f99f  cmp     edi, 8007200Dh
0x18001f9a5  mov     ebx, r12d
0x18001f9a8  cmovnz  ebx, edi
0x18001f9ab  mov     rdi, r12
0x18001f9ae  mov     rcx, rdi
0x18001f9b1  shl     rcx, 5
0x18001f9b5  mov     rcx, [rbp+rcx+220h+var_2B0.pADsValues]; hMem
0x18001f9ba  call    cs:__imp_LocalFree
0x18001f9c0  inc     rdi
0x18001f9c3  cmp     rdi, 2
0x18001f9c7  jnz     short loc_18001F9AE
0x18001f9c9  cmp     [rsp+320h+var_2E0], r12
0x18001f9ce  jz      short loc_18001F9DB
0x18001f9d0  mov     rcx, [rsp+320h+var_2E0]; hMem
0x18001f9d5  call    cs:__imp_LocalFree
0x18001f9db  mov     ecx, ebx; int
0x18001f9dd  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x18001f9e2  mov     rcx, [rbp+220h+var_30]
0x18001f9e9  xor     rcx, rsp; StackCookie
0x18001f9ec  call    __security_check_cookie
0x18001f9f1  mov     rbx, [rsp+320h+arg_18]
0x18001f9f9  add     rsp, 300h
0x18001fa00  pop     r15
0x18001fa02  pop     r14
0x18001fa04  pop     r12
0x18001fa06  pop     rdi
0x18001fa07  pop     rbp
0x18001fa08  retn
```
