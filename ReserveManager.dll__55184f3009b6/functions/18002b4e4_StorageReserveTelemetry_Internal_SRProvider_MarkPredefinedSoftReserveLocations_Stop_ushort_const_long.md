# StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::Stop(ushort const *,long)

- ea: `0x18002b4e4`
- end: `0x18002b8be`
- name: `?Stop@MarkPredefinedSoftReserveLocations@SRProvider@Internal@StorageReserveTelemetry@@QEAAXPEBGJ@Z`
- size: `986`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800287e4`

## callees

- `0x1800013b4`
- `0x180001eb4`
- `0x180003870`
- `0x1800042dc`
- `0x1800042f4`
- `0x180028494`
- `0x180028738`
- `0x180028ac8`
- `0x18002939c`
- `0x18002b4e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b597`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b763`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b597`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b763`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b87c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b87c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b88a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b88a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b7be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b7be`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::Stop(
        StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v6; // rsi
  int v7; // eax
  int *v8; // rsi
  const struct _tlgProvider_t *v9; // rax
  const struct _tlgProvider_t *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r9
  PSRWLOCK v13; // rbx
  int v14; // ebx
  const struct _tlgProvider_t *v15; // rax
  const struct _tlgProvider_t *v16; // rsi
  __int64 v17; // rax
  unsigned __int16 *v18; // r14
  __int64 v19; // r8
  __int64 v20; // rbx
  HANDLE ProcessHeap; // rax
  int v22; // [rsp+B8h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+BCh] [rbp-7Ch] BYREF
  __int64 v24; // [rsp+C0h] [rbp-78h] BYREF
  PSRWLOCK v25; // [rsp+C8h] [rbp-70h] BYREF
  int v26; // [rsp+D0h] [rbp-68h] BYREF
  int v27; // [rsp+D4h] [rbp-64h] BYREF
  int v28; // [rsp+D8h] [rbp-60h] BYREF
  int v29; // [rsp+DCh] [rbp-5Ch] BYREF
  __int64 v30; // [rsp+E0h] [rbp-58h] BYREF
  __int64 v31; // [rsp+E8h] [rbp-50h] BYREF
  __int64 v32; // [rsp+F0h] [rbp-48h] BYREF
  __int64 v33; // [rsp+F8h] [rbp-40h] BYREF
  __int64 v34; // [rsp+100h] [rbp-38h] BYREF
  __int64 v35; // [rsp+108h] [rbp-30h] BYREF
  __int64 v36; // [rsp+110h] [rbp-28h] BYREF
  __int64 v37; // [rsp+118h] [rbp-20h] BYREF
  __int64 v38; // [rsp+120h] [rbp-18h] BYREF
  __int64 v39; // [rsp+128h] [rbp-10h] BYREF
  __int64 v40[3]; // [rsp+130h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+148h] [rbp+10h] BYREF
  PSRWLOCK *v42; // [rsp+168h] [rbp+30h]
  __int64 v43; // [rsp+170h] [rbp+38h]
  int *v44; // [rsp+178h] [rbp+40h]
  __int64 v45; // [rsp+180h] [rbp+48h]
  DWORD *p_CurrentThreadId; // [rsp+188h] [rbp+50h]
  __int64 v47; // [rsp+190h] [rbp+58h]
  unsigned __int16 *v48; // [rsp+198h] [rbp+60h]
  int v49; // [rsp+1A0h] [rbp+68h]
  int v50; // [rsp+1A4h] [rbp+6Ch]
  __int64 *v51; // [rsp+1A8h] [rbp+70h]
  __int64 v52; // [rsp+1B0h] [rbp+78h]
  wchar_t Destination[264]; // [rsp+1B8h] [rbp+80h] BYREF

  v40[1] = -2;
  memset_0(Destination, 0, 0x208u);
  wcscpy_s(Destination, 0x104u, a2);
  v6 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v6 + 72);
  if ( v7 < 0 && (v8 = (int *)(v6 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      (RTL_SRWLOCK **)&v24);
    **((_DWORD **)this + 34) = 2;
    if ( v24 )
      ReleaseSRWLockExclusive((PSRWLOCK)v24);
    v9 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v10 = v9;
    if ( *(_DWORD *)v9 > 5u )
    {
      v11 = *((_QWORD *)v9 + 3);
      if ( (*((_QWORD *)v10 + 2) & 0x400000000000LL) != 0 && (v11 & 0x400000000000LL) == v11 )
      {
        v26 = a3;
        v31 = (__int64)*StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
                          (unsigned __int16 **)&v25,
                          Destination);
        v32 = *((_QWORD *)v8 + 15);
        v33 = *((_QWORD *)v8 + 14);
        v27 = v8[26];
        v34 = *((_QWORD *)v8 + 12);
        v35 = *((_QWORD *)v8 + 11);
        v28 = v8[20];
        v36 = *((_QWORD *)v8 + 9);
        v29 = v8[8];
        v37 = *((_QWORD *)v8 + 3);
        v22 = *v8;
        v38 = *((_QWORD *)v8 + 16);
        CurrentThreadId = v8[16];
        v39 = *((_QWORD *)v8 + 7);
        LODWORD(v24) = v8[2];
        v40[0] = 0x1000000;
        v30 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (int)v10,
          (int)&dword_180043984,
          *((_QWORD *)this + 34) + 8,
          v12,
          (__int64)&v30,
          (__int64)v40,
          (__int64)&v24,
          (const wchar_t **)&v39,
          (__int64)&CurrentThreadId,
          (const wchar_t **)&v38,
          (__int64)&v22,
          (const unsigned __int16 **)&v37,
          (__int64)&v29,
          (const wchar_t **)&v36,
          (__int64)&v28,
          (const wchar_t **)&v35,
          (const unsigned __int16 **)&v34,
          (__int64)&v27,
          (const wchar_t **)&v33,
          (const unsigned __int16 **)&v32,
          (const unsigned __int16 **)&v31,
          (__int64)&v26);
        v13 = v25;
LABEL_21:
        if ( v13 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v13);
        }
      }
    }
  }
  else
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v25);
    v14 = 2;
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
        LODWORD(v24) = a3;
        v18 = *StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
                 (unsigned __int16 **)&v30,
                 Destination);
        CurrentThreadId = GetCurrentThreadId();
        v19 = *((_QWORD *)this + 34);
        v22 = *(_DWORD *)(v19 + 72);
        v25 = (PSRWLOCK)0x1000000;
        v51 = &v24;
        v52 = 4;
        if ( v18 )
        {
          v20 = -1;
          do
            ++v20;
          while ( v18[v20] );
          v14 = 2 * v20 + 2;
        }
        else
        {
          v18 = (unsigned __int16 *)&qword_18003A1F8;
        }
        v48 = v18;
        v49 = v14;
        v50 = 0;
        p_CurrentThreadId = &CurrentThreadId;
        v47 = 4;
        v44 = &v22;
        v45 = 4;
        v42 = &v25;
        v43 = 8;
        tlgWriteTransfer_EventWriteTransfer((int)v16, (int)&byte_180043911, v19 + 8, 0, 7u, &v41);
        v13 = (PSRWLOCK)v30;
        goto LABEL_21;
      }
    }
  }
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002b4e4  mov     rax, rsp
0x18002b4e7  push    rbp
0x18002b4e8  push    rsi
0x18002b4e9  push    rdi
0x18002b4ea  push    r14
0x18002b4ec  push    r15
0x18002b4ee  lea     rbp, [rax-2C8h]
0x18002b4f5  sub     rsp, 3D0h
0x18002b4fc  mov     [rbp+2C0h+var_2C0], 0FFFFFFFFFFFFFFFEh
0x18002b504  mov     [rax+18h], rbx
0x18002b508  mov     rax, cs:__security_cookie
0x18002b50f  xor     rax, rsp
0x18002b512  mov     [rbp+2C0h+var_30], rax
0x18002b519  mov     r14d, r8d
0x18002b51c  mov     rbx, rdx
0x18002b51f  mov     rdi, rcx
0x18002b522  xor     edx, edx; Val
0x18002b524  mov     r8d, 208h; Size
0x18002b52a  lea     rcx, [rbp+2C0h+Destination]; void *
0x18002b531  call    memset_0
0x18002b536  mov     r8, rbx; Source
0x18002b539  mov     edx, 104h; SizeInWords
0x18002b53e  lea     rcx, [rbp+2C0h+Destination]; Destination
0x18002b545  call    wcscpy_s
0x18002b54a  mov     rsi, [rdi+110h]
0x18002b551  mov     eax, [rsi+48h]
0x18002b554  xor     r15d, r15d
0x18002b557  test    eax, eax
0x18002b559  jns     loc_18002B740
0x18002b55f  add     rsi, 50h ; 'P'
0x18002b563  cmp     eax, [rsi+8]
0x18002b566  jnz     loc_18002B740
0x18002b56c  test    rsi, rsi
0x18002b56f  jz      loc_18002B740
0x18002b575  lea     rdx, [rbp+2C0h+var_338]
0x18002b579  mov     rcx, rdi
0x18002b57c  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b581  mov     rax, [rdi+110h]
0x18002b588  mov     dword ptr [rax], 2
0x18002b58e  mov     rcx, [rbp+2C0h+var_338]; SRWLock
0x18002b592  test    rcx, rcx
0x18002b595  jz      short loc_18002B59E
0x18002b597  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b59d  nop
0x18002b59e  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002b5a3  mov     rbx, rax
0x18002b5a6  mov     ecx, [rax]
0x18002b5a8  cmp     ecx, 5
0x18002b5ab  jbe     loc_18002B890
0x18002b5b1  mov     rax, [rax+18h]
0x18002b5b5  mov     rcx, [rbx+10h]
0x18002b5b9  mov     rdx, 400000000000h
0x18002b5c3  test    rdx, rcx
0x18002b5c6  jz      loc_18002B890
0x18002b5cc  mov     rcx, rax
0x18002b5cf  and     rcx, rdx
0x18002b5d2  cmp     rcx, rax
0x18002b5d5  jnz     loc_18002B890
0x18002b5db  mov     dword ptr [rbp+2C0h+var_328], r14d
0x18002b5df  lea     rdx, [rbp+2C0h+Destination]
0x18002b5e6  lea     rcx, [rbp+2C0h+var_330]
0x18002b5ea  call    ?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)
0x18002b5ef  mov     rcx, [rax]
0x18002b5f2  mov     [rbp+2C0h+var_310], rcx
0x18002b5f6  mov     rax, [rsi+78h]
0x18002b5fa  mov     [rbp+2C0h+var_308], rax
0x18002b5fe  mov     rax, [rsi+70h]
0x18002b602  mov     [rbp+2C0h+var_300], rax
0x18002b606  mov     eax, [rsi+68h]
0x18002b609  mov     dword ptr [rbp+2C0h+var_328+4], eax
0x18002b60c  mov     rax, [rsi+60h]
0x18002b610  mov     [rbp+2C0h+var_2F8], rax
0x18002b614  mov     rax, [rsi+58h]
0x18002b618  mov     [rbp+2C0h+var_2F0], rax
0x18002b61c  mov     eax, [rsi+50h]
0x18002b61f  mov     dword ptr [rbp+2C0h+var_320], eax
0x18002b622  mov     rax, [rsi+48h]
0x18002b626  mov     [rbp+2C0h+var_2E8], rax
0x18002b62a  mov     eax, [rsi+20h]
0x18002b62d  mov     dword ptr [rbp+2C0h+var_320+4], eax
0x18002b630  mov     rax, [rsi+18h]
0x18002b634  mov     [rbp+2C0h+var_2E0], rax
0x18002b638  mov     eax, [rsi]
0x18002b63a  mov     dword ptr [rbp+2C0h+var_340], eax
0x18002b63d  mov     rax, [rsi+80h]
0x18002b644  mov     [rbp+2C0h+var_2D8], rax
0x18002b648  mov     eax, [rsi+40h]
0x18002b64b  mov     dword ptr [rbp+2C0h+var_340+4], eax
0x18002b64e  mov     rax, [rsi+38h]
0x18002b652  mov     [rbp+2C0h+var_2D0], rax
0x18002b656  mov     eax, [rsi+8]
0x18002b659  mov     dword ptr [rbp+2C0h+var_338], eax
0x18002b65c  mov     eax, 1000000h
0x18002b661  mov     [rbp+2C0h+var_2C8], rax
0x18002b665  mov     [rbp+2C0h+var_318], rax
0x18002b669  mov     r8, [rdi+110h]
0x18002b670  add     r8, 8; int
0x18002b674  lea     rax, [rbp+2C0h+var_328]
0x18002b678  mov     [rsp+0A8h], rax; __int64
0x18002b680  lea     rax, [rbp+2C0h+var_310]
0x18002b684  mov     [rsp+3F0h+var_350], rax; __int64
0x18002b68c  lea     rax, [rbp+2C0h+var_308]
0x18002b690  mov     [rsp+3F0h+var_358], rax; __int64
0x18002b698  lea     rax, [rbp+2C0h+var_300]
0x18002b69c  mov     [rsp+3F0h+var_360], rax; __int64
0x18002b6a4  lea     rax, [rbp+2C0h+var_328+4]
0x18002b6a8  mov     [rsp+3F0h+var_368], rax; __int64
0x18002b6b0  lea     rax, [rbp+2C0h+var_2F8]
0x18002b6b4  mov     [rsp+3F0h+var_370], rax; __int64
0x18002b6bc  lea     rax, [rbp+2C0h+var_2F0]
0x18002b6c0  mov     [rsp+3F0h+var_378], rax; __int64
0x18002b6c5  lea     rax, [rbp+2C0h+var_320]
0x18002b6c9  mov     [rsp+3F0h+var_380], rax; __int64
0x18002b6ce  lea     rax, [rbp+2C0h+var_2E8]
0x18002b6d2  mov     [rsp+3F0h+var_388], rax; __int64
0x18002b6d7  lea     rax, [rbp+2C0h+var_320+4]
0x18002b6db  mov     [rsp+3F0h+var_390], rax; __int64
0x18002b6e0  lea     rax, [rbp+2C0h+var_2E0]
0x18002b6e4  mov     [rsp+3F0h+var_398], rax; __int64
0x18002b6e9  lea     rax, [rbp+2C0h+var_340]
0x18002b6ed  mov     [rsp+3F0h+var_3A0], rax; __int64
0x18002b6f2  lea     rax, [rbp+2C0h+var_2D8]
0x18002b6f6  mov     [rsp+3F0h+var_3A8], rax; __int64
0x18002b6fb  lea     rax, [rbp+2C0h+var_340+4]
0x18002b6ff  mov     [rsp+3F0h+var_3B0], rax; __int64
0x18002b704  lea     rax, [rbp+2C0h+var_2D0]
0x18002b708  mov     [rsp+3F0h+var_3B8], rax; __int64
0x18002b70d  lea     rax, [rbp+2C0h+var_338]
0x18002b711  mov     [rsp+3F0h+var_3C0], rax; __int64
0x18002b716  lea     rax, [rbp+2C0h+var_2C8]
0x18002b71a  mov     [rsp+3F0h+var_3C8], rax; __int64
0x18002b71f  lea     rax, [rbp+2C0h+var_318]
0x18002b723  mov     qword ptr [rsp+3F0h+var_3D0], rax; __int64
0x18002b728  lea     rdx, dword_180043984; int
0x18002b72f  mov     rcx, rbx; int
0x18002b732  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002b737  mov     rbx, [rbp+2C0h+var_330]
0x18002b73b  jmp     loc_18002B877
0x18002b740  lea     rdx, [rbp+2C0h+var_330]
0x18002b744  mov     rcx, rdi
0x18002b747  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b74c  mov     rax, [rdi+110h]
0x18002b753  mov     ebx, 2
0x18002b758  mov     [rax], ebx
0x18002b75a  mov     rcx, [rbp+2C0h+var_330]; SRWLock
0x18002b75e  test    rcx, rcx
0x18002b761  jz      short loc_18002B76A
0x18002b763  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b769  nop
0x18002b76a  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002b76f  mov     rsi, rax
0x18002b772  mov     ecx, [rax]
0x18002b774  cmp     ecx, 5
0x18002b777  jbe     loc_18002B890
0x18002b77d  mov     rax, [rax+18h]
0x18002b781  mov     rcx, [rsi+10h]
0x18002b785  mov     rdx, 400000000000h
0x18002b78f  test    rdx, rcx
0x18002b792  jz      loc_18002B890
0x18002b798  mov     rcx, rax
0x18002b79b  and     rcx, rdx
0x18002b79e  cmp     rcx, rax
0x18002b7a1  jnz     loc_18002B890
0x18002b7a7  mov     dword ptr [rbp+2C0h+var_338], r14d
0x18002b7ab  lea     rdx, [rbp+2C0h+Destination]
0x18002b7b2  lea     rcx, [rbp+2C0h+var_318]
0x18002b7b6  call    ?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)
0x18002b7bb  mov     r14, [rax]
0x18002b7be  call    cs:__imp_GetCurrentThreadId
0x18002b7c4  mov     dword ptr [rbp+2C0h+var_340+4], eax
0x18002b7c7  mov     r8, [rdi+110h]
0x18002b7ce  mov     eax, [r8+48h]
0x18002b7d2  mov     dword ptr [rbp+2C0h+var_340], eax
0x18002b7d5  mov     eax, 1000000h
0x18002b7da  mov     [rbp+2C0h+var_330], rax
0x18002b7de  lea     rax, [rbp+2C0h+var_338]
0x18002b7e2  mov     [rbp+2C0h+var_250], rax
0x18002b7e6  mov     [rbp+2C0h+var_248], 4
0x18002b7ee  test    r14, r14
0x18002b7f1  jz      short loc_18002B80A
0x18002b7f3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002b7f7  inc     rbx
0x18002b7fa  cmp     [r14+rbx*2], r15w
0x18002b7ff  jnz     short loc_18002B7F7
0x18002b801  lea     ebx, ds:2[rbx*2]
0x18002b808  jmp     short loc_18002B811
0x18002b80a  lea     r14, qword_18003A1F8
0x18002b811  mov     [rbp+2C0h+var_260], r14
0x18002b815  mov     [rbp+2C0h+var_258], ebx
0x18002b818  mov     [rbp+2C0h+var_254], r15d
0x18002b81c  lea     rax, [rbp+2C0h+var_340+4]
0x18002b820  mov     [rbp+2C0h+var_270], rax
0x18002b824  mov     [rbp+2C0h+var_268], 4
0x18002b82c  lea     rax, [rbp+2C0h+var_340]
0x18002b830  mov     [rbp+2C0h+var_280], rax
0x18002b834  mov     [rbp+2C0h+var_278], 4
0x18002b83c  lea     rax, [rbp+2C0h+var_330]
0x18002b840  mov     [rbp+2C0h+var_290], rax
0x18002b844  mov     [rbp+2C0h+var_288], 8
0x18002b84c  add     r8, 8; int
0x18002b850  lea     rax, [rbp+2C0h+var_2B0]
0x18002b854  mov     [rsp+3F0h+var_3C8], rax; PEVENT_DATA_DESCRIPTOR
0x18002b859  mov     [rsp+3F0h+var_3D0], 7; ULONG
0x18002b861  xor     r9d, r9d; int
0x18002b864  lea     rdx, byte_180043911; int
0x18002b86b  mov     rcx, rsi; int
0x18002b86e  call    _tlgWriteTransfer_EventWriteTransfer
0x18002b873  mov     rbx, [rbp+2C0h+var_318]
0x18002b877  test    rbx, rbx
0x18002b87a  jz      short loc_18002B890
0x18002b87c  call    cs:__imp_GetProcessHeap
0x18002b882  mov     r8, rbx; lpMem
0x18002b885  xor     edx, edx; dwFlags
0x18002b887  mov     rcx, rax; hHeap
0x18002b88a  call    cs:__imp_HeapFree
0x18002b890  mov     rcx, rdi
0x18002b893  call    ?IgnoreCurrentThread@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18002b898  mov     rcx, [rbp+2C0h+var_30]
0x18002b89f  xor     rcx, rsp; StackCookie
0x18002b8a2  call    __security_check_cookie
0x18002b8a7  mov     rbx, [rsp+3F0h+arg_10]
0x18002b8af  add     rsp, 3D0h
0x18002b8b6  pop     r15
0x18002b8b8  pop     r14
0x18002b8ba  pop     rdi
0x18002b8bb  pop     rsi
0x18002b8bc  pop     rbp
0x18002b8bd  retn
```
