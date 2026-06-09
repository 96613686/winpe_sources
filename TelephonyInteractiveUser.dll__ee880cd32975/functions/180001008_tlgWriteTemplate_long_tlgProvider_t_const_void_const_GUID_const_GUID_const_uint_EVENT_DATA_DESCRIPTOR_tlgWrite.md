# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800010c0`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z`
- size: `184`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180004480`
- `0x180005090`
- `0x180005130`
- `0x1800051c0`
- `0x18000f3e8`
- `0x18000f478`
- `0x18000f500`
- `0x180012170`
- `0x180012208`
- `0x180012298`
- `0x180015f74`

## callees

- `0x180001008`
- `0x1800011fc`
- `0x180001dc0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8)
{
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+50h] [rbp-19h]
  __int64 v14; // [rsp+58h] [rbp-11h]
  __int64 v15; // [rsp+60h] [rbp-9h]
  __int64 v16; // [rsp+68h] [rbp-1h]
  const unsigned __int16 *v17; // [rsp+70h] [rbp+7h]
  int v18; // [rsp+78h] [rbp+Fh]
  int v19; // [rsp+7Ch] [rbp+13h]
  __int64 v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]

  v20 = a8;
  v21 = 4;
  v8 = *a7;
  if ( *a7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v8 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v8 = &qword_18001CE98;
    v10 = 1;
  }
  v18 = v10;
  v15 = a6;
  v13 = a5;
  v17 = v8;
  v19 = 0;
  v16 = 4;
  v14 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180025038, a2, 0, 0, 6u, &v12);
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
0x180001028  xor     r8d, r8d; int
0x18000102b  mov     [rbp+37h+var_20], rax
0x18000102f  mov     rax, [rbp+37h+arg_30]
0x180001033  mov     [rbp+37h+var_18], 4
0x18000103b  mov     rcx, [rax]
0x18000103e  test    rcx, rcx
0x180001041  jz      short loc_180001054
0x180001043  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001047  inc     rax
0x18000104a  cmp     [rcx+rax], r8b
0x18000104e  jnz     short loc_180001047
0x180001050  inc     eax
0x180001052  jmp     short loc_180001060
0x180001054  lea     rcx, qword_18001CE98
0x18000105b  mov     eax, 1
0x180001060  mov     [rbp+37h+var_28], eax
0x180001063  xor     r9d, r9d; int
0x180001066  mov     rax, [rbp+37h+arg_28]
0x18000106a  mov     [rbp+37h+var_40], rax
0x18000106e  mov     rax, [rbp+37h+arg_20]
0x180001072  mov     [rbp+37h+var_50], rax
0x180001076  lea     rax, [rbp+37h+var_70]
0x18000107a  mov     [rbp+37h+var_30], rcx
0x18000107e  lea     rcx, dword_180025038; int
0x180001085  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x18000108a  mov     [rsp+0A0h+var_80], 6; ULONG
0x180001092  mov     [rbp+37h+var_24], r8d
0x180001096  mov     [rbp+37h+var_38], 4
0x18000109e  mov     [rbp+37h+var_48], 8
0x1800010a6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010ab  mov     rcx, [rbp+37h+var_10]
0x1800010af  xor     rcx, rsp; StackCookie
0x1800010b2  call    __security_check_cookie
0x1800010b7  add     rsp, 0A0h
0x1800010be  pop     rbp
0x1800010bf  retn
```
