# HidForceFeedbackEffectManager::Create(ForceFeedbackEffectManager * *,IGameInputServerDevice *)

- ea: `0x180012d70`
- end: `0x180013540`
- name: `?Create@HidForceFeedbackEffectManager@@SAJPEAPEAVForceFeedbackEffectManager@@PEAUIGameInputServerDevice@@@Z`
- size: `2000`
- prototype: `__int64 __fastcall(struct ForceFeedbackEffectManager **, struct IGameInputServerDevice *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180014f18`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x18000f3f8`
- `0x180012d70`
- `0x180017cc8`
- `0x18004c8a5`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180012f06`
- `ntdll!RtlAllocateHeap` at `0x1800132f4`
- `ntdll!RtlAllocateHeap` at `0x180012f06`
- `ntdll!RtlAllocateHeap` at `0x1800132f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800133b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800133b9`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackEffectManager::Create(
        struct ForceFeedbackEffectManager **a1,
        struct IGameInputServerDevice *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  char *v9; // rdx
  _DWORD *Heap; // rax
  int v12; // r8d
  int v13; // r9d
  _DWORD *v14; // rbx
  int v15; // edx
  const struct std::nothrow_t *v16; // rdx
  const struct std::nothrow_t *v17; // rdx
  int v18; // edi
  int v19; // r8d
  int v20; // r9d
  int v21; // r8d
  int v22; // r9d
  int v23; // r8d
  int v24; // r9d
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  __int16 *v28; // rdx
  HidForceFeedbackEffectManager *v29; // rax
  struct ForceFeedbackEffectManager *v30; // rax
  const struct std::nothrow_t *v31; // rdx
  const struct std::nothrow_t *v32; // rdx
  int v33; // r8d
  int v34; // r9d
  void (*v35)(void); // rax
  __int64 v36; // [rsp+40h] [rbp-40h] BYREF
  __int64 v37; // [rsp+48h] [rbp-38h] BYREF
  __int64 v38; // [rsp+50h] [rbp-30h] BYREF
  __int64 v39; // [rsp+58h] [rbp-28h] BYREF
  __int64 v40; // [rsp+60h] [rbp-20h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v42[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int16 v43; // [rsp+B0h] [rbp+30h] BYREF
  unsigned __int16 v44; // [rsp+B8h] [rbp+38h] BYREF
  int v45; // [rsp+C0h] [rbp+40h] BYREF
  int v46; // [rsp+C8h] [rbp+48h] BYREF

  *a1 = 0;
  v3 = *(_QWORD *)a2;
  v37 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IGameInputServerDevice *, __int64 *))(v3 + 8))(a2, &v37);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v4 = qword_180069018;
      v8 = qword_180069010;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v46 = 83;
        v9 = byte_18005D403;
LABEL_6:
        v42[0] = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
        v45 = v5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v8,
          (_DWORD)v9,
          v6,
          v7,
          (__int64)v42,
          (__int64)&v46,
          (__int64)&v45);
        goto LABEL_7;
      }
    }
    goto LABEL_7;
  }
  v44 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v37 + 80LL))(v37, &v44);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v4 = qword_180069018;
      v8 = qword_180069010;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v46 = 86;
        v9 = &byte_18005C17F;
        goto LABEL_6;
      }
    }
