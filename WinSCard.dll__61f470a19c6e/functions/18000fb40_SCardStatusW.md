# SCardStatusW

- ea: `0x18000fb40`
- end: `0x18000fd8e`
- name: `SCardStatusW`
- size: `590`
- prototype: `LONG __stdcall(SCARDHANDLE hCard, LPWSTR mszReaderNames, LPDWORD pcchReaderLen, LPDWORD pdwState, LPDWORD pdwProtocol, LPBYTE pbAtr, LPDWORD pcbAtrLen)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003430`
- `0x180003de0`
- `0x18000fb40`
- `0x18000fd94`
- `0x180018b48`
- `0x18001b9b8`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LONG __stdcall SCardStatusW(
        SCARDHANDLE hCard,
        LPWSTR mszReaderNames,
        LPDWORD pcchReaderLen,
        LPDWORD pdwState,
        LPDWORD pdwProtocol,
        LPBYTE pbAtr,
        LPDWORD pcbAtrLen)
{
  LONG v11; // r15d
  CHandleList *v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rsi
  SCARDHANDLE v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rcx
  unsigned int v22; // [rsp+44h] [rbp-84h] BYREF
  unsigned int v23[2]; // [rsp+48h] [rbp-80h] BYREF
  ulong v24; // [rsp+50h] [rbp-78h] BYREF
  ulong pExceptionObject; // [rsp+54h] [rbp-74h] BYREF
  const int *v26; // [rsp+58h] [rbp-70h] BYREF
  void *v27; // [rsp+60h] [rbp-68h]
  int v28; // [rsp+68h] [rbp-60h]
  int v29; // [rsp+6Ch] [rbp-5Ch]
  const int *v30; // [rsp+70h] [rbp-58h] BYREF
  void *v31; // [rsp+78h] [rbp-50h]
  int v32; // [rsp+80h] [rbp-48h]
  int v33; // [rsp+84h] [rbp-44h]
  LONG v34; // [rsp+88h] [rbp-40h] BYREF

  v11 = 0;
  try
  {
    v12 = g_phlReaders;
    v13 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlReaders + 32);
    *(_QWORD *)v23 = (char *)g_phlReaders + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlReaders + 32));
    if ( HIBYTE(hCard) != *((_BYTE *)v12 + 8)
      || *((_DWORD *)v12 + 4) <= (hCard & 0x7FFFFFFF)
      || (v14 = 16 * (hCard & 0x7FFFFFFF),
          v15 = *((_QWORD *)v12 + 3),
          ((*(_DWORD *)(v14 + v15 + 8) ^ HIDWORD(hCard)) & 0xFFFFFF) != 0) )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v16 = *(_QWORD *)(v14 + v15);
    LeaveCriticalSection(v13);
    if ( *(_DWORD *)(v16 + 16) )
    {
      v24 = -2146435042;
      throw &v24;
    }
    v17 = *(_QWORD *)(v16 + 40);
    if ( v17 )
    {
      v11 = I_SCardStatus(
              v17,
              (unsigned __int8 *)mszReaderNames,
              pcchReaderLen,
              pdwState,
              pdwProtocol,
              pbAtr,
              pcbAtrLen,
              1);
    }
    else
    {
      v30 = &CBuffer::`vftable';
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v26 = &CBuffer::`vftable';
      v27 = 0;
      v28 = 0;
      v29 = 0;
      v22 = 0;
      v23[0] = 0;
      CReaderContext::Status((CReaderContext *)v16, &v22, v23, (struct CBuffer *)&v30, (struct CBuffer *)&v26);
      if ( pdwState )
        *pdwState = v22;
      if ( pdwProtocol )
        *pdwProtocol = v23[0];
      if ( pcchReaderLen )
        PlaceMultiResult(
          *(struct CSCardUserContext **)(*(_QWORD *)(v16 + 24) + 40LL),
          (struct CBuffer *)&v26,
          mszReaderNames,
          pcchReaderLen);
      if ( pcbAtrLen )
        PlaceResult(
          *(struct CSCardUserContext **)(*(_QWORD *)(v16 + 24) + 40LL),
          (struct CBuffer *)&v30,
          pbAtr,
          pcbAtrLen);
      v26 = &CBuffer::`vftable';
      if ( v27 )
        operator delete(v27);
      v27 = 0;
      v28 = 0;
      v29 = 0;
      v30 = &CBuffer::`vftable';
      if ( v31 )
        operator delete(v31);
      v31 = 0;
      v32 = 0;
      v33 = 0;
    }
  }
  catch ( ulong v34 )
  {
    return v34;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v11;
}

