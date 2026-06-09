# DavAddUse

- ea: `0x18000235c`
- end: `0x1800028bc`
- name: `DavAddUse`
- size: `1376`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, unsigned int, const wchar_t *, wchar_t *pszSrc, int, __int64, HANDLE Handle, HANDLE hObject, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180006d20`

## callees

- `0x18000235c`
- `0x1800031d0`
- `0x180005310`
- `0x18000b6b4`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x180010028`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000258f`
- `msvcrt!_wcsicmp` at `0x18000258f`
- `ntdll!RtlAcquireResourceExclusive` at `0x180002488`
- `ntdll!RtlAcquireResourceExclusive` at `0x180002488`
- `ntdll!NtClose` at `0x180002649`
- `ntdll!NtClose` at `0x180002649`
- `ntdll!RtlReleaseResource` at `0x180002663`
- `ntdll!RtlReleaseResource` at `0x18000288e`
- `ntdll!RtlReleaseResource` at `0x180002663`
- `ntdll!RtlReleaseResource` at `0x18000288e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002404`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002656`
- `DAVHLPR!DavRemoveDummyShareFromFileNameEx` at `0x180002453`
- `DAVHLPR!DavRemoveDummyShareFromFileNameEx` at `0x180002453`
- `KERNEL32!LocalFree` at `0x18000289c`
- `KERNEL32!LocalFree` at `0x18000289c`
- `KERNEL32!LocalAlloc` at `0x1800023f6`
- `KERNEL32!LocalAlloc` at `0x1800023f6`

## pseudocode

```c
__int64 __fastcall DavAddUse(
        __int64 a1,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        wchar_t *pszSrc,
        int a6,
        __int64 a7,
        HANDLE Handle,
        HANDLE hObject,
        const wchar_t *a10)
{
  _QWORD *v10; // r14
  wchar_t *v13; // rdi
  wchar_t *v14; // rax
  DWORD LastError; // eax
  unsigned int v16; // ebx
  unsigned int UserEntry; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 *v21; // r12
  __int64 v22; // rbx
  __int64 v23; // r15
  _QWORD *v24; // rcx
  _QWORD *v25; // rbx
  __int64 v26; // rsi
  _BYTE *v27; // rcx
  __int64 v29; // rdx
  _DWORD *v30; // rax
  __int64 v31; // rsi
  __int64 v32; // rcx
  unsigned int v33; // eax
  unsigned int v34; // [rsp+50h] [rbp-20h] BYREF
  __int64 v35; // [rsp+58h] [rbp-18h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp-10h] BYREF

  v10 = 0;
  v34 = 0;
  v35 = 0;
  String2 = 0;
  if ( (unsigned int)DavConvertIDNToPunyCodeUNC(pszSrc, &String2) && (v13 = String2) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, String2);
  }
  else
  {
    v14 = (wchar_t *)LocalAlloc(0x40u, 2LL * (unsigned int)(a6 + 1));
    v13 = v14;
    if ( !v14 )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
      goto LABEL_81;
    }
    StringCchCopyW(v14, (unsigned int)(a6 + 1), pszSrc);
  }
  DavRemoveDummyShareFromFileNameEx(v13, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v13);
  if ( !RtlAcquireResourceExclusive(&Resource, 1u) )
  {
    v16 = 2140;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    goto LABEL_81;
  }
  UserEntry = DavGetUserEntry(&DavUseObject, a1, &v34, 1);
  v16 = UserEntry;
  if ( UserEntry )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_80;
    v19 = 252;
    v20 = UserEntry;
LABEL_22:
    WPP_SF_d(v18[2], v19, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v20);
LABEL_80:
    RtlReleaseResource(&Resource);
LABEL_81:
    if ( v13 )
      LocalFree(v13);
    return v16;
  }
  v21 = 0;
  v22 = DavUseObject;
  v23 = 2LL * v34;
  if ( !*(_QWORD *)(DavUseObject + 16LL * v34) )
    goto LABEL_60;
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    v24 = WPP_GLOBAL_Control;
    v22 = DavUseObject;
  }
  v25 = *(_QWORD **)(v22 + 8 * v23);
  v26 = 0;
  if ( !v25 )
    goto LABEL_61;
  do
  {
    if ( !(_DWORD)v26 && !_wcsicmp((const wchar_t *)(v25[2] + 8LL), v13) )
    {
      v10 = v25;
      LOBYTE(v26) = v25[3] == v26;
    }
    v21 = v25;
    v25 = (_QWORD *)*v25;
  }
  while ( v25 );
  if ( !v10 )
  {
LABEL_60:
    v24 = WPP_GLOBAL_Control;
LABEL_61:
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 2) != 0 )
      WPP_SF_(v24[2], 254, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    v32 = -1;
    do
      ++v32;
    while ( v13[v32] );
    v33 = DavCreateNewEntry(&v35, a2, a3, a4, v13, v32, a7, (__int64)Handle, (__int64)hObject, a10);
    v16 = v33;
    if ( v33 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_80;
      v19 = 255;
      v20 = v33;
      goto LABEL_22;
    }
    v31 = v35;
LABEL_71:
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
      *v21 = v31;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 263, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
      *(_QWORD *)(DavUseObject + 8 * v23) = v31;
    }
    goto LABEL_80;
  }
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    v27 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( v27 != (_BYTE *)&WPP_GLOBAL_Control )
    {
      if ( (v27[28] & 2) != 0 )
      {
        v29 = 260;
        goto LABEL_51;
      }
LABEL_52:
      if ( v27 != (_BYTE *)&WPP_GLOBAL_Control && (v27[28] & 2) != 0 )
        WPP_SF_(*((_QWORD *)v27 + 2), 261, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    }
LABEL_55:
    v16 = DavCreateNewEntry(&v35, a2, a3, a4, 0, 0, a7, (__int64)Handle, (__int64)hObject, a10);
    if ( v16 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_80;
      v19 = 262;
      v20 = v16;
      goto LABEL_22;
    }
    v30 = (_DWORD *)v10[2];
    v31 = v35;
    *(_QWORD *)(v35 + 16) = v30;
    ++*v30;
    goto LABEL_71;
  }
  if ( v27 != (_BYTE *)&WPP_GLOBAL_Control && (v27[28] & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)v27 + 2), 257, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    v27 = WPP_GLOBAL_Control;
  }
  if ( v10[3] )
  {
    if ( v27 != (_BYTE *)&WPP_GLOBAL_Control )
    {
      if ( (v27[28] & 2) != 0 )
      {
        v29 = 259;
LABEL_51:
        WPP_SF_(*((_QWORD *)v27 + 2), v29, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
        v27 = WPP_GLOBAL_Control;
        goto LABEL_52;
      }
      goto LABEL_52;
    }
    goto LABEL_55;
  }
  if ( v27 != (_BYTE *)&WPP_GLOBAL_Control && (v27[28] & 2) != 0 )
    WPP_SF_(*((_QWORD *)v27 + 2), 258, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
  NtClose(Handle);
  CloseHandle(hObject);
  RtlReleaseResource(&Resource);
  return 0;
}

```

