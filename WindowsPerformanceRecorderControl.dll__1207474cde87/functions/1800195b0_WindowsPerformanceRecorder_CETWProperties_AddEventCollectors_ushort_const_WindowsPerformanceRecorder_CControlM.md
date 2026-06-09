# WindowsPerformanceRecorder::CETWProperties::AddEventCollectors(ushort const *,WindowsPerformanceRecorder::CControlManager *,std::vector<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *,std::less<WindowsPerformanceRecorder::CBaseProfileElement const *>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>,std::allocator<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *,std::less<WindowsPerformanceRecorder::CBaseProfileElement const *>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>>> const &)

- ea: `0x1800195b0`
- end: `0x18001a48a`
- name: `?AddEventCollectors@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEBGPEAVCControlManager@2@AEBV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@@Z`
- size: `3802`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001a92c`

## callees

- `0x180001d74`
- `0x180006914`
- `0x180006b50`
- `0x18000aa10`
- `0x18000c550`
- `0x180013f6c`
- `0x1800195b0`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001f170`
- `0x180033b98`
- `0x180041e00`
- `0x180041e18`
- `0x180045cb4`
- `0x180045d98`
- `0x18004a584`
- `0x18004ed10`
- `0x18004f1d0`
- `0x18004f904`
- `0x1800584fc`
- `0x180082d48`
- `0x18008c010`

## string_xrefs

