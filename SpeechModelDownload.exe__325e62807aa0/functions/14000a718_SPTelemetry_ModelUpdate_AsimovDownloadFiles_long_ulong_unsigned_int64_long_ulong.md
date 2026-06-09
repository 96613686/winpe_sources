# SPTelemetry::ModelUpdate::AsimovDownloadFiles<long &,ulong &>(unsigned __int64,long &,ulong &)

- ea: `0x14000a718`
- end: `0x14000a7af`
- name: `??$AsimovDownloadFiles@AEAJAEAK@ModelUpdate@SPTelemetry@@QEAAX_KAEAJAEAK@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64, __int64, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000d1f4`

## callees

- `0x140001360`
- `0x1400077b0`
- `0x14000a718`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovDownloadFiles<long &,unsigned long &>(
        __int64 a1,
        __int64 a2,
        int *a3,
        int *a4)
{
  __int64 result; // rax
  __int64 v9; // r11
  __int64 v10; // r9
  int v11; // [rsp+40h] [rbp-38h] BYREF
  int v12; // [rsp+44h] [rbp-34h] BYREF
  _QWORD v13[6]; // [rsp+48h] [rbp-30h] BYREF

  result = (__int64)SPTraceLoggingClass::Provider();
  v9 = result;
  if ( *(_DWORD *)result > 4u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      v10 = *(_QWORD *)(a1 + 48);
      v11 = *a4;
      v12 = *a3;
      v13[0] = a2;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               v9,
               (unsigned int)&byte_140029DF7,
               (int)a1 + 32,
               v10,
               (__int64)v13,
               (__int64)&v12,
               (__int64)&v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a718  push    rbx
0x14000a71a  push    rbp
0x14000a71b  push    rsi
0x14000a71c  push    rdi
0x14000a71d  sub     rsp, 58h
0x14000a721  mov     rdi, r9
0x14000a724  mov     rsi, r8
0x14000a727  mov     rbp, rdx
0x14000a72a  mov     rbx, rcx
0x14000a72d  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000a732  mov     r11, rax
0x14000a735  mov     r10d, [rax]
0x14000a738  cmp     r10d, 4
0x14000a73c  jbe     short loc_14000A7A6
0x14000a73e  mov     rax, [rax+18h]
0x14000a742  mov     rdx, 400000000000h
0x14000a74c  mov     r10, [r11+10h]
0x14000a750  test    rdx, r10
0x14000a753  jz      short loc_14000A7A6
0x14000a755  mov     rcx, rax
0x14000a758  and     rcx, rdx
0x14000a75b  cmp     rcx, rax
0x14000a75e  jnz     short loc_14000A7A6
0x14000a760  mov     eax, [rdi]
0x14000a762  lea     r8, [rbx+20h]
0x14000a766  mov     r9, [rbx+30h]
0x14000a76a  lea     rdx, byte_140029DF7
0x14000a771  mov     [rsp+78h+var_38], eax
0x14000a775  mov     rcx, r11
0x14000a778  mov     eax, [rsi]
0x14000a77a  mov     [rsp+78h+var_34], eax
0x14000a77e  lea     rax, [rsp+78h+var_38]
0x14000a783  mov     [rsp+78h+var_48], rax
0x14000a788  lea     rax, [rsp+78h+var_34]
0x14000a78d  mov     [rsp+78h+var_50], rax
0x14000a792  lea     rax, [rsp+78h+var_30]
0x14000a797  mov     [rsp+78h+var_58], rax
0x14000a79c  mov     [rsp+78h+var_30], rbp
0x14000a7a1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000a7a6  add     rsp, 58h
0x14000a7aa  pop     rdi
0x14000a7ab  pop     rsi
0x14000a7ac  pop     rbp
0x14000a7ad  pop     rbx
0x14000a7ae  retn
```
