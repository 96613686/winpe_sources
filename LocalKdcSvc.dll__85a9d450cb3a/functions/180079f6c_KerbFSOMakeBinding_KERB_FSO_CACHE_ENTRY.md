# KerbFSOMakeBinding(_KERB_FSO_CACHE_ENTRY *)

- ea: `0x180079f6c`
- end: `0x18007a5c6`
- name: `?KerbFSOMakeBinding@@YAPEAU_KERB_FSO_BINDING_HANDLE@@PEAU_KERB_FSO_CACHE_ENTRY@@@Z`
- size: `1626`
- prototype: `struct _KERB_FSO_BINDING_HANDLE *__fastcall(struct _KERB_FSO_CACHE_ENTRY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007a92c`

## callees

- `0x1800038f0`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001ff94`
- `0x18002005c`
- `0x180030ee0`
- `0x180079f6c`
- `0x18007ad44`
- `0x18007b754`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180079f9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007a3e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180079f9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007a3e2`
- `logoncli!DsGetDcNameW` at `0x18007a1a4`
- `logoncli!DsGetDcNameW` at `0x18007a1d9`
- `logoncli!DsGetDcNameW` at `0x18007a1a4`
- `logoncli!DsGetDcNameW` at `0x18007a1d9`
- `ntdll!RtlAcquireResourceShared` at `0x180079fc2`
- `ntdll!RtlAcquireResourceShared` at `0x180079fc2`
- `ntdll!RtlReleaseResource` at `0x18007a58e`
- `ntdll!RtlReleaseResource` at `0x18007a58e`
- `ntdll!RtlConvertSharedToExclusive` at `0x18007a105`
- `ntdll!RtlConvertSharedToExclusive` at `0x18007a105`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18007a418`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18007a418`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x18007a59d`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x18007a59d`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18007a325`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18007a325`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18007a08b`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18007a08b`
- `netutils!NetApiBufferFree` at `0x18007a5ac`
- `netutils!NetApiBufferFree` at `0x18007a5ac`

## pseudocode