- `0x180019907`: `COMGUARD`
- `0x18001a230`: `COMGUARD`
- `0x18001a379`: `COMGUARD`
- `0x18001991c`: `CreateEventSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::AddEventCollectors(
        __int64 a1,
        __int64 a2,
        WindowsPerformanceRecorder::CControlManager *a3,
        __int64 *a4)
{
  _QWORD *v5; // rax
  __int64 *v6; // rdi
  __int64 v7; // r12
  __int64 *v8; // rsi
  __int64 *v9; // rbx
  void *v10; // r13
  unsigned int v11; // r14d
  __int64 **v12; // rcx
  __int64 *m; // rax
  __int64 v14; // rax
  __int128 v15; // xmm6
  void *v16; // r14
  _OWORD *v17; // rax
  __int64 **v18; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  __int64 *n; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rsi
  __int64 v25; // rdx
  void **v26; // rax
  void **v27; // rcx
  __int64 v28; // rbx
  WindowsPerformanceRecorder::CControlManager *v29; // r15
  __int64 v30; // r13
  int v31; // r8d
  __int64 v32; // r9
  const WCHAR *v33; // rcx
  __int64 v34; // rax
  signed int ETWSession; // eax
  signed int v36; // edi
  void *v37; // rbx
  void *v38; // rcx
  _QWORD *v39; // rbx
  void *v40; // rcx
  _QWORD *v41; // r14
  _QWORD *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdi
  unsigned __int64 v45; // rcx
  __int64 v46; // r12
  unsigned __int64 v47; // rax
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // r15
  _QWORD *v50; // rbx
  void *v51; // rax
  _QWORD *v52; // r8
  _QWORD *v53; // rdi
  __int64 v54; // rcx
  void *v55; // rax
  __int64 v56; // r15
  int v57; // r14d
  unsigned int v58; // r12d
  unsigned int v59; // ebx
  __int64 v60; // rcx
  unsigned int v61; // eax
  unsigned int v62; // r13d
  unsigned int v63; // eax
  __int64 v64; // rcx
  unsigned int v65; // eax
  __int64 v66; // rcx
  _BYTE *v67; // r14
  void *v68; // rcx
  _QWORD *v69; // rbx
  void *v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rdi
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rbx
  __int64 v78; // rcx
  __int64 v79; // rax
  void *v80; // rcx
  _QWORD *v81; // rbx
  void *v82; // rcx
  __int64 result; // rax
  unsigned int v84; // ecx
  WindowsPerformanceRecorder::CETWProperties *v85; // rcx
  void *v86; // rcx
  _QWORD *v87; // rbx
  void *v88; // rcx
  const struct _GUID *v89; // r8
  _QWORD *v90; // rbx
  void *v91; // rcx
  __int64 v92; // r9
  _QWORD *v93; // rcx
  _QWORD *v94; // rbx
  void *v95; // rcx
  _QWORD *v96; // rax
  _QWORD *v97; // rbx
  void *v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rcx
  const unsigned __int16 *v101; // r9
  const char *SessionName; // rax
  void *v103; // rcx
  _QWORD *v104; // rbx
  void *v105; // rcx
  signed int v106; // eax
  _QWORD *v107; // rbx
  void *v108; // rcx
  __int64 v109; // rcx
  unsigned int *v110; // rcx
  struct _TRACE_ENABLE_FLAG_EXT_HEADER *v111; // rbx
  __int64 v112; // rax
  const unsigned __int16 *v113; // r8
  signed int v114; // eax
  _QWORD *v115; // rbx
  void *v116; // rcx
  void *v117; // rcx
  _QWORD *v118; // rbx
  void *v119; // rcx
  struct IControlErrorInfo *v120; // [rsp+28h] [rbp-E0h]
  struct IControlErrorInfo *v121; // [rsp+28h] [rbp-E0h]
  struct IControlErrorInfo *v122; // [rsp+28h] [rbp-E0h]
  void *v123; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v124; // [rsp+48h] [rbp-C0h]
  void *Block; // [rsp+50h] [rbp-B8h] BYREF
  int v126; // [rsp+58h] [rbp-B0h]
  __int64 v127; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v128; // [rsp+68h] [rbp-A0h]
  unsigned int v129; // [rsp+6Ch] [rbp-9Ch]
  __int64 v130; // [rsp+70h] [rbp-98h] BYREF
  _QWORD *i; // [rsp+78h] [rbp-90h]
  void **v132; // [rsp+80h] [rbp-88h]
  __int64 v133; // [rsp+88h] [rbp-80h]
  _OWORD v134[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v135; // [rsp+B0h] [rbp-58h]
  ATL::CAtlException *v136; // [rsp+B8h] [rbp-50h] BYREF

  v135 = -2;
  v123 = 0;
  v124 = 0;
  try
  {
    v5 = operator new(0x38u);
    *v5 = v5;
    v5[1] = v5;
    v5[2] = v5;
    *((_WORD *)v5 + 12) = 257;
    v123 = v5;
    v11 = 0;
    v128 = 0;
    v22 = *a4;
    v23 = a4[1];
    for ( i = (_QWORD *)v23; ; v23 = (__int64)i )
    {
      v127 = v22;
      if ( v22 == v23 )
        break;
      v6 = **(__int64 ***)(*(_QWORD *)v22 + 40LL);
      while ( !*((_BYTE *)v6 + 25) )
      {
        v7 = v6[4];
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) == 8 && *(_QWORD *)(v7 + 200) )
        {
          v8 = *(__int64 **)(v7 + 192);
          v9 = (__int64 *)*v8;
          v10 = v123;
          while ( v9 != v8 )
          {
            v14 = std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,0>>::_Find_hint<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(
                    &v123,
                    v134,
                    v10,
                    v9 + 4);
            v15 = *(_OWORD *)v14;
            if ( !*(_BYTE *)(v14 + 16) )
            {
              if ( v124 == 0x492492492492492LL )
                std::_Throw_tree_length_error();
              v16 = v123;
              v132 = &v123;
              v133 = 0;
              v17 = operator new(0x38u);
              v17[2] = *((_OWORD *)v9 + 2);
              *((_QWORD *)v17 + 6) = v9[6];
              *(_QWORD *)v17 = v16;
              *((_QWORD *)v17 + 1) = v16;
              *((_QWORD *)v17 + 2) = v16;
              *((_WORD *)v17 + 12) = 0;
              v133 = 0;
              v134[0] = v15;
              std::_Tree_val<std::_Tree_simple_types<unsigned short>>::_Insert_node(&v123, v134, v17);
              v11 = v128;
            }
            v18 = (__int64 **)v9[2];
            if ( *((_BYTE *)v18 + 25) )
            {
              for ( j = (__int64 *)v9[1]; !*((_BYTE *)j + 25); j = (__int64 *)j[1] )
              {
                if ( v9 != (__int64 *)j[2] )
                  break;
                v9 = j;
              }
              v9 = j;
            }
            else
            {
              v9 = (__int64 *)v9[2];
              for ( k = *v18; !*((_BYTE *)k + 25); k = (__int64 *)*k )
                v9 = k;
            }
          }
          v11 += *(_DWORD *)(v7 + 200);
          v128 = v11;
        }
        v12 = (__int64 **)v6[2];
        if ( *((_BYTE *)v12 + 25) )
        {
          for ( m = (__int64 *)v6[1]; !*((_BYTE *)m + 25); m = (__int64 *)m[1] )
          {
            if ( v6 != (__int64 *)m[2] )
              break;
            v6 = m;
          }
          v6 = m;
        }
        else
        {
          v6 = (__int64 *)v6[2];
          for ( n = *v12; !*((_BYTE *)n + 25); n = (__int64 *)*n )
            v6 = n;
        }
      }
      v22 = v127 + 8;
    }
    v24 = 0;
    v129 = 0;
    v25 = 0;
    v26 = (void **)*a4;
    v27 = (void **)a4[1];
    v132 = v27;
    v28 = a1;
    v29 = a3;
    while ( 1 )
    {
      i = v26;
      v126 = v25;
      if ( v26 == v27 )
        break;
      *(_QWORD *)&v134[0] = *v26;
      v30 = *(_QWORD *)(*(_QWORD *)&v134[0] + 32LL);
      v127 = v30;
      if ( !v24 )
      {
        Block = 0;
        v31 = *(_DWORD *)(v28 + 256);
        if ( v11 )
          v32 = 4LL * v11 + 4;
        else
          v32 = 0;
        v33 = L"Shutdown";
        if ( !*(_BYTE *)(v28 + 418) )
          v33 = 0;
        if ( v31 == 2 || (v34 = *(_QWORD *)(v28 + 344), !*(_DWORD *)(v34 - 16)) )
          v34 = *(_QWORD *)(v28 + 336);
        ETWSession = WindowsPerformanceRecorder::CETWProperties::CreateETWSession(
                       *(_WORD **)(v30 + 24),
                       a2,
                       v31,
                       v32,
                       (__int64)&Block,
                       v34,
                       *(_BYTE *)(v30 + 80),
                       (__int64)v33);
        v36 = ETWSession;
        if ( ETWSession < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            "CreateEventSession",
            (const char *)0x60B,
            ETWSession,
            "COMGUARD",
            (const char *)v120);
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            "AddEventCollectors",
            (const char *)0x46E,
            v36,
            "COMGUARD",
            (const char *)v121);
          v37 = Block;
          if ( Block )
          {
            WindowsPerformanceRecorder::CETWProperties::CEventSession::~CEventSession((WindowsPerformanceRecorder::CETWProperties::CEventSession *)Block);
            operator delete(v37);
          }
          v38 = v123;
          v39 = (_QWORD *)*((_QWORD *)v123 + 1);
          if ( !*((_BYTE *)v39 + 25) )
          {
            do
            {
              std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
                &v123,
                &v123,
                v39[2]);
              v40 = v39;
              v39 = (_QWORD *)*v39;
              operator delete(v40);
            }
            while ( !*((_BYTE *)v39 + 25) );
            v38 = v123;
          }
          goto LABEL_182;
        }
        v24 = Block;
        *(_DWORD *)(*((_QWORD *)Block + 1) + 64LL) |= 0x1000000u;
        Block = 0;
        v41 = *(_QWORD **)(v28 + 16);
        v42 = *(_QWORD **)(v28 + 24);
        if ( v41 == v42 )
        {
          v43 = *(_QWORD *)(v28 + 8);
          v44 = ((__int64)v41 - v43) >> 3;
          if ( v44 == 0x1FFFFFFFFFFFFFFFLL )
            std::vector<WindowsPerformanceRecorder::Status::CWprEventProviderInfo>::_Xlength();
          v45 = ((__int64)v42 - v43) >> 3;
          if ( v45 > 0x1FFFFFFFFFFFFFFFLL - (v45 >> 1) )
LABEL_192:
            std::_Throw_bad_array_new_length();
          v46 = v44 + 1;
          v47 = (v45 >> 1) + v45;
          v48 = v44 + 1;
          if ( v47 >= v44 + 1 )
            v48 = v47;
          if ( v48 > 0x1FFFFFFFFFFFFFFFLL )
            std::_Throw_bad_array_new_length();
          v49 = 8 * v48;
          if ( 8 * v48 )
          {
            if ( v49 < 0x1000 )
            {
              v50 = operator new(8 * v48);
            }
            else
            {
              if ( v49 + 39 < v49 )
                goto LABEL_192;
              v51 = operator new(v49 + 39);
              if ( !v51 )
LABEL_67:
                __fastfail(5u);
              v50 = (_QWORD *)(((unsigned __int64)v51 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *(v50 - 1) = v51;
            }
          }
          else
          {
            v50 = 0;
          }
          v50[v44] = v24;
          v52 = *(_QWORD **)(a1 + 16);
          if ( v41 == v52 )
          {
            v53 = (_QWORD *)a1;
            memmove_0(v50, *(const void **)(a1 + 8), (size_t)v52 - *(_QWORD *)(a1 + 8));
          }
          else
          {
            memmove_0(v50, *(const void **)(a1 + 8), (size_t)v41 - *(_QWORD *)(a1 + 8));
            memmove_0(&v50[v44 + 1], v41, *(_QWORD *)(a1 + 16) - (_QWORD)v41);
            v53 = (_QWORD *)a1;
          }
          v54 = v53[1];
          if ( v54 )
          {
            if ( (unsigned __int64)(8 * ((v53[3] - v54) >> 3)) < 0x1000 )
            {
              v55 = (void *)v53[1];
            }
            else
            {
              v55 = *(void **)(v54 - 8);
              if ( (unsigned __int64)(v54 - (_QWORD)v55 - 8) > 0x1F )
                goto LABEL_67;
            }
            operator delete(v55);
          }
          v53[1] = v50;
          v53[2] = &v50[v46];
          v53[3] = &v50[v49 / 8];
        }
        else
        {
          *v41 = v24;
          *(_QWORD *)(v28 + 16) += 8LL;
        }
        *(_DWORD *)v24 = 2;
      }
      v56 = v30 + 16;
      v24[23] = *(_QWORD *)(v30 + 52);
      v57 = *(_DWORD *)(v30 + 44);
      if ( v57 == -1 )
      {
        v58 = *(_DWORD *)(v30 + 40);
        v59 = v58;
      }
      else
      {
        v60 = *(unsigned int *)(v30 + 36);
        v59 = *(_DWORD *)(v30 + 40);
        if ( (_DWORD)v60 )
        {
          v61 = (int)o_ceil_0(v60, v25);
          v58 = v59;
          if ( v59 >= v61 )
            v58 = v61;
        }
        else
        {
          v58 = *(_DWORD *)(v30 + 40);
        }
      }
      v62 = *(_DWORD *)(v30 + 36);
      v63 = v129;
      if ( v129 < v62 )
        v63 = v62;
      v129 = v63;
      if ( v57 != -1 )
      {
        v64 = *(unsigned int *)(v56 + 20);
        if ( (_DWORD)v64 )
        {
          v65 = (int)o_ceil_0(v64, v25);
          if ( v59 < v65 )
            v65 = v59;
          v59 = v65;
        }
      }
      v66 = v24[1];
      if ( *(_DWORD *)(v66 + 56) >= v59 )
        v59 = *(_DWORD *)(v66 + 56);
      *(_DWORD *)(v66 + 56) = v59;
      *(_DWORD *)(v24[1] + 52LL) = *(_DWORD *)(v24[1] + 56LL);
      v67 = (_BYTE *)v127;
      v28 = a1;
      if ( *(_BYTE *)(v127 + 32) )
      {
        if ( *(_DWORD *)(a1 + 256) == 1 )
        {
          v68 = v123;
          v69 = (_QWORD *)*((_QWORD *)v123 + 1);
          if ( !*((_BYTE *)v69 + 25) )
          {
            do
            {
              std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
                &v123,
                &v123,
                v69[2]);
              v70 = v69;
              v69 = (_QWORD *)*v69;
              operator delete(v70);
            }
            while ( !*((_BYTE *)v69 + 25) );
            v68 = v123;
          }
LABEL_152:
          operator delete(v68);
          return 2147549183LL;
        }
        *(_DWORD *)(v24[1] + 64LL) |= 0x100u;
      }
      if ( *(_BYTE *)(v56 + 64) )
      {
        v71 = v24[2];
        if ( v71 )
        {
          *(_DWORD *)(v71 + 136) |= 2u;
          *(_BYTE *)(a1 + 417) = 1;
          goto LABEL_121;
        }
        if ( a3 )
        {
          v72 = *(_QWORD *)(a1 + 320);
          v73 = v24[1];
          if ( v73 && (v74 = *(unsigned int *)(v73 + 116), (_DWORD)v74) )
            v75 = v73 + v74;
          else
            v75 = 0;
          v127 = 0;
          if ( (int)WindowsPerformanceRecorder::CControlManager::GetControlWarningInfo(
                      v73,
                      &v127,
                      3310880317LL,
                      2,
                      &IID_IControlManager,
                      v75) < 0 )
          {
            if ( v127 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
LABEL_117:
            v78 = v24[1];
            if ( v78 && (v79 = *(unsigned int *)(v78 + 116), (_DWORD)v79) )
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)3,
                "AddQPCDeltaTracking",
                (const char *)0xA6E,
                0xC558063D,
                "%ws: %ws",
                (const char *)(v78 + v79),
                *(_QWORD *)(v28 + 320));
            else
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)3,
                "AddQPCDeltaTracking",
                (const char *)0xA6E,
                0xC558063D,
                "%ws: %ws",
                0,
                *(_QWORD *)(v28 + 320));
            goto LABEL_121;
          }
          v77 = v127;
          Block = 0;
          if ( (int)WindowsPerformanceRecorder::CControlManager::GetControlWarningInfo(
                      v76,
                      &Block,
                      3310880317LL,
                      1,
                      &IID_IControlManager,
                      v72) >= 0 )
          {
            if ( v77 )
            {
              v130 = 0;
              if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))Block)(
                     Block,
                     &GUID_da87e768_8f54_4c65_bf91_0c3e6ff56519,
                     &v130) < 0 )
              {
                if ( v130 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
                goto LABEL_112;
              }
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v130 + 48LL))(v130, v77);
              if ( v130 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
            }
            WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::AddControlWarningInfo(
              (char *)a3 + 104,
              Block);
          }
LABEL_112:
          if ( Block )
            (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
          if ( v127 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
          v28 = a1;
          goto LABEL_117;
        }
      }
LABEL_121:
      if ( *(_DWORD *)(v56 + 44) )
      {
        if ( *(_DWORD *)(v28 + 256) == 1 )
        {
          v80 = v123;
          v81 = (_QWORD *)*((_QWORD *)v123 + 1);
          if ( !*((_BYTE *)v81 + 25) )
          {
            do
            {
              std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
                &v123,
                &v123,
                v81[2]);
              v82 = v81;
              v81 = (_QWORD *)*v81;
              operator delete(v82);
            }
            while ( !*((_BYTE *)v81 + 25) );
            v80 = v123;
          }
          operator delete(v80);
          return 3310886922LL;
        }
        if ( !*(_BYTE *)(v56 + 48) )
        {
          *(_DWORD *)(v24[1] + 64LL) |= 2u;
          *(_DWORD *)(v24[1] + 64LL) &= ~1u;
        }
        *(_DWORD *)(v24[1] + 60LL) = *(_DWORD *)(v56 + 44);
      }
      v84 = *(_DWORD *)(v56 + 52);
      if ( *((_DWORD *)v24 + 50) >= v84 )
        v84 = *((_DWORD *)v24 + 50);
      *((_DWORD *)v24 + 50) = v84;
      v85 = (WindowsPerformanceRecorder::CETWProperties *)*(unsigned int *)(v56 + 56);
      if ( (_DWORD)v85 && *(_DWORD *)(v56 + 60) )
      {
        v86 = v123;
        v87 = (_QWORD *)*((_QWORD *)v123 + 1);
        if ( !*((_BYTE *)v87 + 25) )
        {
          do
          {
            std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
              &v123,
              &v123,
              v87[2]);
            v88 = v87;
            v87 = (_QWORD *)*v87;
            operator delete(v88);
          }
          while ( !*((_BYTE *)v87 + 25) );
          v86 = v123;
        }
        operator delete(v86);
        return 3310880301LL;
      }
      *(_DWORD *)(v24[1] + 68LL) = (_DWORD)v85;
      v36 = WindowsPerformanceRecorder::CETWProperties::AddFlushThreshold(
              v85,
              (const struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *)v56,
              (struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)v24);
      if ( v36 < 0 )
      {
        v38 = v123;
        v90 = (_QWORD *)*((_QWORD *)v123 + 1);
        if ( !*((_BYTE *)v90 + 25) )
        {
          do
          {
            std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
              &v123,
              &v123,
              v90[2]);
            v91 = v90;
            v90 = (_QWORD *)*v90;
            operator delete(v91);
          }
          while ( !*((_BYTE *)v90 + 25) );
          v38 = v123;
        }
LABEL_182:
        operator delete(v38);
        return (unsigned int)v36;
      }
      v92 = *(_QWORD *)&v134[0] + 40LL;
      v93 = (_QWORD *)(*(_QWORD *)&v134[0] + 48LL);
      if ( v67[88] )
      {
        *(_DWORD *)(v24[1] + 64LL) |= 0x800u;
        if ( *v93 > 1u )
        {
          v68 = v123;
          v94 = (_QWORD *)*((_QWORD *)v123 + 1);
          if ( !*((_BYTE *)v94 + 25) )
          {
            do
            {
              std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
                &v123,
                &v123,
                v94[2]);
              v95 = v94;
              v94 = (_QWORD *)*v94;
              operator delete(v95);
            }
            while ( !*((_BYTE *)v94 + 25) );
            v68 = v123;
          }
          goto LABEL_152;
        }
      }
      v96 = v93;
      if ( v67[89] )
      {
        *(_DWORD *)(v24[1] + 64LL) |= 0x20000u;
        v96 = (_QWORD *)(v92 + 8);
        if ( *(_QWORD *)(v92 + 8) > 1u )
        {
          v68 = v123;
          v97 = (_QWORD *)*((_QWORD *)v123 + 1);
          if ( !*((_BYTE *)v97 + 25) )
          {
            do
            {
              std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
                &v123,
                &v123,
                v97[2]);
              v98 = v97;
              v97 = (_QWORD *)*v97;
              operator delete(v98);
            }
            while ( !*((_BYTE *)v97 + 25) );
            v68 = v123;
          }
          goto LABEL_152;
        }
      }
      if ( v67[90] )
        *(_DWORD *)(v24[1] + 64LL) |= 0x80u;
      else
        v93 = v96;
      v29 = a3;
      if ( !*v93 && a3 )
      {
        v99 = v24[1];
        if ( v99 && (v100 = *(unsigned int *)(v99 + 116), (_DWORD)v100) )
          v101 = (const unsigned __int16 *)(v99 + v100);
        else
          v101 = 0;
        WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(
          a3,
          -984087022,
          v89,
          v101,
          *(const unsigned __int16 **)(v28 + 320),
          0);
        SessionName = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)v24);
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          "AddEventCollectors",
          (const char *)0x4B8,
          0xC5580612,
          "%ws: %ws",
          SessionName,
          *(_QWORD *)(v28 + 320));
        v103 = v123;
        v104 = (_QWORD *)*((_QWORD *)v123 + 1);
        if ( !*((_BYTE *)v104 + 25) )
        {
          do
          {
            std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
              &v123,
              &v123,
              v104[2]);
            v105 = v104;
            v104 = (_QWORD *)*v104;
            operator delete(v105);
          }
          while ( !*((_BYTE *)v104 + 25) );
          v103 = v123;
        }
        operator delete(v103);
        return 3310880274LL;
      }
      v106 = WindowsPerformanceRecorder::CETWProperties::ConfigEventProviders(
               (WindowsPerformanceRecorder::CETWProperties *)v28,
               a3,
               (WindowsPerformanceRecorder::CETWProperties::CEventSession *)v24,
               (_QWORD **)v92,
               (__int64)v67);
      v36 = v106;
      if ( v106 < 0 )
      {
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          "AddEventCollectors",
          (const char *)0x4BD,
          v106,
          "COMGUARD",
          (const char *)v120);
        v38 = v123;
        v107 = (_QWORD *)*((_QWORD *)v123 + 1);
        if ( !*((_BYTE *)v107 + 25) )
        {
          do
          {
            std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
              &v123,
              &v123,
              v107[2]);
            v108 = v107;
            v107 = (_QWORD *)*v107;
            operator delete(v108);
          }
          while ( !*((_BYTE *)v107 + 25) );
          v38 = v123;
        }
        goto LABEL_182;
      }
      v25 = v62 * v58 + v126;
      v26 = (void **)(i + 1);
      v11 = v128;
      v27 = v132;
    }
    v109 = v129;
    *(_DWORD *)(v24[1] + 48LL) = v129;
    if ( (unsigned int)v109 > 0x400 )
      *(_BYTE *)(v28 + 416) = 1;
    *(_DWORD *)(v24[1] + 56LL) = (int)o_ceil_0(v109, v25);
    *(_DWORD *)(v24[1] + 52LL) = *(_DWORD *)(v24[1] + 56LL);
    v110 = (unsigned int *)v24[1];
    v111 = (struct _TRACE_ENABLE_FLAG_EXT_HEADER *)((char *)v110 + *((unsigned __int16 *)v110 + 36));
    if ( v124 )
    {
      if ( v110 && (v112 = v110[29], (_DWORD)v112) )
        v113 = (const unsigned __int16 *)((char *)v110 + v112);
      else
        v113 = 0;
      v114 = WindowsPerformanceRecorder::CETWProperties::AddSystemStacks(
               a1,
               v29,
               v113,
               v111,
               (char *)v110 + *v110,
               (__int64 **)&v123);
      v36 = v114;
      if ( v114 < 0 )
      {
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          "AddEventCollectors",
          (const char *)0x4D0,
          v114,
          "COMGUARD",
          (const char *)v122);
        v38 = v123;
        v115 = (_QWORD *)*((_QWORD *)v123 + 1);
        if ( !*((_BYTE *)v115 + 25) )
        {
          do
          {
            std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
              &v123,
              &v123,
              v115[2]);
            v116 = v115;
            v115 = (_QWORD *)*v115;
            operator delete(v116);
          }
          while ( !*((_BYTE *)v115 + 25) );
          v38 = v123;
        }
        goto LABEL_182;
      }
    }
    if ( !*((_WORD *)v111 + 1) )
      *(_DWORD *)(v24[1] + 72LL) = 0;
    v117 = v123;
    v118 = (_QWORD *)*((_QWORD *)v123 + 1);
    if ( !*((_BYTE *)v118 + 25) )
    {
      do
      {
        std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
          &v123,
          &v123,
          v118[2]);
        v119 = v118;
        v118 = (_QWORD *)*v118;
        operator delete(v119);
      }
      while ( !*((_BYTE *)v118 + 25) );
      v117 = v123;
    }
    operator delete(v117);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( std::length_error )
  {
    return 2147942414LL;
  }
  catch ( ATL::CAtlException *v136 )
  {
    return *(unsigned int *)v136;
  }
  return result;
}

```

