# SPTelemetry::ModelUpdate::AsimovDownloadFilesLocal<long &,ulong &>(unsigned __int64,long &,ulong &)

- ea: `0x14000a7b8`
- end: `0x14000a846`
- name: `??$AsimovDownloadFilesLocal@AEAJAEAK@ModelUpdate@SPTelemetry@@QEAAX_KAEAJAEAK@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64, __int64, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000d1f4`

## callees

- `0x140001360`
- `0x1400077b0`
- `0x14000a7b8`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovDownloadFilesLocal<long &,unsigned long &>(
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
    if ( (*(_QWORD *)(v9 + 16) & 1) != 0 && (result & 1) == result )
    {
      v10 = *(_QWORD *)(a1 + 48);
      v11 = *a4;
      v12 = *a3;
      v13[0] = a2;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               v9,
               (unsigned int)&unk_140029DB0,
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
0x14000a7b8  push    rbx
0x14000a7ba  push    rbp
0x14000a7bb  push    rsi
0x14000a7bc  push    rdi
0x14000a7bd  sub     rsp, 58h
0x14000a7c1  mov     rdi, r9
0x14000a7c4  mov     rsi, r8
0x14000a7c7  mov     rbp, rdx
0x14000a7ca  mov     rbx, rcx
0x14000a7cd  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000a7d2  mov     r11, rax
0x14000a7d5  mov     r10d, [rax]
0x14000a7d8  cmp     r10d, 4
0x14000a7dc  jbe     short loc_14000A83D
0x14000a7de  mov     rax, [rax+18h]
0x14000a7e2  mov     r10, [r11+10h]
0x14000a7e6  test    r10b, 1
0x14000a7ea  jz      short loc_14000A83D
0x14000a7ec  mov     rcx, rax
0x14000a7ef  and     ecx, 1
0x14000a7f2  cmp     rcx, rax
0x14000a7f5  jnz     short loc_14000A83D
0x14000a7f7  mov     eax, [rdi]
0x14000a7f9  lea     r8, [rbx+20h]
0x14000a7fd  mov     r9, [rbx+30h]
0x14000a801  lea     rdx, unk_140029DB0
0x14000a808  mov     [rsp+78h+var_38], eax
0x14000a80c  mov     rcx, r11
0x14000a80f  mov     eax, [rsi]
0x14000a811  mov     [rsp+78h+var_34], eax
0x14000a815  lea     rax, [rsp+78h+var_38]
0x14000a81a  mov     [rsp+78h+var_48], rax
0x14000a81f  lea     rax, [rsp+78h+var_34]
0x14000a824  mov     [rsp+78h+var_50], rax
0x14000a829  lea     rax, [rsp+78h+var_30]
0x14000a82e  mov     [rsp+78h+var_58], rax
0x14000a833  mov     [rsp+78h+var_30], rbp
0x14000a838  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000a83d  add     rsp, 58h
0x14000a841  pop     rdi
0x14000a842  pop     rsi
0x14000a843  pop     rbp
0x14000a844  pop     rbx
0x14000a845  retn
```
