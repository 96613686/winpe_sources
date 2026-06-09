# SCardReadCacheCommon(unsigned __int64,_GUID *,ulong,uchar *,uchar *,ulong *,int)

- ea: `0x18000dbf0`
- end: `0x18000e088`
- name: `?SCardReadCacheCommon@@YAJ_KPEAU_GUID@@KPEAE2PEAKH@Z`
- size: `1176`
- prototype: `int(unsigned __int64, struct _GUID *, unsigned int, unsigned __int8 *, unsigned __int8 *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000dba0`
- `0x180026d50`

## callees

- `0x180003de0`
- `0x18000dbf0`
- `0x18000e090`
- `0x18000e680`
- `0x18000e864`
- `0x180012650`
- `0x180012730`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002bd60`
- `0x18002ef20`
- `0x18002ef38`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SCardReadCacheCommon(
        __int64 a1,
        struct _GUID *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        int a7)
{
  unsigned __int8 *v7; // r12
  unsigned int v8; // r13d
  struct _GUID *v9; // r15
  CHandleList *v11; // rsi
  struct _RTL_CRITICAL_SECTION *v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rax
  CSCardUserContext *v15; // rdi
  int v16; // esi
  unsigned int v17; // edi
  void *v18; // rsi
  const unsigned __int16 *v19; // rax
  struct CSCardUserContext *v20; // rax
  unsigned int v22; // eax
  unsigned int Cache; // edi
  struct _REDIR_LOCAL_SCARDCONTEXT *v24; // rcx
  bool v25; // zf
  const unsigned __int8 *v26; // rsi
  const unsigned __int16 *v27; // rax
  int v28; // [rsp+30h] [rbp-D8h]
  unsigned int v29; // [rsp+40h] [rbp-C8h]
  const int *v30; // [rsp+48h] [rbp-C0h] BYREF
  void *v31; // [rsp+50h] [rbp-B8h]
  int v32; // [rsp+58h] [rbp-B0h]
  int v33; // [rsp+5Ch] [rbp-ACh]
  ulong v34; // [rsp+60h] [rbp-A8h] BYREF
  ulong v35; // [rsp+64h] [rbp-A4h] BYREF
  struct CSCardUserContext *v36; // [rsp+68h] [rbp-A0h]
  ulong v37; // [rsp+70h] [rbp-98h] BYREF
  ulong pExceptionObject; // [rsp+74h] [rbp-94h] BYREF
  CSCardUserContext *v39; // [rsp+78h] [rbp-90h]
  void **v40; // [rsp+80h] [rbp-88h] BYREF
  int v41; // [rsp+88h] [rbp-80h]
  const int *v42; // [rsp+90h] [rbp-78h]
  void *v43; // [rsp+98h] [rbp-70h]
  unsigned int v44; // [rsp+A0h] [rbp-68h]
  unsigned int v45; // [rsp+A4h] [rbp-64h]
  _QWORD v46[2]; // [rsp+A8h] [rbp-60h] BYREF
  int v47; // [rsp+B8h] [rbp-50h]
  int v48; // [rsp+BCh] [rbp-4Ch]
  ulong v49; // [rsp+C0h] [rbp-48h] BYREF
  ulong v50; // [rsp+C4h] [rbp-44h] BYREF
  struct CSCardUserContext *v51; // [rsp+C8h] [rbp-40h]

  v7 = a4;
  v8 = a3;
  v9 = a2;
  try
  {
    v11 = g_phlContexts;
    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    v39 = (CHandleList *)((char *)g_phlContexts + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    if ( HIBYTE(a1) != *((_BYTE *)v11 + 8)
      || *((_DWORD *)v11 + 4) <= ((unsigned int)a1 & 0x7FFFFFFF)
      || (v13 = 16 * (a1 & 0x7FFFFFFF),
          v14 = *((_QWORD *)v11 + 3),
          ((*(_DWORD *)(v13 + v14 + 8) ^ HIDWORD(a1)) & 0xFFFFFF) != 0) )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v15 = *(CSCardUserContext **)(v13 + v14);
    v36 = v15;
    v51 = v15;
    LeaveCriticalSection(v12);
    if ( *((_DWORD *)v15 + 4) )
    {
      v34 = -2146435042;
      throw &v34;
    }
    if ( !v9 || !v7 || !a6 )
    {
      v37 = -2146435068;
      throw &v37;
    }
    v39 = v15;
    v30 = &CBuffer::`vftable';
    v31 = 0;
    v32 = 0;
    v33 = 0;
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
    v16 = a7;
    if ( a7 )
    {
      v17 = 2 * ((__int64 (__fastcall *)(void ***, unsigned __int8 *))CTextString::Length)(&v40, v7) + 2;
      if ( v45 >= v17 )
      {
        v18 = v43;
      }
      else
      {
        v18 = operator new[](v17);
        if ( !v18 )
        {
          v35 = 14;
          throw &v35;
        }
        if ( v43 )
          operator delete(v43);
        v43 = v18;
        v45 = v17;
      }
      v44 = 0;
      if ( v17 )
        memcpy_0(v18, v7, v17);
      v44 = v17;
      v41 = 2;
      v16 = a7;
      v15 = v39;
    }
    else
    {
      v22 = CTextString::Length((CTextString *)&v40, (const char *)v7);
      CBuffer::Set((CBuffer *)v46, v7, v22 + 1);
      v41 = 1;
    }
    try
    {
      v19 = CTextString::Unicode((CTextString *)&v40);
      Cache = CSCardUserContext::ReadCache(v15, v9, v8, v19, (struct CBuffer *)&v30);
    }
    catch ( ulong v49 )
    {
      v7 = a4;
      v8 = a3;
      v9 = a2;
      Cache = v49;
      v20 = v51;
      v16 = a7;
      goto LABEL_21;
    }
    v20 = v36;
