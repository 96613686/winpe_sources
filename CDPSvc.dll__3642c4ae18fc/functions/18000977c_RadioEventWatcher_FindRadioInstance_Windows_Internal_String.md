# RadioEventWatcher::FindRadioInstance(Windows::Internal::String *)

- ea: `0x18000977c`
- end: `0x1800099a9`
- name: `?FindRadioInstance@RadioEventWatcher@@AEAAJPEAVString@Internal@Windows@@@Z`
- size: `557`
- prototype: `int(RadioEventWatcher *__hidden this, struct Windows::Internal::String *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180017474`

## callees

- `0x18000977c`
- `0x180010964`
- `0x1800109bc`
- `0x1800130ec`
- `0x18001a694`
- `0x180025d9c`
- `0x180025e04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009894`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180009944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180009944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009970`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009970`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180009984`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180009984`

## pseudocode

```c
__int64 __fastcall RadioEventWatcher::FindRadioInstance(RadioEventWatcher *this, HSTRING *a2)
{
  int v3; // eax
  HANDLE EventW; // rax
  HANDLE v5; // rcx
  HANDLE v6; // rbx
  signed int LastError; // eax
  int v8; // ebx
  HSTRING v9; // rcx
  int v11; // [rsp+20h] [rbp-40h]
  void **v12; // [rsp+48h] [rbp-18h] BYREF
  HANDLE v13; // [rsp+50h] [rbp-10h]
  HSTRING *p_string; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  HSTRING string; // [rsp+70h] [rbp+10h] BYREF

  string = (HSTRING)this;
  if ( dword_1800C775C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800C775C);
    if ( dword_1800C775C == -1 )
    {
      xmmword_1800C7170 = *(_OWORD *)&DeviceFinder::FILTER_INTERFACE_ENABLED.Operator;
      xmmword_1800C7180 = xmmword_180073000;
      xmmword_1800C7190 = xmmword_180073010;
      qword_1800C71A0 = (__int64)&DeviceFinder::DEVPROPVALUE_TRUE;
      xmmword_1800C71A8 = xmmword_180072FB8;
      xmmword_1800C71B8 = xmmword_180072FC8;
      xmmword_1800C71C8 = xmmword_180072FD8;
      qword_1800C71D8 = (__int64)&GUID_BTHPORT_DEVICE_INTERFACE;
      Init_thread_footer(&dword_1800C775C);
    }
  }
  string = 0;
  v3 = 2;
  v13 = 0;
  do
  {
    v12 = &Microsoft::WRL::Wrappers::Event::`vftable';
    --v3;
  }
  while ( v3 );
  p_string = &string;
  EventW = CreateEventW(0, 0, 0, 0);
  v5 = v13;
  v6 = EventW;
  if ( EventW == v13 )
  {
    v6 = v13;
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(&v12);
    v5 = v6;
    v13 = v6;
  }
  if ( v6 )
    goto LABEL_14;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 >= 0 )
  {
    v5 = v13;
LABEL_14:
    v8 = DeviceFinder::RunQuery(v5, &xmmword_1800C7170);
    if ( v8 >= 0 )
      v8 = 0;
  }
  v12 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(&v12);
  if ( v8 >= 0 )
  {
    if ( WindowsGetStringLen(string) )
    {
      WindowsDeleteString(*a2);
      v9 = string;
      *a2 = 0;
      v8 = WindowsDuplicateString(v9, a2);
    }
    else
    {
      v8 = -2147023728;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)".\\radioeventwatcher.cpp",
        (const char *)0x80070490LL,
        v11);
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)".\\radioeventwatcher.cpp",
      (const char *)(unsigned int)v8,
      v11);
    if ( string )
      WindowsDeleteString(string);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000977c  mov     [rsp-8+arg_8], rbx