```c
struct _KERB_FSO_BINDING_HANDLE *__fastcall KerbFSOMakeBinding(struct _KERB_FSO_CACHE_ENTRY *a1)
{
  union _LARGE_INTEGER v3; // rbx
  __int64 v4; // rsi
  int v5; // r14d
  int v6; // edx
  void *v7; // rcx
  int v8; // edx
  DWORD v9; // eax
  DWORD v10; // ebx
  CSecurityData *v11; // rcx
  DWORD DcNameW; // eax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int16 v16; // ax
  void *v17; // rax
  __int64 v18; // rcx
  __int16 v19; // bx
  void *v20; // rax
  DWORD v21; // eax
  HANDLE v22; // rbx
  __int64 v23; // rax
  int v24; // ecx
  CSecurityData *v25; // rcx
  __int64 v26; // rdx
  int v27; // ecx
  const char *v28; // r9
  LPCWSTR rpNames; // [rsp+40h] [rbp-18h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+A0h] [rbp+48h] BYREF
  HANDLE phDS; // [rsp+A8h] [rbp+50h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+58h] BYREF
  PDS_NAME_RESULTW pResult; // [rsp+B8h] [rbp+60h] BYREF

  pResult = 0;
  DomainControllerInfo = 0;
  phDS = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( !a1 )
    return 0;
  v3 = KerbFsoBindingCacheTimeout;
  v4 = 0;
  v5 = 0;
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)a1 + 24), 1u);
  v6 = *((_DWORD *)a1 + 44);
  if ( (v6 & 0x8001) != 0x8000 || v3.QuadPart + *((_QWORD *)a1 + 15) < *(_QWORD *)&SystemTimeAsFileTime )
    goto LABEL_18;
  if ( (v6 & 0x4000) == 0 )
  {
    v4 = *((_QWORD *)a1 + 23);
    if ( v4 )
    {
      v5 = 1;
      _InterlockedAdd((volatile signed __int32 *)(v4 + 8), 1u);
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_0117c3251e483c44e322262836b1158e_Traceguids,
          (char *)a1 + 128);
      v7 = *(void **)v4;
      v8 = *((_DWORD *)a1 + 44) & 0x2000;
      rpNames = L" ";
      v9 = DsCrackNamesW(
             v7,
             (DS_NAME_FLAGS)((v8 | 0x1000u) >> 11),
             (DS_NAME_FORMAT)-15,
             (DS_NAME_FORMAT)-15,
             1u,
             &rpNames,
             &pResult);
      v10 = v9;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_0117c3251e483c44e322262836b1158e_Traceguids, v9);
      if ( !v10 )
        goto LABEL_78;
      KerbDereferenceFsoBindingHandle((struct _KERB_FSO_BINDING_HANDLE *)v4);
      v4 = 0;
    }
    else if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_0117c3251e483c44e322262836b1158e_Traceguids);
    }
LABEL_18:
    _interlockedbittestandset((volatile signed __int32 *)a1 + 44, 0);
    RtlConvertSharedToExclusive((PRTL_RESOURCE)((char *)a1 + 24));
    if ( (*((_BYTE *)a1 + 176) & 1) == 0 )
    {
      v4 = *((_QWORD *)a1 + 23);
      if ( v4 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
        goto LABEL_78;
      }
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_78;
      v26 = 28;
      goto LABEL_77;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_0117c3251e483c44e322262836b1158e_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    if ( *((_QWORD *)a1 + 23) )
    {
      if ( v11 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)v11 + 2), 20, &WPP_0117c3251e483c44e322262836b1158e_Traceguids);
      KerbDereferenceFsoBindingHandle(*((struct _KERB_FSO_BINDING_HANDLE **)a1 + 23));
      *((_QWORD *)a1 + 23) = 0;
    }
    DcNameW = DsGetDcNameW(0, *((LPCWSTR *)a1 + 17), 0, 0, v5 | 0x50, &DomainControllerInfo);
    if ( DcNameW )
    {
      DcNameW = DsGetDcNameW(0, *((LPCWSTR *)a1 + 17), 0, 0, v5 | 0x10, &DomainControllerInfo);
      *((_DWORD *)a1 + 44) &= ~0x2000u;
      if ( DcNameW )
        goto LABEL_62;
    }
    else
    {
      *((_DWORD *)a1 + 44) |= 0x2000u;
    }
    if ( DomainControllerInfo )
    {
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( DomainControllerInfo->DomainName[v14] );
      v15 = *((_QWORD *)a1 + 19);
      v16 = 2 * v14;
      *((_WORD *)a1 + 72) = v16;
      *((_WORD *)a1 + 73) = v16 + 2;
      if ( v15 )
        (*((void (**)(void))FsoFunctions + 1))();
      v17 = (void *)(*(__int64 (__fastcall **)(_QWORD))FsoFunctions)(*((unsigned __int16 *)a1 + 73));
      *((_QWORD *)a1 + 19) = v17;
      if ( v17 )
      {
        memcpy_0(v17, DomainControllerInfo->DomainName, *((unsigned __int16 *)a1 + 73));
        do
          ++v13;
        while ( DomainControllerInfo->DomainControllerName[v13] );
        v18 = *((_QWORD *)a1 + 21);
        v19 = 2 * v13;
        *((_WORD *)a1 + 80) = v19;
        *((_WORD *)a1 + 81) = v19 + 2;
        if ( v18 )
          (*((void (**)(void))FsoFunctions + 1))();
        v20 = (void *)(*(__int64 (__fastcall **)(_QWORD))FsoFunctions)(*((unsigned __int16 *)a1 + 81));
        *((_QWORD *)a1 + 21) = v20;
        if ( v20 )
        {
          memcpy_0(v20, DomainControllerInfo->DomainControllerName, *((unsigned __int16 *)a1 + 81));
          v21 = DsBindWithSpnExW(*((LPCWSTR *)a1 + 21), *((LPCWSTR *)a1 + 19), 0, 0, 0, &phDS);
          v22 = phDS;
          if ( phDS && !v21 )
          {
            v23 = (*(__int64 (__fastcall **)(__int64))FsoFunctions)(16);
            v4 = v23;
            if ( v23 )
            {
              *(_QWORD *)v23 = v22;
              *(_DWORD *)(v23 + 8) = 1;
              _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
              *((_DWORD *)a1 + 44) &= ~0x4000u;
              if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_sZZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1 + 128, (__int64)a1 + 160);
              }
LABEL_48:
              *((_DWORD *)a1 + 44) &= ~1u;
              *((_DWORD *)a1 + 44) |= 0x8000u;
              *((_QWORD *)a1 + 23) = v4;
              GetSystemTimeAsFileTime((LPFILETIME)a1 + 15);
              goto LABEL_78;
            }
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_0117c3251e483c44e322262836b1158e_Traceguids);
            }
            DsUnBindW(&phDS);
            v24 = *((_DWORD *)a1 + 44);
LABEL_66:
            v27 = v24 | 0x4000;
            *((_DWORD *)a1 + 44) = v27;
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v28 = "forest";
              if ( (v27 & 0x2000) == 0 )
                v28 = "domain";
              WPP_SF_sZ(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                (unsigned int)&WPP_0117c3251e483c44e322262836b1158e_Traceguids,
                (_DWORD)v28,
                (__int64)a1 + 128);
            }
            (*((void (__fastcall **)(char *))FsoFunctions + 2))((char *)a1 + 128);
            goto LABEL_48;
          }
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_Zd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              (unsigned int)&WPP_0117c3251e483c44e322262836b1158e_Traceguids,
              (_DWORD)a1 + 160,
              v21);
          }
LABEL_65:
          v24 = *((_DWORD *)a1 + 44);
          goto LABEL_66;
        }
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_78;
        }
        v26 = 23;
      }
      else
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_78;
        }
        v26 = 22;
      }
LABEL_77:
      WPP_SF_(*((_QWORD *)v25 + 2), v26, &WPP_0117c3251e483c44e322262836b1158e_Traceguids);
      goto LABEL_78;
    }
LABEL_62:
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_0117c3251e483c44e322262836b1158e_Traceguids, DcNameW);
    goto LABEL_65;
  }
LABEL_78:
  RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 24));
  if ( pResult )
    DsFreeNameResultW(pResult);
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  return (struct _KERB_FSO_BINDING_HANDLE *)v4;
}

```