LABEL_21:
    if ( Cache )
    {
      if ( Cache == -2146434958 )
      {
LABEL_23:
        CTextString::~CTextString((CTextString *)&v40);
        v30 = &CBuffer::`vftable';
        if ( v31 )
          operator delete(v31);
        v31 = 0;
        v32 = 0;
        v33 = 0;
        goto LABEL_52;
      }
    }
    else
    {
      if ( v32 )
      {
        PlaceResult(v20, (struct CBuffer *)&v30, a5, a6);
        goto LABEL_23;
      }
      Cache = -2146434960;
    }
    v24 = (struct _REDIR_LOCAL_SCARDCONTEXT *)*((_QWORD *)v20 + 16);
    if ( v24 )
    {
      LODWORD(v36) = *a6;
      v25 = v16 == 1;
      v26 = a5;
      v28 = v25;
      v29 = I_SCardReadCache(v24, v9, v8, v7, a5, a6, v28);
      Cache = v29;
      if ( !v29 )
      {
        try
        {
          if ( (_DWORD)v36 == -1 )
            v26 = *(const unsigned __int8 **)a5;
          CBuffer::Set((CBuffer *)&v30, v26, *a6);
          v27 = CTextString::Unicode((CTextString *)&v40);
          CSCardUserContext::WriteCache(v39, v9, v8, v27, (struct CBuffer *)&v30);
        }
        catch ( ... )
        {
          Cache = v29;
          goto LABEL_23;
        }
      }
    }
    goto LABEL_23;
  }
  catch ( ulong v50 )
  {
    Cache = v50;
  }
  catch ( ... )
  {
    return (unsigned int)-2146434960;
  }
LABEL_52:
  if ( Cache != 6
    && (Cache == -2146435068 || Cache != -2146435064 && Cache != -2146434959 && Cache != -2146434958 && Cache) )
  {
    return (unsigned int)-2146434960;
  }
  return Cache;
}

```

## disassembly

```asm
0x18000dbf0  mov     [rsp+arg_18], r9
0x18000dbf5  mov     [rsp+arg_10], r8d
0x18000dbfa  mov     [rsp+arg_8], rdx
0x18000dbff  push    rbx
0x18000dc00  push    rsi
0x18000dc01  push    rdi
0x18000dc02  push    r12
0x18000dc04  push    r13
0x18000dc06  push    r14
0x18000dc08  push    r15
0x18000dc0a  sub     rsp, 0D0h
0x18000dc11  mov     r12, r9
0x18000dc14  mov     r13d, r8d
0x18000dc17  mov     r15, rdx
0x18000dc1a  mov     rdi, rcx
0x18000dc1d  xor     ebx, ebx
0x18000dc1f  mov     [rsp+108h+var_C4], ebx
0x18000dc23  mov     rsi, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18000dc2a  lea     r14, [rsi+20h]
0x18000dc2e  mov     [rsp+108h+var_90], r14
0x18000dc33  mov     rcx, r14; lpCriticalSection
0x18000dc36  call    cs:__imp_EnterCriticalSection
0x18000dc3c  nop
0x18000dc3d  mov     rax, rdi
0x18000dc40  shr     rax, 38h
0x18000dc44  cmp     al, [rsi+8]
0x18000dc47  jnz     short loc_18000DC6E
0x18000dc49  mov     eax, edi
0x18000dc4b  btr     eax, 1Fh
0x18000dc4f  cmp     [rsi+10h], eax
0x18000dc52  jbe     short loc_18000DC6E
0x18000dc54  mov     edx, eax
0x18000dc56  shl     rdx, 4
0x18000dc5a  mov     rax, [rsi+18h]
0x18000dc5e  shr     rdi, 20h
0x18000dc62  xor     edi, [rdx+rax+8]
0x18000dc66  test    edi, 0FFFFFFh
0x18000dc6c  jz      short loc_18000DC87
0x18000dc6e  mov     [rsp+108h+pExceptionObject], 6
0x18000dc76  lea     rdx, _TI1K; pThrowInfo
0x18000dc7d  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18000dc82  call    _CxxThrowException_0
0x18000dc87  mov     rdi, [rdx+rax]
0x18000dc8b  mov     [rsp+108h+var_A0], rdi
0x18000dc90  mov     [rsp+108h+var_40], rdi
0x18000dc98  mov     rcx, r14; lpCriticalSection
0x18000dc9b  call    cs:__imp_LeaveCriticalSection
0x18000dca1  cmp     dword ptr [rdi+10h], 0
0x18000dca5  jnz     loc_18000DF3E
0x18000dcab  test    r15, r15
0x18000dcae  jnz     short loc_18000DCD1
0x18000dcb0  mov     [rsp+108h+var_C4], 1
0x18000dcb8  mov     [rsp+108h+var_98], 80100004h
0x18000dcc0  lea     rdx, _TI1K; pThrowInfo
0x18000dcc7  lea     rcx, [rsp+108h+var_98]; pExceptionObject
0x18000dccc  call    _CxxThrowException_0
0x18000dcd1  test    r12, r12
0x18000dcd4  jz      short loc_18000DCB0
0x18000dcd6  cmp     [rsp+108h+arg_28], 0
0x18000dcdf  jz      short loc_18000DCB0
0x18000dce1  mov     [rsp+108h+var_90], rdi
0x18000dce6  lea     r14, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000dced  mov     [rsp+108h+var_C0], r14
0x18000dcf2  mov     [rsp+108h+var_B8], rbx
0x18000dcf7  mov     [rsp+108h+var_B0], ebx
0x18000dcfb  mov     [rsp+108h+var_AC], ebx
0x18000dcff  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x18000dd06  mov     [rsp+108h+var_88], rax
0x18000dd0e  mov     [rsp+108h+var_78], r14
0x18000dd16  mov     [rsp+108h+var_70], rbx
0x18000dd1e  mov     [rsp+108h+var_68], ebx
0x18000dd25  mov     [rsp+108h+var_64], ebx
0x18000dd2c  mov     [rsp+108h+var_60], r14
0x18000dd34  mov     [rsp+108h+var_58], rbx
0x18000dd3c  mov     [rsp+108h+var_50], ebx
0x18000dd43  mov     [rsp+108h+var_4C], ebx
0x18000dd4a  mov     [rsp+108h+var_80], 3
0x18000dd55  mov     esi, [rsp+108h+arg_30]
0x18000dd5c  mov     rax, [rsp+108h+var_88]
0x18000dd64  mov     rdx, r12
0x18000dd67  lea     rcx, [rsp+108h+var_88]
0x18000dd6f  test    esi, esi
0x18000dd71  jz      loc_18000DEC0
0x18000dd77  mov     rax, [rax+8]
0x18000dd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd80  lea     edi, ds:2[rax*2]
0x18000dd87  mov     r14d, edi
0x18000dd8a  cmp     [rsp+108h+var_64], edi
0x18000dd91  jnb     loc_18000DEED
0x18000dd97  mov     ecx, r14d; unsigned __int64
0x18000dd9a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000dd9f  mov     rsi, rax
0x18000dda2  test    rax, rax
0x18000dda5  jz      loc_18000DF58
0x18000ddab  mov     rcx, [rsp+108h+var_70]; void *
0x18000ddb3  test    rcx, rcx
0x18000ddb6  jz      short loc_18000DDBD
0x18000ddb8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ddbd  mov     [rsp+108h+var_70], rsi
0x18000ddc5  mov     [rsp+108h+var_64], edi
0x18000ddcc  mov     [rsp+108h+var_68], ebx
0x18000ddd3  test    edi, edi
0x18000ddd5  jz      short loc_18000DDE5
0x18000ddd7  mov     r8, r14; Size
0x18000ddda  mov     rdx, r12; Src
0x18000dddd  mov     rcx, rsi; void *
0x18000dde0  call    memcpy_0
0x18000dde5  mov     [rsp+108h+var_68], edi
0x18000ddec  mov     [rsp+108h+var_80], 2
0x18000ddf7  mov     esi, [rsp+108h+arg_30]
0x18000ddfe  lea     r14, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000de05  mov     rdi, [rsp+108h+var_90]
0x18000de0a  lea     rcx, [rsp+108h+var_88]; this
0x18000de12  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x18000de17  lea     rcx, [rsp+108h+var_C0]
0x18000de1c  mov     [rsp+108h+var_E8], rcx; struct CBuffer *
0x18000de21  mov     r9, rax; unsigned __int16 *
0x18000de24  mov     r8d, r13d; unsigned int
0x18000de27  mov     rdx, r15; struct _GUID *
0x18000de2a  mov     rcx, rdi; this
0x18000de2d  call    ?ReadCache@CSCardUserContext@@QEAAKPEAU_GUID@@KPEBGAEAVCBuffer@@@Z; CSCardUserContext::ReadCache(_GUID *,ulong,ushort const *,CBuffer &)
0x18000de32  mov     edi, eax
0x18000de34  mov     [rsp+108h+var_C8], eax
0x18000de38  mov     rax, [rsp+108h+var_A0]
0x18000de3d  test    edi, edi
0x18000de3f  jz      short loc_18000DE9A
0x18000de41  cmp     edi, 80100072h
0x18000de47  jnz     loc_18000DF03
0x18000de4d  lea     rcx, [rsp+108h+var_88]; this
0x18000de55  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18000de5a  nop
0x18000de5b  mov     [rsp+108h+var_C0], r14
0x18000de60  mov     rcx, [rsp+108h+var_B8]; void *
0x18000de65  test    rcx, rcx
0x18000de68  jz      short loc_18000DE6F
0x18000de6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000de6f  mov     [rsp+108h+var_B8], rbx
0x18000de74  mov     [rsp+108h+var_B0], ebx
0x18000de78  mov     [rsp+108h+var_AC], ebx
0x18000de7c  cmp     edi, 6
0x18000de7f  jnz     loc_18000E03B
0x18000de85  mov     eax, edi
0x18000de87  add     rsp, 0D0h
0x18000de8e  pop     r15
0x18000de90  pop     r14
0x18000de92  pop     r13
0x18000de94  pop     r12
0x18000de96  pop     rdi
0x18000de97  pop     rsi
0x18000de98  pop     rbx
0x18000de99  retn
0x18000de9a  cmp     [rsp+108h+var_B0], 0
0x18000de9f  jbe     short loc_18000DEFA
0x18000dea1  mov     r9, [rsp+108h+arg_28]; unsigned int *
0x18000dea9  mov     r8, [rsp+108h+arg_20]; unsigned __int8 *
0x18000deb1  lea     rdx, [rsp+108h+var_C0]; struct CBuffer *
0x18000deb6  mov     rcx, rax; struct CSCardUserContext *
0x18000deb9  call    ?PlaceResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAEPEAK@Z; PlaceResult(CSCardUserContext *,CBuffer &,uchar *,ulong *)
0x18000debe  jmp     short loc_18000DE4D
0x18000dec0  mov     rax, [rax+10h]
0x18000dec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dec9  lea     r8d, [rax+1]; unsigned int
0x18000decd  mov     rdx, r12; unsigned __int8 *
0x18000ded0  lea     rcx, [rsp+108h+var_60]; this
0x18000ded8  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18000dedd  mov     [rsp+108h+var_80], 1
0x18000dee8  jmp     loc_18000DE0A
0x18000deed  mov     rsi, [rsp+108h+var_70]
0x18000def5  jmp     loc_18000DDCC
0x18000defa  mov     edi, 80100070h
0x18000deff  mov     [rsp+108h+var_C8], edi
0x18000df03  mov     rcx, [rax+80h]; struct _REDIR_LOCAL_SCARDCONTEXT *
0x18000df0a  test    rcx, rcx
0x18000df0d  jz      loc_18000DE4D
0x18000df13  mov     rdx, [rsp+108h+arg_28]
0x18000df1b  mov     eax, [rdx]
0x18000df1d  mov     dword ptr [rsp+108h+var_A0], eax
0x18000df21  mov     r9, r12; unsigned __int8 *
0x18000df24  mov     r8d, r13d; unsigned int
0x18000df27  cmp     esi, 1
0x18000df2a  mov     rsi, [rsp+108h+arg_20]
0x18000df32  jnz     short loc_18000DFAA
0x18000df34  mov     [rsp+108h+var_D8], 1
0x18000df3c  jmp     short loc_18000DFAE
0x18000df3e  mov     [rsp+108h+var_A8], 8010001Eh
0x18000df46  lea     rdx, _TI1K; pThrowInfo
0x18000df4d  lea     rcx, [rsp+108h+var_A8]; pExceptionObject
0x18000df52  call    _CxxThrowException_0
0x18000df58  mov     [rsp+108h+var_A4], 0Eh
0x18000df60  lea     rdx, _TI1K; pThrowInfo
0x18000df67  lea     rcx, [rsp+108h+var_A4]; pExceptionObject
0x18000df6c  call    _CxxThrowException_0
0x18000df71  xor     ebx, ebx
0x18000df73  lea     r14, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000df7a  mov     r12, [rsp+108h+arg_18]
0x18000df82  mov     r13d, [rsp+108h+arg_10]
0x18000df8a  mov     r15, [rsp+108h+arg_8]
0x18000df92  mov     edi, [rsp+108h+var_C8]
0x18000df96  mov     rax, [rsp+108h+var_40]
0x18000df9e  mov     esi, [rsp+108h+arg_30]
0x18000dfa5  jmp     loc_18000DE3D
0x18000dfaa  mov     [rsp+108h+var_D8], ebx; int
0x18000dfae  mov     [rsp+108h+var_E0], rdx; unsigned int *
0x18000dfb3  mov     [rsp+108h+var_E8], rsi; unsigned __int8 *
0x18000dfb8  mov     rdx, r15; struct _GUID *
0x18000dfbb  call    ?I_SCardReadCache@@YAJ_KPEAU_GUID@@KPEAE2PEAKH@Z; I_SCardReadCache(unsigned __int64,_GUID *,ulong,uchar *,uchar *,ulong *,int)
0x18000dfc0  mov     [rsp+108h+var_C8], eax
0x18000dfc4  mov     edi, eax
0x18000dfc6  test    eax, eax
0x18000dfc8  jnz     loc_18000DE4D
0x18000dfce  cmp     dword ptr [rsp+108h+var_A0], 0FFFFFFFFh
0x18000dfd3  jnz     short loc_18000DFD8
0x18000dfd5  mov     rsi, [rsi]
0x18000dfd8  mov     rax, [rsp+108h+arg_28]
0x18000dfe0  mov     r8d, [rax]; unsigned int
0x18000dfe3  mov     rdx, rsi; unsigned __int8 *
0x18000dfe6  lea     rcx, [rsp+108h+var_C0]; this
0x18000dfeb  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18000dff0  lea     rcx, [rsp+108h+var_88]; this
0x18000dff8  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x18000dffd  lea     rcx, [rsp+108h+var_C0]
0x18000e002  mov     [rsp+108h+var_E8], rcx; struct CBuffer *
0x18000e007  mov     r9, rax; unsigned __int16 *
0x18000e00a  mov     r8d, r13d; unsigned int
0x18000e00d  mov     rdx, r15; struct _GUID *
0x18000e010  mov     rcx, [rsp+108h+var_90]; this
0x18000e015  call    ?WriteCache@CSCardUserContext@@QEAAXPEAU_GUID@@KPEBGAEAVCBuffer@@@Z; CSCardUserContext::WriteCache(_GUID *,ulong,ushort const *,CBuffer &)
0x18000e01a  nop
0x18000e01b  jmp     loc_18000DE4D
0x18000e020  xor     ebx, ebx
0x18000e022  lea     r14, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000e029  mov     edi, [rsp+108h+var_C8]
0x18000e02d  jmp     loc_18000DE4D
0x18000e032  mov     edi, [rsp+108h+var_C8]
0x18000e036  jmp     loc_18000DE7C
0x18000e03b  cmp     edi, 80100004h
0x18000e041  jz      short loc_18000E071
0x18000e043  cmp     edi, 80100008h
0x18000e049  jz      loc_18000DE85
0x18000e04f  cmp     edi, 80100071h
0x18000e055  jz      loc_18000DE85
0x18000e05b  cmp     edi, 80100072h
0x18000e061  jz      loc_18000DE85
0x18000e067  test    edi, edi
0x18000e069  jz      loc_18000DE85
0x18000e06f  jmp     short loc_18000E07E
0x18000e071  cmp     [rsp+108h+var_C4], 1
0x18000e076  jz      loc_18000DE85
0x18000e07c  jmp     short $+2
0x18000e07e  mov     edi, 80100070h
0x18000e083  jmp     loc_18000DE85
```
