# CalaisAsyncAddReader(ulong (*)(ushort const *,ulong),ushort const *,ulong)

- ea: `0x18002a150`
- end: `0x18002a33e`
- name: `?CalaisAsyncAddReader@@YAKP6AKPEBGK@Z0K@Z`
- size: `494`
- prototype: `__int64 __fastcall(unsigned int (*)(const unsigned __int16 *, unsigned int), const unsigned __int16 *, const unsigned __int8 *, const unsigned __int8 *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x1800144e0`
- `0x180017f44`
- `0x180019220`

## callees

- `0x1800075d0`
- `0x180012380`
- `0x1800123a0`
- `0x180017db0`
- `0x18001b7b0`
- `0x18001c330`
- `0x18002a150`
- `0x18002ab90`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a221`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a25f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a25f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a2c9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a2c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CalaisAsyncAddReader(
        unsigned int (*a1)(const unsigned __int16 *, unsigned int),
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4)
{
  int v4; // r14d
  unsigned int v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  const unsigned __int8 *v10; // r8
  const unsigned __int8 *v11; // r9
  DWORD v12; // eax
  __int64 v13; // rcx
  char LastError; // al
  struct _TP_WORK *AsyncReaderHandlingWork; // rax
  _BYTE v17[32]; // [rsp+0h] [rbp-68h] BYREF
  ulong pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  ulong v19; // [rsp+34h] [rbp-34h] BYREF
  ulong v20; // [rsp+38h] [rbp-30h] BYREF
  ulong v21; // [rsp+3Ch] [rbp-2Ch] BYREF
  ulong v22; // [rsp+40h] [rbp-28h] BYREF
  CAsyncAddReaderContext *v23; // [rsp+48h] [rbp-20h]
  char v24; // [rsp+78h] [rbp+10h] BYREF
  ulong v25; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    v4 = (int)a3;
    v7 = 0;
    v23 = 0;
    v24 = 0;
    if ( a2 )
    {
      v8 = operator new(0x50u);
      v9 = v8;
      if ( !v8 )
      {
        v23 = 0;
        v21 = -2146435066;
        throw &v21;
      }
      v8[5] = 0;
      *((_QWORD *)v8 + 9) = 0;
      *((_QWORD *)v8 + 1) = &CTextString::`vftable';
      *((_QWORD *)v8 + 3) = &CBuffer::`vftable';
      *((_QWORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 5) = 0;
      *((_QWORD *)v8 + 6) = &CBuffer::`vftable';
      *((_QWORD *)v8 + 7) = 0;
      *((_QWORD *)v8 + 8) = 0;
      v8[4] = 3;
      v23 = (CAsyncAddReaderContext *)v8;
      *(_QWORD *)v8 = a1;
      CTextString::operator=(v8 + 2, a2);
      v9[18] = v4;
      COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v25, qword_18004BA68, v10, v11);
      if ( !g_hCalaisShutdown )
      {
        pExceptionObject = 1115;
        throw &pExceptionObject;
      }
      v12 = WaitForSingleObject(g_hCalaisShutdown, 0);
      if ( !v12 )
      {
        v20 = 1115;
        throw &v20;
      }
      if ( v12 == 258 )
      {
        ++l_dwReaderActionsInProgress;
        v24 = 1;
        AsyncReaderHandlingWork = CalaisCreateAsyncReaderHandlingWork(CalaisAsyncAddReaderThread, v9);
        if ( !AsyncReaderHandlingWork )
        {
          v19 = -2146435066;
          throw &v19;
        }
        SubmitThreadpoolWork(AsyncReaderHandlingWork);
      }
      else
      {
        WppTraceIndent(v13, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_f3ba224ca5d536188ece76512abbdd99_Traceguids,
            (_DWORD)WPP_pszIndent,
            LastError);
        }
      }
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v25);
    }
  }
  catch ( ulong v22 )
  {
    v25 = v22;
    if ( v23 )
      CAsyncAddReaderContext::`scalar deleting destructor'(v23, (unsigned int)v17);
    if ( v24 )
    {
      COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v24, qword_18004BA68, a3, a4);
      --l_dwReaderActionsInProgress;
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v24);
      WakeAllConditionVariable(&l_cvReaderAsyncActionFinished);
    }
    return v25;
  }
  catch ( ... )
  {
    v25 = -2146435068;
    if ( v23 )
      CAsyncAddReaderContext::`scalar deleting destructor'(v23, (unsigned int)v17);
    if ( v24 )
    {
      COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v24, qword_18004BA68, a3, a4);
      --l_dwReaderActionsInProgress;
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v24);
      WakeAllConditionVariable(&l_cvReaderAsyncActionFinished);
    }
    return v25;
  }
  return v7;
}

