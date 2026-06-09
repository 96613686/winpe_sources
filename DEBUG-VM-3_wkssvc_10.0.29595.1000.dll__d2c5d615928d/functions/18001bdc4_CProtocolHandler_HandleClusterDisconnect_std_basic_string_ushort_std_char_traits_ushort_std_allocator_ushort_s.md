# CProtocolHandler::HandleClusterDisconnect(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong)

- ea: `0x18001bdc4`
- end: `0x18001c0da`
- name: `?HandleClusterDisconnect@CProtocolHandler@@QEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00K@Z`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030080`

## callees

- `0x18001bdc4`
- `0x18001c0e0`
- `0x18001c630`
- `0x18001c6dc`
- `0x18001c73c`
- `0x18001c7f0`
- `0x18001c82c`
- `0x18001cabc`
- `0x18001cbf4`
- `0x18001e420`
- `0x180030eac`
- `0x1800315b8`
- `0x180031640`
- `0x180031b00`
- `0x180032324`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bfdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c08f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bfdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c08f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be19`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CProtocolHandler::HandleClusterDisconnect(__int64 a1, _QWORD *a2, __int64 *a3, __int64 a4, char a5)
{
  CProtocolHandler *v7; // r13
  int v8; // r8d
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rbx
  CClusterConnection *v12; // rdi
  int v13; // r15d
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r9
  char *v18; // rcx
  _QWORD *v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // r10
  __int64 v22; // r9
  __int64 v23; // rax
  _QWORD *v24; // r9
  unsigned int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v29; // [rsp+38h] [rbp-59h] BYREF
  __int64 v30; // [rsp+40h] [rbp-51h]
  _QWORD *v31; // [rsp+48h] [rbp-49h]
  __int64 *v32; // [rsp+50h] [rbp-41h]
  __int64 v33; // [rsp+58h] [rbp-39h]
  _BYTE v34[32]; // [rsp+60h] [rbp-31h] BYREF
  _BYTE v35[32]; // [rsp+80h] [rbp-11h] BYREF

  v30 = a4;
  v31 = a2;
  v32 = a3;
  v33 = a4;
  v7 = WitnessProtocolHandler;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)WitnessProtocolHandler + 10));
  if ( !*((_DWORD *)v7 + 32) )
    goto LABEL_54;
  if ( (a5 & 1) != 0 )
  {
    v9 = std::operator+<unsigned short>(v35, a2);
    v10 = std::operator+<unsigned short>(v34, v9, a3);
    v11 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                       (char *)v7 + 24,
                       &v29,
                       v10);
    std::wstring::~wstring(v34);
    std::wstring::~wstring(v35);
    if ( v11 == *((_QWORD *)v7 + 3) )
      v12 = 0;
    else
      v12 = *(CClusterConnection **)(v11 + 64);
    v13 = a5 & 2;
  }
  else
  {
    v13 = a5 & 2;
    if ( (a5 & 2) == 0 )
      goto LABEL_43;
    v14 = std::operator+<unsigned short>(v35, a2);
    v15 = std::operator+<unsigned short>(v34, v14, a3);
    v11 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                       (char *)v7 + 40,
                       &v29,
                       v15);
    std::wstring::~wstring(v34);
    std::wstring::~wstring(v35);
    if ( v11 == *((_QWORD *)v7 + 5) )
      goto LABEL_43;
    v12 = *(CClusterConnection **)(v11 + 64);
  }
  if ( !v12 )
  {
LABEL_43:
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      if ( (unsigned __int64)a3[3] <= 7 )
        v26 = (__int64)a3;
      else
        v26 = *a3;
      if ( a2[3] <= 7u )
        LODWORD(v27) = (_DWORD)a2;
      else
        v27 = *a2;
      WPP_SF_SS(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 33, v8, v27, v26);
    }
    v25 = 87;
    goto LABEL_55;
  }
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    if ( (unsigned __int64)a3[3] <= 7 )
      v16 = (__int64)a3;
    else
      v16 = *a3;
    if ( a2[3] <= 7u )
      LODWORD(v17) = (_DWORD)a2;
    else
      v17 = *a2;
    WPP_SF_SS(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 34, v8, v17, v16);
  }
  if ( (a5 & 1) != 0 )
  {
    v18 = (char *)v7 + 24;
  }
  else
  {
    if ( !v13 )
      goto LABEL_26;
    v18 = (char *)v7 + 40;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
    v18,
    v11);
