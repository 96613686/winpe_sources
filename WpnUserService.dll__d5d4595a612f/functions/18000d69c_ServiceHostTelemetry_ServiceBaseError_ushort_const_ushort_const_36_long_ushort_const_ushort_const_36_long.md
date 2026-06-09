# ServiceHostTelemetry::ServiceBaseError<ushort const *,ushort const (&)[36],long>(ushort const * &&,ushort const (&)[36],long &&)

- ea: `0x18000d69c`
- end: `0x18000d734`
- name: `??$ServiceBaseError@PEBGAEAY0CE@$$CBGJ@ServiceHostTelemetry@@SAX$$QEAPEBGAEAY0CE@$$CBG$$QEAJ@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e904`

## callees

- `0x180001d58`
- `0x18000a648`
- `0x18000d69c`

## string_xrefs

- `0x18000d6f2`: `PreShutdownThreadPoolCreationFailed`

## pseudocode

```c
__int64 __fastcall ServiceHostTelemetry::ServiceBaseError<unsigned short const *,unsigned short const (&)[36],long>(
        _QWORD *a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 result; // rax
  __int64 v6; // r9
  _QWORD v7[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v8; // [rsp+68h] [rbp+10h] BYREF
  const wchar_t *v9; // [rsp+78h] [rbp+20h] BYREF

  v8 = a2;
  result = (__int64)ServiceHostLogging::Provider();
  v6 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      LODWORD(v8) = *a3;
      v9 = L"PreShutdownThreadPoolCreationFailed";
      v7[0] = *a1;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
               v6,
               (unsigned int)&word_1800153C6,
               0,
               v6,
               (__int64)v7,
               (__int64)&v9,
               (__int64)&v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d69c  mov     [rsp+arg_0], rbx
0x18000d6a1  mov     [rsp+arg_8], rdx
0x18000d6a6  push    rdi
0x18000d6a7  sub     rsp, 50h
0x18000d6ab  mov     rbx, r8
0x18000d6ae  mov     rdi, rcx
0x18000d6b1  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000d6b6  mov     r9, rax
0x18000d6b9  mov     edx, [rax]
0x18000d6bb  cmp     edx, 5
0x18000d6be  jbe     short loc_18000D729
0x18000d6c0  mov     rax, [rax+18h]
0x18000d6c4  mov     r8, 400000000000h
0x18000d6ce  mov     rdx, [r9+10h]
0x18000d6d2  test    r8, rdx
0x18000d6d5  jz      short loc_18000D729
0x18000d6d7  mov     rcx, rax
0x18000d6da  and     rcx, r8
0x18000d6dd  cmp     rcx, rax
0x18000d6e0  jnz     short loc_18000D729
0x18000d6e2  mov     eax, [rbx]
0x18000d6e4  lea     rdx, word_1800153C6
0x18000d6eb  mov     dword ptr [rsp+58h+arg_8], eax
0x18000d6ef  mov     rcx, r9
0x18000d6f2  lea     rax, aPreshutdownthr; "PreShutdownThreadPoolCreationFailed"
0x18000d6f9  mov     [rsp+58h+arg_18], rax
0x18000d6fe  mov     rax, [rdi]
0x18000d701  mov     [rsp+58h+var_18], rax
0x18000d706  lea     rax, [rsp+58h+arg_8]
0x18000d70b  mov     [rsp+58h+var_28], rax
0x18000d710  lea     rax, [rsp+58h+arg_18]
0x18000d715  mov     [rsp+58h+var_30], rax
0x18000d71a  lea     rax, [rsp+58h+var_18]
0x18000d71f  mov     [rsp+58h+var_38], rax
0x18000d724  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000d729  mov     rbx, [rsp+58h+arg_0]
0x18000d72e  add     rsp, 50h
0x18000d732  pop     rdi
0x18000d733  retn
```
