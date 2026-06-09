# PrinterCleanUpTelemetry::StalePrintJobDelete<char const *,ushort * &,ushort * &,int &>(char const * &&,ushort * &,ushort * &,int &)

- ea: `0x180007a74`
- end: `0x180007b29`
- name: `??$StalePrintJobDelete@PEBDAEAPEAGAEAPEAGAEAH@PrinterCleanUpTelemetry@@SAX$$QEAPEBDAEAPEAG1AEAH@Z`
- size: `181`
- prototype: `const struct _tlgProvider_t *__fastcall(_QWORD *, __int64 *, __int64 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b308`

## callees

- `0x1800010c0`
- `0x1800018ec`
- `0x180007a74`
- `0x18000e004`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall PrinterCleanUpTelemetry::StalePrintJobDelete<char const *,unsigned short * &,unsigned short * &,int &>(
        _QWORD *a1,
        __int64 *a2,
        __int64 *a3,
        int *a4)
{
  const struct _tlgProvider_t *result; // rax
  int v9; // r8d
  int v10; // r9d
  int v11; // r11d
  int v12; // ecx
  int v13; // [rsp+50h] [rbp-58h] BYREF
  __int64 v14; // [rsp+58h] [rbp-50h] BYREF
  __int64 v15; // [rsp+60h] [rbp-48h] BYREF
  __int64 v16; // [rsp+68h] [rbp-40h] BYREF
  _QWORD v17[7]; // [rsp+70h] [rbp-38h] BYREF

  result = PrinterCleanUpLogging::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v12 = *a4;
      v15 = *a3;
      v16 = *a2;
      v17[0] = *a1;
      v13 = v12;
      v14 = 0x1000000;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                                              v11,
                                              (unsigned int)byte_18001CC41,
                                              v9,
                                              v10,
                                              (__int64)v17,
                                              (__int64)&v16,
                                              (__int64)&v15,
                                              (__int64)&v13,
                                              (__int64)&v14);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007a74  push    rbx
0x180007a76  push    rsi
0x180007a77  push    rdi
0x180007a78  push    r14
0x180007a7a  sub     rsp, 88h
0x180007a81  mov     rbx, r9
0x180007a84  mov     rdi, r8
0x180007a87  mov     rsi, rdx
0x180007a8a  mov     r14, rcx
0x180007a8d  call    ?Provider@PrinterCleanUpLogging@@SAPEBU_tlgProvider_t@@XZ; PrinterCleanUpLogging::Provider(void)
0x180007a92  mov     r11, rax
0x180007a95  mov     r10d, [rax]
0x180007a98  cmp     r10d, 5
0x180007a9c  jbe     short loc_180007B1C
0x180007a9e  mov     rdx, 400000000000h
0x180007aa8  mov     rcx, rax
0x180007aab  call    _tlgKeywordOn
0x180007ab0  test    al, al
0x180007ab2  jz      short loc_180007B1C
0x180007ab4  mov     rax, [rdi]
0x180007ab7  lea     rdx, byte_18001CC41
0x180007abe  mov     ecx, [rbx]
0x180007ac0  mov     [rsp+0A8h+var_48], rax
0x180007ac5  mov     rax, [rsi]
0x180007ac8  mov     [rsp+0A8h+var_40], rax
0x180007acd  mov     rax, [r14]
0x180007ad0  mov     [rsp+0A8h+var_38], rax
0x180007ad5  lea     rax, [rsp+0A8h+var_50]
0x180007ada  mov     [rsp+0A8h+var_68], rax
0x180007adf  lea     rax, [rsp+0A8h+var_58]
0x180007ae4  mov     [rsp+0A8h+var_70], rax
0x180007ae9  lea     rax, [rsp+0A8h+var_48]
0x180007aee  mov     [rsp+0A8h+var_78], rax
0x180007af3  lea     rax, [rsp+0A8h+var_40]
0x180007af8  mov     [rsp+0A8h+var_80], rax
0x180007afd  lea     rax, [rsp+0A8h+var_38]
0x180007b02  mov     [rsp+0A8h+var_58], ecx
0x180007b06  mov     rcx, r11
0x180007b09  mov     [rsp+0A8h+var_88], rax
0x180007b0e  mov     [rsp+0A8h+var_50], 1000000h
0x180007b17  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180007b1c  add     rsp, 88h
0x180007b23  pop     r14
0x180007b25  pop     rdi
0x180007b26  pop     rsi
0x180007b27  pop     rbx
0x180007b28  retn
```
