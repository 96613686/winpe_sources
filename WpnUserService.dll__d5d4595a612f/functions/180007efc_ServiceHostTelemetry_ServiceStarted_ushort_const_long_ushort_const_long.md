# ServiceHostTelemetry::ServiceStarted<ushort const *,long &>(ushort const * &&,long &)

- ea: `0x180007efc`
- end: `0x180007f7b`
- name: `??$ServiceStarted@PEBGAEAJ@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ@Z`
- size: `127`
- prototype: `__int64 __fastcall(__int64 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180009d40`

## callees

- `0x180001098`
- `0x180007efc`
- `0x18000a648`

## pseudocode

```c
__int64 __fastcall ServiceHostTelemetry::ServiceStarted<unsigned short const *,long &>(__int64 *a1, int *a2)
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
               (unsigned int)&dword_180014AEC,
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
0x180007efc  mov     [rsp+arg_0], rbx
0x180007f01  push    rdi
0x180007f02  sub     rsp, 30h
0x180007f06  mov     rbx, rdx
0x180007f09  mov     rdi, rcx
0x180007f0c  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x180007f11  mov     r9, rax
0x180007f14  mov     r8d, [rax]
0x180007f17  cmp     r8d, 5
0x180007f1b  jbe     short loc_180007F70
0x180007f1d  mov     rax, [rax+18h]
0x180007f21  mov     rdx, 400000000000h
0x180007f2b  mov     r8, [r9+10h]
0x180007f2f  test    rdx, r8
0x180007f32  jz      short loc_180007F70
0x180007f34  mov     rcx, rax
0x180007f37  and     rcx, rdx
0x180007f3a  cmp     rcx, rax
0x180007f3d  jnz     short loc_180007F70
0x180007f3f  mov     eax, [rbx]
0x180007f41  lea     rdx, dword_180014AEC
0x180007f48  mov     [rsp+38h+arg_10], eax
0x180007f4c  mov     rcx, r9
0x180007f4f  mov     rax, [rdi]
0x180007f52  mov     [rsp+38h+arg_18], rax
0x180007f57  lea     rax, [rsp+38h+arg_10]
0x180007f5c  mov     [rsp+38h+var_10], rax
0x180007f61  lea     rax, [rsp+38h+arg_18]
0x180007f66  mov     [rsp+38h+var_18], rax
0x180007f6b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180007f70  mov     rbx, [rsp+38h+arg_0]
0x180007f75  add     rsp, 30h
0x180007f79  pop     rdi
0x180007f7a  retn
```
