# NetSetupApiAdapter::GetObjectProperties(NetSetupTransaction &,NetSetupOperation *,_NETSETUP_OBJECT_TYPE,_GUID const &,ulong,ulong,_NETSETUPPROPCOMPKEY const *,ulong *,_NETSETUPPROPERTY const * *)

- ea: `0x180008c90`
- end: `0x180009433`
- name: `?GetObjectProperties@NetSetupApiAdapter@@SAXAEAVNetSetupTransaction@@PEAVNetSetupOperation@@W4_NETSETUP_OBJECT_TYPE@@AEBU_GUID@@KKPEBU_NETSETUPPROPCOMPKEY@@PEAKPEAPEBU_NETSETUPPROPERTY@@@Z`
- size: `1955`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18003ea90`

## callees

- `0x180007fc8`
- `0x180008150`
- `0x180008c90`
- `0x18000a430`
- `0x180015900`
- `0x18001e110`
- `0x1800207a0`
- `0x180033600`
- `0x18005097c`
- `0x18005c848`
- `0x1800646b8`
- `0x180064704`
- `0x180065035`
- `0x180065056`
- `0x1800810a2`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800090e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009199`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800090e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009199`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008ff6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008ff6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093b7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008d1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008d1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000911b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000911b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800090f2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800090f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall NetSetupApiAdapter::GetObjectProperties(
        __int64 a1,
        char *a2,
        unsigned int a3,
        _QWORD *a4,
        char a5,
        unsigned int a6,
        __int64 a7,
        _DWORD *a8,
        _QWORD *a9)
{
  __int64 v12; // r13
  DWORD v13; // ecx
  unsigned int Value; // eax
  __int64 v15; // rbx
  unsigned __int64 v16; // rsi
  unsigned int i; // r8d
  __int64 v18; // rax
  __int128 v19; // xmm0
  int v20; // edx
  __int64 v21; // rcx
  _DWORD *v22; // rax
  __int64 ObjectProvider; // rax
  __int64 v24; // rbx
  volatile signed __int32 *v25; // rdi
  char *v26; // rbx
  char *v27; // rdi
  unsigned __int64 v28; // rdi
  HANDLE ProcessHeap; // rax
  _DWORD *v30; // rax
  _DWORD *v31; // r14
  char *v32; // rbx
  char *v33; // rdi
  unsigned __int64 v34; // rax
  __int64 v35; // r15
  __int64 v36; // rdi
  __int64 v37; // rax
  SIZE_T v38; // rdi
  HANDLE v39; // rax
  void *v40; // rax
  PCONDITION_VARIABLE v41; // rdi
  char *Ptr; // rax
  RTL_SRWLOCK *v43; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v45; // rcx
  __int64 v46; // rax
  char *v47; // rax
  char *v48; // rbx
  __int128 v49; // xmm0
  void *v50; // rbx
  HANDLE v51; // rax
  HANDLE v52; // rax
  char *v53; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v54; // [rsp+48h] [rbp-B8h]
  _QWORD *v55; // [rsp+50h] [rbp-B0h]
  __int128 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+70h] [rbp-90h]
  _BYTE pExceptionObject[208]; // [rsp+78h] [rbp-88h] BYREF
  void *Block[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v60; // [rsp+158h] [rbp+58h]
  void *v61[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v62; // [rsp+170h] [rbp+70h]
  PCONDITION_VARIABLE ConditionVariable[2]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v64; // [rsp+188h] [rbp+88h]
  __int64 v65; // [rsp+190h] [rbp+90h]
  char v66; // [rsp+198h] [rbp+98h]
  _QWORD v67[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v68; // [rsp+1B0h] [rbp+B0h]
  unsigned int v69; // [rsp+1B8h] [rbp+B8h]
  _QWORD v70[2]; // [rsp+1BCh] [rbp+BCh] BYREF

  v57 = -2;
  v53 = a2;
  *(_OWORD *)ConditionVariable = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v12 = 0;
  v13 = *(_DWORD *)(a1 + 856);
  if ( v13 != -1 )
  {
    Value = (unsigned int)TlsGetValue(v13);
    if ( Value )
      v12 = Value;
  }
  v15 = *(_QWORD *)(a1 + 904);
  ConditionVariable[0] = (PCONDITION_VARIABLE)v15;
  AcquireSRWLockExclusive((PSRWLOCK)(v15 + 8));
  *(_DWORD *)(v15 + 16) = GetCurrentThreadId();
  while ( 1 )
  {
    if ( !*(_QWORD *)(v15 + 24) )
    {
LABEL_6:
      ConditionVariable[1] = 0;
      LODWORD(v64) = 1;
      HIDWORD(v64) = GetCurrentThreadId();
      v65 = *(_QWORD *)(v15 + 24);
      *(_QWORD *)(v15 + 24) = &ConditionVariable[1];
      goto LABEL_7;
    }
    CurrentThreadId = GetCurrentThreadId();
    v45 = *(_QWORD *)(v15 + 24);
    if ( *(_DWORD *)(v45 + 12) == CurrentThreadId )
      break;
    if ( !v45 || v12 == *(_QWORD *)v45 && v12 )
      goto LABEL_6;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)v15, (PSRWLOCK)(v15 + 8));
  }
  ++*(_DWORD *)(v45 + 8);
LABEL_7:
  *(_DWORD *)(v15 + 16) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(v15 + 8));
  v66 = 1;
  if ( *(_BYTE *)(a1 + 654) && a3 == 7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147019873);
    throw (HResultException *)pExceptionObject;
  }
  v67[0] = a1;
  v67[1] = v53;
  v68 = *(_DWORD *)(a1 + 648);
  *(_OWORD *)v61 = 0;
  v16 = 0;
  v62 = 0;
  std::vector<_NETSETUPPROPKEY>::resize(v61, a6);
  for ( i = 0; i < a6; ++i )
  {
    v18 = 32LL * i;
    v19 = *(_OWORD *)(v18 + a7);
    v20 = *(_DWORD *)(v18 + a7 + 16);
    v21 = 5LL * i;
    v22 = v61[0];
    *(_OWORD *)((char *)v61[0] + 4 * v21) = v19;
    v22[v21 + 4] = v20;
  }
  *(_OWORD *)Block = 0;
  v60 = 0;
  v55 = v67;
  v56 = 0;
  v69 = a3;
  v70[0] = *a4;
  v70[1] = a4[1];
  if ( a3 == 9 )
  {
    v46 = *a4;
    if ( !*a4 )
      v46 = a4[1];
    if ( v46 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_421b3f26bfcd369eac764ae0d92226f2_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
      throw (HResultException *)pExceptionObject;
    }
    v24 = v67[0] + 232LL;
    *(_QWORD *)&v56 = v67[0] + 232LL;
  }
  else if ( (_WORD)a3 == 10 )
  {
    v47 = (char *)operator new(0x38u);
    v48 = v47;
    v53 = v47;
    if ( v47 )
    {
      v49 = *(_OWORD *)a4;
      *((_WORD *)v47 + 4) = 256;
      *(_QWORD *)v47 = &NetSetupReflectedProperty::`vftable'{for `INetSetupObject'};
      *((_QWORD *)v47 + 2) = &NetSetupReflectedProperty::`vftable'{for `INetSetupPropertyProvider'};
      *((_QWORD *)v47 + 6) = 0;
      *(_OWORD *)(v47 + 24) = v49;
      *((_DWORD *)v47 + 10) = HIWORD(a3);
      *((_QWORD *)v47 + 6) = GetPropertyRule((const struct _NETSETUPPROPKEY *)(v47 + 24));
      *((_QWORD *)&v56 + 1) = v48;
      v24 = (__int64)(v48 + 16);
      *(_QWORD *)&v56 = v24;
    }
    else
    {
      v24 = 0;
      *(_QWORD *)&v56 = 0;
    }
  }
  else
  {
    ObjectProvider = NetSetupObjectProviderFactory::GetObjectProvider(v67[0] + 480LL, a3);
    (*(void (__fastcall **)(__int64, char **, _QWORD *, _QWORD *))(*(_QWORD *)ObjectProvider + 16LL))(
      ObjectProvider,
      &v53,
      v67,
      v70);
    v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v53 + 32LL))(v53);
    *(_QWORD *)&v56 = v24;
    v25 = v54;
    if ( v54 )
    {
      if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
      v16 = 0;
    }
  }
  (*(void (__fastcall **)(__int64, __int64, void **, void **))(*(_QWORD *)v24 + 8LL))(v24, a1, v61, Block);
  v26 = (char *)Block[0];
  v27 = (char *)Block[1];
  if ( Block[0] == Block[1] )
  {
    *a8 = 0;
    *a9 = 0;
    if ( *((_QWORD *)&v56 + 1) )
    {
      (***((void (__fastcall ****)(_QWORD, __int64))&v56 + 1))(*((_QWORD *)&v56 + 1), 1);
      v27 = (char *)Block[1];
      v26 = (char *)Block[0];
    }
    if ( v26 )
    {
      if ( v26 != v27 )
      {
        do
        {
          std::vector<_NETSETUPPROPKEY>::_Tidy(v26 + 24);
          v26 += 48;
        }
        while ( v26 != v27 );
        v26 = (char *)Block[0];
      }
      operator delete(v26);
      *(_OWORD *)Block = 0;
      v60 = 0;
    }
    if ( v61[0] )
    {
      operator delete(v61[0]);
      *(_OWORD *)v61 = 0;
      v62 = 0;
    }
    StackLockHolder::~StackLockHolder((StackLockHolder *)ConditionVariable);
  }
  else
  {
    if ( (a5 & 4) != 0 )
    {
      while ( v26 != v27 )
      {
        ResolveIndirectString((NetSetup2::Property *)v26);
        v26 += 48;
      }
      v27 = (char *)Block[1];
      v26 = (char *)Block[0];
    }
    v28 = 0xAAAAAAAAAAAAAAABuLL * ((v27 - v26) >> 4);
    ProcessHeap = GetProcessHeap();
    v30 = HeapAlloc(ProcessHeap, 0, 48 * v28);
    v31 = v30;
    if ( !v30 )
    {
LABEL_80:
      *a9 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024882);
      throw (HResultException *)pExceptionObject;
    }
    memset_0(v30, 0, 48 * v28);
    v32 = (char *)Block[0];
    while ( 1 )
    {
      v33 = (char *)Block[1];
      v34 = 0xAAAAAAAAAAAAAAABuLL * (((char *)Block[1] - (char *)v32) >> 4);
      if ( v16 >= v34 )
        break;
      v35 = 6 * v16;
      *(_OWORD *)&v31[2 * v35] = *(_OWORD *)&v32[48 * v16];
      v31[2 * v35 + 4] = *(_DWORD *)&v32[48 * v16 + 16];
      v31[2 * v35 + 8] = *((_DWORD *)Block[0] + 12 * v16 + 5);
      v32 = (char *)Block[0];
      v36 = *((_QWORD *)Block[0] + 6 * v16 + 4);
      v37 = *((_QWORD *)Block[0] + 6 * v16 + 3);
      if ( v37 != v36 )
      {
        v38 = v36 - v37;
        v39 = GetProcessHeap();
        v40 = HeapAlloc(v39, 0, v38);
        *(_QWORD *)&v31[12 * v16 + 10] = v40;
        if ( !v40 )
        {
          for ( ; v16; --v16 )
          {
            v50 = *(void **)&v31[12 * v16 - 2];
            if ( v50 )
            {
              v51 = GetProcessHeap();
              HeapFree(v51, 0, v50);
            }
            v52 = GetProcessHeap();
            HeapFree(v52, 0, v31);
          }
          goto LABEL_80;
        }
        v31[12 * v16 + 9] = v38;
        memcpy_0(v40, *((const void **)Block[0] + 6 * v16 + 3), v38);
        v32 = (char *)Block[0];
      }
      ++v16;
    }
    *a9 = v31;
    *a8 = v34;
    if ( *((_QWORD *)&v56 + 1) )
    {
      (***((void (__fastcall ****)(_QWORD, __int64))&v56 + 1))(*((_QWORD *)&v56 + 1), 1);
      v33 = (char *)Block[1];
      v32 = (char *)Block[0];
    }
    if ( v32 )
    {
      if ( v32 != v33 )
      {
        do
        {
          std::vector<_NETSETUPPROPKEY>::_Tidy(v32 + 24);
          v32 += 48;
        }
        while ( v32 != v33 );
        v32 = (char *)Block[0];
      }
      operator delete(v32);
      *(_OWORD *)Block = 0;
      v60 = 0;
    }
    if ( v61[0] )
    {
      operator delete(v61[0]);
      *(_OWORD *)v61 = 0;
      v62 = 0;
    }
    if ( v66 )
    {
      v66 = 0;
      v41 = ConditionVariable[0];
      AcquireSRWLockExclusive((PSRWLOCK)&ConditionVariable[0][1]);
      LODWORD(v41[2].Ptr) = GetCurrentThreadId();
      --*((_DWORD *)v41[3].Ptr + 2);
      Ptr = (char *)v41[3].Ptr;
      v43 = (RTL_SRWLOCK *)&v41[1];
      if ( *((_DWORD *)Ptr + 2) )
      {
        LODWORD(v41[2].Ptr) = 0;
        ReleaseSRWLockExclusive(v43);
      }
      else
      {
        v41[3].Ptr = *(PVOID *)(Ptr + 16);
        LODWORD(v41[2].Ptr) = 0;
        ReleaseSRWLockExclusive(v43);
        WakeAllConditionVariable(v41);
      }
    }
  }
}