LABEL_7:
    if ( v37 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 16LL))(v37, v4);
    return (unsigned int)v5;
  }
  v43 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v37 + 72LL))(v37, &v43);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v4 = qword_180069018;
      v8 = qword_180069010;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v46 = 89;
        v9 = &byte_18005A3EF;
        goto LABEL_6;
      }
    }
    goto LABEL_7;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x7D4u);
  v14 = Heap;
  if ( !Heap )
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v45 = -2147024882;
      v42[0] = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
      v46 = 96;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&word_18005A2F6,
        v12,
        v13,
        (__int64)v42,
        (__int64)&v46,
        (__int64)&v45);
    }
    if ( !v37 )
      return 2147942414LL;
    v35 = *(void (**)(void))(*(_QWORD *)v37 + 16LL);
    goto LABEL_96;
  }
  v15 = v43;
  Heap[1] = v44;
  Heap[2] = v15;
  *Heap = 0;
  memset_0(Heap + 3, 0, 0xDCu);
  v14[58] = 0;
  *(_OWORD *)(v14 + 59) = 0;
  memset_0(v14 + 63, 0, 0x6C0u);
  v14[495] = 0;
  *((_OWORD *)v14 + 124) = 0;
  v14[500] = 0;
  if ( (int)HidForceFeedbackSettings::LoadFromRegistry((HidForceFeedbackSettings *)v14) < 0 )
  {
    operator delete(v14, v16);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    return 1;
  }
  v36 = 0;
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v37)(
          v37,
          &GUID_1baf6522_5f64_42c5_8267_b9fe2215bfbd,
          &v36);
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v17 = (const struct std::nothrow_t *)qword_180069018;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v45 = v18;
        v42[0] = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
        v46 = 103;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_18005D5ED,
          v19,
          v20,
          (__int64)v42,
          (__int64)&v46,
          (__int64)&v45);
      }
    }
LABEL_30:
    if ( v36 )
    {
      (*(void (__fastcall **)(__int64, const struct std::nothrow_t *))(*(_QWORD *)v36 + 16LL))(v36, v17);
      v36 = 0;
    }
    operator delete(v14, v17);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    return (unsigned int)v18;
  }
  v38 = 0;
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v36)(
          v36,
          &GUID_debcfefe_f763_4670_940b_57aae2b143ff,
          &v38);
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v17 = (const struct std::nothrow_t *)qword_180069018;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v45 = v18;
        v42[0] = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
        v46 = 106;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_18005DF95,
          v21,
          v22,
          (__int64)v42,
          (__int64)&v46,
          (__int64)&v45);
      }
    }
LABEL_40:
    if ( v38 )
    {
      (*(void (__fastcall **)(__int64, const struct std::nothrow_t *))(*(_QWORD *)v38 + 16LL))(v38, v17);
      v38 = 0;
    }
    goto LABEL_30;
  }
  v39 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v39);
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v17 = (const struct std::nothrow_t *)qword_180069018;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v45 = v18;
        v42[0] = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
        v46 = 109;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_18005A651,
          v23,
          v24,
          (__int64)v42,
          (__int64)&v46,
          (__int64)&v45);
      }
    }
LABEL_47:
    if ( v39 )
    {
      (*(void (__fastcall **)(__int64, const struct std::nothrow_t *))(*(_QWORD *)v39 + 16LL))(v39, v17);
      v39 = 0;
    }
    goto LABEL_40;
  }
  v40 = 0;
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v39)(
          v39,
          &GUID_c3542377_1ea7_4454_8deb_8aa6070db645,
          &v40);
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v17 = (const struct std::nothrow_t *)qword_180069018;
      v27 = qword_180069010;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v46 = 112;
        v28 = &word_18005D76E;
LABEL_54:
        v42[0] = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
        v45 = v18;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v27,
          (_DWORD)v28,
          v25,
          v26,
          (__int64)v42,
          (__int64)&v46,
          (__int64)&v45);
        goto LABEL_55;
      }
    }
    goto LABEL_55;
  }
  string = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 136LL))(v40, &string);
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v17 = (const struct std::nothrow_t *)qword_180069018;
      v27 = qword_180069010;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v46 = 115;
        v28 = (__int16 *)&unk_18005D6A8;
        goto LABEL_54;
      }
    }
LABEL_55:
    if ( v40 )
    {
      (*(void (__fastcall **)(__int64, const struct std::nothrow_t *))(*(_QWORD *)v40 + 16LL))(v40, v17);
      v40 = 0;
    }
    goto LABEL_47;
  }
  v29 = (HidForceFeedbackEffectManager *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xAF8u);
  if ( !v29 )
  {
    *a1 = 0;
LABEL_76:
    WindowsDeleteString(string);
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v45 = -2147024882;
      v42[0] = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
      v46 = 121;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_18005E345,
        v33,
        v34,
        (__int64)v42,
        (__int64)&v46,
        (__int64)&v45);
    }
    if ( v40 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v40 = 0;
    }
    if ( v39 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v39 = 0;
    }
    if ( v38 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      v38 = 0;
    }
    if ( v36 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      v36 = 0;
    }
    operator delete(v14, v32);
    if ( !v37 )
      return 2147942414LL;
    v35 = *(void (**)(void))(*(_QWORD *)v37 + 16LL);
