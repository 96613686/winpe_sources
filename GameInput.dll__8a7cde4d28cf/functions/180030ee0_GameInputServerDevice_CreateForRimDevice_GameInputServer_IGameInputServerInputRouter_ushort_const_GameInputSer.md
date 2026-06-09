# GameInputServerDevice::CreateForRimDevice(GameInputServer *,IGameInputServerInputRouter *,ushort const *,GameInputServerDevice * *)

- ea: `0x180030ee0`
- end: `0x180031975`
- name: `?CreateForRimDevice@GameInputServerDevice@@SAJPEAVGameInputServer@@PEAUIGameInputServerInputRouter@@PEBGPEAPEAV1@@Z`
- size: `2709`
- prototype: `__int64 __fastcall(struct GameInputServer *, struct IGameInputServerInputRouter *, const unsigned __int16 *Src, struct GameInputServerDevice **)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180030308`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x1800230d8`
- `0x1800231fc`
- `0x1800232b4`
- `0x180023558`
- `0x1800244ac`
- `0x18002ce50`
- `0x18002d1c8`
- `0x18002d610`
- `0x18002da74`
- `0x18002e838`
- `0x18002e9a4`
- `0x180030ee0`
- `0x18003b5b4`
- `0x18003ca44`
- `0x18003cccc`
- `0x180047dd0`
- `0x18004c8a5`
- `0x18004c8bd`
- `0x18004c8e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180030f50`
- `ntdll!RtlAllocateHeap` at `0x18003132f`
- `ntdll!RtlAllocateHeap` at `0x18003139a`
- `ntdll!RtlAllocateHeap` at `0x18003143d`
- `ntdll!RtlAllocateHeap` at `0x1800314e0`
- `ntdll!RtlAllocateHeap` at `0x18003158e`
- `ntdll!RtlAllocateHeap` at `0x18003165b`
- `ntdll!RtlAllocateHeap` at `0x180031714`
- `ntdll!RtlAllocateHeap` at `0x1800317aa`
- `ntdll!RtlAllocateHeap` at `0x180030f50`
- `ntdll!RtlAllocateHeap` at `0x18003132f`
- `ntdll!RtlAllocateHeap` at `0x18003139a`
- `ntdll!RtlAllocateHeap` at `0x18003143d`
- `ntdll!RtlAllocateHeap` at `0x1800314e0`
- `ntdll!RtlAllocateHeap` at `0x18003158e`
- `ntdll!RtlAllocateHeap` at `0x18003165b`
- `ntdll!RtlAllocateHeap` at `0x180031714`
- `ntdll!RtlAllocateHeap` at `0x1800317aa`

## pseudocode

```c
__int64 __fastcall GameInputServerDevice::CreateForRimDevice(
        HKL *a1,
        struct IGameInputServerInputRouter *a2,
        wchar_t *Src,
        struct GameInputServerDevice **a4)
{
  int v8; // r12d
  GameInputServerDevice *Heap; // rax
  int v10; // r8d
  int v11; // r9d
  GameInputServerDevice *v12; // rbx
  int AppLocalDeviceId; // edi
  int v14; // r9d
  PUCHAR *v15; // rsi
  int v16; // r9d
  __int64 v17; // rcx
  int v18; // r9d
  int v19; // r8d
  int v20; // ecx
  char *v21; // rdx
  HKL v22; // rcx
  const struct std::nothrow_t *v23; // rdx
  void *v24; // rcx
  char *v25; // rax
  char *v26; // rdi
  const struct std::nothrow_t *v27; // rdx
  void *v28; // rcx
  CallbackDataLayout *v29; // rax
  const struct std::nothrow_t *v30; // rdx
  CallbackDataLayout *v31; // rax
  void *v32; // rcx
  ReadingDataLayout *v33; // rax
  const struct std::nothrow_t *v34; // rdx
  ReadingDataLayout *v35; // rax
  void *v36; // rcx
  InputDataLayout *v37; // rax
  const struct std::nothrow_t *v38; // rdx
  InputDataLayout *v39; // rax
  void *v40; // rcx
  SharedBufferLayout *v41; // rax
  const struct std::nothrow_t *v42; // rdx
  SharedBufferLayout *v43; // rax
  void *v44; // rcx
  unsigned int *v45; // rax
  unsigned int v46; // ecx
  PVOID v47; // rax
  const struct std::nothrow_t *v48; // rdx
  void *v49; // rcx
  void *v50; // rcx
  PVOID v51; // rax
  const struct std::nothrow_t *v52; // rdx
  void *v53; // rcx
  PVOID v54; // rax
  const struct std::nothrow_t *v55; // rdx
  void *v56; // rcx
  const struct std::nothrow_t *v58; // rdx
  int v59; // [rsp+40h] [rbp-C0h] BYREF
  int v60; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v61; // [rsp+48h] [rbp-B8h] BYREF
  int v62; // [rsp+50h] [rbp-B0h]
  int v63; // [rsp+54h] [rbp-ACh]
  struct GameInputDeviceInfo *v64; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v65[6]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v66; // [rsp+78h] [rbp-88h]
  __int64 v67; // [rsp+80h] [rbp-80h]
  UCHAR pbOutput[16]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v69; // [rsp+98h] [rbp-68h]
  _BYTE v70[4]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v71; // [rsp+ACh] [rbp-54h]
  __int16 v72; // [rsp+B4h] [rbp-4Ch]
  __int16 v73; // [rsp+B6h] [rbp-4Ah]
  __int128 v74; // [rsp+C8h] [rbp-38h]
  __int128 v75; // [rsp+D8h] [rbp-28h]
  __int128 v76; // [rsp+E8h] [rbp-18h]
  __int128 v77; // [rsp+F8h] [rbp-8h]
  int v78; // [rsp+108h] [rbp+8h]
  int v79; // [rsp+10Ch] [rbp+Ch]

