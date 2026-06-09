# Microsoft::Windows::Performance::CElfImageEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180020cc0`
- end: `0x1800213e4`
- name: `?OnAfterEvents@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `1828`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000139c`
- `0x18000f560`
- `0x18000fdb0`
- `0x18000fee4`
- `0x1800130a8`
- `0x180020cc0`
- `0x180022440`
- `0x180022584`
- `0x18002261c`
- `0x1800227bc`
- `0x18002282c`
- `0x180024c24`
- `0x1800268f4`
- `0x180026e30`
- `0x180027444`
- `0x180027910`

## import_xrefs

- `msvcrt!malloc` at `0x180021004`
- `msvcrt!malloc` at `0x180021063`
- `msvcrt!malloc` at `0x180021004`
- `msvcrt!malloc` at `0x180021063`
- `msvcrt!free` at `0x180021314`
- `msvcrt!free` at `0x180021322`
- `msvcrt!free` at `0x180021314`
- `msvcrt!free` at `0x180021322`
- `msvcrt!wcschr` at `0x1800210ca`
- `msvcrt!wcschr` at `0x1800210fc`
- `msvcrt!wcschr` at `0x1800210ca`
- `msvcrt!wcschr` at `0x1800210fc`
- `KERNEL32!QueryDosDeviceW` at `0x180020d83`
- `KERNEL32!QueryDosDeviceW` at `0x180020d83`
- `bcrypt!BCryptGetProperty` at `0x180020fcc`
- `bcrypt!BCryptGetProperty` at `0x180021038`
- `bcrypt!BCryptGetProperty` at `0x180020fcc`
- `bcrypt!BCryptGetProperty` at `0x180021038`
- `bcrypt!BCryptCreateHash` at `0x180021091`
- `bcrypt!BCryptCreateHash` at `0x180021091`
- `bcrypt!BCryptDestroyHash` at `0x1800212fe`
- `bcrypt!BCryptDestroyHash` at `0x1800212fe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002130a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002130a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180020f8f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180020f8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Performance::CElfImageEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r15d
  int v7; // r12d
  __int64 v8; // rdx
  WCHAR *v9; // rbx
  __int64 v10; // rax
  DWORD DosDeviceW; // eax
  char *v12; // rbx
  _QWORD *v13; // rdi
  __int64 *v14; // rax
  char *v15; // rcx
  signed __int64 v16; // r9
  int v17; // r8d
  int v18; // edx
  __int64 v19; // rcx
  unsigned __int16 *v20; // rax
  __int64 v21; // rcx
  int v22; // r8d
  int v23; // edx
  volatile signed __int32 *v24; // r14
  _QWORD **v25; // rax
  _QWORD *v26; // rdx
  _QWORD *v27; // rdx
  __int64 v28; // rax
  size_t v29; // rcx
  size_t v30; // rcx
  NTSTATUS v31; // eax
  char v32; // cl
  __int64 **v33; // rax
  __int64 *v34; // rbx
  bool i; // zf
  _QWORD *v36; // r14
  __int64 v37; // rcx
  wchar_t *v38; // rax
  __int64 v39; // rax
  int v40; // ecx
  wchar_t *v41; // rax
  __int64 v42; // rdi
  char *v43; // rax
  _QWORD *v44; // r15
  __int64 *v45; // rcx
  char *v46; // rdx
  signed __int64 v47; // r11
  int v48; // r10d
  int v49; // r9d
  __int64 v50; // rdx
  unsigned __int16 *v51; // rcx
  __int64 v52; // rdx
  int v53; // r10d
  int v54; // r9d
  __int64 v55; // rax
  _QWORD *v56; // rdx
  _QWORD *v57; // rdx
  __int64 *v58; // rax
  __int64 *j; // rax
  __int64 v60; // rcx
  unsigned int v61; // ebx
  ULONG pcbResult; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v64; // [rsp+44h] [rbp-BCh] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v66; // [rsp+4Ch] [rbp-B4h]
  char v67[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h]
  __int64 v69; // [rsp+60h] [rbp-A0h]
  unsigned int v70; // [rsp+68h] [rbp-98h]
  char *v71; // [rsp+70h] [rbp-90h] BYREF
  char *v72; // [rsp+78h] [rbp-88h] BYREF
  char v73[8]; // [rsp+80h] [rbp-80h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+88h] [rbp-78h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+90h] [rbp-70h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+98h] [rbp-68h]
  UCHAR v77[4]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v78; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v79; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v80; // [rsp+C0h] [rbp-40h]
  __int64 v81; // [rsp+C8h] [rbp-38h] BYREF
  char v82[8]; // [rsp+D0h] [rbp-30h] BYREF
  LPWSTR lpTargetPath; // [rsp+D8h] [rbp-28h]
  __int64 v84; // [rsp+E0h] [rbp-20h]
  char v85[8]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR DeviceName[4]; // [rsp+F8h] [rbp-8h] BYREF

  v70 = a4;
  v4 = a3;
  v66 = a3;
  Block = (void *)std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::_Buynode();
  v7 = 1;
  v64 = 0;
  *((_BYTE *)Block + 41) = 1;
  *((_QWORD *)Block + 1) = Block;
  *(_QWORD *)Block = Block;
  *((_QWORD *)Block + 2) = Block;
  wcscpy(DeviceName, L"_:");
  v69 = 0;
  std::vector<unsigned short>::_Construct_n(v82, v8, &v64);
  v9 = lpTargetPath;
  DeviceName[0] = 65;
  do
  {
    if ( v9 )
      v10 = (v84 - (__int64)v9) >> 1;
    else
      LODWORD(v10) = 0;
    DosDeviceW = QueryDosDeviceW(DeviceName, v9, v10);
    if ( DosDeviceW > 1 )
    {
      ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v71, v9, DosDeviceW - 2, &ATL::g_strmgr);
      v12 = v71;
      v13 = Block;
      v14 = (__int64 *)*((_QWORD *)Block + 1);
      while ( !*((_BYTE *)v14 + 41) )
      {
        if ( !v71 )
          ATL::AtlThrowImpl(-2147467259);
        v15 = (char *)v14[3];
        v16 = v71 - v15;
        do
        {
          v17 = *(unsigned __int16 *)&v15[v16];
          v18 = *(unsigned __int16 *)v15 - v17;
          if ( v18 )
            break;
          v15 += 2;
        }
        while ( v17 );
        if ( v18 >= 0 )
        {
          v13 = v14;
          v14 = (__int64 *)*v14;
        }
        else
        {
          v14 = (__int64 *)v14[2];
        }
      }
      if ( v13 == Block )
        goto LABEL_21;
      v19 = v13[3];
      if ( !v19 )
        ATL::AtlThrowImpl(-2147467259);
      v20 = (unsigned __int16 *)v71;
      v21 = v19 - (_QWORD)v71;
      do
      {
        v22 = *(unsigned __int16 *)((char *)v20 + v21);
        v23 = *v20 - v22;
        if ( v23 )
          break;
        ++v20;
      }
      while ( v22 );
      if ( v23 < 0 )
      {
LABEL_21:
        v24 = (volatile signed __int32 *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
        v79 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12 - 24) + 24;
        v80 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v24) + 24;
        v25 = (_QWORD **)std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,0>>::insert(
                           v67,
                           v85,
                           v13,
                           &v79);
        v26 = (_QWORD *)(v80 - 24);
        v13 = *v25;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v80 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
        v27 = (_QWORD *)(v79 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v79 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 8LL))(*v27);
        if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24, v24);
        v12 = v71;
      }
      v28 = -1;
      do
        ++v28;
      while ( DeviceName[v28] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(v13 + 4, DeviceName, (unsigned int)v28);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
      v9 = lpTargetPath;
    }
    ++DeviceName[0];
  }
  while ( DeviceName[0] != 91 );
  if ( v9 )
    operator delete(v9);
  if ( *((_QWORD *)this + 12) )
  {
    v73[0] = 0;
    *(_OWORD *)pbHashObject = 0;
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0x20u) < 0 )
      goto LABEL_53;
    *(_DWORD *)pbOutput = 0;
    pcbResult = 0;
    if ( BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0) < 0 || pcbResult != 4 )
      goto LABEL_53;
    v29 = *(unsigned int *)pbOutput;
    if ( *(_DWORD *)pbOutput )
    {
      if ( !(0xFFFFFFFFFFFFFFFFuLL / *(unsigned int *)pbOutput) )
        goto LABEL_53;
    }
    else
    {
      v29 = 0;
    }
    pbHashObject[0] = (PUCHAR)malloc(v29);
    if ( pbHashObject[0]
      && BCryptGetProperty(phAlgorithm, L"HashDigestLength", v77, 4u, &pcbResult, 0) >= 0
      && pcbResult == 4 )
    {
      v30 = *(unsigned int *)v77;
      if ( !*(_DWORD *)v77 )
      {
        v30 = 0;
        goto LABEL_49;
      }
      if ( 0xFFFFFFFFFFFFFFFFuLL / *(unsigned int *)v77 )
      {
LABEL_49:
        pbHashObject[1] = (PUCHAR)malloc(v30);
        if ( pbHashObject[1] )
        {
          v31 = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject[0], *(ULONG *)pbOutput, 0, 0, 0x20u);
          v32 = v73[0];
          if ( v31 >= 0 )
            v32 = 1;
          v73[0] = v32;
        }
      }
    }
LABEL_53:
    v33 = (__int64 **)*((_QWORD *)this + 11);
    v34 = *v33;
    for ( i = *v33 == (__int64 *)v33; ; i = v34 == *((__int64 **)this + 11) )
    {
      if ( i )
      {
        BCryptDestroyHash(phHash);
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        free(pbHashObject[1]);
        pbHashObject[1] = 0;
        free(pbHashObject[0]);
        break;
      }
      v36 = v34 + 3;
      v37 = v34[3];
      if ( *(int *)(v37 - 16) > 1 && (v38 = wcschr((const wchar_t *)(v37 + 2), 0x5Cu)) != 0 )
        v39 = ((__int64)v38 - *v36) >> 1;
      else
        LODWORD(v39) = -1;
      v40 = v39 + 1;
      if ( (int)v39 + 1 < 0 || v40 >= *(_DWORD *)(*v36 - 16LL) )
      {
        LODWORD(v42) = -1;
      }
      else
      {
        v41 = wcschr((const wchar_t *)(*v36 + 2LL * v40), 0x5Cu);
        if ( !v41 )
          goto LABEL_90;
        v42 = ((__int64)v41 - *v36) >> 1;
      }
      if ( (_DWORD)v42 != -1 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
          v34 + 3,
          &v72,
          (unsigned int)v42);
        v43 = v72;
        v44 = Block;
        v45 = (__int64 *)*((_QWORD *)Block + 1);
        if ( *((_BYTE *)v45 + 41) )
          goto LABEL_80;
        do
        {
          if ( !v72 )
            ATL::AtlThrowImpl(-2147467259);
          v46 = (char *)v45[3];
          v47 = v72 - v46;
          do
          {
            v48 = *(unsigned __int16 *)&v46[v47];
            v49 = *(unsigned __int16 *)v46 - v48;
            if ( v49 )
              break;
            v46 += 2;
          }
          while ( v48 );
          if ( v49 >= 0 )
          {
            v44 = v45;
            v45 = (__int64 *)*v45;
          }
          else
          {
            v45 = (__int64 *)v45[2];
          }
        }
        while ( !*((_BYTE *)v45 + 41) );
        if ( v44 == Block )
          goto LABEL_80;
        v50 = v44[3];
        if ( !v50 )
          ATL::AtlThrowImpl(-2147467259);
        v51 = (unsigned __int16 *)v72;
        v52 = v50 - (_QWORD)v72;
        do
        {
          v53 = *(unsigned __int16 *)((char *)v51 + v52);
          v54 = *v51 - v53;
          if ( v54 )
            break;
          ++v51;
        }
        while ( v53 );
        if ( v54 < 0 )
LABEL_80:
          v44 = Block;
        if ( v44 == Block )
        {
          v4 = v66;
        }
        else
        {
          v55 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
                  v34 + 3,
                  &v81,
                  (unsigned int)(*(_DWORD *)(*v36 - 16LL) - v42));
          ATL::operator+(&v78, v44 + 4, v55);
          v56 = (_QWORD *)(v81 - 24);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v81 - 24 + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v56 + 8LL))(*v56);
          v4 = v66;
          (*(void (__fastcall **)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, __int64 *, char *, union _LARGE_INTEGER, unsigned int))(*(_QWORD *)this + 152LL))(
            this,
            &v78,
            v73,
            a2,
            v66);
          v57 = (_QWORD *)(v78 - 24);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v78 - 24 + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v57 + 8LL))(*v57);
          v43 = v72;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v43 - 3) + 8LL))(*((_QWORD *)v43 - 3));
      }
LABEL_90:
      if ( *((_BYTE *)v34 + 33) )
        invalid_parameter(0, 0, 0, 0, 0);
      v58 = (__int64 *)v34[2];
      if ( *((_BYTE *)v58 + 33) )
      {
        for ( j = (__int64 *)v34[1]; !*((_BYTE *)j + 33) && v34 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v34 = j;
        v34 = j;
      }
      else
      {
        do
        {
          v34 = v58;
          v58 = (__int64 *)*v58;
        }
        while ( !*((_BYTE *)v58 + 33) );
      }
    }
  }
  v60 = *((_QWORD *)this + 1);
  if ( v60 )
    v7 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v60 + 96LL))(
           v60,
           a2,
           v4,
           v70);
  v61 = 0;
  if ( v7 != -2147467263 )
    v61 = v7;
  std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,0>>::_Erase(
    v67,
    *((_QWORD *)Block + 1));
  *((_QWORD *)Block + 1) = Block;
  v69 = 0;
  *(_QWORD *)Block = Block;
  *((_QWORD *)Block + 2) = Block;
  operator delete(Block);
  return v61;
}

```