0x180009781  mov     [rsp-8+arg_10], rdi
0x180009786  mov     [rsp-8+string], rcx
0x18000978b  push    rbp
0x18000978c  mov     rbp, rsp
0x18000978f  sub     rsp, 60h
0x180009793  mov     ecx, cs:_tls_index
0x180009799  mov     rdi, rdx
0x18000979c  mov     rax, gs:58h
0x1800097a5  mov     edx, 4
0x1800097aa  mov     rax, [rax+rcx*8]
0x1800097ae  mov     eax, [rdx+rax]
0x1800097b1  cmp     cs:dword_1800C775C, eax
0x1800097b7  jle     loc_180009856
0x1800097bd  lea     rcx, dword_1800C775C
0x1800097c4  call    _Init_thread_header
0x1800097c9  cmp     cs:dword_1800C775C, 0FFFFFFFFh
0x1800097d0  jnz     loc_180009856
0x1800097d6  movups  xmm0, cs:?FILTER_INTERFACE_ENABLED@DeviceFinder@@2U_DEVPROP_FILTER_EXPRESSION@@B; _DEVPROP_FILTER_EXPRESSION const DeviceFinder::FILTER_INTERFACE_ENABLED
0x1800097dd  lea     rcx, dword_1800C775C
0x1800097e4  movups  xmm1, cs:xmmword_180073000
0x1800097eb  movaps  cs:xmmword_1800C7170, xmm0
0x1800097f2  movups  xmm0, cs:xmmword_180073010
0x1800097f9  movaps  cs:xmmword_1800C7180, xmm1
0x180009800  movsd   xmm1, cs:off_180073020
0x180009808  movaps  cs:xmmword_1800C7190, xmm0
0x18000980f  movups  xmm0, cs:xmmword_180072FB8
0x180009816  movsd   cs:qword_1800C71A0, xmm1
0x18000981e  movups  xmm1, cs:xmmword_180072FC8
0x180009825  movups  cs:xmmword_1800C71A8, xmm0
0x18000982c  movups  xmm0, cs:xmmword_180072FD8
0x180009833  movups  cs:xmmword_1800C71B8, xmm1
0x18000983a  movsd   xmm1, cs:off_180072FE8
0x180009842  movups  cs:xmmword_1800C71C8, xmm0
0x180009849  movsd   cs:qword_1800C71D8, xmm1
0x180009851  call    _Init_thread_footer
0x180009856  mov     [rbp+string], 0
0x18000985e  mov     eax, 2
0x180009863  mov     [rbp+var_20], 0
0x18000986a  mov     [rbp+var_10], 0
0x180009872  lea     rcx, ??_7Event@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::Event::`vftable'
0x180009879  mov     [rbp+var_18], rcx
0x18000987d  sub     eax, 1
0x180009880  jnz     short loc_180009872
0x180009882  lea     rax, [rbp+string]
0x180009886  xor     r9d, r9d; lpName
0x180009889  xor     r8d, r8d; bInitialState
0x18000988c  mov     [rbp+var_8], rax
0x180009890  xor     edx, edx; bManualReset
0x180009892  xor     ecx, ecx; lpEventAttributes
0x180009894  call    cs:__imp_CreateEventW
0x18000989a  mov     rcx, [rbp+var_10]
0x18000989e  mov     rbx, rax
0x1800098a1  cmp     rax, rcx
0x1800098a4  jz      short loc_1800098B8
0x1800098a6  lea     rcx, [rbp+var_18]
0x1800098aa  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x1800098af  mov     rcx, rbx
0x1800098b2  mov     [rbp+var_10], rbx
0x1800098b6  jmp     short loc_1800098BB
0x1800098b8  mov     rbx, rcx
0x1800098bb  test    rbx, rbx
0x1800098be  jnz     short loc_1800098DD
0x1800098c0  call    cs:__imp_GetLastError
0x1800098c6  mov     ebx, eax
0x1800098c8  test    eax, eax
0x1800098ca  jle     short loc_1800098D5
0x1800098cc  movzx   ebx, ax
0x1800098cf  or      ebx, 80070000h
0x1800098d5  test    ebx, ebx
0x1800098d7  js      short loc_1800098FF
0x1800098d9  mov     rcx, [rbp+var_10]
0x1800098dd  lea     rax, [rbp+var_20]
0x1800098e1  mov     [rsp+60h+var_28], rcx
0x1800098e6  lea     rdx, xmmword_1800C7170
0x1800098ed  mov     [rsp+60h+var_30], rax
0x1800098f2  call    ?RunQuery@DeviceFinder@@SAJW4_DEV_OBJECT_TYPE@@PEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@KP6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z44@Z; DeviceFinder::RunQuery(_DEV_OBJECT_TYPE,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,ulong,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),void *,void *)
0x1800098f7  test    eax, eax
0x1800098f9  mov     ebx, eax
0x1800098fb  cmovns  ebx, [rbp+var_20]
0x1800098ff  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180009906  lea     rcx, [rbp+var_18]
0x18000990a  mov     [rbp+var_18], rax
0x18000990e  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x180009913  test    ebx, ebx
0x180009915  jns     short loc_180009940
0x180009917  mov     rcx, [rbp+8]; this
0x18000991b  lea     r8, aRadioeventwatc; ".\\radioeventwatcher.cpp"
0x180009922  mov     r9d, ebx; char *
0x180009925  mov     edx, 0EAh; void *
0x18000992a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000992f  mov     rcx, [rbp+string]; string
0x180009933  test    rcx, rcx
0x180009936  jz      short loc_180009995
0x180009938  call    cs:__imp_WindowsDeleteString
0x18000993e  jmp     short loc_180009995
0x180009940  mov     rcx, [rbp+string]; string
0x180009944  call    cs:__imp_WindowsGetStringLen
0x18000994a  test    eax, eax
0x18000994c  jnz     short loc_18000996D
0x18000994e  mov     rcx, [rbp+8]; this
0x180009952  lea     r8, aRadioeventwatc; ".\\radioeventwatcher.cpp"
0x180009959  mov     ebx, 80070490h
0x18000995e  mov     edx, 0EFh; void *
0x180009963  mov     r9d, ebx; char *
0x180009966  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000996b  jmp     short loc_18000998C
0x18000996d  mov     rcx, [rdi]; string
0x180009970  call    cs:__imp_WindowsDeleteString
0x180009976  mov     rcx, [rbp+string]; string
0x18000997a  mov     rdx, rdi; newString
0x18000997d  mov     qword ptr [rdi], 0
0x180009984  call    cs:__imp_WindowsDuplicateString
0x18000998a  mov     ebx, eax
0x18000998c  lea     rcx, [rbp+string]; this
0x180009990  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180009995  lea     r11, [rsp+60h+var_s0]
0x18000999a  mov     eax, ebx
0x18000999c  mov     rbx, [r11+18h]
0x1800099a0  mov     rdi, [r11+20h]
0x1800099a4  mov     rsp, r11
0x1800099a7  pop     rbp
0x1800099a8  retn
```
