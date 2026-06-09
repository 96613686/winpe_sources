# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001010`
- end: `0x18000111d`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800035d0`

## callees

- `0x180001010`
- `0x180001858`
- `0x180001ed0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        __int64 a7,
        void **a8)
{
  __int64 v8; // r8
  _WORD *v9; // rax
  __int64 v10; // r9
  int v12; // r9d
  const unsigned __int16 *v13; // r9
  int v14; // r8d
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-78h] BYREF
  __int64 v17; // [rsp+50h] [rbp-58h]
  __int64 v18; // [rsp+58h] [rbp-50h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-48h]
  int v20; // [rsp+68h] [rbp-40h]
  int v21; // [rsp+6Ch] [rbp-3Ch]
  __int64 v22; // [rsp+70h] [rbp-38h]
  __int64 v23; // [rsp+78h] [rbp-30h]
  _WORD *v24; // [rsp+80h] [rbp-28h]
  int v25; // [rsp+88h] [rbp-20h]
  int v26; // [rsp+8Ch] [rbp-1Ch]

  v8 = -1;
  v9 = *a8;
  if ( *a8 )
  {
    v10 = -1;
    while ( v9[++v10] != 0 )
      ;
    v12 = 2 * v10 + 2;
  }
  else
  {
    v9 = &unk_180012E8C;
    v12 = 2;
  }
  v24 = v9;
  v22 = a7;
  v25 = v12;
  v26 = 0;
  v23 = 4;
  v13 = *a6;
  if ( *a6 )
  {
    do
      ++v8;
    while ( *((_BYTE *)v13 + v8) );
    v14 = v8 + 1;
  }
  else
  {
    v13 = &word_180012E8A;
    v14 = 1;
  }
  v17 = a5;
  v19 = v13;
  v20 = v14;
  v21 = 0;
  v18 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 6u, &v16);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 0A8h
0x180001017  mov     rax, cs:__security_cookie
0x18000101e  xor     rax, rsp
0x180001021  mov     [rsp+0A8h+var_18], rax
0x180001029  mov     rax, [rsp+0A8h+arg_38]
0x180001031  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180001038  mov     rax, [rax]
0x18000103b  test    rax, rax
0x18000103e  jz      short loc_18000105A
0x180001040  mov     r9, r8
0x180001043  cmp     word ptr [rax+r9*2+2], 0
0x18000104a  lea     r9, [r9+1]
0x18000104e  jnz     short loc_180001043
0x180001050  lea     r9d, ds:2[r9*2]
0x180001058  jmp     short loc_180001067
0x18000105a  lea     rax, unk_180012E8C
0x180001061  mov     r9d, 2
0x180001067  mov     [rsp+0A8h+var_28], rax
0x18000106f  xor     r10d, r10d
0x180001072  mov     rax, [rsp+0A8h+arg_30]
0x18000107a  mov     [rsp+0A8h+var_38], rax
0x18000107f  mov     rax, [rsp+0A8h+arg_28]
0x180001087  mov     [rsp+0A8h+var_20], r9d
0x18000108f  mov     [rsp+0A8h+var_1C], r10d
0x180001097  mov     [rsp+0A8h+var_30], 4
0x1800010a0  mov     r9, [rax]
0x1800010a3  test    r9, r9
0x1800010a6  jz      short loc_1800010B6
0x1800010a8  inc     r8
0x1800010ab  cmp     [r9+r8], r10b
0x1800010af  jnz     short loc_1800010A8
0x1800010b1  inc     r8d
0x1800010b4  jmp     short loc_1800010C3
0x1800010b6  lea     r9, word_180012E8A
0x1800010bd  mov     r8d, 1
0x1800010c3  mov     rax, [rsp+0A8h+arg_20]
0x1800010cb  mov     [rsp+0A8h+var_58], rax
0x1800010d0  lea     rax, [rsp+0A8h+var_78]
0x1800010d5  mov     [rsp+0A8h+var_48], r9
0x1800010da  xor     r9d, r9d
0x1800010dd  mov     [rsp+0A8h+var_40], r8d
0x1800010e2  xor     r8d, r8d
0x1800010e5  mov     [rsp+0A8h+var_80], rax
0x1800010ea  mov     [rsp+0A8h+var_88], 6
0x1800010f2  mov     [rsp+0A8h+var_3C], r10d
0x1800010f7  mov     [rsp+0A8h+var_50], 4
0x180001100  call    _tlgWriteTransfer_EventWriteTransfer
0x180001105  mov     rcx, [rsp+0A8h+var_18]
0x18000110d  xor     rcx, rsp; StackCookie
0x180001110  call    __security_check_cookie
0x180001115  add     rsp, 0A8h
0x18000111c  retn
```
