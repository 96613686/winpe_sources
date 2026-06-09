# HidForceFeedbackBroker::OpenDevice(IHidForceFeedbackDevice * *,ushort const *,ushort,ushort)

- ea: `0x180018390`
- end: `0x180018a78`
- name: `?OpenDevice@HidForceFeedbackBroker@@UEAAJPEAPEAUIHidForceFeedbackDevice@@PEBGGG@Z`
- size: `1768`
- prototype: `int(HidForceFeedbackBroker *__hidden this, struct IHidForceFeedbackDevice **, const unsigned __int16 *, unsigned __int16, unsigned __int16)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001304`
- `0x180001cc0`
- `0x18000c11c`
- `0x18000f244`
- `0x1800161f0`
- `0x1800169fc`
- `0x180016e94`
- `0x180017cc8`
- `0x180018390`
- `0x18004c8a5`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800184ed`
- `ntdll!RtlAllocateHeap` at `0x18001866f`
- `ntdll!RtlAllocateHeap` at `0x180018778`
- `ntdll!RtlAllocateHeap` at `0x1800184ed`
- `ntdll!RtlAllocateHeap` at `0x18001866f`
- `ntdll!RtlAllocateHeap` at `0x180018778`

## string_xrefs

- `0x1800183fc`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x1800185c0`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x1800186dc`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x180018815`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x1800188d1`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x180018989`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x1800189f6`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x18001880a`: `HID force feedback device opened`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackBroker::OpenDevice(
        HidForceFeedbackBroker *this,
        struct IHidForceFeedbackDevice **a2,
        const unsigned __int16 *a3,
        __int16 a4,
        unsigned __int16 a5)
{
  int v8; // ebx
  int v9; // r8d
  int v10; // r9d
  __int64 result; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  struct IDirectInputDevice8W *v15; // rcx
  int v16; // r14d
  signed __int32 v17; // edi
  _DWORD *Heap; // rax
  int v19; // r8d
  int v20; // r9d
  _DWORD *v21; // rbx
  int v22; // r13d
  const struct std::nothrow_t *v23; // rdx
  int v24; // edi
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  __int16 *v28; // rdx
  _QWORD *v29; // rax
  const struct std::nothrow_t *v30; // rdx
  int v31; // r8d
  int v32; // r9d
  _QWORD *v33; // rdi
  const struct std::nothrow_t *v34; // rdx
  int v35; // r8d
  int v36; // r9d
  int v37; // r14d
  __int64 v38; // rcx
  const struct std::nothrow_t *v39; // rdx
  HidForceFeedbackDevice *v40; // rax
  int v41; // r8d
  int v42; // r9d
  struct IHidForceFeedbackDevice *v43; // rax
  __int64 v44; // rcx
  void (*Release)(void); // rax
  int v46; // [rsp+70h] [rbp-41h] BYREF
  int v47; // [rsp+74h] [rbp-3Dh] BYREF
  int v48; // [rsp+78h] [rbp-39h] BYREF
  const char *v49; // [rsp+80h] [rbp-31h] BYREF
  struct IDirectInputDevice8W *v50; // [rsp+88h] [rbp-29h] BYREF
  const char *v51; // [rsp+90h] [rbp-21h] BYREF
  int v52; // [rsp+98h] [rbp-19h] BYREF
  struct _GUID *v53; // [rsp+A0h] [rbp-11h] BYREF
  const unsigned __int16 *v54; // [rsp+A8h] [rbp-9h] BYREF
  const char *v55; // [rsp+B0h] [rbp-1h] BYREF
  struct _GUID v56; // [rsp+B8h] [rbp+7h] BYREF

  LOWORD(v46) = a4;
  v8 = HidForceFeedbackBroker::InitializeIfNeeded(this);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v47 = v8;
      v49 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
      v46 = 24;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)&dword_18005B81C,
        v9,
        v10,
        (__int64)&v49,
        (__int64)&v46,
        (__int64)&v47);
    }
    return (unsigned int)v8;
  }
  v12 = *((_QWORD *)this + 3);
  v56 = 0;
  result = (*(__int64 (__fastcall **)(__int64, GUID *, const unsigned __int16 *, struct _GUID *))(*(_QWORD *)v12 + 64LL))(
             v12,
             &GUID_HIDClass,
             a3,
             &v56);
  if ( (int)result >= 0 )
  {
    v13 = *((_QWORD *)this + 3);
    v50 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, struct IDirectInputDevice8W **, _QWORD))(*(_QWORD *)v13 + 24LL))(
            v13,
            &v56,
            &v50,
            0);
    v15 = v50;
    v8 = v14;
    if ( v14 < 0 )
      goto LABEL_9;
    v8 = ((__int64 (__fastcall *)(struct IDirectInputDevice8W *, _QWORD))v50->lpVtbl->SetDataFormat)(
           v50,
           *((_QWORD *)this + 4));
    if ( v8 < 0 )
    {
      v15 = v50;
LABEL_9:
      if ( v15 )
        ((void (__fastcall *)(struct IDirectInputDevice8W *))v15->lpVtbl->Release)(v15);
      return (unsigned int)v8;
    }
    v16 = *((_DWORD *)this + 11);
    v17 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 10, 1u);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x7D4u);
    v21 = Heap;
    if ( !Heap )
    {
      if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        LODWORD(v49) = -2147024882;
        v51 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
        v48 = 36;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)byte_18005D865,
          v19,
          v20,
          (__int64)&v51,
          (__int64)&v48,
          (__int64)&v49);
      }
      if ( !v50 )
        return 2147942414LL;
      Release = (void (*)(void))v50->lpVtbl->Release;
      goto LABEL_72;
    }
    v22 = (v16 << 16) | (v17 + 1);
    *Heap = v22;
    Heap[1] = (unsigned __int16)v46;
    Heap[2] = a5;
    memset_0(Heap + 3, 0, 0xDCu);
    v21[58] = 0;
    *(_OWORD *)(v21 + 59) = 0;
    memset_0(v21 + 63, 0, 0x6C0u);
    v21[495] = 0;
    *((_OWORD *)v21 + 124) = 0;
    v21[500] = 0;
    v24 = HidForceFeedbackSettings::LoadFromDevice((HidForceFeedbackSettings *)v21, v50);
    if ( v24 < 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_20;
      v23 = (const struct std::nothrow_t *)qword_180069018;
      v27 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        goto LABEL_20;
      v46 = 37;
      v28 = (__int16 *)byte_18005B685;
LABEL_19:
      v49 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
      v47 = v24;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v27,
        (_DWORD)v28,
        v25,
        v26,
        (__int64)&v49,
        (__int64)&v46,
        (__int64)&v47);