```

## disassembly

```asm
0x18000fb40  push    rbx
0x18000fb42  push    rsi
0x18000fb43  push    rdi
0x18000fb44  push    r12
0x18000fb46  push    r13
0x18000fb48  push    r14
0x18000fb4a  push    r15
0x18000fb4c  sub     rsp, 90h
0x18000fb53  mov     r14, r9
0x18000fb56  mov     r12, r8
0x18000fb59  mov     r13, rdx
0x18000fb5c  mov     rbx, rcx
0x18000fb5f  xor     r15d, r15d
0x18000fb62  mov     rdi, cs:?g_phlReaders@@3PEAVCHandleList@@EA; CHandleList * g_phlReaders
0x18000fb69  lea     rsi, [rdi+20h]
0x18000fb6d  mov     qword ptr [rsp+0C8h+var_80], rsi
0x18000fb72  mov     rcx, rsi; lpCriticalSection
0x18000fb75  call    cs:__imp_EnterCriticalSection
0x18000fb7b  nop
0x18000fb7c  mov     rax, rbx
0x18000fb7f  shr     rax, 38h
0x18000fb83  cmp     al, [rdi+8]
0x18000fb86  jnz     short loc_18000FBAD
0x18000fb88  mov     eax, ebx
0x18000fb8a  btr     eax, 1Fh
0x18000fb8e  cmp     [rdi+10h], eax
0x18000fb91  jbe     short loc_18000FBAD
0x18000fb93  mov     edx, eax
0x18000fb95  shl     rdx, 4
0x18000fb99  mov     rax, [rdi+18h]
0x18000fb9d  shr     rbx, 20h
0x18000fba1  xor     ebx, [rdx+rax+8]
0x18000fba5  test    ebx, 0FFFFFFh
0x18000fbab  jz      short loc_18000FBC6
0x18000fbad  mov     [rsp+0C8h+pExceptionObject], 6
0x18000fbb5  lea     rdx, _TI1K; pThrowInfo
0x18000fbbc  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18000fbc1  call    _CxxThrowException_0
0x18000fbc6  mov     rbx, [rdx+rax]
0x18000fbca  mov     rcx, rsi; lpCriticalSection
0x18000fbcd  call    cs:__imp_LeaveCriticalSection
0x18000fbd3  cmp     dword ptr [rbx+10h], 0
0x18000fbd7  jnz     loc_18000FD40
0x18000fbdd  mov     rcx, [rbx+28h]; unsigned __int64
0x18000fbe1  test    rcx, rcx
0x18000fbe4  jnz     loc_18000FCDB
0x18000fbea  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000fbf1  mov     [rsp+0C8h+var_58], rsi
0x18000fbf6  xor     edi, edi
0x18000fbf8  mov     [rsp+0C8h+var_50], rdi
0x18000fbfd  mov     [rsp+0C8h+var_48], edi
0x18000fc04  mov     [rsp+0C8h+var_44], edi
0x18000fc0b  mov     [rsp+0C8h+var_70], rsi
0x18000fc10  mov     [rsp+0C8h+var_68], rdi
0x18000fc15  mov     [rsp+0C8h+var_60], edi
0x18000fc19  mov     [rsp+0C8h+var_5C], edi
0x18000fc1d  mov     [rsp+0C8h+var_84], edi
0x18000fc21  mov     [rsp+0C8h+var_80], edi
0x18000fc25  lea     rax, [rsp+0C8h+var_70]
0x18000fc2a  mov     [rsp+0C8h+var_A8], rax; struct CBuffer *
0x18000fc2f  lea     r9, [rsp+0C8h+var_58]; struct CBuffer *
0x18000fc34  lea     r8, [rsp+0C8h+var_80]; unsigned int *
0x18000fc39  lea     rdx, [rsp+0C8h+var_84]; unsigned int *
0x18000fc3e  mov     rcx, rbx; this
0x18000fc41  call    ?Status@CReaderContext@@QEAAXPEAK0AEAVCBuffer@@1@Z; CReaderContext::Status(ulong *,ulong *,CBuffer &,CBuffer &)
0x18000fc46  test    r14, r14
0x18000fc49  jz      short loc_18000FC52
0x18000fc4b  mov     eax, [rsp+0C8h+var_84]
0x18000fc4f  mov     [r14], eax
0x18000fc52  mov     rcx, [rsp+0C8h+pdwProtocol]
0x18000fc5a  test    rcx, rcx
0x18000fc5d  jnz     loc_18000FD5A
0x18000fc63  test    r12, r12
0x18000fc66  jnz     loc_18000FD65
0x18000fc6c  mov     r9, [rsp+0C8h+pcbAtrLen]; unsigned int *
0x18000fc74  test    r9, r9
0x18000fc77  jnz     loc_18000FD21
0x18000fc7d  mov     [rsp+0C8h+var_70], rsi
0x18000fc82  mov     rcx, [rsp+0C8h+var_68]; void *
0x18000fc87  test    rcx, rcx
0x18000fc8a  jz      short loc_18000FC91
0x18000fc8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fc91  mov     [rsp+0C8h+var_68], rdi
0x18000fc96  mov     [rsp+0C8h+var_60], edi
0x18000fc9a  mov     [rsp+0C8h+var_5C], edi
0x18000fc9e  mov     [rsp+0C8h+var_58], rsi
0x18000fca3  mov     rcx, [rsp+0C8h+var_50]; void *
0x18000fca8  test    rcx, rcx
0x18000fcab  jz      short loc_18000FCB2
0x18000fcad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fcb2  mov     [rsp+0C8h+var_50], rdi
0x18000fcb7  mov     [rsp+0C8h+var_48], edi
0x18000fcbe  mov     [rsp+0C8h+var_44], edi
0x18000fcc5  mov     eax, r15d
0x18000fcc8  add     rsp, 90h
0x18000fccf  pop     r15
0x18000fcd1  pop     r14
0x18000fcd3  pop     r13
0x18000fcd5  pop     r12
0x18000fcd7  pop     rdi
0x18000fcd8  pop     rsi
0x18000fcd9  pop     rbx
0x18000fcda  retn
0x18000fcdb  mov     [rsp+0C8h+var_90], 1; int
0x18000fce3  mov     rax, [rsp+0C8h+pcbAtrLen]
0x18000fceb  mov     [rsp+0C8h+var_98], rax; unsigned int *
0x18000fcf0  mov     rax, [rsp+0C8h+pbAtr]
0x18000fcf8  mov     [rsp+0C8h+var_A0], rax; unsigned __int8 *
0x18000fcfd  mov     rax, [rsp+0C8h+pdwProtocol]
0x18000fd05  mov     [rsp+0C8h+var_A8], rax; unsigned int *
0x18000fd0a  mov     r9, r14; unsigned int *
0x18000fd0d  mov     r8, r12; unsigned int *
0x18000fd10  mov     rdx, r13; unsigned __int8 *
0x18000fd13  call    ?I_SCardStatus@@YAJ_KPEAEPEAK2212H@Z; I_SCardStatus(unsigned __int64,uchar *,ulong *,ulong *,ulong *,uchar *,ulong *,int)
0x18000fd18  mov     r15d, eax
0x18000fd1b  mov     [rsp+0C8h+var_88], eax
0x18000fd1f  jmp     short loc_18000FCC5
0x18000fd21  mov     rcx, [rbx+18h]
0x18000fd25  mov     r8, [rsp+0C8h+pbAtr]; unsigned __int8 *
0x18000fd2d  lea     rdx, [rsp+0C8h+var_58]; struct CBuffer *
0x18000fd32  mov     rcx, [rcx+28h]; struct CSCardUserContext *
0x18000fd36  call    ?PlaceResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAEPEAK@Z; PlaceResult(CSCardUserContext *,CBuffer &,uchar *,ulong *)
0x18000fd3b  jmp     loc_18000FC7D
0x18000fd40  mov     [rsp+0C8h+var_78], 8010001Eh
0x18000fd48  lea     rdx, _TI1K; pThrowInfo
0x18000fd4f  lea     rcx, [rsp+0C8h+var_78]; pExceptionObject
0x18000fd54  call    _CxxThrowException_0
0x18000fd5a  mov     eax, [rsp+0C8h+var_80]
0x18000fd5e  mov     [rcx], eax
0x18000fd60  jmp     loc_18000FC63
0x18000fd65  mov     rcx, [rbx+18h]
0x18000fd69  mov     r9, r12; unsigned int *
0x18000fd6c  mov     r8, r13; unsigned __int16 *
0x18000fd6f  lea     rdx, [rsp+0C8h+var_70]; struct CBuffer *
0x18000fd74  mov     rcx, [rcx+28h]; this
0x18000fd78  call    ?PlaceMultiResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAGPEAK@Z; PlaceMultiResult(CSCardUserContext *,CBuffer &,ushort *,ulong *)
0x18000fd7d  jmp     loc_18000FC6C
0x18000fd82  jmp     short $+2
0x18000fd84  mov     r15d, [rsp+0C8h+var_88]
0x18000fd89  jmp     loc_18000FCC5
```
