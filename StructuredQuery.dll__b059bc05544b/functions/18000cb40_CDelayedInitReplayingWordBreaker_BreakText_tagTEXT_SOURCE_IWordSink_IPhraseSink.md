# CDelayedInitReplayingWordBreaker::BreakText(tagTEXT_SOURCE *,IWordSink *,IPhraseSink *)

- ea: `0x18000cb40`
- end: `0x18000cd9f`
- name: `?BreakText@CDelayedInitReplayingWordBreaker@@UEAAJPEAUtagTEXT_SOURCE@@PEAUIWordSink@@PEAUIPhraseSink@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(CDelayedInitReplayingWordBreaker *__hidden this, struct tagTEXT_SOURCE *, struct IWordSink *, struct IPhraseSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000cb40`
- `0x18000cda8`
- `0x18000cde4`
- `0x180038dc4`
- `0x180047a98`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cbc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cbc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cc53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cc53`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cc1f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cc1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccda`

## pseudocode

```c
__int64 __fastcall CDelayedInitReplayingWordBreaker::BreakText(
        CDelayedInitReplayingWordBreaker *this,
        struct tagTEXT_SOURCE *a2,
        struct IWordSink *a3,
        struct IPhraseSink *a4)
{
  __int64 v7; // rcx
  char *v8; // rsi
  unsigned __int64 v9; // r14
  int v10; // r13d
  char *v11; // rdi
  char *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // edi
  char *v16; // rbx
  char *v17; // r15
  int v18; // eax
  unsigned __int64 i; // rbx
  char *v21; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-20h]
  __int64 v23; // [rsp+48h] [rbp-18h]
  __int64 v24; // [rsp+50h] [rbp-10h]
  char *v25; // [rsp+A8h] [rbp+48h]
  LPCWCH lpString2; // [rsp+B8h] [rbp+58h]

  if ( ((__int64 (__fastcall *)(struct tagTEXT_SOURCE *))a2->pfnFillTextBuffer)(a2) != -2147215488 )
    return (unsigned int)-2147024809;
  if ( a2->iCur )
    return (unsigned int)-2147024809;
  lpString2 = a2->awcBuffer;
  v7 = -1;
  do
    ++v7;
  while ( a2->awcBuffer[v7] );
  if ( v7 != a2->iEnd )
    return (unsigned int)-2147024809;
  v8 = 0;
  v21 = 0;
  v9 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  AcquireSRWLockShared(&CDelayedInitReplayingWordBreaker::s_lock);
  v10 = -2147023728;
  v11 = (char *)CDelayedInitReplayingWordBreaker::s_srgCachedReplays;
  v12 = (char *)CDelayedInitReplayingWordBreaker::s_srgCachedReplays + 72 * qword_1800B12A0;
  v25 = v12;
  while ( v11 != v12 )
  {
    v13 = *((_QWORD *)this + 3) - *(_QWORD *)v11;
    if ( !v13 )
      v13 = *((_QWORD *)this + 4) - *((_QWORD *)v11 + 1);
    if ( !v13 && CompareStringOrdinal(*((LPCWCH *)v11 + 2), -1, lpString2, -1, 0) == 2 )
    {
      v10 = CDelayedInitReplayingWordBreaker::_CloneReplayDataArray(v14, (__int64 *)v11 + 5, &v21);
      v9 = v22;
      v8 = v21;
      break;
    }
    v11 += 72;
    v12 = v25;
  }
  ReleaseSRWLockShared(&CDelayedInitReplayingWordBreaker::s_lock);
  if ( v10 >= 0 )
    goto LABEL_15;
  v15 = CDelayedInitReplayingWordBreaker::_CaptureBreakText((__int64)this, (__int64)a2, &v21);
  if ( v15 >= 0 )
  {
    CDelayedInitReplayingWordBreaker::_Cache((__int64)this, (__int64)a2->awcBuffer, (__int64)&v21);
    v9 = v22;
    v8 = v21;
LABEL_15:
    v15 = 0;
    v16 = v8;
    v17 = &v8[48 * v9];
    if ( v8 != v17 )
    {
      while ( 1 )
      {
        if ( *(_DWORD *)v16 == 1 )
        {
          v18 = ((__int64 (__fastcall *)(struct IWordSink *, _QWORD, _QWORD, _QWORD, _DWORD))a3->lpVtbl->PutWord)(
                  a3,
                  *((unsigned int *)v16 + 8),
                  *((_QWORD *)v16 + 1),
                  *((unsigned int *)v16 + 9),
                  *((_DWORD *)v16 + 10));
          goto LABEL_18;
        }
        if ( *(_DWORD *)v16 == 2 )
        {
          v18 = ((__int64 (__fastcall *)(struct IWordSink *, _QWORD, _QWORD, _QWORD, _DWORD))a3->lpVtbl->PutAltWord)(
                  a3,
                  *((unsigned int *)v16 + 8),
                  *((_QWORD *)v16 + 1),
                  *((unsigned int *)v16 + 9),
                  *((_DWORD *)v16 + 10));
          goto LABEL_18;
        }
        if ( *(_DWORD *)v16 == 3 )
          break;
        if ( *(_DWORD *)v16 == 4 )
        {
          v18 = ((__int64 (__fastcall *)(struct IWordSink *))a3->lpVtbl->EndAltPhrase)(a3);
          goto LABEL_18;
        }
        if ( *(_DWORD *)v16 == 5 )
        {
          v18 = ((__int64 (__fastcall *)(struct IWordSink *, _QWORD))a3->lpVtbl->PutBreak)(
                  a3,
                  *((unsigned int *)v16 + 11));
          goto LABEL_18;
        }
LABEL_19:
        v16 += 48;
        if ( v16 == v17 )
          goto LABEL_20;
      }
      v18 = ((__int64 (__fastcall *)(struct IWordSink *))a3->lpVtbl->StartAltPhrase)(a3);
LABEL_18:
      v15 = v18;
      if ( v18 < 0 )
        goto LABEL_20;
      goto LABEL_19;
    }
    goto LABEL_20;
  }
  v9 = v22;
  v8 = v21;
LABEL_20:
  if ( v8 )
  {
    for ( i = 0; i < v9; ++i )
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::~NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>((__int64)&v8[48 * i + 8]);
    CoTaskMemFree(v8);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000cb40  mov     [rsp-38h+arg_0], rbx
0x18000cb45  mov     [rsp-38h+lpString2], r9
0x18000cb4a  push    rbp
0x18000cb4b  push    rsi
0x18000cb4c  push    rdi
0x18000cb4d  push    r12
0x18000cb4f  push    r13
0x18000cb51  push    r14
0x18000cb53  push    r15
0x18000cb55  mov     rbp, rsp
0x18000cb58  sub     rsp, 60h
0x18000cb5c  mov     r12, r8
0x18000cb5f  mov     rbx, rdx
0x18000cb62  mov     r15, rcx
0x18000cb65  mov     rcx, rdx
0x18000cb68  mov     rax, [rdx]
0x18000cb6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb70  cmp     eax, 80041780h
0x18000cb75  jnz     loc_18000CD95
0x18000cb7b  xor     edx, edx
0x18000cb7d  cmp     [rbx+14h], edx
0x18000cb80  jnz     loc_18000CD95
0x18000cb86  mov     rax, [rbx+8]
0x18000cb8a  mov     [rbp+lpString2], rax
0x18000cb8e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000cb92  inc     rcx
0x18000cb95  cmp     [rax+rcx*2], dx
0x18000cb99  jnz     short loc_18000CB92
0x18000cb9b  mov     eax, [rbx+10h]
0x18000cb9e  cmp     rcx, rax
0x18000cba1  jnz     loc_18000CD95
0x18000cba7  mov     rsi, rdx
0x18000cbaa  mov     [rbp+var_28], rdx
0x18000cbae  mov     r14, rdx
0x18000cbb1  mov     [rbp+var_20], rdx
0x18000cbb5  mov     [rbp+var_18], rdx
0x18000cbb9  mov     [rbp+var_10], rdx
0x18000cbbd  lea     rdi, ?s_lock@CDelayedInitReplayingWordBreaker@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CDelayedInitReplayingWordBreaker::s_lock
0x18000cbc4  mov     rcx, rdi; SRWLock
0x18000cbc7  call    cs:__imp_AcquireSRWLockShared
0x18000cbcd  mov     [rbp+var_30], rdi
0x18000cbd1  mov     r13d, 80070490h
0x18000cbd7  mov     rdi, cs:?s_srgCachedReplays@CDelayedInitReplayingWordBreaker@@0V?$CCoSimpleArray@UWordbreakerCachedReplay@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UWordbreakerCachedReplay@@@@@@A; CCoSimpleArray<WordbreakerCachedReplay,4294967294,CSimpleArrayStandardCompareHelper<WordbreakerCachedReplay>> CDelayedInitReplayingWordBreaker::s_srgCachedReplays
0x18000cbde  mov     rax, cs:qword_1800B12A0
0x18000cbe5  lea     rcx, [rax+rax*8]
0x18000cbe9  lea     rax, [rdi+rcx*8]
0x18000cbed  mov     [rbp+arg_8], rax
0x18000cbf1  cmp     rdi, rax
0x18000cbf4  jz      short loc_18000CC4C
0x18000cbf6  mov     rax, [r15+18h]
0x18000cbfa  sub     rax, [rdi]
0x18000cbfd  jnz     short loc_18000CC07
0x18000cbff  mov     rax, [r15+20h]
0x18000cc03  sub     rax, [rdi+8]
0x18000cc07  test    rax, rax
0x18000cc0a  jnz     short loc_18000CC2A
0x18000cc0c  mov     [rsp+60h+bIgnoreCase], eax; bIgnoreCase
0x18000cc10  or      r9d, 0FFFFFFFFh; cchCount2
0x18000cc14  mov     r8, [rbp+lpString2]; lpString2
0x18000cc18  or      edx, r9d; cchCount1
0x18000cc1b  mov     rcx, [rdi+10h]; lpString1
0x18000cc1f  call    cs:__imp_CompareStringOrdinal
0x18000cc25  cmp     eax, 2
0x18000cc28  jz      short loc_18000CC34
0x18000cc2a  add     rdi, 48h ; 'H'
0x18000cc2e  mov     rax, [rbp+arg_8]
0x18000cc32  jmp     short loc_18000CBF1
0x18000cc34  lea     rdx, [rdi+28h]
0x18000cc38  lea     r8, [rbp+var_28]
0x18000cc3c  call    ?_CloneReplayDataArray@CDelayedInitReplayingWordBreaker@@AEAAJAEBV?$CCoSimpleArray@UWordbreakerReplayData@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UWordbreakerReplayData@@@@@@AEAV2@@Z; CDelayedInitReplayingWordBreaker::_CloneReplayDataArray(CCoSimpleArray<WordbreakerReplayData,4294967294,CSimpleArrayStandardCompareHelper<WordbreakerReplayData>> const &,CCoSimpleArray<WordbreakerReplayData,4294967294,CSimpleArrayStandardCompareHelper<WordbreakerReplayData>> &)
0x18000cc41  mov     r13d, eax
0x18000cc44  mov     r14, [rbp+var_20]
0x18000cc48  mov     rsi, [rbp+var_28]
0x18000cc4c  lea     rcx, ?s_lock@CDelayedInitReplayingWordBreaker@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18000cc53  call    cs:__imp_ReleaseSRWLockShared
0x18000cc59  test    r13d, r13d
0x18000cc5c  js      loc_18000CD0C
0x18000cc62  xor     edi, edi
0x18000cc64  mov     rbx, rsi
0x18000cc67  lea     r15, [r14+r14*2]
0x18000cc6b  shl     r15, 4
0x18000cc6f  add     r15, rsi
0x18000cc72  cmp     rsi, r15
0x18000cc75  jz      short loc_18000CCAF
0x18000cc77  mov     ecx, [rbx]
0x18000cc79  sub     ecx, 1
0x18000cc7c  jnz     short loc_18000CCFA
0x18000cc7e  mov     rax, [r12]
0x18000cc82  mov     rax, [rax+18h]
0x18000cc86  mov     ecx, [rbx+28h]
0x18000cc89  mov     [rsp+60h+bIgnoreCase], ecx
0x18000cc8d  mov     r9d, [rbx+24h]
0x18000cc91  mov     r8, [rbx+8]
0x18000cc95  mov     edx, [rbx+20h]
0x18000cc98  mov     rcx, r12
0x18000cc9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca0  mov     edi, eax
0x18000cca2  test    eax, eax
0x18000cca4  js      short loc_18000CCAF
0x18000cca6  add     rbx, 30h ; '0'
0x18000ccaa  cmp     rbx, r15
0x18000ccad  jnz     short loc_18000CC77
0x18000ccaf  test    rsi, rsi
0x18000ccb2  jz      short loc_18000CCE0
0x18000ccb4  xor     ebx, ebx
0x18000ccb6  test    r14, r14
0x18000ccb9  jz      short loc_18000CCD7
0x18000ccbb  lea     rcx, [rbx+rbx*2]
0x18000ccbf  shl     rcx, 4
0x18000ccc3  add     rcx, 8
0x18000ccc7  add     rcx, rsi
0x18000ccca  call    ??1?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::~NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>(void)
0x18000cccf  inc     rbx
0x18000ccd2  cmp     rbx, r14
0x18000ccd5  jb      short loc_18000CCBB
0x18000ccd7  mov     rcx, rsi; pv
0x18000ccda  call    cs:__imp_CoTaskMemFree
0x18000cce0  mov     eax, edi
0x18000cce2  mov     rbx, [rsp+60h+arg_0]
0x18000ccea  add     rsp, 60h
0x18000ccee  pop     r15
0x18000ccf0  pop     r14
0x18000ccf2  pop     r13
0x18000ccf4  pop     r12
0x18000ccf6  pop     rdi
0x18000ccf7  pop     rsi
0x18000ccf8  pop     rbp
0x18000ccf9  retn
0x18000ccfa  sub     ecx, 1
0x18000ccfd  jnz     short loc_18000CD3E
0x18000ccff  mov     rax, [r12]
0x18000cd03  mov     rax, [rax+20h]
0x18000cd07  jmp     loc_18000CC86
0x18000cd0c  lea     r8, [rbp+var_28]
0x18000cd10  mov     rdx, rbx
0x18000cd13  mov     rcx, r15
0x18000cd16  call    ?_CaptureBreakText@CDelayedInitReplayingWordBreaker@@AEAAJPEAUtagTEXT_SOURCE@@AEAV?$CCoSimpleArray@UWordbreakerReplayData@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UWordbreakerReplayData@@@@@@@Z; CDelayedInitReplayingWordBreaker::_CaptureBreakText(tagTEXT_SOURCE *,CCoSimpleArray<WordbreakerReplayData,4294967294,CSimpleArrayStandardCompareHelper<WordbreakerReplayData>> &)
0x18000cd1b  mov     edi, eax
0x18000cd1d  test    eax, eax
0x18000cd1f  js      short loc_18000CD69
0x18000cd21  lea     r8, [rbp+var_28]
0x18000cd25  mov     rdx, [rbx+8]
0x18000cd29  mov     rcx, r15
0x18000cd2c  call    ?_Cache@CDelayedInitReplayingWordBreaker@@AEAAJPEB_WAEAV?$CCoSimpleArray@UWordbreakerReplayData@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UWordbreakerReplayData@@@@@@@Z; CDelayedInitReplayingWordBreaker::_Cache(wchar_t const *,CCoSimpleArray<WordbreakerReplayData,4294967294,CSimpleArrayStandardCompareHelper<WordbreakerReplayData>> &)
0x18000cd31  mov     r14, [rbp+var_20]
0x18000cd35  mov     rsi, [rbp+var_28]
0x18000cd39  jmp     loc_18000CC62
0x18000cd3e  sub     ecx, 1
0x18000cd41  jz      short loc_18000CD80
0x18000cd43  sub     ecx, 1
0x18000cd46  jz      short loc_18000CD76
0x18000cd48  cmp     ecx, 1
0x18000cd4b  jnz     loc_18000CCA6
0x18000cd51  mov     rax, [r12]
0x18000cd55  mov     edx, [rbx+2Ch]
0x18000cd58  mov     rcx, r12
0x18000cd5b  mov     rax, [rax+38h]
0x18000cd5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd64  jmp     loc_18000CCA0
0x18000cd69  mov     r14, [rbp+var_20]
0x18000cd6d  mov     rsi, [rbp+var_28]
0x18000cd71  jmp     loc_18000CCAF
0x18000cd76  mov     rax, [r12]
0x18000cd7a  mov     rax, [rax+30h]
0x18000cd7e  jmp     short loc_18000CD88
0x18000cd80  mov     rax, [r12]
0x18000cd84  mov     rax, [rax+28h]
0x18000cd88  mov     rcx, r12
0x18000cd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd90  jmp     loc_18000CCA0
0x18000cd95  mov     edi, 80070057h
0x18000cd9a  jmp     loc_18000CCE0
```
