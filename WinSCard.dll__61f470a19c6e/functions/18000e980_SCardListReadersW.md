# SCardListReadersW

- ea: `0x18000e980`
- end: `0x18000ebd3`
- name: `SCardListReadersW`
- size: `595`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCWSTR mszGroups, LPWSTR mszReaders, LPDWORD pcchReaders)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180002e84`

## callees

- `0x180003430`
- `0x1800093e4`
- `0x180009480`
- `0x18000e090`
- `0x18000e400`
- `0x18000e680`
- `0x18000e980`
- `0x180010898`
- `0x180012d80`
- `0x180019b80`
- `0x18001b9b8`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ea66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ea66`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LONG __stdcall SCardListReadersW(SCARDCONTEXT hContext, LPCWSTR mszGroups, LPWSTR mszReaders, LPDWORD pcchReaders)
{
  LONG v7; // edi
  void *v8; // rsi
  CHandleList *v9; // r14
  struct _RTL_CRITICAL_SECTION *v10; // r15
  SCARDCONTEXT v11; // r8
  __int64 v12; // rbx
  struct _REDIR_LOCAL_SCARDCONTEXT *v13; // r14
  unsigned int v14; // r15d
  const unsigned __int16 *v15; // rax
  ulong pExceptionObject; // [rsp+34h] [rbp-A4h] BYREF
  ulong v18; // [rsp+38h] [rbp-A0h] BYREF
  ulong v19; // [rsp+3Ch] [rbp-9Ch] BYREF
  const int *v20; // [rsp+40h] [rbp-98h] BYREF
  void *v21; // [rsp+48h] [rbp-90h]
  int v22; // [rsp+50h] [rbp-88h]
  int v23; // [rsp+54h] [rbp-84h]
  LONG v24; // [rsp+58h] [rbp-80h] BYREF
  void **v25; // [rsp+60h] [rbp-78h] BYREF
  int v26; // [rsp+68h] [rbp-70h]
  const int *v27; // [rsp+70h] [rbp-68h]
  __int64 v28; // [rsp+78h] [rbp-60h]
  int v29; // [rsp+80h] [rbp-58h]
  int v30; // [rsp+84h] [rbp-54h]
  const int *v31; // [rsp+88h] [rbp-50h]
  __int64 v32; // [rsp+90h] [rbp-48h]
  int v33; // [rsp+98h] [rbp-40h]
  int v34; // [rsp+9Ch] [rbp-3Ch]
  char *v35; // [rsp+A0h] [rbp-38h]

  v7 = 0;
  try
  {
    v20 = &CBuffer::`vftable';
    v8 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v27 = &CBuffer::`vftable';
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = &CBuffer::`vftable';
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v26 = 3;
    v25 = &CTextMultistring::`vftable';
    if ( hContext )
    {
      v9 = g_phlContexts;
      v10 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
      v35 = (char *)g_phlContexts + 32;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
      if ( HIBYTE(hContext) != *((_BYTE *)v9 + 8)
        || *((_DWORD *)v9 + 4) <= (hContext & 0x7FFFFFFF)
        || (v11 = *((_QWORD *)v9 + 3) + 16 * (hContext & 0x7FFFFFFF),
            ((*(_DWORD *)(v11 + 8) ^ HIDWORD(hContext)) & 0xFFFFFF) != 0)
        || !v11 )
      {
        v18 = 6;
        throw &v18;
      }
      v12 = *(_QWORD *)v11;
      LeaveCriticalSection(v10);
      if ( *(_DWORD *)(v12 + 16) )
      {
        pExceptionObject = -2146435042;
        throw &pExceptionObject;
      }
      v13 = *(struct _REDIR_LOCAL_SCARDCONTEXT **)(v12 + 128);
      if ( v13 )
        goto LABEL_17;
      v14 = *(_DWORD *)(v12 + 28);
    }
    else
    {
      v12 = 0;
      v14 = 2;
      v13 = 0;
    }
    if ( RedirectionContextIsLocal(0) )
    {
      CTextString::operator=(&v25, mszGroups);
      v15 = CTextString::Unicode((CTextString *)&v25);
      ListReaders(v14, v15, (struct CBuffer *)&v20);
      if ( v12 )
        CSCardUserContext::StripInactiveReaders((CSCardUserContext *)v12, (struct CBuffer *)&v20);
      PlaceMultiResult((struct CSCardUserContext *)v12, (struct CBuffer *)&v20, mszReaders, pcchReaders);
      v8 = v21;
LABEL_20:
      CTextString::~CTextString((CTextString *)&v25);
      v20 = &CBuffer::`vftable';
      if ( v8 )
        operator delete(v8);
      v21 = 0;
      v22 = 0;
      v23 = 0;
      return v7;
    }
LABEL_17:
    if ( RedirectDisabled() )
    {
      v19 = -2146435043;
      throw &v19;
    }
    v7 = I_SCardListReaders(v13, mszGroups, (unsigned __int8 *)mszReaders, pcchReaders, 1);
    goto LABEL_20;
  }
  catch ( ulong v24 )
  {
    return v24;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v7;
}

```

## disassembly

```asm
0x18000e980  mov     r11, rsp
0x18000e983  mov     [r11+8], rbx
0x18000e987  mov     [r11+18h], rsi
0x18000e98b  mov     [r11+10h], rdx
0x18000e98f  push    rdi
0x18000e990  push    r12
0x18000e992  push    r13
0x18000e994  push    r14
0x18000e996  push    r15
0x18000e998  sub     rsp, 0B0h
0x18000e99f  mov     r12, r9
0x18000e9a2  mov     r13, r8
0x18000e9a5  mov     rbx, rcx
0x18000e9a8  xor     ecx, ecx
0x18000e9aa  mov     edi, ecx
0x18000e9ac  lea     rdx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000e9b3  mov     [rsp+0D8h+var_98], rdx
0x18000e9b8  mov     esi, ecx
0x18000e9ba  mov     [rsp+0D8h+var_90], rcx
0x18000e9bf  mov     [rsp+0D8h+var_88], ecx
0x18000e9c3  mov     [rsp+0D8h+var_84], ecx
0x18000e9c7  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x18000e9ce  mov     [r11-78h], rax
0x18000e9d2  mov     [r11-68h], rdx
0x18000e9d6  mov     [r11-60h], rcx
0x18000e9da  mov     [r11-58h], ecx
0x18000e9de  mov     [r11-54h], ecx
0x18000e9e2  mov     [r11-50h], rdx
0x18000e9e6  mov     [r11-48h], rcx
0x18000e9ea  mov     [r11-40h], ecx
0x18000e9ee  mov     [r11-3Ch], ecx
0x18000e9f2  mov     [rsp+0D8h+var_70], 3
0x18000e9fa  lea     rax, ??_7CTextMultistring@@6B@; const CTextMultistring::`vftable'
0x18000ea01  mov     [r11-78h], rax
0x18000ea05  test    rbx, rbx
0x18000ea08  jz      loc_18000EABA
0x18000ea0e  mov     r14, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18000ea15  lea     r15, [r14+20h]
0x18000ea19  mov     [r11-38h], r15
0x18000ea1d  mov     rcx, r15; lpCriticalSection
0x18000ea20  call    cs:__imp_EnterCriticalSection
0x18000ea26  nop
0x18000ea27  mov     rax, rbx
0x18000ea2a  shr     rax, 38h
0x18000ea2e  cmp     al, [r14+8]
0x18000ea32  jnz     short loc_18000EAA0
0x18000ea34  mov     eax, ebx
0x18000ea36  btr     eax, 1Fh
0x18000ea3a  cmp     [r14+10h], eax
0x18000ea3e  jbe     short loc_18000EAA0
0x18000ea40  mov     r8d, eax
0x18000ea43  shl     r8, 4
0x18000ea47  add     r8, [r14+18h]
0x18000ea4b  shr     rbx, 20h
0x18000ea4f  xor     ebx, [r8+8]
0x18000ea53  test    ebx, 0FFFFFFh
0x18000ea59  jnz     short loc_18000EAA0
0x18000ea5b  test    r8, r8
0x18000ea5e  jz      short loc_18000EAA0
0x18000ea60  mov     rbx, [r8]
0x18000ea63  mov     rcx, r15; lpCriticalSection
0x18000ea66  call    cs:__imp_LeaveCriticalSection
0x18000ea6c  cmp     [rbx+10h], esi
0x18000ea6f  jz      short loc_18000EA8A
0x18000ea71  mov     [rsp+0D8h+pExceptionObject], 8010001Eh
0x18000ea79  lea     rdx, _TI1K; pThrowInfo
0x18000ea80  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000ea85  call    _CxxThrowException_0
0x18000ea8a  mov     r14, [rbx+80h]
0x18000ea91  test    r14, r14
0x18000ea94  jnz     loc_18000EB29
0x18000ea9a  mov     r15d, [rbx+1Ch]
0x18000ea9e  jmp     short loc_18000EAC6
0x18000eaa0  mov     [rsp+0D8h+var_A0], 6
0x18000eaa8  lea     rdx, _TI1K; pThrowInfo
0x18000eaaf  lea     rcx, [rsp+0D8h+var_A0]; pExceptionObject
0x18000eab4  call    _CxxThrowException_0
0x18000eaba  mov     rbx, rcx
0x18000eabd  mov     r15d, 2
0x18000eac3  mov     r14, rcx
0x18000eac6  xor     ecx, ecx; lpCriticalSection
0x18000eac8  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x18000eacd  test    al, al
0x18000eacf  jz      short loc_18000EB29
0x18000ead1  mov     rdx, [rsp+0D8h+arg_8]
0x18000ead9  lea     rcx, [rsp+0D8h+var_78]
0x18000eade  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x18000eae3  lea     rcx, [rsp+0D8h+var_78]; this
0x18000eae8  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x18000eaed  lea     r8, [rsp+0D8h+var_98]; struct CBuffer *
0x18000eaf2  mov     rdx, rax; unsigned __int16 *
0x18000eaf5  mov     ecx, r15d; unsigned int
0x18000eaf8  call    ?ListReaders@@YAXKPEBGAEAVCBuffer@@@Z; ListReaders(ulong,ushort const *,CBuffer &)
0x18000eafd  test    rbx, rbx
0x18000eb00  jz      short loc_18000EB0F
0x18000eb02  lea     rdx, [rsp+0D8h+var_98]; struct CBuffer *
0x18000eb07  mov     rcx, rbx; this
0x18000eb0a  call    ?StripInactiveReaders@CSCardUserContext@@QEAAXAEAVCBuffer@@@Z; CSCardUserContext::StripInactiveReaders(CBuffer &)
0x18000eb0f  mov     r9, r12; unsigned int *
0x18000eb12  mov     r8, r13; unsigned __int16 *
0x18000eb15  lea     rdx, [rsp+0D8h+var_98]; struct CBuffer *
0x18000eb1a  mov     rcx, rbx; this
0x18000eb1d  call    ?PlaceMultiResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAGPEAK@Z; PlaceMultiResult(CSCardUserContext *,CBuffer &,ushort *,ulong *)
0x18000eb22  mov     rsi, [rsp+0D8h+var_90]
0x18000eb27  jmp     short loc_18000EB6F
0x18000eb29  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x18000eb2e  test    al, al
0x18000eb30  jz      short loc_18000EB4B
0x18000eb32  mov     [rsp+0D8h+var_9C], 8010001Dh
0x18000eb3a  lea     rdx, _TI1K; pThrowInfo
0x18000eb41  lea     rcx, [rsp+0D8h+var_9C]; pExceptionObject
0x18000eb46  call    _CxxThrowException_0
0x18000eb4b  mov     [rsp+0D8h+var_B8], 1; int
0x18000eb53  mov     r9, r12; unsigned int *
0x18000eb56  mov     r8, r13; unsigned __int8 *
0x18000eb59  mov     rdx, [rsp+0D8h+arg_8]; unsigned __int8 *
0x18000eb61  mov     rcx, r14; struct _REDIR_LOCAL_SCARDCONTEXT *
0x18000eb64  call    ?I_SCardListReaders@@YAJ_KPEBEPEAEPEAKH@Z; I_SCardListReaders(unsigned __int64,uchar const *,uchar *,ulong *,int)
0x18000eb69  mov     edi, eax
0x18000eb6b  mov     [rsp+0D8h+var_A8], eax
0x18000eb6f  lea     rcx, [rsp+0D8h+var_78]; this
0x18000eb74  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18000eb79  nop
0x18000eb7a  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000eb81  mov     [rsp+0D8h+var_98], rax
0x18000eb86  test    rsi, rsi
0x18000eb89  jz      short loc_18000EB93
0x18000eb8b  mov     rcx, rsi; void *
0x18000eb8e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000eb93  mov     [rsp+0D8h+var_90], 0
0x18000eb9c  mov     [rsp+0D8h+var_88], 0
0x18000eba4  mov     [rsp+0D8h+var_84], 0
0x18000ebac  jmp     short loc_18000EBB4
0x18000ebae  jmp     short $+2
0x18000ebb0  mov     edi, [rsp+0D8h+var_A8]
0x18000ebb4  mov     eax, edi
0x18000ebb6  lea     r11, [rsp+0D8h+var_28]
0x18000ebbe  mov     rbx, [r11+30h]
0x18000ebc2  mov     rsi, [r11+40h]
0x18000ebc6  mov     rsp, r11
0x18000ebc9  pop     r15
0x18000ebcb  pop     r14
0x18000ebcd  pop     r13
0x18000ebcf  pop     r12
0x18000ebd1  pop     rdi
0x18000ebd2  retn
```