  *a4 = 0;
  v8 = wcsncmp_0(Src, L"\\\\?\\Microsoft Keyboard RID\\", 0x1Bu);
  Heap = (GameInputServerDevice *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x260u);
  if ( !Heap || (v12 = GameInputServerDevice::GameInputServerDevice(Heap, (struct GameInputServer *)a1, a2, 0)) == 0 )
  {
    AppLocalDeviceId = -2147024882;
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v60 = -2147024882;
      v61 = (__int64)"onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
      v59 = 513;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_18005F2DB,
        v10,
        v11,
        (__int64)&v61,
        (__int64)&v59,
        (__int64)&v60);
    }
    return (unsigned int)AppLocalDeviceId;
  }
  AppLocalDeviceId = CopyStringToBuffer(Src);
  if ( AppLocalDeviceId < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v59 = AppLocalDeviceId;
      v61 = (__int64)"onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
      v60 = 516;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)&word_180060556,
        qword_180069018,
        v14,
        (__int64)&v61,
        (__int64)&v60,
        (__int64)&v59);
    }
    goto LABEL_110;
  }
  v15 = (PUCHAR *)((char *)v12 + 200);
  AppLocalDeviceId = CopyStringToBuffer(Src);
  if ( AppLocalDeviceId < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v60 = AppLocalDeviceId;
      v61 = (__int64)"onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
      v59 = 517;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)byte_18005FA9D,
        qword_180069018,
        v16,
        (__int64)&v61,
        (__int64)&v59,
        (__int64)&v60);
    }
    goto LABEL_110;
  }
  GameInputDeviceInfoBuilder::GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v70);
  v71 = 0;
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)&(*v15)[2 * v17] );
  *(_OWORD *)pbOutput = 0;
  v69 = 0;
  AppLocalDeviceId = GameInputServerDevice::GenerateAppLocalDeviceId(2 * (int)v17, *v15, pbOutput);
  if ( AppLocalDeviceId >= 0 )
  {
    v72 = 1;
    v74 = *(_OWORD *)pbOutput;
    v78 = -1;
    v79 = 0;
    v73 = v8 != 0 ? 2 : 6;
    v75 = v69;
    v76 = *(_OWORD *)pbOutput;
    v77 = v69;
    if ( v8 )
    {
      v63 = 256;
      v61 = 7;
      v62 = 0;
      AppLocalDeviceId = GameInputDeviceInfoBuilder::AddMouseInfo(
                           (GameInputDeviceInfoBuilder *)v70,
                           (const struct GameInputMouseInfo *)&v61);
      if ( AppLocalDeviceId < 0 )
      {
        if ( (unsigned int)dword_180069000 <= 2 )
          goto LABEL_109;
        v19 = qword_180069018;
        v20 = qword_180069010;
        if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
          goto LABEL_109;
        v59 = 578;
        v21 = byte_1800607E1;
        goto LABEL_108;
      }
    }
    else
    {
      v22 = a1[28];
      v66 = 0;
      v65[0] = -1;
      v65[1] = KeyboardLookupTable::KlidFromHkl(v22);
      v65[2] = 104;
      v65[3] = 12;
      v65[4] = 16;
      v65[5] = 4;
      v67 = 0;
      AppLocalDeviceId = GameInputDeviceInfoBuilder::AddKeyboardInfo(
                           (GameInputDeviceInfoBuilder *)v70,
                           (const struct GameInputKeyboardInfo *)v65);
      if ( AppLocalDeviceId < 0 )
      {
        if ( (unsigned int)dword_180069000 <= 2 )
          goto LABEL_109;
        v19 = qword_180069018;
        v20 = qword_180069010;
        if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
          goto LABEL_109;
        v59 = 565;
        v21 = byte_1800627A1;
        goto LABEL_108;
      }
    }
    v64 = 0;
    AppLocalDeviceId = GameInputDeviceInfoBuilder::Make((GameInputDeviceInfoBuilder *)v70, &v64);
    if ( AppLocalDeviceId >= 0 )
    {
      v24 = (void *)*((_QWORD *)v12 + 11);
      *((_QWORD *)v12 + 11) = v64;
      if ( v24 )
        operator delete(v24, v23);
      v25 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x340u);
      v26 = v25;
      if ( v25 )
      {
        memset_0(v25 + 4, 0, 0x33Cu);
        memset_0(v26 + 4, 0, 0x33Cu);
        *(_DWORD *)v26 = 832;
        *((_QWORD *)v26 + 1) = *((_QWORD *)v12 + 27);
        v28 = (void *)*((_QWORD *)v12 + 12);
        *((_QWORD *)v12 + 12) = v26;
        if ( v28 )
          operator delete(v28, v27);
        v29 = (CallbackDataLayout *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x10u);
        if ( v29 )
          v31 = CallbackDataLayout::CallbackDataLayout(v29, v64);
        else
          v31 = 0;
        v32 = (void *)*((_QWORD *)v12 + 14);
        *((_QWORD *)v12 + 14) = v31;
        if ( v32 )
          operator delete(v32, v30);
        if ( *((_QWORD *)v12 + 14) )
        {
          v33 = (ReadingDataLayout *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA8u);
          if ( v33 )
            v35 = ReadingDataLayout::ReadingDataLayout(v33, 0, v19, v64);
          else
            v35 = 0;
          v36 = (void *)*((_QWORD *)v12 + 15);
          *((_QWORD *)v12 + 15) = v35;
          if ( v36 )
            operator delete(v36, v34);
          if ( *((_QWORD *)v12 + 15) )
          {
            v37 = (InputDataLayout *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x30u);
            if ( v37 )
              v39 = InputDataLayout::InputDataLayout(
                      v37,
                      (unsigned int)v38,
                      *((const struct ReadingDataLayout **)v12 + 15),
                      v64);
            else
              v39 = 0;
            v40 = (void *)*((_QWORD *)v12 + 16);
            *((_QWORD *)v12 + 16) = v39;
            if ( v40 )
              operator delete(v40, v38);
            if ( *((_QWORD *)v12 + 16) )
            {
              v41 = (SharedBufferLayout *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x24u);
              if ( v41 )
                v43 = SharedBufferLayout::SharedBufferLayout(
                        v41,
                        *((const struct CallbackDataLayout **)v12 + 14),
                        *((const struct InputDataLayout **)v12 + 16),
                        (const struct GameInputDeviceInfoPrivate *)v26,
                        v64,
                        0);
              else
                v43 = 0;
              v44 = (void *)*((_QWORD *)v12 + 18);
              *((_QWORD *)v12 + 18) = v43;
              if ( v44 )
                operator delete(v44, v42);
              if ( *((_QWORD *)v12 + 18) )
              {
                v45 = (unsigned int *)*((_QWORD *)v12 + 15);
                v46 = *v45;
                *((_DWORD *)v12 + 47) = *v45;
                v47 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v46);
                v49 = (void *)*((_QWORD *)v12 + 19);
                *((_QWORD *)v12 + 19) = v47;
                if ( v49 )
                  operator delete(v49, v48);
                v50 = (void *)*((_QWORD *)v12 + 19);
                if ( v50 )
                {
                  memset_0(v50, 0, *((unsigned int *)v12 + 47));
                  *(_DWORD *)(*((_QWORD *)v12 + 19) + 12LL) = *((_DWORD *)v64 + 26);
                  v51 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *((unsigned int *)v12 + 47));
                  v53 = (void *)*((_QWORD *)v12 + 20);
                  *((_QWORD *)v12 + 20) = v51;
                  if ( v53 )
                    operator delete(v53, v52);
                  if ( *((_QWORD *)v12 + 20) )
                  {
                    v54 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *((unsigned int *)v12 + 47));
                    v56 = (void *)*((_QWORD *)v12 + 21);
                    *((_QWORD *)v12 + 21) = v54;
                    if ( v56 )
                      operator delete(v56, v55);
                    if ( *((_QWORD *)v12 + 21) )
                    {
                      GameInputServerDevice::LogDeviceCreated(v12);
                      *a4 = v12;
                      GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v70);
                      return 0;
                    }
                    AppLocalDeviceId = -2147024882;
                    if ( (unsigned int)dword_180069000 <= 2 )
                      goto LABEL_109;
                    v20 = qword_180069018;
                    if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                      goto LABEL_109;
                    v59 = 627;
                    v21 = byte_18005F6BB;
                  }
                  else
                  {
                    AppLocalDeviceId = -2147024882;
                    if ( (unsigned int)dword_180069000 <= 2 )
                      goto LABEL_109;
                    v20 = qword_180069018;
                    if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                      goto LABEL_109;
                    v59 = 625;
                    v21 = (char *)&unk_18005EAD0;
                  }
                }
                else
                {
                  AppLocalDeviceId = -2147024882;
                  if ( (unsigned int)dword_180069000 <= 2 )
                    goto LABEL_109;
                  v20 = qword_180069018;
                  if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                    goto LABEL_109;
                  v59 = 610;
                  v21 = byte_1800602E1;
                }
              }
              else
              {
                AppLocalDeviceId = -2147024882;
                if ( (unsigned int)dword_180069000 <= 2 )
                  goto LABEL_109;
                v20 = qword_180069018;
                if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                  goto LABEL_109;
                v59 = 605;
                v21 = (char *)&dword_1800620D4;
              }
            }
            else
            {
              AppLocalDeviceId = -2147024882;
              if ( (unsigned int)dword_180069000 <= 2 )
                goto LABEL_109;
              v20 = qword_180069018;
              if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                goto LABEL_109;
              v59 = 602;
              v21 = (char *)&unk_18005FFE0;
            }
          }
          else
          {
            AppLocalDeviceId = -2147024882;
            if ( (unsigned int)dword_180069000 <= 2 )
              goto LABEL_109;
            v20 = qword_180069018;
            if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
              goto LABEL_109;
            v59 = 599;
            v21 = &byte_18005F4E7;
          }
        }
        else
        {
          AppLocalDeviceId = -2147024882;
          if ( (unsigned int)dword_180069000 <= 2 )
            goto LABEL_109;
          v20 = qword_180069018;
          if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
            goto LABEL_109;
          v59 = 596;
          v21 = (char *)&word_180061B6E;
        }
      }
      else
      {
        AppLocalDeviceId = -2147024882;
        if ( (unsigned int)dword_180069000 <= 2 )
          goto LABEL_109;
        v20 = qword_180069018;
        if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
          goto LABEL_109;
        v59 = 587;
        v21 = byte_180061655;
      }
    }
    else
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_109;
      v19 = qword_180069018;
      v20 = qword_180069010;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_109;
      v59 = 583;
      v21 = byte_180060519;
    }
    goto LABEL_108;
  }
  if ( (unsigned int)dword_180069000 <= 2 )
    goto LABEL_109;
  v19 = qword_180069018;
  v20 = qword_180069010;
  if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
    goto LABEL_109;
  v59 = 533;
  v21 = (char *)word_18005F4AA;
