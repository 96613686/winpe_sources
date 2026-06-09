# CInSeqHash::GetInSequenceInformation(QUEUE_FORMAT const *,wchar_t const *,_GUID * *,_ULARGE_INTEGER * *,ulong * *,wchar_t * * *,long * *,ulong * *,ulong *)

- ea: `0x180066148`
- end: `0x18006694d`
- name: `?GetInSequenceInformation@CInSeqHash@@QEAAXPEBUQUEUE_FORMAT@@PEB_WPEAPEAU_GUID@@PEAPEAT_ULARGE_INTEGER@@PEAPEAKPEAPEAPEA_WPEAPEAJ4PEAK@Z`
- size: `2053`
- prototype: `void __fastcall(CInSeqHash *__hidden this, const struct QUEUE_FORMAT *, const wchar_t *, struct _GUID **, union _ULARGE_INTEGER **, unsigned int **, wchar_t ***, int **, unsigned int **, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18002f830`

## callees

- `0x18000bab8`
- `0x18000ebdc`
- `0x18000f430`
- `0x18000fa28`
- `0x180011578`
- `0x180012d5c`
- `0x180013780`
- `0x18002c61c`
- `0x18004bb70`
- `0x1800650ac`
- `0x180066148`
- `0x180066954`
- `0x18009b51c`
- `0x18009bd1c`
- `0x1800abd04`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180066376`
- `msvcrt!free` at `0x1800663f7`
- `msvcrt!free` at `0x180066441`
- `msvcrt!free` at `0x180066456`
- `msvcrt!free` at `0x180066773`
- `msvcrt!free` at `0x18006677f`
- `msvcrt!free` at `0x180066789`
- `msvcrt!free` at `0x180066795`
- `msvcrt!free` at `0x1800667a1`
- `msvcrt!free` at `0x1800667ab`
- `msvcrt!free` at `0x180066831`
- `msvcrt!free` at `0x18006683d`
- `msvcrt!free` at `0x180066847`
- `msvcrt!free` at `0x180066853`
- `msvcrt!free` at `0x18006685f`
- `msvcrt!free` at `0x180066869`
- `msvcrt!free` at `0x180066913`
- `msvcrt!free` at `0x18006691c`
- `msvcrt!free` at `0x180066925`
- `msvcrt!free` at `0x18006692e`
- `msvcrt!free` at `0x180066937`
- `msvcrt!free` at `0x180066940`
- `msvcrt!free` at `0x180066376`
- `msvcrt!free` at `0x1800663f7`
- `msvcrt!free` at `0x180066441`
- `msvcrt!free` at `0x180066456`
- `msvcrt!free` at `0x180066773`
- `msvcrt!free` at `0x18006677f`
- `msvcrt!free` at `0x180066789`
- `msvcrt!free` at `0x180066795`
- `msvcrt!free` at `0x1800667a1`
- `msvcrt!free` at `0x1800667ab`
- `msvcrt!free` at `0x180066831`
- `msvcrt!free` at `0x18006683d`
- `msvcrt!free` at `0x180066847`
- `msvcrt!free` at `0x180066853`
- `msvcrt!free` at `0x18006685f`
- `msvcrt!free` at `0x180066869`
- `msvcrt!free` at `0x180066913`
- `msvcrt!free` at `0x18006691c`
- `msvcrt!free` at `0x180066925`
- `msvcrt!free` at `0x18006692e`
- `msvcrt!free` at `0x180066937`
- `msvcrt!free` at `0x180066940`
- `msvcrt!wcschr` at `0x180066336`
- `msvcrt!wcschr` at `0x1800663ba`
- `msvcrt!wcschr` at `0x180066336`
- `msvcrt!wcschr` at `0x1800663ba`
- `KERNEL32!CompareStringW` at `0x180066422`
- `KERNEL32!CompareStringW` at `0x180066422`

## pseudocode

```c
// Hidden C++ exception states: #wind=27 #try_helpers=1
void __fastcall CInSeqHash::GetInSequenceInformation(
        CInSeqHash *this,
        const struct QUEUE_FORMAT *a2,
        const wchar_t *a3,
        struct _GUID **a4,
        union _ULARGE_INTEGER **a5,
        unsigned int **a6,
        wchar_t ***a7,
        int **a8,
        unsigned int **a9,
        unsigned int *a10)
{
  CInSeqHash *v10; // r15
  void *v11; // r12
  int v12; // eax
  CReference *v13; // rbx
  wchar_t *v14; // rdi
  wchar_t *v15; // rax
  unsigned __int64 v16; // rbx
  _OWORD *v17; // r13
  CInSeqHash *v18; // r12
  _DWORD *v19; // rdi
  __int64 v20; // r14
  const WCHAR *i; // rax
  CReference *v22; // rbx
  int v23; // eax
  wchar_t *v24; // rax
  int v25; // eax
  unsigned int v26[2]; // [rsp+30h] [rbp-938h] BYREF
  wchar_t *v27; // [rsp+38h] [rbp-930h]
  void *v28; // [rsp+40h] [rbp-928h]
  void *Block; // [rsp+48h] [rbp-920h] BYREF
  PCNZWCH lpString2; // [rsp+50h] [rbp-918h]
  unsigned __int64 v31; // [rsp+58h] [rbp-910h] BYREF
  CReadWriteLock *v32; // [rsp+60h] [rbp-908h] BYREF
  const struct QUEUE_FORMAT *v33; // [rsp+68h] [rbp-900h] BYREF
  CInSeqHash *v34; // [rsp+70h] [rbp-8F8h]
  struct _GUID **v35; // [rsp+78h] [rbp-8F0h]
  union _ULARGE_INTEGER **v36; // [rsp+80h] [rbp-8E8h]
  unsigned int **v37; // [rsp+88h] [rbp-8E0h]
  wchar_t ***v38; // [rsp+90h] [rbp-8D8h]
  int **v39; // [rsp+98h] [rbp-8D0h]
  unsigned int *v40; // [rsp+A0h] [rbp-8C8h]
  const WCHAR *v41; // [rsp+A8h] [rbp-8C0h]
  unsigned int **v42; // [rsp+B0h] [rbp-8B8h]
  void **v43; // [rsp+B8h] [rbp-8B0h] BYREF
  const WCHAR *v44; // [rsp+C0h] [rbp-8A8h]
  __int64 v45; // [rsp+C8h] [rbp-8A0h]
  unsigned int v46; // [rsp+D0h] [rbp-898h]
  __int64 v47; // [rsp+D8h] [rbp-890h]
  __int64 v48; // [rsp+E0h] [rbp-888h]
  int v49; // [rsp+E8h] [rbp-880h]
  _OWORD *v50; // [rsp+F0h] [rbp-878h]
  void *v51; // [rsp+F8h] [rbp-870h]
  void *v52; // [rsp+100h] [rbp-868h]
  wchar_t *v53; // [rsp+108h] [rbp-860h]
  _DWORD *v54; // [rsp+110h] [rbp-858h]
  __int128 v55; // [rsp+118h] [rbp-850h] BYREF
  wchar_t *Str[2]; // [rsp+128h] [rbp-840h] BYREF
  __int128 v57; // [rsp+138h] [rbp-830h]
  __int64 v58; // [rsp+148h] [rbp-820h]
  wchar_t v59[1000]; // [rsp+150h] [rbp-818h] BYREF

  v35 = a4;
  lpString2 = a3;
  v28 = a2;
  v33 = a2;
  v41 = a3;
  v31 = (unsigned __int64)a4;
  v36 = a5;
  v37 = a6;
  v38 = a7;
  v39 = a8;
  v42 = a9;
  v40 = a10;
  v10 = g_pInSeqHash;
  v34 = g_pInSeqHash;
  v43 = &CList<_TA_ADDRESS const *,_TA_ADDRESS const *>::`vftable';
  v46 = 0;
  v47 = 0;
  v45 = 0;
  v44 = 0;
  v48 = 0;
  v49 = 10;
  v32 = (CInSeqHash *)((char *)g_pInSeqHash + 8);
  CReadWriteLock::LockRead((CInSeqHash *)((char *)g_pInSeqHash + 8));
  Block = (void *)-(__int64)(*((_DWORD *)v10 + 13) != 0);
  while ( 1 )
  {
    v11 = Block;
    if ( !Block )
      break;
    *(_OWORD *)Str = 0;
    v57 = 0;
    v58 = 0;
    v55 = 0;
    LOWORD(Str[0]) = 0;
    *(_QWORD *)v26 = 0;
    CMap<CKeyInSeq,CKeyInSeq &,R<CInSequence>,R<CInSequence> &>::GetNextAssoc((char *)v10 + 32, &Block, &v55, v26);
    LOBYTE(v12) = operator==((PCNZWCH *)Str, (PCNZWCH *)v28);
    if ( v12 )
    {
      CList<__POSITION *,__POSITION *>::AddTail(&v43, v11);
LABEL_5:
      v13 = *(CReference **)v26;
      goto LABEL_6;
    }
    if ( LOBYTE(Str[0]) != 3 )
      goto LABEL_5;
    v14 = 0;
    v27 = 0;
    v13 = *(CReference **)v26;
    if ( *(_DWORD *)(*(_QWORD *)v26 + 216LL) != 1 )
    {
      try
      {
        FnDirectIDToLocalPathName(Str[1], (wchar_t *)L".");
      }
      catch ( exception )
      {
        free(v27);
        SafeRelease<CSockTransport>(*(CReference **)v26);
        CKeyInSeq::~CKeyInSeq((CKeyInSeq *)&v55);
        v10 = v34;
        v28 = v33;
        lpString2 = v41;
        v35 = (struct _GUID **)v31;
        continue;
      }
      v14 = v27;
      v15 = wcschr(v27, 0x5Cu);
      if ( v15 )
      {
LABEL_19:
        if ( CompareStringW(0x7Fu, 1u, v15 + 1, -1, lpString2, -1) == 2 )
          CList<__POSITION *,__POSITION *>::AddTail(&v43, v11);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 42));
      }
      free(v14);
      goto LABEL_6;
    }
    v15 = wcschr(Str[1], 0x5Cu);
    if ( v15 )
      goto LABEL_19;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 42));
    free(0);
LABEL_6:
    SafeRelease<CSockTransport>(v13);
    CKeyInSeq::~CKeyInSeq((CKeyInSeq *)&v55);
  }
  if ( v46 )
  {
    v16 = v46;
    v17 = MmAllocate(saturated_mul(v46, 0x10u));
    v50 = v17;
    v28 = MmAllocate(saturated_mul(v16, 8u));
    v51 = v28;
    Block = MmAllocate(saturated_mul(v16, 4u));
    v52 = Block;
    v18 = (CInSeqHash *)MmAllocate(saturated_mul(v16, 8u));
    v34 = v18;
    v27 = (wchar_t *)MmAllocate(saturated_mul(v16, 4u));
    v53 = v27;
    v19 = MmAllocate(saturated_mul(v16, 4u));
    v54 = v19;
    v20 = 0;
    LODWORD(lpString2) = 0;
    for ( i = v44; i; i = v41 )
    {
      v41 = *(const WCHAR **)i;
      v31 = *((_QWORD *)i + 2);
      *(_OWORD *)Str = 0;
      v57 = 0;
      v58 = 0;
      v55 = 0;
      LOWORD(Str[0]) = 0;
      v33 = 0;
      CMap<CKeyInSeq,CKeyInSeq &,R<CInSequence>,R<CInSequence> &>::GetNextAssoc((char *)v10 + 32, &v31, &v55, &v33);
      v17[v20] = v55;
      v22 = v33;
      *((_QWORD *)v28 + v20) = *((_QWORD *)v33 + 16);
      *((_DWORD *)Block + v20) = *((_DWORD *)v22 + 34);
      *(_DWORD *)&v27[2 * v20] = *((_DWORD *)v22 + 50);
      v19[v20] = *((_DWORD *)v22 + 64);
      v26[0] = 0;
      v23 = MQpQueueFormatToFormatName((const struct QUEUE_FORMAT *)Str, v59, 0x3E8u, v26, 0);
      if ( v23 < 0 )
        LogMsgHR(v23, (wchar_t *)L"xactin", 0xAEu);
      if ( v26[0] + 1 < v26[0] )
      {
        LogMsgHR(-2147024362, (wchar_t *)L"xactin", 0xAFu);
        SafeRelease<CSockTransport>(v22);
        CKeyInSeq::~CKeyInSeq((CKeyInSeq *)&v55);
        free(v19);
        free(v27);
        free(v18);
        free(Block);
        free(v28);
        free(v17);
        CSR::~CSR(&v32);
        CList<wchar_t const *,wchar_t const *>::~CList<wchar_t const *,wchar_t const *>(&v43);
        return;
      }
      v31 = v26[0] + 1;
      v24 = (wchar_t *)MmAllocate(saturated_mul(v31, 2u));
      *((_QWORD *)v18 + v20) = v24;
      v25 = StringCchCopyW(v24, v31, v59);
      if ( v25 < 0 )
      {
        LogMsgHR(v25, (wchar_t *)L"xactin", 0x13Du);
        SafeRelease<CSockTransport>(v22);
        CKeyInSeq::~CKeyInSeq((CKeyInSeq *)&v55);
        free(v19);
        free(v27);
        free(v18);
        free(Block);
        free(v28);
        free(v17);
        CSR::~CSR(&v32);
        CList<wchar_t const *,wchar_t const *>::~CList<wchar_t const *,wchar_t const *>(&v43);
        return;
      }
      v20 = (unsigned int)((_DWORD)lpString2 + 1);
      LODWORD(lpString2) = (_DWORD)lpString2 + 1;
      SafeRelease<CSockTransport>(v22);
      CKeyInSeq::~CKeyInSeq((CKeyInSeq *)&v55);
    }
    v50 = 0;
    *v35 = (struct _GUID *)v17;
    v51 = 0;
    *v36 = (union _ULARGE_INTEGER *)v28;
    v52 = 0;
    *v37 = (unsigned int *)Block;
    v34 = 0;
    *v38 = (wchar_t **)v18;
    v53 = 0;
    *v39 = (int *)v27;
    *v42 = v19;
    *v40 = v46;
    free(0);
    free(0);
    free(0);
    free(0);
    free(0);
    free(0);
  }
  else
  {
    *v35 = 0;
    *v36 = 0;
    *v37 = 0;
    *v38 = 0;
    *v39 = 0;
    *v40 = 0;
  }
  CSR::~CSR(&v32);
  CList<wchar_t const *,wchar_t const *>::~CList<wchar_t const *,wchar_t const *>(&v43);
}

```

## disassembly

```asm
0x180066148  mov     r11, rsp
0x18006614b  push    rbx
0x18006614c  push    rsi
0x18006614d  push    rdi
0x18006614e  push    r12
0x180066150  push    r13
0x180066152  push    r14
0x180066154  push    r15
0x180066156  sub     rsp, 930h
0x18006615d  mov     rax, cs:__security_cookie
0x180066164  xor     rax, rsp
0x180066167  mov     [rsp+968h+var_48], rax
0x18006616f  mov     rbx, r9
0x180066172  mov     [rsp+968h+var_8F0], rbx
0x180066177  mov     [rsp+968h+var_918], r8
0x18006617c  mov     [rsp+968h+var_928], rdx
0x180066181  mov     [rsp+968h+var_900], rdx
0x180066186  mov     [rsp+968h+var_8C0], r8
0x18006618e  mov     [rsp+968h+var_910], rbx
0x180066193  mov     rbx, [rsp+968h+arg_20]
0x18006619b  mov     [rsp+968h+var_8E8], rbx
0x1800661a3  mov     rbx, [rsp+968h+arg_28]
0x1800661ab  mov     [rsp+968h+var_8E0], rbx
0x1800661b3  mov     rbx, [rsp+968h+arg_30]
0x1800661bb  mov     [rsp+968h+var_8D8], rbx
0x1800661c3  mov     rbx, [rsp+968h+arg_38]
0x1800661cb  mov     [rsp+968h+var_8D0], rbx
0x1800661d3  mov     r14, [rsp+968h+arg_40]
0x1800661db  mov     [rsp+968h+var_8B8], r14
0x1800661e3  mov     rbx, [rsp+968h+arg_48]
0x1800661eb  mov     [rsp+968h+var_8C8], rbx
0x1800661f3  mov     r15, cs:?g_pInSeqHash@@3PEAVCInSeqHash@@EA; CInSeqHash * g_pInSeqHash
0x1800661fa  mov     [rsp+968h+var_8F8], r15
0x1800661ff  lea     rax, ??_7?$CList@PEBU_TA_ADDRESS@@PEBU1@@@6B@; const CList<_TA_ADDRESS const *,_TA_ADDRESS const *>::`vftable'
0x180066206  mov     [r11-8B0h], rax
0x18006620d  xor     esi, esi
0x18006620f  mov     [rsp+968h+var_898], esi
0x180066216  mov     [r11-890h], rsi
0x18006621d  mov     [r11-8A0h], rsi
0x180066224  mov     [r11-8A8h], rsi
0x18006622b  mov     [r11-888h], rsi
0x180066232  mov     [rsp+968h+var_880], 0Ah
0x18006623d  lea     rcx, [r15+8]; this
0x180066241  mov     [rsp+968h+var_908], rcx
0x180066246  call    ?LockRead@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockRead(void)
0x18006624b  nop
0x18006624c  mov     eax, [r15+34h]
0x180066250  neg     eax
0x180066252  sbb     rcx, rcx
0x180066255  mov     [rsp+968h+Block], rcx
0x18006625a  lea     r13, WPP_GLOBAL_Control
0x180066261  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180066265  mov     r12, [rsp+968h+Block]
0x18006626a  test    r12, r12
0x18006626d  jz      loc_1800664A2
0x180066273  xorps   xmm0, xmm0
0x180066276  movups  xmmword ptr [rsp+968h+Str], xmm0
0x18006627e  movups  [rsp+968h+var_830], xmm0
0x180066286  mov     [rsp+968h+var_820], rsi
0x18006628e  movups  [rsp+968h+var_850], xmm0
0x180066296  mov     word ptr [rsp+968h+Str], 0
0x1800662a0  mov     qword ptr [rsp+968h+var_938], rsi
0x1800662a5  lea     rcx, [r15+20h]
0x1800662a9  lea     r9, [rsp+968h+var_938]
0x1800662ae  lea     r8, [rsp+968h+var_850]
0x1800662b6  lea     rdx, [rsp+968h+Block]
0x1800662bb  call    ?GetNextAssoc@?$CMap@VCKeyInSeq@@AEAV1@V?$R@VCInSequence@@@@AEAV2@@@QEBAXAEAPEAU__POSITION@@AEAVCKeyInSeq@@AEAV?$R@VCInSequence@@@@@Z; CMap<CKeyInSeq,CKeyInSeq &,R<CInSequence>,R<CInSequence> &>::GetNextAssoc(__POSITION * &,CKeyInSeq &,R<CInSequence> &)
0x1800662c0  mov     rdx, [rsp+968h+var_928]
0x1800662c5  lea     rcx, [rsp+968h+Str]
0x1800662cd  call    ??8@YAHAEBUQUEUE_FORMAT@@0@Z; operator==(QUEUE_FORMAT const &,QUEUE_FORMAT const &)
0x1800662d2  test    eax, eax
0x1800662d4  jz      short loc_180066306
0x1800662d6  mov     rdx, r12
0x1800662d9  lea     rcx, [rsp+968h+var_8B0]
0x1800662e1  call    ?AddTail@?$CList@PEAU__POSITION@@PEAU1@@@QEAAPEAU__POSITION@@PEAU2@@Z; CList<__POSITION *,__POSITION *>::AddTail(__POSITION *)
0x1800662e6  mov     rbx, qword ptr [rsp+968h+var_938]
0x1800662eb  mov     rcx, rbx
0x1800662ee  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x1800662f3  nop
0x1800662f4  lea     rcx, [rsp+968h+var_850]; this
0x1800662fc  call    ??1CKeyInSeq@@QEAA@XZ; CKeyInSeq::~CKeyInSeq(void)
0x180066301  jmp     loc_180066265
0x180066306  cmp     byte ptr [rsp+968h+Str], 3
0x18006630e  jnz     short loc_1800662E6
0x180066310  mov     r14, [rsp+968h+Str+8]
0x180066318  mov     rdi, rsi
0x18006631b  mov     [rsp+968h+var_930], rsi
0x180066320  mov     rbx, qword ptr [rsp+968h+var_938]
0x180066325  cmp     dword ptr [rbx+0D8h], 1
0x18006632c  jnz     short loc_180066398
0x18006632e  mov     edx, 5Ch ; '\'; Ch
0x180066333  mov     rcx, r14; Str
0x180066336  call    cs:__imp_wcschr
0x18006633c  test    rax, rax
0x18006633f  jnz     loc_180066403
0x180066345  mov     rcx, cs:WPP_GLOBAL_Control
0x18006634c  cmp     rcx, r13
0x18006634f  jz      short loc_180066374
0x180066351  test    byte ptr [rcx+15Ch], 1
0x180066358  jz      short loc_180066374
0x18006635a  lea     edx, [rax+35h]
0x18006635d  mov     r9, r14
0x180066360  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180066367  mov     rcx, [rcx+150h]; LoggerHandle
0x18006636e  call    WPP_SF_S
0x180066373  nop
0x180066374  xor     ecx, ecx; Block
0x180066376  call    cs:__imp_free
0x18006637c  nop
0x18006637d  mov     rcx, rbx
0x180066380  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180066385  nop
0x180066386  lea     rcx, [rsp+968h+var_850]; this
0x18006638e  call    ??1CKeyInSeq@@QEAA@XZ; CKeyInSeq::~CKeyInSeq(void)
0x180066393  jmp     loc_180066261
0x180066398  lea     r8, [rsp+968h+var_930]
0x18006639d  lea     rdx, asc_1801038C8; "."
0x1800663a4  mov     rcx, r14; wchar_t *
0x1800663a7  call    ?FnDirectIDToLocalPathName@@YAXPEB_W0AEAV?$AP@_W@@@Z; FnDirectIDToLocalPathName(wchar_t const *,wchar_t const *,AP<wchar_t> &)
0x1800663ac  nop
0x1800663ad  mov     edx, 5Ch ; '\'; Ch
0x1800663b2  mov     rdi, [rsp+968h+var_930]
0x1800663b7  mov     rcx, rdi; Str
0x1800663ba  call    cs:__imp_wcschr
0x1800663c0  test    rax, rax
0x1800663c3  jnz     short loc_180066403
0x1800663c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800663cc  cmp     rcx, r13
0x1800663cf  jz      short loc_1800663F4
0x1800663d1  test    byte ptr [rcx+15Ch], 1
0x1800663d8  jz      short loc_1800663F4
0x1800663da  lea     edx, [rax+36h]
0x1800663dd  mov     r9, rdi
0x1800663e0  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x1800663e7  mov     rcx, [rcx+150h]; LoggerHandle
0x1800663ee  call    WPP_SF_S
0x1800663f3  nop
0x1800663f4  mov     rcx, rdi; Block
0x1800663f7  call    cs:__imp_free
0x1800663fd  nop
0x1800663fe  jmp     loc_18006637D
0x180066403  lea     r8, [rax+2]; lpString1
0x180066407  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006640b  mov     [rsp+968h+cchCount2], eax; cchCount2
0x18006640f  mov     rcx, [rsp+968h+var_918]
0x180066414  mov     [rsp+968h+lpString2], rcx; lpString2
0x180066419  mov     r9d, eax; cchCount1
0x18006641c  lea     edx, [rax+2]; dwCmpFlags
0x18006641f  lea     ecx, [rdx+7Eh]; Locale
0x180066422  call    cs:__imp_CompareStringW
0x180066428  cmp     eax, 2
0x18006642b  jnz     short loc_18006643E
0x18006642d  mov     rdx, r12
0x180066430  lea     rcx, [rsp+968h+var_8B0]
0x180066438  call    ?AddTail@?$CList@PEAU__POSITION@@PEAU1@@@QEAAPEAU__POSITION@@PEAU2@@Z; CList<__POSITION *,__POSITION *>::AddTail(__POSITION *)
0x18006643d  nop
0x18006643e  mov     rcx, rdi; Block
0x180066441  call    cs:__imp_free
0x180066447  nop
0x180066448  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006644c  jmp     loc_1800662EB
0x180066451  mov     rcx, [rsp+968h+var_930]; Block
0x180066456  call    cs:__imp_free
0x18006645c  nop
0x18006645d  mov     rcx, qword ptr [rsp+968h+var_938]
0x180066462  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180066467  nop
0x180066468  lea     rcx, [rsp+968h+var_850]; this
0x180066470  call    ??1CKeyInSeq@@QEAA@XZ; CKeyInSeq::~CKeyInSeq(void)
0x180066475  xor     esi, esi
0x180066477  mov     r15, [rsp+968h+var_8F8]
0x18006647c  mov     rax, [rsp+968h+var_900]
0x180066481  mov     [rsp+968h+var_928], rax
0x180066486  mov     rax, [rsp+968h+var_8C0]
0x18006648e  mov     [rsp+968h+var_918], rax
0x180066493  mov     rax, [rsp+968h+var_910]
0x180066498  mov     [rsp+968h+var_8F0], rax
0x18006649d  jmp     loc_18006625A
0x1800664a2  mov     eax, [rsp+968h+var_898]
0x1800664a9  test    eax, eax
0x1800664ab  jnz     short loc_180066526
0x1800664ad  mov     rax, [rsp+968h+var_8F0]
0x1800664b2  mov     [rax], rsi
0x1800664b5  mov     rcx, [rsp+968h+var_8E8]
0x1800664bd  mov     [rcx], rsi
0x1800664c0  mov     rcx, [rsp+968h+var_8E0]
0x1800664c8  mov     [rcx], rsi
0x1800664cb  mov     rax, [rsp+968h+var_8D8]
0x1800664d3  mov     [rax], rsi
0x1800664d6  mov     rcx, [rsp+968h+var_8D0]
0x1800664de  mov     [rcx], rsi
0x1800664e1  mov     rax, [rsp+968h+var_8C8]
0x1800664e9  mov     [rax], esi
0x1800664eb  lea     rcx, [rsp+968h+var_908]; this
0x1800664f0  call    ??1CSR@@QEAA@XZ; CSR::~CSR(void)
0x1800664f5  nop
0x1800664f6  lea     rcx, [rsp+968h+var_8B0]
0x1800664fe  call    ??1?$CList@PEB_WPEB_W@@UEAA@XZ; CList<wchar_t const *,wchar_t const *>::~CList<wchar_t const *,wchar_t const *>(void)
0x180066503  mov     rcx, [rsp+968h+var_48]
0x18006650b  xor     rcx, rsp; StackCookie
0x18006650e  call    __security_check_cookie
0x180066513  add     rsp, 930h
0x18006651a  pop     r15
0x18006651c  pop     r14
0x18006651e  pop     r13
0x180066520  pop     r12
0x180066522  pop     rdi
0x180066523  pop     rsi
0x180066524  pop     rbx
0x180066525  retn
0x180066526  mov     rbx, rax
0x180066529  mov     eax, 10h
0x18006652e  mul     rbx
0x180066531  cmovb   rax, rdi
0x180066535  mov     rcx, rax; unsigned __int64
0x180066538  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18006653d  mov     r13, rax
0x180066540  mov     [rsp+968h+var_878], rax
0x180066548  mov     r12d, 8
0x18006654e  mov     eax, r12d
0x180066551  mul     rbx
0x180066554  cmovb   rax, rdi
0x180066558  mov     rcx, rax; unsigned __int64
0x18006655b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180066560  mov     [rsp+968h+var_928], rax
0x180066565  mov     [rsp+968h+var_870], rax
0x18006656d  lea     r14d, [r12-4]
0x180066572  mov     eax, r14d
0x180066575  mul     rbx
0x180066578  cmovb   rax, rdi
0x18006657c  mov     rcx, rax; unsigned __int64
0x18006657f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180066584  mov     [rsp+968h+Block], rax
0x180066589  mov     [rsp+968h+var_868], rax
0x180066591  mov     eax, r12d
0x180066594  mul     rbx
0x180066597  cmovb   rax, rdi
0x18006659b  mov     rcx, rax; unsigned __int64
0x18006659e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800665a3  mov     r12, rax
0x1800665a6  mov     [rsp+968h+var_8F8], rax
0x1800665ab  mov     eax, r14d
0x1800665ae  mul     rbx
0x1800665b1  cmovb   rax, rdi
0x1800665b5  mov     rcx, rax; unsigned __int64
0x1800665b8  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800665bd  mov     [rsp+968h+var_930], rax
0x1800665c2  mov     [rsp+968h+var_860], rax
0x1800665ca  mov     eax, r14d
0x1800665cd  mul     rbx
0x1800665d0  cmovb   rax, rdi
0x1800665d4  mov     rcx, rax; unsigned __int64
0x1800665d7  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800665dc  mov     rdi, rax
0x1800665df  mov     [rsp+968h+var_858], rax
0x1800665e7  mov     r14d, esi
0x1800665ea  mov     dword ptr [rsp+968h+var_918], r14d
0x1800665ef  mov     rax, [rsp+968h+var_8A8]
0x1800665f7  test    rax, rax
0x1800665fa  jz      loc_18006688D
0x180066600  mov     rcx, [rax]
0x180066603  mov     [rsp+968h+var_8C0], rcx
0x18006660b  mov     rax, [rax+10h]
0x18006660f  mov     [rsp+968h+var_910], rax
0x180066614  xorps   xmm0, xmm0
0x180066617  movups  xmmword ptr [rsp+968h+Str], xmm0
0x18006661f  movups  [rsp+968h+var_830], xmm0
0x180066627  mov     [rsp+968h+var_820], rsi
0x18006662f  movups  [rsp+968h+var_850], xmm0
0x180066637  mov     word ptr [rsp+968h+Str], 0
0x180066641  mov     [rsp+968h+var_900], rsi
0x180066646  lea     rcx, [r15+20h]
0x18006664a  lea     r9, [rsp+968h+var_900]
0x18006664f  lea     r8, [rsp+968h+var_850]
0x180066657  lea     rdx, [rsp+968h+var_910]
0x18006665c  call    ?GetNextAssoc@?$CMap@VCKeyInSeq@@AEAV1@V?$R@VCInSequence@@@@AEAV2@@@QEBAXAEAPEAU__POSITION@@AEAVCKeyInSeq@@AEAV?$R@VCInSequence@@@@@Z; CMap<CKeyInSeq,CKeyInSeq &,R<CInSequence>,R<CInSequence> &>::GetNextAssoc(__POSITION * &,CKeyInSeq &,R<CInSequence> &)
0x180066661  movups  xmm0, [rsp+968h+var_850]
0x180066669  mov     rax, r14
0x18006666c  add     rax, rax
0x18006666f  movdqu  xmmword ptr [r13+rax*8+0], xmm0
0x180066676  mov     rbx, [rsp+968h+var_900]
0x18006667b  mov     rax, [rbx+80h]
0x180066682  mov     rcx, [rsp+968h+var_928]
0x180066687  mov     [rcx+r14*8], rax
0x18006668b  mov     eax, [rbx+88h]
0x180066691  mov     rcx, [rsp+968h+Block]
0x180066696  mov     [rcx+r14*4], eax
0x18006669a  mov     eax, [rbx+0C8h]
0x1800666a0  mov     rcx, [rsp+968h+var_930]
0x1800666a5  mov     [rcx+r14*4], eax
0x1800666a9  mov     eax, [rbx+100h]
0x1800666af  mov     [rdi+r14*4], eax
0x1800666b3  mov     [rsp+968h+var_938], esi
0x1800666b7  mov     byte ptr [rsp+968h+lpString2], sil; bool
0x1800666bc  lea     r9, [rsp+968h+var_938]; unsigned int *
0x1800666c1  mov     r8d, 3E8h; unsigned int
0x1800666c7  lea     rdx, [rsp+968h+var_818]; wchar_t *
0x1800666cf  lea     rcx, [rsp+968h+Str]; struct QUEUE_FORMAT *
0x1800666d7  call    ?MQpQueueFormatToFormatName@@YAJPEBUQUEUE_FORMAT@@PEA_WKPEAK_N@Z; MQpQueueFormatToFormatName(QUEUE_FORMAT const *,wchar_t *,ulong,ulong *,bool)
0x1800666dc  test    eax, eax
  ... truncated ...
```