LABEL_20:
      operator delete(v21, v23);
      if ( v50 )
        ((void (__fastcall *)(struct IDirectInputDevice8W *))v50->lpVtbl->Release)(v50);
      return (unsigned int)v24;
    }
    v24 = HidForceFeedbackSettings::LoadFromRegistry((HidForceFeedbackSettings *)v21);
    if ( v24 < 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_20;
      v23 = (const struct std::nothrow_t *)qword_180069018;
      v27 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        goto LABEL_20;
      v46 = 38;
      v28 = word_18005B48A;
      goto LABEL_19;
    }
    v29 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
    v33 = v29;
    if ( !v29 )
    {
      if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        LODWORD(v49) = -2147024882;
        v51 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
        v48 = 41;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)&word_18005B8E6,
          v31,
          v32,
          (__int64)&v51,
          (__int64)&v48,
          (__int64)&v49);
      }
LABEL_59:
      operator delete(v21, v30);
LABEL_60:
      if ( !v50 )
        return 2147942414LL;
      Release = (void (*)(void))v50->lpVtbl->Release;
LABEL_72:
      Release();
      return 2147942414LL;
    }
    *(_DWORD *)v29 = v22;
    v29[1] = v21;
    v29[2] = 0;
    *((_DWORD *)v29 + 6) = 1065353216;
    v37 = HidForceFeedbackDriver::Initialize((HidForceFeedbackDriver *)v29, &v56, a3);
    if ( v37 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v34 = (const struct std::nothrow_t *)qword_180069018;
        if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
        {
          v47 = v37;
          v49 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
          v46 = 42;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)&byte_18005B24F,
            v35,
            v36,
            (__int64)&v49,
            (__int64)&v46,
            (__int64)&v47);
        }
      }
      v38 = v33[2];
      if ( v38 )
      {
        (*(void (__fastcall **)(__int64, const struct std::nothrow_t *))(*(_QWORD *)v38 + 16LL))(v38, v34);
        v33[2] = 0;
      }
      operator delete(v33, v34);
      operator delete(v21, v39);
      if ( v50 )
        ((void (__fastcall *)(struct IDirectInputDevice8W *))v50->lpVtbl->Release)(v50);
      return (unsigned int)v37;
    }
    v40 = (HidForceFeedbackDevice *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x178u);
    if ( !v40 )
    {
      *a2 = 0;
      goto LABEL_50;
    }
    v43 = HidForceFeedbackDevice::HidForceFeedbackDevice(
            v40,
            v50,
            (struct HidForceFeedbackDriver *)v33,
            (struct HidForceFeedbackSettings *)v21);
    *a2 = v43;
    if ( !v43 )
    {
      v21 = 0;
      v33 = 0;
LABEL_50:
      if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        LODWORD(v49) = -2147024882;
        v51 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
        v48 = 45;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)&dword_18005E1C4,
          v41,
          v42,
          (__int64)&v51,
          (__int64)&v48,
          (__int64)&v49);
      }
      if ( v33 )
      {
        v44 = v33[2];
        if ( v44 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          v33[2] = 0;
        }
        operator delete(v33, v30);
      }
      if ( !v21 )
        goto LABEL_60;
      goto LABEL_59;
    }
    if ( (unsigned int)dword_180069000 > 4 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      LOWORD(v47) = a5;
      v53 = &v56;
      v48 = *((_DWORD *)this + 11);
      v55 = "HID force feedback device opened";
      v51 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
      v54 = a3;
      v52 = v22;
      LODWORD(v49) = 54;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
        qword_180069018,
        (unsigned int)&word_18005CEE6,
        v41,
        v42,
        (__int64)&v51,
        (__int64)&v49,
        (__int64)&v55,
        (__int64)&v48,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v53,
        (__int64)&v46,
        (__int64)&v47);
    }
    if ( v50 )
      ((void (__fastcall *)(struct IDirectInputDevice8W *))v50->lpVtbl->Release)(v50);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180018390  mov     [rsp-8+arg_18], rbx
