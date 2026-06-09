# Windows::UI::Input::Preview::Injection::WriteKeyboardTelemetry(Windows::UI::Input::Preview::Injection::KeyboardTelemetry &)

- ea: `0x180010858`
- end: `0x180010918`
- name: `?WriteKeyboardTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUKeyboardTelemetry@12345@@Z`
- size: `192`
- prototype: `void __fastcall(Windows::UI::Input::Preview::Injection *this, struct Windows::UI::Input::Preview::Injection::KeyboardTelemetry *, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c10`

## callees

- `0x18000116c`
- `0x180010858`

## pseudocode

```c
void __fastcall Windows::UI::Input::Preview::Injection::WriteKeyboardTelemetry(
        Windows::UI::Input::Preview::Injection *this,
        struct Windows::UI::Input::Preview::Injection::KeyboardTelemetry *a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // [rsp+60h] [rbp-20h] BYREF
  int v5; // [rsp+64h] [rbp-1Ch] BYREF
  int v6; // [rsp+68h] [rbp-18h] BYREF
  const char *v7; // [rsp+70h] [rbp-10h] BYREF
  int v8; // [rsp+98h] [rbp+18h] BYREF
  int v9; // [rsp+A0h] [rbp+20h] BYREF
  int v10; // [rsp+A8h] [rbp+28h] BYREF

  if ( (unsigned int)dword_180022000 > 5
    && (qword_180022010 & 0x400000000000LL) != 0
    && (qword_180022018 & 0x400000000000LL) == qword_180022018 )
  {
    v8 = *((_DWORD *)this + 5);
    v9 = *((_DWORD *)this + 2);
    v10 = *((_DWORD *)this + 4);
    v4 = *((_DWORD *)this + 1);
    v5 = *(_DWORD *)this;
    v6 = *((_DWORD *)this + 3);
    v7 = "InjectKeyboard";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)byte_18001E951,
      0x400000000000LL,
      a4,
      (const unsigned __int16 **)&v7,
      (__int64)&v6,
      (__int64)&v5,
      (__int64)&v4,
      (__int64)&v10,
      (__int64)&v9,
      (__int64)&v8);
  }
}

```

## disassembly

```asm
0x180010858  mov     r11, rsp
0x18001085b  push    rbp
0x18001085c  mov     rbp, rsp
0x18001085f  sub     rsp, 80h
0x180010866  mov     eax, cs:dword_180022000
0x18001086c  cmp     eax, 5
0x18001086f  jbe     loc_18001090F
0x180010875  mov     rdx, cs:qword_180022018
0x18001087c  mov     r8, 400000000000h
0x180010886  mov     rax, cs:qword_180022010
0x18001088d  test    r8, rax
0x180010890  jz      short loc_18001090F
0x180010892  mov     rax, rdx
0x180010895  and     rax, r8
0x180010898  cmp     rax, rdx
0x18001089b  jnz     short loc_18001090F
0x18001089d  mov     eax, [rcx+14h]
0x1800108a0  lea     rdx, byte_18001E951
0x1800108a7  mov     [rbp+arg_8], eax
0x1800108aa  mov     eax, [rcx+8]
0x1800108ad  mov     [rbp+arg_10], eax
0x1800108b0  mov     eax, [rcx+10h]
0x1800108b3  mov     [rbp+arg_18], eax
0x1800108b6  mov     eax, [rcx+4]
0x1800108b9  mov     [rbp+var_20], eax
0x1800108bc  mov     eax, [rcx]
0x1800108be  mov     [rbp+var_1C], eax
0x1800108c1  mov     eax, [rcx+0Ch]
0x1800108c4  mov     [rbp+var_18], eax
0x1800108c7  lea     rax, aInjectkeyboard; "InjectKeyboard"
0x1800108ce  mov     [rbp+var_10], rax
0x1800108d2  lea     rax, [rbp+arg_8]
0x1800108d6  mov     [r11-38h], rax
0x1800108da  lea     rax, [rbp+arg_10]
0x1800108de  mov     [r11-40h], rax
0x1800108e2  lea     rax, [rbp+arg_18]
0x1800108e6  mov     [r11-48h], rax
0x1800108ea  lea     rax, [rbp+var_20]
0x1800108ee  mov     [r11-50h], rax
0x1800108f2  lea     rax, [rbp+var_1C]
0x1800108f6  mov     [r11-58h], rax
0x1800108fa  lea     rax, [rbp+var_18]
0x1800108fe  mov     [r11-60h], rax
0x180010902  lea     rax, [rbp+var_10]
0x180010906  mov     [r11-68h], rax
0x18001090a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001090f  add     rsp, 80h
0x180010916  pop     rbp
0x180010917  retn
```
