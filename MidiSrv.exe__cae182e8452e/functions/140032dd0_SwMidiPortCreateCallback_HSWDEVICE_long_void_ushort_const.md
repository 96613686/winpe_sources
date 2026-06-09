# SwMidiPortCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x140032dd0`
- end: `0x140032fee`
- name: `?SwMidiPortCreateCallback@@YAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `542`
- prototype: `void __fastcall(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002b1a0`

## callees

- `0x140001f28`
- `0x14000298c`
- `0x14000984c`
- `0x14000c55c`
- `0x140032dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140032fb9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140032fb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140032f14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140032f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032f01`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x140032edc`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x140032edc`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x140032f0c`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x140032f0c`

## string_xrefs

- `0x140032e04`: `SwMidiPortCreateCallback`

## pseudocode

```c
void __fastcall SwMidiPortCreateCallback(struct HSWDEVICE__ *a1, int a2, unsigned int *a3, const unsigned __int16 *a4)
{
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rax
  _QWORD *v14; // rsi
  __int64 v15; // r15
  __int64 v16; // r14
  DWORD LastError; // ebx
  _DWORD *v18; // r8
  __int64 v19; // r9
  const char *v20; // rcx
  __int64 v21; // r8
  const char *v22; // r9
  const char *v23; // [rsp+50h] [rbp-9h] BYREF
  const wchar_t *v24; // [rsp+58h] [rbp-1h] BYREF
  const wchar_t *v25; // [rsp+60h] [rbp+7h] BYREF
  const char *v26; // [rsp+68h] [rbp+Fh] BYREF
  _QWORD *v27; // [rsp+70h] [rbp+17h]
  __int64 v28; // [rsp+78h] [rbp+1Fh] BYREF
  char v29; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v31; // [rsp+D0h] [rbp+77h] BYREF

  if ( a3 )
  {
    v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v7 > 4u )
    {
      LODWORD(v31) = a3[6];
      v10 = (const char *)(*(_QWORD *)a3 + 48LL);
      if ( *(_QWORD *)(*(_QWORD *)a3 + 72LL) > 7u )
        v10 = *(const char **)v10;
      v23 = v10;
      v25 = 0;
      v24 = L"Enter";
      v26 = "SwMidiPortCreateCallback";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v7,
        (__int64)byte_140089CA3,
        v8,
        v9,
        &v26,
        (__int64)&v25,
        &v24,
        &v23);
    }
    *(_DWORD *)(*(_QWORD *)a3 + 16LL) = 3;
    *(_DWORD *)(*(_QWORD *)a3 + 192LL) = a2;
    v11 = *(_QWORD *)a3;
    if ( *(int *)(*(_QWORD *)a3 + 192LL) >= 0 )
    {
      v12 = a3[6];
      v27 = (_QWORD *)(v11 + 40);
      v28 = 0;
      v13 = *((_QWORD *)a3 + 2);
      v29 = 1;
      *(_DWORD *)(*(_QWORD *)a3 + 192LL) = SwDeviceInterfaceRegister(a1, *(_QWORD *)(v11 + 8), 0, v12, v13, 1, &v28);
      if ( v29 )
      {
        v14 = v27;
        v15 = v28;
        v16 = *v27;
        if ( *v27 )
        {
          LastError = GetLastError();
          SwMemFree(v16);
          SetLastError(LastError);
        }
        *v14 = v15;
      }
    }
    if ( *(int *)(*(_QWORD *)a3 + 192LL) >= 0 )
    {
      *(_DWORD *)(*(_QWORD *)a3 + 16LL) = 2;
      v18 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v18 > 4u )
      {
        v20 = (const char *)(*(_QWORD *)a3 + 48LL);
        v31 = *(_QWORD *)(*(_QWORD *)a3 + 40LL);
        if ( *((_QWORD *)v20 + 3) > 7u )
          v20 = *(const char **)v20;
        v26 = v20;
        v25 = L"Creation succeeded";
        v24 = 0;
        v23 = "SwMidiPortCreateCallback";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (__int64)v18,
          (__int64)&byte_1400890E7,
          (__int64)v18,
          v19,
          &v23,
          (__int64)&v24,
          &v25,
          &v26,
          &v31);
      }
    }
    if ( !SetEvent(*((HANDLE *)a3 + 1)) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v21, v22);
  }
}

