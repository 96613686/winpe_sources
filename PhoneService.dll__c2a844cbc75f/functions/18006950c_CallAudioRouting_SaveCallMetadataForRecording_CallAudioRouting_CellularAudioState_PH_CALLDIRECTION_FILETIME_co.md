# CallAudioRouting::_SaveCallMetadataForRecording(CallAudioRouting::CellularAudioState *,PH_CALLDIRECTION,_FILETIME const *,RecordedCallParticipants *)

- ea: `0x18006950c`
- end: `0x1800698b4`
- name: `?_SaveCallMetadataForRecording@CallAudioRouting@@AEAAJPEAUCellularAudioState@1@W4PH_CALLDIRECTION@@PEBU_FILETIME@@PEAURecordedCallParticipants@@@Z`
- size: `936`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180061800`

## callees

- `0x180006e94`
- `0x18000bb40`
- `0x18005bc0c`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006950c`
- `0x18006c0f4`
- `0x18007f9ec`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800696fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006974b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006985d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800696fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006974b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006985d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800696e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800696e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069542`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006955f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069542`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006955f`

## string_xrefs

- `0x180069553`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800697ad`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800697e5`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180069819`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180069847`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180069873`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006989c`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_SaveCallMetadataForRecording(
        __int64 a1,
        __int64 a2,
        int a3,
        _QWORD *a4,
        __int64 a5)
{
  __int64 v9; // rcx
  __int64 v10; // r14
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rbx
  void *v14; // rcx
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rbx
  void *v18; // rcx
  unsigned int v19; // r15d
  BackTraceCollection *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // edi
  __int64 v23; // rbx
  void *v24; // rax
  void *v25; // rsi
  int v26; // eax
  BackTraceCollection *v27; // rcx
  BackTraceCollection *v28; // rcx
  BackTraceCollection *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rsi
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rbx
  unsigned __int16 *v34; // rdi
  int v35; // eax
  BackTraceCollection *v36; // rcx
  BackTraceCollection *v37; // rcx
  __int64 v39; // r9
  void *v40; // rcx
  __int64 v41; // r9
  __int64 v42; // [rsp+38h] [rbp-30h] BYREF
  char v43; // [rsp+40h] [rbp-28h]
  LPVOID pv; // [rsp+48h] [rbp-20h] BYREF

  if ( *(_DWORD *)(a1 + 104) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v9, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3828);
    if ( *(_DWORD *)(a1 + 104) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v10 = a2 + 72;
  *(_DWORD *)v10 = a3;
  *(_QWORD *)(v10 + 4) = *a4;
  *(_QWORD *)(v10 + 12) = 0;
  *(_DWORD *)(v10 + 20) = *(_DWORD *)a5;
  v11 = *(_QWORD *)(v10 + 48);
  v12 = *(_QWORD *)(v10 + 56) - v11;
  *(_QWORD *)(v10 + 56) = v11;
  v13 = v12 >> 3;
  while ( v13 )
  {
    --v13;
    v14 = *(void **)(v11 + 8 * v13);
    if ( v14 )
      CoTaskMemFree(v14);
  }
  v15 = *(_QWORD *)(v10 + 24);
  v16 = *(_QWORD *)(v10 + 32) - v15;
  *(_QWORD *)(v10 + 32) = v15;
  v17 = v16 >> 3;
  while ( v17 )
  {
    --v17;
    v18 = *(void **)(v15 + 8 * v17);
    if ( v18 )
      CoTaskMemFree(v18);
  }
  v19 = 0;
  v42 = v10;
  v43 = 1;
  if ( *(_DWORD *)(v10 + 20) )
  {
    while ( 1 )
    {
      v20 = *(BackTraceCollection **)(*(_QWORD *)(a5 + 16) + 8LL * v19);
      if ( !v20 )
        break;
      v21 = 80;
      while ( *(_WORD *)v20 )
      {
        v20 = (BackTraceCollection *)((char *)v20 + 2);
        if ( !--v21 )
        {
          v22 = -2147024809;
          v23 = 0;
          goto LABEL_19;
        }
      }
      v22 = 0;
      v23 = 80 - v21;
LABEL_19:
      if ( (v22 & 0x80000000) != 0 )
        goto LABEL_57;
      v24 = CoTaskMemAlloc(2 * v23 + 2);
      v25 = v24;
      if ( !v24 )
      {
        v41 = 3856;
LABEL_54:
        Log_HREvent_17(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v41);
LABEL_55:
        v22 = -2147024882;
        goto LABEL_41;
      }
      pv = v24;
      v26 = StringCchCopyW(
              (unsigned __int16 *)v24,
              v23 + 1,
              *(const unsigned __int16 **)(*(_QWORD *)(a5 + 16) + 8LL * v19));
      v22 = v26;
      if ( v26 < 0 )
      {
        BackTraceCollection::Capture(v27, v26);
        Log_HREvent_17(v22, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3857);
        v40 = v25;
        goto LABEL_52;
      }
      if ( !(unsigned __int8)utl::vector<tlx::auto_xxx<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>>>::push_back(
                               v10 + 48,
                               &pv) )
      {
        BackTraceCollection::Capture(v28, -2147024882);
        v39 = 3858;
        goto LABEL_49;
      }
      v29 = *(BackTraceCollection **)(*(_QWORD *)(a5 + 8) + 8LL * v19);
      if ( !v29 )
      {
        v22 = -2147024809;
LABEL_46:
        BackTraceCollection::Capture(v29, v22);
        Log_HREvent_17(v22, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3860);
        v40 = pv;
        if ( !pv )
          goto LABEL_41;
LABEL_52:
        CoTaskMemFree(v40);
        goto LABEL_41;
      }
      v30 = 64;
      while ( *(_WORD *)v29 )
      {
        v29 = (BackTraceCollection *)((char *)v29 + 2);
        if ( !--v30 )
        {
          v22 = -2147024809;
          v31 = 0;
          goto LABEL_29;
        }
      }
      v22 = 0;
      v31 = 64 - v30;
LABEL_29:
      if ( (v22 & 0x80000000) != 0 )
        goto LABEL_46;
      v32 = (unsigned __int16 *)CoTaskMemAlloc(2 * v31 + 2);
      v33 = (unsigned __int16 *)pv;
      v34 = v32;
      if ( v32 != pv )
      {
        if ( pv )
          CoTaskMemFree(pv);
        v33 = v34;
        pv = v34;
      }
      if ( !v33 )
      {
        v41 = 3862;
        goto LABEL_54;
      }
      v35 = StringCchCopyW(v33, v31 + 1, *(const unsigned __int16 **)(*(_QWORD *)(a5 + 8) + 8LL * v19));
      v22 = v35;
      if ( v35 < 0 )
      {
        BackTraceCollection::Capture(v36, v35);
        Log_HREvent_17(v22, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3863);
        v40 = v33;
        goto LABEL_52;
      }
      if ( !(unsigned __int8)utl::vector<tlx::auto_xxx<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>>>::push_back(
                               v10 + 24,
                               &pv) )
      {
        BackTraceCollection::Capture(v37, -2147024882);
        v39 = 3864;
LABEL_49:
        Log_HREvent_17(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v39);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_55;
      }
      if ( pv )
        CoTaskMemFree(pv);
      if ( ++v19 >= *(_DWORD *)(v10 + 20) )
        goto LABEL_40;
    }
    v22 = -2147024809;
LABEL_57:
    BackTraceCollection::Capture(v20, v22);
    Log_HREvent_17(v22, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3854);
  }
  else
  {
LABEL_40:
    v43 = 0;
    v22 = 0;
  }
LABEL_41:
  tlx::_UndoSolo__lambda_5ec45c1e8939def1afefba6e39a15329___::__UndoSolo__lambda_5ec45c1e8939def1afefba6e39a15329___(&v42);
  return v22;
}

```

