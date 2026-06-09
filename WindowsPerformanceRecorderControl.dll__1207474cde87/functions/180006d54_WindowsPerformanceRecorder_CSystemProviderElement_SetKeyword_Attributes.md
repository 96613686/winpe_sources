# WindowsPerformanceRecorder::CSystemProviderElement::SetKeyword(Attributes *)

- ea: `0x180006d54`
- end: `0x1800073f4`
- name: `?SetKeyword@CSystemProviderElement@WindowsPerformanceRecorder@@AEAAJPEAVAttributes@@@Z`
- size: `1696`
- prototype: `int(WindowsPerformanceRecorder::CSystemProviderElement *__hidden this, struct Attributes *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180004de0`

## callees

- `0x180006d54`
- `0x180007620`
- `0x180008330`
- `0x18000e340`
- `0x18000eeb0`
- `0x1800103c0`
- `0x180015744`
- `0x1800251b0`
- `0x18002c9e0`
- `0x180033a2c`
- `0x180044210`
- `0x180082d48`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007145`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007164`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007145`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007164`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WindowsPerformanceRecorder::CSystemProviderElement::SetKeyword(
        WindowsPerformanceRecorder::CSystemProviderElement *this,
        struct Attributes *a2)
{
  __int64 v3; // r14
  __int64 v4; // rdi
  __int64 v5; // rbx
  int IndexFromName; // eax
  unsigned int v7; // esi
  int *v8; // rcx
  __int64 v9; // rbx
  __int64 result; // rax
  _QWORD *v11; // r15
  char *v12; // rdx
  char *v13; // rcx
  volatile signed __int32 *v14; // r12
  __int64 v15; // r14
  int *v16; // rcx
  __int64 v17; // rdi
  char *v18; // rdx
  char *v19; // rcx
  volatile signed __int32 *v20; // r12
  __int64 v21; // rdi
  int *v22; // rcx
  __int64 v23; // rbx
  char *v24; // rdx
  char *v25; // rcx
  volatile signed __int32 *v26; // r15
  __int64 v27; // rbx
  char v28; // r12
  int v29; // r15d
  _DWORD *i; // rsi
  __int64 v31; // rbx
  unsigned __int64 j; // rcx
  __int64 v33; // rdx
  __int64 v34; // r11
  unsigned __int16 *v35; // rax
  int v36; // r8d
  int v37; // r9d
  __int64 *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // r8
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // [rsp+20h] [rbp-88h] BYREF
  __int64 v45[2]; // [rsp+28h] [rbp-80h] BYREF
  ATL::CAtlException *v46; // [rsp+38h] [rbp-70h] BYREF
  __int128 v47; // [rsp+40h] [rbp-68h] BYREF
  __int128 v48; // [rsp+50h] [rbp-58h]
  __int64 v49; // [rsp+60h] [rbp-48h]
  int v51; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v52; // [rsp+C8h] [rbp+20h] BYREF

