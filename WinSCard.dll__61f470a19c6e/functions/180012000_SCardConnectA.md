# SCardConnectA

- ea: `0x180012000`
- end: `0x180012478`
- name: `SCardConnectA`
- size: `1144`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCSTR szReader, DWORD dwShareMode, DWORD dwPreferredProtocols, LPSCARDHANDLE phCard, LPDWORD pdwActiveProtocol)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005a90`
- `0x180008f70`
- `0x18000d640`
- `0x18000dab0`
- `0x18000e090`
- `0x18000e680`
- `0x180012000`
- `0x180012480`
- `0x180012650`
- `0x1800153a0`
- `0x1800170f8`
- `0x18001b9b8`
- `0x18001b9c4`
- `0x18002ef20`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012056`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012056`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800120ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800120ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LONG __stdcall SCardConnectA(
        SCARDCONTEXT hContext,
        LPCSTR szReader,
        DWORD dwShareMode,
        DWORD dwPreferredProtocols,
        LPSCARDHANDLE phCard,
        LPDWORD pdwActiveProtocol)
{
  LONG v8; // esi
  CHandleList *v9; // rdi
  struct _RTL_CRITICAL_SECTION *v10; // r14
  SCARDCONTEXT v11; // rdi
  __int64 v12; // rdi
  int v13; // eax
  char *v14; // rbx
  __int64 v15; // r14
  __int64 v16; // r13
  unsigned __int64 v17; // rdi
  struct CSCardSubcontext *v18; // rdi
  const unsigned __int16 *v19; // rdx
  struct CBuffer *v20; // r8
  const WCHAR *v21; // r9
  void *v22; // r14
  ulong v23; // eax
  int v25; // [rsp+30h] [rbp-D8h]
  int v26; // [rsp+38h] [rbp-D0h]
  int v27; // [rsp+40h] [rbp-C8h]
  int pExceptionObject; // [rsp+50h] [rbp-B8h] BYREF
  ulong v29; // [rsp+54h] [rbp-B4h] BYREF
  ulong v30; // [rsp+58h] [rbp-B0h] BYREF
  ulong v31; // [rsp+5Ch] [rbp-ACh] BYREF
  ulong v32; // [rsp+60h] [rbp-A8h] BYREF
  ulong v33; // [rsp+64h] [rbp-A4h] BYREF
  ulong v34; // [rsp+68h] [rbp-A0h] BYREF
  void (__fastcall ***v35)(_QWORD, __int64); // [rsp+70h] [rbp-98h]
  const int *v36; // [rsp+78h] [rbp-90h] BYREF
  void *v37; // [rsp+80h] [rbp-88h]
  int v38; // [rsp+88h] [rbp-80h]
  int v39; // [rsp+8Ch] [rbp-7Ch]
  void **v40; // [rsp+90h] [rbp-78h] BYREF
  int v41; // [rsp+98h] [rbp-70h]
  const int *v42; // [rsp+A0h] [rbp-68h]
  __int64 v43; // [rsp+A8h] [rbp-60h]
  int v44; // [rsp+B0h] [rbp-58h]
  int v45; // [rsp+B4h] [rbp-54h]
  _QWORD v46[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v47; // [rsp+C8h] [rbp-40h]
  int v48; // [rsp+CCh] [rbp-3Ch]
  LONG v49; // [rsp+D0h] [rbp-38h] BYREF
  char *v50; // [rsp+D8h] [rbp-30h]

  v8 = 0;
  v35 = 0;
  try
  {
    *phCard = 0;
    v9 = g_phlContexts;
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    v50 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    if ( HIBYTE(hContext) != *((_BYTE *)v9 + 8)
      || *((_DWORD *)v9 + 4) <= (hContext & 0x7FFFFFFF)
      || (v11 = 16 * (hContext & 0x7FFFFFFF) + *((_QWORD *)v9 + 3),
          ((*(_DWORD *)(v11 + 8) ^ HIDWORD(hContext)) & 0xFFFFFF) != 0)
      || !v11 )
    {
      v34 = 6;
      throw &v34;
    }
    v12 = *(_QWORD *)v11;
    LeaveCriticalSection(v10);
    v40 = &CTextString::`vftable';
    v42 = &CBuffer::`vftable';
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46[0] = &CBuffer::`vftable';
    v46[1] = 0;
    v47 = 0;
    v48 = 0;
    v41 = 3;
    if ( *(_DWORD *)(v12 + 16) )
    {
      pExceptionObject = -2146435042;
      throw (ulong *)&pExceptionObject;
    }
    if ( szReader )
    {
      v13 = ((__int64 (__fastcall *)(void ***, LPCSTR))v40[2])(&v40, szReader);
      CBuffer::Set((CBuffer *)v46, (const unsigned __int8 *const)szReader, v13 + 1);
    }
    else
    {
      v47 = 0;
    }
    v41 = 1;
    v14 = (char *)operator new(0x30u);
    v50 = v14;
    if ( v14 )
    {
      *(_QWORD *)v14 = &CHandle::`vftable';
      *((_DWORD *)v14 + 2) = 0;
      *((_DWORD *)v14 + 3) = 0x7FFFFFFF;
      *((_DWORD *)v14 + 4) = 0;
      *(_QWORD *)v14 = &CReaderContext::`vftable';
      *((_DWORD *)v14 + 9) = 0;
      *((_QWORD *)v14 + 3) = 0;
      *((_DWORD *)v14 + 8) = -1;
      *((_QWORD *)v14 + 5) = 0;
    }
    else
    {
      v14 = 0;
    }
    v35 = (void (__fastcall ***)(_QWORD, __int64))v14;
    if ( !v14 )
    {
      v29 = -2146435066;
      throw &v29;
    }
    v15 = *(_QWORD *)(v12 + 128);
    v16 = *(_QWORD *)(v12 + 136);
    if ( v15 )
    {
      v17 = CHandleList::Add(g_phlReaders, (struct CHandle *)v14, *(_DWORD *)(v16 + 72));
      v8 = I_SCardConnect(
             v15,
             (const unsigned __int8 *)szReader,
             dwShareMode,
             dwPreferredProtocols,
             phCard,
             pdwActiveProtocol,
             0);
      if ( v8 )
      {
        CHandleList::Close(g_phlReaders, v17);
        (**(void (__fastcall ***)(void *, __int64))v14)(v14, 1);
      }
      else
      {
        *((_QWORD *)v14 + 5) = *phCard;
        *phCard = v17;
      }
    }
    else
    {
      v18 = CSCardUserContext::AcquireSubcontext((CSCardUserContext *)v12, 1);
      if ( !v18 )
      {
        v30 = -2146435066;
        throw &v30;
      }
      v19 = CTextString::Unicode((CTextString *)&v40);
      v36 = &CBuffer::`vftable';
      v37 = 0;
      v38 = 0;
      v39 = 0;
      if ( !*v19 )
      {
        v31 = -2146435063;
        throw &v31;
      }
      if ( !(unsigned int)GetReaderInfo(*(_DWORD *)(*((_QWORD *)v18 + 5) + 28LL), v19, v20, (const void **)&v36) )
      {
        v32 = -2146435063;
        throw &v32;
      }
      v21 = &WideCharStr;
      v22 = v37;
      if ( v39 )
        LODWORD(v21) = (_DWORD)v37;
      v23 = CalRpcConnect(
              *((_QWORD *)v18 + 14),
              dwPreferredProtocols,
              dwShareMode,
              (int)v21,
              (__int64)(v14 + 32),
              (__int64)(v14 + 36),
              v25,
              v26,
              v27,
              (int)v18,
              pExceptionObject);
      if ( v23 )
      {
        v33 = v23;
        throw &v33;
      }
      *((_QWORD *)v14 + 3) = v18;
      v36 = &CBuffer::`vftable';
      if ( v22 )
        operator delete(v22);
      v37 = 0;
      v38 = 0;
      v39 = 0;
      CSCardSubcontext::ReleaseSubcontext(*((CSCardSubcontext **)v14 + 3));
      if ( pdwActiveProtocol )
        *pdwActiveProtocol = *((_DWORD *)v14 + 9);
      *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL) = CHandleList::Add(
                                                  g_phlReaders,
                                                  (struct CHandle *)v14,
                                                  *(_DWORD *)(v16 + 72));
      *phCard = *(_QWORD *)(*((_QWORD *)v14 + 3) + 8LL);
    }
    CTextString::~CTextString((CTextString *)&v40);
  }
  catch ( ulong v49 )
  {
    if ( v35 )
      (**v35)(v35, 1);
    return v49;
  }
  catch ( ... )
  {
    if ( v35 )
      (**v35)(v35, 1);
    return -2146435068;
  }
  return v8;
}

