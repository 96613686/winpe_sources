# Windows::UI::Input::Preview::Injection::WriteGamepadTelemetry(Windows::UI::Input::Preview::Injection::GamepadTelemetry &)

- ea: `0x1800107a4`
- end: `0x180010850`
- name: `?WriteGamepadTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUGamepadTelemetry@12345@@Z`
- size: `172`
- prototype: `void __fastcall(Windows::UI::Input::Preview::Injection *this, struct Windows::UI::Input::Preview::Injection::GamepadTelemetry *, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e340`

## callees

- `0x18000108c`
- `0x1800107a4`

## pseudocode

```c
void __fastcall Windows::UI::Input::Preview::Injection::WriteGamepadTelemetry(
        Windows::UI::Input::Preview::Injection *this,
        struct Windows::UI::Input::Preview::Injection::GamepadTelemetry *a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // [rsp+50h] [rbp-10h] BYREF
  int v5; // [rsp+54h] [rbp-Ch] BYREF
  const char *v6; // [rsp+58h] [rbp-8h] BYREF
  int v7; // [rsp+78h] [rbp+18h] BYREF
  int v8; // [rsp+80h] [rbp+20h] BYREF
  int v9; // [rsp+88h] [rbp+28h] BYREF

  if ( (unsigned int)dword_180022000 > 5
    && (qword_180022010 & 0x400000000000LL) != 0
    && (qword_180022018 & 0x400000000000LL) == qword_180022018 )
  {
    v7 = *((_DWORD *)this + 5);
    v8 = *((_DWORD *)this + 4);
    v9 = *((_DWORD *)this + 1);
    v4 = *(_DWORD *)this;
    v5 = *((_DWORD *)this + 3);
    v6 = "InputGamepad";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&unk_18001E810,
      0x400000000000LL,
      a4,
      (const unsigned __int16 **)&v6,
      (__int64)&v5,
      (__int64)&v4,
      (__int64)&v9,
      (__int64)&v8,
      (__int64)&v7);
  }
}

```

## disassembly

```asm
0x1800107a4  mov     r11, rsp
0x1800107a7  push    rbp
0x1800107a8  mov     rbp, rsp
0x1800107ab  sub     rsp, 60h
0x1800107af  mov     eax, cs:dword_180022000
0x1800107b5  cmp     eax, 5
0x1800107b8  jbe     loc_18001084A
0x1800107be  mov     rdx, cs:qword_180022018
0x1800107c5  mov     r8, 400000000000h
0x1800107cf  mov     rax, cs:qword_180022010
0x1800107d6  test    r8, rax
0x1800107d9  jz      short loc_18001084A
0x1800107db  mov     rax, rdx
0x1800107de  and     rax, r8
0x1800107e1  cmp     rax, rdx
0x1800107e4  jnz     short loc_18001084A
0x1800107e6  mov     eax, [rcx+14h]
0x1800107e9  lea     rdx, unk_18001E810
0x1800107f0  mov     [rbp+arg_8], eax
0x1800107f3  mov     eax, [rcx+10h]
0x1800107f6  mov     [rbp+arg_10], eax
0x1800107f9  mov     eax, [rcx+4]
0x1800107fc  mov     [rbp+arg_18], eax
0x1800107ff  mov     eax, [rcx]
0x180010801  mov     [rbp+var_10], eax
0x180010804  mov     eax, [rcx+0Ch]
0x180010807  mov     [rbp+var_C], eax
0x18001080a  lea     rax, aInputgamepad; "InputGamepad"
0x180010811  mov     [rbp+var_8], rax
0x180010815  lea     rax, [rbp+arg_8]
0x180010819  mov     [r11-20h], rax
0x18001081d  lea     rax, [rbp+arg_10]
0x180010821  mov     [r11-28h], rax
0x180010825  lea     rax, [rbp+arg_18]
0x180010829  mov     [r11-30h], rax
0x18001082d  lea     rax, [rbp+var_10]
0x180010831  mov     [r11-38h], rax
0x180010835  lea     rax, [rbp+var_C]
0x180010839  mov     [r11-40h], rax
0x18001083d  lea     rax, [rbp+var_8]
0x180010841  mov     [r11-48h], rax
0x180010845  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001084a  add     rsp, 60h
0x18001084e  pop     rbp
0x18001084f  retn
```