LABEL_108:
  v61 = (__int64)"onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
  v60 = AppLocalDeviceId;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    v20,
    (_DWORD)v21,
    v19,
    v18,
    (__int64)&v61,
    (__int64)&v59,
    (__int64)&v60);
LABEL_109:
  GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v70);
LABEL_110:
  GameInputServerDevice::~GameInputServerDevice(v12);
  operator delete(v12, v58);
  return (unsigned int)AppLocalDeviceId;
}

```

## disassembly

```asm
0x180030ee0  mov     [rsp-8+arg_0], rbx
0x180030ee5  push    rbp
0x180030ee6  push    rsi
0x180030ee7  push    rdi
0x180030ee8  push    r12
0x180030eea  push    r13
0x180030eec  push    r14
0x180030eee  push    r15
0x180030ef0  lea     rbp, [rsp-340h]
0x180030ef8  sub     rsp, 440h
0x180030eff  mov     rax, cs:__security_cookie
0x180030f06  xor     rax, rsp
0x180030f09  mov     [rbp+370h+var_38], rax
0x180030f10  mov     r14, r8
0x180030f13  mov     qword ptr [r9], 0
0x180030f1a  mov     rbx, rdx
0x180030f1d  mov     r15, rcx
0x180030f20  mov     rcx, r14; String1
0x180030f23  lea     rdx, aMicrosoftKeybo; "\\\\?\\Microsoft Keyboard RID\\"
0x180030f2a  mov     r8d, 1Bh; MaxCount
0x180030f30  mov     r13, r9
0x180030f33  call    wcsncmp_0
0x180030f38  mov     rcx, gs:60h
0x180030f41  xor     edx, edx; Flags
0x180030f43  mov     r8d, 260h; Size
0x180030f49  mov     r12d, eax
0x180030f4c  mov     rcx, [rcx+30h]; HeapHandle
0x180030f50  call    cs:__imp_RtlAllocateHeap
0x180030f57  nop     dword ptr [rax+rax+00h]
0x180030f5c  test    rax, rax
0x180030f5f  jz      loc_1800318D3
0x180030f65  xor     r9d, r9d; struct Windows::Gaming::Input::IRawGameController *
0x180030f68  mov     r8, rbx; struct IGameInputServerInputRouter *
0x180030f6b  mov     rdx, r15; struct GameInputServer *
0x180030f6e  mov     rcx, rax; this
0x180030f71  call    ??0GameInputServerDevice@@AEAA@PEAVGameInputServer@@PEAUIGameInputServerInputRouter@@PEAUIRawGameController@Input@Gaming@Windows@@@Z; GameInputServerDevice::GameInputServerDevice(GameInputServer *,IGameInputServerInputRouter *,Windows::Gaming::Input::IRawGameController *)
0x180030f76  mov     rbx, rax
0x180030f79  test    rax, rax
0x180030f7c  jz      loc_1800318D3
0x180030f82  lea     r8, [rax+0C0h]
0x180030f89  mov     rcx, r14; Src
0x180030f8c  call    ?CopyStringToBuffer@@YAJPEBG_KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z; CopyStringToBuffer(ushort const *,unsigned __int64,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &)
0x180030f91  mov     edi, eax
0x180030f93  test    eax, eax
0x180030f95  jns     short loc_180031004
0x180030f97  mov     ecx, cs:dword_180069000
0x180030f9d  cmp     ecx, 2
0x180030fa0  jbe     loc_1800318C1
0x180030fa6  mov     r8, cs:qword_180069018
0x180030fad  mov     edx, 400h
0x180030fb2  mov     rcx, cs:qword_180069010
0x180030fb9  test    rdx, rcx
0x180030fbc  jz      loc_1800318C1
0x180030fc2  mov     rax, r8
0x180030fc5  and     rax, rdx
0x180030fc8  cmp     rax, r8
0x180030fcb  jnz     loc_1800318C1
0x180030fd1  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180030fd8  mov     [rsp+470h+var_430], edi
0x180030fdc  mov     [rsp+470h+var_428], rax
0x180030fe1  lea     rdx, word_180060556
0x180030fe8  lea     rax, [rsp+470h+var_430]
0x180030fed  mov     [rsp+470h+var_42C], 204h
0x180030ff5  mov     [rsp+470h+var_440], rax
0x180030ffa  lea     rax, [rsp+470h+var_42C]
0x180030fff  jmp     loc_18003108B
0x180031004  lea     rsi, [rbx+0C8h]
0x18003100b  mov     rcx, r14; Src
0x18003100e  mov     r8, rsi
0x180031011  call    ?CopyStringToBuffer@@YAJPEBG_KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z; CopyStringToBuffer(ushort const *,unsigned __int64,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &)
0x180031016  xor     r14d, r14d
0x180031019  mov     edi, eax
0x18003101b  test    eax, eax
0x18003101d  jns     loc_1800310A4
0x180031023  mov     ecx, cs:dword_180069000
0x180031029  cmp     ecx, 2
0x18003102c  jbe     loc_1800318C1
0x180031032  mov     r8, cs:qword_180069018
0x180031039  mov     edx, 400h
0x18003103e  mov     rcx, cs:qword_180069010
0x180031045  test    rdx, rcx
0x180031048  jz      loc_1800318C1
0x18003104e  mov     rax, r8
0x180031051  and     rax, rdx
0x180031054  cmp     rax, r8
0x180031057  jnz     loc_1800318C1
0x18003105d  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180031064  mov     [rsp+470h+var_42C], edi
0x180031068  mov     [rsp+470h+var_428], rax
0x18003106d  lea     rdx, byte_18005FA9D
0x180031074  lea     rax, [rsp+470h+var_42C]
0x180031079  mov     [rsp+470h+var_430], 205h
0x180031081  mov     [rsp+470h+var_440], rax
0x180031086  lea     rax, [rsp+470h+var_430]
0x18003108b  mov     [rsp+470h+var_448], rax
0x180031090  lea     rax, [rsp+470h+var_428]
0x180031095  mov     [rsp+470h+var_450], rax
0x18003109a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003109f  jmp     loc_1800318C1
0x1800310a4  lea     rcx, [rbp+370h+var_3C8]; this
0x1800310a8  call    ??0GameInputDeviceInfoBuilder@@QEAA@XZ; GameInputDeviceInfoBuilder::GameInputDeviceInfoBuilder(void)
0x1800310ad  mov     [rbp+370h+var_3C4], r14
0x1800310b1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800310b5  mov     rax, [rsi]
0x1800310b8  inc     rcx
0x1800310bb  cmp     [rax+rcx*2], r14w
0x1800310c0  jnz     short loc_1800310B8
0x1800310c2  xorps   xmm0, xmm0
0x1800310c5  lea     r8, [rbp+370h+pbOutput]; pbOutput
0x1800310c9  movups  xmmword ptr [rbp+370h+pbOutput], xmm0
0x1800310cd  add     rcx, rcx; cbInput
0x1800310d0  movups  [rbp+370h+var_3D8], xmm0
0x1800310d4  mov     rdx, [rsi]; pbInput
0x1800310d7  call    ?GenerateAppLocalDeviceId@GameInputServerDevice@@CAJ_KPEBXAEAUAPP_LOCAL_DEVICE_ID@@@Z; GameInputServerDevice::GenerateAppLocalDeviceId(unsigned __int64,void const *,APP_LOCAL_DEVICE_ID &)
0x1800310dc  mov     edi, eax
0x1800310de  test    eax, eax
0x1800310e0  jns     short loc_180031130
0x1800310e2  mov     ecx, cs:dword_180069000
0x1800310e8  cmp     ecx, 2
0x1800310eb  jbe     loc_1800318B8
0x1800310f1  mov     r8, cs:qword_180069018
0x1800310f8  mov     edx, 400h
0x1800310fd  mov     rcx, cs:qword_180069010
0x180031104  test    rdx, rcx
0x180031107  jz      loc_1800318B8
0x18003110d  mov     rax, r8
0x180031110  and     rax, rdx
0x180031113  cmp     rax, r8
0x180031116  jnz     loc_1800318B8
0x18003111c  mov     [rsp+470h+var_430], 215h
0x180031124  lea     rdx, word_18005F4AA
0x18003112b  jmp     loc_180031885
0x180031130  movups  xmm1, xmmword ptr [rbp+370h+pbOutput]
0x180031134  mov     eax, r12d
0x180031137  mov     edx, 1
0x18003113c  movups  xmm0, [rbp+370h+var_3D8]
0x180031140  neg     eax
0x180031142  mov     [rbp+370h+var_3BC], dx
0x180031146  movups  [rbp+370h+var_3A8], xmm1
0x18003114a  sbb     cx, cx
0x18003114d  mov     [rbp+370h+var_368], 0FFFFFFFFh
0x180031154  and     cx, 0FFFCh
0x180031159  mov     [rbp+370h+var_364], r14d
0x18003115d  add     cx, 6
0x180031161  mov     [rbp+370h+var_3BA], cx
0x180031165  movups  [rbp+370h+var_398], xmm0
0x180031169  movups  [rbp+370h+var_388], xmm1
0x18003116d  movups  [rbp+370h+var_378], xmm0
0x180031171  test    r12d, r12d
0x180031174  jnz     loc_180031221
0x18003117a  mov     rcx, [r15+0E0h]; HKL
0x180031181  mov     [rsp+470h+var_3F8], r14
0x180031186  mov     [rsp+470h+var_410], 0FFFFFFFFh
0x18003118e  call    ?KlidFromHkl@KeyboardLookupTable@@SAIPEAUHKL__@@@Z; KeyboardLookupTable::KlidFromHkl(HKL__ *)
0x180031193  lea     rdx, [rsp+470h+var_410]; struct GameInputKeyboardInfo *
0x180031198  mov     [rsp+470h+var_40C], eax
0x18003119c  lea     rcx, [rbp+370h+var_3C8]; this
0x1800311a0  mov     [rsp+470h+var_408], 68h ; 'h'
0x1800311a8  mov     [rsp+470h+var_404], 0Ch
0x1800311b0  mov     [rsp+470h+var_400], 10h
0x1800311b8  mov     [rsp+470h+var_3FC], 4
0x1800311c0  mov     [rbp+370h+var_3F0], r14
0x1800311c4  call    ?AddKeyboardInfo@GameInputDeviceInfoBuilder@@QEAAJPEBUGameInputKeyboardInfo@@@Z; GameInputDeviceInfoBuilder::AddKeyboardInfo(GameInputKeyboardInfo const *)
0x1800311c9  mov     edi, eax
0x1800311cb  test    eax, eax
0x1800311cd  jns     loc_180031299
0x1800311d3  mov     ecx, cs:dword_180069000
0x1800311d9  cmp     ecx, 2
0x1800311dc  jbe     loc_1800318B8
0x1800311e2  mov     r8, cs:qword_180069018
0x1800311e9  mov     edx, 400h
0x1800311ee  mov     rcx, cs:qword_180069010
0x1800311f5  test    rdx, rcx
0x1800311f8  jz      loc_1800318B8
0x1800311fe  mov     rax, r8
0x180031201  and     rax, rdx
0x180031204  cmp     rax, r8
0x180031207  jnz     loc_1800318B8
0x18003120d  mov     [rsp+470h+var_430], 235h
0x180031215  lea     rdx, byte_1800627A1
0x18003121c  jmp     loc_180031885
0x180031221  lea     rdx, [rsp+470h+var_428]; struct GameInputMouseInfo *
0x180031226  mov     [rsp+470h+var_41C], 100h
0x18003122e  lea     rcx, [rbp+370h+var_3C8]; this
0x180031232  mov     [rsp+470h+var_428], 7
0x18003123b  mov     [rsp+470h+var_420], r14d
0x180031240  call    ?AddMouseInfo@GameInputDeviceInfoBuilder@@QEAAJPEBUGameInputMouseInfo@@@Z; GameInputDeviceInfoBuilder::AddMouseInfo(GameInputMouseInfo const *)
0x180031245  mov     edi, eax
0x180031247  test    eax, eax
0x180031249  jns     short loc_180031299
0x18003124b  mov     ecx, cs:dword_180069000
0x180031251  cmp     ecx, 2
0x180031254  jbe     loc_1800318B8
0x18003125a  mov     r8, cs:qword_180069018
0x180031261  mov     edx, 400h
0x180031266  mov     rcx, cs:qword_180069010
0x18003126d  test    rdx, rcx
0x180031270  jz      loc_1800318B8
0x180031276  mov     rax, r8
0x180031279  and     rax, rdx
0x18003127c  cmp     rax, r8
0x18003127f  jnz     loc_1800318B8
0x180031285  mov     [rsp+470h+var_430], 242h
0x18003128d  lea     rdx, byte_1800607E1
0x180031294  jmp     loc_180031885
0x180031299  lea     rdx, [rsp+470h+var_418]; struct GameInputDeviceInfo **
0x18003129e  mov     [rsp+470h+var_418], r14
0x1800312a3  lea     rcx, [rbp+370h+var_3C8]; this
0x1800312a7  call    ?Make@GameInputDeviceInfoBuilder@@QEAAJPEAPEAUGameInputDeviceInfo@@@Z; GameInputDeviceInfoBuilder::Make(GameInputDeviceInfo * *)
0x1800312ac  mov     edi, eax
0x1800312ae  test    eax, eax
0x1800312b0  jns     short loc_180031300
0x1800312b2  mov     ecx, cs:dword_180069000
0x1800312b8  cmp     ecx, 2
0x1800312bb  jbe     loc_1800318B8
0x1800312c1  mov     r8, cs:qword_180069018
0x1800312c8  mov     edx, 400h
0x1800312cd  mov     rcx, cs:qword_180069010
0x1800312d4  test    rdx, rcx
0x1800312d7  jz      loc_1800318B8
0x1800312dd  mov     rax, r8
0x1800312e0  and     rax, rdx
0x1800312e3  cmp     rax, r8
0x1800312e6  jnz     loc_1800318B8
0x1800312ec  mov     [rsp+470h+var_430], 247h
0x1800312f4  lea     rdx, byte_180060519
0x1800312fb  jmp     loc_180031885
0x180031300  mov     rcx, [rbx+58h]; P
0x180031304  mov     rax, [rsp+470h+var_418]
0x180031309  mov     [rbx+58h], rax
0x18003130d  test    rcx, rcx
0x180031310  jz      short loc_180031317
0x180031312  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031317  mov     rcx, gs:60h
0x180031320  mov     r15d, 340h
0x180031326  mov     r8d, r15d; Size
0x180031329  xor     edx, edx; Flags
0x18003132b  mov     rcx, [rcx+30h]; HeapHandle
0x18003132f  call    cs:__imp_RtlAllocateHeap
0x180031336  nop     dword ptr [rax+rax+00h]
0x18003133b  mov     rdi, rax
0x18003133e  test    rax, rax
0x180031341  jz      loc_180031843
0x180031347  lea     esi, [r15-4]
0x18003134b  xor     edx, edx; Val
0x18003134d  mov     r8d, esi; Size
0x180031350  lea     rcx, [rax+4]; void *
0x180031354  call    memset_0
0x180031359  lea     rcx, [rdi+4]; void *
0x18003135d  mov     r8d, esi; Size
0x180031360  xor     edx, edx; Val
0x180031362  call    memset_0
0x180031367  mov     [rdi], r15d
0x18003136a  mov     rcx, [rbx+0D8h]
0x180031371  mov     [rdi+8], rcx
0x180031375  mov     rcx, [rbx+60h]; P
0x180031379  mov     [rbx+60h], rdi
0x18003137d  test    rcx, rcx
0x180031380  jz      short loc_180031387
0x180031382  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031387  mov     rcx, gs:60h
0x180031390  xor     edx, edx; Flags
0x180031392  mov     rcx, [rcx+30h]; HeapHandle
0x180031396  lea     r8d, [rdx+10h]; Size
0x18003139a  call    cs:__imp_RtlAllocateHeap
0x1800313a1  nop     dword ptr [rax+rax+00h]
0x1800313a6  test    rax, rax
0x1800313a9  jz      short loc_1800313BA
0x1800313ab  mov     rdx, [rsp+470h+var_418]; struct GameInputDeviceInfo *
0x1800313b0  mov     rcx, rax; this
0x1800313b3  call    ??0CallbackDataLayout@@QEAA@PEBUGameInputDeviceInfo@@@Z; CallbackDataLayout::CallbackDataLayout(GameInputDeviceInfo const *)
0x1800313b8  jmp     short loc_1800313BD
0x1800313ba  mov     rax, r14
0x1800313bd  mov     rcx, [rbx+70h]; P
0x1800313c1  mov     [rbx+70h], rax
0x1800313c5  test    rcx, rcx
0x1800313c8  jz      short loc_1800313CF
0x1800313ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800313cf  cmp     [rbx+70h], r14
0x1800313d3  jnz     short loc_180031428
0x1800313d5  mov     eax, cs:dword_180069000
0x1800313db  mov     edi, 8007000Eh
0x1800313e0  cmp     eax, 2
0x1800313e3  jbe     loc_1800318B8
0x1800313e9  mov     rcx, cs:qword_180069018
0x1800313f0  mov     edx, 400h
0x1800313f5  mov     rax, cs:qword_180069010
0x1800313fc  test    rdx, rax
0x1800313ff  jz      loc_1800318B8
0x180031405  mov     rax, rcx
0x180031408  and     rax, rdx
0x18003140b  cmp     rax, rcx
0x18003140e  jnz     loc_1800318B8
0x180031414  mov     [rsp+470h+var_430], 254h
0x18003141c  lea     rdx, word_180061B6E
0x180031423  jmp     loc_180031885
0x180031428  mov     rcx, gs:60h
0x180031431  xor     edx, edx; Flags
0x180031433  mov     r8d, 0A8h; Size
0x180031439  mov     rcx, [rcx+30h]; HeapHandle
  ... truncated ...
```
