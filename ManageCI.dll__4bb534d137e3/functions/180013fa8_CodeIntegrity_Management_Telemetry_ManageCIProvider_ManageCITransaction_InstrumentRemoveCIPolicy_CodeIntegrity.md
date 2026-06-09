# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveCIPolicy(CodeIntegrity::Management::SiPolicyView const &)

- ea: `0x180013fa8`
- end: `0x1800140eb`
- name: `?InstrumentRemoveCIPolicy@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVSiPolicyView@45@@Z`
- size: `323`
- prototype: `void __fastcall(CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *this, const struct CodeIntegrity::Management::SiPolicyView *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011c00`

## callees

- `0x1800019bc`
- `0x180001e80`
- `0x18000828c`
- `0x1800086b4`
- `0x180013fa8`
- `0x180014ce4`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveCIPolicy(
        CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *this,
        const struct CodeIntegrity::Management::SiPolicyView *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  char v6; // al
  _QWORD *v7; // r10
  _QWORD *v8; // r11
  __int64 v9; // rax
  int *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r10
  __int64 v13; // r11
  __int64 v14; // r9
  char v15; // [rsp+80h] [rbp+17h] BYREF
  bool is_authorized; // [rsp+81h] [rbp+18h] BYREF
  _BYTE v17[2]; // [rsp+82h] [rbp+19h] BYREF
  int v18; // [rsp+84h] [rbp+1Bh] BYREF
  __int64 v19; // [rsp+88h] [rbp+1Fh] BYREF
  int *v20; // [rsp+90h] [rbp+27h] BYREF
  __int64 v21; // [rsp+98h] [rbp+2Fh] BYREF
  __int64 v22; // [rsp+A0h] [rbp+37h] BYREF
  __int64 v23[3]; // [rsp+A8h] [rbp+3Fh] BYREF
  char v24; // [rsp+D0h] [rbp+67h] BYREF
  bool v25; // [rsp+E0h] [rbp+77h] BYREF
  char v26; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
  v5 = *(unsigned int *)v4;
  if ( (unsigned int)v5 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL, v5) )
  {
    v6 = *((_BYTE *)a2 + 92);
    v7 = (_QWORD *)*((_QWORD *)a2 + 1);
    v8 = *(_QWORD **)a2;
    v18 = 0;
    v24 = v6;
    v9 = *v7 - *v8;
    if ( *v7 == *v8 )
      v9 = v7[1] - v8[1];
    v26 = *((_BYTE *)a2 + 93);
    v25 = v9 == 0;
    v15 = *((_BYTE *)a2 + 88);
    is_authorized = CodeIntegrity::Management::SiPolicyView::is_authorized(a2);
    v17[0] = *((_BYTE *)a2 + 90);
    v19 = *((_QWORD *)a2 + 2);
    v10 = (int *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v11 = *((_QWORD *)this + 34);
    v20 = v10;
    v21 = v12;
    v22 = v13;
    v23[0] = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      v14,
      (__int64)&word_180031C46,
      v11 + 8,
      v14,
      (__int64)v23,
      &v22,
      &v21,
      &v20,
      (__int64)&v19,
      (__int64)v17,
      (__int64)&is_authorized,
      (__int64)&v15,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v18);
  }
}