0x180018395  push    rbp
0x180018396  push    rsi
0x180018397  push    rdi
0x180018398  push    r12
0x18001839a  push    r13
0x18001839c  push    r14
0x18001839e  push    r15
0x1800183a0  lea     rbp, [rsp-1Fh]
0x1800183a5  sub     rsp, 0D0h
0x1800183ac  mov     rax, cs:__security_cookie
0x1800183b3  xor     rax, rsp
0x1800183b6  mov     [rbp+4Fh+var_38], rax
0x1800183ba  mov     word ptr [rbp+4Fh+var_90], r9w
0x1800183bf  mov     r15, r8
0x1800183c2  mov     r12, rdx
0x1800183c5  mov     rsi, rcx
0x1800183c8  call    ?InitializeIfNeeded@HidForceFeedbackBroker@@AEAAJXZ; HidForceFeedbackBroker::InitializeIfNeeded(void)
0x1800183cd  mov     ebx, eax
0x1800183cf  test    eax, eax
0x1800183d1  jns     short loc_18001843F
0x1800183d3  mov     ecx, cs:dword_180069000
0x1800183d9  cmp     ecx, 2
0x1800183dc  jbe     short loc_180018438
0x1800183de  mov     rdx, cs:qword_180069018
0x1800183e5  mov     rcx, cs:qword_180069010
0x1800183ec  test    cl, 8
0x1800183ef  jz      short loc_180018438
0x1800183f1  mov     rax, rdx
0x1800183f4  and     eax, 8
0x1800183f7  cmp     rax, rdx
0x1800183fa  jnz     short loc_180018438
0x1800183fc  lea     rax, aOnecoreXboxGam_36; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180018403  mov     [rbp+4Fh+var_8C], ebx
0x180018406  mov     [rbp+4Fh+var_80], rax
0x18001840a  lea     rdx, dword_18005B81C
0x180018411  lea     rax, [rbp+4Fh+var_8C]
0x180018415  mov     [rbp+4Fh+var_90], 18h
0x18001841c  mov     [rsp+100h+var_D0], rax
0x180018421  lea     rax, [rbp+4Fh+var_90]
0x180018425  mov     [rsp+100h+var_D8], rax
0x18001842a  lea     rax, [rbp+4Fh+var_80]
0x18001842e  mov     [rsp+100h+var_E0], rax
0x180018433  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018438  mov     eax, ebx
0x18001843a  jmp     loc_180018A50
0x18001843f  mov     rcx, [rsi+18h]
0x180018443  lea     r9, [rbp+4Fh+var_48]
0x180018447  xorps   xmm0, xmm0
0x18001844a  lea     rdx, GUID_HIDClass
0x180018451  movups  xmmword ptr [rbp+4Fh+var_48.Data1], xmm0
0x180018455  mov     r8, r15
0x180018458  mov     rax, [rcx]
0x18001845b  mov     rax, [rax+40h]
0x18001845f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018464  test    eax, eax
0x180018466  js      loc_180018A50
0x18001846c  mov     rcx, [rsi+18h]
0x180018470  lea     r8, [rbp+4Fh+var_78]
0x180018474  mov     [rbp+4Fh+var_78], 0
0x18001847c  lea     rdx, [rbp+4Fh+var_48]
0x180018480  xor     r9d, r9d
0x180018483  mov     rax, [rcx]
0x180018486  mov     rax, [rax+18h]
0x18001848a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001848f  mov     rcx, [rbp+4Fh+var_78]
0x180018493  mov     ebx, eax
0x180018495  test    eax, eax
0x180018497  jns     short loc_1800184AC
0x180018499  test    rcx, rcx
0x18001849c  jz      short loc_180018438
0x18001849e  mov     rdx, [rcx]
0x1800184a1  mov     rax, [rdx+10h]
0x1800184a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184aa  jmp     short loc_180018438
0x1800184ac  mov     rax, [rcx]
0x1800184af  mov     rdx, [rsi+20h]
0x1800184b3  mov     rax, [rax+58h]
0x1800184b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184bc  mov     ebx, eax
0x1800184be  test    eax, eax
0x1800184c0  jns     short loc_1800184C8
0x1800184c2  mov     rcx, [rbp+4Fh+var_78]
0x1800184c6  jmp     short loc_180018499
0x1800184c8  mov     r14d, [rsi+2Ch]
0x1800184cc  mov     edi, 1
0x1800184d1  nop
0x1800184d2  lock xadd [rsi+28h], edi
0x1800184d7  nop
0x1800184d8  xor     edx, edx; Flags
0x1800184da  mov     rcx, gs:60h
0x1800184e3  mov     r8d, 7D4h; Size
0x1800184e9  mov     rcx, [rcx+30h]; HeapHandle
0x1800184ed  call    cs:__imp_RtlAllocateHeap
0x1800184f4  nop     dword ptr [rax+rax+00h]
0x1800184f9  mov     rbx, rax
0x1800184fc  test    rax, rax
0x1800184ff  jz      loc_1800189CE
0x180018505  lea     r13d, [rdi+1]
0x180018509  shl     r14d, 10h
0x18001850d  or      r13d, r14d
0x180018510  lea     rcx, [rbx+0Ch]; void *
0x180018514  mov     [rax], r13d
0x180018517  xor     edx, edx; Val
0x180018519  movzx   eax, word ptr [rbp+4Fh+var_90]
0x18001851d  mov     r8d, 0DCh; Size
0x180018523  mov     [rbx+4], eax
0x180018526  movzx   eax, [rbp+4Fh+arg_20]
0x18001852a  mov     [rbx+8], eax
0x18001852d  call    memset_0
0x180018532  xorps   xmm0, xmm0
0x180018535  lea     rcx, [rbx+0FCh]; void *
0x18001853c  xor     r14d, r14d
0x18001853f  xor     edx, edx; Val
0x180018541  mov     [rbx+0E8h], r14d
0x180018548  mov     r8d, 6C0h; Size
0x18001854e  movups  xmmword ptr [rbx+0ECh], xmm0
0x180018555  call    memset_0
0x18001855a  mov     [rbx+7BCh], r14d
0x180018561  xorps   xmm0, xmm0
0x180018564  movups  xmmword ptr [rbx+7C0h], xmm0
0x18001856b  xor     eax, eax
0x18001856d  mov     rcx, rbx; this
0x180018570  mov     [rbx+7D0h], eax
0x180018576  mov     rdx, [rbp+4Fh+var_78]; struct IDirectInputDevice8W *
0x18001857a  call    ?LoadFromDevice@HidForceFeedbackSettings@@QEAAJPEAUIDirectInputDevice8W@@@Z; HidForceFeedbackSettings::LoadFromDevice(IDirectInputDevice8W *)
0x18001857f  mov     edi, eax
0x180018581  test    eax, eax
0x180018583  jns     loc_180018612
0x180018589  mov     ecx, cs:dword_180069000
0x18001858f  cmp     ecx, 2
0x180018592  jbe     short loc_1800185EE
0x180018594  mov     rdx, cs:qword_180069018
0x18001859b  mov     rcx, cs:qword_180069010
0x1800185a2  test    cl, 8
0x1800185a5  jz      short loc_1800185EE
0x1800185a7  mov     rax, rdx
0x1800185aa  and     eax, 8
0x1800185ad  cmp     rax, rdx
0x1800185b0  jnz     short loc_1800185EE
0x1800185b2  mov     [rbp+4Fh+var_90], 25h ; '%'
0x1800185b9  lea     rdx, byte_18005B685
0x1800185c0  lea     rax, aOnecoreXboxGam_36; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x1800185c7  mov     [rbp+4Fh+var_80], rax
0x1800185cb  lea     rax, [rbp+4Fh+var_8C]
0x1800185cf  mov     [rsp+100h+var_D0], rax
0x1800185d4  lea     rax, [rbp+4Fh+var_90]
0x1800185d8  mov     [rsp+100h+var_D8], rax
0x1800185dd  lea     rax, [rbp+4Fh+var_80]
0x1800185e1  mov     [rsp+100h+var_E0], rax
0x1800185e6  mov     [rbp+4Fh+var_8C], edi
0x1800185e9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800185ee  mov     rcx, rbx; P
0x1800185f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800185f6  mov     rcx, [rbp+4Fh+var_78]
0x1800185fa  test    rcx, rcx
0x1800185fd  jz      short loc_18001860B
0x1800185ff  mov     rax, [rcx]
0x180018602  mov     rax, [rax+10h]
0x180018606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001860b  mov     eax, edi
0x18001860d  jmp     loc_180018A50
0x180018612  mov     rcx, rbx; this
0x180018615  call    ?LoadFromRegistry@HidForceFeedbackSettings@@QEAAJXZ; HidForceFeedbackSettings::LoadFromRegistry(void)
0x18001861a  mov     edi, eax
0x18001861c  test    eax, eax
0x18001861e  jns     short loc_18001865C
0x180018620  mov     ecx, cs:dword_180069000
0x180018626  cmp     ecx, 2
0x180018629  jbe     short loc_1800185EE
0x18001862b  mov     rdx, cs:qword_180069018
0x180018632  mov     rcx, cs:qword_180069010
0x180018639  test    cl, 8
0x18001863c  jz      short loc_1800185EE
0x18001863e  mov     rax, rdx
0x180018641  and     eax, 8
0x180018644  cmp     rax, rdx
0x180018647  jnz     short loc_1800185EE
0x180018649  mov     [rbp+4Fh+var_90], 26h ; '&'
0x180018650  lea     rdx, word_18005B48A
0x180018657  jmp     loc_1800185C0
0x18001865c  mov     rcx, gs:60h
0x180018665  xor     edx, edx; Flags
0x180018667  mov     rcx, [rcx+30h]; HeapHandle
0x18001866b  lea     r8d, [rdx+20h]; Size
0x18001866f  call    cs:__imp_RtlAllocateHeap
0x180018676  nop     dword ptr [rax+rax+00h]
0x18001867b  mov     rdi, rax
0x18001867e  test    rax, rax
0x180018681  jz      loc_180018961
0x180018687  mov     r8, r15; unsigned __int16 *
0x18001868a  mov     [rax], r13d
0x18001868d  lea     rdx, [rbp+4Fh+var_48]; struct _GUID *
0x180018691  mov     [rax+8], rbx
0x180018695  mov     rcx, rax; this
0x180018698  mov     [rax+10h], r14
0x18001869c  mov     dword ptr [rax+18h], 3F800000h
0x1800186a3  call    ?Initialize@HidForceFeedbackDriver@@QEAAJAEBU_GUID@@PEBG@Z; HidForceFeedbackDriver::Initialize(_GUID const &,ushort const *)
0x1800186a8  mov     r14d, eax
0x1800186ab  test    eax, eax
0x1800186ad  jns     loc_180018763
0x1800186b3  mov     ecx, cs:dword_180069000
0x1800186b9  cmp     ecx, 2
0x1800186bc  jbe     short loc_180018719
0x1800186be  mov     rdx, cs:qword_180069018
0x1800186c5  mov     rcx, cs:qword_180069010
0x1800186cc  test    cl, 8
0x1800186cf  jz      short loc_180018719
0x1800186d1  mov     rax, rdx
0x1800186d4  and     eax, 8
0x1800186d7  cmp     rax, rdx
0x1800186da  jnz     short loc_180018719
0x1800186dc  lea     rax, aOnecoreXboxGam_36; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x1800186e3  mov     [rbp+4Fh+var_8C], r14d
0x1800186e7  mov     [rbp+4Fh+var_80], rax
0x1800186eb  lea     rdx, byte_18005B24F
0x1800186f2  lea     rax, [rbp+4Fh+var_8C]
0x1800186f6  mov     [rbp+4Fh+var_90], 2Ah ; '*'
0x1800186fd  mov     [rsp+100h+var_D0], rax
0x180018702  lea     rax, [rbp+4Fh+var_90]
0x180018706  mov     [rsp+100h+var_D8], rax
0x18001870b  lea     rax, [rbp+4Fh+var_80]
0x18001870f  mov     [rsp+100h+var_E0], rax
0x180018714  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018719  mov     rcx, [rdi+10h]
0x18001871d  test    rcx, rcx
0x180018720  jz      short loc_180018736
0x180018722  mov     rax, [rcx]
0x180018725  mov     rax, [rax+10h]
0x180018729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001872e  mov     qword ptr [rdi+10h], 0
0x180018736  mov     rcx, rdi; P
0x180018739  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001873e  mov     rcx, rbx; P
0x180018741  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018746  mov     rcx, [rbp+4Fh+var_78]
0x18001874a  test    rcx, rcx
0x18001874d  jz      short loc_18001875B
0x18001874f  mov     rax, [rcx]
0x180018752  mov     rax, [rax+10h]
0x180018756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001875b  mov     eax, r14d
0x18001875e  jmp     loc_180018A50
0x180018763  mov     rcx, gs:60h
0x18001876c  xor     edx, edx; Flags
0x18001876e  mov     r8d, 178h; Size
0x180018774  mov     rcx, [rcx+30h]; HeapHandle
0x180018778  call    cs:__imp_RtlAllocateHeap
0x18001877f  nop     dword ptr [rax+rax+00h]
0x180018784  test    rax, rax
0x180018787  jz      loc_1800188A1
0x18001878d  mov     rdx, [rbp+4Fh+var_78]; struct IDirectInputDevice8W *
0x180018791  mov     r9, rbx; struct HidForceFeedbackSettings *
0x180018794  mov     r8, rdi; struct HidForceFeedbackDriver *
0x180018797  mov     rcx, rax; this
0x18001879a  call    ??0HidForceFeedbackDevice@@QEAA@PEAUIDirectInputDevice8W@@PEAVHidForceFeedbackDriver@@PEAVHidForceFeedbackSettings@@@Z; HidForceFeedbackDevice::HidForceFeedbackDevice(IDirectInputDevice8W *,HidForceFeedbackDriver *,HidForceFeedbackSettings *)
0x18001879f  mov     [r12], rax
0x1800187a3  test    rax, rax
0x1800187a6  jnz     short loc_1800187B1
0x1800187a8  xor     ebx, ebx
0x1800187aa  xor     edi, edi
0x1800187ac  jmp     loc_1800188A9
0x1800187b1  mov     eax, cs:dword_180069000
0x1800187b7  cmp     eax, 4
0x1800187ba  jbe     loc_180018885
0x1800187c0  mov     rcx, cs:qword_180069018
0x1800187c7  mov     rax, cs:qword_180069010
0x1800187ce  test    al, 8
0x1800187d0  jz      loc_180018885
0x1800187d6  mov     rax, rcx
0x1800187d9  and     eax, 8
0x1800187dc  cmp     rax, rcx
0x1800187df  jnz     loc_180018885
0x1800187e5  movzx   eax, [rbp+4Fh+arg_20]
0x1800187e9  lea     rdx, word_18005CEE6
0x1800187f0  mov     word ptr [rbp+4Fh+var_8C], ax
0x1800187f4  movzx   eax, word ptr [rbp+4Fh+var_90]
0x1800187f8  mov     word ptr [rbp+4Fh+var_90], ax
0x1800187fc  lea     rax, [rbp+4Fh+var_48]
0x180018800  mov     [rbp+4Fh+var_60], rax
0x180018804  mov     eax, [rsi+2Ch]
0x180018807  mov     [rbp+4Fh+var_88], eax
0x18001880a  lea     rax, aHidForceFeedba_7; "HID force feedback device opened"
0x180018811  mov     [rbp+4Fh+var_50], rax
0x180018815  lea     rax, aOnecoreXboxGam_36; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x18001881c  mov     [rbp+4Fh+var_70], rax
0x180018820  lea     rax, [rbp+4Fh+var_8C]
0x180018824  mov     [rsp+100h+var_A0], rax
0x180018829  lea     rax, [rbp+4Fh+var_90]
0x18001882d  mov     [rsp+100h+var_A8], rax
0x180018832  lea     rax, [rbp+4Fh+var_60]
0x180018836  mov     [rsp+100h+var_B0], rax
0x18001883b  lea     rax, [rbp+4Fh+var_58]
0x18001883f  mov     [rsp+100h+var_B8], rax
0x180018844  lea     rax, [rbp+4Fh+var_68]
0x180018848  mov     [rsp+100h+var_C0], rax
0x18001884d  lea     rax, [rbp+4Fh+var_88]
0x180018851  mov     [rsp+100h+var_C8], rax
0x180018856  lea     rax, [rbp+4Fh+var_50]
0x18001885a  mov     [rsp+100h+var_D0], rax
  ... truncated ...
```