## disassembly

```asm
0x18000235c  mov     [rsp-38h+arg_0], rbx
0x180002361  mov     [rsp-38h+arg_18], r9
0x180002366  mov     [rsp-38h+arg_10], r8d
0x18000236b  push    rbp
0x18000236c  push    rsi
0x18000236d  push    rdi
0x18000236e  push    r12
0x180002370  push    r13
0x180002372  push    r14
0x180002374  push    r15
0x180002376  mov     rbp, rsp
0x180002379  sub     rsp, 70h
0x18000237d  xor     r14d, r14d
0x180002380  mov     r13, rdx
0x180002383  mov     rsi, rcx
0x180002386  mov     [rbp+var_20], r14d
0x18000238a  mov     rcx, [rbp+pszSrc]
0x18000238e  lea     rdx, [rbp+String2]
0x180002392  mov     [rbp+var_18], r14
0x180002396  mov     [rbp+String2], r14
0x18000239a  call    DavConvertIDNToPunyCodeUNC
0x18000239f  lea     r12, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800023a6  lea     r15, WPP_GLOBAL_Control
0x1800023ad  test    eax, eax
0x1800023af  jz      short loc_1800023E6
0x1800023b1  mov     rdi, [rbp+String2]
0x1800023b5  test    rdi, rdi
0x1800023b8  jz      short loc_1800023E6
0x1800023ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023c1  cmp     rcx, r15
0x1800023c4  jz      loc_18000244E
0x1800023ca  test    byte ptr [rcx+1Ch], 2
0x1800023ce  jz      short loc_18000244E
0x1800023d0  mov     rcx, [rcx+10h]
0x1800023d4  mov     edx, 0F8h
0x1800023d9  mov     r9, rdi
0x1800023dc  mov     r8, r12
0x1800023df  call    WPP_SF_S
0x1800023e4  jmp     short loc_18000244E
0x1800023e6  mov     eax, [rbp+arg_28]
0x1800023e9  mov     ecx, 40h ; '@'; uFlags
0x1800023ee  inc     eax
0x1800023f0  mov     ebx, eax
0x1800023f2  lea     rdx, [rax+rax]; uBytes
0x1800023f6  call    cs:__imp_LocalAlloc
0x1800023fc  mov     rdi, rax
0x1800023ff  test    rax, rax
0x180002402  jnz     short loc_18000243F
0x180002404  call    cs:__imp_GetLastError
0x18000240a  mov     ebx, eax
0x18000240c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002413  cmp     rcx, r15
0x180002416  jz      loc_180002894
0x18000241c  test    byte ptr [rcx+1Ch], 1
0x180002420  jz      loc_180002894
0x180002426  mov     rcx, [rcx+10h]
0x18000242a  mov     edx, 0F9h
0x18000242f  mov     r9d, eax
0x180002432  mov     r8, r12
0x180002435  call    WPP_SF_d
0x18000243a  jmp     loc_180002894
0x18000243f  mov     r8, [rbp+pszSrc]; pszSrc
0x180002443  mov     rdx, rbx; cchDest
0x180002446  mov     rcx, rax; pszDest
0x180002449  call    StringCchCopyW
0x18000244e  xor     edx, edx
0x180002450  mov     rcx, rdi
0x180002453  call    cs:__imp_DavRemoveDummyShareFromFileNameEx
0x180002459  mov     rcx, cs:WPP_GLOBAL_Control
0x180002460  cmp     rcx, r15
0x180002463  jz      short loc_18000247F
0x180002465  test    byte ptr [rcx+1Ch], 2
0x180002469  jz      short loc_18000247F
0x18000246b  mov     rcx, [rcx+10h]
0x18000246f  mov     edx, 0FAh
0x180002474  mov     r9, rdi
0x180002477  mov     r8, r12
0x18000247a  call    WPP_SF_S
0x18000247f  mov     dl, 1; Wait
0x180002481  lea     rcx, Resource; Resource
0x180002488  call    cs:__imp_RtlAcquireResourceExclusive
0x18000248e  test    al, al
0x180002490  jnz     short loc_1800024C7
0x180002492  mov     ebx, 85Ch
0x180002497  mov     rcx, cs:WPP_GLOBAL_Control
0x18000249e  cmp     rcx, r15
0x1800024a1  jz      loc_180002894
0x1800024a7  test    byte ptr [rcx+1Ch], 1
0x1800024ab  jz      loc_180002894
0x1800024b1  mov     rcx, [rcx+10h]
0x1800024b5  mov     edx, 0FBh
0x1800024ba  mov     r8, r12
0x1800024bd  call    WPP_SF_
0x1800024c2  jmp     loc_180002894
0x1800024c7  mov     r9d, 1
0x1800024cd  lea     r8, [rbp+var_20]
0x1800024d1  mov     rdx, rsi
0x1800024d4  lea     rcx, DavUseObject
0x1800024db  call    DavGetUserEntry
0x1800024e0  mov     ebx, eax
0x1800024e2  test    eax, eax
0x1800024e4  jz      short loc_180002519
0x1800024e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024ed  cmp     rcx, r15
0x1800024f0  jz      loc_180002887
0x1800024f6  test    byte ptr [rcx+1Ch], 1
0x1800024fa  jz      loc_180002887
0x180002500  mov     edx, 0FCh
0x180002505  mov     r9d, eax
0x180002508  mov     r8, r12
0x18000250b  mov     rcx, [rcx+10h]
0x18000250f  call    WPP_SF_d
0x180002514  jmp     loc_180002887
0x180002519  mov     r15d, [rbp+var_20]
0x18000251d  mov     r12, r14
0x180002520  mov     rbx, cs:DavUseObject
0x180002527  add     r15, r15
0x18000252a  cmp     [rbx+r15*8], r14
0x18000252e  jz      loc_180002757
0x180002534  mov     rcx, cs:WPP_GLOBAL_Control
0x18000253b  lea     rax, WPP_GLOBAL_Control
0x180002542  cmp     rcx, rax
0x180002545  jz      short loc_180002570
0x180002547  test    byte ptr [rcx+1Ch], 2
0x18000254b  jz      short loc_180002570
0x18000254d  mov     rcx, [rcx+10h]
0x180002551  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180002558  mov     edx, 0FDh
0x18000255d  call    WPP_SF_
0x180002562  mov     rcx, cs:WPP_GLOBAL_Control
0x180002569  mov     rbx, cs:DavUseObject
0x180002570  mov     rbx, [rbx+r15*8]
0x180002574  mov     esi, r14d
0x180002577  test    rbx, rbx
0x18000257a  jz      loc_18000275E
0x180002580  test    esi, esi
0x180002582  jnz     short loc_1800025A4
0x180002584  mov     rcx, [rbx+10h]
0x180002588  mov     rdx, rdi; String2
0x18000258b  add     rcx, 8; String1
0x18000258f  call    cs:__imp__wcsicmp
0x180002595  test    eax, eax
0x180002597  jnz     short loc_1800025A4
0x180002599  cmp     [rbx+18h], rsi
0x18000259d  mov     r14, rbx
0x1800025a0  setz    sil
0x1800025a4  mov     r12, rbx
0x1800025a7  mov     rbx, [rbx]
0x1800025aa  test    rbx, rbx
0x1800025ad  jnz     short loc_180002580
0x1800025af  xor     esi, esi
0x1800025b1  test    r14, r14
0x1800025b4  jz      loc_180002757
0x1800025ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025c1  lea     rbx, WPP_GLOBAL_Control
0x1800025c8  cmp     rcx, rbx
0x1800025cb  jz      short loc_1800025EF
0x1800025cd  test    byte ptr [rcx+1Ch], 2
0x1800025d1  jz      short loc_1800025EF
0x1800025d3  mov     rcx, [rcx+10h]
0x1800025d7  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800025de  mov     edx, 100h
0x1800025e3  call    WPP_SF_
0x1800025e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025ef  test    r13, r13
0x1800025f2  jnz     loc_180002682
0x1800025f8  cmp     rcx, rbx
0x1800025fb  jz      short loc_18000261F
0x1800025fd  test    byte ptr [rcx+1Ch], 2
0x180002601  jz      short loc_18000261F
0x180002603  mov     rcx, [rcx+10h]
0x180002607  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000260e  mov     edx, 101h
0x180002613  call    WPP_SF_
0x180002618  mov     rcx, cs:WPP_GLOBAL_Control
0x18000261f  cmp     [r14+18h], rsi
0x180002623  jnz     short loc_180002670
0x180002625  cmp     rcx, rbx
0x180002628  jz      short loc_180002645
0x18000262a  test    byte ptr [rcx+1Ch], 2
0x18000262e  jz      short loc_180002645
0x180002630  mov     rcx, [rcx+10h]
0x180002634  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000263b  mov     edx, 102h
0x180002640  call    WPP_SF_
0x180002645  mov     rcx, [rbp+Handle]; Handle
0x180002649  call    cs:__imp_NtClose
0x18000264f  mov     rcx, [rbp+hObject]; hObject
0x180002656  call    cs:__imp_CloseHandle
0x18000265c  lea     rcx, Resource; Resource
0x180002663  call    cs:__imp_RtlReleaseResource
0x180002669  xor     eax, eax
0x18000266b  jmp     loc_1800028A4
0x180002670  cmp     rcx, rbx
0x180002673  jz      short loc_1800026C9
0x180002675  test    byte ptr [rcx+1Ch], 2
0x180002679  jz      short loc_1800026A9
0x18000267b  mov     edx, 103h
0x180002680  jmp     short loc_180002692
0x180002682  cmp     rcx, rbx
0x180002685  jz      short loc_1800026C9
0x180002687  test    byte ptr [rcx+1Ch], 2
0x18000268b  jz      short loc_1800026A9
0x18000268d  mov     edx, 104h
0x180002692  mov     rcx, [rcx+10h]
0x180002696  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000269d  call    WPP_SF_
0x1800026a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026a9  cmp     rcx, rbx
0x1800026ac  jz      short loc_1800026C9
0x1800026ae  test    byte ptr [rcx+1Ch], 2
0x1800026b2  jz      short loc_1800026C9
0x1800026b4  mov     rcx, [rcx+10h]
0x1800026b8  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800026bf  mov     edx, 105h
0x1800026c4  call    WPP_SF_
0x1800026c9  mov     rax, [rbp+arg_48]
0x1800026d0  lea     rcx, [rbp+var_18]
0x1800026d4  mov     r9, [rbp+arg_18]
0x1800026d8  mov     rdx, r13
0x1800026db  mov     r8d, [rbp+arg_10]
0x1800026df  mov     [rsp+70h+var_28], rax
0x1800026e4  mov     rax, [rbp+hObject]
0x1800026eb  mov     [rsp+70h+var_30], rax
0x1800026f0  mov     rax, [rbp+Handle]
0x1800026f4  mov     [rsp+70h+var_38], rax
0x1800026f9  mov     rax, [rbp+arg_30]
0x1800026fd  mov     [rsp+70h+var_40], rax
0x180002702  mov     [rsp+70h+var_48], esi
0x180002706  mov     [rsp+70h+var_50], rsi
0x18000270b  call    DavCreateNewEntry
0x180002710  mov     ebx, eax
0x180002712  test    eax, eax
0x180002714  jz      short loc_180002744
0x180002716  mov     rcx, cs:WPP_GLOBAL_Control
0x18000271d  lea     rax, WPP_GLOBAL_Control
0x180002724  cmp     rcx, rax
0x180002727  jz      loc_180002887
0x18000272d  test    byte ptr [rcx+1Ch], 1
0x180002731  jz      loc_180002887
0x180002737  mov     edx, 106h
0x18000273c  mov     r9d, ebx
0x18000273f  jmp     loc_180002805
0x180002744  mov     rax, [r14+10h]
0x180002748  mov     rsi, [rbp+var_18]
0x18000274c  mov     [rsi+10h], rax
0x180002750  inc     dword ptr [rax]
0x180002752  jmp     loc_180002815
0x180002757  mov     rcx, cs:WPP_GLOBAL_Control
0x18000275e  lea     rsi, WPP_GLOBAL_Control
0x180002765  cmp     rcx, rsi
0x180002768  jz      short loc_180002785
0x18000276a  test    byte ptr [rcx+1Ch], 2
0x18000276e  jz      short loc_180002785
0x180002770  mov     rcx, [rcx+10h]
0x180002774  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000277b  mov     edx, 0FEh
0x180002780  call    WPP_SF_
0x180002785  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002789  xor     r14d, r14d
0x18000278c  inc     rcx
0x18000278f  cmp     [rdi+rcx*2], r14w
0x180002794  jnz     short loc_18000278C
0x180002796  mov     rax, [rbp+arg_48]
0x18000279d  mov     rdx, r13
0x1800027a0  mov     r9, [rbp+arg_18]
0x1800027a4  mov     r8d, [rbp+arg_10]
0x1800027a8  mov     [rsp+70h+var_28], rax
0x1800027ad  mov     rax, [rbp+hObject]
0x1800027b4  mov     [rsp+70h+var_30], rax
0x1800027b9  mov     rax, [rbp+Handle]
0x1800027bd  mov     [rsp+70h+var_38], rax
0x1800027c2  mov     rax, [rbp+arg_30]
0x1800027c6  mov     [rsp+70h+var_40], rax
0x1800027cb  mov     [rsp+70h+var_48], ecx
0x1800027cf  lea     rcx, [rbp+var_18]
0x1800027d3  mov     [rsp+70h+var_50], rdi
0x1800027d8  call    DavCreateNewEntry
0x1800027dd  mov     ebx, eax
0x1800027df  test    eax, eax
0x1800027e1  jz      short loc_180002811
0x1800027e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027ea  cmp     rcx, rsi
0x1800027ed  jz      loc_180002887
0x1800027f3  test    byte ptr [rcx+1Ch], 1
0x1800027f7  jz      loc_180002887
0x1800027fd  mov     edx, 0FFh
0x180002802  mov     r9d, eax
0x180002805  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000280c  jmp     loc_18000250B
0x180002811  mov     rsi, [rbp+var_18]
0x180002815  test    r12, r12
0x180002818  jnz     short loc_180002855
0x18000281a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002821  lea     rax, WPP_GLOBAL_Control
0x180002828  cmp     rcx, rax
0x18000282b  jz      short loc_180002848
0x18000282d  test    byte ptr [rcx+1Ch], 2
0x180002831  jz      short loc_180002848
0x180002833  mov     rcx, [rcx+10h]
  ... truncated ...
```