```

## disassembly

```asm
0x180013fa8  push    rbp
0x180013faa  push    rbx
0x180013fab  push    rdi
0x180013fac  lea     rbp, [rsp-47h]
0x180013fb1  sub     rsp, 0B0h
0x180013fb8  mov     rbx, rdx
0x180013fbb  mov     rdi, rcx
0x180013fbe  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180013fc3  mov     r9, rax
0x180013fc6  mov     r8d, [rax]
0x180013fc9  cmp     r8d, 5
0x180013fcd  jbe     loc_1800140E0
0x180013fd3  mov     rdx, 400000000000h
0x180013fdd  mov     rcx, rax
0x180013fe0  call    _tlgKeywordOn
0x180013fe5  test    al, al
0x180013fe7  jz      loc_1800140E0
0x180013fed  mov     al, [rbx+5Ch]
0x180013ff0  mov     r10, [rbx+8]
0x180013ff4  mov     r11, [rbx]
0x180013ff7  mov     [rbp+57h+var_3C], 0
0x180013ffe  mov     [rbp+57h+arg_0], al
0x180014001  mov     rax, [r10]
0x180014004  sub     rax, [r11]
0x180014007  jnz     short loc_180014011
0x180014009  mov     rax, [r10+8]
0x18001400d  sub     rax, [r11+8]
0x180014011  test    rax, rax
0x180014014  mov     rcx, rbx; this
0x180014017  mov     al, [rbx+5Dh]
0x18001401a  mov     [rbp+57h+arg_18], al
0x18001401d  setz    [rbp+57h+arg_10]
0x180014021  mov     al, [rbx+58h]
0x180014024  mov     [rbp+57h+var_40], al
0x180014027  call    ?is_authorized@SiPolicyView@Management@CodeIntegrity@@QEBA_NXZ; CodeIntegrity::Management::SiPolicyView::is_authorized(void)
0x18001402c  mov     [rbp+57h+var_3F], al
0x18001402f  lea     rcx, [rbx+18h]
0x180014033  mov     al, [rbx+5Ah]
0x180014036  mov     [rbp+57h+var_3E], al
0x180014039  mov     rax, [rbx+10h]
0x18001403d  mov     [rbp+57h+var_38], rax
0x180014041  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014046  mov     r8, [rdi+110h]
0x18001404d  lea     rdx, word_180031C46
0x180014054  mov     [rbp+57h+var_30], rax
0x180014058  add     r8, 8
0x18001405c  lea     rax, [rbp+57h+var_3C]
0x180014060  mov     [rbp+57h+var_28], r10
0x180014064  mov     [rsp+0C0h+var_48], rax
0x180014069  mov     rcx, r9
0x18001406c  lea     rax, [rbp+57h+arg_0]
0x180014070  mov     [rbp+57h+var_20], r11
0x180014074  mov     [rsp+0C0h+var_50], rax
0x180014079  lea     rax, [rbp+57h+arg_10]
0x18001407d  mov     [rsp+0C0h+var_58], rax
0x180014082  lea     rax, [rbp+57h+arg_18]
0x180014086  mov     [rsp+0C0h+var_60], rax
0x18001408b  lea     rax, [rbp+57h+var_40]
0x18001408f  mov     [rsp+0C0h+var_68], rax
0x180014094  lea     rax, [rbp+57h+var_3F]
0x180014098  mov     [rsp+0C0h+var_70], rax
0x18001409d  lea     rax, [rbp+57h+var_3E]
0x1800140a1  mov     [rsp+0C0h+var_78], rax
0x1800140a6  lea     rax, [rbp+57h+var_38]
0x1800140aa  mov     [rsp+0C0h+var_80], rax
0x1800140af  lea     rax, [rbp+57h+var_30]
0x1800140b3  mov     [rsp+0C0h+var_88], rax
0x1800140b8  lea     rax, [rbp+57h+var_28]
0x1800140bc  mov     [rsp+0C0h+var_90], rax
0x1800140c1  lea     rax, [rbp+57h+var_20]
0x1800140c5  mov     [rsp+0C0h+var_98], rax
0x1800140ca  lea     rax, [rbp+57h+var_18]
0x1800140ce  mov     [rsp+0C0h+var_A0], rax
0x1800140d3  mov     [rbp+57h+var_18], 2000000h
0x1800140db  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$00@@U4@U4@U4@U4@U4@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$00@@66666AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x1800140e0  add     rsp, 0B0h
0x1800140e7  pop     rdi
0x1800140e8  pop     rbx
0x1800140e9  pop     rbp
0x1800140ea  retn
```