  v45[1] = -2;
  v3 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v52 = v3;
  v4 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v45[0] = v4;
  v5 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v44 = v5;
  v51 = 0;
  IndexFromName = Attributes::getIndexFromName(a2, L"Value", 5, &v51);
  try
  {
    v7 = IndexFromName;
    if ( IndexFromName >= 0 )
    {
      v11 = (_QWORD *)((char *)a2 + 8);
      v12 = *(char **)(*((_QWORD *)a2 + 1) + 16LL * v51 + 8);
      v13 = v12 - 24;
      v14 = (volatile signed __int32 *)(v3 - 24);
      if ( v12 - 24 != (char *)(v3 - 24) )
      {
        if ( *((int *)v14 + 4) >= 0 && *(_QWORD *)v13 == *(_QWORD *)v14 )
        {
          v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13);
          if ( _InterlockedDecrement(v14 + 4) <= 0 )
            (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14, v14);
          v3 = v15 + 24;
          v52 = v3;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v52, v12, *((_DWORD *)v12 - 4));
          v3 = v52;
        }
      }
      if ( *(_DWORD *)(v3 - 16) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&v52);
        v3 = v52;
      }
      v51 = 0;
      if ( Attributes::getIndexFromName(a2, L"Strict", 6, &v51) >= 0 )
      {
        v18 = *(char **)(*v11 + 16LL * v51 + 8);
        v19 = v18 - 24;
        v20 = (volatile signed __int32 *)(v4 - 24);
        if ( v18 - 24 != (char *)(v4 - 24) )
        {
          if ( *((int *)v20 + 4) >= 0 && *(_QWORD *)v19 == *(_QWORD *)v20 )
          {
            v21 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v19);
            if ( _InterlockedDecrement(v20 + 4) <= 0 )
              (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20, v20);
            v4 = v21 + 24;
            v45[0] = v4;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(v45, v18, *((_DWORD *)v18 - 4));
            v4 = v45[0];
          }
        }
        if ( *(_DWORD *)(v4 - 16) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(v45);
          v4 = v45[0];
        }
      }
      else
      {
        v16 = (int *)(v4 - 24);
        if ( *(_DWORD *)(v4 - 24 + 8) )
        {
          if ( v16[4] >= 0 )
          {
            v17 = *(_QWORD *)v16;
            ATL::CStringData::Release((ATL::CStringData *)v16);
            v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17) + 24;
            v45[0] = v4;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetLength(v45, 0);
          }
        }
      }
      v51 = 0;
      if ( Attributes::getIndexFromName(a2, L"RundownFlag", 11, &v51) >= 0 )
      {
        v24 = *(char **)(*v11 + 16LL * v51 + 8);
        v25 = v24 - 24;
        v26 = (volatile signed __int32 *)(v5 - 24);
        if ( v24 - 24 != (char *)(v5 - 24) )
        {
          if ( *((int *)v26 + 4) >= 0 && *(_QWORD *)v25 == *(_QWORD *)v26 )
          {
            v27 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v25);
            if ( _InterlockedDecrement(v26 + 4) <= 0 )
              (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26, v26);
            v5 = v27 + 24;
            v44 = v5;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v44, v24, *((_DWORD *)v24 - 4));
            v5 = v44;
          }
        }
        if ( *(_DWORD *)(v5 - 16) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&v44);
          v5 = v44;
        }
      }
      else
      {
        v22 = (int *)(v5 - 24);
        if ( *(_DWORD *)(v5 - 24 + 8) )
        {
          if ( v22[4] >= 0 )
          {
            v23 = *(_QWORD *)v22;
            ATL::CStringData::Release((ATL::CStringData *)v22);
            v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23) + 24;
            v44 = v5;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetLength(&v44, 0);
          }
        }
      }
      if ( *(_DWORD *)(v3 - 16) )
      {
        v28 = (unsigned int)_o__wcsicmp(v4, L"true") == 0;
        v29 = 0;
        if ( *(_DWORD *)(v5 - 16) )
          v29 = ((unsigned int)_o__wcsicmp(v5, L"Start") != 0) + 1;
        if ( *((_DWORD *)this + 38) == 2 )
        {
          for ( i = (_DWORD *)**((_QWORD **)this + 21); i != *(_DWORD **)(*((_QWORD *)this + 21) + 8LL); i += 10 )
          {
            if ( *(_QWORD *)i
              && !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                                  &v52,
                                  *(_QWORD *)i)
              && i[8] == v29 )
            {
              v31 = *((_QWORD *)this + 21);
              memmove_0(i, i + 10, *(_QWORD *)(v31 + 8) - (_QWORD)(i + 10));
              *(_QWORD *)(v31 + 8) -= 40LL;
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v44);
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v45);
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v52);
              return 0;
            }
          }
        }
        else
        {
          for ( j = 0; j < 0x49; ++j )
          {
            v33 = 32 * j;
            v34 = *((_QWORD *)&WindowsPerformanceRecorder::CSystemProviderElement::sc_Keywords + 4 * j);
            if ( !v34 )
              ATL::AtlThrowImpl(-2147467259);
            v35 = (unsigned __int16 *)v3;
            do
            {
              v36 = *(unsigned __int16 *)((char *)v35 + v34 - v3);
              v37 = *v35 - v36;
              if ( v37 )
                break;
              ++v35;
            }
            while ( v36 );
            if ( !v37 )
            {
              v38 = (__int64 *)*((_QWORD *)this + 21);
              v39 = *v38;
              v40 = v38[1];
              while ( 1 )
              {
                v41 = *(_DWORD *)((char *)&WindowsPerformanceRecorder::CSystemProviderElement::sc_Keywords + v33 + 8);
                if ( v39 == v40 )
                  break;
                if ( *(_DWORD *)(v39 + 8) == v41 && *(_DWORD *)(v39 + 32) == v29 )
                {
                  if ( *(_BYTE *)(v39 + 36) != v28 )
                    *(_BYTE *)(v39 + 36) = 1;
                  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v44);
                  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v45);
                  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v52);
                  return 0;
                }
                v39 += 40;
              }
              *(_QWORD *)&v47 = v34;
              DWORD2(v47) = v41;
              DWORD2(v48) = *(_DWORD *)((char *)&WindowsPerformanceRecorder::CSystemProviderElement::sc_Keywords
                                      + v33
                                      + 24);
              *(const struct WindowsPerformanceRecorder::CSystemProviderElement::CKeyword near **)&v48 = *(const struct WindowsPerformanceRecorder::CSystemProviderElement::CKeyword near *const *)((char *)&WindowsPerformanceRecorder::CSystemProviderElement::sc_Keywords + v33 + 16);
              BYTE4(v49) = v28;
              LODWORD(v49) = v29;
              v42 = *((_QWORD *)this + 21);
              v43 = *(_QWORD *)(v42 + 8);
              if ( v43 == *(_QWORD *)(v42 + 16) )
              {
                std::vector<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>::_Emplace_reallocate<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx const &>(
                  v42,
                  (_BYTE *)v43,
                  (__int64)&v47);
              }
              else
              {
                *(_OWORD *)v43 = v47;
                *(_OWORD *)(v43 + 16) = v48;
                *(_QWORD *)(v43 + 32) = v49;
                *(_QWORD *)(v42 + 8) += 40LL;
              }
              if ( _InterlockedDecrement((volatile signed __int32 *)(v5 - 24 + 16)) <= 0 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 - 24) + 8LL))(*(_QWORD *)(v5 - 24));
              if ( _InterlockedDecrement((volatile signed __int32 *)(v4 - 24 + 16)) <= 0 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 - 24) + 8LL))(*(_QWORD *)(v4 - 24));
              if ( _InterlockedDecrement((volatile signed __int32 *)(v3 - 24 + 16)) <= 0 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v3 - 24) + 8LL))(*(_QWORD *)(v3 - 24));
              return 0;
            }
          }
        }
        ATL::CStringData::Release((ATL::CStringData *)(v5 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v4 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v3 - 24));
        result = 3310882822LL;
      }
      else
      {
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v44);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v45);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v52);
        result = 3310882822LL;
      }
    }
    else
    {
      v8 = (int *)(v3 - 24);
      if ( *(_DWORD *)(v3 - 24 + 8) )
      {
        if ( v8[4] >= 0 )
        {
          v9 = *(_QWORD *)v8;
          ATL::CStringData::Release((ATL::CStringData *)v8);
          v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9) + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetLength(&v52, 0);
        }
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v44);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v45);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v52);
      result = v7;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( std::length_error )
  {
    return 2147942414LL;
  }
  catch ( ATL::CAtlException *v46 )
  {
    return *(unsigned int *)v46;
  }
  return result;
}