```

## disassembly

```asm
0x140032dd0  test    r8, r8
0x140032dd3  jz      locret_140032FDE
0x140032dd9  mov     [rsp-8+arg_0], rbx
0x140032dde  mov     [rsp-8+arg_8], rsi
0x140032de3  push    rbp
0x140032de4  push    rdi
0x140032de5  push    r13
0x140032de7  push    r14
0x140032de9  push    r15
0x140032deb  lea     rbp, [rsp-37h]
0x140032df0  sub     rsp, 90h
0x140032df7  mov     rdi, r8
0x140032dfa  mov     esi, edx
0x140032dfc  mov     r14, rcx
0x140032dff  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140032e04  lea     r13, aSwmidiportcrea; "SwMidiPortCreateCallback"
0x140032e0b  mov     rcx, [rax+8]
0x140032e0f  mov     eax, [rcx]
0x140032e11  cmp     eax, 4
0x140032e14  jbe     short loc_140032E81
0x140032e16  mov     eax, [rdi+18h]
0x140032e19  mov     dword ptr [rbp+57h+arg_10], eax
0x140032e1c  mov     rax, [rdi]
0x140032e1f  add     rax, 30h ; '0'
0x140032e23  cmp     qword ptr [rax+18h], 7
0x140032e28  jbe     short loc_140032E2D
0x140032e2a  mov     rax, [rax]
0x140032e2d  mov     [rbp+57h+var_60], rax
0x140032e31  lea     rdx, byte_140089CA3
0x140032e38  lea     rax, aEnter; "Enter"
0x140032e3f  mov     [rbp+57h+var_50], 0
0x140032e47  mov     [rbp+57h+var_58], rax
0x140032e4b  lea     rax, [rbp+57h+arg_10]
0x140032e4f  mov     [rsp+0B0h+var_70], rax
0x140032e54  lea     rax, [rbp+57h+var_60]
0x140032e58  mov     [rsp+0B0h+var_78], rax
0x140032e5d  lea     rax, [rbp+57h+var_58]
0x140032e61  mov     [rsp+0B0h+var_80], rax
0x140032e66  lea     rax, [rbp+57h+var_50]
0x140032e6a  mov     [rsp+0B0h+var_88], rax
0x140032e6f  lea     rax, [rbp+57h+var_48]
0x140032e73  mov     [rsp+0B0h+var_90], rax
0x140032e78  mov     [rbp+57h+var_48], r13
0x140032e7c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x140032e81  mov     rax, [rdi]
0x140032e84  mov     dword ptr [rax+10h], 3
0x140032e8b  mov     rax, [rdi]
0x140032e8e  mov     [rax+0C0h], esi
0x140032e94  mov     rdx, [rdi]
0x140032e97  cmp     dword ptr [rdx+0C0h], 0
0x140032e9e  jl      short loc_140032F1D
0x140032ea0  mov     r9d, [rdi+18h]
0x140032ea4  lea     rax, [rdx+28h]
0x140032ea8  mov     [rbp+57h+var_40], rax
0x140032eac  xor     r8d, r8d
0x140032eaf  lea     rax, [rbp+57h+var_38]
0x140032eb3  mov     [rbp+57h+var_38], 0
0x140032ebb  mov     [rsp+0B0h+var_80], rax
0x140032ec0  mov     rcx, r14
0x140032ec3  mov     rax, [rdi+10h]
0x140032ec7  mov     [rbp+57h+var_30], 1
0x140032ecb  mov     rdx, [rdx+8]
0x140032ecf  mov     dword ptr [rsp+0B0h+var_88], 1
0x140032ed7  mov     [rsp+0B0h+var_90], rax
0x140032edc  call    cs:__imp_SwDeviceInterfaceRegister
0x140032ee2  mov     rcx, [rdi]
0x140032ee5  mov     [rcx+0C0h], eax
0x140032eeb  cmp     [rbp+57h+var_30], 0
0x140032eef  jz      short loc_140032F1D
0x140032ef1  mov     rsi, [rbp+57h+var_40]
0x140032ef5  mov     r15, [rbp+57h+var_38]
0x140032ef9  mov     r14, [rsi]
0x140032efc  test    r14, r14
0x140032eff  jz      short loc_140032F1A
0x140032f01  call    cs:__imp_GetLastError
0x140032f07  mov     rcx, r14
0x140032f0a  mov     ebx, eax
0x140032f0c  call    cs:__imp_SwMemFree
0x140032f12  mov     ecx, ebx; dwErrCode
0x140032f14  call    cs:__imp_SetLastError
0x140032f1a  mov     [rsi], r15
0x140032f1d  mov     rax, [rdi]
0x140032f20  cmp     dword ptr [rax+0C0h], 0
0x140032f27  jl      loc_140032FB5
0x140032f2d  mov     dword ptr [rax+10h], 2
0x140032f34  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140032f39  mov     r8, [rax+8]
0x140032f3d  mov     eax, [r8]
0x140032f40  cmp     eax, 4
0x140032f43  jbe     short loc_140032FB5
0x140032f45  mov     rcx, [rdi]
0x140032f48  mov     rax, [rcx+28h]
0x140032f4c  add     rcx, 30h ; '0'
0x140032f50  mov     [rbp+57h+arg_10], rax
0x140032f54  cmp     qword ptr [rcx+18h], 7
0x140032f59  jbe     short loc_140032F5E
0x140032f5b  mov     rcx, [rcx]
0x140032f5e  lea     rax, aCreationSuccee; "Creation succeeded"
0x140032f65  mov     [rbp+57h+var_48], rcx
0x140032f69  mov     [rbp+57h+var_50], rax
0x140032f6d  lea     rdx, byte_1400890E7
0x140032f74  lea     rax, [rbp+57h+arg_10]
0x140032f78  mov     [rbp+57h+var_58], 0
0x140032f80  mov     [rsp+0B0h+var_70], rax
0x140032f85  mov     rcx, r8
0x140032f88  lea     rax, [rbp+57h+var_48]
0x140032f8c  mov     [rbp+57h+var_60], r13
0x140032f90  mov     [rsp+0B0h+var_78], rax
0x140032f95  lea     rax, [rbp+57h+var_50]
0x140032f99  mov     [rsp+0B0h+var_80], rax
0x140032f9e  lea     rax, [rbp+57h+var_58]
0x140032fa2  mov     [rsp+0B0h+var_88], rax
0x140032fa7  lea     rax, [rbp+57h+var_60]
0x140032fab  mov     [rsp+0B0h+var_90], rax
0x140032fb0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140032fb5  mov     rcx, [rdi+8]; hEvent
0x140032fb9  call    cs:__imp_SetEvent
0x140032fbf  test    eax, eax
0x140032fc1  jz      short loc_140032FDF
0x140032fc3  lea     r11, [rsp+0B0h+var_20]
0x140032fcb  mov     rbx, [r11+30h]
0x140032fcf  mov     rsi, [r11+38h]
0x140032fd3  mov     rsp, r11
0x140032fd6  pop     r15
0x140032fd8  pop     r14
0x140032fda  pop     r13
0x140032fdc  pop     rdi
0x140032fdd  pop     rbp
0x140032fde  retn
0x140032fdf  mov     rcx, [rbp+5Fh]; this
0x140032fe3  mov     edx, 0A01h; void *
0x140032fe8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
