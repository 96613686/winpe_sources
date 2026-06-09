# WhesvcTelemetryProvider::TraceToastShown<char const (&)[10],long,char const (&)[5]>(char const (&)[10],long &&,char const (&)[5])

- ea: `0x180014218`
- end: `0x1800142b3`
- name: `??$TraceToastShown@AEAY09$$CBDJAEAY04$$CBD@WhesvcTelemetryProvider@@SAXAEAY09$$CBD$$QEAJAEAY04$$CBD@Z`
- size: `155`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001642c`

## callees

- `0x180001008`
- `0x1800018bc`
- `0x180014218`
- `0x180016f2c`

## string_xrefs

- `0x180014274`: `completed`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall WhesvcTelemetryProvider::TraceToastShown<char const (&)[10],long,char const (&)[5]>(
        __int64 a1,
        _DWORD *a2,
        __int64 a3)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v5; // r9
  int v6; // r8d
  int v7; // r9d
  const char *v8; // [rsp+40h] [rbp-18h] BYREF
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF
  __int64 v10; // [rsp+70h] [rbp+18h] BYREF
  const char *v11; // [rsp+78h] [rbp+20h] BYREF

  v10 = a3;
  v9 = a1;
  result = WhesvcTelemetryProvider::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x400000000000LL, result, v5);
    if ( (_BYTE)result )
    {
      v9 = 0x1000000;
      v11 = "None";
      LODWORD(v10) = *a2;
      v8 = "completed";
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                                              v6,
                                              (unsigned int)byte_1800218AB,
                                              v6,
                                              v7,
                                              (__int64)&v8,
                                              (__int64)&v10,
                                              (__int64)&v11,
                                              (__int64)&v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014218  mov     [rsp+arg_10], r8
0x18001421d  mov     [rsp+arg_0], rcx
0x180014222  push    rbx
0x180014223  sub     rsp, 50h
0x180014227  mov     rbx, rdx
0x18001422a  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x18001422f  mov     r8, rax
0x180014232  mov     ecx, [rax]
0x180014234  cmp     ecx, 5
0x180014237  jbe     short loc_1800142AD
0x180014239  mov     rdx, 400000000000h
0x180014243  mov     rcx, rax
0x180014246  call    _tlgKeywordOn
0x18001424b  test    al, al
0x18001424d  jz      short loc_1800142AD
0x18001424f  lea     rax, aNone; "None"
0x180014256  mov     [rsp+58h+arg_0], 1000000h
0x18001425f  mov     [rsp+58h+arg_18], rax
0x180014264  lea     rdx, byte_1800218AB
0x18001426b  mov     eax, [rbx]
0x18001426d  mov     rcx, r8
0x180014270  mov     dword ptr [rsp+58h+arg_10], eax
0x180014274  lea     rax, aCompleted; "completed"
0x18001427b  mov     [rsp+58h+var_18], rax
0x180014280  lea     rax, [rsp+58h+arg_0]
0x180014285  mov     [rsp+58h+var_20], rax
0x18001428a  lea     rax, [rsp+58h+arg_18]
0x18001428f  mov     [rsp+58h+var_28], rax
0x180014294  lea     rax, [rsp+58h+arg_10]
0x180014299  mov     [rsp+58h+var_30], rax
0x18001429e  lea     rax, [rsp+58h+var_18]
0x1800142a3  mov     [rsp+58h+var_38], rax
0x1800142a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800142ad  add     rsp, 50h
0x1800142b1  pop     rbx
0x1800142b2  retn
```
