# StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::Stop(ushort const *,ushort,long)

- ea: `0x18002ac04`
- end: `0x18002afa0`
- name: `?Stop@DeleteReserveAreaContent@SRProvider@Internal@StorageReserveTelemetry@@QEAAXPEBGGJ@Z`
- size: `924`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent *this, const unsigned __int16 *, __int16, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800262e0`

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
- `0x18002ac04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002acb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ae8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002acb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ae8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002af5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002af5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002af6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002af6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aeec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aeec`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::Stop(
        StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent *this,
        const unsigned __int16 *a2,
        __int16 a3,
        int a4)
{
  __int64 v8; // rbx
  int v9; // eax
  int *v10; // rbx
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rsi
  __int64 v13; // rax
  __int64 v14; // r9
  PSRWLOCK v15; // rbx
  const struct _tlgProvider_t *v16; // rax
  const struct _tlgProvider_t *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  HANDLE ProcessHeap; // rax
  _WORD v22[2]; // [rsp+C8h] [rbp-80h] BYREF
  int v23; // [rsp+CCh] [rbp-7Ch] BYREF
  __int64 v24; // [rsp+D0h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+D8h] [rbp-70h] BYREF
  PSRWLOCK v26; // [rsp+E0h] [rbp-68h] BYREF
  int v27; // [rsp+E8h] [rbp-60h] BYREF
  int v28; // [rsp+ECh] [rbp-5Ch] BYREF
  int v29; // [rsp+F0h] [rbp-58h] BYREF
  int v30; // [rsp+F4h] [rbp-54h] BYREF
  __int64 v31; // [rsp+F8h] [rbp-50h] BYREF
  __int64 v32; // [rsp+100h] [rbp-48h] BYREF
  __int64 v33; // [rsp+108h] [rbp-40h] BYREF
  __int64 v34; // [rsp+110h] [rbp-38h] BYREF
  __int64 v35; // [rsp+118h] [rbp-30h] BYREF
  __int64 v36; // [rsp+120h] [rbp-28h] BYREF
  __int64 v37; // [rsp+128h] [rbp-20h] BYREF
  __int64 v38; // [rsp+130h] [rbp-18h] BYREF
  __int64 v39; // [rsp+138h] [rbp-10h] BYREF
  __int64 v40; // [rsp+140h] [rbp-8h] BYREF
  __int64 v41[2]; // [rsp+148h] [rbp+0h] BYREF
  wchar_t Destination[264]; // [rsp+158h] [rbp+10h] BYREF

  v41[1] = -2;
  memset_0(Destination, 0, 0x208u);
  wcscpy_s(Destination, 0x104u, a2);
  v8 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v8 + 72);
  if ( v9 < 0 && (v10 = (int *)(v8 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v11 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        v27 = a4;
        v22[0] = a3;
        v33 = (__int64)*StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
                          (unsigned __int16 **)&v26,
                          Destination);
        v34 = *((_QWORD *)v10 + 15);
        v35 = *((_QWORD *)v10 + 14);
        v28 = v10[26];
        v36 = *((_QWORD *)v10 + 12);
        v37 = *((_QWORD *)v10 + 11);
        v29 = v10[20];
        v38 = *((_QWORD *)v10 + 9);
        v30 = v10[8];
        v39 = *((_QWORD *)v10 + 3);
        v23 = *v10;
        v40 = *((_QWORD *)v10 + 16);
        LODWORD(v24) = v10[16];
        v41[0] = *((_QWORD *)v10 + 7);
        LODWORD(SRWLock) = v10[2];
        v31 = 0x1000000;
        v32 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
          (int)v12,
          (int)&byte_180044113,
          *((_QWORD *)this + 34) + 8,
          v14,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&SRWLock,
          (const wchar_t **)v41,
          (__int64)&v24,
          (const wchar_t **)&v40,
          (__int64)&v23,
          (const unsigned __int16 **)&v39,
          (__int64)&v30,
          (const wchar_t **)&v38,
          (__int64)&v29,
          (const wchar_t **)&v37,
          (const unsigned __int16 **)&v36,
          (__int64)&v28,
          (const wchar_t **)&v35,
          (const unsigned __int16 **)&v34,
          (const unsigned __int16 **)&v33,
          (__int64)v22,
          (__int64)&v27);
        v15 = v26;
        goto LABEL_16;
      }
    }
  }
  else
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v26);
    **((_DWORD **)this + 34) = 2;
    if ( v26 )
      ReleaseSRWLockExclusive(v26);
    v16 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v17 = v16;
    if ( *(_DWORD *)v16 > 5u )
    {
      v18 = *((_QWORD *)v16 + 3);
      if ( (*((_QWORD *)v17 + 2) & 0x400000000000LL) != 0 && (v18 & 0x400000000000LL) == v18 )
      {
        LODWORD(SRWLock) = a4;
        v22[0] = a3;
        v26 = (PSRWLOCK)*StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
                           (unsigned __int16 **)&v31,
                           Destination);
        LODWORD(v24) = GetCurrentThreadId();
        v19 = *((_QWORD *)this + 34);
        v23 = *(_DWORD *)(v19 + 72);
        v32 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
          (int)v17,
          (int)&word_1800440A2,
          v19 + 8,
          v20,
          (__int64)&v32,
          (__int64)&v23,
          (__int64)&v24,
          (const unsigned __int16 **)&v26,
          (__int64)v22,
          (__int64)&SRWLock);
        v15 = (PSRWLOCK)v31;
LABEL_16:
        if ( v15 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v15);
        }
      }
    }
  }
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002ac04  mov     rax, rsp
0x18002ac07  push    rbp
0x18002ac08  push    rsi
0x18002ac09  push    rdi
0x18002ac0a  push    r14
0x18002ac0c  push    r15
0x18002ac0e  lea     rbp, [rax-258h]
0x18002ac15  sub     rsp, 370h
0x18002ac1c  mov     [rbp+250h+var_248], 0FFFFFFFFFFFFFFFEh
0x18002ac24  mov     [rax+18h], rbx
0x18002ac28  mov     rax, cs:__security_cookie
0x18002ac2f  xor     rax, rsp
0x18002ac32  mov     [rbp+250h+var_30], rax
0x18002ac39  mov     r14d, r9d
0x18002ac3c  movzx   r15d, r8w
0x18002ac40  mov     rbx, rdx
0x18002ac43  mov     rdi, rcx
0x18002ac46  xor     edx, edx; Val
0x18002ac48  mov     r8d, 208h; Size
0x18002ac4e  lea     rcx, [rbp+250h+Destination]; void *
0x18002ac52  call    memset_0
0x18002ac57  mov     r8, rbx; Source
0x18002ac5a  mov     edx, 104h; SizeInWords
0x18002ac5f  lea     rcx, [rbp+250h+Destination]; Destination
0x18002ac63  call    wcscpy_s
0x18002ac68  mov     rbx, [rdi+110h]
0x18002ac6f  mov     eax, [rbx+48h]
0x18002ac72  test    eax, eax
0x18002ac74  jns     loc_18002AE69
0x18002ac7a  add     rbx, 50h ; 'P'
0x18002ac7e  cmp     eax, [rbx+8]
0x18002ac81  jnz     loc_18002AE69
0x18002ac87  test    rbx, rbx
0x18002ac8a  jz      loc_18002AE69
0x18002ac90  lea     rdx, [rbp+250h+SRWLock]
0x18002ac94  mov     rcx, rdi
0x18002ac97  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002ac9c  mov     rax, [rdi+110h]
0x18002aca3  mov     dword ptr [rax], 2
0x18002aca9  mov     rcx, [rbp+250h+SRWLock]; SRWLock
0x18002acad  test    rcx, rcx
0x18002acb0  jz      short loc_18002ACB9
0x18002acb2  call    cs:__imp_ReleaseSRWLockExclusive
0x18002acb8  nop
0x18002acb9  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002acbe  mov     rsi, rax
0x18002acc1  mov     ecx, [rax]
0x18002acc3  cmp     ecx, 5
0x18002acc6  jbe     loc_18002AF72
0x18002accc  mov     rax, [rax+18h]
0x18002acd0  mov     rcx, [rsi+10h]
0x18002acd4  mov     rdx, 400000000000h
0x18002acde  test    rdx, rcx
0x18002ace1  jz      loc_18002AF72
0x18002ace7  mov     rcx, rax
0x18002acea  and     rcx, rdx
0x18002aced  cmp     rcx, rax
0x18002acf0  jnz     loc_18002AF72
0x18002acf6  mov     dword ptr [rbp+250h+var_2B0], r14d
0x18002acfa  mov     word ptr [rbp+250h+var_2D0], r15w
0x18002acff  lea     rdx, [rbp+250h+Destination]
0x18002ad03  lea     rcx, [rbp+250h+var_2B8]
0x18002ad07  call    ?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)
0x18002ad0c  mov     rcx, [rax]
0x18002ad0f  mov     [rbp+250h+var_290], rcx
0x18002ad13  mov     rax, [rbx+78h]
0x18002ad17  mov     [rbp+250h+var_288], rax
0x18002ad1b  mov     rax, [rbx+70h]
0x18002ad1f  mov     [rbp+250h+var_280], rax
0x18002ad23  mov     eax, [rbx+68h]
0x18002ad26  mov     dword ptr [rbp+250h+var_2B0+4], eax
0x18002ad29  mov     rax, [rbx+60h]
0x18002ad2d  mov     [rbp+250h+var_278], rax
0x18002ad31  mov     rax, [rbx+58h]
0x18002ad35  mov     [rbp+250h+var_270], rax
0x18002ad39  mov     eax, [rbx+50h]
0x18002ad3c  mov     dword ptr [rbp+250h+var_2A8], eax
0x18002ad3f  mov     rax, [rbx+48h]
0x18002ad43  mov     [rbp+250h+var_268], rax
0x18002ad47  mov     eax, [rbx+20h]
0x18002ad4a  mov     dword ptr [rbp+250h+var_2A8+4], eax
0x18002ad4d  mov     rax, [rbx+18h]
0x18002ad51  mov     [rbp+250h+var_260], rax
0x18002ad55  mov     eax, [rbx]
0x18002ad57  mov     dword ptr [rbp+250h+var_2D0+4], eax
0x18002ad5a  mov     rax, [rbx+80h]
0x18002ad61  mov     [rbp+250h+var_258], rax
0x18002ad65  mov     eax, [rbx+40h]
0x18002ad68  mov     dword ptr [rbp+250h+var_2C8], eax
0x18002ad6b  mov     rax, [rbx+38h]
0x18002ad6f  mov     [rbp+250h+var_250], rax
0x18002ad73  mov     eax, [rbx+8]
0x18002ad76  mov     dword ptr [rbp+250h+SRWLock], eax
0x18002ad79  mov     eax, 1000000h
0x18002ad7e  mov     [rbp+250h+var_2A0], rax
0x18002ad82  mov     [rbp+250h+var_298], rax
0x18002ad86  mov     r8, [rdi+110h]
0x18002ad8d  add     r8, 8; int
0x18002ad91  lea     rax, [rbp+250h+var_2B0]
0x18002ad95  mov     [rsp+0B0h], rax; __int64
0x18002ad9d  lea     rax, [rbp+250h+var_2D0]
0x18002ada1  mov     [rsp+390h+var_2E8], rax; __int64
0x18002ada9  lea     rax, [rbp+250h+var_290]
0x18002adad  mov     [rsp+390h+var_2F0], rax; __int64
0x18002adb5  lea     rax, [rbp+250h+var_288]
0x18002adb9  mov     [rsp+390h+var_2F8], rax; __int64
0x18002adc1  lea     rax, [rbp+250h+var_280]
0x18002adc5  mov     [rsp+390h+var_300], rax; __int64
0x18002adcd  lea     rax, [rbp+250h+var_2B0+4]
0x18002add1  mov     [rsp+390h+var_308], rax; __int64
0x18002add9  lea     rax, [rbp+250h+var_278]
0x18002addd  mov     [rsp+390h+var_310], rax; __int64
0x18002ade5  lea     rax, [rbp+250h+var_270]
0x18002ade9  mov     [rsp+390h+var_318], rax; __int64
0x18002adee  lea     rax, [rbp+250h+var_2A8]
0x18002adf2  mov     [rsp+390h+var_320], rax; __int64
0x18002adf7  lea     rax, [rbp+250h+var_268]
0x18002adfb  mov     [rsp+390h+var_328], rax; __int64
0x18002ae00  lea     rax, [rbp+250h+var_2A8+4]
0x18002ae04  mov     [rsp+390h+var_330], rax; __int64
0x18002ae09  lea     rax, [rbp+250h+var_260]
0x18002ae0d  mov     [rsp+390h+var_338], rax; __int64
0x18002ae12  lea     rax, [rbp+250h+var_2D0+4]
0x18002ae16  mov     [rsp+390h+var_340], rax; __int64
0x18002ae1b  lea     rax, [rbp+250h+var_258]
0x18002ae1f  mov     [rsp+390h+var_348], rax; __int64
0x18002ae24  lea     rax, [rbp+250h+var_2C8]
0x18002ae28  mov     [rsp+390h+var_350], rax; __int64
0x18002ae2d  lea     rax, [rbp+250h+var_250]
0x18002ae31  mov     [rsp+390h+var_358], rax; __int64
0x18002ae36  lea     rax, [rbp+250h+SRWLock]
0x18002ae3a  mov     [rsp+390h+var_360], rax; __int64
0x18002ae3f  lea     rax, [rbp+250h+var_2A0]
0x18002ae43  mov     [rsp+390h+var_368], rax; __int64
0x18002ae48  lea     rax, [rbp+250h+var_298]
0x18002ae4c  mov     [rsp+390h+var_370], rax; __int64
0x18002ae51  lea     rdx, byte_180044113; int
0x18002ae58  mov     rcx, rsi; int
0x18002ae5b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18002ae60  mov     rbx, [rbp+250h+var_2B8]
0x18002ae64  jmp     loc_18002AF59
0x18002ae69  lea     rdx, [rbp+250h+var_2B8]
0x18002ae6d  mov     rcx, rdi
0x18002ae70  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002ae75  mov     rax, [rdi+110h]
0x18002ae7c  mov     dword ptr [rax], 2
0x18002ae82  mov     rcx, [rbp+250h+var_2B8]; SRWLock
0x18002ae86  test    rcx, rcx
0x18002ae89  jz      short loc_18002AE92
0x18002ae8b  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ae91  nop
0x18002ae92  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002ae97  mov     rbx, rax
0x18002ae9a  mov     ecx, [rax]
0x18002ae9c  cmp     ecx, 5
0x18002ae9f  jbe     loc_18002AF72
0x18002aea5  mov     rax, [rax+18h]
0x18002aea9  mov     rcx, [rbx+10h]
0x18002aead  mov     rdx, 400000000000h
0x18002aeb7  test    rdx, rcx
0x18002aeba  jz      loc_18002AF72
0x18002aec0  mov     rcx, rax
0x18002aec3  and     rcx, rdx
0x18002aec6  cmp     rcx, rax
0x18002aec9  jnz     loc_18002AF72
0x18002aecf  mov     dword ptr [rbp+250h+SRWLock], r14d
0x18002aed3  mov     word ptr [rbp+250h+var_2D0], r15w
0x18002aed8  lea     rdx, [rbp+250h+Destination]
0x18002aedc  lea     rcx, [rbp+250h+var_2A0]
0x18002aee0  call    ?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)
0x18002aee5  mov     rcx, [rax]
0x18002aee8  mov     [rbp+250h+var_2B8], rcx
0x18002aeec  call    cs:__imp_GetCurrentThreadId
0x18002aef2  mov     dword ptr [rbp+250h+var_2C8], eax
0x18002aef5  mov     r8, [rdi+110h]
0x18002aefc  mov     eax, [r8+48h]
0x18002af00  mov     dword ptr [rbp+250h+var_2D0+4], eax
0x18002af03  mov     eax, 1000000h
0x18002af08  mov     [rbp+250h+var_298], rax
0x18002af0c  add     r8, 8
0x18002af10  lea     rax, [rbp+250h+SRWLock]
0x18002af14  mov     [rsp+390h+var_348], rax; __int64
0x18002af19  lea     rax, [rbp+250h+var_2D0]
0x18002af1d  mov     [rsp+390h+var_350], rax; __int64
0x18002af22  lea     rax, [rbp+250h+var_2B8]
0x18002af26  mov     [rsp+390h+var_358], rax; __int64
0x18002af2b  lea     rax, [rbp+250h+var_2C8]
0x18002af2f  mov     [rsp+390h+var_360], rax; __int64
0x18002af34  lea     rax, [rbp+250h+var_2D0+4]
0x18002af38  mov     [rsp+390h+var_368], rax; __int64
0x18002af3d  lea     rax, [rbp+250h+var_298]
0x18002af41  mov     [rsp+390h+var_370], rax; __int64
0x18002af46  lea     rdx, word_1800440A2; int
0x18002af4d  mov     rcx, rbx; int
0x18002af50  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18002af55  mov     rbx, [rbp+250h+var_2A0]
0x18002af59  test    rbx, rbx
0x18002af5c  jz      short loc_18002AF72
0x18002af5e  call    cs:__imp_GetProcessHeap
0x18002af64  mov     r8, rbx; lpMem
0x18002af67  xor     edx, edx; dwFlags
0x18002af69  mov     rcx, rax; hHeap
0x18002af6c  call    cs:__imp_HeapFree
0x18002af72  mov     rcx, rdi
0x18002af75  call    ?IgnoreCurrentThread@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18002af7a  mov     rcx, [rbp+250h+var_30]
0x18002af81  xor     rcx, rsp; StackCookie
0x18002af84  call    __security_check_cookie
0x18002af89  mov     rbx, [rsp+390h+arg_10]
0x18002af91  add     rsp, 370h
0x18002af98  pop     r15
0x18002af9a  pop     r14
0x18002af9c  pop     rdi
0x18002af9d  pop     rsi
0x18002af9e  pop     rbp
0x18002af9f  retn
```
