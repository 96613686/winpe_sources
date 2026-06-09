# GameInputServerDevice::CreateForPnpDevice(GameInputServer *,IGameInputServerInputRouter *,ushort const *,GameInputServerDevice * *)

- ea: `0x180030308`
- end: `0x180030eda`
- name: `?CreateForPnpDevice@GameInputServerDevice@@SAJPEAVGameInputServer@@PEAUIGameInputServerInputRouter@@PEBGPEAPEAV1@@Z`
- size: `3026`
- prototype: `__int64 __fastcall(struct GameInputServer *, struct IGameInputServerInputRouter *, unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *), struct GameInputServerDevice **)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18003ee94`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x1800230d8`
- `0x1800231fc`
- `0x1800232b4`
- `0x180023558`
- `0x18002ce50`
- `0x18002d1c8`
- `0x18002d610`
- `0x18002da74`
- `0x18002e838`
- `0x18002e9a4`
- `0x180030308`
- `0x180030ee0`
- `0x18003b5b4`
- `0x18003ca44`
- `0x18003cccc`
- `0x180041ff0`
- `0x180042310`
- `0x180047dd0`
- `0x180048380`
- `0x1800485a8`
- `0x1800486e0`
- `0x1800487e0`
- `0x18004c881`
- `0x18004c8a5`
- `0x18004c8bd`
- `0x18004c8e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800303e6`
- `ntdll!RtlAllocateHeap` at `0x180030885`
- `ntdll!RtlAllocateHeap` at `0x1800308f0`
- `ntdll!RtlAllocateHeap` at `0x180030992`
- `ntdll!RtlAllocateHeap` at `0x180030a34`
- `ntdll!RtlAllocateHeap` at `0x180030ae1`
- `ntdll!RtlAllocateHeap` at `0x180030bad`
- `ntdll!RtlAllocateHeap` at `0x180030c65`
- `ntdll!RtlAllocateHeap` at `0x180030cfa`
- `ntdll!RtlAllocateHeap` at `0x1800303e6`
- `ntdll!RtlAllocateHeap` at `0x180030885`
- `ntdll!RtlAllocateHeap` at `0x1800308f0`
- `ntdll!RtlAllocateHeap` at `0x180030992`
- `ntdll!RtlAllocateHeap` at `0x180030a34`
- `ntdll!RtlAllocateHeap` at `0x180030ae1`
- `ntdll!RtlAllocateHeap` at `0x180030bad`
- `ntdll!RtlAllocateHeap` at `0x180030c65`
- `ntdll!RtlAllocateHeap` at `0x180030cfa`

## pseudocode

```c
__int64 __fastcall GameInputServerDevice::CreateForPnpDevice(
        struct GameInputServer *a1,
        struct IGameInputServerInputRouter *a2,
        unsigned int (*a3)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *),
        struct GameInputServerDevice **a4)
{
  PnpApiWrapper::Details *v8; // rcx
  void *v9; // r8
  GameInputServerDevice *Heap; // rax
  int v11; // r8d
  int v12; // r9d
  GameInputServerDevice *v13; // rdi
  int DeviceInstanceId; // ebx
  int v15; // r9d
  DEVINSTID_W *v16; // r14
  unsigned int *v17; // r8
  int v18; // r9d
  int v19; // r8d
  int v20; // ecx
  int *v21; // rdx
  __int64 v22; // rcx
  int v23; // r9d
  int v24; // r8d
  int v25; // ecx
  char *v26; // rdx
  __int16 v27; // cx
  const struct std::nothrow_t *v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  void *v30; // rcx
  char *v31; // rax
  char *v32; // rbx
  const struct std::nothrow_t *v33; // rdx
  void *v34; // rcx
  CallbackDataLayout *v35; // rax
  const struct std::nothrow_t *v36; // rdx
  CallbackDataLayout *v37; // rax
  void *v38; // rcx
  ReadingDataLayout *v39; // rax
  const struct std::nothrow_t *v40; // rdx
  ReadingDataLayout *v41; // rax
  void *v42; // rcx
  InputDataLayout *v43; // rax
  const struct std::nothrow_t *v44; // rdx
  InputDataLayout *v45; // rax
  void *v46; // rcx
  SharedBufferLayout *v47; // rax
  const struct std::nothrow_t *v48; // rdx
  SharedBufferLayout *v49; // rax
  void *v50; // rcx
  unsigned int *v51; // rax
  unsigned int v52; // ecx
  PVOID v53; // rax
  const struct std::nothrow_t *v54; // rdx
  void *v55; // rcx
  void *v56; // rcx
  PVOID v57; // rax
  const struct std::nothrow_t *v58; // rdx
  void *v59; // rcx
  PVOID v60; // rax
  const struct std::nothrow_t *v61; // rdx
  void *v62; // rcx
  const struct std::nothrow_t *v64; // rdx
  struct GameInputDeviceInfo *v65; // [rsp+20h] [rbp-E0h]
  int v66; // [rsp+40h] [rbp-C0h] BYREF
  PVOID P; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v68; // [rsp+50h] [rbp-B0h] BYREF
  struct GameInputDeviceInfo *v69; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v70[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v71; // [rsp+88h] [rbp-78h]
  __int128 Buf1; // [rsp+90h] [rbp-70h] BYREF
  UCHAR pbOutput[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v74; // [rsp+B0h] [rbp-50h]
  _BYTE v75[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v76; // [rsp+C4h] [rbp-3Ch]
  __int16 v77; // [rsp+CCh] [rbp-34h]
  __int16 v78; // [rsp+CEh] [rbp-32h]
  __int128 v79; // [rsp+E0h] [rbp-20h]
  __int128 v80; // [rsp+F0h] [rbp-10h]
  __int128 v81; // [rsp+100h] [rbp+0h]
  __int128 v82; // [rsp+110h] [rbp+10h]
  __int64 v83; // [rsp+120h] [rbp+20h]

  if ( !wcsncmp_0((const wchar_t *)a3, L"\\\\?\\Microsoft Keyboard RID\\", 0x1Bu)
    || !wcsncmp_0((const wchar_t *)a3, L"\\\\?\\Microsoft Mouse RID\\", 0x18u) )
  {
    return GameInputServerDevice::CreateForRimDevice(a1, a2, (const unsigned __int16 *)a3, a4);
  }
  *a4 = 0;
  Buf1 = 0;
  if ( PnpApiWrapper::Details::GetDeviceGuidProperty(v8, a3, v9, (const struct _DEVPROPKEY *)&Buf1, (struct _GUID *)v65) >= 0
    && (!memcmp_0(&Buf1, &GameInputServerDevice::c_keyboardInterfaceGuid, 0x10u)
     || !memcmp_0(&Buf1, &GameInputServerDevice::c_mouseInterfaceGuid, 0x10u)) )
  {
    Heap = (GameInputServerDevice *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x260u);
    if ( !Heap || (v13 = GameInputServerDevice::GameInputServerDevice(Heap, a1, a2, 0)) == 0 )
    {
      DeviceInstanceId = -2147024882;
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v66 = -2147024882;
        *(_QWORD *)&v68 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
        LODWORD(P) = 378;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)word_18006064A,
          v11,
          v12,
          (__int64)&v68,
          (__int64)&P,
          (__int64)&v66);
      }
      return (unsigned int)DeviceInstanceId;
    }
    DeviceInstanceId = CopyStringToBuffer(a3);
    if ( DeviceInstanceId < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        LODWORD(P) = DeviceInstanceId;
        *(_QWORD *)&v68 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
        v66 = 381;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)&byte_18006049F,
          qword_180069018,
          v15,
          (__int64)&v68,
          (__int64)&v66,
          (__int64)&P);
      }
      goto LABEL_127;
    }
    v16 = (DEVINSTID_W *)((char *)v13 + 200);
    DeviceInstanceId = PnpApiWrapper::GetDeviceInstanceId(a3, (char *)v13 + 200);
    if ( DeviceInstanceId < 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_127;
      v19 = qword_180069018;
      v20 = qword_180069010;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_127;
      LODWORD(P) = 382;
      v21 = &dword_18005F574;
      goto LABEL_18;
    }
    DeviceInstanceId = PnpApiWrapper::GetDeviceNode(*v16, (PDEVINST)v13 + 52, v17);
    if ( DeviceInstanceId < 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_127;
      v19 = qword_180069018;
      v20 = qword_180069010;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_127;
      LODWORD(P) = 383;
      v21 = (int *)&byte_18005EBD7;
LABEL_18:
      *(_QWORD *)&v68 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
      v66 = DeviceInstanceId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v20,
        (_DWORD)v21,
        v19,
        v18,
        (__int64)&v68,
        (__int64)&P,
        (__int64)&v66);
      goto LABEL_127;
    }
    GameInputDeviceInfoBuilder::GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v75);
    v76 = 0;
    v22 = -1;
    do
      ++v22;
    while ( (*v16)[v22] );
    *(_OWORD *)pbOutput = 0;
    v74 = 0;
    DeviceInstanceId = GameInputServerDevice::GenerateAppLocalDeviceId(2 * (int)v22, (PUCHAR)*v16, pbOutput);
    if ( DeviceInstanceId >= 0 )
    {
      v79 = *(_OWORD *)pbOutput;
      v80 = v74;
      v81 = *(_OWORD *)pbOutput;
      v82 = v74;
      if ( !memcmp_0(&Buf1, &GameInputServerDevice::c_keyboardInterfaceGuid, 0x10u) )
        v27 = 6;
      else
        v27 = 2;
      v78 = v27;
      v77 = 1;
      v83 = 3;
      v66 = *((_DWORD *)v13 + 52);
      P = 0;
      PnpApiWrapper::Details::GetDeviceStringProperty(
        PnpApiWrapper::Adapters::GetDeviceNodeProperty,
        &v66,
        &DEVPKEY_NAME,
        &P);
      if ( P )
        operator delete(P, v28);
      if ( !memcmp_0(&Buf1, &GameInputServerDevice::c_keyboardInterfaceGuid, 0x10u)
        && (memset(v70, 0, sizeof(v70)),
            v71 = 0,
            GameInputServerDevice::TryReadKeyboardInfo(v13, (struct GameInputKeyboardInfo *)v70),
            DeviceInstanceId = GameInputDeviceInfoBuilder::AddKeyboardInfo(
                                 (GameInputDeviceInfoBuilder *)v75,
                                 (const struct GameInputKeyboardInfo *)v70),
            DeviceInstanceId < 0) )
      {
        if ( (unsigned int)dword_180069000 <= 2 )
          goto LABEL_126;
        v24 = qword_180069018;
        v25 = qword_180069010;
        if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
          goto LABEL_126;
        LODWORD(P) = 435;
        v26 = (char *)&word_18005F996;
      }
      else if ( !memcmp_0(&Buf1, &GameInputServerDevice::c_mouseInterfaceGuid, 0x10u)
             && (v68 = 0,
                 GameInputServerDevice::TryReadMouseInfo((LPCWSTR *)v13, (struct GameInputMouseInfo *)&v68),
                 DeviceInstanceId = GameInputDeviceInfoBuilder::AddMouseInfo(
                                      (GameInputDeviceInfoBuilder *)v75,
                                      (const struct GameInputMouseInfo *)&v68),
                 DeviceInstanceId < 0) )
      {
        if ( (unsigned int)dword_180069000 <= 2 )
          goto LABEL_126;
        v24 = qword_180069018;
        v25 = qword_180069010;
        if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
          goto LABEL_126;
        LODWORD(P) = 443;
        v26 = (char *)&word_18005ED5E;
      }
      else
      {
        v69 = 0;
        DeviceInstanceId = GameInputDeviceInfoBuilder::Make((GameInputDeviceInfoBuilder *)v75, &v69);
        if ( DeviceInstanceId >= 0 )
        {
          v30 = (void *)*((_QWORD *)v13 + 11);
          *((_QWORD *)v13 + 11) = v69;
          if ( v30 )
            operator delete(v30, v29);
          v31 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x340u);
          v32 = v31;
          if ( v31 )
          {
            memset_0(v31 + 4, 0, 0x33Cu);
            memset_0(v32 + 4, 0, 0x33Cu);
            *(_DWORD *)v32 = 832;
            *((_QWORD *)v32 + 1) = *((_QWORD *)v13 + 27);
            v34 = (void *)*((_QWORD *)v13 + 12);
            *((_QWORD *)v13 + 12) = v32;
            if ( v34 )
              operator delete(v34, v33);
            v35 = (CallbackDataLayout *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x10u);
            if ( v35 )
              v37 = CallbackDataLayout::CallbackDataLayout(v35, v69);
            else
              v37 = 0;
            v38 = (void *)*((_QWORD *)v13 + 14);
            *((_QWORD *)v13 + 14) = v37;
            if ( v38 )
              operator delete(v38, v36);
            if ( *((_QWORD *)v13 + 14) )
            {
              v39 = (ReadingDataLayout *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA8u);
              if ( v39 )
                v41 = ReadingDataLayout::ReadingDataLayout(v39, 0, v24, v69);
              else
                v41 = 0;
              v42 = (void *)*((_QWORD *)v13 + 15);
              *((_QWORD *)v13 + 15) = v41;
              if ( v42 )
                operator delete(v42, v40);
              if ( *((_QWORD *)v13 + 15) )
              {
                v43 = (InputDataLayout *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x30u);
                if ( v43 )
                  v45 = InputDataLayout::InputDataLayout(
                          v43,
                          (unsigned int)v44,
                          *((const struct ReadingDataLayout **)v13 + 15),
                          v69);
                else
                  v45 = 0;
                v46 = (void *)*((_QWORD *)v13 + 16);
                *((_QWORD *)v13 + 16) = v45;
                if ( v46 )
                  operator delete(v46, v44);
                if ( *((_QWORD *)v13 + 16) )
                {
                  v47 = (SharedBufferLayout *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x24u);
                  if ( v47 )
                    v49 = SharedBufferLayout::SharedBufferLayout(
                            v47,
                            *((const struct CallbackDataLayout **)v13 + 14),
                            *((const struct InputDataLayout **)v13 + 16),
                            (const struct GameInputDeviceInfoPrivate *)v32,
                            v69,
                            0);
                  else
                    v49 = 0;
                  v50 = (void *)*((_QWORD *)v13 + 18);
                  *((_QWORD *)v13 + 18) = v49;
                  if ( v50 )
                    operator delete(v50, v48);
                  if ( *((_QWORD *)v13 + 18) )
                  {
                    v51 = (unsigned int *)*((_QWORD *)v13 + 15);
                    v52 = *v51;
                    *((_DWORD *)v13 + 47) = *v51;
                    v53 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v52);
                    v55 = (void *)*((_QWORD *)v13 + 19);
                    *((_QWORD *)v13 + 19) = v53;
                    if ( v55 )
                      operator delete(v55, v54);
                    v56 = (void *)*((_QWORD *)v13 + 19);
                    if ( v56 )
                    {
                      memset_0(v56, 0, *((unsigned int *)v13 + 47));
                      *(_DWORD *)(*((_QWORD *)v13 + 19) + 12LL) = *((_DWORD *)v69 + 26);
                      v57 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *((unsigned int *)v13 + 47));
                      v59 = (void *)*((_QWORD *)v13 + 20);
                      *((_QWORD *)v13 + 20) = v57;
                      if ( v59 )
                        operator delete(v59, v58);
                      if ( *((_QWORD *)v13 + 20) )
                      {
                        v60 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *((unsigned int *)v13 + 47));
                        v62 = (void *)*((_QWORD *)v13 + 21);
                        *((_QWORD *)v13 + 21) = v60;
                        if ( v62 )
                          operator delete(v62, v61);
                        if ( *((_QWORD *)v13 + 21) )
                        {
                          GameInputServerDevice::LogDeviceCreated(v13);
                          *a4 = v13;
                          GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v75);
                          return 0;
                        }
                        DeviceInstanceId = -2147024882;
                        if ( (unsigned int)dword_180069000 <= 2 )
                          goto LABEL_126;
                        v25 = qword_180069018;
                        if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                          goto LABEL_126;
                        LODWORD(P) = 492;
                        v26 = byte_18005ED9B;
                      }
                      else
                      {
                        DeviceInstanceId = -2147024882;
                        if ( (unsigned int)dword_180069000 <= 2 )
                          goto LABEL_126;
                        v25 = qword_180069018;
                        if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                          goto LABEL_126;
                        LODWORD(P) = 490;
                        v26 = (char *)&unk_180060D08;
                      }
                    }
                    else
                    {
                      DeviceInstanceId = -2147024882;
                      if ( (unsigned int)dword_180069000 <= 2 )
                        goto LABEL_126;
                      v25 = qword_180069018;
                      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                        goto LABEL_126;
                      LODWORD(P) = 475;
                      v26 = &byte_180061407;
                    }
                  }
                  else
                  {
                    DeviceInstanceId = -2147024882;
                    if ( (unsigned int)dword_180069000 <= 2 )
                      goto LABEL_126;
                    v25 = qword_180069018;
                    if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                      goto LABEL_126;
                    LODWORD(P) = 470;
                    v26 = byte_18005F66B;
                  }
                }
                else
                {
                  DeviceInstanceId = -2147024882;
                  if ( (unsigned int)dword_180069000 <= 2 )
                    goto LABEL_126;
                  v25 = qword_180069018;
                  if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                    goto LABEL_126;
                  LODWORD(P) = 467;
                  v26 = byte_180060E35;
                }
              }
              else
              {
                DeviceInstanceId = -2147024882;
                if ( (unsigned int)dword_180069000 <= 2 )
                  goto LABEL_126;
                v25 = qword_180069018;
                if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                  goto LABEL_126;
                LODWORD(P) = 464;
                v26 = byte_180060F79;
              }
            }
            else
            {
              DeviceInstanceId = -2147024882;
              if ( (unsigned int)dword_180069000 <= 2 )
                goto LABEL_126;
              v25 = qword_180069018;
              if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
                goto LABEL_126;
              LODWORD(P) = 461;
              v26 = byte_18006133D;
            }
          }
          else
          {
            DeviceInstanceId = -2147024882;
            if ( (unsigned int)dword_180069000 <= 2 )
              goto LABEL_126;
            v25 = qword_180069018;
            if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
              goto LABEL_126;
            LODWORD(P) = 452;
            v26 = (char *)&word_180060A06;
          }
        }
        else
        {
          if ( (unsigned int)dword_180069000 <= 2 )
            goto LABEL_126;
          v24 = qword_180069018;
          v25 = qword_180069010;
          if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
            goto LABEL_126;
          LODWORD(P) = 448;
          v26 = (char *)&unk_180061F90;
        }
      }
    }
    else
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_126;
      v24 = qword_180069018;
      v25 = qword_180069010;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_126;
      LODWORD(P) = 403;
      v26 = byte_1800616A5;
    }
    *(_QWORD *)&v68 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
    v66 = DeviceInstanceId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v25,
      (_DWORD)v26,
      v24,
      v23,
      (__int64)&v68,
      (__int64)&P,
      (__int64)&v66);
