# StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::Stop(ushort const *,ushort,ulong,ulong,ulong,unsigned __int64,unsigned __int64,long)

- ea: `0x18002afa8`
- end: `0x18002b4dc`
- name: `?Stop@FixReserveAreaUntaggedParent@SRProvider@Internal@StorageReserveTelemetry@@QEAAXPEBGGKKK_K1J@Z`
- size: `1332`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent *this, const unsigned __int16 *, __int64, unsigned int, unsigned int, unsigned int, unsigned __int64, RTL_SRWLOCK *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180027414`

## callees

- `0x1800013b4`
- `0x1800021b0`
- `0x180003870`
- `0x1800042dc`
- `0x1800042f4`
- `0x180028494`
- `0x180028738`
- `0x180028ac8`
- `0x18002939c`
- `0x18002afa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b061`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b2ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b061`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b2ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b495`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b495`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b4a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b4a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b33e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b33e`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::Stop(
        StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int64 a7,
        RTL_SRWLOCK *a8,
        int a9)
{
  __int64 v9; // r15
  __int64 v12; // rsi
  int v13; // eax
  int *v14; // rsi
  const struct _tlgProvider_t *v15; // rax
  const struct _tlgProvider_t *v16; // r14
  __int64 v17; // rax
  __int64 v18; // r9
  PSRWLOCK v19; // rbx
  int v20; // ebx
  const struct _tlgProvider_t *v21; // rax
  const struct _tlgProvider_t *v22; // rsi
  __int64 v23; // rax
  unsigned __int16 *v24; // r14
  __int64 v25; // r8
  __int64 v26; // rbx
  HANDLE ProcessHeap; // rax
  _WORD v28[2]; // [rsp+E8h] [rbp-80h] BYREF
  int v29; // [rsp+ECh] [rbp-7Ch] BYREF
  __int64 v30; // [rsp+F0h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+F8h] [rbp-70h] BYREF
  PSRWLOCK v32; // [rsp+100h] [rbp-68h] BYREF
  int v33; // [rsp+108h] [rbp-60h] BYREF
  int v34; // [rsp+10Ch] [rbp-5Ch] BYREF
  int v35; // [rsp+110h] [rbp-58h] BYREF
  int v36; // [rsp+114h] [rbp-54h] BYREF
  RTL_SRWLOCK *v37; // [rsp+118h] [rbp-50h] BYREF
  __int64 v38; // [rsp+120h] [rbp-48h] BYREF
  __int64 v39; // [rsp+128h] [rbp-40h] BYREF
  __int64 v40; // [rsp+130h] [rbp-38h] BYREF
  __int64 v41; // [rsp+138h] [rbp-30h] BYREF
  __int64 v42; // [rsp+140h] [rbp-28h] BYREF
  __int64 v43; // [rsp+148h] [rbp-20h] BYREF
  __int64 v44; // [rsp+150h] [rbp-18h] BYREF
  __int64 v45; // [rsp+158h] [rbp-10h] BYREF
  __int64 v46; // [rsp+160h] [rbp-8h] BYREF
  __int64 v47; // [rsp+168h] [rbp+0h] BYREF
  __int64 v48; // [rsp+170h] [rbp+8h] BYREF
  __int64 v49; // [rsp+178h] [rbp+10h] BYREF
  __int64 v50; // [rsp+180h] [rbp+18h] BYREF
  __int64 v51; // [rsp+188h] [rbp+20h] BYREF
  __int64 v52[3]; // [rsp+190h] [rbp+28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+1A8h] [rbp+40h] BYREF
  __int64 *v54; // [rsp+1C8h] [rbp+60h]
  __int64 v55; // [rsp+1D0h] [rbp+68h]
  int *v56; // [rsp+1D8h] [rbp+70h]
  __int64 v57; // [rsp+1E0h] [rbp+78h]
  __int64 *v58; // [rsp+1E8h] [rbp+80h]
  __int64 v59; // [rsp+1F0h] [rbp+88h]
  unsigned __int16 *v60; // [rsp+1F8h] [rbp+90h]
  int v61; // [rsp+200h] [rbp+98h]
  int v62; // [rsp+204h] [rbp+9Ch]
  _WORD *v63; // [rsp+208h] [rbp+A0h]
  __int64 v64; // [rsp+210h] [rbp+A8h]
  __int64 *v65; // [rsp+218h] [rbp+B0h]
  __int64 v66; // [rsp+220h] [rbp+B8h]
  __int64 *v67; // [rsp+228h] [rbp+C0h]
  __int64 v68; // [rsp+230h] [rbp+C8h]
  __int64 *v69; // [rsp+238h] [rbp+D0h]
  __int64 v70; // [rsp+240h] [rbp+D8h]
  __int64 *v71; // [rsp+248h] [rbp+E0h]
  __int64 v72; // [rsp+250h] [rbp+E8h]
  PSRWLOCK *v73; // [rsp+258h] [rbp+F0h]
  __int64 v74; // [rsp+260h] [rbp+F8h]
  PSRWLOCK *p_SRWLock; // [rsp+268h] [rbp+100h]
  __int64 v76; // [rsp+270h] [rbp+108h]
  wchar_t Destination[264]; // [rsp+278h] [rbp+110h] BYREF

  v52[1] = -2;
  v9 = a4;
  memset_0(Destination, 0, 0x208u);
  wcscpy_s(Destination, 0x104u, a2);
  v12 = *((_QWORD *)this + 34);
  v13 = *(_DWORD *)(v12 + 72);
  if ( v13 < 0 && (v14 = (int *)(v12 + 80), v13 == v14[2]) && v14 )
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v15 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v16 = v15;
    if ( *(_DWORD *)v15 > 5u )
    {
      v17 = *((_QWORD *)v15 + 3);
      if ( (*((_QWORD *)v16 + 2) & 0x400000000000LL) != 0 && (v17 & 0x400000000000LL) == v17 )
      {
        v33 = a9;
        v43 = (__int64)a8;
        v44 = a7;
        v45 = a6;
        v46 = a5;
        v47 = v9;
        v28[0] = 2;
        v48 = (__int64)*StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
                          (unsigned __int16 **)&v32,
                          Destination);
        v49 = *((_QWORD *)v14 + 15);
        v50 = *((_QWORD *)v14 + 14);
        v34 = v14[26];
        v51 = *((_QWORD *)v14 + 12);
        v52[0] = *((_QWORD *)v14 + 11);
        v35 = v14[20];
        v37 = (RTL_SRWLOCK *)*((_QWORD *)v14 + 9);
        v36 = v14[8];
        v38 = *((_QWORD *)v14 + 3);
        v29 = *v14;
        v39 = *((_QWORD *)v14 + 16);
        LODWORD(v30) = v14[16];
        v40 = *((_QWORD *)v14 + 7);
        LODWORD(SRWLock) = v14[2];
        v41 = 0x1000000;
        v42 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (int)v16,
          (int)&word_180044B9A,
          *((_QWORD *)this + 34) + 8,
          v18,
          (__int64)&v42,
          (__int64)&v41,
          (__int64)&SRWLock,
          (const wchar_t **)&v40,
          (__int64)&v30,
          (const wchar_t **)&v39,
          (__int64)&v29,
          (const unsigned __int16 **)&v38,
          (__int64)&v36,
          (const wchar_t **)&v37,
          (__int64)&v35,
          (const wchar_t **)v52,
          (const unsigned __int16 **)&v51,
          (__int64)&v34,
          (const wchar_t **)&v50,
          (const unsigned __int16 **)&v49,
          (const unsigned __int16 **)&v48,
          (__int64)v28,
          (__int64)&v47,
          (__int64)&v46,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v33);
        v19 = v32;
LABEL_21:
        if ( v19 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v19);
        }
      }
    }
  }
  else
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v32);
    v20 = 2;
    **((_DWORD **)this + 34) = 2;
    if ( v32 )
      ReleaseSRWLockExclusive(v32);
    v21 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v22 = v21;
    if ( *(_DWORD *)v21 > 5u )
    {
      v23 = *((_QWORD *)v21 + 3);
      if ( (*((_QWORD *)v22 + 2) & 0x400000000000LL) != 0 && (v23 & 0x400000000000LL) == v23 )
      {
        LODWORD(SRWLock) = a9;
        v32 = a8;
        v42 = a7;
        v41 = a6;
        v40 = a5;
        v39 = v9;
        v28[0] = 2;
        v24 = *StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
                 (unsigned __int16 **)&v37,
                 Destination);
        LODWORD(v30) = GetCurrentThreadId();
        v25 = *((_QWORD *)this + 34);
        v29 = *(_DWORD *)(v25 + 72);
        v38 = 0x1000000;
        p_SRWLock = &SRWLock;
        v76 = 4;
        v73 = &v32;
        v74 = 8;
        v71 = &v42;
        v72 = 8;
        v69 = &v41;
        v70 = 8;
        v67 = &v40;
        v68 = 8;
        v65 = &v39;
        v66 = 8;
        v63 = v28;
        v64 = 2;
        if ( v24 )
        {
          v26 = -1;
          do
            ++v26;
          while ( v24[v26] );
          v20 = 2 * v26 + 2;
        }
        else
        {
          v24 = (unsigned __int16 *)&qword_18003A1F8;
        }
        v60 = v24;
        v61 = v20;
        v62 = 0;
        v58 = &v30;
        v59 = 4;
        v56 = &v29;
        v57 = 4;
        v54 = &v38;
        v55 = 8;
        tlgWriteTransfer_EventWriteTransfer((int)v22, (int)&byte_180044AC7, v25 + 8, 0, 0xDu, &v53);
        v19 = v37;
        goto LABEL_21;
      }
    }
  }
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002afa8  mov     rax, rsp
0x18002afab  push    rbp
0x18002afac  push    rdi
0x18002afad  push    r12
0x18002afaf  push    r14
0x18002afb1  push    r15
0x18002afb3  lea     rbp, [rax-358h]
0x18002afba  sub     rsp, 490h
0x18002afc1  mov     [rbp+350h+var_320], 0FFFFFFFFFFFFFFFEh
0x18002afc9  mov     [rax+18h], rbx
0x18002afcd  mov     [rax+20h], rsi
0x18002afd1  mov     rax, cs:__security_cookie
0x18002afd8  xor     rax, rsp
0x18002afdb  mov     [rbp+350h+var_30], rax
0x18002afe2  mov     r15d, r9d
0x18002afe5  mov     rbx, rdx
0x18002afe8  mov     rdi, rcx
0x18002afeb  xor     edx, edx; Val
0x18002afed  mov     r8d, 208h; Size
0x18002aff3  lea     rcx, [rbp+350h+Destination]; void *
0x18002affa  call    memset_0
0x18002afff  mov     r8, rbx; Source
0x18002b002  mov     edx, 104h; SizeInWords
0x18002b007  lea     rcx, [rbp+350h+Destination]; Destination
0x18002b00e  call    wcscpy_s
0x18002b013  mov     rsi, [rdi+110h]
0x18002b01a  mov     eax, [rsi+48h]
0x18002b01d  xor     r12d, r12d
0x18002b020  test    eax, eax
0x18002b022  jns     loc_18002B289
0x18002b028  add     rsi, 50h ; 'P'
0x18002b02c  cmp     eax, [rsi+8]
0x18002b02f  jnz     loc_18002B289
0x18002b035  test    rsi, rsi
0x18002b038  jz      loc_18002B289
0x18002b03e  lea     rdx, [rbp+350h+SRWLock]
0x18002b042  mov     rcx, rdi
0x18002b045  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b04a  mov     rax, [rdi+110h]
0x18002b051  lea     ebx, [r12+2]
0x18002b056  mov     [rax], ebx
0x18002b058  mov     rcx, [rbp+350h+SRWLock]; SRWLock
0x18002b05c  test    rcx, rcx
0x18002b05f  jz      short loc_18002B068
0x18002b061  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b067  nop
0x18002b068  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002b06d  mov     r14, rax
0x18002b070  mov     ecx, [rax]
0x18002b072  cmp     ecx, 5
0x18002b075  jbe     loc_18002B4A9
0x18002b07b  mov     rax, [rax+18h]
0x18002b07f  mov     rcx, [r14+10h]
0x18002b083  mov     rdx, 400000000000h
0x18002b08d  test    rdx, rcx
0x18002b090  jz      loc_18002B4A9
0x18002b096  mov     rcx, rax
0x18002b099  and     rcx, rdx
0x18002b09c  cmp     rcx, rax
0x18002b09f  jnz     loc_18002B4A9
0x18002b0a5  mov     eax, [rbp+350h+arg_40]
0x18002b0ab  mov     dword ptr [rbp+350h+var_3B0], eax
0x18002b0ae  mov     rax, [rbp+350h+arg_38]
0x18002b0b5  mov     [rbp+350h+var_370], rax
0x18002b0b9  mov     rax, [rbp+350h+arg_30]
0x18002b0c0  mov     [rbp+350h+var_368], rax
0x18002b0c4  mov     eax, [rbp+350h+arg_28]
0x18002b0ca  mov     [rbp+350h+var_360], rax
0x18002b0ce  mov     eax, [rbp+350h+arg_20]
0x18002b0d4  mov     [rbp+350h+var_358], rax
0x18002b0d8  mov     [rbp+350h+var_350], r15
0x18002b0dc  mov     word ptr [rbp+350h+var_3D0], bx
0x18002b0e0  lea     rdx, [rbp+350h+Destination]
0x18002b0e7  lea     rcx, [rbp+350h+var_3B8]
0x18002b0eb  call    ?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)
0x18002b0f0  mov     rcx, [rax]
0x18002b0f3  mov     [rbp+350h+var_348], rcx
0x18002b0f7  mov     rax, [rsi+78h]
0x18002b0fb  mov     [rbp+350h+var_340], rax
0x18002b0ff  mov     rax, [rsi+70h]
0x18002b103  mov     [rbp+350h+var_338], rax
0x18002b107  mov     eax, [rsi+68h]
0x18002b10a  mov     dword ptr [rbp+350h+var_3B0+4], eax
0x18002b10d  mov     rax, [rsi+60h]
0x18002b111  mov     [rbp+350h+var_330], rax
0x18002b115  mov     rax, [rsi+58h]
0x18002b119  mov     [rbp+350h+var_328], rax
0x18002b11d  mov     eax, [rsi+50h]
0x18002b120  mov     dword ptr [rbp+350h+var_3A8], eax
0x18002b123  mov     rax, [rsi+48h]
0x18002b127  mov     [rbp+350h+var_3A0], rax
0x18002b12b  mov     eax, [rsi+20h]
0x18002b12e  mov     dword ptr [rbp+350h+var_3A8+4], eax
0x18002b131  mov     rax, [rsi+18h]
0x18002b135  mov     [rbp+350h+var_398], rax
0x18002b139  mov     eax, [rsi]
0x18002b13b  mov     dword ptr [rbp+350h+var_3D0+4], eax
0x18002b13e  mov     rax, [rsi+80h]
0x18002b145  mov     [rbp+350h+var_390], rax
0x18002b149  mov     eax, [rsi+40h]
0x18002b14c  mov     dword ptr [rbp+350h+var_3C8], eax
0x18002b14f  mov     rax, [rsi+38h]
0x18002b153  mov     [rbp+350h+var_388], rax
0x18002b157  mov     eax, [rsi+8]
0x18002b15a  mov     dword ptr [rbp+350h+SRWLock], eax
0x18002b15d  mov     eax, 1000000h
0x18002b162  mov     [rbp+350h+var_380], rax
0x18002b166  mov     [rbp+350h+var_378], rax
0x18002b16a  mov     r8, [rdi+110h]
0x18002b171  add     r8, 8; int
0x18002b175  lea     rax, [rbp+350h+var_3B0]
0x18002b179  mov     [rsp+4B0h+var_3D8], rax; __int64
0x18002b181  lea     rax, [rbp+350h+var_370]
0x18002b185  mov     [rsp+4B0h+var_3E0], rax; __int64
0x18002b18d  lea     rax, [rbp+350h+var_368]
0x18002b191  mov     [rsp+4B0h+var_3E8], rax; __int64
0x18002b199  lea     rax, [rbp+350h+var_360]
0x18002b19d  mov     [rsp+4B0h+var_3F0], rax; __int64
0x18002b1a5  lea     rax, [rbp+350h+var_358]
0x18002b1a9  mov     [rsp+4B0h+var_3F8], rax; __int64
0x18002b1b1  lea     rax, [rbp+350h+var_350]
0x18002b1b5  mov     [rsp+4B0h+var_400], rax; __int64
0x18002b1bd  lea     rax, [rbp+350h+var_3D0]
0x18002b1c1  mov     [rsp+4B0h+var_408], rax; __int64
0x18002b1c9  lea     rax, [rbp+350h+var_348]
0x18002b1cd  mov     [rsp+4B0h+var_410], rax; __int64
0x18002b1d5  lea     rax, [rbp+350h+var_340]
0x18002b1d9  mov     [rsp+4B0h+var_418], rax; __int64
0x18002b1e1  lea     rax, [rbp+350h+var_338]
0x18002b1e5  mov     [rsp+4B0h+var_420], rax; __int64
0x18002b1ed  lea     rax, [rbp+350h+var_3B0+4]
0x18002b1f1  mov     [rsp+4B0h+var_428], rax; __int64
0x18002b1f9  lea     rax, [rbp+350h+var_330]
0x18002b1fd  mov     [rsp+4B0h+var_430], rax; __int64
0x18002b205  lea     rax, [rbp+350h+var_328]
0x18002b209  mov     [rsp+4B0h+var_438], rax; __int64
0x18002b20e  lea     rax, [rbp+350h+var_3A8]
0x18002b212  mov     [rsp+4B0h+var_440], rax; __int64
0x18002b217  lea     rax, [rbp+350h+var_3A0]
0x18002b21b  mov     [rsp+4B0h+var_448], rax; __int64
0x18002b220  lea     rax, [rbp+350h+var_3A8+4]
0x18002b224  mov     [rsp+4B0h+var_450], rax; __int64
0x18002b229  lea     rax, [rbp+350h+var_398]
0x18002b22d  mov     [rsp+4B0h+var_458], rax; __int64
0x18002b232  lea     rax, [rbp+350h+var_3D0+4]
0x18002b236  mov     [rsp+4B0h+var_460], rax; __int64
0x18002b23b  lea     rax, [rbp+350h+var_390]
0x18002b23f  mov     [rsp+4B0h+var_468], rax; __int64
0x18002b244  lea     rax, [rbp+350h+var_3C8]
0x18002b248  mov     [rsp+4B0h+var_470], rax; __int64
0x18002b24d  lea     rax, [rbp+350h+var_388]
0x18002b251  mov     [rsp+4B0h+var_478], rax; __int64
0x18002b256  lea     rax, [rbp+350h+SRWLock]
0x18002b25a  mov     [rsp+4B0h+var_480], rax; __int64
0x18002b25f  lea     rax, [rbp+350h+var_380]
0x18002b263  mov     [rsp+4B0h+var_488], rax; __int64
0x18002b268  lea     rax, [rbp+350h+var_378]
0x18002b26c  mov     qword ptr [rsp+4B0h+var_490], rax; __int64
0x18002b271  lea     rdx, word_180044B9A; int
0x18002b278  mov     rcx, r14; int
0x18002b27b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$01@@U1@U1@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566AEBU?$_tlgWrapperByVal@$01@@333334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002b280  mov     rbx, [rbp+350h+var_3B8]
0x18002b284  jmp     loc_18002B490
0x18002b289  lea     rdx, [rbp+350h+var_3B8]
0x18002b28d  mov     rcx, rdi
0x18002b290  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b295  mov     rax, [rdi+110h]
0x18002b29c  mov     ebx, 2
0x18002b2a1  mov     [rax], ebx
0x18002b2a3  mov     rcx, [rbp+350h+var_3B8]; SRWLock
0x18002b2a7  test    rcx, rcx
0x18002b2aa  jz      short loc_18002B2B3
0x18002b2ac  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b2b2  nop
0x18002b2b3  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002b2b8  mov     rsi, rax
0x18002b2bb  mov     ecx, [rax]
0x18002b2bd  cmp     ecx, 5
0x18002b2c0  jbe     loc_18002B4A9
0x18002b2c6  mov     rax, [rax+18h]
0x18002b2ca  mov     rcx, [rsi+10h]
0x18002b2ce  mov     rdx, 400000000000h
0x18002b2d8  test    rdx, rcx
0x18002b2db  jz      loc_18002B4A9
0x18002b2e1  mov     rcx, rax
0x18002b2e4  and     rcx, rdx
0x18002b2e7  cmp     rcx, rax
0x18002b2ea  jnz     loc_18002B4A9
0x18002b2f0  mov     eax, [rbp+350h+arg_40]
0x18002b2f6  mov     dword ptr [rbp+350h+SRWLock], eax
0x18002b2f9  mov     rax, [rbp+350h+arg_38]
0x18002b300  mov     [rbp+350h+var_3B8], rax
0x18002b304  mov     rax, [rbp+350h+arg_30]
0x18002b30b  mov     [rbp+350h+var_378], rax
0x18002b30f  mov     eax, [rbp+350h+arg_28]
0x18002b315  mov     [rbp+350h+var_380], rax
0x18002b319  mov     eax, [rbp+350h+arg_20]
0x18002b31f  mov     [rbp+350h+var_388], rax
0x18002b323  mov     [rbp+350h+var_390], r15
0x18002b327  mov     word ptr [rbp+350h+var_3D0], bx
0x18002b32b  lea     rdx, [rbp+350h+Destination]
0x18002b332  lea     rcx, [rbp+350h+var_3A0]
0x18002b336  call    ?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)
0x18002b33b  mov     r14, [rax]
0x18002b33e  call    cs:__imp_GetCurrentThreadId
0x18002b344  mov     dword ptr [rbp+350h+var_3C8], eax
0x18002b347  mov     r8, [rdi+110h]
0x18002b34e  mov     eax, [r8+48h]
0x18002b352  mov     dword ptr [rbp+350h+var_3D0+4], eax
0x18002b355  mov     eax, 1000000h
0x18002b35a  mov     [rbp+350h+var_398], rax
0x18002b35e  lea     rax, [rbp+350h+SRWLock]
0x18002b362  mov     [rbp+350h+var_250], rax
0x18002b369  mov     [rbp+350h+var_248], 4
0x18002b374  lea     rax, [rbp+350h+var_3B8]
0x18002b378  mov     [rbp+350h+var_260], rax
0x18002b37f  mov     [rbp+350h+var_258], 8
0x18002b38a  lea     rcx, [rbp+350h+var_378]
0x18002b38e  mov     [rbp+350h+var_270], rcx
0x18002b395  mov     [rbp+350h+var_268], 8
0x18002b3a0  lea     rcx, [rbp+350h+var_380]
0x18002b3a4  mov     [rbp+350h+var_280], rcx
0x18002b3ab  mov     [rbp+350h+var_278], 8
0x18002b3b6  lea     rcx, [rbp+350h+var_388]
0x18002b3ba  mov     [rbp+350h+var_290], rcx
0x18002b3c1  mov     [rbp+350h+var_288], 8
0x18002b3cc  lea     rcx, [rbp+350h+var_390]
0x18002b3d0  mov     [rbp+350h+var_2A0], rcx
0x18002b3d7  mov     [rbp+350h+var_298], 8
0x18002b3e2  lea     rcx, [rbp+350h+var_3D0]
0x18002b3e6  mov     [rbp+350h+var_2B0], rcx
0x18002b3ed  mov     [rbp+350h+var_2A8], 2
0x18002b3f8  test    r14, r14
0x18002b3fb  jz      short loc_18002B414
0x18002b3fd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002b401  inc     rbx
0x18002b404  cmp     [r14+rbx*2], r12w
0x18002b409  jnz     short loc_18002B401
0x18002b40b  lea     ebx, ds:2[rbx*2]
0x18002b412  jmp     short loc_18002B41B
0x18002b414  lea     r14, qword_18003A1F8
0x18002b41b  mov     [rbp+350h+var_2C0], r14
0x18002b422  mov     [rbp+350h+var_2B8], ebx
0x18002b428  mov     [rbp+350h+var_2B4], r12d
0x18002b42f  lea     rcx, [rbp+350h+var_3C8]
0x18002b433  mov     [rbp+350h+var_2D0], rcx
0x18002b43a  mov     [rbp+350h+var_2C8], 4
0x18002b445  lea     rcx, [rbp+350h+var_3D0+4]
0x18002b449  mov     [rbp+350h+var_2E0], rcx
0x18002b44d  mov     [rbp+350h+var_2D8], 4
0x18002b455  lea     rcx, [rbp+350h+var_398]
0x18002b459  mov     [rbp+350h+var_2F0], rcx
0x18002b45d  mov     [rbp+350h+var_2E8], 8
0x18002b465  add     r8, 8; int
0x18002b469  lea     rax, [rbp+350h+var_310]
0x18002b46d  mov     [rsp+4B0h+var_488], rax; PEVENT_DATA_DESCRIPTOR
0x18002b472  mov     [rsp+4B0h+var_490], 0Dh; ULONG
0x18002b47a  xor     r9d, r9d; int
0x18002b47d  lea     rdx, byte_180044AC7; int
0x18002b484  mov     rcx, rsi; int
0x18002b487  call    _tlgWriteTransfer_EventWriteTransfer
0x18002b48c  mov     rbx, [rbp+350h+var_3A0]
0x18002b490  test    rbx, rbx
0x18002b493  jz      short loc_18002B4A9
0x18002b495  call    cs:__imp_GetProcessHeap
0x18002b49b  mov     r8, rbx; lpMem
0x18002b49e  xor     edx, edx; dwFlags
0x18002b4a0  mov     rcx, rax; hHeap
0x18002b4a3  call    cs:__imp_HeapFree
0x18002b4a9  mov     rcx, rdi
0x18002b4ac  call    ?IgnoreCurrentThread@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18002b4b1  mov     rcx, [rbp+350h+var_30]
0x18002b4b8  xor     rcx, rsp; StackCookie
0x18002b4bb  call    __security_check_cookie
0x18002b4c0  lea     r11, [rsp+4B0h+var_20]
0x18002b4c8  mov     rbx, [r11+40h]
0x18002b4cc  mov     rsi, [r11+48h]
0x18002b4d0  mov     rsp, r11
0x18002b4d3  pop     r15
0x18002b4d5  pop     r14
0x18002b4d7  pop     r12
0x18002b4d9  pop     rdi
0x18002b4da  pop     rbp
0x18002b4db  retn
```