```

## disassembly

```asm
0x18002a150  mov     [rsp+arg_0], rbx
0x18002a155  mov     [rsp+arg_10], rsi
0x18002a15a  push    rdi
0x18002a15b  push    r14
0x18002a15d  push    r15
0x18002a15f  sub     rsp, 50h
0x18002a163  mov     r14d, r8d
0x18002a166  mov     rsi, rdx
0x18002a169  mov     r15, rcx
0x18002a16c  xor     edi, edi
0x18002a16e  mov     [rsp+68h+var_20], rdi
0x18002a173  mov     [rsp+68h+arg_8], dil
0x18002a178  test    rdx, rdx
0x18002a17b  jz      loc_18002A2DE
0x18002a181  lea     ecx, [rdi+50h]; Size
0x18002a184  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a189  mov     rbx, rax
0x18002a18c  test    rax, rax
0x18002a18f  jz      loc_18002A2FA
0x18002a195  mov     [rax+14h], edi
0x18002a198  mov     [rax+48h], rdi
0x18002a19c  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x18002a1a3  mov     [rbx+8], rax
0x18002a1a7  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002a1ae  mov     [rbx+18h], rax
0x18002a1b2  mov     [rbx+20h], rdi
0x18002a1b6  mov     [rbx+28h], rdi
0x18002a1ba  mov     [rbx+30h], rax
0x18002a1be  mov     [rbx+38h], rdi
0x18002a1c2  mov     [rbx+40h], rdi
0x18002a1c6  mov     dword ptr [rbx+10h], 3
0x18002a1cd  mov     [rsp+68h+var_20], rbx
0x18002a1d2  mov     [rbx], r15
0x18002a1d5  lea     rcx, [rbx+8]
0x18002a1d9  mov     rdx, rsi
0x18002a1dc  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x18002a1e1  mov     [rbx+48h], r14d
0x18002a1e5  mov     rdx, cs:qword_18004BA68; struct CCriticalSectionObject *
0x18002a1ec  lea     rcx, [rsp+68h+arg_18]; this
0x18002a1f4  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x18002a1f9  nop
0x18002a1fa  mov     rcx, cs:?g_hCalaisShutdown@@3PEAXEA; hHandle
0x18002a201  test    rcx, rcx
0x18002a204  jnz     short loc_18002A21F
0x18002a206  mov     [rsp+68h+pExceptionObject], 45Bh
0x18002a20e  lea     rdx, _TI1K; pThrowInfo
0x18002a215  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002a21a  call    _CxxThrowException_0
0x18002a21f  xor     edx, edx; dwMilliseconds
0x18002a221  call    cs:__imp_WaitForSingleObject
0x18002a227  test    eax, eax
0x18002a229  jz      loc_18002A2E0
0x18002a22f  cmp     eax, 102h
0x18002a234  jz      short loc_18002A28E
0x18002a236  mov     edx, 2
0x18002a23b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002a240  lea     rcx, WPP_GLOBAL_Control
0x18002a247  mov     rax, cs:WPP_GLOBAL_Control
0x18002a24e  cmp     rax, rcx
0x18002a251  jz      short loc_18002A2D0
0x18002a253  test    byte ptr [rax+1Ch], 1
0x18002a257  jz      short loc_18002A2D0
0x18002a259  cmp     byte ptr [rax+19h], 2
0x18002a25d  jb      short loc_18002A2D0
0x18002a25f  call    cs:__imp_GetLastError
0x18002a265  mov     edx, 0Dh
0x18002a26a  mov     [rsp+68h+var_48], eax
0x18002a26e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002a275  lea     r8, WPP_f3ba224ca5d536188ece76512abbdd99_Traceguids
0x18002a27c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a283  mov     rcx, [rcx+10h]
0x18002a287  call    WPP_SF_sD
0x18002a28c  jmp     short loc_18002A2D0
0x18002a28e  inc     cs:?l_dwReaderActionsInProgress@@3KA; ulong l_dwReaderActionsInProgress
0x18002a294  mov     [rsp+68h+arg_8], 1
0x18002a299  mov     rdx, rbx; pv
0x18002a29c  lea     rcx, ?CalaisAsyncAddReaderThread@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002a2a3  call    ?CalaisCreateAsyncReaderHandlingWork@@YAPEAU_TP_WORK@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z1@Z; CalaisCreateAsyncReaderHandlingWork(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x18002a2a8  test    rax, rax
0x18002a2ab  jnz     short loc_18002A2C6
0x18002a2ad  mov     [rsp+68h+var_34], 80100006h
0x18002a2b5  lea     rdx, _TI1K; pThrowInfo
0x18002a2bc  lea     rcx, [rsp+68h+var_34]; pExceptionObject
0x18002a2c1  call    _CxxThrowException_0
0x18002a2c6  mov     rcx, rax; pwk
0x18002a2c9  call    cs:__imp_SubmitThreadpoolWork
0x18002a2cf  nop
0x18002a2d0  lea     rcx, [rsp+68h+arg_18]; this
0x18002a2d8  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002a2dd  nop
0x18002a2de  jmp     short loc_18002A326
0x18002a2e0  mov     [rsp+68h+var_30], 45Bh
0x18002a2e8  lea     rdx, _TI1K; pThrowInfo
0x18002a2ef  lea     rcx, [rsp+68h+var_30]; pExceptionObject
0x18002a2f4  call    _CxxThrowException_0
0x18002a2fa  mov     [rsp+68h+var_20], 0
0x18002a303  mov     [rsp+68h+var_2C], 80100006h
0x18002a30b  lea     rdx, _TI1K; pThrowInfo
0x18002a312  lea     rcx, [rsp+68h+var_2C]; pExceptionObject
0x18002a317  call    _CxxThrowException_0
0x18002a31d  jmp     short $+2
0x18002a31f  mov     edi, [rsp+68h+arg_18]
0x18002a326  mov     eax, edi
0x18002a328  lea     r11, [rsp+68h+var_18]
0x18002a32d  mov     rbx, [r11+20h]
0x18002a331  mov     rsi, [r11+30h]
0x18002a335  mov     rsp, r11
0x18002a338  pop     r15
0x18002a33a  pop     r14
0x18002a33c  pop     rdi
0x18002a33d  retn
```
