# ServiceHostTelemetry::StartingService<ushort const *,long &>(ushort const * &&,long &)

- ea: `0x180007f84`
- end: `0x180008003`
- name: `??$StartingService@PEBGAEAJ@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ@Z`
- size: `127`
- prototype: `__int64 __fastcall(__int64 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a170`

## callees

- `0x180001098`
- `0x180007f84`
- `0x18000a648`

## pseudocode

```c
__int64 __fastcall ServiceHostTelemetry::StartingService<unsigned short const *,long &>(__int64 *a1, int *a2)
{
  __int64 result; // rax
  __int64 v5; // r9
  __int64 v6; // r8
  int v7; // [rsp+50h] [rbp+18h] BYREF
  __int64 v8; // [rsp+58h] [rbp+20h] BYREF

  result = (__int64)ServiceHostLogging::Provider();
  v5 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = *(_QWORD *)(result + 24);
    v6 = *(_QWORD *)(v5 + 16);
    if ( (v6 & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      v7 = *a2;
      v8 = *a1;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
               v5,
               (unsigned int)byte_180014B5B,
               v6,
               v5,
               (__int64)&v8,
               (__int64)&v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007f84  mov     [rsp+arg_0], rbx
0x180007f89  push    rdi
0x180007f8a  sub     rsp, 30h
0x180007f8e  mov     rbx, rdx
0x180007f91  mov     rdi, rcx
0x180007f94  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x180007f99  mov     r9, rax
0x180007f9c  mov     r8d, [rax]
0x180007f9f  cmp     r8d, 5
0x180007fa3  jbe     short loc_180007FF8
0x180007fa5  mov     rax, [rax+18h]
0x180007fa9  mov     rdx, 400000000000h
0x180007fb3  mov     r8, [r9+10h]
0x180007fb7  test    rdx, r8
0x180007fba  jz      short loc_180007FF8
0x180007fbc  mov     rcx, rax
0x180007fbf  and     rcx, rdx
0x180007fc2  cmp     rcx, rax
0x180007fc5  jnz     short loc_180007FF8
0x180007fc7  mov     eax, [rbx]
0x180007fc9  lea     rdx, byte_180014B5B
0x180007fd0  mov     [rsp+38h+arg_10], eax
0x180007fd4  mov     rcx, r9
0x180007fd7  mov     rax, [rdi]
0x180007fda  mov     [rsp+38h+arg_18], rax
0x180007fdf  lea     rax, [rsp+38h+arg_10]
0x180007fe4  mov     [rsp+38h+var_10], rax
0x180007fe9  lea     rax, [rsp+38h+arg_18]
0x180007fee  mov     [rsp+38h+var_18], rax
0x180007ff3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180007ff8  mov     rbx, [rsp+38h+arg_0]
0x180007ffd  add     rsp, 30h
0x180008001  pop     rdi
0x180008002  retn
```