## disassembly

```asm
0x180020cc0  push    rbp
0x180020cc2  push    rbx
0x180020cc3  push    rsi
0x180020cc4  push    rdi
0x180020cc5  push    r12
0x180020cc7  push    r13
0x180020cc9  push    r14
0x180020ccb  push    r15
0x180020ccd  lea     rbp, [rsp-18h]
0x180020cd2  sub     rsp, 118h
0x180020cd9  mov     rax, cs:__security_cookie
0x180020ce0  xor     rax, rsp
0x180020ce3  mov     [rbp+50h+var_50], rax
0x180020ce7  mov     [rsp+150h+var_E8], r9d
0x180020cec  mov     r15d, r8d
0x180020cef  mov     [rsp+150h+var_104], r8d
0x180020cf4  mov     rsi, rdx
0x180020cf7  mov     r13, rcx
0x180020cfa  call    ?_Buynode@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@2@XZ; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::_Buynode(void)
0x180020cff  mov     [rsp+150h+Block], rax
0x180020d04  lea     r8, [rsp+150h+var_10C]
0x180020d09  xor     r14d, r14d
0x180020d0c  lea     rcx, [rbp+50h+var_80]
0x180020d10  mov     r12d, 1
0x180020d16  mov     [rsp+150h+var_10C], r14w
0x180020d1c  mov     [rax+29h], r12b
0x180020d20  mov     rax, [rsp+150h+Block]
0x180020d25  mov     [rax+8], rax
0x180020d29  mov     rax, [rsp+150h+Block]
0x180020d2e  mov     [rax], rax
0x180020d31  mov     rax, [rsp+150h+Block]
0x180020d36  mov     [rax+10h], rax
0x180020d3a  mov     eax, dword ptr cs:asc_18002D63C; "_:"
0x180020d40  mov     dword ptr [rbp+50h+DeviceName], eax
0x180020d43  movzx   eax, word ptr cs:asc_18002D63C+4; ""
0x180020d4a  mov     [rbp+50h+var_54], ax
0x180020d4e  mov     [rsp+150h+var_F0], r14
0x180020d53  call    ?_Construct_n@?$vector@GV?$allocator@G@std@@@std@@QEAAX_KAEBG@Z; std::vector<ushort>::_Construct_n(unsigned __int64,ushort const &)
0x180020d58  mov     rbx, [rbp+50h+lpTargetPath]
0x180020d5c  lea     eax, [r12+40h]
0x180020d61  mov     [rbp+50h+DeviceName], ax
0x180020d65  test    rbx, rbx
0x180020d68  jnz     short loc_180020D6F
0x180020d6a  mov     rax, r14
0x180020d6d  jmp     short loc_180020D79
0x180020d6f  mov     rax, [rbp+50h+var_70]
0x180020d73  sub     rax, rbx
0x180020d76  sar     rax, 1
0x180020d79  mov     r8d, eax; ucchMax
0x180020d7c  lea     rcx, [rbp+50h+DeviceName]; lpDeviceName
0x180020d80  mov     rdx, rbx; lpTargetPath
0x180020d83  call    cs:__imp_QueryDosDeviceW
0x180020d89  cmp     eax, r12d
0x180020d8c  jbe     loc_180020F40
0x180020d92  lea     r8d, [rax-2]
0x180020d96  mov     rdx, rbx
0x180020d99  lea     r9, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180020da0  lea     rcx, [rsp+150h+var_E0]
0x180020da5  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ushort const *,int,ATL::IAtlStringMgr *)
0x180020daa  mov     r10, [rsp+150h+Block]
0x180020daf  mov     rbx, [rsp+150h+var_E0]
0x180020db4  mov     rdi, r10
0x180020db7  mov     rax, [r10+8]
0x180020dbb  jmp     short loc_180020DF6
0x180020dbd  test    rbx, rbx
0x180020dc0  jz      loc_1800213B8
0x180020dc6  mov     rcx, [rax+18h]
0x180020dca  mov     r9, rbx
0x180020dcd  sub     r9, rcx
0x180020dd0  movzx   edx, word ptr [rcx]
0x180020dd3  movzx   r8d, word ptr [rcx+r9]
0x180020dd8  sub     edx, r8d
0x180020ddb  jnz     short loc_180020DE6
0x180020ddd  add     rcx, 2
0x180020de1  test    r8d, r8d
0x180020de4  jnz     short loc_180020DD0
0x180020de6  test    edx, edx
0x180020de8  jns     short loc_180020DF0
0x180020dea  mov     rax, [rax+10h]
0x180020dee  jmp     short loc_180020DF6
0x180020df0  mov     rdi, rax
0x180020df3  mov     rax, [rax]
0x180020df6  cmp     [rax+29h], r14b
0x180020dfa  jz      short loc_180020DBD
0x180020dfc  cmp     rdi, r10
0x180020dff  jz      short loc_180020E32
0x180020e01  mov     rcx, [rdi+18h]
0x180020e05  test    rcx, rcx
0x180020e08  jz      loc_1800213C3
0x180020e0e  mov     rax, rbx
0x180020e11  sub     rcx, rbx
0x180020e14  movzx   edx, word ptr [rax]
0x180020e17  movzx   r8d, word ptr [rax+rcx]
0x180020e1c  sub     edx, r8d
0x180020e1f  jnz     short loc_180020E2A
0x180020e21  add     rax, 2
0x180020e25  test    r8d, r8d
0x180020e28  jnz     short loc_180020E14
0x180020e2a  test    edx, edx
0x180020e2c  jns     loc_180020EF9
0x180020e32  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180020e39  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180020e40  mov     rax, [rax+18h]
0x180020e44  call    cs:__guard_dispatch_icall_fptr
0x180020e4a  lea     rcx, [rbx-18h]
0x180020e4e  mov     r14, rax
0x180020e51  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180020e56  add     rax, 18h
0x180020e5a  mov     rcx, r14
0x180020e5d  mov     [rbp+50h+var_98], rax
0x180020e61  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180020e66  add     rax, 18h
0x180020e6a  lea     r9, [rbp+50h+var_98]
0x180020e6e  mov     r8, rdi
0x180020e71  mov     [rbp+50h+var_90], rax
0x180020e75  lea     rdx, [rbp+50h+var_60]
0x180020e79  lea     rcx, [rsp+150h+var_100]
0x180020e7e  call    ?insert@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$0A@@std@@@std@@QEAA?AViterator@12@V312@AEBU?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,0>>::insert(std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,0>>::iterator,std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> const &)
0x180020e83  mov     rdx, [rbp+50h+var_90]
0x180020e87  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180020e8b  mov     rdi, [rax]
0x180020e8e  or      eax, 0FFFFFFFFh
0x180020e91  lock xadd [rdx+10h], eax
0x180020e96  sub     eax, r12d
0x180020e99  jg      short loc_180020EAB
0x180020e9b  mov     rcx, [rdx]
0x180020e9e  mov     rax, [rcx]
0x180020ea1  mov     rax, [rax+8]
0x180020ea5  call    cs:__guard_dispatch_icall_fptr
0x180020eab  mov     rdx, [rbp+50h+var_98]
0x180020eaf  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180020eb3  or      eax, 0FFFFFFFFh
0x180020eb6  lock xadd [rdx+10h], eax
0x180020ebb  sub     eax, r12d
0x180020ebe  jg      short loc_180020ED0
0x180020ec0  mov     rcx, [rdx]
0x180020ec3  mov     rax, [rcx]
0x180020ec6  mov     rax, [rax+8]
0x180020eca  call    cs:__guard_dispatch_icall_fptr
0x180020ed0  or      eax, 0FFFFFFFFh
0x180020ed3  lock xadd [r14+10h], eax
0x180020ed9  sub     eax, r12d
0x180020edc  jg      short loc_180020EF1
0x180020ede  mov     rcx, [r14]
0x180020ee1  mov     rdx, r14
0x180020ee4  mov     rax, [rcx]
0x180020ee7  mov     rax, [rax+8]
0x180020eeb  call    cs:__guard_dispatch_icall_fptr
0x180020ef1  mov     rbx, [rsp+150h+var_E0]
0x180020ef6  xor     r14d, r14d
0x180020ef9  lea     rcx, [rdi+20h]
0x180020efd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020f01  lea     rdx, [rbp+50h+DeviceName]
0x180020f05  inc     rax
0x180020f08  cmp     [rdx+rax*2], r14w
0x180020f0d  jnz     short loc_180020F05
0x180020f0f  mov     r8d, eax
0x180020f12  lea     rdx, [rbp+50h+DeviceName]
0x180020f16  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180020f1b  lea     rdx, [rbx-18h]
0x180020f1f  or      eax, 0FFFFFFFFh
0x180020f22  lock xadd [rdx+10h], eax
0x180020f27  sub     eax, r12d
0x180020f2a  jg      short loc_180020F3C
0x180020f2c  mov     rcx, [rdx]
0x180020f2f  mov     rax, [rcx]
0x180020f32  mov     rax, [rax+8]
0x180020f36  call    cs:__guard_dispatch_icall_fptr
0x180020f3c  mov     rbx, [rbp+50h+lpTargetPath]
0x180020f40  movzx   eax, [rbp+50h+DeviceName]
0x180020f44  add     ax, r12w
0x180020f48  mov     [rbp+50h+DeviceName], ax
0x180020f4c  cmp     ax, 5Bh ; '['
0x180020f50  jnz     loc_180020D65
0x180020f56  test    rbx, rbx
0x180020f59  jz      short loc_180020F63
0x180020f5b  mov     rcx, rbx; Block
0x180020f5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020f63  cmp     [r13+60h], r14
0x180020f67  jz      loc_180021328
0x180020f6d  xorps   xmm0, xmm0
0x180020f70  mov     [rbp+50h+var_D0], r14b
0x180020f74  mov     edi, 20h ; ' '
0x180020f79  lea     rdx, pszAlgId; "SHA256"
0x180020f80  mov     r9d, edi; dwFlags
0x180020f83  lea     rcx, [rbp+50h+phAlgorithm]; phAlgorithm
0x180020f87  xor     r8d, r8d; pszImplementation
0x180020f8a  movdqu  xmmword ptr [rbp+50h+pbHashObject], xmm0
0x180020f8f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180020f95  test    eax, eax
0x180020f97  js      loc_1800210A4
0x180020f9d  mov     rcx, [rbp+50h+phAlgorithm]; hObject
0x180020fa1  lea     rax, [rsp+150h+var_110]
0x180020fa6  lea     ebx, [rdi-1Ch]
0x180020fa9  mov     [rsp+150h+dwFlags], r14d; dwFlags
0x180020fae  mov     r9d, ebx; cbOutput
0x180020fb1  mov     dword ptr [rsp+150h+pbOutput], r14d
0x180020fb6  lea     r8, [rsp+150h+pbOutput]; pbOutput
0x180020fbb  mov     [rsp+150h+var_110], r14d
0x180020fc0  lea     rdx, pszProperty; "ObjectLength"
0x180020fc7  mov     [rsp+150h+pcbResult], rax; pcbResult
0x180020fcc  call    cs:__imp_BCryptGetProperty
0x180020fd2  test    eax, eax
0x180020fd4  js      loc_1800210A4
0x180020fda  cmp     [rsp+150h+var_110], ebx
0x180020fde  jnz     loc_1800210A4
0x180020fe4  mov     ecx, dword ptr [rsp+150h+pbOutput]; Size
0x180020fe8  test    rcx, rcx
0x180020feb  jnz     short loc_180020FF2
0x180020fed  mov     rcx, r14
0x180020ff0  jmp     short loc_180021004
0x180020ff2  xor     edx, edx
0x180020ff4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020ff8  div     rcx
0x180020ffb  cmp     rax, r12
0x180020ffe  jb      loc_1800210A4
0x180021004  call    cs:__imp_malloc
0x18002100a  mov     [rbp+50h+pbHashObject], rax
0x18002100e  test    rax, rax
0x180021011  jz      loc_1800210A4
0x180021017  mov     rcx, [rbp+50h+phAlgorithm]; hObject
0x18002101b  lea     rax, [rsp+150h+var_110]
0x180021020  mov     [rsp+150h+dwFlags], r14d; dwFlags
0x180021025  lea     r8, [rbp+50h+var_A8]; pbOutput
0x180021029  mov     r9d, ebx; cbOutput
0x18002102c  mov     [rsp+150h+pcbResult], rax; pcbResult
0x180021031  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180021038  call    cs:__imp_BCryptGetProperty
0x18002103e  test    eax, eax
0x180021040  js      short loc_1800210A4
0x180021042  cmp     [rsp+150h+var_110], ebx
0x180021046  jnz     short loc_1800210A4
0x180021048  mov     ecx, dword ptr [rbp+50h+var_A8]; Size
0x18002104b  test    rcx, rcx
0x18002104e  jnz     short loc_180021055
0x180021050  mov     rcx, r14
0x180021053  jmp     short loc_180021063
0x180021055  xor     edx, edx
0x180021057  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002105b  div     rcx
0x18002105e  cmp     rax, r12
0x180021061  jb      short loc_1800210A4
0x180021063  call    cs:__imp_malloc
0x180021069  mov     [rbp+50h+pbHashObject+8], rax
0x18002106d  test    rax, rax
0x180021070  jz      short loc_1800210A4
0x180021072  mov     r9d, dword ptr [rsp+150h+pbOutput]; cbHashObject
0x180021077  lea     rdx, [rbp+50h+phHash]; phHash
0x18002107b  mov     r8, [rbp+50h+pbHashObject]; pbHashObject
0x18002107f  mov     rcx, [rbp+50h+phAlgorithm]; hAlgorithm
0x180021083  mov     [rsp+150h+var_120], edi; dwFlags
0x180021087  mov     [rsp+150h+dwFlags], r14d; cbSecret
0x18002108c  mov     [rsp+150h+pcbResult], r14; pbSecret
0x180021091  call    cs:__imp_BCryptCreateHash
0x180021097  movzx   ecx, [rbp+50h+var_D0]
0x18002109b  test    eax, eax
0x18002109d  cmovns  ecx, r12d
0x1800210a1  mov     [rbp+50h+var_D0], cl
0x1800210a4  mov     rax, [r13+58h]
0x1800210a8  mov     rbx, [rax]
0x1800210ab  cmp     rbx, rax
0x1800210ae  jz      loc_1800212FA
0x1800210b4  lea     r14, [rbx+18h]
0x1800210b8  mov     rcx, [r14]
0x1800210bb  cmp     [rcx-10h], r12d
0x1800210bf  jle     short loc_1800210DD
0x1800210c1  mov     edx, 5Ch ; '\'; Ch
0x1800210c6  add     rcx, 2; Str
0x1800210ca  call    cs:__imp_wcschr
0x1800210d0  test    rax, rax
0x1800210d3  jz      short loc_1800210DD
0x1800210d5  sub     rax, [r14]
0x1800210d8  sar     rax, 1
0x1800210db  jmp     short loc_1800210E0
0x1800210dd  or      eax, 0FFFFFFFFh
0x1800210e0  lea     ecx, [rax+1]
0x1800210e3  test    ecx, ecx
0x1800210e5  js      short loc_180021116
0x1800210e7  mov     r8, [r14]
0x1800210ea  cmp     ecx, [r8-10h]
0x1800210ee  jge     short loc_180021116
0x1800210f0  movsxd  rax, ecx
0x1800210f3  mov     edx, 5Ch ; '\'; Ch
0x1800210f8  lea     rcx, [r8+rax*2]; Str
0x1800210fc  call    cs:__imp_wcschr
0x180021102  mov     rdi, rax
0x180021105  test    rax, rax
0x180021108  jz      loc_18002129E
0x18002110e  sub     rdi, [r14]
0x180021111  sar     rdi, 1
0x180021114  jmp     short loc_180021119
0x180021116  or      edi, 0FFFFFFFFh
0x180021119  cmp     edi, 0FFFFFFFFh
0x18002111c  jz      loc_18002129E
0x180021122  mov     r8d, edi
0x180021125  lea     rdx, [rsp+150h+var_D8]
0x18002112a  mov     rcx, r14
0x18002112d  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x180021132  mov     r8, [rsp+150h+Block]
0x180021137  xor     r11d, r11d
  ... truncated ...
```
