# ControllerHostTelemetry::CreateVirtualTouchPad::Dimensions(int,int,int,int)

- ea: `0x18000db08`
- end: `0x18000dc62`
- name: `?Dimensions@CreateVirtualTouchPad@ControllerHostTelemetry@@QEAAXHHHH@Z`
- size: `346`
- prototype: `void __fastcall(ControllerHostTelemetry::CreateVirtualTouchPad *__hidden this, int, int, int, char)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180012960`

## callees

- `0x180001c6c`
- `0x18000298c`
- `0x180002f60`
- `0x18000db08`
- `0x18000ea48`
- `0x1800102f8`

## pseudocode

```c
void ControllerHostTelemetry::CreateVirtualTouchPad::Dimensions(
        ControllerHostTelemetry::CreateVirtualTouchPad *this,
        int a2,
        int a3,
        int a4,
        ...)
{
  const struct _tlgProvider_t *v4; // [rsp+48h] [rbp-60h]
  _BYTE v5[4]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v6[4]; // [rsp+54h] [rbp-54h] BYREF
  _BYTE v7[4]; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v8[4]; // [rsp+5Ch] [rbp-4Ch] BYREF
  const struct _tlgProvider_t *v9; // [rsp+60h] [rbp-48h]
  ControllerHostTelemetry::CreateVirtualTouchPad *v10; // [rsp+68h] [rbp-40h]
  __int64 v11; // [rsp+70h] [rbp-38h]
  __int64 v12; // [rsp+78h] [rbp-30h]
  __int64 v13; // [rsp+80h] [rbp-28h]
  __int64 v14; // [rsp+88h] [rbp-20h]
  __int64 v15; // [rsp+90h] [rbp-18h]
  int v16; // [rsp+B8h] [rbp+10h] BYREF
  int v17; // [rsp+C0h] [rbp+18h] BYREF
  int v18; // [rsp+C8h] [rbp+20h] BYREF
  va_list va; // [rsp+D0h] [rbp+28h] BYREF

  va_start(va, a4);
  v18 = a4;
  v17 = a3;
  v16 = a2;
  v10 = this;
  v4 = ControllerHostLogging::Provider();
  v9 = v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL) )
    {
      v11 = _tlgTypeMapBaseScalarImpl<int,7,0,4>::_tlgWrapAuto(v5, va);
      v12 = _tlgTypeMapBaseScalarImpl<int,7,0,4>::_tlgWrapAuto(v6, &v18);
      v13 = _tlgTypeMapBaseScalarImpl<int,7,0,4>::_tlgWrapAuto(v7, &v17);
      v14 = _tlgTypeMapBaseScalarImpl<int,7,0,4>::_tlgWrapAuto(v8, &v16);
      v15 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v10);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v4,
        (unsigned int)byte_180020861,
        v15,
        0,
        v14,
        v13,
        v12,
        v11);
    }
  }
}

```

## disassembly

