# CMidi2SchedulerMidiTransform::SendMidiMessageNow(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x18000b964`
- end: `0x18000ba5e`
- name: `?SendMidiMessageNow@CMidi2SchedulerMidiTransform@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000af80`
- `0x18000b540`

## callees

- `0x1800016dc`
- `0x180007864`
- `0x1800096d8`
- `0x18000b964`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CMidi2SchedulerMidiTransform::SendMidiMessageNow(
        _QWORD *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  __int64 result; // rax
  _DWORD *v11; // rcx
  int v12; // r9d
  _QWORD *v13; // rax
  _DWORD *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  int v19; // [rsp+20h] [rbp-48h]
  int v20; // [rsp+20h] [rbp-48h]
  _QWORD *v21; // [rsp+40h] [rbp-28h] BYREF
  const char *v22; // [rsp+48h] [rbp-20h] BYREF
  _QWORD *v23; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v24[2]; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  _QWORD *v26; // [rsp+70h] [rbp+8h] BYREF

  v26 = a1;
  try
  {
    v6 = a1[15];
    if ( v6 && a3 )
    {
      v20 = a5;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 24LL))(v6, a2);
      v9 = v7;
      if ( v7 >= 0 )
      {
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC5,
          (unsigned int)"avcore\\midi2\\transform\\schedulertransform\\midi2.schedulermiditransform.cpp",
          (const char *)(unsigned int)v7,
          v20);
        result = v9;
      }
    }
    else
    {
      v11 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
      if ( *v11 > 2u )
      {
        v13 = a1 + 2;
        if ( a1[5] > 7u )
          v13 = (_QWORD *)*v13;
        v21 = v13;
        v22 = (const char *)L"Callback or data is nullptr";
        v23 = a1;
        v24[0] = "CMidi2SchedulerMidiTransform::SendMidiMessageNow";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v11,
          (unsigned int)word_1800118E2,
          v8,
          v12,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v21);
      }
      result = 2147500037LL;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xDB, v8, (const char *)0x80004005LL, v19);
    v14 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
    if ( *v14 > 2u )
    {
      v17 = v26;
      v18 = v26 + 2;
      if ( v26[5] > 7u )
        v18 = (_QWORD *)*v18;
      v26 = v18;
      v24[0] = L"Exception sending MIDI Message";
      v23 = v17;
      v22 = "CMidi2SchedulerMidiTransform::SendMidiMessageNow";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v14,
        (unsigned int)byte_18001188B,
        v15,
        v16,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)v24,
        (__int64)&v26);
    }
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000b964  mov     [rsp+arg_0], rcx
0x18000b969  push    rbx
0x18000b96a  sub     rsp, 60h
0x18000b96e  mov     r10d, edx
0x18000b971  mov     rbx, rcx
0x18000b974  mov     rcx, [rcx+78h]
0x18000b978  test    rcx, rcx
0x18000b97b  jz      short loc_18000B9D7
0x18000b97d  test    r8, r8
0x18000b980  jz      short loc_18000B9D7
0x18000b982  mov     rax, [rcx]
0x18000b985  mov     rdx, [rbx+80h]
0x18000b98c  mov     [rsp+68h+var_40], rdx
0x18000b991  mov     rdx, qword ptr [rsp+68h+arg_20]
0x18000b999  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18000b99e  mov     edx, r10d
0x18000b9a1  mov     rax, [rax+18h]
0x18000b9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9aa  mov     ebx, eax
0x18000b9ac  test    eax, eax
0x18000b9ae  jns     short loc_18000B9D0
0x18000b9b0  mov     rcx, [rsp+68h]; this
0x18000b9b5  mov     r9d, eax; char *
0x18000b9b8  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transform\\schedulertran"...
0x18000b9bf  mov     edx, 0C5h; void *
0x18000b9c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9c9  mov     eax, ebx
0x18000b9cb  jmp     loc_18000BA57
0x18000b9d0  xor     eax, eax
0x18000b9d2  jmp     loc_18000BA57
0x18000b9d7  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000b9dc  mov     rcx, [rax+8]
0x18000b9e0  mov     eax, [rcx]
0x18000b9e2  cmp     eax, 2
0x18000b9e5  jbe     short loc_18000BA4B
0x18000b9e7  lea     rax, [rbx+10h]
0x18000b9eb  cmp     qword ptr [rax+18h], 7
0x18000b9f0  jbe     short loc_18000B9F5
0x18000b9f2  mov     rax, [rax]
0x18000b9f5  mov     [rsp+68h+var_28], rax
0x18000b9fa  lea     rax, aCallbackOrData; "Callback or data is nullptr"
0x18000ba01  mov     [rsp+68h+var_20], rax
0x18000ba06  mov     [rsp+68h+var_18], rbx
0x18000ba0b  lea     rax, aCmidi2schedule_6; "CMidi2SchedulerMidiTransform::SendMidiM"...
0x18000ba12  mov     [rsp+68h+var_10], rax
0x18000ba17  lea     rax, [rsp+68h+var_28]
0x18000ba1c  mov     [rsp+68h+var_30], rax
0x18000ba21  lea     rax, [rsp+68h+var_20]
0x18000ba26  mov     [rsp+68h+var_38], rax
0x18000ba2b  lea     rax, [rsp+68h+var_18]
0x18000ba30  mov     [rsp+68h+var_40], rax
0x18000ba35  lea     rax, [rsp+68h+var_10]
0x18000ba3a  mov     qword ptr [rsp+68h+var_48], rax
0x18000ba3f  lea     rdx, word_1800118E2
0x18000ba46  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000ba4b  mov     eax, 80004005h
0x18000ba50  jmp     short loc_18000BA57
0x18000ba52  mov     eax, 80004005h
0x18000ba57  add     rsp, 60h
0x18000ba5b  pop     rbx
0x18000ba5c  retn
```
