# StorageReserveTelemetry::Internal::SRProvider::SetReserveAreaOnFileTree::Stop(ushort const *,ushort,long)

- ea: `0x18002b8c4`
- end: `0x18002bc5c`
- name: `?Stop@SetReserveAreaOnFileTree@SRProvider@Internal@StorageReserveTelemetry@@QEAAXPEBGGJ@Z`
- size: `920`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::SetReserveAreaOnFileTree *this, const unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002a1fc`

## callees

- `0x180002550`
- `0x180002b64`
- `0x180003870`
- `0x1800042dc`
- `0x1800042f4`
- `0x180028494`
- `0x180028738`
- `0x180028ac8`
- `0x18002939c`
- `0x18002b8c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b96f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bb48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b96f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bb48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bc1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bc1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bc28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bc28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bba8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bba8`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::SetReserveAreaOnFileTree::Stop(
        StorageReserveTelemetry::Internal::SRProvider::SetReserveAreaOnFileTree *this,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4)
{
  __int64 v7; // rbx
  int v8; // eax
  int *v9; // rbx
  const struct _tlgProvider_t *v10; // rax
  const struct _tlgProvider_t *v11; // r14
  __int64 v12; // rax
  __int64 v13; // r9
  PSRWLOCK v14; // rbx
  const struct _tlgProvider_t *v15; // rax
  const struct _tlgProvider_t *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  HANDLE ProcessHeap; // rax
  _WORD v21[2]; // [rsp+C8h] [rbp-80h] BYREF
  int v22; // [rsp+CCh] [rbp-7Ch] BYREF
  __int64 v23; // [rsp+D0h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+D8h] [rbp-70h] BYREF
  PSRWLOCK v25; // [rsp+E0h] [rbp-68h] BYREF
  int v26; // [rsp+E8h] [rbp-60h] BYREF
  int v27; // [rsp+ECh] [rbp-5Ch] BYREF
  int v28; // [rsp+F0h] [rbp-58h] BYREF
  int v29; // [rsp+F4h] [rbp-54h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-50h] BYREF
  __int64 v31; // [rsp+100h] [rbp-48h] BYREF
  __int64 v32; // [rsp+108h] [rbp-40h] BYREF
  __int64 v33; // [rsp+110h] [rbp-38h] BYREF
  __int64 v34; // [rsp+118h] [rbp-30h] BYREF
  __int64 v35; // [rsp+120h] [rbp-28h] BYREF
  __int64 v36; // [rsp+128h] [rbp-20h] BYREF
  __int64 v37; // [rsp+130h] [rbp-18h] BYREF
  __int64 v38; // [rsp+138h] [rbp-10h] BYREF
  __int64 v39; // [rsp+140h] [rbp-8h] BYREF
  __int64 v40[2]; // [rsp+148h] [rbp+0h] BYREF
  wchar_t Destination[264]; // [rsp+158h] [rbp+10h] BYREF

  v40[1] = -2;
  memset_0(Destination, 0, 0x208u);
  wcscpy_s(Destination, 0x104u, a2);
  v7 = *((_QWORD *)this + 34);
  v8 = *(_DWORD *)(v7 + 72);
  if ( v8 < 0 && (v9 = (int *)(v7 + 80), v8 == v9[2]) && v9 )
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v10 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v11 = v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      v12 = *((_QWORD *)v10 + 3);
      if ( (*((_QWORD *)v11 + 2) & 0x400000000000LL) != 0 && (v12 & 0x400000000000LL) == v12 )
      {
        v26 = a4;
        v21[0] = 2;
        v32 = (__int64)*StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
                          (unsigned __int16 **)&v25,
                          Destination);
        v33 = *((_QWORD *)v9 + 15);
        v34 = *((_QWORD *)v9 + 14);
        v27 = v9[26];
        v35 = *((_QWORD *)v9 + 12);
        v36 = *((_QWORD *)v9 + 11);
        v28 = v9[20];
        v37 = *((_QWORD *)v9 + 9);
        v29 = v9[8];
        v38 = *((_QWORD *)v9 + 3);
        v22 = *v9;
        v39 = *((_QWORD *)v9 + 16);
        LODWORD(v23) = v9[16];
        v40[0] = *((_QWORD *)v9 + 7);
        LODWORD(SRWLock) = v9[2];
        v30 = 0x1000000;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
          (int)v11,
          (int)&byte_1800444A5,
          *((_QWORD *)this + 34) + 8,
          v13,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&SRWLock,
          (const wchar_t **)v40,
          (__int64)&v23,
          (const wchar_t **)&v39,
          (__int64)&v22,
          (const unsigned __int16 **)&v38,
          (__int64)&v29,
          (const wchar_t **)&v37,
          (__int64)&v28,
          (const wchar_t **)&v36,
          (const unsigned __int16 **)&v35,
          (__int64)&v27,
          (const wchar_t **)&v34,
          (const unsigned __int16 **)&v33,
          (const unsigned __int16 **)&v32,
          (__int64)v21,
          (__int64)&v26);
        v14 = v25;
        goto LABEL_16;
      }
    }
  }
  else
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v25);
    **((_DWORD **)this + 34) = 2;
    if ( v25 )
      ReleaseSRWLockExclusive(v25);
    v15 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v16 = v15;
    if ( *(_DWORD *)v15 > 5u )
    {
      v17 = *((_QWORD *)v15 + 3);
      if ( (*((_QWORD *)v16 + 2) & 0x400000000000LL) != 0 && (v17 & 0x400000000000LL) == v17 )
      {
        LODWORD(SRWLock) = a4;
        v21[0] = 2;
        v25 = (PSRWLOCK)*StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
                           (unsigned __int16 **)&v30,
                           Destination);
        LODWORD(v23) = GetCurrentThreadId();
        v18 = *((_QWORD *)this + 34);
        v22 = *(_DWORD *)(v18 + 72);
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
          (int)v16,
          (int)&dword_180044434,
          v18 + 8,
          v19,
          (__int64)&v31,
          (__int64)&v22,
          (__int64)&v23,
          (const unsigned __int16 **)&v25,
          (__int64)v21,
          (__int64)&SRWLock);
        v14 = (PSRWLOCK)v30;
LABEL_16:
        if ( v14 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v14);
        }
      }
    }
  }
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002b8c4  mov     rax, rsp
0x18002b8c7  push    rbp
0x18002b8c8  push    rsi
0x18002b8c9  push    rdi
0x18002b8ca  push    r14
0x18002b8cc  push    r15
0x18002b8ce  lea     rbp, [rax-258h]
0x18002b8d5  sub     rsp, 370h
0x18002b8dc  mov     [rbp+250h+var_248], 0FFFFFFFFFFFFFFFEh
0x18002b8e4  mov     [rax+18h], rbx
0x18002b8e8  mov     rax, cs:__security_cookie
0x18002b8ef  xor     rax, rsp
0x18002b8f2  mov     [rbp+250h+var_30], rax
0x18002b8f9  mov     r15d, r9d
0x18002b8fc  mov     rbx, rdx
0x18002b8ff  mov     rdi, rcx
0x18002b902  xor     edx, edx; Val
0x18002b904  mov     r8d, 208h; Size
0x18002b90a  lea     rcx, [rbp+250h+Destination]; void *
0x18002b90e  call    memset_0
0x18002b913  mov     r8, rbx; Source
0x18002b916  mov     edx, 104h; SizeInWords
0x18002b91b  lea     rcx, [rbp+250h+Destination]; Destination
0x18002b91f  call    wcscpy_s
0x18002b924  mov     rbx, [rdi+110h]
0x18002b92b  mov     eax, [rbx+48h]
0x18002b92e  test    eax, eax
0x18002b930  jns     loc_18002BB25
0x18002b936  add     rbx, 50h ; 'P'
0x18002b93a  cmp     eax, [rbx+8]
0x18002b93d  jnz     loc_18002BB25
0x18002b943  test    rbx, rbx
0x18002b946  jz      loc_18002BB25
0x18002b94c  lea     rdx, [rbp+250h+SRWLock]
0x18002b950  mov     rcx, rdi
0x18002b953  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b958  mov     rax, [rdi+110h]
0x18002b95f  mov     esi, 2
0x18002b964  mov     [rax], esi
0x18002b966  mov     rcx, [rbp+250h+SRWLock]; SRWLock
0x18002b96a  test    rcx, rcx
0x18002b96d  jz      short loc_18002B976
0x18002b96f  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b975  nop
0x18002b976  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002b97b  mov     r14, rax
0x18002b97e  mov     ecx, [rax]
0x18002b980  cmp     ecx, 5
0x18002b983  jbe     loc_18002BC2E
0x18002b989  mov     rax, [rax+18h]
0x18002b98d  mov     rcx, [r14+10h]
0x18002b991  mov     rdx, 400000000000h
0x18002b99b  test    rdx, rcx
0x18002b99e  jz      loc_18002BC2E
0x18002b9a4  mov     rcx, rax
0x18002b9a7  and     rcx, rdx
0x18002b9aa  cmp     rcx, rax
0x18002b9ad  jnz     loc_18002BC2E
0x18002b9b3  mov     dword ptr [rbp+250h+var_2B0], r15d
0x18002b9b7  mov     word ptr [rbp+250h+var_2D0], si
0x18002b9bb  lea     rdx, [rbp+250h+Destination]
0x18002b9bf  lea     rcx, [rbp+250h+var_2B8]
0x18002b9c3  call    ?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)
0x18002b9c8  mov     rcx, [rax]
0x18002b9cb  mov     [rbp+250h+var_290], rcx
0x18002b9cf  mov     rax, [rbx+78h]
0x18002b9d3  mov     [rbp+250h+var_288], rax
0x18002b9d7  mov     rax, [rbx+70h]
0x18002b9db  mov     [rbp+250h+var_280], rax
0x18002b9df  mov     eax, [rbx+68h]
0x18002b9e2  mov     dword ptr [rbp+250h+var_2B0+4], eax
0x18002b9e5  mov     rax, [rbx+60h]
0x18002b9e9  mov     [rbp+250h+var_278], rax
0x18002b9ed  mov     rax, [rbx+58h]
0x18002b9f1  mov     [rbp+250h+var_270], rax
0x18002b9f5  mov     eax, [rbx+50h]
0x18002b9f8  mov     dword ptr [rbp+250h+var_2A8], eax
0x18002b9fb  mov     rax, [rbx+48h]
0x18002b9ff  mov     [rbp+250h+var_268], rax
0x18002ba03  mov     eax, [rbx+20h]
0x18002ba06  mov     dword ptr [rbp+250h+var_2A8+4], eax
0x18002ba09  mov     rax, [rbx+18h]
0x18002ba0d  mov     [rbp+250h+var_260], rax
0x18002ba11  mov     eax, [rbx]
0x18002ba13  mov     dword ptr [rbp+250h+var_2D0+4], eax
0x18002ba16  mov     rax, [rbx+80h]
0x18002ba1d  mov     [rbp+250h+var_258], rax
0x18002ba21  mov     eax, [rbx+40h]
0x18002ba24  mov     dword ptr [rbp+250h+var_2C8], eax
0x18002ba27  mov     rax, [rbx+38h]
0x18002ba2b  mov     [rbp+250h+var_250], rax
0x18002ba2f  mov     eax, [rbx+8]
0x18002ba32  mov     dword ptr [rbp+250h+SRWLock], eax
0x18002ba35  mov     eax, 1000000h
0x18002ba3a  mov     [rbp+250h+var_2A0], rax
0x18002ba3e  mov     [rbp+250h+var_298], rax
0x18002ba42  mov     r8, [rdi+110h]
0x18002ba49  add     r8, 8; int
0x18002ba4d  lea     rax, [rbp+250h+var_2B0]
0x18002ba51  mov     [rsp+0B0h], rax; __int64
0x18002ba59  lea     rax, [rbp+250h+var_2D0]
0x18002ba5d  mov     [rsp+390h+var_2E8], rax; __int64
0x18002ba65  lea     rax, [rbp+250h+var_290]
0x18002ba69  mov     [rsp+390h+var_2F0], rax; __int64
0x18002ba71  lea     rax, [rbp+250h+var_288]
0x18002ba75  mov     [rsp+390h+var_2F8], rax; __int64
0x18002ba7d  lea     rax, [rbp+250h+var_280]
0x18002ba81  mov     [rsp+390h+var_300], rax; __int64
0x18002ba89  lea     rax, [rbp+250h+var_2B0+4]
0x18002ba8d  mov     [rsp+390h+var_308], rax; __int64
0x18002ba95  lea     rax, [rbp+250h+var_278]
0x18002ba99  mov     [rsp+390h+var_310], rax; __int64
0x18002baa1  lea     rax, [rbp+250h+var_270]
0x18002baa5  mov     [rsp+390h+var_318], rax; __int64
0x18002baaa  lea     rax, [rbp+250h+var_2A8]
0x18002baae  mov     [rsp+390h+var_320], rax; __int64
0x18002bab3  lea     rax, [rbp+250h+var_268]
0x18002bab7  mov     [rsp+390h+var_328], rax; __int64
0x18002babc  lea     rax, [rbp+250h+var_2A8+4]
0x18002bac0  mov     [rsp+390h+var_330], rax; __int64
0x18002bac5  lea     rax, [rbp+250h+var_260]
0x18002bac9  mov     [rsp+390h+var_338], rax; __int64
0x18002bace  lea     rax, [rbp+250h+var_2D0+4]
0x18002bad2  mov     [rsp+390h+var_340], rax; __int64
0x18002bad7  lea     rax, [rbp+250h+var_258]
0x18002badb  mov     [rsp+390h+var_348], rax; __int64
0x18002bae0  lea     rax, [rbp+250h+var_2C8]
0x18002bae4  mov     [rsp+390h+var_350], rax; __int64
0x18002bae9  lea     rax, [rbp+250h+var_250]
0x18002baed  mov     [rsp+390h+var_358], rax; __int64
0x18002baf2  lea     rax, [rbp+250h+SRWLock]
0x18002baf6  mov     [rsp+390h+var_360], rax; __int64
0x18002bafb  lea     rax, [rbp+250h+var_2A0]
0x18002baff  mov     [rsp+390h+var_368], rax; __int64
0x18002bb04  lea     rax, [rbp+250h+var_298]
0x18002bb08  mov     [rsp+390h+var_370], rax; __int64
0x18002bb0d  lea     rdx, byte_1800444A5; int
0x18002bb14  mov     rcx, r14; int
0x18002bb17  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18002bb1c  mov     rbx, [rbp+250h+var_2B8]
0x18002bb20  jmp     loc_18002BC15
0x18002bb25  lea     rdx, [rbp+250h+var_2B8]
0x18002bb29  mov     rcx, rdi
0x18002bb2c  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002bb31  mov     rax, [rdi+110h]
0x18002bb38  mov     esi, 2
0x18002bb3d  mov     [rax], esi
0x18002bb3f  mov     rcx, [rbp+250h+var_2B8]; SRWLock
0x18002bb43  test    rcx, rcx
0x18002bb46  jz      short loc_18002BB4F
0x18002bb48  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bb4e  nop
0x18002bb4f  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002bb54  mov     rbx, rax
0x18002bb57  mov     ecx, [rax]
0x18002bb59  cmp     ecx, 5
0x18002bb5c  jbe     loc_18002BC2E
0x18002bb62  mov     rax, [rax+18h]
0x18002bb66  mov     rcx, [rbx+10h]
0x18002bb6a  mov     rdx, 400000000000h
0x18002bb74  test    rdx, rcx
0x18002bb77  jz      loc_18002BC2E
0x18002bb7d  mov     rcx, rax
0x18002bb80  and     rcx, rdx
0x18002bb83  cmp     rcx, rax
0x18002bb86  jnz     loc_18002BC2E
0x18002bb8c  mov     dword ptr [rbp+250h+SRWLock], r15d
0x18002bb90  mov     word ptr [rbp+250h+var_2D0], si
0x18002bb94  lea     rdx, [rbp+250h+Destination]
0x18002bb98  lea     rcx, [rbp+250h+var_2A0]
0x18002bb9c  call    ?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)
0x18002bba1  mov     rcx, [rax]
0x18002bba4  mov     [rbp+250h+var_2B8], rcx
0x18002bba8  call    cs:__imp_GetCurrentThreadId
0x18002bbae  mov     dword ptr [rbp+250h+var_2C8], eax
0x18002bbb1  mov     r8, [rdi+110h]
0x18002bbb8  mov     eax, [r8+48h]
0x18002bbbc  mov     dword ptr [rbp+250h+var_2D0+4], eax
0x18002bbbf  mov     eax, 1000000h
0x18002bbc4  mov     [rbp+250h+var_298], rax
0x18002bbc8  add     r8, 8
0x18002bbcc  lea     rax, [rbp+250h+SRWLock]
0x18002bbd0  mov     [rsp+390h+var_348], rax; __int64
0x18002bbd5  lea     rax, [rbp+250h+var_2D0]
0x18002bbd9  mov     [rsp+390h+var_350], rax; __int64
0x18002bbde  lea     rax, [rbp+250h+var_2B8]
0x18002bbe2  mov     [rsp+390h+var_358], rax; __int64
0x18002bbe7  lea     rax, [rbp+250h+var_2C8]
0x18002bbeb  mov     [rsp+390h+var_360], rax; __int64
0x18002bbf0  lea     rax, [rbp+250h+var_2D0+4]
0x18002bbf4  mov     [rsp+390h+var_368], rax; __int64
0x18002bbf9  lea     rax, [rbp+250h+var_298]
0x18002bbfd  mov     [rsp+390h+var_370], rax; __int64
0x18002bc02  lea     rdx, dword_180044434; int
0x18002bc09  mov     rcx, rbx; int
0x18002bc0c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18002bc11  mov     rbx, [rbp+250h+var_2A0]
0x18002bc15  test    rbx, rbx
0x18002bc18  jz      short loc_18002BC2E
0x18002bc1a  call    cs:__imp_GetProcessHeap
0x18002bc20  mov     r8, rbx; lpMem
0x18002bc23  xor     edx, edx; dwFlags
0x18002bc25  mov     rcx, rax; hHeap
0x18002bc28  call    cs:__imp_HeapFree
0x18002bc2e  mov     rcx, rdi
0x18002bc31  call    ?IgnoreCurrentThread@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18002bc36  mov     rcx, [rbp+250h+var_30]
0x18002bc3d  xor     rcx, rsp; StackCookie
0x18002bc40  call    __security_check_cookie
0x18002bc45  mov     rbx, [rsp+390h+arg_10]
0x18002bc4d  add     rsp, 370h
0x18002bc54  pop     r15
0x18002bc56  pop     r14
0x18002bc58  pop     rdi
0x18002bc59  pop     rsi
0x18002bc5a  pop     rbp
0x18002bc5b  retn
```
