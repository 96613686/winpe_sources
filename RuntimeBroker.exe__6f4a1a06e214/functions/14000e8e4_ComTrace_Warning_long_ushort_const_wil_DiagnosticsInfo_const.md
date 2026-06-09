# ComTrace::Warning_(long,ushort const *,wil::DiagnosticsInfo const &)

- ea: `0x14000e8e4`
- end: `0x14000e985`
- name: `?Warning_@ComTrace@@QEAAXJPEBGAEBUDiagnosticsInfo@wil@@@Z`
- size: `161`
- prototype: `void __fastcall(ComTrace *__hidden this, int, const unsigned __int16 *, const struct DiagnosticsInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000eb14`

## callees

- `0x1400010b8`
- `0x14000e06c`
- `0x14000e8e4`

## pseudocode

```c
void __fastcall ComTrace::Warning_(ComTrace *this, int a2, const size_t *a3, const struct DiagnosticsInfo *a4)
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
  v7 = ComTrace::Provider((__int64)this);
  if ( *(_DWORD *)v7 > 3u )
  {
    LOWORD(v15) = a4[3].cost;
    v11 = (const unsigned __int16 *)a4[1];
    v12 = (const unsigned __int16 *)a4[2];
    v13 = a3;
    v14 = 0;
    v10 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
      (__int64)v7,
      (unsigned __int8 *)&dword_14001474C,
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
0x14000e8e4  mov     [rsp-8+arg_0], rcx
0x14000e8e9  push    rbp
0x14000e8ea  push    rbx
0x14000e8eb  push    rsi
0x14000e8ec  push    rdi
0x14000e8ed  lea     rbp, [rsp-3Fh]
0x14000e8f2  sub     rsp, 88h
0x14000e8f9  mov     rbx, r9
0x14000e8fc  mov     rdi, r8
0x14000e8ff  mov     esi, edx
0x14000e901  call    ?Provider@ComTrace@@SAPEBU_tlgProvider_t@@XZ; ComTrace::Provider(void)
0x14000e906  mov     ecx, [rax]
0x14000e908  cmp     ecx, 3
0x14000e90b  jbe     short loc_14000E979
0x14000e90d  movzx   ecx, word ptr [rbx+18h]
0x14000e911  lea     rdx, dword_14001474C
0x14000e918  mov     word ptr [rbp+57h+arg_0], cx
0x14000e91c  mov     rcx, [rbx+8]
0x14000e920  mov     [rbp+57h+var_48], rcx
0x14000e924  mov     rcx, [rbx+10h]
0x14000e928  mov     [rbp+57h+var_40], rcx
0x14000e92c  lea     rcx, [rbp+57h+arg_0]
0x14000e930  mov     [rsp+0A0h+var_58], rcx
0x14000e935  lea     rcx, [rbp+57h+var_48]
0x14000e939  mov     [rsp+0A0h+var_60], rcx
0x14000e93e  lea     rcx, [rbp+57h+var_40]
0x14000e942  mov     [rsp+0A0h+var_68], rcx
0x14000e947  lea     rcx, [rbp+57h+var_38]
0x14000e94b  mov     [rsp+0A0h+var_70], rcx
0x14000e950  lea     rcx, [rbp+57h+var_30]
0x14000e954  mov     [rsp+0A0h+var_78], rcx
0x14000e959  lea     rcx, [rbp+57h+var_50]
0x14000e95d  mov     [rsp+0A0h+var_80], rcx
0x14000e962  mov     rcx, rax
0x14000e965  mov     [rbp+57h+var_38], rdi
0x14000e969  mov     [rbp+57h+var_30], 0
0x14000e971  mov     [rbp+57h+var_50], esi
0x14000e974  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &)
0x14000e979  add     rsp, 88h
0x14000e980  pop     rdi
0x14000e981  pop     rsi
0x14000e982  pop     rbx
0x14000e983  pop     rbp
0x14000e984  retn
```