## disassembly

```asm
0x1800195b0  mov     rax, rsp
0x1800195b3  mov     [rax+20h], r9
0x1800195b7  mov     [rax+18h], r8
0x1800195bb  mov     [rax+10h], rdx
0x1800195bf  mov     [rax+8], rcx
0x1800195c3  push    rbx
0x1800195c4  push    rsi
0x1800195c5  push    rdi
0x1800195c6  push    r12
0x1800195c8  push    r13
0x1800195ca  push    r14
0x1800195cc  push    r15
0x1800195ce  sub     rsp, 0D0h
0x1800195d5  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1800195dd  movaps  xmmword ptr [rax-48h], xmm6
0x1800195e1  mov     rbx, r9
0x1800195e4  mov     [rsp+108h+var_C8], 0
0x1800195ed  mov     [rsp+108h+var_C0], 0
0x1800195f6  mov     ecx, 38h ; '8'; Size
0x1800195fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019600  mov     [rax], rax
0x180019603  mov     [rax+8], rax
0x180019607  mov     [rax+10h], rax
0x18001960b  mov     word ptr [rax+18h], 101h
0x180019611  mov     [rsp+108h+var_C8], rax
0x180019616  xor     r14d, r14d
0x180019619  mov     [rsp+108h+var_A0], r14d
0x18001961e  mov     rcx, [rbx]
0x180019621  mov     rax, [rbx+8]
0x180019625  mov     [rsp+108h+var_90], rax
0x18001962a  mov     [rsp+108h+var_A8], rcx
0x18001962f  cmp     rcx, rax
0x180019632  jz      loc_180019817
0x180019638  mov     rax, [rcx]
0x18001963b  mov     rdi, [rax+28h]
0x18001963f  mov     rdi, [rdi]
0x180019642  cmp     byte ptr [rdi+19h], 0
0x180019646  jnz     loc_180019804
0x18001964c  mov     r12, [rdi+20h]
0x180019650  mov     rax, [r12]
0x180019654  mov     rcx, r12
0x180019657  mov     rax, [rax+8]
0x18001965b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019660  cmp     eax, 8
0x180019663  jnz     short loc_180019692
0x180019665  cmp     qword ptr [r12+0C8h], 0
0x18001966e  jz      short loc_180019692
0x180019670  mov     rsi, [r12+0C0h]
0x180019678  mov     rbx, [rsi]
0x18001967b  mov     r13, [rsp+108h+var_C8]
0x180019680  cmp     rbx, rsi
0x180019683  jnz     short loc_1800196CB
0x180019685  add     r14d, [r12+0C8h]
0x18001968d  mov     [rsp+108h+var_A0], r14d
0x180019692  mov     rcx, [rdi+10h]
0x180019696  cmp     byte ptr [rcx+19h], 0
0x18001969a  jz      loc_1800197D4
0x1800196a0  mov     rax, [rdi+8]
0x1800196a4  cmp     byte ptr [rax+19h], 0
0x1800196a8  jnz     short loc_1800196C3
0x1800196aa  nop     word ptr [rax+rax+00h]
0x1800196b0  cmp     rdi, [rax+10h]
0x1800196b4  jnz     short loc_1800196C3
0x1800196b6  mov     rdi, rax
0x1800196b9  mov     rax, [rax+8]
0x1800196bd  cmp     byte ptr [rax+19h], 0
0x1800196c1  jz      short loc_1800196B0
0x1800196c3  mov     rdi, rax
0x1800196c6  jmp     loc_180019642
0x1800196cb  lea     r9, [rbx+20h]
0x1800196cf  mov     r8, r13
0x1800196d2  lea     rdx, [rsp+108h+var_78]
0x1800196da  lea     rcx, [rsp+108h+var_C8]
0x1800196df  call    ??$_Find_hint@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@?$_Tree@V?$_Tset_traits@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@PEAX@std@@@1@QEAU?$_Tree_node@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@PEAX@1@AEBUCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@Z; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,0>>::_Find_hint<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *> * const,WindowsPerformanceRecorder::CBaseProfileElement::CStack const &)
0x1800196e4  movups  xmm6, xmmword ptr [rax]
0x1800196e7  cmp     byte ptr [rax+10h], 0
0x1800196eb  jnz     loc_180019780
0x1800196f1  mov     rax, 492492492492492h
0x1800196fb  cmp     [rsp+108h+var_C0], rax
0x180019700  jz      loc_18001A473
0x180019706  mov     r14, [rsp+108h+var_C8]
0x18001970b  lea     rax, [rsp+108h+var_C8]
0x180019710  mov     [rsp+108h+var_88], rax
0x180019718  mov     [rsp+108h+var_80], 0
0x180019724  mov     ecx, 38h ; '8'; Size
0x180019729  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001972e  nop
0x18001972f  movups  xmm0, xmmword ptr [rbx+20h]
0x180019733  movups  xmmword ptr [rax+20h], xmm0
0x180019737  movsd   xmm1, qword ptr [rbx+30h]
0x18001973c  movsd   qword ptr [rax+30h], xmm1
0x180019741  mov     [rax], r14
0x180019744  mov     [rax+8], r14
0x180019748  mov     [rax+10h], r14
0x18001974c  mov     word ptr [rax+18h], 0
0x180019752  mov     [rsp+108h+var_80], 0
0x18001975e  movaps  [rsp+108h+var_78], xmm6
0x180019766  mov     r8, rax
0x180019769  lea     rdx, [rsp+108h+var_78]
0x180019771  lea     rcx, [rsp+108h+var_C8]
0x180019776  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@G@std@@@std@@QEAAPEAU?$_Tree_node@GPEAX@2@U?$_Tree_id@PEAU?$_Tree_node@GPEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ushort>>::_Insert_node(std::_Tree_id<std::_Tree_node<ushort,void *> *>,std::_Tree_node<ushort,void *> * const)
0x18001977b  mov     r14d, [rsp+108h+var_A0]
0x180019780  mov     rcx, [rbx+10h]
0x180019784  cmp     byte ptr [rcx+19h], 0
0x180019788  jz      short loc_1800197AF
0x18001978a  mov     rax, [rbx+8]
0x18001978e  cmp     byte ptr [rax+19h], 0
0x180019792  jnz     short loc_1800197A7
0x180019794  cmp     rbx, [rax+10h]
0x180019798  jnz     short loc_1800197A7
0x18001979a  mov     rbx, rax
0x18001979d  mov     rax, [rax+8]
0x1800197a1  cmp     byte ptr [rax+19h], 0
0x1800197a5  jz      short loc_180019794
0x1800197a7  mov     rbx, rax
0x1800197aa  jmp     loc_180019680
0x1800197af  mov     rbx, rcx
0x1800197b2  mov     rcx, [rcx]
0x1800197b5  cmp     byte ptr [rcx+19h], 0
0x1800197b9  jnz     loc_180019680
0x1800197bf  nop
0x1800197c0  mov     rbx, rcx
0x1800197c3  mov     rax, [rcx]
0x1800197c6  mov     rcx, rax
0x1800197c9  cmp     byte ptr [rax+19h], 0
0x1800197cd  jz      short loc_1800197C0
0x1800197cf  jmp     loc_180019680
0x1800197d4  mov     rdi, rcx
0x1800197d7  mov     rcx, [rcx]
0x1800197da  cmp     byte ptr [rcx+19h], 0
0x1800197de  jnz     loc_180019642
0x1800197e4  nop     dword ptr [rax+00h]
0x1800197e8  nop     dword ptr [rax+rax+00000000h]
0x1800197f0  mov     rdi, rcx
0x1800197f3  mov     rax, [rcx]
0x1800197f6  mov     rcx, rax
0x1800197f9  cmp     byte ptr [rax+19h], 0
0x1800197fd  jz      short loc_1800197F0
0x1800197ff  jmp     loc_180019642
0x180019804  mov     rcx, [rsp+108h+var_A8]
0x180019809  add     rcx, 8
0x18001980d  mov     rax, [rsp+108h+var_90]
0x180019812  jmp     loc_18001962A
0x180019817  xor     esi, esi
0x180019819  xor     ecx, ecx
0x18001981b  mov     [rsp+108h+var_9C], ecx
0x18001981f  xor     edx, edx
0x180019821  mov     rcx, [rsp+108h+arg_18]
0x180019829  mov     rax, [rcx]
0x18001982c  mov     rcx, [rcx+8]
0x180019830  mov     [rsp+108h+var_88], rcx
0x180019838  mov     rbx, [rsp+108h+arg_0]
0x180019840  mov     r15, [rsp+108h+arg_10]
0x180019848  mov     r12, 1FFFFFFFFFFFFFFFh
0x180019852  mov     [rsp+108h+var_90], rax
0x180019857  mov     [rsp+108h+var_B0], edx
0x18001985b  cmp     rax, rcx
0x18001985e  jz      loc_18001A2D5
0x180019864  mov     rax, [rax]
0x180019867  mov     qword ptr [rsp+108h+var_78], rax
0x18001986f  mov     r13, [rax+20h]
0x180019873  mov     [rsp+108h+var_A8], r13
0x180019878  test    rsi, rsi
0x18001987b  jnz     loc_180019B5E
0x180019881  mov     [rsp+108h+Block], rsi
0x180019886  mov     r8d, [rbx+100h]
0x18001988d  test    r14d, r14d
0x180019890  jz      short loc_18001989F
0x180019892  mov     eax, r14d
0x180019895  lea     r9, ds:4[rax*4]
0x18001989d  jmp     short loc_1800198A2
0x18001989f  xor     r9d, r9d
0x1800198a2  lea     rcx, ?sc_wchShutdownFileNameTag@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Shutdown"
0x1800198a9  xor     eax, eax
0x1800198ab  cmp     [rbx+1A2h], al
0x1800198b1  cmovz   rcx, rax
0x1800198b5  movzx   edx, byte ptr [r13+50h]
0x1800198ba  cmp     r8d, 2
0x1800198be  jz      short loc_1800198CD
0x1800198c0  mov     rax, [rbx+158h]
0x1800198c7  cmp     dword ptr [rax-10h], 0
0x1800198cb  jnz     short loc_1800198D4
0x1800198cd  mov     rax, [rbx+150h]
0x1800198d4  mov     [rsp+108h+var_D0], rcx
0x1800198d9  mov     byte ptr [rsp+108h+var_D8], dl
0x1800198dd  mov     [rsp+108h+var_E0], rax; char *
0x1800198e2  lea     rax, [rsp+108h+Block]
0x1800198e7  mov     [rsp+108h+Format], rax
0x1800198ec  mov     rdx, [rsp+108h+arg_8]
0x1800198f4  mov     rcx, [r13+18h]
0x1800198f8  call    ?CreateETWSession@CETWProperties@WindowsPerformanceRecorder@@CAJPEBG0W4__MIDL_IProfile_0001@@_KPEAPEAUCEventSession@12@0_N0@Z; WindowsPerformanceRecorder::CETWProperties::CreateETWSession(ushort const *,ushort const *,__MIDL_IProfile_0001,unsigned __int64,WindowsPerformanceRecorder::CETWProperties::CEventSession * *,ushort const *,bool,ushort const *)
0x1800198fd  mov     edi, eax
0x1800198ff  test    eax, eax
0x180019901  jns     loc_1800199BF
0x180019907  lea     rbx, aComguard; "COMGUARD"
0x18001990e  mov     [rsp+108h+Format], rbx; Format
0x180019913  mov     r9d, eax; unsigned int
0x180019916  mov     r8d, 60Bh; char *
0x18001991c  lea     rdx, aCreateeventses; "CreateEventSession"
0x180019923  mov     ecx, 2; this
0x180019928  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001992d  mov     [rsp+108h+Format], rbx; Format
0x180019932  mov     r9d, edi; unsigned int
0x180019935  mov     r8d, 46Eh; char *
0x18001993b  lea     rdx, aAddeventcollec; "AddEventCollectors"
0x180019942  mov     ecx, 2; this
0x180019947  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001994c  nop
0x18001994d  mov     rbx, [rsp+108h+Block]
0x180019952  test    rbx, rbx
0x180019955  jz      short loc_18001996D
0x180019957  mov     rcx, rbx; this
0x18001995a  call    ??1CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::~CEventSession(void)
0x18001995f  mov     edx, 0D8h
0x180019964  mov     rcx, rbx; Block
0x180019967  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001996c  nop
0x18001996d  mov     rcx, [rsp+108h+var_C8]
0x180019972  mov     rbx, [rcx+8]
0x180019976  cmp     byte ptr [rbx+19h], 0
0x18001997a  jnz     short loc_1800199AE
0x18001997c  nop     dword ptr [rax+00h]
0x180019980  mov     r8, [rbx+10h]
0x180019984  lea     rdx, [rsp+108h+var_C8]
0x180019989  lea     rcx, [rsp+108h+var_C8]
0x18001998e  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@PEAX@std@@@1@PEAU?$_Tree_node@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>> &,std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *> *)
0x180019993  mov     rcx, rbx; Block
0x180019996  mov     rbx, [rbx]
0x180019999  mov     edx, 38h ; '8'
0x18001999e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800199a3  cmp     byte ptr [rbx+19h], 0
0x1800199a7  jz      short loc_180019980
0x1800199a9  mov     rcx, [rsp+108h+var_C8]; Block
0x1800199ae  mov     edx, 38h ; '8'
0x1800199b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800199b8  mov     eax, edi
0x1800199ba  jmp     loc_18001A458
0x1800199bf  mov     rsi, [rsp+108h+Block]
0x1800199c4  mov     rax, [rsi+8]
0x1800199c8  or      dword ptr [rax+40h], 1000000h
0x1800199cf  mov     [rsp+108h+Block], 0
0x1800199d8  mov     r14, [rbx+10h]
0x1800199dc  mov     rcx, [rbx+18h]
0x1800199e0  cmp     r14, rcx
0x1800199e3  jz      short loc_1800199F2
0x1800199e5  mov     [r14], rsi
0x1800199e8  add     qword ptr [rbx+10h], 8
0x1800199ed  jmp     loc_180019B58
0x1800199f2  mov     rax, [rbx+8]
0x1800199f6  mov     rdi, r14
0x1800199f9  sub     rdi, rax
0x1800199fc  sar     rdi, 3
0x180019a00  cmp     rdi, r12
0x180019a03  jz      loc_18001A479
0x180019a09  sub     rcx, rax
0x180019a0c  sar     rcx, 3
0x180019a10  mov     rdx, rcx
0x180019a13  shr     rdx, 1
0x180019a16  mov     rax, r12
0x180019a19  sub     rax, rdx
0x180019a1c  cmp     rcx, rax
0x180019a1f  ja      loc_18001A483
0x180019a25  lea     r12, [rdi+1]
0x180019a29  lea     rax, [rdx+rcx]
0x180019a2d  mov     rcx, r12
0x180019a30  cmp     rax, r12
0x180019a33  cmovnb  rcx, rax
0x180019a37  mov     rax, 1FFFFFFFFFFFFFFFh
0x180019a41  cmp     rcx, rax
0x180019a44  ja      loc_18001A47E
0x180019a4a  lea     r15, ds:0[rcx*8]
0x180019a52  test    r15, r15
0x180019a55  jnz     short loc_180019A5B
0x180019a57  xor     ebx, ebx
0x180019a59  jmp     short loc_180019A98
0x180019a5b  cmp     r15, 1000h
0x180019a62  jb      short loc_180019A8D
0x180019a64  lea     rcx, [r15+27h]; Size
0x180019a68  cmp     rcx, r15
0x180019a6b  jbe     loc_18001A483
0x180019a71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019a76  test    rax, rax
0x180019a79  jz      loc_180019B32
0x180019a7f  lea     rbx, [rax+27h]
0x180019a83  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180019a87  mov     [rbx-8], rax
0x180019a8b  jmp     short loc_180019A98
0x180019a8d  mov     rcx, r15; Size
0x180019a90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019a95  mov     rbx, rax
0x180019a98  mov     [rbx+rdi*8], rsi
0x180019a9c  mov     rax, [rsp+108h+arg_0]
0x180019aa4  mov     r8, [rax+10h]
0x180019aa8  mov     rcx, rbx; void *
0x180019aab  cmp     r14, r8
0x180019aae  jnz     short loc_180019AC1
0x180019ab0  mov     rdi, rax
0x180019ab3  mov     rdx, [rax+8]; Src
0x180019ab7  sub     r8, rdx; Size
0x180019aba  call    memmove_0
  ... truncated ...
```
