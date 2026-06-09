# SPTelemetry::ModelUpdate::AsimovInitializeParametersLocal<long &,ushort const * &,ushort const * &,ushort const * &,ushort const * &>(unsigned __int64,long &,ushort const * &,ushort const * &,ushort const * &,ushort const * &)

- ea: `0x14000acb0`
- end: `0x14000ad8b`
- name: `??$AsimovInitializeParametersLocal@AEAJAEAPEBGAEAPEBGAEAPEBGAEAPEBG@ModelUpdate@SPTelemetry@@QEAAX_KAEAJAEAPEBG222@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, int *, __int64 *, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000fdf4`

## callees

- `0x14000180c`
- `0x1400077b0`
- `0x14000acb0`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovInitializeParametersLocal<long &,unsigned short const * &,unsigned short const * &,unsigned short const * &,unsigned short const * &>(
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
    if ( (*(_QWORD *)(v12 + 16) & 1) != 0 && (result & 1) == result )
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
               (unsigned int)&dword_140029F24,
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
0x14000acb0  push    rbp
0x14000acb2  push    rbx
0x14000acb3  push    rsi
0x14000acb4  push    rdi
0x14000acb5  push    r14
0x14000acb7  mov     rbp, rsp
0x14000acba  sub     rsp, 80h
0x14000acc1  mov     rdi, r9
0x14000acc4  mov     rsi, r8
0x14000acc7  mov     r14, rdx
0x14000acca  mov     rbx, rcx
0x14000accd  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000acd2  mov     r11, rax
0x14000acd5  mov     r10d, [rax]
0x14000acd8  cmp     r10d, 4
0x14000acdc  jbe     loc_14000AD7D
0x14000ace2  mov     rax, [rax+18h]
0x14000ace6  mov     r10, [r11+10h]
0x14000acea  test    r10b, 1
0x14000acee  jz      loc_14000AD7D
0x14000acf4  mov     rcx, rax
0x14000acf7  and     ecx, 1
0x14000acfa  cmp     rcx, rax
0x14000acfd  jnz     short loc_14000AD7D
0x14000acff  mov     rax, [rbp+arg_30]
0x14000ad03  lea     r8, [rbx+20h]
0x14000ad07  mov     r9, [rbx+30h]
0x14000ad0b  lea     rdx, dword_140029F24
0x14000ad12  mov     [rbp+var_8], r14
0x14000ad16  mov     rcx, [rax]
0x14000ad19  mov     rax, [rbp+arg_28]
0x14000ad1d  mov     [rbp+var_28], rcx
0x14000ad21  mov     rcx, [rax]
0x14000ad24  mov     rax, [rbp+arg_20]
0x14000ad28  mov     [rbp+var_20], rcx
0x14000ad2c  mov     rcx, [rax]
0x14000ad2f  mov     rax, [rdi]
0x14000ad32  mov     [rbp+var_10], rax
0x14000ad36  mov     eax, [rsi]
0x14000ad38  mov     [rbp+var_30], eax
0x14000ad3b  lea     rax, [rbp+var_28]
0x14000ad3f  mov     [rsp+80h+var_38], rax
0x14000ad44  lea     rax, [rbp+var_20]
0x14000ad48  mov     [rsp+80h+var_40], rax
0x14000ad4d  lea     rax, [rbp+var_18]
0x14000ad51  mov     [rsp+80h+var_48], rax
0x14000ad56  lea     rax, [rbp+var_10]
0x14000ad5a  mov     [rsp+80h+var_50], rax
0x14000ad5f  lea     rax, [rbp+var_30]
0x14000ad63  mov     [rsp+80h+var_58], rax
0x14000ad68  lea     rax, [rbp+var_8]
0x14000ad6c  mov     [rbp+var_18], rcx
0x14000ad70  mov     rcx, r11
0x14000ad73  mov     [rsp+80h+var_60], rax
0x14000ad78  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14000ad7d  add     rsp, 80h
0x14000ad84  pop     r14
0x14000ad86  pop     rdi
0x14000ad87  pop     rsi
0x14000ad88  pop     rbx
0x14000ad89  pop     rbp
0x14000ad8a  retn
```