LABEL_26:
  if ( CClusterConnection::ReleaseRegisterReference(v12) )
  {
LABEL_54:
    v25 = 0;
LABEL_55:
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)v7 + 10));
    goto LABEL_56;
  }
  if ( (a5 & 1) != 0 )
  {
    if ( a2[3] <= 7u )
      v19 = a2;
    else
      v19 = (_QWORD *)*a2;
    std::wstring::wstring(v34, v19);
    v20 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Eqrange<std::wstring>(
                       (char *)v7 + 8,
                       v35,
                       v34);
    v21 = *v20;
    v22 = v20[1];
    v23 = *v20;
    v29 = v23;
    while ( v23 != v22 )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(&v29);
      v23 = v29;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
      (char *)v7 + 8,
      v21,
      v22);
    std::wstring::~wstring(v34);
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)v7 + 10));
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    if ( a2[3] <= 7u )
      v24 = a2;
    else
      v24 = (_QWORD *)*a2;
    WPP_SF_S(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 35, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v24);
  }
  CClusterConnection::Terminate(v12);
  v25 = 0;
LABEL_56:
  std::wstring::~wstring(a2);
  std::wstring::~wstring(a3);
  std::wstring::~wstring(v30);
  return v25;
}

```

## disassembly

```asm
0x18001bdc4  mov     [rsp-8+arg_0], rbx
0x18001bdc9  push    rbp
0x18001bdca  push    rsi
0x18001bdcb  push    rdi
0x18001bdcc  push    r12
0x18001bdce  push    r13
0x18001bdd0  push    r14
0x18001bdd2  push    r15
0x18001bdd4  lea     rbp, [rsp-1Fh]
0x18001bdd9  sub     rsp, 0B0h
0x18001bde0  mov     rax, cs:__security_cookie
0x18001bde7  xor     rax, rsp
0x18001bdea  mov     [rbp+4Fh+var_40], rax
0x18001bdee  mov     rax, r9
0x18001bdf1  mov     [rbp+4Fh+var_A0], rax
0x18001bdf5  mov     r14, r8
0x18001bdf8  mov     rsi, rdx
0x18001bdfb  mov     [rbp+4Fh+var_98], rdx
0x18001bdff  mov     [rbp+4Fh+var_90], r8
0x18001be03  mov     [rbp+4Fh+var_88], rax
0x18001be07  mov     r13, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x18001be0e  mov     [rbp+4Fh+var_B0], 0
0x18001be15  mov     rcx, [r13+50h]; lpCriticalSection
0x18001be19  call    cs:__imp_EnterCriticalSection
0x18001be1f  cmp     dword ptr [r13+80h], 0
0x18001be27  jz      loc_18001C088
0x18001be2d  mov     r15d, [rbp+4Fh+arg_20]
0x18001be31  mov     r12d, r15d
0x18001be34  and     r12d, 1
0x18001be38  jz      short loc_18001BE90
0x18001be3a  mov     rdx, rsi
0x18001be3d  lea     rcx, [rbp+4Fh+var_60]
0x18001be41  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001be46  nop
0x18001be47  mov     r8, r14
0x18001be4a  mov     rdx, rax
0x18001be4d  lea     rcx, [rbp+4Fh+var_80]
0x18001be51  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001be56  mov     r8, rax
0x18001be59  lea     rdx, [rbp+4Fh+var_A8]
0x18001be5d  lea     rcx, [r13+18h]
0x18001be61  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001be66  mov     rbx, [rax]
0x18001be69  lea     rcx, [rbp+4Fh+var_80]
0x18001be6d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001be72  nop
0x18001be73  lea     rcx, [rbp+4Fh+var_60]
0x18001be77  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001be7c  cmp     rbx, [r13+18h]
0x18001be80  jnz     short loc_18001BE86
0x18001be82  xor     edi, edi
0x18001be84  jmp     short loc_18001BE8A
0x18001be86  mov     rdi, [rbx+40h]
0x18001be8a  and     r15d, 2
0x18001be8e  jmp     short loc_18001BEEA
0x18001be90  and     r15d, 2
0x18001be94  jz      loc_18001C031
0x18001be9a  mov     rdx, rsi
0x18001be9d  lea     rcx, [rbp+4Fh+var_60]
0x18001bea1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001bea6  nop
0x18001bea7  mov     r8, r14
0x18001beaa  mov     rdx, rax
0x18001bead  lea     rcx, [rbp+4Fh+var_80]
0x18001beb1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18001beb6  mov     r8, rax
0x18001beb9  lea     rdx, [rbp+4Fh+var_A8]
0x18001bebd  lea     rcx, [r13+28h]
0x18001bec1  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x18001bec6  mov     rbx, [rax]
0x18001bec9  lea     rcx, [rbp+4Fh+var_80]
0x18001becd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bed2  nop
0x18001bed3  lea     rcx, [rbp+4Fh+var_60]
0x18001bed7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bedc  cmp     rbx, [r13+28h]
0x18001bee0  jz      loc_18001C031
0x18001bee6  mov     rdi, [rbx+40h]
0x18001beea  test    rdi, rdi
0x18001beed  jz      loc_18001C031
0x18001bef3  lea     rax, WPP_witness_GLOBAL_Control
0x18001befa  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001bf01  cmp     rcx, rax
0x18001bf04  jz      short loc_18001BF43
0x18001bf06  test    byte ptr [rcx+1Ch], 1
0x18001bf0a  jz      short loc_18001BF43
0x18001bf0c  cmp     byte ptr [rcx+19h], 3
0x18001bf10  jb      short loc_18001BF43
0x18001bf12  cmp     qword ptr [r14+18h], 7
0x18001bf17  jbe     short loc_18001BF1E
0x18001bf19  mov     rax, [r14]
0x18001bf1c  jmp     short loc_18001BF21
0x18001bf1e  mov     rax, r14
0x18001bf21  cmp     qword ptr [rsi+18h], 7
0x18001bf26  jbe     short loc_18001BF2D
0x18001bf28  mov     r9, [rsi]
0x18001bf2b  jmp     short loc_18001BF30
0x18001bf2d  mov     r9, rsi
0x18001bf30  mov     edx, 22h ; '"'
0x18001bf35  mov     [rsp+0E0h+var_C0], rax
0x18001bf3a  mov     rcx, [rcx+10h]
0x18001bf3e  call    WPP_SF_SS
0x18001bf43  test    r12d, r12d
0x18001bf46  jz      short loc_18001BF4E
0x18001bf48  lea     rcx, [r13+18h]
0x18001bf4c  jmp     short loc_18001BF57
0x18001bf4e  test    r15d, r15d
0x18001bf51  jz      short loc_18001BF5F
0x18001bf53  lea     rcx, [r13+28h]
0x18001bf57  mov     rdx, rbx
0x18001bf5a  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x18001bf5f  mov     rcx, rdi; this
0x18001bf62  call    ?ReleaseRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::ReleaseRegisterReference(void)
0x18001bf67  test    eax, eax
0x18001bf69  jnz     loc_18001C088
0x18001bf6f  test    r12d, r12d
0x18001bf72  jz      short loc_18001BFD7
0x18001bf74  cmp     qword ptr [rsi+18h], 7
0x18001bf79  jbe     short loc_18001BF80
0x18001bf7b  mov     rdx, [rsi]
0x18001bf7e  jmp     short loc_18001BF83
0x18001bf80  mov     rdx, rsi
0x18001bf83  lea     rcx, [rbp+4Fh+var_80]
0x18001bf87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001bf8c  lea     r8, [rbp+4Fh+var_80]
0x18001bf90  lea     rdx, [rbp+4Fh+var_60]
0x18001bf94  lea     rcx, [r13+8]
0x18001bf98  call    ??$_Eqrange@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@std@@PEAU12@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Eqrange<std::wstring>(std::wstring const &)
0x18001bf9d  mov     r10, [rax]
0x18001bfa0  mov     r9, [rax+8]
0x18001bfa4  mov     rax, r10
0x18001bfa7  mov     [rbp+4Fh+var_A8], rax
0x18001bfab  cmp     rax, r9
0x18001bfae  jz      short loc_18001BFBF
0x18001bfb0  lea     rcx, [rbp+4Fh+var_A8]
0x18001bfb4  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(void)
0x18001bfb9  mov     rax, [rbp+4Fh+var_A8]
0x18001bfbd  jmp     short loc_18001BFAB
0x18001bfbf  mov     r8, r9
0x18001bfc2  mov     rdx, r10
0x18001bfc5  lea     rcx, [r13+8]
0x18001bfc9  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x18001bfce  lea     rcx, [rbp+4Fh+var_80]
0x18001bfd2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bfd7  mov     rcx, [r13+50h]; lpCriticalSection
0x18001bfdb  call    cs:__imp_LeaveCriticalSection
0x18001bfe1  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001bfe8  lea     rax, WPP_witness_GLOBAL_Control
0x18001bfef  cmp     rcx, rax
0x18001bff2  jz      short loc_18001C024
0x18001bff4  test    byte ptr [rcx+1Ch], 1
0x18001bff8  jz      short loc_18001C024
0x18001bffa  cmp     byte ptr [rcx+19h], 3
0x18001bffe  jb      short loc_18001C024
0x18001c000  cmp     qword ptr [rsi+18h], 7
0x18001c005  jbe     short loc_18001C00C
0x18001c007  mov     r9, [rsi]
0x18001c00a  jmp     short loc_18001C00F
0x18001c00c  mov     r9, rsi
0x18001c00f  mov     edx, 23h ; '#'
0x18001c014  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18001c01b  mov     rcx, [rcx+10h]
0x18001c01f  call    WPP_SF_S
0x18001c024  mov     rcx, rdi; this
0x18001c027  call    ?Terminate@CClusterConnection@@QEAAXXZ; CClusterConnection::Terminate(void)
0x18001c02c  mov     ebx, [rbp+4Fh+var_B0]
0x18001c02f  jmp     short loc_18001C096
0x18001c031  lea     rax, WPP_witness_GLOBAL_Control
0x18001c038  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001c03f  cmp     rcx, rax
0x18001c042  jz      short loc_18001C081
0x18001c044  test    byte ptr [rcx+1Ch], 1
0x18001c048  jz      short loc_18001C081
0x18001c04a  cmp     byte ptr [rcx+19h], 1
0x18001c04e  jb      short loc_18001C081
0x18001c050  cmp     qword ptr [r14+18h], 7
0x18001c055  jbe     short loc_18001C05C
0x18001c057  mov     rax, [r14]
0x18001c05a  jmp     short loc_18001C05F
0x18001c05c  mov     rax, r14
0x18001c05f  cmp     qword ptr [rsi+18h], 7
0x18001c064  jbe     short loc_18001C06B
0x18001c066  mov     r9, [rsi]
0x18001c069  jmp     short loc_18001C06E
0x18001c06b  mov     r9, rsi
0x18001c06e  mov     edx, 21h ; '!'
0x18001c073  mov     [rsp+0E0h+var_C0], rax
0x18001c078  mov     rcx, [rcx+10h]
0x18001c07c  call    WPP_SF_SS
0x18001c081  mov     ebx, 57h ; 'W'
0x18001c086  jmp     short loc_18001C08B
0x18001c088  mov     ebx, [rbp+4Fh+var_B0]
0x18001c08b  mov     rcx, [r13+50h]; lpCriticalSection
0x18001c08f  call    cs:__imp_LeaveCriticalSection
0x18001c095  nop
0x18001c096  mov     rcx, rsi
0x18001c099  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c09e  nop
0x18001c09f  mov     rcx, r14
0x18001c0a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c0a7  nop
0x18001c0a8  mov     rcx, [rbp+4Fh+var_A0]
0x18001c0ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c0b1  mov     eax, ebx
0x18001c0b3  mov     rcx, [rbp+4Fh+var_40]
0x18001c0b7  xor     rcx, rsp; StackCookie
0x18001c0ba  call    __security_check_cookie
0x18001c0bf  mov     rbx, [rsp+0E0h+arg_0]
0x18001c0c7  add     rsp, 0B0h
0x18001c0ce  pop     r15
0x18001c0d0  pop     r14
0x18001c0d2  pop     r13
0x18001c0d4  pop     r12
0x18001c0d6  pop     rdi
0x18001c0d7  pop     rsi
0x18001c0d8  pop     rbp
0x18001c0d9  retn
```