LABEL_126:
    GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v75);
LABEL_127:
    GameInputServerDevice::~GameInputServerDevice(v13);
    operator delete(v13, v64);
    return (unsigned int)DeviceInstanceId;
  }
  return 1;
}

```

## disassembly

```asm
0x180030308  push    rbp
0x18003030a  push    rbx
0x18003030b  push    rsi
0x18003030c  push    rdi
0x18003030d  push    r12
0x18003030f  push    r13
0x180030311  push    r14
0x180030313  push    r15
0x180030315  lea     rbp, [rsp-368h]
0x18003031d  sub     rsp, 468h
0x180030324  mov     rax, cs:__security_cookie
0x18003032b  xor     rax, rsp
0x18003032e  mov     [rbp+3A0h+var_50], rax
0x180030335  mov     rsi, r8
0x180030338  mov     rdi, rdx
0x18003033b  mov     rbx, rcx
0x18003033e  lea     rdx, aMicrosoftKeybo; "\\\\?\\Microsoft Keyboard RID\\"
0x180030345  mov     rcx, rsi; String1
0x180030348  mov     r8d, 1Bh; MaxCount
0x18003034e  mov     r12, r9
0x180030351  call    wcsncmp_0
0x180030356  xor     r13d, r13d
0x180030359  test    eax, eax
0x18003035b  jz      loc_180030EA5
0x180030361  lea     r8d, [r13+18h]; MaxCount
0x180030365  mov     rcx, rsi; String1
0x180030368  lea     rdx, aMicrosoftMouse; "\\\\?\\Microsoft Mouse RID\\"
0x18003036f  call    wcsncmp_0
0x180030374  test    eax, eax
0x180030376  jz      loc_180030EA5
0x18003037c  xorps   xmm0, xmm0
0x18003037f  mov     [r12], r13
0x180030383  lea     r9, [rbp+3A0h+Buf1]; struct _DEVPROPKEY *
0x180030387  mov     rdx, rsi; unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *)
0x18003038a  movups  [rbp+3A0h+Buf1], xmm0
0x18003038e  call    ?GetDeviceGuidProperty@Details@PnpApiWrapper@@YAJP6AKPEAXPEBU_DEVPROPKEY@@AEAI0PEAK@Z01AEAU_GUID@@@Z; PnpApiWrapper::Details::GetDeviceGuidProperty(ulong (*)(void *,_DEVPROPKEY const *,uint &,void *,ulong *),void *,_DEVPROPKEY const *,_GUID &)
0x180030393  test    eax, eax
0x180030395  js      loc_180030E9E
0x18003039b  lea     r14d, [r13+10h]
0x18003039f  mov     r8d, r14d; Size
0x1800303a2  lea     rdx, ?c_keyboardInterfaceGuid@GameInputServerDevice@@0U_GUID@@B; Buf2
0x1800303a9  lea     rcx, [rbp+3A0h+Buf1]; Buf1
0x1800303ad  call    memcmp_0
0x1800303b2  test    eax, eax
0x1800303b4  jz      short loc_1800303D1
0x1800303b6  mov     r8d, r14d; Size
0x1800303b9  lea     rdx, ?c_mouseInterfaceGuid@GameInputServerDevice@@0U_GUID@@B; Buf2
0x1800303c0  lea     rcx, [rbp+3A0h+Buf1]; Buf1
0x1800303c4  call    memcmp_0
0x1800303c9  test    eax, eax
0x1800303cb  jnz     loc_180030E9E
0x1800303d1  mov     rcx, gs:60h
0x1800303da  xor     edx, edx; Flags
0x1800303dc  mov     r8d, 260h; Size
0x1800303e2  mov     rcx, [rcx+30h]; HeapHandle
0x1800303e6  call    cs:__imp_RtlAllocateHeap
0x1800303ed  nop     dword ptr [rax+rax+00h]
0x1800303f2  test    rax, rax
0x1800303f5  jz      loc_180030E21
0x1800303fb  xor     r9d, r9d; struct Windows::Gaming::Input::IRawGameController *
0x1800303fe  mov     r8, rdi; struct IGameInputServerInputRouter *
0x180030401  mov     rdx, rbx; struct GameInputServer *
0x180030404  mov     rcx, rax; this
0x180030407  call    ??0GameInputServerDevice@@AEAA@PEAVGameInputServer@@PEAUIGameInputServerInputRouter@@PEAUIRawGameController@Input@Gaming@Windows@@@Z; GameInputServerDevice::GameInputServerDevice(GameInputServer *,IGameInputServerInputRouter *,Windows::Gaming::Input::IRawGameController *)
0x18003040c  mov     rdi, rax
0x18003040f  test    rax, rax
0x180030412  jz      loc_180030E21
0x180030418  lea     r8, [rax+0C0h]
0x18003041f  mov     rcx, rsi; Src
0x180030422  call    ?CopyStringToBuffer@@YAJPEBG_KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z; CopyStringToBuffer(ushort const *,unsigned __int64,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &)
0x180030427  mov     ebx, eax
0x180030429  test    eax, eax
0x18003042b  jns     short loc_18003049E
0x18003042d  mov     ecx, cs:dword_180069000
0x180030433  mov     esi, 2
0x180030438  cmp     ecx, esi
0x18003043a  jbe     loc_180030E0F
0x180030440  mov     r8, cs:qword_180069018
0x180030447  mov     edx, 400h
0x18003044c  mov     rcx, cs:qword_180069010
0x180030453  test    rdx, rcx
0x180030456  jz      loc_180030E0F
0x18003045c  mov     rax, r8
0x18003045f  and     rax, rdx
0x180030462  cmp     rax, r8
0x180030465  jnz     loc_180030E0F
0x18003046b  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180030472  mov     dword ptr [rsp+4A0h+P], ebx
0x180030476  mov     qword ptr [rsp+4A0h+var_450], rax
0x18003047b  lea     rdx, byte_18006049F
0x180030482  lea     rax, [rsp+4A0h+P]
0x180030487  mov     [rsp+4A0h+var_460], 17Dh
0x18003048f  mov     [rsp+4A0h+var_470], rax
0x180030494  lea     rax, [rsp+4A0h+var_460]
0x180030499  jmp     loc_180030526
0x18003049e  lea     r14, [rdi+0C8h]
0x1800304a5  mov     rcx, rsi
0x1800304a8  mov     rdx, r14
0x1800304ab  call    ?GetDeviceInstanceId@PnpApiWrapper@@YAJPEBGAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z; PnpApiWrapper::GetDeviceInstanceId(ushort const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &)
0x1800304b0  mov     ebx, eax
0x1800304b2  test    eax, eax
0x1800304b4  jns     loc_18003053F
0x1800304ba  mov     ecx, cs:dword_180069000
0x1800304c0  mov     esi, 2
0x1800304c5  cmp     ecx, esi
0x1800304c7  jbe     loc_180030E0F
0x1800304cd  mov     r8, cs:qword_180069018
0x1800304d4  mov     edx, 400h
0x1800304d9  mov     rcx, cs:qword_180069010
0x1800304e0  test    rdx, rcx
0x1800304e3  jz      loc_180030E0F
0x1800304e9  mov     rax, r8
0x1800304ec  and     rax, rdx
0x1800304ef  cmp     rax, r8
0x1800304f2  jnz     loc_180030E0F
0x1800304f8  mov     dword ptr [rsp+4A0h+P], 17Eh
0x180030500  lea     rdx, dword_18005F574
0x180030507  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x18003050e  mov     qword ptr [rsp+4A0h+var_450], rax
0x180030513  lea     rax, [rsp+4A0h+var_460]
0x180030518  mov     [rsp+4A0h+var_470], rax
0x18003051d  lea     rax, [rsp+4A0h+P]
0x180030522  mov     [rsp+4A0h+var_460], ebx
0x180030526  mov     [rsp+4A0h+var_478], rax
0x18003052b  lea     rax, [rsp+4A0h+var_450]
0x180030530  mov     [rsp+4A0h+var_480], rax
0x180030535  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003053a  jmp     loc_180030E0F
0x18003053f  mov     rcx, [r14]; pDeviceID
0x180030542  lea     r15, [rdi+0D0h]
0x180030549  mov     rdx, r15; pdnDevInst
0x18003054c  call    ?GetDeviceNode@PnpApiWrapper@@YAJPEBGAEAI@Z; PnpApiWrapper::GetDeviceNode(ushort const *,uint &)
0x180030551  mov     ebx, eax
0x180030553  test    eax, eax
0x180030555  jns     short loc_1800305A9
0x180030557  mov     ecx, cs:dword_180069000
0x18003055d  mov     esi, 2
0x180030562  cmp     ecx, esi
0x180030564  jbe     loc_180030E0F
0x18003056a  mov     r8, cs:qword_180069018
0x180030571  mov     edx, 400h
0x180030576  mov     rcx, cs:qword_180069010
0x18003057d  test    rdx, rcx
0x180030580  jz      loc_180030E0F
0x180030586  mov     rax, r8
0x180030589  and     rax, rdx
0x18003058c  cmp     rax, r8
0x18003058f  jnz     loc_180030E0F
0x180030595  mov     dword ptr [rsp+4A0h+P], 17Fh
0x18003059d  lea     rdx, byte_18005EBD7
0x1800305a4  jmp     loc_180030507
0x1800305a9  lea     rcx, [rbp+3A0h+var_3E0]; this
0x1800305ad  call    ??0GameInputDeviceInfoBuilder@@QEAA@XZ; GameInputDeviceInfoBuilder::GameInputDeviceInfoBuilder(void)
0x1800305b2  mov     [rbp+3A0h+var_3DC], r13
0x1800305b6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800305ba  mov     rax, [r14]
0x1800305bd  inc     rcx
0x1800305c0  cmp     [rax+rcx*2], r13w
0x1800305c5  jnz     short loc_1800305BD
0x1800305c7  xorps   xmm0, xmm0
0x1800305ca  lea     r8, [rbp+3A0h+pbOutput]; pbOutput
0x1800305ce  movups  xmmword ptr [rbp+3A0h+pbOutput], xmm0
0x1800305d2  add     rcx, rcx; cbInput
0x1800305d5  movups  [rbp+3A0h+var_3F0], xmm0
0x1800305d9  mov     rdx, [r14]; pbInput
0x1800305dc  call    ?GenerateAppLocalDeviceId@GameInputServerDevice@@CAJ_KPEBXAEAUAPP_LOCAL_DEVICE_ID@@@Z; GameInputServerDevice::GenerateAppLocalDeviceId(unsigned __int64,void const *,APP_LOCAL_DEVICE_ID &)
0x1800305e1  mov     ebx, eax
0x1800305e3  test    eax, eax
0x1800305e5  jns     short loc_180030639
0x1800305e7  mov     ecx, cs:dword_180069000
0x1800305ed  mov     esi, 2
0x1800305f2  cmp     ecx, esi
0x1800305f4  jbe     loc_180030E06
0x1800305fa  mov     r8, cs:qword_180069018
0x180030601  mov     edx, 400h
0x180030606  mov     rcx, cs:qword_180069010
0x18003060d  test    rdx, rcx
0x180030610  jz      loc_180030E06
0x180030616  mov     rax, r8
0x180030619  and     rax, rdx
0x18003061c  cmp     rax, r8
0x18003061f  jnz     loc_180030E06
0x180030625  mov     dword ptr [rsp+4A0h+P], 193h
0x18003062d  lea     rdx, byte_1800616A5
0x180030634  jmp     loc_180030DD3
0x180030639  movups  xmm1, xmmword ptr [rbp+3A0h+pbOutput]
0x18003063d  mov     r14d, 10h
0x180030643  lea     rdx, ?c_keyboardInterfaceGuid@GameInputServerDevice@@0U_GUID@@B; Buf2
0x18003064a  movups  xmm0, [rbp+3A0h+var_3F0]
0x18003064e  mov     r8d, r14d; Size
0x180030651  lea     rcx, [rbp+3A0h+Buf1]; Buf1
0x180030655  movups  [rbp+3A0h+var_3C0], xmm1
0x180030659  movups  [rbp+3A0h+var_3B0], xmm0
0x18003065d  movups  [rbp+3A0h+var_3A0], xmm1
0x180030661  movups  [rbp+3A0h+var_390], xmm0
0x180030665  call    memcmp_0
0x18003066a  lea     esi, [r14-0Eh]
0x18003066e  test    eax, eax
0x180030670  jnz     short loc_180030677
0x180030672  lea     ecx, [rsi+4]
0x180030675  jmp     short loc_18003067A
0x180030677  movzx   ecx, si
0x18003067a  mov     eax, 1
0x18003067f  mov     [rbp+3A0h+var_3D2], cx
0x180030683  mov     [rbp+3A0h+var_3D4], ax
0x180030687  lea     r9, [rsp+4A0h+P]
0x18003068c  mov     [rbp+3A0h+var_380], 3
0x180030694  lea     r8, DEVPKEY_NAME
0x18003069b  mov     eax, [r15]
0x18003069e  lea     rdx, [rsp+4A0h+var_460]
0x1800306a3  lea     rcx, ?GetDeviceNodeProperty@Adapters@PnpApiWrapper@@YAKPEAXPEBU_DEVPROPKEY@@AEAI0PEAK@Z; PnpApiWrapper::Adapters::GetDeviceNodeProperty(void *,_DEVPROPKEY const *,uint &,void *,ulong *)
0x1800306aa  mov     [rsp+4A0h+var_460], eax
0x1800306ae  mov     [rsp+4A0h+P], r13
0x1800306b3  call    ?GetDeviceStringProperty@Details@PnpApiWrapper@@YAJP6AKPEAXPEBU_DEVPROPKEY@@AEAI0PEAK@Z01AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z; PnpApiWrapper::Details::GetDeviceStringProperty(ulong (*)(void *,_DEVPROPKEY const *,uint &,void *,ulong *),void *,_DEVPROPKEY const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &)
0x1800306b8  mov     rcx, [rsp+4A0h+P]; P
0x1800306bd  test    rcx, rcx
0x1800306c0  jz      short loc_1800306C7
0x1800306c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800306c7  mov     r8, r14; Size
0x1800306ca  lea     rdx, ?c_keyboardInterfaceGuid@GameInputServerDevice@@0U_GUID@@B; Buf2
0x1800306d1  lea     rcx, [rbp+3A0h+Buf1]; Buf1
0x1800306d5  call    memcmp_0
0x1800306da  test    eax, eax
0x1800306dc  jnz     loc_180030763
0x1800306e2  xorps   xmm0, xmm0
0x1800306e5  lea     rdx, [rsp+4A0h+var_438]; struct GameInputKeyboardInfo *
0x1800306ea  xor     eax, eax
0x1800306ec  mov     rcx, rdi; this
0x1800306ef  movups  [rsp+4A0h+var_438], xmm0
0x1800306f4  mov     [rbp+3A0h+var_418], rax
0x1800306f8  movups  [rsp+4A0h+var_428], xmm0
0x1800306fd  call    ?TryReadKeyboardInfo@GameInputServerDevice@@AEAAXPEAUGameInputKeyboardInfo@@@Z; GameInputServerDevice::TryReadKeyboardInfo(GameInputKeyboardInfo *)
0x180030702  lea     rdx, [rsp+4A0h+var_438]; struct GameInputKeyboardInfo *
0x180030707  lea     rcx, [rbp+3A0h+var_3E0]; this
0x18003070b  call    ?AddKeyboardInfo@GameInputDeviceInfoBuilder@@QEAAJPEBUGameInputKeyboardInfo@@@Z; GameInputDeviceInfoBuilder::AddKeyboardInfo(GameInputKeyboardInfo const *)
0x180030710  mov     ebx, eax
0x180030712  test    eax, eax
0x180030714  jns     short loc_180030763
0x180030716  mov     ecx, cs:dword_180069000
0x18003071c  cmp     ecx, esi
0x18003071e  jbe     loc_180030E06
0x180030724  mov     r8, cs:qword_180069018
0x18003072b  mov     edx, 400h
0x180030730  mov     rcx, cs:qword_180069010
0x180030737  test    rdx, rcx
0x18003073a  jz      loc_180030E06
0x180030740  mov     rax, r8
0x180030743  and     rax, rdx
0x180030746  cmp     rax, r8
0x180030749  jnz     loc_180030E06
0x18003074f  mov     dword ptr [rsp+4A0h+P], 1B3h
0x180030757  lea     rdx, word_18005F996
0x18003075e  jmp     loc_180030DD3
0x180030763  mov     r8, r14; Size
0x180030766  lea     rdx, ?c_mouseInterfaceGuid@GameInputServerDevice@@0U_GUID@@B; Buf2
0x18003076d  lea     rcx, [rbp+3A0h+Buf1]; Buf1
0x180030771  call    memcmp_0
0x180030776  test    eax, eax
0x180030778  jnz     short loc_1800307F0
0x18003077a  xorps   xmm0, xmm0
0x18003077d  lea     rdx, [rsp+4A0h+var_450]; struct GameInputMouseInfo *
0x180030782  mov     rcx, rdi; this
0x180030785  movups  [rsp+4A0h+var_450], xmm0
0x18003078a  call    ?TryReadMouseInfo@GameInputServerDevice@@AEAAXPEAUGameInputMouseInfo@@@Z; GameInputServerDevice::TryReadMouseInfo(GameInputMouseInfo *)
0x18003078f  lea     rdx, [rsp+4A0h+var_450]; struct GameInputMouseInfo *
0x180030794  lea     rcx, [rbp+3A0h+var_3E0]; this
0x180030798  call    ?AddMouseInfo@GameInputDeviceInfoBuilder@@QEAAJPEBUGameInputMouseInfo@@@Z; GameInputDeviceInfoBuilder::AddMouseInfo(GameInputMouseInfo const *)
0x18003079d  mov     ebx, eax
0x18003079f  test    eax, eax
0x1800307a1  jns     short loc_1800307F0
0x1800307a3  mov     ecx, cs:dword_180069000
0x1800307a9  cmp     ecx, esi
0x1800307ab  jbe     loc_180030E06
0x1800307b1  mov     r8, cs:qword_180069018
0x1800307b8  mov     edx, 400h
0x1800307bd  mov     rcx, cs:qword_180069010
0x1800307c4  test    rdx, rcx
0x1800307c7  jz      loc_180030E06
0x1800307cd  mov     rax, r8
0x1800307d0  and     rax, rdx
0x1800307d3  cmp     rax, r8
0x1800307d6  jnz     loc_180030E06
0x1800307dc  mov     dword ptr [rsp+4A0h+P], 1BBh
0x1800307e4  lea     rdx, word_18005ED5E
0x1800307eb  jmp     loc_180030DD3
0x1800307f0  lea     rdx, [rsp+4A0h+var_440]; struct GameInputDeviceInfo **
0x1800307f5  mov     [rsp+4A0h+var_440], r13
0x1800307fa  lea     rcx, [rbp+3A0h+var_3E0]; this
0x1800307fe  call    ?Make@GameInputDeviceInfoBuilder@@QEAAJPEAPEAUGameInputDeviceInfo@@@Z; GameInputDeviceInfoBuilder::Make(GameInputDeviceInfo * *)
0x180030803  mov     ebx, eax
0x180030805  test    eax, eax
0x180030807  jns     short loc_180030856
0x180030809  mov     ecx, cs:dword_180069000
0x18003080f  cmp     ecx, esi
0x180030811  jbe     loc_180030E06
0x180030817  mov     r8, cs:qword_180069018
0x18003081e  mov     edx, 400h
0x180030823  mov     rcx, cs:qword_180069010
0x18003082a  test    rdx, rcx
0x18003082d  jz      loc_180030E06
  ... truncated ...
```
