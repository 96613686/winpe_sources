# SPTelemetry::ModelUpdate::AsimovInitializeParameters<long &,ushort const * &,ushort const * &,ushort const * &,ushort const * &>(unsigned __int64,long &,ushort const * &,ushort const * &,ushort const * &,ushort const * &)

- ea: `0x14000abc4`
- end: `0x14000aca8`
- name: `??$AsimovInitializeParameters@AEAJAEAPEBGAEAPEBGAEAPEBGAEAPEBG@ModelUpdate@SPTelemetry@@QEAAX_KAEAJAEAPEBG222@Z`
- size: `228`
- prototype: `__int64 __fastcall(__int64, __int64, int *, __int64 *, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000fdf4`

## callees

- `0x14000180c`
- `0x1400077b0`
- `0x14000abc4`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovInitializeParameters<long &,unsigned short const * &,unsigned short const * &,unsigned short const * &,unsigned short const * &>(
        __int64 a1,
        __int64 a2,
        int *a3,
        __int64 *a4,
        __int64 *a5,
        __int64 *a6,
        __int64 *a7)
{
  __int64 result; // rax
  __int64 v12; // r11
  __int64 v13; // r9
  __int64 v14; // rcx
  int v15; // [rsp+50h] [rbp-30h] BYREF
  __int64 v16; // [rsp+58h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-20h] BYREF
  __int64 v18; // [rsp+68h] [rbp-18h] BYREF
  __int64 v19; // [rsp+70h] [rbp-10h] BYREF
  __int64 v20; // [rsp+78h] [rbp-8h] BYREF

  result = (__int64)SPTraceLoggingClass::Provider();
  v12 = result;
  if ( *(_DWORD *)result > 4u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      v13 = *(_QWORD *)(a1 + 48);
      v20 = a2;
      v16 = *a7;
      v17 = *a6;
      v14 = *a5;
      v19 = *a4;
      v15 = *a3;
      v18 = v14;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
               v12,
               (unsigned int)&dword_140029F94,
               (int)a1 + 32,
               v13,
               (__int64)&v20,
               (__int64)&v15,
               (__int64)&v19,
               (__int64)&v18,
               (__int64)&v17,
               (__int64)&v16);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000abc4  push    rbp
0x14000abc6  push    rbx
0x14000abc7  push    rsi
0x14000abc8  push    rdi
0x14000abc9  push    r14
0x14000abcb  mov     rbp, rsp
0x14000abce  sub     rsp, 80h
0x14000abd5  mov     rdi, r9
0x14000abd8  mov     rsi, r8
0x14000abdb  mov     r14, rdx
0x14000abde  mov     rbx, rcx
0x14000abe1  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000abe6  mov     r11, rax
0x14000abe9  mov     r10d, [rax]
0x14000abec  cmp     r10d, 4
0x14000abf0  jbe     loc_14000AC9A
0x14000abf6  mov     rax, [rax+18h]
0x14000abfa  mov     rdx, 400000000000h
0x14000ac04  mov     r10, [r11+10h]
0x14000ac08  test    rdx, r10
0x14000ac0b  jz      loc_14000AC9A
0x14000ac11  mov     rcx, rax
0x14000ac14  and     rcx, rdx
0x14000ac17  cmp     rcx, rax
0x14000ac1a  jnz     short loc_14000AC9A
0x14000ac1c  mov     rax, [rbp+arg_30]
0x14000ac20  lea     r8, [rbx+20h]
0x14000ac24  mov     r9, [rbx+30h]
0x14000ac28  lea     rdx, dword_140029F94
0x14000ac2f  mov     [rbp+var_8], r14
0x14000ac33  mov     rcx, [rax]
0x14000ac36  mov     rax, [rbp+arg_28]
0x14000ac3a  mov     [rbp+var_28], rcx
0x14000ac3e  mov     rcx, [rax]
0x14000ac41  mov     rax, [rbp+arg_20]
0x14000ac45  mov     [rbp+var_20], rcx
0x14000ac49  mov     rcx, [rax]
0x14000ac4c  mov     rax, [rdi]
0x14000ac4f  mov     [rbp+var_10], rax
0x14000ac53  mov     eax, [rsi]
0x14000ac55  mov     [rbp+var_30], eax
0x14000ac58  lea     rax, [rbp+var_28]
0x14000ac5c  mov     [rsp+80h+var_38], rax
0x14000ac61  lea     rax, [rbp+var_20]
0x14000ac65  mov     [rsp+80h+var_40], rax
0x14000ac6a  lea     rax, [rbp+var_18]
0x14000ac6e  mov     [rsp+80h+var_48], rax
0x14000ac73  lea     rax, [rbp+var_10]
0x14000ac77  mov     [rsp+80h+var_50], rax
0x14000ac7c  lea     rax, [rbp+var_30]
0x14000ac80  mov     [rsp+80h+var_58], rax
0x14000ac85  lea     rax, [rbp+var_8]
0x14000ac89  mov     [rbp+var_18], rcx
0x14000ac8d  mov     rcx, r11
0x14000ac90  mov     [rsp+80h+var_60], rax
0x14000ac95  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14000ac9a  add     rsp, 80h
0x14000aca1  pop     r14
0x14000aca3  pop     rdi
0x14000aca4  pop     rsi
0x14000aca5  pop     rbx
0x14000aca6  pop     rbp
0x14000aca7  retn
```
