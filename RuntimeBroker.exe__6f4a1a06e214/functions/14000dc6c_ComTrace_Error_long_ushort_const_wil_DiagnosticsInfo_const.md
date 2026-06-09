# ComTrace::Error_(long,ushort const *,wil::DiagnosticsInfo const &)

- ea: `0x14000dc6c`
- end: `0x14000dd0d`
- name: `?Error_@ComTrace@@QEAAXJPEBGAEBUDiagnosticsInfo@wil@@@Z`
- size: `161`
- prototype: `void __fastcall(ComTrace *__hidden this, int, const unsigned __int16 *, const struct DiagnosticsInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000eb14`

## callees

- `0x1400010b8`
- `0x14000dc6c`
- `0x14000e06c`

## pseudocode

```c
void __fastcall ComTrace::Error_(ComTrace *this, int a2, const size_t *a3, const struct DiagnosticsInfo *a4)
{
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // [rsp+50h] [rbp+7h] BYREF
  const unsigned __int16 *v11; // [rsp+58h] [rbp+Fh] BYREF
  const unsigned __int16 *v12; // [rsp+60h] [rbp+17h] BYREF
  const size_t *v13; // [rsp+68h] [rbp+1Fh] BYREF
  const unsigned __int16 *v14; // [rsp+70h] [rbp+27h] BYREF
  ComTrace *v15; // [rsp+B0h] [rbp+67h] BYREF

  v15 = this;
  v7 = ComTrace::Provider();
  if ( *(_DWORD *)v7 > 2u )
  {
    LOWORD(v15) = a4[3].cost;
    v11 = (const unsigned __int16 *)a4[1];
    v12 = (const unsigned __int16 *)a4[2];
    v13 = a3;
    v14 = 0;
    v10 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
      (__int64)v7,
      (unsigned __int8 *)byte_14001479D,
      v8,
      v9,
      (__int64)&v10,
      &v14,
      &v13,
      &v12,
      &v11,
      (__int64)&v15);
  }
}

```

## disassembly

```asm
0x14000dc6c  mov     [rsp-8+arg_0], rcx
0x14000dc71  push    rbp
0x14000dc72  push    rbx
0x14000dc73  push    rsi
0x14000dc74  push    rdi
0x14000dc75  lea     rbp, [rsp-3Fh]
0x14000dc7a  sub     rsp, 88h
0x14000dc81  mov     rbx, r9
0x14000dc84  mov     rdi, r8
0x14000dc87  mov     esi, edx
0x14000dc89  call    ?Provider@ComTrace@@SAPEBU_tlgProvider_t@@XZ; ComTrace::Provider(void)
0x14000dc8e  mov     ecx, [rax]
0x14000dc90  cmp     ecx, 2
0x14000dc93  jbe     short loc_14000DD01
0x14000dc95  movzx   ecx, word ptr [rbx+18h]
0x14000dc99  lea     rdx, byte_14001479D
0x14000dca0  mov     word ptr [rbp+57h+arg_0], cx
0x14000dca4  mov     rcx, [rbx+8]
0x14000dca8  mov     [rbp+57h+var_48], rcx
0x14000dcac  mov     rcx, [rbx+10h]
0x14000dcb0  mov     [rbp+57h+var_40], rcx
0x14000dcb4  lea     rcx, [rbp+57h+arg_0]
0x14000dcb8  mov     [rsp+0A0h+var_58], rcx
0x14000dcbd  lea     rcx, [rbp+57h+var_48]
0x14000dcc1  mov     [rsp+0A0h+var_60], rcx
0x14000dcc6  lea     rcx, [rbp+57h+var_40]
0x14000dcca  mov     [rsp+0A0h+var_68], rcx
0x14000dccf  lea     rcx, [rbp+57h+var_38]
0x14000dcd3  mov     [rsp+0A0h+var_70], rcx
0x14000dcd8  lea     rcx, [rbp+57h+var_30]
0x14000dcdc  mov     [rsp+0A0h+var_78], rcx
0x14000dce1  lea     rcx, [rbp+57h+var_50]
0x14000dce5  mov     [rsp+0A0h+var_80], rcx
0x14000dcea  mov     rcx, rax
0x14000dced  mov     [rbp+57h+var_38], rdi
0x14000dcf1  mov     [rbp+57h+var_30], 0
0x14000dcf9  mov     [rbp+57h+var_50], esi
0x14000dcfc  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &)
0x14000dd01  add     rsp, 88h
0x14000dd08  pop     rdi
0x14000dd09  pop     rsi
0x14000dd0a  pop     rbx
0x14000dd0b  pop     rbp
0x14000dd0c  retn
```
