# WhesvcTelemetryProvider::TraceToastShown<char const (&)[10],long &,char const * &>(char const (&)[10],long &,char const * &)

- ea: `0x180014170`
- end: `0x18001420f`
- name: `??$TraceToastShown@AEAY09$$CBDAEAJAEAPEBD@WhesvcTelemetryProvider@@SAXAEAY09$$CBDAEAJAEAPEBD@Z`
- size: `159`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001642c`

## callees

- `0x180001008`
- `0x1800018bc`
- `0x180014170`
- `0x180016f2c`

## string_xrefs

- `0x1800141ba`: `completed`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall WhesvcTelemetryProvider::TraceToastShown<char const (&)[10],long &,char const * &>(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v6; // r8
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rcx
  __int64 v10; // [rsp+40h] [rbp-18h] BYREF
  const char *v11; // [rsp+48h] [rbp-10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  v12 = a1;
  result = WhesvcTelemetryProvider::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x400000000000LL, v6, result);
    if ( (_BYTE)result )
    {
      v9 = *a3;
      LODWORD(v12) = *a2;
      v11 = "completed";
      v10 = v9;
      v13 = 0x1000000;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                                              v8,
                                              (unsigned int)qword_1800218F8,
                                              v7,
                                              v8,
                                              (__int64)&v11,
                                              (__int64)&v12,
                                              (__int64)&v10,
                                              (__int64)&v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014170  mov     [rsp+arg_8], rbx
0x180014175  mov     [rsp+arg_0], rcx
0x18001417a  push    rdi
0x18001417b  sub     rsp, 50h
0x18001417f  mov     rbx, r8
0x180014182  mov     rdi, rdx
0x180014185  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x18001418a  mov     r9, rax
0x18001418d  mov     ecx, [rax]
0x18001418f  cmp     ecx, 5
0x180014192  jbe     short loc_180014204
0x180014194  mov     rdx, 400000000000h
0x18001419e  mov     rcx, rax
0x1800141a1  call    _tlgKeywordOn
0x1800141a6  test    al, al
0x1800141a8  jz      short loc_180014204
0x1800141aa  mov     eax, [rdi]
0x1800141ac  lea     rdx, qword_1800218F8
0x1800141b3  mov     rcx, [rbx]
0x1800141b6  mov     dword ptr [rsp+58h+arg_0], eax
0x1800141ba  lea     rax, aCompleted; "completed"
0x1800141c1  mov     [rsp+58h+var_10], rax
0x1800141c6  lea     rax, [rsp+58h+arg_18]
0x1800141cb  mov     [rsp+58h+var_20], rax
0x1800141d0  lea     rax, [rsp+58h+var_18]
0x1800141d5  mov     [rsp+58h+var_28], rax
0x1800141da  lea     rax, [rsp+58h+arg_0]
0x1800141df  mov     [rsp+58h+var_30], rax
0x1800141e4  lea     rax, [rsp+58h+var_10]
0x1800141e9  mov     [rsp+58h+var_18], rcx
0x1800141ee  mov     rcx, r9
0x1800141f1  mov     [rsp+58h+var_38], rax
0x1800141f6  mov     [rsp+58h+arg_18], 1000000h
0x1800141ff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180014204  mov     rbx, [rsp+58h+arg_8]
0x180014209  add     rsp, 50h
0x18001420d  pop     rdi
0x18001420e  retn
```
