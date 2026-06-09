# Windows::UI::Input::Preview::Injection::WriteButtonTelemetry(Windows::UI::Input::Preview::Injection::ButtonTelemetry &)

- ea: `0x1800106f0`
- end: `0x18001079c`
- name: `?WriteButtonTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUButtonTelemetry@12345@@Z`
- size: `172`
- prototype: `void __fastcall(Windows::UI::Input::Preview::Injection *this, struct Windows::UI::Input::Preview::Injection::ButtonTelemetry *, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e2bc`

## callees

- `0x18000108c`
- `0x1800106f0`

## pseudocode

```c
void __fastcall Windows::UI::Input::Preview::Injection::WriteButtonTelemetry(
        Windows::UI::Input::Preview::Injection *this,
        struct Windows::UI::Input::Preview::Injection::ButtonTelemetry *a2,
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
    v7 = *((_DWORD *)this + 4);
    v8 = *((_DWORD *)this + 3);
    v9 = *((_DWORD *)this + 1);
    v4 = *(_DWORD *)this;
    v5 = *((_DWORD *)this + 2);
    v6 = "InputButton";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)byte_18001EC71,
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
0x1800106f0  mov     r11, rsp
0x1800106f3  push    rbp
0x1800106f4  mov     rbp, rsp
0x1800106f7  sub     rsp, 60h
0x1800106fb  mov     eax, cs:dword_180022000
0x180010701  cmp     eax, 5
0x180010704  jbe     loc_180010796
0x18001070a  mov     rdx, cs:qword_180022018
0x180010711  mov     r8, 400000000000h
0x18001071b  mov     rax, cs:qword_180022010
0x180010722  test    r8, rax
0x180010725  jz      short loc_180010796
0x180010727  mov     rax, rdx
0x18001072a  and     rax, r8
0x18001072d  cmp     rax, rdx
0x180010730  jnz     short loc_180010796
0x180010732  mov     eax, [rcx+10h]
0x180010735  lea     rdx, byte_18001EC71
0x18001073c  mov     [rbp+arg_8], eax
0x18001073f  mov     eax, [rcx+0Ch]
0x180010742  mov     [rbp+arg_10], eax
0x180010745  mov     eax, [rcx+4]
0x180010748  mov     [rbp+arg_18], eax
0x18001074b  mov     eax, [rcx]
0x18001074d  mov     [rbp+var_10], eax
0x180010750  mov     eax, [rcx+8]
0x180010753  mov     [rbp+var_C], eax
0x180010756  lea     rax, aInputbutton; "InputButton"
0x18001075d  mov     [rbp+var_8], rax
0x180010761  lea     rax, [rbp+arg_8]
0x180010765  mov     [r11-20h], rax
0x180010769  lea     rax, [rbp+arg_10]
0x18001076d  mov     [r11-28h], rax
0x180010771  lea     rax, [rbp+arg_18]
0x180010775  mov     [r11-30h], rax
0x180010779  lea     rax, [rbp+var_10]
0x18001077d  mov     [r11-38h], rax
0x180010781  lea     rax, [rbp+var_C]
0x180010785  mov     [r11-40h], rax
0x180010789  lea     rax, [rbp+var_8]
0x18001078d  mov     [r11-48h], rax
0x180010791  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010796  add     rsp, 60h
0x18001079a  pop     rbp
0x18001079b  retn
```
