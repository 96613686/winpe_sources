# HidForceFeedbackBrokerFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180013be0`
- end: `0x180013d40`
- name: `?CreateInstance@HidForceFeedbackBrokerFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `352`
- prototype: `__int64 __fastcall(HidForceFeedbackBrokerFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001304`
- `0x18000f180`
- `0x180013be0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180013c2b`
- `ntdll!RtlAllocateHeap` at `0x180013c2b`

## string_xrefs

- `0x180013c87`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBrokerFactory.cpp`
- `0x180013cff`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBrokerFactory.cpp`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackBrokerFactory::CreateInstance(
        HidForceFeedbackBrokerFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        HidForceFeedbackBroker **a4)
{
  HidForceFeedbackBroker *Heap; // rax
  int v6; // r8d
  int v7; // r9d
  HidForceFeedbackBroker *v8; // rax
  int v10; // [rsp+40h] [rbp-10h] BYREF
  const char *v11; // [rsp+48h] [rbp-8h] BYREF
  int v12; // [rsp+78h] [rbp+28h] BYREF

  *a4 = 0;
  if ( *(_OWORD *)a3 == *(_OWORD *)&GUID_815211c2_e515_4437_a8cc_e93857df54f5 )
  {
    Heap = (HidForceFeedbackBroker *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x30u);
    if ( Heap )
    {
      v8 = HidForceFeedbackBroker::HidForceFeedbackBroker(Heap);
      *a4 = v8;
      if ( v8 )
        return 0;
    }
    else
    {
      *a4 = 0;
    }
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v12 = -2147024882;
      v11 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBrokerFactory.cpp";
      v10 = 13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&v11,
        (unsigned int)&dword_18005C1BC,
        v6,
        v7,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v12);
    }
    return 2147942414LL;
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v12 = -2147221231;
      v10 = 17;
      v11 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBrokerFactory.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBrokerFactory.cpp",
        (unsigned int)&byte_18005E7A7,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v12);
    }
    return 2147746065LL;
  }
}

```

## disassembly

```asm
0x180013be0  mov     [rsp-8+arg_0], rbx
0x180013be5  push    rbp
0x180013be6  mov     rbp, rsp
0x180013be9  sub     rsp, 50h
0x180013bed  mov     qword ptr [r9], 0
0x180013bf4  mov     rbx, r9
0x180013bf7  mov     rax, [r8]
0x180013bfa  cmp     rax, qword ptr cs:_GUID_815211c2_e515_4437_a8cc_e93857df54f5.Data1
0x180013c01  jnz     loc_180013CC7
0x180013c07  mov     rax, [r8+8]
0x180013c0b  cmp     rax, qword ptr cs:_GUID_815211c2_e515_4437_a8cc_e93857df54f5.Data4
0x180013c12  jnz     loc_180013CC7
0x180013c18  mov     rcx, gs:60h
0x180013c21  xor     edx, edx; Flags
0x180013c23  mov     rcx, [rcx+30h]; HeapHandle
0x180013c27  lea     r8d, [rdx+30h]; Size
0x180013c2b  call    cs:__imp_RtlAllocateHeap
0x180013c32  nop     dword ptr [rax+rax+00h]
0x180013c37  test    rax, rax
0x180013c3a  jz      short loc_180013C53
0x180013c3c  mov     rcx, rax; this
0x180013c3f  call    ??0HidForceFeedbackBroker@@QEAA@XZ; HidForceFeedbackBroker::HidForceFeedbackBroker(void)
0x180013c44  mov     [rbx], rax
0x180013c47  test    rax, rax
0x180013c4a  jz      short loc_180013C5A
0x180013c4c  xor     eax, eax
0x180013c4e  jmp     loc_180013D34
0x180013c53  mov     qword ptr [rbx], 0
0x180013c5a  mov     eax, cs:dword_180069000
0x180013c60  mov     ebx, 8007000Eh
0x180013c65  cmp     eax, 2
0x180013c68  jbe     short loc_180013CC3
0x180013c6a  mov     rcx, cs:qword_180069018
0x180013c71  mov     rax, cs:qword_180069010
0x180013c78  test    al, 8
0x180013c7a  jz      short loc_180013CC3
0x180013c7c  mov     rax, rcx
0x180013c7f  and     eax, 8
0x180013c82  cmp     rax, rcx
0x180013c85  jnz     short loc_180013CC3
0x180013c87  lea     rcx, aOnecoreXboxGam_19; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180013c8e  mov     [rbp+arg_18], ebx
0x180013c91  mov     [rbp+var_8], rcx
0x180013c95  lea     rdx, dword_18005C1BC
0x180013c9c  lea     rcx, [rbp+arg_18]
0x180013ca0  mov     [rbp+var_10], 0Dh
0x180013ca7  mov     [rsp+50h+var_20], rcx
0x180013cac  lea     rcx, [rbp+var_10]
0x180013cb0  mov     [rsp+50h+var_28], rcx
0x180013cb5  lea     rcx, [rbp+var_8]
0x180013cb9  mov     [rsp+50h+var_30], rcx
0x180013cbe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013cc3  mov     eax, ebx
0x180013cc5  jmp     short loc_180013D34
0x180013cc7  mov     eax, cs:dword_180069000
0x180013ccd  cmp     eax, 2
0x180013cd0  jbe     short loc_180013D2F
0x180013cd2  mov     rcx, cs:qword_180069018
0x180013cd9  mov     rax, cs:qword_180069010
0x180013ce0  test    al, 8
0x180013ce2  jz      short loc_180013D2F
0x180013ce4  mov     rax, rcx
0x180013ce7  and     eax, 8
0x180013cea  cmp     rax, rcx
0x180013ced  jnz     short loc_180013D2F
0x180013cef  lea     rax, [rbp+arg_18]
0x180013cf3  mov     [rbp+arg_18], 80040111h
0x180013cfa  mov     [rsp+50h+var_20], rax
0x180013cff  lea     rcx, aOnecoreXboxGam_19; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180013d06  lea     rax, [rbp+var_10]
0x180013d0a  mov     [rbp+var_10], 11h
0x180013d11  mov     [rsp+50h+var_28], rax
0x180013d16  lea     rdx, byte_18005E7A7
0x180013d1d  lea     rax, [rbp+var_8]
0x180013d21  mov     [rbp+var_8], rcx
0x180013d25  mov     [rsp+50h+var_30], rax
0x180013d2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013d2f  mov     eax, 80040111h
0x180013d34  mov     rbx, [rsp+50h+arg_0]
0x180013d39  add     rsp, 50h
0x180013d3d  pop     rbp
0x180013d3e  retn
```
