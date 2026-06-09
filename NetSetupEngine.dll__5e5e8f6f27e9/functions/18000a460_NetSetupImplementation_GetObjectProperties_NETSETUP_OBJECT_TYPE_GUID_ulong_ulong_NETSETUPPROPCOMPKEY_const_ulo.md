# NetSetupImplementation::GetObjectProperties(_NETSETUP_OBJECT_TYPE,_GUID,ulong,ulong,_NETSETUPPROPCOMPKEY const *,ulong *,_NETSETUPPROPERTY const * *)

- ea: `0x18000a460`
- end: `0x18000abeb`
- name: `?GetObjectProperties@NetSetupImplementation@@UEAAXW4_NETSETUP_OBJECT_TYPE@@U_GUID@@KKPEBU_NETSETUPPROPCOMPKEY@@PEAKPEAPEBU_NETSETUPPROPERTY@@@Z`
- size: `1931`
- prototype: `void __high(enum _NETSETUP_OBJECT_TYPE, struct _GUID, unsigned int, unsigned int, const struct _NETSETUPPROPCOMPKEY *, unsigned int *, const struct _NETSETUPPROPERTY **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180007fc8`
- `0x180008150`
- `0x18000a430`
- `0x18000a460`
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
- `0x180081096`
- `0x1800810a2`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a552`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a953`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a552`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a953`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a500`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a872`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a500`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a872`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a725`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a7b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a725`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a7b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a717`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a7a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a717`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a7a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab73`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a4e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a4e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a506`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a52b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a878`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a8d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a506`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a52b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a878`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a8d8`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000a8af`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000a8af`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall NetSetupImplementation::GetObjectProperties(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        char a4,
        unsigned int a5,
        __int64 a6,
        _DWORD *a7,
        _QWORD *a8)
{
  __int64 v10; // r14
  __int64 v11; // r15
  DWORD v12; // ecx
  unsigned int Value; // eax
  __int64 v14; // rbx
  unsigned int i; // r8d
  __int64 v16; // rax
  __int128 v17; // xmm0
  int v18; // edx
  __int64 v19; // rcx
  _DWORD *v20; // rax
  __int64 ObjectProvider; // rax
  __int64 v22; // rbx
  volatile signed __int32 *v23; // rdi
  char *v24; // rbx
  char *v25; // rdi
  unsigned __int64 v26; // rdi
  HANDLE ProcessHeap; // rax
  _DWORD *v28; // rax
  _DWORD *v29; // r14
  unsigned __int64 v30; // rsi
  char *v31; // rbx
  char *v32; // rdi
  unsigned __int64 v33; // rax
  __int64 v34; // r15
  __int64 v35; // rdi
  __int64 v36; // rax
  SIZE_T v37; // rdi
  HANDLE v38; // rax
  void *v39; // rax
  PCONDITION_VARIABLE v40; // rdi
  char *Ptr; // rax
  RTL_SRWLOCK *v42; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v44; // rcx
  char *v45; // rax
  char *v46; // rbx
  void *v47; // rbx
  HANDLE v48; // rax
  HANDLE v49; // rax
  __int128 v51; // [rsp+48h] [rbp-B8h]
  char *v52; // [rsp+58h] [rbp-A8h] BYREF
  volatile signed __int32 *v53; // [rsp+60h] [rbp-A0h]
  __int64 v54; // [rsp+68h] [rbp-98h]
  _BYTE pExceptionObject[208]; // [rsp+70h] [rbp-90h] BYREF
  void *Block[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v57; // [rsp+150h] [rbp+50h]
  void *v58[2]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v59; // [rsp+168h] [rbp+68h]
  PCONDITION_VARIABLE ConditionVariable[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v61; // [rsp+180h] [rbp+80h]
  __int64 v62; // [rsp+188h] [rbp+88h]
  char v63; // [rsp+190h] [rbp+90h]
  _QWORD v64[2]; // [rsp+198h] [rbp+98h] BYREF
  int v65; // [rsp+1A8h] [rbp+A8h]
  unsigned int v66; // [rsp+1B0h] [rbp+B0h]
  _QWORD v67[2]; // [rsp+1B4h] [rbp+B4h] BYREF

  v54 = -2;
  v10 = a1 + 24;
  *(_OWORD *)ConditionVariable = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v11 = 0;
  v12 = *(_DWORD *)(a1 + 880);
  if ( v12 != -1 )
  {
    Value = (unsigned int)TlsGetValue(v12);
    if ( Value )
      v11 = Value;
  }
  v14 = *(_QWORD *)(v10 + 904);
  ConditionVariable[0] = (PCONDITION_VARIABLE)v14;
  AcquireSRWLockExclusive((PSRWLOCK)(v14 + 8));
  *(_DWORD *)(v14 + 16) = GetCurrentThreadId();
  while ( 1 )
  {
    if ( !*(_QWORD *)(v14 + 24) )
    {
LABEL_6:
      ConditionVariable[1] = 0;
      LODWORD(v61) = 1;
      HIDWORD(v61) = GetCurrentThreadId();
      v62 = *(_QWORD *)(v14 + 24);
      *(_QWORD *)(v14 + 24) = &ConditionVariable[1];
      goto LABEL_7;
    }
    CurrentThreadId = GetCurrentThreadId();
    v44 = *(_QWORD *)(v14 + 24);
    if ( *(_DWORD *)(v44 + 12) == CurrentThreadId )
      break;
    if ( !v44 || v11 == *(_QWORD *)v44 && v11 )
      goto LABEL_6;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)v14, (PSRWLOCK)(v14 + 8));
  }
  ++*(_DWORD *)(v44 + 8);
LABEL_7:
  *(_DWORD *)(v14 + 16) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(v14 + 8));
  v63 = 1;
  if ( *(_BYTE *)(v10 + 654) && a2 == 7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147019873);
    throw (HResultException *)pExceptionObject;
  }
  v64[0] = v10;
  v64[1] = 0;
  v65 = *(_DWORD *)(v10 + 648);
  *(_OWORD *)v58 = 0;
  v59 = 0;
  std::vector<_NETSETUPPROPKEY>::resize(v58, a5);
  for ( i = 0; i < a5; ++i )
  {
    v16 = 32LL * i;
    v17 = *(_OWORD *)(v16 + a6);
    v18 = *(_DWORD *)(v16 + a6 + 16);
    v19 = 5LL * i;
    v20 = v58[0];
    *(_OWORD *)((char *)v58[0] + 4 * v19) = v17;
    v20[v19 + 4] = v18;
  }
  *(_OWORD *)Block = 0;
  v57 = 0;
  v51 = 0;
  v66 = a2;
  v67[0] = *a3;
  v67[1] = a3[1];
  if ( a2 == 9 )
  {
    if ( memcmp_0(a3, &qword_180099E70, 0x10u) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_421b3f26bfcd369eac764ae0d92226f2_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
      throw (HResultException *)pExceptionObject;
    }
    v22 = v64[0] + 232LL;
  }
  else if ( (_WORD)a2 == 10 )
  {
    v45 = (char *)operator new(0x38u);
    v46 = v45;
    v52 = v45;
    if ( v45 )
    {
      *((_WORD *)v45 + 4) = 256;
      *(_QWORD *)v45 = &NetSetupReflectedProperty::`vftable'{for `INetSetupObject'};
      *((_QWORD *)v45 + 2) = &NetSetupReflectedProperty::`vftable'{for `INetSetupPropertyProvider'};
      *((_QWORD *)v45 + 6) = 0;
      *(_OWORD *)(v45 + 24) = *(_OWORD *)a3;
      *((_DWORD *)v45 + 10) = HIWORD(a2);
      *((_QWORD *)v45 + 6) = GetPropertyRule((const struct _NETSETUPPROPKEY *)(v45 + 24));
      *((_QWORD *)&v51 + 1) = v46;
      v22 = (__int64)(v46 + 16);
    }
    else
    {
      v22 = 0;
    }
  }
  else
  {
    ObjectProvider = NetSetupObjectProviderFactory::GetObjectProvider(v64[0] + 480LL, a2);
    (*(void (__fastcall **)(__int64, char **, _QWORD *, _QWORD *))(*(_QWORD *)ObjectProvider + 16LL))(
      ObjectProvider,
      &v52,
      v64,
      v67);
    v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v52 + 32LL))(v52);
    v23 = v53;
    if ( v53 )
    {
      if ( _InterlockedExchangeAdd(v53 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
  }
  (*(void (__fastcall **)(__int64, __int64, void **, void **))(*(_QWORD *)v22 + 8LL))(v22, v10, v58, Block);
  v24 = (char *)Block[0];
  v25 = (char *)Block[1];
  if ( Block[0] == Block[1] )
  {
    *a7 = 0;
    *a8 = 0;
    if ( *((_QWORD *)&v51 + 1) )
    {
      (***((void (__fastcall ****)(_QWORD, __int64))&v51 + 1))(*((_QWORD *)&v51 + 1), 1);
      v25 = (char *)Block[1];
      v24 = (char *)Block[0];
    }
    if ( v24 )
    {
      if ( v24 != v25 )
      {
        do
        {
          std::vector<_NETSETUPPROPKEY>::_Tidy(v24 + 24);
          v24 += 48;
        }
        while ( v24 != v25 );
        v24 = (char *)Block[0];
      }
      operator delete(v24);
      *(_OWORD *)Block = 0;
      v57 = 0;
    }
    if ( v58[0] )
    {
      operator delete(v58[0]);
      *(_OWORD *)v58 = 0;
      v59 = 0;
    }
    StackLockHolder::~StackLockHolder((StackLockHolder *)ConditionVariable);
  }
  else
  {
    if ( (a4 & 4) != 0 )
    {
      while ( v24 != v25 )
      {
        ResolveIndirectString((NetSetup2::Property *)v24);
        v24 += 48;
      }
      v25 = (char *)Block[1];
      v24 = (char *)Block[0];
    }
    v26 = 0xAAAAAAAAAAAAAAABuLL * ((v25 - v24) >> 4);
    ProcessHeap = GetProcessHeap();
    v28 = HeapAlloc(ProcessHeap, 0, 48 * v26);
    v29 = v28;
    if ( !v28 )
    {
LABEL_77:
      *a8 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024882);
      throw (HResultException *)pExceptionObject;
    }
    memset_0(v28, 0, 48 * v26);
    v30 = 0;
    v31 = (char *)Block[0];
    while ( 1 )
    {
      v32 = (char *)Block[1];
      v33 = 0xAAAAAAAAAAAAAAABuLL * (((char *)Block[1] - (char *)v31) >> 4);
      if ( v30 >= v33 )
        break;
      v34 = 6 * v30;
      *(_OWORD *)&v29[2 * v34] = *(_OWORD *)&v31[48 * v30];
      v29[2 * v34 + 4] = *(_DWORD *)&v31[48 * v30 + 16];
      v29[2 * v34 + 8] = *((_DWORD *)Block[0] + 12 * v30 + 5);
      v31 = (char *)Block[0];
      v35 = *((_QWORD *)Block[0] + 6 * v30 + 4);
      v36 = *((_QWORD *)Block[0] + 6 * v30 + 3);
      if ( v36 != v35 )
      {
        v37 = v35 - v36;
        v38 = GetProcessHeap();
        v39 = HeapAlloc(v38, 0, v37);
        *(_QWORD *)&v29[12 * v30 + 10] = v39;
        if ( !v39 )
        {
          for ( ; v30; --v30 )
          {
            v47 = *(void **)&v29[12 * v30 - 2];
            if ( v47 )
            {
              v48 = GetProcessHeap();
              HeapFree(v48, 0, v47);
            }
            v49 = GetProcessHeap();
            HeapFree(v49, 0, v29);
          }
          goto LABEL_77;
        }
        v29[12 * v30 + 9] = v37;
        memcpy_0(v39, *((const void **)Block[0] + 6 * v30 + 3), v37);
        v31 = (char *)Block[0];
      }
      ++v30;
    }
    *a8 = v29;
    *a7 = v33;
    if ( *((_QWORD *)&v51 + 1) )
    {
      (***((void (__fastcall ****)(_QWORD, __int64))&v51 + 1))(*((_QWORD *)&v51 + 1), 1);
      v32 = (char *)Block[1];
      v31 = (char *)Block[0];
    }
    if ( v31 )
    {
      if ( v31 != v32 )
      {
        do
        {
          std::vector<_NETSETUPPROPKEY>::_Tidy(v31 + 24);
          v31 += 48;
        }
        while ( v31 != v32 );
        v31 = (char *)Block[0];
      }
      operator delete(v31);
      *(_OWORD *)Block = 0;
      v57 = 0;
    }
    if ( v58[0] )
    {
      operator delete(v58[0]);
      *(_OWORD *)v58 = 0;
      v59 = 0;
    }
    if ( v63 )
    {
      v63 = 0;
      v40 = ConditionVariable[0];
      AcquireSRWLockExclusive((PSRWLOCK)&ConditionVariable[0][1]);
      LODWORD(v40[2].Ptr) = GetCurrentThreadId();
      --*((_DWORD *)v40[3].Ptr + 2);
      Ptr = (char *)v40[3].Ptr;
      v42 = (RTL_SRWLOCK *)&v40[1];
      if ( *((_DWORD *)Ptr + 2) )
      {
        LODWORD(v40[2].Ptr) = 0;
        ReleaseSRWLockExclusive(v42);
      }
      else
      {
        v40[3].Ptr = *(PVOID *)(Ptr + 16);
        LODWORD(v40[2].Ptr) = 0;
        ReleaseSRWLockExclusive(v42);
        WakeAllConditionVariable(v40);
      }
    }
  }
}

