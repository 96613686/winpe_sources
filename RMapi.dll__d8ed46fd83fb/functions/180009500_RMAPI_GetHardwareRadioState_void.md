# RMAPI::GetHardwareRadioState(void)

- ea: `0x180009500`
- end: `0x18000960d`
- name: `?GetHardwareRadioState@RMAPI@@YA?AW4SliderPosition@@XZ`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800233a4`

## callees

- `0x1800035b0`
- `0x1800042b0`
- `0x1800088e0`
- `0x180009500`
- `0x18000d2a0`
- `0x18000df4c`
- `0x180024ac0`
- `0x180024b00`

## string_xrefs

- `0x180009582`: `ReadSwitchState failed to read AB_Switch state - returning NoSlider`

## pseudocode

```c
__int64 RMAPI::GetHardwareRadioState()
{
  unsigned int v0; // ebx
  __int64 v1; // r8
  __int64 v2; // r9
  unsigned int SwitchState; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned __int8 v7[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v8; // [rsp+34h] [rbp-CCh] BYREF
  const wchar_t *v9; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v10[608]; // [rsp+40h] [rbp-C0h] BYREF

  v0 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( (unsigned __int8)SearchHidDevicesForRadioFeature(4u, (__int64)v10) )
  {
    v7[0] = 0;
    SwitchState = ReadSwitchState((__int64)v10, 4, v7);
    if ( SwitchState == 1114112 )
    {
      v0 = 2 - (v7[0] != 0);
    }
    else if ( (unsigned int)dword_180037050 > 4 )
    {
      v8 = SwitchState;
      v9 = (const wchar_t *)"ReadSwitchState failed to read AB_Switch state - returning NoSlider";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        SwitchState,
        (unsigned __int8 *)&unk_180030440,
        v4,
        v5,
        &v9,
        (__int64)&v8);
    }
    RadioHidDeviceFree((__int64)v10);
  }
  else if ( (unsigned int)dword_180037050 > 4 )
  {
    v9 = (const wchar_t *)"SearchHidDevicesForRadioFeature didn't find an RFT_AB_SWITCH - returning NoSlider";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)dword_180037050,
      (unsigned __int8 *)byte_180030407,
      v1,
      v2,
      &v9);
  }
  return v0;
}

```

## disassembly

```asm
0x180009500  mov     [rsp-8+arg_0], rbx
0x180009505  push    rbp
0x180009506  lea     rbp, [rsp-1B0h]
0x18000950e  sub     rsp, 2B0h
0x180009515  mov     rax, cs:__security_cookie
0x18000951c  xor     rax, rsp
0x18000951f  mov     [rbp+1B0h+var_10], rax
0x180009526  xor     edx, edx; Val
0x180009528  lea     rcx, [rsp+2B0h+var_270]; void *
0x18000952d  mov     r8d, 260h; Size
0x180009533  xor     ebx, ebx
0x180009535  call    memset_0
0x18000953a  lea     rdx, [rsp+2B0h+var_270]
0x18000953f  lea     ecx, [rbx+4]
0x180009542  call    SearchHidDevicesForRadioFeature
0x180009547  test    al, al
0x180009549  jz      short loc_1800095BE
0x18000954b  lea     r8, [rsp+2B0h+var_280]
0x180009550  mov     [rsp+2B0h+var_280], bl
0x180009554  lea     edx, [rbx+4]
0x180009557  lea     rcx, [rsp+2B0h+var_270]
0x18000955c  call    ReadSwitchState
0x180009561  mov     ecx, eax
0x180009563  cmp     eax, 110000h
0x180009568  jnz     short loc_180009577
0x18000956a  mov     al, [rsp+2B0h+var_280]
0x18000956e  neg     al
0x180009570  sbb     ebx, ebx
0x180009572  add     ebx, 2
0x180009575  jmp     short loc_1800095B2
0x180009577  mov     eax, cs:dword_180037050
0x18000957d  cmp     eax, 4
0x180009580  jbe     short loc_1800095B2
0x180009582  lea     rax, aReadswitchstat; "ReadSwitchState failed to read AB_Switc"...
0x180009589  mov     [rsp+2B0h+var_27C], ecx
0x18000958d  mov     [rsp+2B0h+var_278], rax
0x180009592  lea     rdx, unk_180030440
0x180009599  lea     rax, [rsp+2B0h+var_27C]
0x18000959e  mov     [rsp+2B0h+var_288], rax
0x1800095a3  lea     rax, [rsp+2B0h+var_278]
0x1800095a8  mov     [rsp+2B0h+var_290], rax
0x1800095ad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800095b2  lea     rcx, [rsp+2B0h+var_270]
0x1800095b7  call    RadioHidDeviceFree
0x1800095bc  jmp     short loc_1800095EB
0x1800095be  mov     ecx, cs:dword_180037050
0x1800095c4  cmp     ecx, 4
0x1800095c7  jbe     short loc_1800095EB
0x1800095c9  lea     rax, aSearchhiddevic; "SearchHidDevicesForRadioFeature didn't "...
0x1800095d0  mov     [rsp+2B0h+var_278], rax
0x1800095d5  lea     rdx, byte_180030407
0x1800095dc  lea     rax, [rsp+2B0h+var_278]
0x1800095e1  mov     [rsp+2B0h+var_290], rax
0x1800095e6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800095eb  mov     eax, ebx
0x1800095ed  mov     rcx, [rbp+1B0h+var_10]
0x1800095f4  xor     rcx, rsp; StackCookie
0x1800095f7  call    __security_check_cookie
0x1800095fc  mov     rbx, [rsp+2B0h+arg_0]
0x180009604  add     rsp, 2B0h
0x18000960b  pop     rbp
0x18000960c  retn
```