```

## disassembly

```asm
0x180008c90  push    rbp
0x180008c92  push    rbx
0x180008c93  push    rsi
0x180008c94  push    rdi
0x180008c95  push    r12
0x180008c97  push    r13
0x180008c99  push    r14
0x180008c9b  push    r15
0x180008c9d  lea     rbp, [rsp-0E8h]
0x180008ca5  sub     rsp, 1E8h
0x180008cac  mov     [rsp+220h+var_1B0], 0FFFFFFFFFFFFFFFEh
0x180008cb5  mov     rax, cs:__security_cookie
0x180008cbc  xor     rax, rsp
0x180008cbf  mov     [rbp+120h+var_50], rax
0x180008cc6  mov     r14, r9
0x180008cc9  mov     edi, r8d
0x180008ccc  mov     [rsp+220h+var_1E0], rdx
0x180008cd1  mov     r15, rcx
0x180008cd4  mov     eax, [rbp+120h+arg_28]
0x180008cda  mov     [rsp+220h+var_1F0], eax
0x180008cde  mov     rax, [rbp+120h+arg_38]
0x180008ce5  mov     [rsp+220h+var_1E8], rax
0x180008cea  mov     r12, [rbp+120h+arg_40]
0x180008cf1  xor     eax, eax
0x180008cf3  xorps   xmm0, xmm0
0x180008cf6  movdqu  xmmword ptr [rbp+120h+ConditionVariable], xmm0
0x180008cfb  mov     [rbp+120h+var_98], rax
0x180008d02  mov     [rbp+120h+var_90], rax
0x180008d09  mov     [rbp+120h+var_88], al
0x180008d0f  mov     r13d, eax
0x180008d12  mov     ecx, [rcx+358h]; dwTlsIndex
0x180008d18  cmp     ecx, 0FFFFFFFFh
0x180008d1b  jz      short loc_180008D2A
0x180008d1d  call    cs:__imp_TlsGetValue
0x180008d23  test    eax, eax
0x180008d25  jz      short loc_180008D2A
0x180008d27  mov     r13d, eax
0x180008d2a  mov     rbx, [r15+388h]
0x180008d31  mov     [rbp+120h+ConditionVariable], rbx
0x180008d35  lea     rcx, [rbx+8]; SRWLock
0x180008d39  call    cs:__imp_AcquireSRWLockExclusive
0x180008d3f  call    cs:__imp_GetCurrentThreadId
0x180008d45  mov     [rbx+10h], eax
0x180008d48  cmp     qword ptr [rbx+18h], 0
0x180008d4d  jnz     loc_18000911B
0x180008d53  xor     r13d, r13d
0x180008d56  mov     [rbp+120h+ConditionVariable+8], r13
0x180008d5d  mov     dword ptr [rbp+120h+var_98], 1
0x180008d67  call    cs:__imp_GetCurrentThreadId
0x180008d6d  mov     dword ptr [rbp+120h+var_98+4], eax
0x180008d73  mov     rax, [rbx+18h]
0x180008d77  mov     [rbp+120h+var_90], rax
0x180008d7e  lea     rax, [rbp+120h+ConditionVariable+8]
0x180008d85  mov     [rbx+18h], rax
0x180008d89  mov     [rbx+10h], r13d
0x180008d8d  lea     rcx, [rbx+8]; SRWLock
0x180008d91  call    cs:__imp_ReleaseSRWLockExclusive
0x180008d97  mov     [rbp+120h+var_88], 1
0x180008d9e  cmp     byte ptr [r15+28Eh], 0
0x180008da6  jnz     loc_1800092E1
0x180008dac  mov     [rbp+120h+var_80], r15
0x180008db3  mov     rax, [rsp+220h+var_1E0]
0x180008db8  mov     [rbp+120h+var_78], rax
0x180008dbf  mov     eax, [r15+288h]
0x180008dc6  mov     [rbp+120h+var_70], eax
0x180008dcc  xorps   xmm0, xmm0
0x180008dcf  movdqu  xmmword ptr [rbp+120h+var_C0], xmm0
0x180008dd4  xor     esi, esi
0x180008dd6  mov     [rbp+120h+var_B0], rsi
0x180008dda  mov     ebx, [rsp+220h+var_1F0]
0x180008dde  mov     edx, ebx
0x180008de0  lea     rcx, [rbp+120h+var_C0]
0x180008de4  call    ?resize@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@QEAAX_K@Z; std::vector<_NETSETUPPROPKEY>::resize(unsigned __int64)
0x180008de9  nop
0x180008dea  mov     r8d, esi
0x180008ded  test    ebx, ebx
0x180008def  jz      short loc_180008E24
0x180008df1  mov     r9, [rbp+120h+arg_30]
0x180008df8  mov     ecx, r8d
0x180008dfb  mov     eax, r8d
0x180008dfe  shl     rax, 5
0x180008e02  movups  xmm0, xmmword ptr [rax+r9]
0x180008e07  mov     edx, [rax+r9+10h]
0x180008e0c  lea     rcx, [rcx+rcx*4]
0x180008e10  mov     rax, [rbp+120h+var_C0]
0x180008e14  movups  xmmword ptr [rax+rcx*4], xmm0
0x180008e18  mov     [rax+rcx*4+10h], edx
0x180008e1c  inc     r8d
0x180008e1f  cmp     r8d, ebx
0x180008e22  jb      short loc_180008DF8
0x180008e24  xorps   xmm0, xmm0
0x180008e27  movdqu  xmmword ptr [rbp+120h+Block], xmm0
0x180008e2c  mov     [rbp+120h+var_C8], rsi
0x180008e30  lea     rax, [rbp+120h+var_80]
0x180008e37  mov     [rsp+220h+var_1D0], rax
0x180008e3c  movdqu  [rsp+220h+var_1C8], xmm0
0x180008e42  mov     [rbp+120h+var_68], edi
0x180008e48  mov     rax, [r14]
0x180008e4b  mov     [rbp+120h+var_64], rax
0x180008e52  mov     rax, [r14+8]
0x180008e56  mov     [rbp+120h+var_5C], rax
0x180008e5d  cmp     edi, 9
0x180008e60  jz      loc_18000915D
0x180008e66  cmp     di, 0Ah
0x180008e6a  jz      loc_1800091A4
0x180008e70  mov     rcx, [rbp+120h+var_80]
0x180008e77  add     rcx, 1E0h
0x180008e7e  mov     edx, edi
0x180008e80  call    ?GetObjectProvider@NetSetupObjectProviderFactory@@QEBAAEAVINetSetupObjectProvider@@W4_NETSETUP_OBJECT_TYPE@@@Z; NetSetupObjectProviderFactory::GetObjectProvider(_NETSETUP_OBJECT_TYPE)
0x180008e85  mov     r10, rax
0x180008e88  mov     rcx, [rax]
0x180008e8b  mov     rax, [rcx+10h]
0x180008e8f  lea     r9, [rbp+120h+var_64]
0x180008e96  lea     r8, [rbp+120h+var_80]
0x180008e9d  lea     rdx, [rsp+220h+var_1E0]
0x180008ea2  mov     rcx, r10
0x180008ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eaa  nop
0x180008eab  mov     rcx, [rsp+220h+var_1E0]
0x180008eb0  mov     rax, [rcx]
0x180008eb3  mov     rax, [rax+20h]
0x180008eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ebc  mov     rbx, rax
0x180008ebf  mov     qword ptr [rsp+220h+var_1C8], rax
0x180008ec4  mov     rdi, [rsp+220h+var_1D8]
0x180008ec9  test    rdi, rdi
0x180008ecc  jz      short loc_180008F08
0x180008ece  mov     esi, 0FFFFFFFFh
0x180008ed3  mov     ecx, esi
0x180008ed5  lock xadd [rdi+8], ecx
0x180008eda  cmp     ecx, 1
0x180008edd  jnz     short loc_180008F06
0x180008edf  mov     rax, [rdi]
0x180008ee2  mov     rcx, rdi
0x180008ee5  mov     rax, [rax]
0x180008ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eed  lock xadd [rdi+0Ch], esi
0x180008ef2  cmp     esi, 1
0x180008ef5  jnz     short loc_180008F06
0x180008ef7  mov     rax, [rdi]
0x180008efa  mov     rcx, rdi
0x180008efd  mov     rax, [rax+8]
0x180008f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f06  xor     esi, esi
0x180008f08  mov     rax, [rbx]
0x180008f0b  lea     r9, [rbp+120h+Block]
0x180008f0f  lea     r8, [rbp+120h+var_C0]
0x180008f13  mov     rdx, r15
0x180008f16  mov     rcx, rbx
0x180008f19  mov     rax, [rax+8]
0x180008f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f22  mov     rbx, [rbp+120h+Block]
0x180008f26  mov     rdi, [rbp+120h+Block+8]
0x180008f2a  cmp     rbx, rdi
0x180008f2d  jz      loc_180009236
0x180008f33  test    [rbp+120h+arg_20], 4
0x180008f3a  jnz     loc_1800092C1
0x180008f40  sub     rdi, rbx
0x180008f43  sar     rdi, 4
0x180008f47  mov     r13, 0AAAAAAAAAAAAAAABh
0x180008f51  imul    rdi, r13
0x180008f55  lea     rbx, [rdi+rdi*2]
0x180008f59  shl     rbx, 4
0x180008f5d  call    cs:__imp_GetProcessHeap
0x180008f63  mov     rcx, rax; hHeap
0x180008f66  mov     r8, rbx; dwBytes
0x180008f69  xor     edx, edx; dwFlags
0x180008f6b  call    cs:__imp_HeapAlloc
0x180008f71  mov     r14, rax
0x180008f74  test    rax, rax
0x180008f77  jz      loc_180009388
0x180008f7d  mov     r8, rbx; Size
0x180008f80  xor     edx, edx; Val
0x180008f82  mov     rcx, rax; void *
0x180008f85  call    memset_0
0x180008f8a  mov     rbx, [rbp+120h+Block]
0x180008f8e  mov     rdi, [rbp+120h+Block+8]
0x180008f92  mov     rax, rdi
0x180008f95  sub     rax, rbx
0x180008f98  sar     rax, 4
0x180008f9c  imul    rax, r13
0x180008fa0  cmp     rsi, rax
0x180008fa3  jnb     loc_18000902F
0x180008fa9  lea     r15, [rsi+rsi*2]
0x180008fad  add     r15, r15
0x180008fb0  movups  xmm0, xmmword ptr [rbx+r15*8]
0x180008fb5  movups  xmmword ptr [r14+r15*8], xmm0
0x180008fba  mov     eax, [rbx+r15*8+10h]
0x180008fbf  mov     [r14+r15*8+10h], eax
0x180008fc4  mov     rax, [rbp+120h+Block]
0x180008fc8  mov     ecx, [rax+r15*8+14h]
0x180008fcd  mov     [r14+r15*8+20h], ecx
0x180008fd2  mov     rbx, [rbp+120h+Block]
0x180008fd6  mov     rdi, [rbx+r15*8+20h]
0x180008fdb  mov     rax, [rbx+r15*8+18h]
0x180008fe0  cmp     rax, rdi
0x180008fe3  jz      short loc_180009027
0x180008fe5  sub     rdi, rax
0x180008fe8  call    cs:__imp_GetProcessHeap
0x180008fee  mov     rcx, rax; hHeap
0x180008ff1  mov     r8, rdi; dwBytes
0x180008ff4  xor     edx, edx; dwFlags
0x180008ff6  call    cs:__imp_HeapAlloc
0x180008ffc  mov     [r14+r15*8+28h], rax
0x180009001  test    rax, rax
0x180009004  jz      loc_18000938D
0x18000900a  mov     [r14+r15*8+24h], edi
0x18000900f  mov     r8, rdi; Size
0x180009012  mov     rdx, [rbp+120h+Block]
0x180009016  mov     rdx, [rdx+r15*8+18h]; Src
0x18000901b  mov     rcx, rax; void *
0x18000901e  call    memcpy_0
0x180009023  mov     rbx, [rbp+120h+Block]
0x180009027  inc     rsi
0x18000902a  jmp     loc_180008F8E
0x18000902f  mov     [r12], r14
0x180009033  mov     rcx, [rsp+220h+var_1E8]
0x180009038  mov     [rcx], eax
0x18000903a  mov     rcx, qword ptr [rsp+220h+var_1C8+8]
0x18000903f  test    rcx, rcx
0x180009042  jnz     loc_18000920C
0x180009048  test    rbx, rbx
0x18000904b  jz      loc_18000942A
0x180009051  cmp     rbx, rdi
0x180009054  jz      short loc_18000906C
0x180009056  lea     rcx, [rbx+18h]
0x18000905a  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18000905f  add     rbx, 30h ; '0'
0x180009063  cmp     rbx, rdi
0x180009066  jnz     short loc_180009056
0x180009068  mov     rbx, [rbp+120h+Block]
0x18000906c  mov     rcx, rbx; Block
0x18000906f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009074  xorps   xmm0, xmm0
0x180009077  movdqu  xmmword ptr [rbp+120h+Block], xmm0
0x18000907c  xor     r13d, r13d
0x18000907f  mov     [rbp+120h+var_C8], r13
0x180009083  mov     rcx, [rbp+120h+var_C0]; Block
0x180009087  test    rcx, rcx
0x18000908a  jz      short loc_18000909D
0x18000908c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009091  xorps   xmm0, xmm0
0x180009094  movdqu  xmmword ptr [rbp+120h+var_C0], xmm0
0x180009099  mov     [rbp+120h+var_B0], r13
0x18000909d  cmp     [rbp+120h+var_88], 0
0x1800090a4  jz      short loc_1800090F8
0x1800090a6  mov     [rbp+120h+var_88], 0
0x1800090ad  mov     rdi, [rbp+120h+ConditionVariable]
0x1800090b1  lea     rcx, [rdi+8]; SRWLock
0x1800090b5  call    cs:__imp_AcquireSRWLockExclusive
0x1800090bb  call    cs:__imp_GetCurrentThreadId
0x1800090c1  mov     [rdi+10h], eax
0x1800090c4  mov     rax, [rdi+18h]
0x1800090c8  dec     dword ptr [rax+8]
0x1800090cb  mov     rax, [rdi+18h]
0x1800090cf  lea     rcx, [rdi+8]; SRWLock
0x1800090d3  cmp     dword ptr [rax+8], 0
0x1800090d7  jnz     loc_180009195
0x1800090dd  mov     rax, [rax+10h]
0x1800090e1  mov     [rdi+18h], rax
0x1800090e5  mov     [rdi+10h], r13d
0x1800090e9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800090ef  mov     rcx, rdi; ConditionVariable
0x1800090f2  call    cs:__imp_WakeAllConditionVariable
0x1800090f8  mov     rcx, [rbp+120h+var_50]
0x1800090ff  xor     rcx, rsp; StackCookie
0x180009102  call    __security_check_cookie
0x180009107  add     rsp, 1E8h
0x18000910e  pop     r15
0x180009110  pop     r14
0x180009112  pop     r13
0x180009114  pop     r12
0x180009116  pop     rdi
0x180009117  pop     rsi
0x180009118  pop     rbx
0x180009119  pop     rbp
0x18000911a  retn
0x18000911b  call    cs:__imp_GetCurrentThreadId
0x180009121  mov     rcx, [rbx+18h]
0x180009125  cmp     [rcx+0Ch], eax
0x180009128  jz      short loc_180009152
0x18000912a  test    rcx, rcx
0x18000912d  jz      loc_180008D53
0x180009133  cmp     r13, [rcx]
0x180009136  jnz     short loc_180009141
0x180009138  test    r13, r13
0x18000913b  jnz     loc_180008D53
0x180009141  lea     rdx, [rbx+8]; SRWLock
0x180009145  mov     rcx, rbx; ConditionVariable
0x180009148  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x18000914d  jmp     loc_180008D48
0x180009152  inc     dword ptr [rcx+8]
0x180009155  xor     r13d, r13d
0x180009158  jmp     loc_180008D89
0x18000915d  mov     rax, [r14]
0x180009160  sub     rax, cs:qword_180099E70
0x180009167  jnz     short loc_180009174
0x180009169  mov     rax, [r14+8]
0x18000916d  sub     rax, cs:qword_180099E78
0x180009174  test    rax, rax
  ... truncated ...
```
