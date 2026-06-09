# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400018f4`
- end: `0x140001987`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140016320`
- `0x140016520`

## callees

- `0x1400010f4`
- `0x14001adc0`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-68h] BYREF
  __int64 v9; // [rsp+50h] [rbp-48h]
  __int64 v10; // [rsp+58h] [rbp-40h]
  __int64 v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  __int64 v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  v13 = a7;
  v11 = a6;
  v9 = a5;
  v14 = 4;
  v12 = 4;
  v10 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140022000, a2, 0, 0, 5u, &v8);
}

```

## disassembly

```asm
0x1400018f4  mov     r11, rsp
0x1400018f7  sub     rsp, 98h
0x1400018fe  mov     rax, cs:__security_cookie
0x140001905  xor     rax, rsp
0x140001908  mov     [rsp+98h+var_18], rax
0x140001910  mov     rax, [rsp+98h+arg_30]
0x140001918  lea     rcx, dword_140022000
0x14000191f  mov     [r11-28h], rax
0x140001923  xor     r9d, r9d
0x140001926  mov     rax, [rsp+98h+arg_28]
0x14000192e  xor     r8d, r8d
0x140001931  mov     [r11-38h], rax
0x140001935  mov     rax, [rsp+98h+arg_20]
0x14000193d  mov     [r11-48h], rax
0x140001941  lea     rax, [r11-68h]
0x140001945  mov     [r11-70h], rax
0x140001949  mov     [rsp+98h+var_78], 5
0x140001951  mov     qword ptr [r11-20h], 4
0x140001959  mov     qword ptr [r11-30h], 4
0x140001961  mov     qword ptr [r11-40h], 8
0x140001969  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000196e  mov     rcx, [rsp+98h+var_18]
0x140001976  xor     rcx, rsp; StackCookie
0x140001979  call    __security_check_cookie
0x14000197e  add     rsp, 98h
0x140001985  retn
```
