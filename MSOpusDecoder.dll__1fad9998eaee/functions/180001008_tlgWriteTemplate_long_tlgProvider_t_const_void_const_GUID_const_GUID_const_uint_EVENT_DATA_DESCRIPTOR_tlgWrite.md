# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800010c0`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bf50`

## callees

- `0x180001008`
- `0x1800011dc`
- `0x1800018f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int16 **a6,
        __int64 a7,
        __int64 a8)
{
  __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+50h] [rbp-19h]
  __int64 v14; // [rsp+58h] [rbp-11h]
  __int16 *v15; // [rsp+60h] [rbp-9h]
  int v16; // [rsp+68h] [rbp-1h]
  int v17; // [rsp+6Ch] [rbp+3h]
  __int64 v18; // [rsp+70h] [rbp+7h]
  __int64 v19; // [rsp+78h] [rbp+Fh]
  __int64 v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]

  v20 = a8;
  v18 = a7;
  v21 = 4;
  v19 = 8;
  v8 = *a6;
  if ( *a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v8 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v8 = &word_18002F8BE;
    v10 = 1;
  }
  v16 = v10;
  v13 = a5;
  v15 = v8;
  v17 = 0;
  v14 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180035090, a2, 0, 0, 6u, &v12);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-37h]
0x18000100f  sub     rsp, 0A0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+37h+var_10], rax
0x180001024  mov     rax, [rbp+37h+arg_38]
0x180001028  xor     r8d, r8d
0x18000102b  mov     [rbp+37h+var_20], rax
0x18000102f  mov     rax, [rbp+37h+arg_30]
0x180001033  mov     [rbp+37h+var_30], rax
0x180001037  mov     rax, [rbp+37h+arg_28]
0x18000103b  mov     [rbp+37h+var_18], 4
0x180001043  mov     [rbp+37h+var_28], 8
0x18000104b  mov     rcx, [rax]
0x18000104e  test    rcx, rcx
0x180001051  jz      short loc_180001064
0x180001053  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001057  inc     rax
0x18000105a  cmp     [rcx+rax], r8b
0x18000105e  jnz     short loc_180001057
0x180001060  inc     eax
0x180001062  jmp     short loc_180001070
0x180001064  lea     rcx, word_18002F8BE
0x18000106b  mov     eax, 1
0x180001070  mov     [rbp+37h+var_38], eax
0x180001073  xor     r9d, r9d
0x180001076  mov     rax, [rbp+37h+arg_20]
0x18000107a  mov     [rbp+37h+var_50], rax
0x18000107e  lea     rax, [rbp+37h+var_70]
0x180001082  mov     [rbp+37h+var_40], rcx
0x180001086  lea     rcx, dword_180035090
0x18000108d  mov     [rsp+0A0h+var_78], rax
0x180001092  mov     [rsp+0A0h+var_80], 6
0x18000109a  mov     [rbp+37h+var_34], r8d
0x18000109e  mov     [rbp+37h+var_48], 8
0x1800010a6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010ab  mov     rcx, [rbp+37h+var_10]
0x1800010af  xor     rcx, rsp; StackCookie
0x1800010b2  call    __security_check_cookie
0x1800010b7  add     rsp, 0A0h
0x1800010be  pop     rbp
0x1800010bf  retn
```
