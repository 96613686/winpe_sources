# Windows::UI::Input::Preview::Injection::WriteShortcutTelemetry(Windows::UI::Input::Preview::Injection::ShortcutTelemetry &)

- ea: `0x180010c80`
- end: `0x180010d40`
- name: `?WriteShortcutTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUShortcutTelemetry@12345@@Z`
- size: `192`
- prototype: `void __fastcall(Windows::UI::Input::Preview::Injection *this, struct Windows::UI::Input::Preview::Injection::ShortcutTelemetry *, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c10`

## callees

- `0x18000116c`
- `0x180010c80`

## pseudocode

```c
void __fastcall Windows::UI::Input::Preview::Injection::WriteShortcutTelemetry(
        Windows::UI::Input::Preview::Injection *this,
        struct Windows::UI::Input::Preview::Injection::ShortcutTelemetry *a2,
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
    v8 = *((_DWORD *)this + 4);
    v9 = *((_DWORD *)this + 5);
    v10 = *((_DWORD *)this + 3);
    v4 = *((_DWORD *)this + 1);
    v5 = *(_DWORD *)this;
    v6 = *((_DWORD *)this + 2);
    v7 = "InputShortcut";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)byte_18001E8A9,
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
0x180010c80  mov     r11, rsp
0x180010c83  push    rbp
0x180010c84  mov     rbp, rsp
0x180010c87  sub     rsp, 80h
0x180010c8e  mov     eax, cs:dword_180022000
0x180010c94  cmp     eax, 5
0x180010c97  jbe     loc_180010D37
0x180010c9d  mov     rdx, cs:qword_180022018
0x180010ca4  mov     r8, 400000000000h
0x180010cae  mov     rax, cs:qword_180022010
0x180010cb5  test    r8, rax
0x180010cb8  jz      short loc_180010D37
0x180010cba  mov     rax, rdx
0x180010cbd  and     rax, r8
0x180010cc0  cmp     rax, rdx
0x180010cc3  jnz     short loc_180010D37
0x180010cc5  mov     eax, [rcx+10h]
0x180010cc8  lea     rdx, byte_18001E8A9
0x180010ccf  mov     [rbp+arg_8], eax
0x180010cd2  mov     eax, [rcx+14h]
0x180010cd5  mov     [rbp+arg_10], eax
0x180010cd8  mov     eax, [rcx+0Ch]
0x180010cdb  mov     [rbp+arg_18], eax
0x180010cde  mov     eax, [rcx+4]
0x180010ce1  mov     [rbp+var_20], eax
0x180010ce4  mov     eax, [rcx]
0x180010ce6  mov     [rbp+var_1C], eax
0x180010ce9  mov     eax, [rcx+8]
0x180010cec  mov     [rbp+var_18], eax
0x180010cef  lea     rax, aInputshortcut; "InputShortcut"
0x180010cf6  mov     [rbp+var_10], rax
0x180010cfa  lea     rax, [rbp+arg_8]
0x180010cfe  mov     [r11-38h], rax
0x180010d02  lea     rax, [rbp+arg_10]
0x180010d06  mov     [r11-40h], rax
0x180010d0a  lea     rax, [rbp+arg_18]
0x180010d0e  mov     [r11-48h], rax
0x180010d12  lea     rax, [rbp+var_20]
0x180010d16  mov     [r11-50h], rax
0x180010d1a  lea     rax, [rbp+var_1C]
0x180010d1e  mov     [r11-58h], rax
0x180010d22  lea     rax, [rbp+var_18]
0x180010d26  mov     [r11-60h], rax
0x180010d2a  lea     rax, [rbp+var_10]
0x180010d2e  mov     [r11-68h], rax
0x180010d32  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010d37  add     rsp, 80h
0x180010d3e  pop     rbp
0x180010d3f  retn
```