LABEL_96:
    v35();
    return 2147942414LL;
  }
  v30 = HidForceFeedbackEffectManager::HidForceFeedbackEffectManager(v29, v44, v43, string);
  *a1 = v30;
  if ( !v30 )
    goto LABEL_76;
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  operator delete(v14, v31);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  return 0;
}

```

## disassembly

```asm
0x180012d70  push    rbp
0x180012d72  push    rbx
0x180012d73  push    rsi
0x180012d74  push    rdi
0x180012d75  push    r14
0x180012d77  mov     rbp, rsp
0x180012d7a  sub     rsp, 80h
0x180012d81  mov     r8, rdx
0x180012d84  xor     r14d, r14d
0x180012d87  mov     [rcx], r14
0x180012d8a  mov     rsi, rcx
0x180012d8d  mov     rax, [rdx]
0x180012d90  mov     rcx, r8
0x180012d93  lea     rdx, [rbp+var_38]
0x180012d97  mov     [rbp+var_38], r14
0x180012d9b  mov     rax, [rax+8]
0x180012d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012da4  mov     ebx, eax
0x180012da6  test    eax, eax
0x180012da8  jns     loc_180012E2F
0x180012dae  mov     ecx, cs:dword_180069000
0x180012db4  cmp     ecx, 2
0x180012db7  jbe     short loc_180012E13
0x180012db9  mov     rdx, cs:qword_180069018
0x180012dc0  mov     rcx, cs:qword_180069010
0x180012dc7  test    cl, 8
0x180012dca  jz      short loc_180012E13
0x180012dcc  mov     rax, rdx
0x180012dcf  and     eax, 8
0x180012dd2  cmp     rax, rdx
0x180012dd5  jnz     short loc_180012E13
0x180012dd7  mov     [rbp+arg_18], 53h ; 'S'
0x180012dde  lea     rdx, byte_18005D403
0x180012de5  lea     rax, aOnecoreXboxGam_17; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180012dec  mov     [rbp+var_10], rax
0x180012df0  lea     rax, [rbp+arg_10]
0x180012df4  mov     [rsp+80h+var_50], rax
0x180012df9  lea     rax, [rbp+arg_18]
0x180012dfd  mov     [rsp+80h+var_58], rax
0x180012e02  lea     rax, [rbp+var_10]
0x180012e06  mov     [rsp+80h+var_60], rax
0x180012e0b  mov     [rbp+arg_10], ebx
0x180012e0e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180012e13  mov     rcx, [rbp+var_38]
0x180012e17  test    rcx, rcx
0x180012e1a  jz      short loc_180012E28
0x180012e1c  mov     rax, [rcx]
0x180012e1f  mov     rax, [rax+10h]
0x180012e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e28  mov     eax, ebx
0x180012e2a  jmp     loc_180013531
0x180012e2f  mov     rcx, [rbp+var_38]
0x180012e33  lea     rdx, [rbp+arg_8]
0x180012e37  mov     [rbp+arg_8], r14w
0x180012e3c  mov     rax, [rcx]
0x180012e3f  mov     rax, [rax+50h]
0x180012e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e48  mov     ebx, eax
0x180012e4a  test    eax, eax
0x180012e4c  jns     short loc_180012E8A
0x180012e4e  mov     ecx, cs:dword_180069000
0x180012e54  cmp     ecx, 2
0x180012e57  jbe     short loc_180012E13
0x180012e59  mov     rdx, cs:qword_180069018
0x180012e60  mov     rcx, cs:qword_180069010
0x180012e67  test    cl, 8
0x180012e6a  jz      short loc_180012E13
0x180012e6c  mov     rax, rdx
0x180012e6f  and     eax, 8
0x180012e72  cmp     rax, rdx
0x180012e75  jnz     short loc_180012E13
0x180012e77  mov     [rbp+arg_18], 56h ; 'V'
0x180012e7e  lea     rdx, byte_18005C17F
0x180012e85  jmp     loc_180012DE5
0x180012e8a  mov     rcx, [rbp+var_38]
0x180012e8e  lea     rdx, [rbp+arg_0]
0x180012e92  mov     [rbp+arg_0], r14w
0x180012e97  mov     rax, [rcx]
0x180012e9a  mov     rax, [rax+48h]
0x180012e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ea3  mov     ebx, eax
0x180012ea5  test    eax, eax
0x180012ea7  jns     short loc_180012EF1
0x180012ea9  mov     ecx, cs:dword_180069000
0x180012eaf  cmp     ecx, 2
0x180012eb2  jbe     loc_180012E13
0x180012eb8  mov     rdx, cs:qword_180069018
0x180012ebf  mov     rcx, cs:qword_180069010
0x180012ec6  test    cl, 8
0x180012ec9  jz      loc_180012E13
0x180012ecf  mov     rax, rdx
0x180012ed2  and     eax, 8
0x180012ed5  cmp     rax, rdx
0x180012ed8  jnz     loc_180012E13
0x180012ede  mov     [rbp+arg_18], 59h ; 'Y'
0x180012ee5  lea     rdx, byte_18005A3EF
0x180012eec  jmp     loc_180012DE5
0x180012ef1  mov     rcx, gs:60h
0x180012efa  xor     edx, edx; Flags
0x180012efc  mov     r8d, 7D4h; Size
0x180012f02  mov     rcx, [rcx+30h]; HeapHandle
0x180012f06  call    cs:__imp_RtlAllocateHeap
0x180012f0d  nop     dword ptr [rax+rax+00h]
0x180012f12  mov     rbx, rax
0x180012f15  test    rax, rax
0x180012f18  jz      loc_1800134AF
0x180012f1e  movzx   edx, [rbp+arg_0]
0x180012f22  mov     r8d, 0DCh; Size
0x180012f28  movzx   ecx, [rbp+arg_8]
0x180012f2c  mov     [rax+4], ecx
0x180012f2f  lea     rcx, [rax+0Ch]; void *
0x180012f33  mov     [rax+8], edx
0x180012f36  xor     edx, edx; Val
0x180012f38  mov     [rax], r14d
0x180012f3b  call    memset_0
0x180012f40  xorps   xmm0, xmm0
0x180012f43  mov     [rbx+0E8h], r14d
0x180012f4a  lea     rcx, [rbx+0FCh]; void *
0x180012f51  xor     edx, edx; Val
0x180012f53  mov     r8d, 6C0h; Size
0x180012f59  movups  xmmword ptr [rbx+0ECh], xmm0
0x180012f60  call    memset_0
0x180012f65  mov     [rbx+7BCh], r14d
0x180012f6c  xorps   xmm0, xmm0
0x180012f6f  xor     eax, eax
0x180012f71  mov     rcx, rbx; this
0x180012f74  movups  xmmword ptr [rbx+7C0h], xmm0
0x180012f7b  mov     [rbx+7D0h], eax
0x180012f81  call    ?LoadFromRegistry@HidForceFeedbackSettings@@QEAAJXZ; HidForceFeedbackSettings::LoadFromRegistry(void)
0x180012f86  test    eax, eax
0x180012f88  jns     short loc_180012FB1
0x180012f8a  mov     rcx, rbx; P
0x180012f8d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012f92  mov     rcx, [rbp+var_38]
0x180012f96  test    rcx, rcx
0x180012f99  jz      short loc_180012FA7
0x180012f9b  mov     rax, [rcx]
0x180012f9e  mov     rax, [rax+10h]
0x180012fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fa7  mov     eax, 1
0x180012fac  jmp     loc_180013531
0x180012fb1  mov     rcx, [rbp+var_38]
0x180012fb5  lea     r8, [rbp+var_40]
0x180012fb9  mov     [rbp+var_40], r14
0x180012fbd  lea     rdx, _GUID_1baf6522_5f64_42c5_8267_b9fe2215bfbd
0x180012fc4  mov     rax, [rcx]
0x180012fc7  mov     rax, [rax]
0x180012fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fcf  mov     edi, eax
0x180012fd1  test    eax, eax
0x180012fd3  jns     loc_18001307B
0x180012fd9  mov     ecx, cs:dword_180069000
0x180012fdf  cmp     ecx, 2
0x180012fe2  jbe     short loc_18001303E
0x180012fe4  mov     rdx, cs:qword_180069018
0x180012feb  mov     rcx, cs:qword_180069010
0x180012ff2  test    cl, 8
0x180012ff5  jz      short loc_18001303E
0x180012ff7  mov     rax, rdx
0x180012ffa  and     eax, 8
0x180012ffd  cmp     rax, rdx
0x180013000  jnz     short loc_18001303E
0x180013002  lea     rax, aOnecoreXboxGam_17; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180013009  mov     [rbp+arg_10], edi
0x18001300c  mov     [rbp+var_10], rax
0x180013010  lea     rdx, byte_18005D5ED
0x180013017  lea     rax, [rbp+arg_10]
0x18001301b  mov     [rbp+arg_18], 67h ; 'g'
0x180013022  mov     [rsp+80h+var_50], rax
0x180013027  lea     rax, [rbp+arg_18]
0x18001302b  mov     [rsp+80h+var_58], rax
0x180013030  lea     rax, [rbp+var_10]
0x180013034  mov     [rsp+80h+var_60], rax
0x180013039  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001303e  mov     rcx, [rbp+var_40]
0x180013042  test    rcx, rcx
0x180013045  jz      short loc_180013057
0x180013047  mov     rax, [rcx]
0x18001304a  mov     rax, [rax+10h]
0x18001304e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013053  mov     [rbp+var_40], r14
0x180013057  mov     rcx, rbx; P
0x18001305a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001305f  mov     rcx, [rbp+var_38]
0x180013063  test    rcx, rcx
0x180013066  jz      short loc_180013074
0x180013068  mov     rax, [rcx]
0x18001306b  mov     rax, [rax+10h]
0x18001306f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013074  mov     eax, edi
0x180013076  jmp     loc_180013531
0x18001307b  mov     rcx, [rbp+var_40]
0x18001307f  lea     r8, [rbp+var_30]
0x180013083  mov     [rbp+var_30], r14
0x180013087  lea     rdx, _GUID_debcfefe_f763_4670_940b_57aae2b143ff
0x18001308e  mov     rax, [rcx]
0x180013091  mov     rax, [rax]
0x180013094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013099  mov     edi, eax
0x18001309b  test    eax, eax
0x18001309d  jns     loc_18001312A
0x1800130a3  mov     ecx, cs:dword_180069000
0x1800130a9  cmp     ecx, 2
0x1800130ac  jbe     short loc_180013108
0x1800130ae  mov     rdx, cs:qword_180069018
0x1800130b5  mov     rcx, cs:qword_180069010
0x1800130bc  test    cl, 8
0x1800130bf  jz      short loc_180013108
0x1800130c1  mov     rax, rdx
0x1800130c4  and     eax, 8
0x1800130c7  cmp     rax, rdx
0x1800130ca  jnz     short loc_180013108
0x1800130cc  lea     rax, aOnecoreXboxGam_17; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x1800130d3  mov     [rbp+arg_10], edi
0x1800130d6  mov     [rbp+var_10], rax
0x1800130da  lea     rdx, byte_18005DF95
0x1800130e1  lea     rax, [rbp+arg_10]
0x1800130e5  mov     [rbp+arg_18], 6Ah ; 'j'
0x1800130ec  mov     [rsp+80h+var_50], rax
0x1800130f1  lea     rax, [rbp+arg_18]
0x1800130f5  mov     [rsp+80h+var_58], rax
0x1800130fa  lea     rax, [rbp+var_10]
0x1800130fe  mov     [rsp+80h+var_60], rax
0x180013103  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013108  mov     rcx, [rbp+var_30]
0x18001310c  test    rcx, rcx
0x18001310f  jz      loc_18001303E
0x180013115  mov     rax, [rcx]
0x180013118  mov     rax, [rax+10h]
0x18001311c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013121  mov     [rbp+var_30], r14
0x180013125  jmp     loc_18001303E
0x18001312a  mov     rcx, [rbp+var_30]
0x18001312e  lea     rdx, [rbp+var_28]
0x180013132  mov     [rbp+var_28], r14
0x180013136  mov     rax, [rcx]
0x180013139  mov     rax, [rax+30h]
0x18001313d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013142  mov     edi, eax
0x180013144  test    eax, eax
0x180013146  jns     loc_1800131D3
0x18001314c  mov     ecx, cs:dword_180069000
0x180013152  cmp     ecx, 2
0x180013155  jbe     short loc_1800131B1
0x180013157  mov     rdx, cs:qword_180069018
0x18001315e  mov     rcx, cs:qword_180069010
0x180013165  test    cl, 8
0x180013168  jz      short loc_1800131B1
0x18001316a  mov     rax, rdx
0x18001316d  and     eax, 8
0x180013170  cmp     rax, rdx
0x180013173  jnz     short loc_1800131B1
0x180013175  lea     rax, aOnecoreXboxGam_17; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x18001317c  mov     [rbp+arg_10], edi
0x18001317f  mov     [rbp+var_10], rax
0x180013183  lea     rdx, byte_18005A651
0x18001318a  lea     rax, [rbp+arg_10]
0x18001318e  mov     [rbp+arg_18], 6Dh ; 'm'
0x180013195  mov     [rsp+80h+var_50], rax
0x18001319a  lea     rax, [rbp+arg_18]
0x18001319e  mov     [rsp+80h+var_58], rax
0x1800131a3  lea     rax, [rbp+var_10]
0x1800131a7  mov     [rsp+80h+var_60], rax
0x1800131ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800131b1  mov     rcx, [rbp+var_28]
0x1800131b5  test    rcx, rcx
0x1800131b8  jz      loc_180013108
0x1800131be  mov     rax, [rcx]
0x1800131c1  mov     rax, [rax+10h]
0x1800131c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131ca  mov     [rbp+var_28], r14
0x1800131ce  jmp     loc_180013108
0x1800131d3  mov     rcx, [rbp+var_28]
0x1800131d7  lea     r8, [rbp+var_20]
0x1800131db  mov     [rbp+var_20], r14
0x1800131df  lea     rdx, _GUID_c3542377_1ea7_4454_8deb_8aa6070db645
0x1800131e6  mov     rax, [rcx]
0x1800131e9  mov     rax, [rax]
0x1800131ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131f1  mov     edi, eax
0x1800131f3  test    eax, eax
0x1800131f5  jns     loc_180013282
0x1800131fb  mov     ecx, cs:dword_180069000
0x180013201  cmp     ecx, 2
0x180013204  jbe     short loc_180013260
0x180013206  mov     rdx, cs:qword_180069018
0x18001320d  mov     rcx, cs:qword_180069010
0x180013214  test    cl, 8
0x180013217  jz      short loc_180013260
0x180013219  mov     rax, rdx
0x18001321c  and     eax, 8
0x18001321f  cmp     rax, rdx
0x180013222  jnz     short loc_180013260
0x180013224  mov     [rbp+arg_18], 70h ; 'p'
0x18001322b  lea     rdx, word_18005D76E
0x180013232  lea     rax, aOnecoreXboxGam_17; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180013239  mov     [rbp+var_10], rax
0x18001323d  lea     rax, [rbp+arg_10]
0x180013241  mov     [rsp+80h+var_50], rax
0x180013246  lea     rax, [rbp+arg_18]
  ... truncated ...
```