```

## disassembly

```asm
0x18000a460  push    rbp
0x18000a462  push    rbx
0x18000a463  push    rsi
0x18000a464  push    rdi
0x18000a465  push    r12
0x18000a467  push    r13
0x18000a469  push    r14
0x18000a46b  push    r15
0x18000a46d  lea     rbp, [rsp-0D8h]
0x18000a475  sub     rsp, 1D8h
0x18000a47c  mov     [rsp+210h+var_1A8], 0FFFFFFFFFFFFFFFEh
0x18000a485  mov     rax, cs:__security_cookie
0x18000a48c  xor     rax, rsp
0x18000a48f  mov     [rbp+110h+var_48], rax
0x18000a496  mov     [rsp+210h+var_1E0], r9d
0x18000a49b  mov     r13, r8
0x18000a49e  mov     edi, edx
0x18000a4a0  mov     rax, [rbp+110h+arg_30]
0x18000a4a7  mov     [rsp+210h+var_1D8], rax
0x18000a4ac  mov     r12, [rbp+110h+arg_38]
0x18000a4b3  xor     eax, eax
0x18000a4b5  lea     r14, [rcx+18h]
0x18000a4b9  xorps   xmm0, xmm0
0x18000a4bc  movdqu  xmmword ptr [rbp+110h+ConditionVariable], xmm0
0x18000a4c1  mov     [rbp+110h+var_90], rax
0x18000a4c8  mov     [rbp+110h+var_88], rax
0x18000a4cf  mov     [rbp+110h+var_80], al
0x18000a4d5  mov     r15d, eax
0x18000a4d8  mov     ecx, [r14+358h]; dwTlsIndex
0x18000a4df  cmp     ecx, 0FFFFFFFFh
0x18000a4e2  jz      short loc_18000A4F1
0x18000a4e4  call    cs:__imp_TlsGetValue
0x18000a4ea  test    eax, eax
0x18000a4ec  jz      short loc_18000A4F1
0x18000a4ee  mov     r15d, eax
0x18000a4f1  mov     rbx, [r14+388h]
0x18000a4f8  mov     [rbp+110h+ConditionVariable], rbx
0x18000a4fc  lea     rcx, [rbx+8]; SRWLock
0x18000a500  call    cs:__imp_AcquireSRWLockExclusive
0x18000a506  call    cs:__imp_GetCurrentThreadId
0x18000a50c  mov     [rbx+10h], eax
0x18000a50f  cmp     qword ptr [rbx+18h], 0
0x18000a514  jnz     loc_18000A8D8
0x18000a51a  xor     r15d, r15d
0x18000a51d  mov     [rbp+110h+ConditionVariable+8], r15
0x18000a521  mov     dword ptr [rbp+110h+var_90], 1
0x18000a52b  call    cs:__imp_GetCurrentThreadId
0x18000a531  mov     dword ptr [rbp+110h+var_90+4], eax
0x18000a537  mov     rax, [rbx+18h]
0x18000a53b  mov     [rbp+110h+var_88], rax
0x18000a542  lea     rax, [rbp+110h+ConditionVariable+8]
0x18000a546  mov     [rbx+18h], rax
0x18000a54a  mov     [rbx+10h], r15d
0x18000a54e  lea     rcx, [rbx+8]; SRWLock
0x18000a552  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a558  mov     [rbp+110h+var_80], 1
0x18000a55f  cmp     byte ptr [r14+28Eh], 0
0x18000a567  jnz     loc_18000AA9D
0x18000a56d  mov     [rbp+110h+var_78], r14
0x18000a574  mov     [rbp+110h+var_70], r15
0x18000a57b  mov     eax, [r14+288h]
0x18000a582  mov     [rbp+110h+var_68], eax
0x18000a588  xorps   xmm0, xmm0
0x18000a58b  movdqu  xmmword ptr [rbp+110h+var_B8], xmm0
0x18000a590  mov     [rbp+110h+var_A8], r15
0x18000a594  mov     ebx, [rbp+110h+arg_20]
0x18000a59a  mov     edx, ebx
0x18000a59c  lea     rcx, [rbp+110h+var_B8]
0x18000a5a0  call    ?resize@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@QEAAX_K@Z; std::vector<_NETSETUPPROPKEY>::resize(unsigned __int64)
0x18000a5a5  nop
0x18000a5a6  mov     r8d, r15d
0x18000a5a9  test    ebx, ebx
0x18000a5ab  jz      short loc_18000A5E0
0x18000a5ad  mov     r9, [rbp+110h+arg_28]
0x18000a5b4  mov     ecx, r8d
0x18000a5b7  mov     eax, r8d
0x18000a5ba  shl     rax, 5
0x18000a5be  movups  xmm0, xmmword ptr [rax+r9]
0x18000a5c3  mov     edx, [rax+r9+10h]
0x18000a5c8  lea     rcx, [rcx+rcx*4]
0x18000a5cc  mov     rax, [rbp+110h+var_B8]
0x18000a5d0  movups  xmmword ptr [rax+rcx*4], xmm0
0x18000a5d4  mov     [rax+rcx*4+10h], edx
0x18000a5d8  inc     r8d
0x18000a5db  cmp     r8d, ebx
0x18000a5de  jb      short loc_18000A5B4
0x18000a5e0  xorps   xmm0, xmm0
0x18000a5e3  movdqu  xmmword ptr [rbp+110h+Block], xmm0
0x18000a5e8  mov     [rbp+110h+var_C0], r15
0x18000a5ec  lea     rax, [rbp+110h+var_78]
0x18000a5f3  mov     [rsp+210h+var_1D0], rax
0x18000a5f8  movdqu  [rsp+210h+var_1C8], xmm0
0x18000a5fe  mov     [rbp+110h+var_60], edi
0x18000a604  mov     rax, [r13+0]
0x18000a608  mov     [rbp+110h+var_5C], rax
0x18000a60f  mov     rax, [r13+8]
0x18000a613  mov     [rbp+110h+var_54], rax
0x18000a61a  cmp     edi, 9
0x18000a61d  jz      loc_18000A91A
0x18000a623  cmp     di, 0Ah
0x18000a627  jz      loc_18000A95E
0x18000a62d  mov     rcx, [rbp+110h+var_78]
0x18000a634  add     rcx, 1E0h
0x18000a63b  mov     edx, edi
0x18000a63d  call    ?GetObjectProvider@NetSetupObjectProviderFactory@@QEBAAEAVINetSetupObjectProvider@@W4_NETSETUP_OBJECT_TYPE@@@Z; NetSetupObjectProviderFactory::GetObjectProvider(_NETSETUP_OBJECT_TYPE)
0x18000a642  mov     r10, rax
0x18000a645  mov     rcx, [rax]
0x18000a648  mov     rax, [rcx+10h]
0x18000a64c  lea     r9, [rbp+110h+var_5C]
0x18000a653  lea     r8, [rbp+110h+var_78]
0x18000a65a  lea     rdx, [rsp+210h+var_1B8]
0x18000a65f  mov     rcx, r10
0x18000a662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a667  nop
0x18000a668  mov     rcx, [rsp+210h+var_1B8]
0x18000a66d  mov     rax, [rcx]
0x18000a670  mov     rax, [rax+20h]
0x18000a674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a679  mov     rbx, rax
0x18000a67c  mov     qword ptr [rsp+210h+var_1C8], rax
0x18000a681  mov     rdi, [rsp+210h+var_1B0]
0x18000a686  test    rdi, rdi
0x18000a689  jz      short loc_18000A6C4
0x18000a68b  mov     esi, 0FFFFFFFFh
0x18000a690  mov     ecx, esi
0x18000a692  lock xadd [rdi+8], ecx
0x18000a697  cmp     ecx, 1
0x18000a69a  jnz     short loc_18000A6C4
0x18000a69c  mov     rax, [rdi]
0x18000a69f  mov     rcx, rdi
0x18000a6a2  mov     rax, [rax]
0x18000a6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6aa  lock xadd [rdi+0Ch], esi
0x18000a6af  cmp     esi, 1
0x18000a6b2  jnz     short loc_18000A6C4
0x18000a6b4  mov     rax, [rdi]
0x18000a6b7  mov     rcx, rdi
0x18000a6ba  mov     rax, [rax+8]
0x18000a6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c3  nop
0x18000a6c4  mov     rax, [rbx]
0x18000a6c7  lea     r9, [rbp+110h+Block]
0x18000a6cb  lea     r8, [rbp+110h+var_B8]
0x18000a6cf  mov     rdx, r14
0x18000a6d2  mov     rcx, rbx
0x18000a6d5  mov     rax, [rax+8]
0x18000a6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6de  mov     rbx, [rbp+110h+Block]
0x18000a6e2  mov     rdi, [rbp+110h+Block+8]
0x18000a6e6  cmp     rbx, rdi
0x18000a6e9  jz      loc_18000A9F1
0x18000a6ef  test    byte ptr [rsp+210h+var_1E0], 4
0x18000a6f4  jnz     loc_18000AA7D
0x18000a6fa  sub     rdi, rbx
0x18000a6fd  sar     rdi, 4
0x18000a701  mov     r13, 0AAAAAAAAAAAAAAABh
0x18000a70b  imul    rdi, r13
0x18000a70f  lea     rbx, [rdi+rdi*2]
0x18000a713  shl     rbx, 4
0x18000a717  call    cs:__imp_GetProcessHeap
0x18000a71d  mov     rcx, rax; hHeap
0x18000a720  mov     r8, rbx; dwBytes
0x18000a723  xor     edx, edx; dwFlags
0x18000a725  call    cs:__imp_HeapAlloc
0x18000a72b  mov     r14, rax
0x18000a72e  test    rax, rax
0x18000a731  jz      loc_18000AB44
0x18000a737  mov     r8, rbx; Size
0x18000a73a  xor     edx, edx; Val
0x18000a73c  mov     rcx, rax; void *
0x18000a73f  call    memset_0
0x18000a744  mov     rsi, r15
0x18000a747  mov     rbx, [rbp+110h+Block]
0x18000a74b  mov     rdi, [rbp+110h+Block+8]
0x18000a74f  mov     rax, rdi
0x18000a752  sub     rax, rbx
0x18000a755  sar     rax, 4
0x18000a759  imul    rax, r13
0x18000a75d  cmp     rsi, rax
0x18000a760  jnb     loc_18000A7EC
0x18000a766  lea     r15, [rsi+rsi*2]
0x18000a76a  add     r15, r15
0x18000a76d  movups  xmm0, xmmword ptr [rbx+r15*8]
0x18000a772  movups  xmmword ptr [r14+r15*8], xmm0
0x18000a777  mov     eax, [rbx+r15*8+10h]
0x18000a77c  mov     [r14+r15*8+10h], eax
0x18000a781  mov     rax, [rbp+110h+Block]
0x18000a785  mov     ecx, [rax+r15*8+14h]
0x18000a78a  mov     [r14+r15*8+20h], ecx
0x18000a78f  mov     rbx, [rbp+110h+Block]
0x18000a793  mov     rdi, [rbx+r15*8+20h]
0x18000a798  mov     rax, [rbx+r15*8+18h]
0x18000a79d  cmp     rax, rdi
0x18000a7a0  jz      short loc_18000A7E4
0x18000a7a2  sub     rdi, rax
0x18000a7a5  call    cs:__imp_GetProcessHeap
0x18000a7ab  mov     rcx, rax; hHeap
0x18000a7ae  mov     r8, rdi; dwBytes
0x18000a7b1  xor     edx, edx; dwFlags
0x18000a7b3  call    cs:__imp_HeapAlloc
0x18000a7b9  mov     [r14+r15*8+28h], rax
0x18000a7be  test    rax, rax
0x18000a7c1  jz      loc_18000AB49
0x18000a7c7  mov     [r14+r15*8+24h], edi
0x18000a7cc  mov     r8, rdi; Size
0x18000a7cf  mov     rdx, [rbp+110h+Block]
0x18000a7d3  mov     rdx, [rdx+r15*8+18h]; Src
0x18000a7d8  mov     rcx, rax; void *
0x18000a7db  call    memcpy_0
0x18000a7e0  mov     rbx, [rbp+110h+Block]
0x18000a7e4  inc     rsi
0x18000a7e7  jmp     loc_18000A74B
0x18000a7ec  mov     [r12], r14
0x18000a7f0  mov     rcx, [rsp+210h+var_1D8]
0x18000a7f5  mov     [rcx], eax
0x18000a7f7  mov     rcx, qword ptr [rsp+210h+var_1C8+8]
0x18000a7fc  test    rcx, rcx
0x18000a7ff  jnz     loc_18000A9C7
0x18000a805  test    rbx, rbx
0x18000a808  jz      loc_18000ABE2
0x18000a80e  cmp     rbx, rdi
0x18000a811  jz      short loc_18000A829
0x18000a813  lea     rcx, [rbx+18h]
0x18000a817  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18000a81c  add     rbx, 30h ; '0'
0x18000a820  cmp     rbx, rdi
0x18000a823  jnz     short loc_18000A813
0x18000a825  mov     rbx, [rbp+110h+Block]
0x18000a829  mov     rcx, rbx; Block
0x18000a82c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a831  xorps   xmm0, xmm0
0x18000a834  movdqu  xmmword ptr [rbp+110h+Block], xmm0
0x18000a839  xor     r15d, r15d
0x18000a83c  mov     [rbp+110h+var_C0], r15
0x18000a840  mov     rcx, [rbp+110h+var_B8]; Block
0x18000a844  test    rcx, rcx
0x18000a847  jz      short loc_18000A85A
0x18000a849  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a84e  xorps   xmm0, xmm0
0x18000a851  movdqu  xmmword ptr [rbp+110h+var_B8], xmm0
0x18000a856  mov     [rbp+110h+var_A8], r15
0x18000a85a  cmp     [rbp+110h+var_80], 0
0x18000a861  jz      short loc_18000A8B5
0x18000a863  mov     [rbp+110h+var_80], 0
0x18000a86a  mov     rdi, [rbp+110h+ConditionVariable]
0x18000a86e  lea     rcx, [rdi+8]; SRWLock
0x18000a872  call    cs:__imp_AcquireSRWLockExclusive
0x18000a878  call    cs:__imp_GetCurrentThreadId
0x18000a87e  mov     [rdi+10h], eax
0x18000a881  mov     rax, [rdi+18h]
0x18000a885  dec     dword ptr [rax+8]
0x18000a888  mov     rax, [rdi+18h]
0x18000a88c  lea     rcx, [rdi+8]; SRWLock
0x18000a890  cmp     dword ptr [rax+8], 0
0x18000a894  jnz     loc_18000A94F
0x18000a89a  mov     rax, [rax+10h]
0x18000a89e  mov     [rdi+18h], rax
0x18000a8a2  mov     [rdi+10h], r15d
0x18000a8a6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a8ac  mov     rcx, rdi; ConditionVariable
0x18000a8af  call    cs:__imp_WakeAllConditionVariable
0x18000a8b5  mov     rcx, [rbp+110h+var_48]
0x18000a8bc  xor     rcx, rsp; StackCookie
0x18000a8bf  call    __security_check_cookie
0x18000a8c4  add     rsp, 1D8h
0x18000a8cb  pop     r15
0x18000a8cd  pop     r14
0x18000a8cf  pop     r13
0x18000a8d1  pop     r12
0x18000a8d3  pop     rdi
0x18000a8d4  pop     rsi
0x18000a8d5  pop     rbx
0x18000a8d6  pop     rbp
0x18000a8d7  retn
0x18000a8d8  call    cs:__imp_GetCurrentThreadId
0x18000a8de  mov     rcx, [rbx+18h]
0x18000a8e2  cmp     [rcx+0Ch], eax
0x18000a8e5  jz      short loc_18000A90F
0x18000a8e7  test    rcx, rcx
0x18000a8ea  jz      loc_18000A51A
0x18000a8f0  cmp     r15, [rcx]
0x18000a8f3  jnz     short loc_18000A8FE
0x18000a8f5  test    r15, r15
0x18000a8f8  jnz     loc_18000A51A
0x18000a8fe  lea     rdx, [rbx+8]; SRWLock
0x18000a902  mov     rcx, rbx; ConditionVariable
0x18000a905  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x18000a90a  jmp     loc_18000A50F
0x18000a90f  inc     dword ptr [rcx+8]
0x18000a912  xor     r15d, r15d
0x18000a915  jmp     loc_18000A54A
0x18000a91a  mov     r8d, 10h; Size
0x18000a920  lea     rdx, qword_180099E70; Buf2
0x18000a927  mov     rcx, r13; Buf1
0x18000a92a  call    memcmp_0
0x18000a92f  test    eax, eax
0x18000a931  jnz     loc_18000AAF5
0x18000a937  mov     rbx, [rbp+110h+var_78]
0x18000a93e  add     rbx, 0E8h
0x18000a945  mov     qword ptr [rsp+210h+var_1C8], rbx
  ... truncated ...
```