## disassembly

```asm
0x180079f6c  push    rbp
0x180079f6e  push    rbx
0x180079f6f  push    rsi
0x180079f70  push    rdi
0x180079f71  push    r12
0x180079f73  push    r13
0x180079f75  push    r14
0x180079f77  push    r15
0x180079f79  mov     rbp, rsp
0x180079f7c  sub     rsp, 58h
0x180079f80  xor     r12d, r12d
0x180079f83  mov     rdi, rcx
0x180079f86  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180079f8a  mov     [rbp+pResult], r12
0x180079f8e  mov     [rbp+DomainControllerInfo], r12
0x180079f92  mov     [rbp+phDS], r12
0x180079f96  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r12
0x180079f9a  call    cs:__imp_GetSystemTimeAsFileTime
0x180079fa0  test    rdi, rdi
0x180079fa3  jnz     short loc_180079FAC
0x180079fa5  xor     eax, eax
0x180079fa7  jmp     loc_18007A5B5
0x180079fac  mov     rbx, cs:?KerbFsoBindingCacheTimeout@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbFsoBindingCacheTimeout
0x180079fb3  lea     r15, [rdi+18h]
0x180079fb7  mov     rcx, r15; Resource
0x180079fba  mov     dl, 1; Wait
0x180079fbc  mov     rsi, r12
0x180079fbf  mov     r14d, r12d
0x180079fc2  call    cs:__imp_RtlAcquireResourceShared
0x180079fc8  mov     edx, [rdi+0B0h]
0x180079fce  lea     r13, WPP_GLOBAL_Control
0x180079fd5  mov     eax, edx
0x180079fd7  and     eax, 8001h
0x180079fdc  cmp     eax, 8000h
0x180079fe1  jnz     loc_18007A0F9
0x180079fe7  mov     rcx, [rdi+78h]
0x180079feb  add     rcx, rbx
0x180079fee  cmp     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180079ff2  jl      loc_18007A0F9
0x180079ff8  bt      edx, 0Eh
0x180079ffc  jb      loc_18007A58B
0x18007a002  mov     rsi, [rdi+0B8h]
0x18007a009  test    rsi, rsi
0x18007a00c  jz      loc_18007A0D2
0x18007a012  mov     r14d, 1
0x18007a018  lock add [rsi+8], r14d
0x18007a01d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a024  cmp     rcx, r13
0x18007a027  jz      short loc_18007A04A
0x18007a029  test    byte ptr [rcx+1Ch], 8
0x18007a02d  jz      short loc_18007A04A
0x18007a02f  mov     rcx, [rcx+10h]
0x18007a033  lea     r9, [rdi+80h]
0x18007a03a  lea     edx, [r14+0Fh]
0x18007a03e  lea     r8, WPP_0117c3251e483c44e322262836b1158e_Traceguids
0x18007a045  call    WPP_SF_Z
0x18007a04a  mov     edx, [rdi+0B0h]
0x18007a050  lea     rax, asc_1800A4740; " "
0x18007a057  mov     rcx, [rsi]; hDS
0x18007a05a  and     edx, 2000h
0x18007a060  mov     [rbp+var_18], rax
0x18007a064  bts     edx, 0Ch
0x18007a068  lea     rax, [rbp+pResult]
0x18007a06c  shr     edx, 0Bh; flags
0x18007a06f  mov     [rsp+58h+ppResult], rax; ppResult
0x18007a074  mov     r8d, 0FFFFFFF1h; formatOffered
0x18007a07a  lea     rax, [rbp+var_18]
0x18007a07e  mov     r9d, r8d; formatDesired
0x18007a081  mov     [rsp+58h+rpNames], rax; rpNames
0x18007a086  mov     [rsp+58h+cNames], r14d; cNames
0x18007a08b  call    cs:__imp_DsCrackNamesW
0x18007a091  mov     ebx, eax
0x18007a093  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a09a  cmp     rcx, r13
0x18007a09d  jz      short loc_18007A0BD
0x18007a09f  test    byte ptr [rcx+1Ch], 8
0x18007a0a3  jz      short loc_18007A0BD
0x18007a0a5  mov     rcx, [rcx+10h]
0x18007a0a9  lea     r8, WPP_0117c3251e483c44e322262836b1158e_Traceguids
0x18007a0b0  mov     edx, 11h
0x18007a0b5  mov     r9d, eax
0x18007a0b8  call    WPP_SF_d
0x18007a0bd  test    ebx, ebx
0x18007a0bf  jz      loc_18007A58B
0x18007a0c5  mov     rcx, rsi; struct _KERB_FSO_BINDING_HANDLE *
0x18007a0c8  call    ?KerbDereferenceFsoBindingHandle@@YAXPEAU_KERB_FSO_BINDING_HANDLE@@@Z; KerbDereferenceFsoBindingHandle(_KERB_FSO_BINDING_HANDLE *)
0x18007a0cd  mov     rsi, r12
0x18007a0d0  jmp     short loc_18007A0F9
0x18007a0d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a0d9  cmp     rcx, r13
0x18007a0dc  jz      short loc_18007A0F9
0x18007a0de  test    byte ptr [rcx+1Ch], 8
0x18007a0e2  jz      short loc_18007A0F9
0x18007a0e4  mov     rcx, [rcx+10h]
0x18007a0e8  lea     r8, WPP_0117c3251e483c44e322262836b1158e_Traceguids
0x18007a0ef  mov     edx, 12h
0x18007a0f4  call    WPP_SF_
0x18007a0f9  lock bts dword ptr [rdi+0B0h], 0
0x18007a102  mov     rcx, r15; Resource
0x18007a105  call    cs:__imp_RtlConvertSharedToExclusive
0x18007a10b  test    byte ptr [rdi+0B0h], 1
0x18007a112  jz      loc_18007A552
0x18007a118  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a11f  cmp     rcx, r13
0x18007a122  jz      short loc_18007A146
0x18007a124  test    byte ptr [rcx+1Ch], 8
0x18007a128  jz      short loc_18007A146
0x18007a12a  mov     rcx, [rcx+10h]
0x18007a12e  lea     r8, WPP_0117c3251e483c44e322262836b1158e_Traceguids
0x18007a135  mov     edx, 13h
0x18007a13a  call    WPP_SF_
0x18007a13f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a146  cmp     [rdi+0B8h], r12
0x18007a14d  jz      short loc_18007A182
0x18007a14f  cmp     rcx, r13
0x18007a152  jz      short loc_18007A16F
0x18007a154  test    byte ptr [rcx+1Ch], 8
0x18007a158  jz      short loc_18007A16F
0x18007a15a  mov     rcx, [rcx+10h]
0x18007a15e  lea     r8, WPP_0117c3251e483c44e322262836b1158e_Traceguids
0x18007a165  mov     edx, 14h
0x18007a16a  call    WPP_SF_
0x18007a16f  mov     rcx, [rdi+0B8h]; struct _KERB_FSO_BINDING_HANDLE *
0x18007a176  call    ?KerbDereferenceFsoBindingHandle@@YAXPEAU_KERB_FSO_BINDING_HANDLE@@@Z; KerbDereferenceFsoBindingHandle(_KERB_FSO_BINDING_HANDLE *)
0x18007a17b  mov     [rdi+0B8h], r12
0x18007a182  mov     rdx, [rdi+88h]; DomainName
0x18007a189  lea     rcx, [rbp+DomainControllerInfo]
0x18007a18d  mov     [rsp+58h+rpNames], rcx; DomainControllerInfo
0x18007a192  mov     eax, r14d
0x18007a195  or      eax, 50h
0x18007a198  xor     ecx, ecx; ComputerName
0x18007a19a  xor     r9d, r9d; SiteName
0x18007a19d  mov     [rsp+58h+cNames], eax; Flags
0x18007a1a1  xor     r8d, r8d; DomainGuid
0x18007a1a4  call    cs:__imp_DsGetDcNameW
0x18007a1aa  test    eax, eax
0x18007a1ac  jnz     short loc_18007A1B8
0x18007a1ae  bts     dword ptr [rdi+0B0h], 0Dh
0x18007a1b6  jmp     short loc_18007A1EF
0x18007a1b8  mov     rdx, [rdi+88h]; DomainName
0x18007a1bf  lea     rax, [rbp+DomainControllerInfo]
0x18007a1c3  mov     [rsp+58h+rpNames], rax; DomainControllerInfo
0x18007a1c8  or      r14d, 10h
0x18007a1cc  xor     r9d, r9d; SiteName
0x18007a1cf  mov     [rsp+58h+cNames], r14d; Flags
0x18007a1d4  xor     r8d, r8d; DomainGuid
0x18007a1d7  xor     ecx, ecx; ComputerName
0x18007a1d9  call    cs:__imp_DsGetDcNameW
0x18007a1df  btr     dword ptr [rdi+0B0h], 0Dh
0x18007a1e7  test    eax, eax
0x18007a1e9  jnz     loc_18007A4A9
0x18007a1ef  mov     rcx, [rbp+DomainControllerInfo]
0x18007a1f3  test    rcx, rcx
0x18007a1f6  jz      loc_18007A4A9
0x18007a1fc  mov     rdx, [rcx+28h]
0x18007a200  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007a204  mov     rax, rbx
0x18007a207  inc     rax
0x18007a20a  cmp     [rdx+rax*2], r12w
0x18007a20f  jnz     short loc_18007A207
0x18007a211  mov     rcx, [rdi+98h]
0x18007a218  add     ax, ax
0x18007a21b  mov     [rdi+90h], ax
0x18007a222  add     ax, 2
0x18007a226  mov     [rdi+92h], ax
0x18007a22d  test    rcx, rcx
0x18007a230  jz      short loc_18007A242
0x18007a232  mov     rax, cs:?FsoFunctions@@3PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@EB; _KERB_FSO_COMMON_FUNCTION_TABLE const * const FsoFunctions
0x18007a239  mov     rax, [rax+8]
0x18007a23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a242  mov     rax, cs:?FsoFunctions@@3PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@EB; _KERB_FSO_COMMON_FUNCTION_TABLE const * const FsoFunctions
0x18007a249  movzx   ecx, word ptr [rdi+92h]
0x18007a250  mov     rax, [rax]
0x18007a253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a258  mov     [rdi+98h], rax
0x18007a25f  test    rax, rax
0x18007a262  jz      loc_18007A485
0x18007a268  mov     rdx, [rbp+DomainControllerInfo]
0x18007a26c  mov     rcx, rax; void *
0x18007a26f  movzx   r8d, word ptr [rdi+92h]; Size
0x18007a277  mov     rdx, [rdx+28h]; Src
0x18007a27b  call    memcpy_0
0x18007a280  mov     rax, [rbp+DomainControllerInfo]
0x18007a284  mov     rcx, [rax]
0x18007a287  inc     rbx
0x18007a28a  cmp     [rcx+rbx*2], r12w
0x18007a28f  jnz     short loc_18007A287
0x18007a291  mov     rcx, [rdi+0A8h]
0x18007a298  lea     r14, [rdi+0A0h]
0x18007a29f  add     bx, bx
0x18007a2a2  mov     [r14], bx
0x18007a2a6  add     bx, 2
0x18007a2aa  mov     [rdi+0A2h], bx
0x18007a2b1  test    rcx, rcx
0x18007a2b4  jz      short loc_18007A2C6
0x18007a2b6  mov     rax, cs:?FsoFunctions@@3PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@EB; _KERB_FSO_COMMON_FUNCTION_TABLE const * const FsoFunctions
0x18007a2bd  mov     rax, [rax+8]
0x18007a2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a2c6  mov     rax, cs:?FsoFunctions@@3PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@EB; _KERB_FSO_COMMON_FUNCTION_TABLE const * const FsoFunctions
0x18007a2cd  movzx   ecx, word ptr [rdi+0A2h]
0x18007a2d4  mov     rax, [rax]
0x18007a2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a2dc  mov     [rdi+0A8h], rax
0x18007a2e3  test    rax, rax
0x18007a2e6  jz      loc_18007A461
0x18007a2ec  mov     rdx, [rbp+DomainControllerInfo]
0x18007a2f0  mov     rcx, rax; void *
0x18007a2f3  movzx   r8d, word ptr [rdi+0A2h]; Size
0x18007a2fb  mov     rdx, [rdx]; Src
0x18007a2fe  call    memcpy_0
0x18007a303  mov     rdx, [rdi+98h]; DnsDomainName
0x18007a30a  lea     rax, [rbp+phDS]
0x18007a30e  mov     rcx, [rdi+0A8h]; DomainControllerName
0x18007a315  xor     r9d, r9d; ServicePrincipalName
0x18007a318  mov     [rsp+58h+rpNames], rax; phDS
0x18007a31d  xor     r8d, r8d; AuthIdentity
0x18007a320  mov     [rsp+58h+cNames], r12d; BindFlags
0x18007a325  call    cs:__imp_DsBindWithSpnExW
0x18007a32b  mov     rbx, [rbp+phDS]
0x18007a32f  test    rbx, rbx
0x18007a332  jz      loc_18007A429
0x18007a338  test    eax, eax
0x18007a33a  jnz     loc_18007A429
0x18007a340  mov     rax, cs:?FsoFunctions@@3PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@EB; _KERB_FSO_COMMON_FUNCTION_TABLE const * const FsoFunctions
0x18007a347  mov     ecx, 10h
0x18007a34c  mov     rax, [rax]
0x18007a34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a354  mov     rsi, rax
0x18007a357  test    rax, rax
0x18007a35a  jz      loc_18007A3ED
0x18007a360  mov     [rax], rbx
0x18007a363  mov     dword ptr [rax+8], 1
0x18007a36a  lock inc dword ptr [rax+8]
0x18007a36e  mov     ecx, [rdi+0B0h]
0x18007a374  btr     ecx, 0Eh
0x18007a378  mov     [rdi+0B0h], ecx
0x18007a37e  mov     r8, cs:WPP_GLOBAL_Control
0x18007a385  cmp     r8, r13
0x18007a388  jz      short loc_18007A3C8
0x18007a38a  test    byte ptr [r8+1Ch], 8
0x18007a38f  jz      short loc_18007A3C8
0x18007a391  bt      ecx, 0Dh
0x18007a395  lea     rax, [rdi+0A0h]
0x18007a39c  lea     rcx, aDomain; "domain"
0x18007a3a3  mov     [rsp+58h+rpNames], rax; __int64
0x18007a3a8  lea     rdx, [rdi+80h]
0x18007a3af  lea     r9, aForest; "forest"
0x18007a3b6  mov     qword ptr [rsp+58h+cNames], rdx; __int64
0x18007a3bb  cmovnb  r9, rcx
0x18007a3bf  mov     rcx, [r8+10h]; LoggerHandle
0x18007a3c3  call    WPP_SF_sZZ
0x18007a3c8  and     dword ptr [rdi+0B0h], 0FFFFFFFEh
0x18007a3cf  lea     rcx, [rdi+78h]; lpSystemTimeAsFileTime
0x18007a3d3  bts     dword ptr [rdi+0B0h], 0Fh
0x18007a3db  mov     [rdi+0B8h], rsi
0x18007a3e2  call    cs:__imp_GetSystemTimeAsFileTime
0x18007a3e8  jmp     loc_18007A58B
0x18007a3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a3f4  cmp     rcx, r13
0x18007a3f7  jz      short loc_18007A414
0x18007a3f9  test    byte ptr [rcx+1Ch], 2
0x18007a3fd  jz      short loc_18007A414
0x18007a3ff  mov     rcx, [rcx+10h]
0x18007a403  lea     r8, WPP_0117c3251e483c44e322262836b1158e_Traceguids
0x18007a40a  mov     edx, 19h
0x18007a40f  call    WPP_SF_
0x18007a414  lea     rcx, [rbp+phDS]; phDS
0x18007a418  call    cs:__imp_DsUnBindW
0x18007a41e  mov     ecx, [rdi+0B0h]
0x18007a424  jmp     loc_18007A4E2
0x18007a429  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a430  cmp     rcx, r13
0x18007a433  jz      loc_18007A4D3
0x18007a439  test    byte ptr [rcx+1Ch], 2
0x18007a43d  jz      loc_18007A4D3
0x18007a443  mov     rcx, [rcx+10h]
0x18007a447  lea     r8, WPP_0117c3251e483c44e322262836b1158e_Traceguids
0x18007a44e  mov     edx, 18h
0x18007a453  mov     [rsp+58h+cNames], eax
0x18007a457  mov     r9, r14
0x18007a45a  call    WPP_SF_Zd
0x18007a45f  jmp     short loc_18007A4D3
0x18007a461  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a468  cmp     rcx, r13
0x18007a46b  jz      loc_18007A58B
0x18007a471  test    byte ptr [rcx+1Ch], 1
0x18007a475  jz      loc_18007A58B
0x18007a47b  mov     edx, 17h
0x18007a480  jmp     loc_18007A57B
0x18007a485  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a48c  cmp     rcx, r13
0x18007a48f  jz      loc_18007A58B
0x18007a495  test    byte ptr [rcx+1Ch], 1
0x18007a499  jz      loc_18007A58B
0x18007a49f  mov     edx, 16h
0x18007a4a4  jmp     loc_18007A57B
0x18007a4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a4b0  cmp     rcx, r13
0x18007a4b3  jz      short loc_18007A4D3
0x18007a4b5  test    byte ptr [rcx+1Ch], 2
  ... truncated ...
```
