# UiaManagerImpl::RemoveWindowRegistration(uint,uint)

- ea: `0x18000a390`
- end: `0x18000a7eb`
- name: `?RemoveWindowRegistration@UiaManagerImpl@@QEAAXII@Z`
- size: `1115`
- prototype: `void __fastcall(UiaManagerImpl *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a210`

## callees

- `0x18000a390`
- `0x180043680`
- `0x180043a30`
- `0x180043a50`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a59d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a59d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7be`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a48b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a48b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a4a6`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a4a6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a58d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a58d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a4d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a4d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a3e3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a3e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UiaManagerImpl::RemoveWindowRegistration(UiaManagerImpl *this, int a2, unsigned int a3)
{
  ULONGLONG *v6; // rbx
  __int64 v7; // rcx
  _QWORD *v8; // rdx
  unsigned __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // r10
  _QWORD *v12; // r11
  _QWORD *v13; // rbx
  __int64 v14; // r9
  _QWORD *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  __int64 v19; // r9
  __int64 v20; // r10
  _QWORD *v21; // r11
  _QWORD *v22; // rbx
  _QWORD *v23; // r8
  __int64 v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  WINBOOL fPending; // [rsp+30h] [rbp-59h] BYREF
  int v29; // [rsp+38h] [rbp-51h]
  LPVOID Context; // [rsp+40h] [rbp-49h] BYREF
  int v31; // [rsp+48h] [rbp-41h] BYREF
  GUID ProviderId; // [rsp+50h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-29h] BYREF
  char *v34; // [rsp+70h] [rbp-19h]
  int v35; // [rsp+78h] [rbp-11h]
  int v36; // [rsp+7Ch] [rbp-Dh]
  int *v37; // [rsp+80h] [rbp-9h]
  __int64 v38; // [rsp+88h] [rbp-1h]
  WINBOOL *p_fPending; // [rsp+90h] [rbp+7h]
  __int64 v40; // [rsp+98h] [rbp+Fh]

  v29 = a2;
  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    Context = &qword_1800C4F30;
    qword_1800C4F38 = 0;
    byte_1800C4F40 = 0;
    dword_1800C4F44 = 0;
    qword_1800C4F30 = (__int64)&UiaManagerTraceLoggingProvider::`vftable';
    CallbackContext = &`UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_::_lambda_invoker_cdecl_);
    v6 = (ULONGLONG *)CallbackContext;
    qword_1800C4F38 = (__int64)CallbackContext;
    byte_1800C4F40 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    *((_QWORD *)CallbackContext + 5) = 0;
    v6[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v6, v6 + 4) )
      EventSetInformation(v6[4], 2, v6[1], *(unsigned __int16 *)v6[1]);
    dword_1800C4F44 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800C4F30 + 8))(&qword_1800C4F30);
    InitOnceComplete(&`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_1800C4F30);
  }
  v7 = *((_QWORD *)Context + 1);
  if ( *(_DWORD *)v7 > 4u )
  {
    fPending = a3;
    v31 = a2;
    p_fPending = &fPending;
    v40 = 4;
    v37 = &v31;
    v38 = 4;
    ProviderId.Data1 = 184549376;
    *(_DWORD *)&ProviderId.Data2 = 4;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Ptr = *(_QWORD *)(v7 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v34 = &byte_1800ADA9F;
    v35 = 78;
    v36 = 1;
    LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v7 + 32), (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 4u, &UserData);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 808));
  if ( a3 )
  {
    _mm_lfence();
    v9 = *((_QWORD *)this + 27)
       & (0x100000001B3LL
        * (HIBYTE(a3)
         ^ (0x100000001B3LL
          * (BYTE2(a3)
           ^ (0x100000001B3LL * (BYTE1(a3) ^ (0x100000001B3LL * ((unsigned __int8)a3 ^ 0xCBF29CE484222325uLL))))))));
    v10 = *((_QWORD *)this + 24);
    v11 = 2 * v9;
    v12 = *(_QWORD **)(v10 + 16 * v9 + 8);
    v13 = v12;
    v8 = (_QWORD *)*((_QWORD *)this + 22);
    if ( v12 == v8 )
    {
LABEL_15:
      v13 = 0;
    }
    else
    {
      while ( a3 != *((_DWORD *)v13 + 4) )
      {
        if ( v13 == *(_QWORD **)(v10 + 16 * v9) )
          goto LABEL_15;
        v13 = (_QWORD *)v13[1];
      }
    }
    if ( v13 )
    {
      v14 = 16 * v9;
      v15 = *(_QWORD **)(v14 + v10);
      if ( v12 == v13 )
      {
        if ( v15 == v13 )
          *(_QWORD *)(v14 + v10) = v8;
        else
          v8 = (_QWORD *)v13[1];
        *(_QWORD *)(v10 + 8 * v11 + 8) = v8;
      }
      else if ( v15 == v13 )
      {
        *(_QWORD *)(v14 + v10) = *v13;
      }
      v16 = *v13;
      --*((_QWORD *)this + 23);
      *(_QWORD *)v13[1] = v16;
      *(_QWORD *)(v16 + 8) = v13[1];
      v17 = v13[3];
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      operator delete(v13, 0x20u);
    }
  }
  _mm_lfence();
  v18 = *((_QWORD *)this + 19)
      & (0x100000001B3LL
       * (HIBYTE(v29)
        ^ (0x100000001B3LL
         * (BYTE2(v29)
          ^ (0x100000001B3LL * (BYTE1(v29) ^ (0x100000001B3LL * ((unsigned __int8)a2 ^ 0xCBF29CE484222325uLL))))))));
  v19 = *((_QWORD *)this + 16);
  v20 = 2 * v18;
  v21 = *(_QWORD **)(v19 + 16 * v18 + 8);
  v22 = v21;
  v23 = (_QWORD *)*((_QWORD *)this + 14);
  if ( v21 == v23 )
  {
LABEL_32:
    v22 = 0;
  }
  else
  {
    v8 = *(_QWORD **)(v19 + 16 * v18);
    while ( a2 != *((_DWORD *)v22 + 4) )
    {
      if ( v22 == v8 )
        goto LABEL_32;
      v22 = (_QWORD *)v22[1];
    }
  }
  if ( v22 )
  {
    v24 = 16 * v18;
    v25 = *(_QWORD **)(v24 + v19);
    if ( v21 == v22 )
    {
      if ( v25 == v22 )
        *(_QWORD *)(v24 + v19) = v23;
      else
        v23 = (_QWORD *)v22[1];
      *(_QWORD *)(v19 + 8 * v20 + 8) = v23;
    }
    else if ( v25 == v22 )
    {
      *(_QWORD *)(v24 + v19) = *v22;
    }
    v26 = *v22;
    --*((_QWORD *)this + 15);
    *(_QWORD *)v22[1] = v26;
    *(_QWORD *)(v26 + 8) = v22[1];
    v27 = v22[3];
    if ( v27 )
      (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v27 + 16LL))(v27, v8);
    operator delete(v22, 0x20u);
  }
  if ( this != (UiaManagerImpl *)-808LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 808));
}

```

## disassembly

```asm
0x18000a390  mov     [rsp-8+arg_18], rbx
0x18000a395  push    rbp
0x18000a396  push    rsi
0x18000a397  push    rdi
0x18000a398  push    r12
0x18000a39a  push    r13
0x18000a39c  push    r14
0x18000a39e  push    r15
0x18000a3a0  lea     rbp, [rsp-27h]
0x18000a3a5  sub     rsp, 0B0h
0x18000a3ac  mov     rax, cs:__security_cookie
0x18000a3b3  xor     rax, rsp
0x18000a3b6  mov     [rbp+57h+var_40], rax
0x18000a3ba  mov     esi, r8d
0x18000a3bd  mov     r15d, edx
0x18000a3c0  mov     r14, rcx
0x18000a3c3  mov     [rbp+57h+var_A8], r15d
0x18000a3c7  xor     r13d, r13d
0x18000a3ca  mov     [rbp+57h+Context], r13
0x18000a3ce  mov     [rbp+57h+fPending], r13d
0x18000a3d2  lea     r9, [rbp+57h+Context]; lpContext
0x18000a3d6  lea     r8, [rbp+57h+fPending]; fPending
0x18000a3da  xor     edx, edx; dwFlags
0x18000a3dc  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x18000a3e3  call    cs:__imp___std_init_once_begin_initialize
0x18000a3e9  test    eax, eax
0x18000a3eb  jz      loc_18000A4DB
0x18000a3f1  cmp     [rbp+57h+fPending], r13d
0x18000a3f5  jz      loc_18000A4DB
0x18000a3fb  lea     r12, qword_1800C4F30
0x18000a402  mov     [rbp+57h+Context], r12
0x18000a406  mov     cs:qword_1800C4F38, r13
0x18000a40d  mov     cs:byte_1800C4F40, r13b
0x18000a414  mov     cs:dword_1800C4F44, r13d
0x18000a41b  lea     rax, ??_7UiaManagerTraceLoggingProvider@@6B@; const UiaManagerTraceLoggingProvider::`vftable'
0x18000a422  mov     cs:qword_1800C4F30, rax
0x18000a429  lea     rax, ?__hInner@?1???0StaticHandle@UiaManagerTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a430  mov     cs:CallbackContext, rax
0x18000a437  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_@@CA@XZ; void (__cdecl *)()
0x18000a43e  call    atexit
0x18000a443  mov     rbx, cs:CallbackContext
0x18000a44a  mov     cs:qword_1800C4F38, rbx
0x18000a451  mov     cs:byte_1800C4F40, 1
0x18000a458  mov     rax, [rbx+8]
0x18000a45c  movups  xmm0, xmmword ptr [rax-10h]
0x18000a460  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000a464  cmp     [rbx+20h], r13
0x18000a468  jz      short loc_18000A471
0x18000a46a  mov     ecx, 5
0x18000a46f  int     29h; Win8: RtlFailFast(ecx)
0x18000a471  mov     [rbx+28h], r13
0x18000a475  mov     [rbx+30h], r13
0x18000a479  lea     r9, [rbx+20h]; RegHandle
0x18000a47d  mov     r8, rbx; CallbackContext
0x18000a480  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000a487  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18000a48b  call    cs:__imp_EventRegister
0x18000a491  test    eax, eax
0x18000a493  jnz     short loc_18000A4AC
0x18000a495  mov     r8, [rbx+8]
0x18000a499  movzx   r9d, word ptr [r8]
0x18000a49d  mov     edx, 2
0x18000a4a2  mov     rcx, [rbx+20h]
0x18000a4a6  call    cs:__imp_EventSetInformation
0x18000a4ac  mov     cs:dword_1800C4F44, 1
0x18000a4b6  mov     rax, cs:qword_1800C4F30
0x18000a4bd  mov     rcx, r12
0x18000a4c0  mov     rax, [rax+8]
0x18000a4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c9  mov     r8, r12; lpContext
0x18000a4cc  xor     edx, edx; dwFlags
0x18000a4ce  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x18000a4d5  call    cs:__imp_InitOnceComplete
0x18000a4db  mov     rax, [rbp+57h+Context]
0x18000a4df  mov     rcx, [rax+8]
0x18000a4e3  mov     eax, [rcx]
0x18000a4e5  cmp     eax, 4
0x18000a4e8  jbe     loc_18000A593
0x18000a4ee  mov     [rbp+57h+fPending], esi
0x18000a4f1  mov     [rbp+57h+var_98], r15d
0x18000a4f5  lea     rax, [rbp+57h+fPending]
0x18000a4f9  mov     [rbp+57h+var_50], rax
0x18000a4fd  mov     [rbp+57h+var_48], 4
0x18000a505  lea     rax, [rbp+57h+var_98]
0x18000a509  mov     [rbp+57h+var_60], rax
0x18000a50d  mov     [rbp+57h+var_58], 4
0x18000a515  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18000a51c  movzx   eax, cs:word_1800ADA95
0x18000a523  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000a526  mov     qword ptr [rbp+57h+ProviderId.Data4], r13
0x18000a52a  mov     rax, [rcx+8]
0x18000a52e  mov     [rbp+57h+var_80.Ptr], rax
0x18000a532  movzx   eax, word ptr [rax]
0x18000a535  mov     [rbp+57h+var_80.Size], eax
0x18000a538  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18000a53f  lea     rax, byte_1800ADA9F
0x18000a546  mov     [rbp+57h+var_70], rax
0x18000a54a  mov     [rbp+57h+var_68], 4Eh ; 'N'
0x18000a551  mov     [rbp+57h+var_64], 1
0x18000a558  lea     rax, _TraceLoggingMetadataEnd
0x18000a55f  lea     rdx, _TraceLoggingMetadata
0x18000a566  sub     eax, edx
0x18000a568  mov     dword ptr [rbp+57h+Context], eax
0x18000a56b  mov     eax, dword ptr [rbp+57h+Context]
0x18000a56e  lea     rax, [rbp+57h+var_80]
0x18000a572  mov     [rsp+0E0h+UserData], rax; UserData
0x18000a577  mov     [rsp+0E0h+UserDataCount], 4; UserDataCount
0x18000a57f  xor     r9d, r9d; RelatedActivityId
0x18000a582  xor     r8d, r8d; ActivityId
0x18000a585  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000a589  mov     rcx, [rcx+20h]; RegHandle
0x18000a58d  call    cs:__imp_EventWriteTransfer
0x18000a593  lea     r12, [r14+328h]
0x18000a59a  mov     rcx, r12; lpCriticalSection
0x18000a59d  call    cs:__imp_EnterCriticalSection
0x18000a5a3  mov     edi, 10h
0x18000a5a8  mov     r10, 100000001B3h
0x18000a5b2  test    esi, esi
0x18000a5b4  jz      loc_18000A6C5
0x18000a5ba  mov     r8d, esi
0x18000a5bd  shr     r8d, 18h
0x18000a5c1  mov     eax, esi
0x18000a5c3  shr     eax, 10h
0x18000a5c6  movzx   edx, al
0x18000a5c9  mov     eax, esi
0x18000a5cb  shr     eax, 8
0x18000a5ce  movzx   ecx, al
0x18000a5d1  movzx   r9d, sil
0x18000a5d5  lfence
0x18000a5d8  mov     rax, 0CBF29CE484222325h
0x18000a5e2  xor     r9, rax
0x18000a5e5  imul    r9, r10
0x18000a5e9  xor     r9, rcx
0x18000a5ec  imul    r9, r10
0x18000a5f0  xor     r9, rdx
0x18000a5f3  imul    r9, r10
0x18000a5f7  xor     r9, r8
0x18000a5fa  imul    r9, r10
0x18000a5fe  and     r9, [r14+0D8h]
0x18000a605  mov     r8, [r14+0C0h]
0x18000a60c  mov     r10, r9
0x18000a60f  add     r10, r10
0x18000a612  mov     r11, [r8+r10*8+8]
0x18000a617  mov     rbx, r11
0x18000a61a  mov     rdx, [r14+0B0h]
0x18000a621  cmp     r11, rdx
0x18000a624  jz      short loc_18000A640
0x18000a626  mov     rax, r9
0x18000a629  add     rax, rax
0x18000a62c  mov     rcx, [r8+rax*8]
0x18000a630  cmp     esi, [rbx+10h]
0x18000a633  jz      short loc_18000A643
0x18000a635  cmp     rbx, rcx
0x18000a638  jz      short loc_18000A640
0x18000a63a  mov     rbx, [rbx+8]
0x18000a63e  jmp     short loc_18000A630
0x18000a640  mov     rbx, r13
0x18000a643  mov     rax, rdi
0x18000a646  test    rbx, rbx
0x18000a649  jz      short loc_18000A6BB
0x18000a64b  imul    r9, rax
0x18000a64f  mov     rax, [r9+r8]
0x18000a653  cmp     r11, rbx
0x18000a656  jnz     short loc_18000A673
0x18000a658  cmp     rax, rbx
0x18000a65b  jnz     short loc_18000A668
0x18000a65d  mov     [r9+r8], rdx
0x18000a661  mov     [r8+r10*8+8], rdx
0x18000a666  jmp     short loc_18000A67F
0x18000a668  mov     rdx, [rbx+8]
0x18000a66c  mov     [r8+r10*8+8], rdx
0x18000a671  jmp     short loc_18000A67F
0x18000a673  cmp     rax, rbx
0x18000a676  jnz     short loc_18000A67F
0x18000a678  mov     rax, [rbx]
0x18000a67b  mov     [r9+r8], rax
0x18000a67f  mov     rcx, [rbx]
0x18000a682  dec     qword ptr [r14+0B8h]
0x18000a689  mov     rax, [rbx+8]
0x18000a68d  mov     [rax], rcx
0x18000a690  mov     rax, [rbx+8]
0x18000a694  mov     [rcx+8], rax
0x18000a698  mov     rcx, [rbx+18h]
0x18000a69c  test    rcx, rcx
0x18000a69f  jz      short loc_18000A6AE
0x18000a6a1  mov     rax, [rcx]
0x18000a6a4  mov     rax, [rax+10h]
0x18000a6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6ad  nop
0x18000a6ae  mov     edx, 20h ; ' '; unsigned __int64
0x18000a6b3  mov     rcx, rbx; void *
0x18000a6b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a6bb  mov     r10, 100000001B3h
0x18000a6c5  lfence
0x18000a6c8  movzx   ecx, r15b
0x18000a6cc  mov     rax, 0CBF29CE484222325h
0x18000a6d6  xor     rcx, rax
0x18000a6d9  imul    rcx, r10
0x18000a6dd  movzx   eax, byte ptr [rbp+57h+var_A8+1]
0x18000a6e1  xor     rcx, rax
0x18000a6e4  imul    rcx, r10
0x18000a6e8  movzx   eax, byte ptr [rbp+57h+var_A8+2]
0x18000a6ec  xor     rcx, rax
0x18000a6ef  imul    rcx, r10
0x18000a6f3  movzx   eax, byte ptr [rbp+57h+var_A8+3]
0x18000a6f7  xor     rcx, rax
0x18000a6fa  imul    rcx, r10
0x18000a6fe  and     rcx, [r14+98h]
0x18000a705  mov     r9, [r14+80h]
0x18000a70c  mov     r10, rcx
0x18000a70f  add     r10, r10
0x18000a712  mov     r11, [r9+r10*8+8]
0x18000a717  mov     rbx, r11
0x18000a71a  mov     r8, [r14+70h]
0x18000a71e  cmp     r11, r8
0x18000a721  jz      short loc_18000A741
0x18000a723  mov     rax, rcx
0x18000a726  add     rax, rax
0x18000a729  mov     rdx, [r9+rax*8]
0x18000a72d  nop     dword ptr [rax]
0x18000a730  cmp     r15d, [rbx+10h]
0x18000a734  jz      short loc_18000A744
0x18000a736  cmp     rbx, rdx
0x18000a739  jz      short loc_18000A741
0x18000a73b  mov     rbx, [rbx+8]
0x18000a73f  jmp     short loc_18000A730
0x18000a741  mov     rbx, r13
0x18000a744  test    rbx, rbx
0x18000a747  jz      short loc_18000A7B6
0x18000a749  imul    rcx, rdi
0x18000a74d  mov     rax, [rcx+r9]
0x18000a751  cmp     r11, rbx
0x18000a754  jnz     short loc_18000A771
0x18000a756  cmp     rax, rbx
0x18000a759  jnz     short loc_18000A766
0x18000a75b  mov     [rcx+r9], r8
0x18000a75f  mov     [r9+r10*8+8], r8
0x18000a764  jmp     short loc_18000A77D
0x18000a766  mov     r8, [rbx+8]
0x18000a76a  mov     [r9+r10*8+8], r8
0x18000a76f  jmp     short loc_18000A77D
0x18000a771  cmp     rax, rbx
0x18000a774  jnz     short loc_18000A77D
0x18000a776  mov     rax, [rbx]
0x18000a779  mov     [rcx+r9], rax
0x18000a77d  mov     rcx, [rbx]
0x18000a780  dec     qword ptr [r14+78h]
0x18000a784  mov     rax, [rbx+8]
0x18000a788  mov     [rax], rcx
0x18000a78b  mov     rax, [rbx+8]
0x18000a78f  mov     [rcx+8], rax
0x18000a793  mov     rcx, [rbx+18h]
0x18000a797  test    rcx, rcx
0x18000a79a  jz      short loc_18000A7A9
0x18000a79c  mov     rax, [rcx]
0x18000a79f  mov     rax, [rax+10h]
0x18000a7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a8  nop
0x18000a7a9  mov     edx, 20h ; ' '; unsigned __int64
0x18000a7ae  mov     rcx, rbx; void *
0x18000a7b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a7b6  test    r12, r12
0x18000a7b9  jz      short loc_18000A7C4
0x18000a7bb  mov     rcx, r12; lpCriticalSection
0x18000a7be  call    cs:__imp_LeaveCriticalSection
0x18000a7c4  mov     rcx, [rbp+57h+var_40]
0x18000a7c8  xor     rcx, rsp; StackCookie
0x18000a7cb  call    __security_check_cookie
0x18000a7d0  mov     rbx, [rsp+0E0h+arg_18]
0x18000a7d8  add     rsp, 0B0h
0x18000a7df  pop     r15
0x18000a7e1  pop     r14
0x18000a7e3  pop     r13
0x18000a7e5  pop     r12
0x18000a7e7  pop     rdi
0x18000a7e8  pop     rsi
0x18000a7e9  pop     rbp
0x18000a7ea  retn
```