```

## disassembly

```asm
0x180012000  mov     rax, rsp
0x180012003  mov     [rax+8], rbx
0x180012007  mov     [rax+10h], rsi
0x18001200b  mov     [rax+20h], r9d
0x18001200f  mov     [rax+18h], r8d
0x180012013  push    rdi
0x180012014  push    r12
0x180012016  push    r13
0x180012018  push    r14
0x18001201a  push    r15
0x18001201c  sub     rsp, 0E0h
0x180012023  mov     r12, rdx
0x180012026  mov     rbx, rcx
0x180012029  xor     r13d, r13d
0x18001202c  mov     esi, r13d
0x18001202f  mov     [rsp+108h+var_98], r13
0x180012034  mov     qword ptr [rsp+108h+var_C0], r13
0x180012039  mov     r15, [rsp+108h+phCard]
0x180012041  mov     [r15], r13
0x180012044  mov     rdi, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18001204b  lea     r14, [rdi+20h]
0x18001204f  mov     [rax-30h], r14
0x180012053  mov     rcx, r14; lpCriticalSection
0x180012056  call    cs:__imp_EnterCriticalSection
0x18001205c  nop
0x18001205d  mov     rax, rbx
0x180012060  shr     rax, 38h
0x180012064  cmp     al, [rdi+8]
0x180012067  jnz     loc_180012439
0x18001206d  mov     eax, ebx
0x18001206f  btr     eax, 1Fh
0x180012073  cmp     [rdi+10h], eax
0x180012076  jbe     loc_180012439
0x18001207c  mov     edx, eax
0x18001207e  shl     rdx, 4
0x180012082  mov     rdi, [rdi+18h]
0x180012086  add     rdi, rdx
0x180012089  shr     rbx, 20h
0x18001208d  xor     ebx, [rdi+8]
0x180012090  test    ebx, 0FFFFFFh
0x180012096  jnz     loc_180012439
0x18001209c  test    rdi, rdi
0x18001209f  jz      loc_180012439
0x1800120a5  mov     rdi, [rdi]
0x1800120a8  mov     rcx, r14; lpCriticalSection
0x1800120ab  call    cs:__imp_LeaveCriticalSection
0x1800120b1  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x1800120b8  mov     [rsp+108h+var_78], rax
0x1800120c0  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800120c7  mov     [rsp+108h+var_68], rax
0x1800120cf  mov     [rsp+108h+var_60], r13
0x1800120d7  mov     [rsp+108h+var_58], r13d
0x1800120df  mov     [rsp+108h+var_54], r13d
0x1800120e7  mov     [rsp+108h+var_50], rax
0x1800120ef  mov     [rsp+108h+var_48], r13
0x1800120f7  mov     [rsp+108h+var_40], r13d
0x1800120ff  mov     [rsp+108h+var_3C], r13d
0x180012107  mov     [rsp+108h+var_70], 3
0x180012112  cmp     [rdi+10h], r13d
0x180012116  jz      short loc_180012131
0x180012118  mov     [rsp+108h+pExceptionObject], 8010001Eh
0x180012120  lea     rdx, _TI1K; pThrowInfo
0x180012127  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001212c  call    _CxxThrowException_0
0x180012131  test    r12, r12
0x180012134  jz      short loc_180012168
0x180012136  mov     rax, [rsp+108h+var_78]
0x18001213e  mov     rdx, r12
0x180012141  lea     rcx, [rsp+108h+var_78]
0x180012149  mov     rax, [rax+10h]
0x18001214d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012152  lea     r8d, [rax+1]; unsigned int
0x180012156  mov     rdx, r12; unsigned __int8 *
0x180012159  lea     rcx, [rsp+108h+var_50]; this
0x180012161  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x180012166  jmp     short loc_180012170
0x180012168  mov     [rsp+108h+var_40], r13d
0x180012170  mov     [rsp+108h+var_70], 1
0x18001217b  mov     ecx, 30h ; '0'; Size
0x180012180  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012185  mov     rbx, rax
0x180012188  mov     [rsp+108h+var_30], rax
0x180012190  test    rax, rax
0x180012193  jz      short loc_1800121CD
0x180012195  lea     rax, ??_7CHandle@@6B@; const CHandle::`vftable'
0x18001219c  mov     [rbx], rax
0x18001219f  mov     [rbx+8], r13d
0x1800121a3  mov     dword ptr [rbx+0Ch], 7FFFFFFFh
0x1800121aa  mov     [rbx+10h], r13d
0x1800121ae  lea     rax, ??_7CReaderContext@@6B@; const CReaderContext::`vftable'
0x1800121b5  mov     [rbx], rax
0x1800121b8  mov     [rbx+24h], r13d
0x1800121bc  mov     [rbx+18h], r13
0x1800121c0  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x1800121c7  mov     [rbx+28h], r13
0x1800121cb  jmp     short loc_1800121D0
0x1800121cd  mov     rbx, r13
0x1800121d0  mov     [rsp+108h+var_98], rbx
0x1800121d5  test    rbx, rbx
0x1800121d8  jnz     short loc_1800121F3
0x1800121da  mov     [rsp+108h+var_B4], 80100006h
0x1800121e2  lea     rdx, _TI1K; pThrowInfo
0x1800121e9  lea     rcx, [rsp+108h+var_B4]; pExceptionObject
0x1800121ee  call    _CxxThrowException_0
0x1800121f3  mov     r14, [rdi+80h]
0x1800121fa  mov     r13, [rdi+88h]
0x180012201  test    r14, r14
0x180012204  jz      loc_180012295
0x18001220a  mov     r8d, [r13+48h]; unsigned int
0x18001220e  mov     rdx, rbx; struct CHandle *
0x180012211  mov     rcx, cs:?g_phlReaders@@3PEAVCHandleList@@EA; this
0x180012218  call    ?Add@CHandleList@@QEAA_KPEAVCHandle@@K@Z; CHandleList::Add(CHandle *,ulong)
0x18001221d  mov     rdi, rax
0x180012220  mov     [rsp+108h+var_D8], 0; int
0x180012228  mov     rax, [rsp+108h+pdwActiveProtocol]
0x180012230  mov     [rsp+108h+var_E0], rax; unsigned int *
0x180012235  mov     [rsp+108h+var_E8], r15; unsigned __int64 *
0x18001223a  mov     r9d, [rsp+108h+arg_18]; unsigned int
0x180012242  mov     r8d, [rsp+108h+arg_10]; unsigned int
0x18001224a  mov     rdx, r12; unsigned __int8 *
0x18001224d  mov     rcx, r14; unsigned __int64
0x180012250  call    ?I_SCardConnect@@YAJ_KPEBEKKPEA_KPEAKH@Z; I_SCardConnect(unsigned __int64,uchar const *,ulong,ulong,unsigned __int64 *,ulong *,int)
0x180012255  mov     esi, eax
0x180012257  mov     [rsp+108h+var_C8], eax
0x18001225b  test    eax, eax
0x18001225d  jnz     short loc_18001226E
0x18001225f  mov     rax, [r15]
0x180012262  mov     [rbx+28h], rax
0x180012266  mov     [r15], rdi
0x180012269  jmp     loc_180012429
0x18001226e  mov     rdx, rdi; unsigned __int64
0x180012271  mov     rcx, cs:?g_phlReaders@@3PEAVCHandleList@@EA; this
0x180012278  call    ?Close@CHandleList@@QEAAPEAVCHandle@@_K@Z; CHandleList::Close(unsigned __int64)
0x18001227d  mov     rax, [rbx]
0x180012280  mov     edx, 1
0x180012285  mov     rcx, rbx
0x180012288  mov     rax, [rax]
0x18001228b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012290  jmp     loc_180012429
0x180012295  mov     edx, 1; int
0x18001229a  mov     rcx, rdi; this
0x18001229d  call    ?AcquireSubcontext@CSCardUserContext@@QEAAPEAVCSCardSubcontext@@H@Z; CSCardUserContext::AcquireSubcontext(int)
0x1800122a2  mov     rdi, rax
0x1800122a5  mov     qword ptr [rsp+108h+var_C0], rax; int
0x1800122aa  xor     r12d, r12d
0x1800122ad  test    rax, rax
0x1800122b0  jnz     short loc_1800122CB
0x1800122b2  mov     [rsp+108h+var_B0], 80100006h
0x1800122ba  lea     rdx, _TI1K; pThrowInfo
0x1800122c1  lea     rcx, [rsp+108h+var_B0]; pExceptionObject
0x1800122c6  call    _CxxThrowException_0
0x1800122cb  lea     rcx, [rsp+108h+var_78]; this
0x1800122d3  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x1800122d8  mov     rdx, rax; unsigned __int16 *
0x1800122db  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800122e2  mov     [rsp+108h+var_90], rax
0x1800122e7  mov     [rsp+108h+var_88], r12
0x1800122ef  mov     [rsp+108h+var_80], r12d
0x1800122f7  mov     [rsp+108h+var_7C], r12d
0x1800122ff  cmp     r12w, [rdx]
0x180012303  jnz     short loc_18001231E
0x180012305  mov     [rsp+108h+var_AC], 80100009h
0x18001230d  lea     rdx, _TI1K; pThrowInfo
0x180012314  lea     rcx, [rsp+108h+var_AC]; pExceptionObject
0x180012319  call    _CxxThrowException_0
0x18001231e  mov     rcx, [rdi+28h]
0x180012322  lea     r9, [rsp+108h+var_90]; struct CBuffer *
0x180012327  mov     ecx, [rcx+1Ch]; unsigned int
0x18001232a  call    ?GetReaderInfo@@YAHKPEBGPEAVCBuffer@@1@Z; GetReaderInfo(ulong,ushort const *,CBuffer *,CBuffer *)
0x18001232f  test    eax, eax
0x180012331  jnz     short loc_18001234C
0x180012333  mov     [rsp+108h+var_A8], 80100009h
0x18001233b  lea     rdx, _TI1K; pThrowInfo
0x180012342  lea     rcx, [rsp+108h+var_A8]; pExceptionObject
0x180012347  call    _CxxThrowException_0
0x18001234c  lea     r9, WideCharStr
0x180012353  mov     r14, [rsp+108h+var_88]
0x18001235b  cmp     [rsp+108h+var_7C], r12d
0x180012363  cmova   r9, r14; int
0x180012367  lea     r12, [rbx+24h]
0x18001236b  lea     rax, [rbx+20h]
0x18001236f  mov     [rsp+108h+var_E0], r12; __int64
0x180012374  mov     [rsp+108h+var_E8], rax; __int64
0x180012379  mov     r8d, [rsp+108h+arg_10]; int
0x180012381  mov     edx, [rsp+108h+arg_18]; int
0x180012388  mov     rcx, [rdi+70h]; int
0x18001238c  call    CalRpcConnect
0x180012391  test    eax, eax
0x180012393  jz      short loc_1800123AA
0x180012395  mov     [rsp+108h+var_A4], eax
0x180012399  lea     rdx, _TI1K; pThrowInfo
0x1800123a0  lea     rcx, [rsp+108h+var_A4]; pExceptionObject
0x1800123a5  call    _CxxThrowException_0
0x1800123aa  mov     [rbx+18h], rdi
0x1800123ae  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800123b5  mov     [rsp+108h+var_90], rax
0x1800123ba  xor     edi, edi
0x1800123bc  test    r14, r14
0x1800123bf  jz      short loc_1800123C9
0x1800123c1  mov     rcx, r14; void *
0x1800123c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800123c9  mov     [rsp+108h+var_88], rdi
0x1800123d1  mov     [rsp+108h+var_80], edi
0x1800123d8  mov     [rsp+108h+var_7C], edi
0x1800123df  mov     qword ptr [rsp+108h+var_C0], rdi
0x1800123e4  mov     rcx, [rbx+18h]; this
0x1800123e8  call    ?ReleaseSubcontext@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::ReleaseSubcontext(void)
0x1800123ed  mov     rcx, [rsp+108h+pdwActiveProtocol]
0x1800123f5  test    rcx, rcx
0x1800123f8  jz      short loc_180012400
0x1800123fa  mov     eax, [r12]
0x1800123fe  mov     [rcx], eax
0x180012400  mov     r8d, [r13+48h]; unsigned int
0x180012404  mov     rdx, rbx; struct CHandle *
0x180012407  mov     rcx, cs:?g_phlReaders@@3PEAVCHandleList@@EA; this
0x18001240e  call    ?Add@CHandleList@@QEAA_KPEAVCHandle@@K@Z; CHandleList::Add(CHandle *,ulong)
0x180012413  mov     rcx, rax
0x180012416  mov     rax, [rbx+18h]
0x18001241a  mov     [rax+8], rcx
0x18001241e  mov     rax, [rbx+18h]
0x180012422  mov     rcx, [rax+8]
0x180012426  mov     [r15], rcx
0x180012429  lea     rcx, [rsp+108h+var_78]; this
0x180012431  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180012436  nop
0x180012437  jmp     short loc_180012459
0x180012439  mov     [rsp+108h+var_A0], 6
0x180012441  lea     rdx, _TI1K; pThrowInfo
0x180012448  lea     rcx, [rsp+108h+var_A0]; pExceptionObject
0x18001244d  call    _CxxThrowException_0
0x180012453  jmp     short $+2
0x180012455  mov     esi, [rsp+108h+var_C8]
0x180012459  mov     eax, esi
0x18001245b  lea     r11, [rsp+108h+var_28]
0x180012463  mov     rbx, [r11+30h]
0x180012467  mov     rsi, [r11+38h]
0x18001246b  mov     rsp, r11
0x18001246e  pop     r15
0x180012470  pop     r14
0x180012472  pop     r13
0x180012474  pop     r12
0x180012476  pop     rdi
0x180012477  retn
```