```asm
0x18000db08  mov     [rsp+arg_18], r9d
0x18000db0d  mov     [rsp+arg_10], r8d
0x18000db12  mov     [rsp+arg_8], edx
0x18000db16  mov     [rsp+arg_0], rcx
0x18000db1b  sub     rsp, 0A8h
0x18000db22  mov     rax, [rsp+0A8h+arg_0]
0x18000db2a  mov     [rsp+0A8h+var_40], rax
0x18000db2f  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x18000db34  mov     [rsp+0A8h+var_60], rax
0x18000db39  mov     rax, [rsp+0A8h+var_60]
0x18000db3e  mov     [rsp+0A8h+var_48], rax
0x18000db43  mov     [rsp+0A8h+var_68], 0
0x18000db4b  mov     rax, [rsp+0A8h+var_48]
0x18000db50  mov     eax, [rax]
0x18000db52  mov     [rsp+0A8h+var_68], eax
0x18000db56  mov     eax, [rsp+0A8h+var_68]
0x18000db5a  mov     [rsp+0A8h+var_64], eax
0x18000db5e  mov     eax, [rsp+0A8h+var_64]
0x18000db62  cmp     eax, 5
0x18000db65  jbe     loc_18000DC46
0x18000db6b  mov     rdx, cs:qword_180020864
0x18000db72  mov     rcx, [rsp+0A8h+var_60]
0x18000db77  call    _tlgKeywordOn
0x18000db7c  movzx   eax, al
0x18000db7f  test    eax, eax
0x18000db81  jz      loc_18000DC46
0x18000db87  lea     rdx, [rsp+0A8h+arg_20]
0x18000db8f  lea     rcx, [rsp+0A8h+var_58]
0x18000db94  call    ?_tlgWrapAuto@?$_tlgTypeMapBaseScalarImpl@H$06$0A@$03@@SA?AU?$_tlgWrapperByVal@$03@@AEBH@Z; _tlgTypeMapBaseScalarImpl<int,7,0,4>::_tlgWrapAuto(int const &)
0x18000db99  mov     [rsp+0A8h+var_38], rax
0x18000db9e  lea     rdx, [rsp+0A8h+arg_18]
0x18000dba6  lea     rcx, [rsp+0A8h+var_54]
0x18000dbab  call    ?_tlgWrapAuto@?$_tlgTypeMapBaseScalarImpl@H$06$0A@$03@@SA?AU?$_tlgWrapperByVal@$03@@AEBH@Z; _tlgTypeMapBaseScalarImpl<int,7,0,4>::_tlgWrapAuto(int const &)
0x18000dbb0  mov     [rsp+0A8h+var_30], rax
0x18000dbb5  lea     rdx, [rsp+0A8h+arg_10]
0x18000dbbd  lea     rcx, [rsp+0A8h+var_50]
0x18000dbc2  call    ?_tlgWrapAuto@?$_tlgTypeMapBaseScalarImpl@H$06$0A@$03@@SA?AU?$_tlgWrapperByVal@$03@@AEBH@Z; _tlgTypeMapBaseScalarImpl<int,7,0,4>::_tlgWrapAuto(int const &)
0x18000dbc7  mov     [rsp+0A8h+var_28], rax
0x18000dbcf  lea     rdx, [rsp+0A8h+arg_8]
0x18000dbd7  lea     rcx, [rsp+0A8h+var_4C]
0x18000dbdc  call    ?_tlgWrapAuto@?$_tlgTypeMapBaseScalarImpl@H$06$0A@$03@@SA?AU?$_tlgWrapperByVal@$03@@AEBH@Z; _tlgTypeMapBaseScalarImpl<int,7,0,4>::_tlgWrapAuto(int const &)
0x18000dbe1  mov     [rsp+0A8h+var_20], rax
0x18000dbe9  mov     rcx, [rsp+0A8h+var_40]
0x18000dbee  call    ?Id@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000dbf3  mov     [rsp+0A8h+var_18], rax
0x18000dbfb  mov     rax, [rsp+0A8h+var_38]
0x18000dc00  mov     [rsp+0A8h+var_70], rax
0x18000dc05  mov     rax, [rsp+0A8h+var_30]
0x18000dc0a  mov     [rsp+0A8h+var_78], rax
0x18000dc0f  mov     rax, [rsp+0A8h+var_28]
0x18000dc17  mov     [rsp+0A8h+var_80], rax
0x18000dc1c  mov     rax, [rsp+0A8h+var_20]
0x18000dc24  mov     [rsp+0A8h+var_88], rax
0x18000dc29  xor     r9d, r9d
0x18000dc2c  mov     r8, [rsp+0A8h+var_18]
0x18000dc34  lea     rdx, byte_180020861
0x18000dc3b  mov     rcx, [rsp+0A8h+var_60]
0x18000dc40  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000dc45  nop
0x18000dc46  xor     eax, eax
0x18000dc48  test    eax, eax
0x18000dc4a  jnz     loc_18000DB2F
0x18000dc50  xor     eax, eax
0x18000dc52  test    eax, eax
0x18000dc54  jnz     loc_18000DB22
0x18000dc5a  add     rsp, 0A8h
0x18000dc61  retn
```