## disassembly

```asm
0x18006950c  push    rbp
0x18006950e  push    rbx
0x18006950f  push    rsi
0x180069510  push    rdi
0x180069511  push    r12
0x180069513  push    r13
0x180069515  push    r14
0x180069517  push    r15
0x180069519  mov     rbp, rsp
0x18006951c  sub     rsp, 68h
0x180069520  mov     rax, cs:__security_cookie
0x180069527  xor     rax, rsp
0x18006952a  mov     [rbp+var_18], rax
0x18006952e  mov     r15, [rbp+arg_20]
0x180069532  mov     rdi, r9
0x180069535  mov     [rbp+var_38], r15
0x180069539  mov     esi, r8d
0x18006953c  mov     r14, rdx
0x18006953f  mov     rbx, rcx
0x180069542  call    cs:__imp_GetCurrentThreadId
0x180069548  cmp     [rbx+68h], eax
0x18006954b  jz      short loc_18006956F
0x18006954d  mov     r8d, 0EF4h
0x180069553  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006955a  call    Log_AssertionEvent_9
0x18006955f  call    cs:__imp_GetCurrentThreadId
0x180069565  cmp     [rbx+68h], eax
0x180069568  jz      short loc_18006956F
0x18006956a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006956f  add     r14, 48h ; 'H'
0x180069573  mov     [r14], esi
0x180069576  xor     esi, esi
0x180069578  mov     rax, [rdi]
0x18006957b  mov     [r14+4], rax
0x18006957f  mov     [r14+0Ch], rsi
0x180069583  mov     eax, [r15]
0x180069586  mov     [r14+14h], eax
0x18006958a  mov     rdi, [r14+30h]
0x18006958e  mov     rbx, [r14+38h]
0x180069592  sub     rbx, rdi
0x180069595  mov     [r14+38h], rdi
0x180069599  sar     rbx, 3
0x18006959d  jmp     short loc_1800695B1
0x18006959f  dec     rbx
0x1800695a2  mov     rcx, [rdi+rbx*8]; pv
0x1800695a6  test    rcx, rcx
0x1800695a9  jz      short loc_1800695B1
0x1800695ab  call    cs:__imp_CoTaskMemFree
0x1800695b1  test    rbx, rbx
0x1800695b4  jnz     short loc_18006959F
0x1800695b6  mov     rdi, [r14+18h]
0x1800695ba  mov     rbx, [r14+20h]
0x1800695be  sub     rbx, rdi
0x1800695c1  mov     [r14+20h], rdi
0x1800695c5  sar     rbx, 3
0x1800695c9  jmp     short loc_1800695DD
0x1800695cb  dec     rbx
0x1800695ce  mov     rcx, [rdi+rbx*8]; pv
0x1800695d2  test    rcx, rcx
0x1800695d5  jz      short loc_1800695DD
0x1800695d7  call    cs:__imp_CoTaskMemFree
0x1800695dd  test    rbx, rbx
0x1800695e0  jnz     short loc_1800695CB
0x1800695e2  mov     r15d, esi
0x1800695e5  mov     [rbp+var_30], r14
0x1800695e9  mov     [rbp+var_28], 1
0x1800695ed  cmp     [r14+14h], esi
0x1800695f1  jbe     loc_18006975E
0x1800695f7  mov     rax, [rbp+var_38]
0x1800695fb  mov     r12d, r15d
0x1800695fe  mov     rax, [rax+10h]
0x180069602  mov     rcx, [rax+r12*8]; this
0x180069606  test    rcx, rcx
0x180069609  jz      loc_18006988A
0x18006960f  mov     eax, 50h ; 'P'
0x180069614  cmp     [rcx], si
0x180069617  jz      short loc_18006962D
0x180069619  add     rcx, 2
0x18006961d  sub     rax, 1
0x180069621  jnz     short loc_180069614
0x180069623  mov     edi, 80070057h
0x180069628  mov     rbx, rsi
0x18006962b  jmp     short loc_180069637
0x18006962d  mov     ebx, 50h ; 'P'
0x180069632  mov     edi, esi
0x180069634  sub     rbx, rax
0x180069637  test    edi, edi
0x180069639  js      loc_18006988F
0x18006963f  lea     rcx, ds:2[rbx*2]; cb
0x180069647  call    cs:__imp_CoTaskMemAlloc
0x18006964d  mov     rsi, rax
0x180069650  test    rax, rax
0x180069653  jz      loc_180069868
0x180069659  mov     [rbp+pv], rax
0x18006965d  lea     rdx, [rbx+1]; unsigned __int64
0x180069661  mov     rax, [rbp+var_38]
0x180069665  mov     rcx, rsi; unsigned __int16 *
0x180069668  mov     r8, [rax+10h]
0x18006966c  mov     r8, [r8+r12*8]; unsigned __int16 *
0x180069670  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180069675  xor     ebx, ebx
0x180069677  mov     edi, eax
0x180069679  test    eax, eax
0x18006967b  js      loc_18006983A
0x180069681  lea     rdx, [rbp+pv]
0x180069685  lea     rcx, [r14+30h]
0x180069689  call    ?push_back@?$vector@V?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA_N$$QEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@Z; utl::vector<tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>>>::push_back(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &&)
0x18006968e  test    al, al
0x180069690  jz      loc_180069807
0x180069696  mov     rax, [rbp+var_38]
0x18006969a  mov     rax, [rax+8]
0x18006969e  mov     rcx, [rax+r12*8]; this
0x1800696a2  test    rcx, rcx
0x1800696a5  jz      loc_1800697D3
0x1800696ab  lea     edx, [rbx+40h]
0x1800696ae  mov     eax, edx
0x1800696b0  cmp     [rcx], bx
0x1800696b3  jz      short loc_1800696C9
0x1800696b5  add     rcx, 2
0x1800696b9  sub     rax, 1
0x1800696bd  jnz     short loc_1800696B0
0x1800696bf  mov     edi, 80070057h
0x1800696c4  mov     rsi, rbx
0x1800696c7  jmp     short loc_1800696D1
0x1800696c9  mov     rsi, rdx
0x1800696cc  mov     edi, ebx
0x1800696ce  sub     rsi, rax
0x1800696d1  test    edi, edi
0x1800696d3  js      loc_1800697D8
0x1800696d9  lea     rcx, ds:2[rsi*2]; cb
0x1800696e1  call    cs:__imp_CoTaskMemAlloc
0x1800696e7  mov     rbx, [rbp+pv]
0x1800696eb  mov     rdi, rax
0x1800696ee  cmp     rax, rbx
0x1800696f1  jz      short loc_180069708
0x1800696f3  test    rbx, rbx
0x1800696f6  jz      short loc_180069701
0x1800696f8  mov     rcx, rbx; pv
0x1800696fb  call    cs:__imp_CoTaskMemFree
0x180069701  mov     rbx, rdi
0x180069704  mov     [rbp+pv], rbx
0x180069708  test    rbx, rbx
0x18006970b  jz      loc_1800697C8
0x180069711  mov     rax, [rbp+var_38]
0x180069715  lea     rdx, [rsi+1]; unsigned __int64
0x180069719  mov     rcx, rbx; unsigned __int16 *
0x18006971c  mov     r8, [rax+8]
0x180069720  mov     r8, [r8+r12*8]; unsigned __int16 *
0x180069724  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180069729  xor     esi, esi
0x18006972b  mov     edi, eax
0x18006972d  test    eax, eax
0x18006972f  js      short loc_1800697A0
0x180069731  lea     rdx, [rbp+pv]
0x180069735  lea     rcx, [r14+18h]
0x180069739  call    ?push_back@?$vector@V?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA_N$$QEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@Z; utl::vector<tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>>>::push_back(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &&)
0x18006973e  test    al, al
0x180069740  jz      short loc_18006978C
0x180069742  mov     rcx, [rbp+pv]; pv
0x180069746  test    rcx, rcx
0x180069749  jz      short loc_180069751
0x18006974b  call    cs:__imp_CoTaskMemFree
0x180069751  inc     r15d
0x180069754  cmp     r15d, [r14+14h]
0x180069758  jb      loc_1800695F7
0x18006975e  mov     [rbp+var_28], sil
0x180069762  mov     edi, esi
0x180069764  lea     rcx, [rbp+var_30]
0x180069768  call    tlx___UndoSolo__lambda_5ec45c1e8939def1afefba6e39a15329_______UndoSolo__lambda_5ec45c1e8939def1afefba6e39a15329___
0x18006976d  mov     eax, edi
0x18006976f  mov     rcx, [rbp+var_18]
0x180069773  xor     rcx, rsp; StackCookie
0x180069776  call    __security_check_cookie
0x18006977b  add     rsp, 68h
0x18006977f  pop     r15
0x180069781  pop     r14
0x180069783  pop     r13
0x180069785  pop     r12
0x180069787  pop     rdi
0x180069788  pop     rsi
0x180069789  pop     rbx
0x18006978a  pop     rbp
0x18006978b  retn
0x18006978c  mov     ebx, 8007000Eh
0x180069791  mov     edx, ebx; int
0x180069793  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180069798  mov     r9d, 0F18h
0x18006979e  jmp     short loc_180069819
0x1800697a0  mov     edx, edi; int
0x1800697a2  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800697a7  mov     r9d, 0F17h
0x1800697ad  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800697b4  mov     edx, 1
0x1800697b9  mov     ecx, edi
0x1800697bb  call    Log_HREvent_17
0x1800697c0  mov     rcx, rbx
0x1800697c3  jmp     loc_18006985D
0x1800697c8  mov     r9d, 0F16h
0x1800697ce  jmp     loc_18006986E
0x1800697d3  mov     edi, 80070057h
0x1800697d8  mov     edx, edi; int
0x1800697da  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800697df  mov     r9d, 0F14h
0x1800697e5  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800697ec  mov     edx, 1
0x1800697f1  mov     ecx, edi
0x1800697f3  call    Log_HREvent_17
0x1800697f8  mov     rcx, [rbp+pv]
0x1800697fc  test    rcx, rcx
0x1800697ff  jz      loc_180069764
0x180069805  jmp     short loc_18006985D
0x180069807  mov     ebx, 8007000Eh
0x18006980c  mov     edx, ebx; int
0x18006980e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180069813  mov     r9d, 0F12h
0x180069819  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180069820  xor     edx, edx
0x180069822  mov     ecx, ebx
0x180069824  call    Log_HREvent_17
0x180069829  mov     rcx, [rbp+pv]; pv
0x18006982d  test    rcx, rcx
0x180069830  jz      short loc_180069883
0x180069832  call    cs:__imp_CoTaskMemFree
0x180069838  jmp     short loc_180069883
0x18006983a  mov     edx, edi; int
0x18006983c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180069841  mov     r9d, 0F11h
0x180069847  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006984e  mov     edx, 1
0x180069853  mov     ecx, edi
0x180069855  call    Log_HREvent_17
0x18006985a  mov     rcx, rsi; pv
0x18006985d  call    cs:__imp_CoTaskMemFree
0x180069863  jmp     loc_180069764
0x180069868  mov     r9d, 0F10h
0x18006986e  mov     ebx, 8007000Eh
0x180069873  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006987a  mov     ecx, ebx
0x18006987c  xor     edx, edx
0x18006987e  call    Log_HREvent_17
0x180069883  mov     edi, ebx
0x180069885  jmp     loc_180069764
0x18006988a  mov     edi, 80070057h
0x18006988f  mov     edx, edi; int
0x180069891  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180069896  mov     r9d, 0F0Eh
0x18006989c  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800698a3  mov     edx, 1
0x1800698a8  mov     ecx, edi
0x1800698aa  call    Log_HREvent_17
0x1800698af  jmp     loc_180069764
```