```

## disassembly

```asm
0x180006d54  mov     [rsp+arg_0], rcx
0x180006d59  push    rbx
0x180006d5a  push    rsi
0x180006d5b  push    rdi
0x180006d5c  push    r12
0x180006d5e  push    r13
0x180006d60  push    r14
0x180006d62  push    r15
0x180006d64  sub     rsp, 70h
0x180006d68  mov     [rsp+0A8h+var_78], 0FFFFFFFFFFFFFFFEh
0x180006d71  mov     r13, rdx
0x180006d74  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006d7b  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006d82  mov     rcx, rbx
0x180006d85  mov     rax, [rax+18h]
0x180006d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d8e  lea     r14, [rax+18h]
0x180006d92  mov     [rsp+0A8h+arg_18], r14
0x180006d9a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006da1  mov     rcx, rbx
0x180006da4  mov     rax, [rax+18h]
0x180006da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dad  lea     rdi, [rax+18h]
0x180006db1  mov     [rsp+0A8h+var_80], rdi
0x180006db6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006dbd  mov     rcx, rbx
0x180006dc0  mov     rax, [rax+18h]
0x180006dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc9  lea     rbx, [rax+18h]
0x180006dcd  mov     [rsp+0A8h+var_88], rbx
0x180006dd2  xor     r15d, r15d
0x180006dd5  mov     [rsp+0A8h+arg_10], r15d
0x180006ddd  lea     r9, [rsp+0A8h+arg_10]; int *
0x180006de5  lea     r8d, [r15+5]; int
0x180006de9  lea     rdx, aValue; "Value"
0x180006df0  mov     rcx, r13; this
0x180006df3  call    ?getIndexFromName@Attributes@@QEBAJPEBGHPEAH@Z; Attributes::getIndexFromName(ushort const *,int,int *)
0x180006df8  mov     esi, eax
0x180006dfa  test    eax, eax
0x180006dfc  jns     short loc_180006E6C
0x180006dfe  lea     rcx, [r14-18h]; this
0x180006e02  cmp     [rcx+8], r15d
0x180006e06  jz      short loc_180006E42
0x180006e08  cmp     [rcx+10h], r15d
0x180006e0c  jge     short loc_180006E1F
0x180006e0e  xor     edx, edx
0x180006e10  lea     rcx, [rsp+0A8h+arg_18]
0x180006e18  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180006e1d  jmp     short loc_180006E42
0x180006e1f  mov     rbx, [rcx]
0x180006e22  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006e27  mov     rax, [rbx]
0x180006e2a  mov     rcx, rbx
0x180006e2d  mov     rax, [rax+18h]
0x180006e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e36  add     rax, 18h
0x180006e3a  mov     [rsp+0A8h+arg_18], rax
0x180006e42  lea     rcx, [rsp+0A8h+var_88]; this
0x180006e47  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180006e4c  nop
0x180006e4d  lea     rcx, [rsp+0A8h+var_80]; this
0x180006e52  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180006e57  nop
0x180006e58  lea     rcx, [rsp+0A8h+arg_18]; this
0x180006e60  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180006e65  mov     eax, esi
0x180006e67  jmp     loc_1800073E3
0x180006e6c  lea     r15, [r13+8]
0x180006e70  movsxd  rcx, [rsp+0A8h+arg_10]
0x180006e78  add     rcx, rcx
0x180006e7b  mov     rax, [r15]
0x180006e7e  mov     rdx, [rax+rcx*8+8]
0x180006e83  lea     rcx, [rdx-18h]
0x180006e87  lea     r12, [r14-18h]
0x180006e8b  cmp     rcx, r12
0x180006e8e  jz      short loc_180006EF5
0x180006e90  cmp     dword ptr [r12+10h], 0
0x180006e96  jl      short loc_180006EDC
0x180006e98  mov     rax, [r12]
0x180006e9c  cmp     [rcx], rax
0x180006e9f  jnz     short loc_180006EDC
0x180006ea1  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180006ea6  mov     r14, rax
0x180006ea9  or      esi, 0FFFFFFFFh
0x180006eac  mov     ecx, esi
0x180006eae  lock xadd [r12+10h], ecx
0x180006eb5  add     ecx, esi
0x180006eb7  test    ecx, ecx
0x180006eb9  jg      short loc_180006ECE
0x180006ebb  mov     rcx, [r12]
0x180006ebf  mov     rax, [rcx]
0x180006ec2  mov     rdx, r12
0x180006ec5  mov     rax, [rax+8]
0x180006ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ece  add     r14, 18h
0x180006ed2  mov     [rsp+0A8h+arg_18], r14
0x180006eda  jmp     short loc_180006EF8
0x180006edc  mov     r8d, [rdx-10h]
0x180006ee0  lea     rcx, [rsp+0A8h+arg_18]
0x180006ee8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006eed  mov     r14, [rsp+0A8h+arg_18]
0x180006ef5  or      esi, 0FFFFFFFFh
0x180006ef8  xor     r12d, r12d
0x180006efb  cmp     [r14-10h], r12d
0x180006eff  jz      short loc_180006F16
0x180006f01  lea     rcx, [rsp+0A8h+arg_18]
0x180006f09  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x180006f0e  mov     r14, [rsp+0A8h+arg_18]
0x180006f16  mov     [rsp+0A8h+arg_10], r12d
0x180006f1e  lea     r9, [rsp+0A8h+arg_10]; int *
0x180006f26  mov     r8d, 6; int
0x180006f2c  lea     rdx, aStrict; "Strict"
0x180006f33  mov     rcx, r13; this
0x180006f36  call    ?getIndexFromName@Attributes@@QEBAJPEBGHPEAH@Z; Attributes::getIndexFromName(ushort const *,int,int *)
0x180006f3b  test    eax, eax
0x180006f3d  jns     short loc_180006F82
0x180006f3f  lea     rcx, [rdi-18h]; this
0x180006f43  cmp     [rcx+8], r12d
0x180006f47  jz      short loc_180006F7D
0x180006f49  cmp     [rcx+10h], r12d
0x180006f4d  jge     short loc_180006F5D
0x180006f4f  xor     edx, edx
0x180006f51  lea     rcx, [rsp+0A8h+var_80]
0x180006f56  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180006f5b  jmp     short loc_180006F7D
0x180006f5d  mov     rdi, [rcx]
0x180006f60  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006f65  mov     rax, [rdi]
0x180006f68  mov     rcx, rdi
0x180006f6b  mov     rax, [rax+18h]
0x180006f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f74  lea     rdi, [rax+18h]
0x180006f78  mov     [rsp+0A8h+var_80], rdi
0x180006f7d  jmp     loc_180007013
0x180006f82  movsxd  rcx, [rsp+0A8h+arg_10]
0x180006f8a  add     rcx, rcx
0x180006f8d  mov     rax, [r15]
0x180006f90  mov     rdx, [rax+rcx*8+8]
0x180006f95  lea     rcx, [rdx-18h]
0x180006f99  lea     r12, [rdi-18h]
0x180006f9d  cmp     rcx, r12
0x180006fa0  jz      short loc_180006FFB
0x180006fa2  cmp     dword ptr [r12+10h], 0
0x180006fa8  jl      short loc_180006FE8
0x180006faa  mov     rax, [r12]
0x180006fae  cmp     [rcx], rax
0x180006fb1  jnz     short loc_180006FE8
0x180006fb3  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180006fb8  mov     rdi, rax
0x180006fbb  mov     ecx, esi
0x180006fbd  lock xadd [r12+10h], ecx
0x180006fc4  add     ecx, esi
0x180006fc6  test    ecx, ecx
0x180006fc8  jg      short loc_180006FDD
0x180006fca  mov     rcx, [r12]
0x180006fce  mov     rax, [rcx]
0x180006fd1  mov     rdx, r12
0x180006fd4  mov     rax, [rax+8]
0x180006fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fdd  add     rdi, 18h
0x180006fe1  mov     [rsp+0A8h+var_80], rdi
0x180006fe6  jmp     short loc_180006FFB
0x180006fe8  mov     r8d, [rdx-10h]
0x180006fec  lea     rcx, [rsp+0A8h+var_80]
0x180006ff1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006ff6  mov     rdi, [rsp+0A8h+var_80]
0x180006ffb  xor     r12d, r12d
0x180006ffe  cmp     [rdi-10h], r12d
0x180007002  jz      short loc_180007013
0x180007004  lea     rcx, [rsp+0A8h+var_80]
0x180007009  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x18000700e  mov     rdi, [rsp+0A8h+var_80]
0x180007013  mov     [rsp+0A8h+arg_10], r12d
0x18000701b  lea     r9, [rsp+0A8h+arg_10]; int *
0x180007023  mov     r8d, 0Bh; int
0x180007029  lea     rdx, aRundownflag; "RundownFlag"
0x180007030  mov     rcx, r13; this
0x180007033  call    ?getIndexFromName@Attributes@@QEBAJPEBGHPEAH@Z; Attributes::getIndexFromName(ushort const *,int,int *)
0x180007038  test    eax, eax
0x18000703a  jns     short loc_18000707F
0x18000703c  lea     rcx, [rbx-18h]; this
0x180007040  cmp     [rcx+8], r12d
0x180007044  jz      short loc_18000707A
0x180007046  cmp     [rcx+10h], r12d
0x18000704a  jge     short loc_18000705A
0x18000704c  xor     edx, edx
0x18000704e  lea     rcx, [rsp+0A8h+var_88]
0x180007053  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180007058  jmp     short loc_18000707A
0x18000705a  mov     rbx, [rcx]
0x18000705d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007062  mov     rax, [rbx]
0x180007065  mov     rcx, rbx
0x180007068  mov     rax, [rax+18h]
0x18000706c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007071  lea     rbx, [rax+18h]
0x180007075  mov     [rsp+0A8h+var_88], rbx
0x18000707a  jmp     loc_180007108
0x18000707f  movsxd  rcx, [rsp+0A8h+arg_10]
0x180007087  add     rcx, rcx
0x18000708a  mov     rax, [r15]
0x18000708d  mov     rdx, [rax+rcx*8+8]
0x180007092  lea     rcx, [rdx-18h]
0x180007096  lea     r15, [rbx-18h]
0x18000709a  cmp     rcx, r15
0x18000709d  jz      short loc_1800070F3
0x18000709f  cmp     [r15+10h], r12d
0x1800070a3  jl      short loc_1800070E0
0x1800070a5  mov     rax, [r15]
0x1800070a8  cmp     [rcx], rax
0x1800070ab  jnz     short loc_1800070E0
0x1800070ad  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800070b2  mov     rbx, rax
0x1800070b5  mov     ecx, esi
0x1800070b7  lock xadd [r15+10h], ecx
0x1800070bd  add     ecx, esi
0x1800070bf  test    ecx, ecx
0x1800070c1  jg      short loc_1800070D5
0x1800070c3  mov     rcx, [r15]
0x1800070c6  mov     rax, [rcx]
0x1800070c9  mov     rdx, r15
0x1800070cc  mov     rax, [rax+8]
0x1800070d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070d5  add     rbx, 18h
0x1800070d9  mov     [rsp+0A8h+var_88], rbx
0x1800070de  jmp     short loc_1800070F3
0x1800070e0  mov     r8d, [rdx-10h]
0x1800070e4  lea     rcx, [rsp+0A8h+var_88]
0x1800070e9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800070ee  mov     rbx, [rsp+0A8h+var_88]
0x1800070f3  cmp     [rbx-10h], r12d
0x1800070f7  jz      short loc_180007108
0x1800070f9  lea     rcx, [rsp+0A8h+var_88]
0x1800070fe  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x180007103  mov     rbx, [rsp+0A8h+var_88]
0x180007108  cmp     [r14-10h], r12d
0x18000710c  jnz     short loc_18000713B
0x18000710e  lea     rcx, [rsp+0A8h+var_88]; this
0x180007113  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180007118  nop
0x180007119  lea     rcx, [rsp+0A8h+var_80]; this
0x18000711e  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180007123  nop
0x180007124  lea     rcx, [rsp+0A8h+arg_18]; this
0x18000712c  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180007131  mov     eax, 0C5581006h
0x180007136  jmp     loc_1800073E3
0x18000713b  lea     rdx, aTrue; "true"
0x180007142  mov     rcx, rdi
0x180007145  call    cs:__imp__o__wcsicmp
0x18000714b  test    eax, eax
0x18000714d  setz    r12b
0x180007151  xor     r15d, r15d
0x180007154  cmp     [rbx-10h], r15d
0x180007158  jz      short loc_180007175
0x18000715a  lea     rdx, aStart; "Start"
0x180007161  mov     rcx, rbx
0x180007164  call    cs:__imp__o__wcsicmp
0x18000716a  neg     eax
0x18000716c  sbb     r15d, r15d
0x18000716f  neg     r15d
0x180007172  inc     r15d
0x180007175  mov     r13, [rsp+0A8h+arg_0]
0x18000717d  cmp     dword ptr [r13+98h], 2
0x180007185  jnz     loc_180007214
0x18000718b  mov     rsi, [r13+0A8h]
0x180007192  mov     rsi, [rsi]
0x180007195  mov     rax, [r13+0A8h]
0x18000719c  cmp     rsi, [rax+8]
0x1800071a0  jz      loc_1800073A9
0x1800071a6  mov     rdx, [rsi]
0x1800071a9  test    rdx, rdx
0x1800071ac  jz      short loc_18000720E
0x1800071ae  lea     rcx, [rsp+0A8h+arg_18]
0x1800071b6  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x1800071bb  test    eax, eax
0x1800071bd  jnz     short loc_18000720E
0x1800071bf  cmp     [rsi+20h], r15d
0x1800071c3  jnz     short loc_18000720E
0x1800071c5  mov     rbx, [r13+0A8h]
0x1800071cc  lea     rdx, [rsi+28h]; Src
0x1800071d0  mov     r8, [rbx+8]
0x1800071d4  sub     r8, rdx; Size
0x1800071d7  mov     rcx, rsi; void *
0x1800071da  call    memmove_0
0x1800071df  add     qword ptr [rbx+8], 0FFFFFFFFFFFFFFD8h
0x1800071e4  lea     rcx, [rsp+0A8h+var_88]; this
0x1800071e9  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800071ee  nop
0x1800071ef  lea     rcx, [rsp+0A8h+var_80]; this
0x1800071f4  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800071f9  nop
0x1800071fa  lea     rcx, [rsp+0A8h+arg_18]; this
0x180007202  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180007207  xor     eax, eax
0x180007209  jmp     loc_1800073E3
0x18000720e  add     rsi, 28h ; '('
0x180007212  jmp     short loc_180007195
0x180007214  xor     ecx, ecx
0x180007216  lea     rax, ?sc_Keywords@CSystemProviderElement@WindowsPerformanceRecorder@@2QBUCKeyword@12@B; WindowsPerformanceRecorder::CSystemProviderElement::CKeyword const near * const WindowsPerformanceRecorder::CSystemProviderElement::sc_Keywords
  ... truncated ...
```
