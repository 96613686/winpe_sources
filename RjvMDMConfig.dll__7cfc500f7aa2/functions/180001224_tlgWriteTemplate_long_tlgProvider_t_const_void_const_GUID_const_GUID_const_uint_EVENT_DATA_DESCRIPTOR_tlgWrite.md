# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x180001224`
- end: `0x180001308`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bde0`

## callees

- `0x180001224`
- `0x1800014a4`
- `0x180001c60`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        __int64 a7,
        const unsigned __int16 **a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-39h] BYREF
  __int64 v17; // [rsp+50h] [rbp-19h]
  __int64 v18; // [rsp+58h] [rbp-11h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-9h]
  int v20; // [rsp+68h] [rbp-1h]
  int v21; // [rsp+6Ch] [rbp+3h]
  __int64 v22; // [rsp+70h] [rbp+7h]
  __int64 v23; // [rsp+78h] [rbp+Fh]
  const unsigned __int16 *v24; // [rsp+80h] [rbp+17h]
  int v25; // [rsp+88h] [rbp+1Fh]
  int v26; // [rsp+8Ch] [rbp+23h]

  v9 = -1;
  v10 = 1;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &qword_180020258;
    v13 = 1;
  }
  v25 = v13;
  v22 = a7;
  v24 = v11;
  v26 = 0;
  v23 = 8;
  v14 = *a6;
  if ( *a6 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v14 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v14 = &qword_180020258;
  }
  v17 = a5;
  v19 = v14;
  v20 = v10;
  v21 = 0;
  v18 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180029000, a2, 0, 0, 6u, &v16);
}

```

## disassembly

```asm
0x180001224  push    rbp
0x180001226  lea     rbp, [rsp-37h]
0x18000122b  sub     rsp, 0A0h
0x180001232  mov     rax, cs:__security_cookie
0x180001239  xor     rax, rsp
0x18000123c  mov     [rbp+37h+var_10], rax
0x180001240  mov     rax, [rbp+37h+arg_38]
0x180001244  mov     r10, rdx
0x180001247  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000124b  xor     r9d, r9d
0x18000124e  mov     r8d, 1
0x180001254  mov     rdx, [rax]
0x180001257  test    rdx, rdx
0x18000125a  jz      short loc_18000126C
0x18000125c  mov     rax, rcx
0x18000125f  inc     rax
0x180001262  cmp     [rdx+rax], r9b
0x180001266  jnz     short loc_18000125F
0x180001268  inc     eax
0x18000126a  jmp     short loc_180001276
0x18000126c  lea     rdx, qword_180020258
0x180001273  mov     eax, r8d
0x180001276  mov     [rbp+37h+var_18], eax
0x180001279  mov     rax, [rbp+37h+arg_30]
0x18000127d  mov     [rbp+37h+var_30], rax
0x180001281  mov     rax, [rbp+37h+arg_28]
0x180001285  mov     [rbp+37h+var_20], rdx
0x180001289  mov     [rbp+37h+var_14], r9d
0x18000128d  mov     [rbp+37h+var_28], 8
0x180001295  mov     rdx, [rax]
0x180001298  test    rdx, rdx
0x18000129b  jz      short loc_1800012AC
0x18000129d  inc     rcx
0x1800012a0  cmp     [rdx+rcx], r9b
0x1800012a4  jnz     short loc_18000129D
0x1800012a6  lea     r8d, [rcx+1]
0x1800012aa  jmp     short loc_1800012B3
0x1800012ac  lea     rdx, qword_180020258
0x1800012b3  mov     rax, [rbp+37h+arg_20]
0x1800012b7  lea     rcx, dword_180029000
0x1800012be  mov     [rbp+37h+var_50], rax
0x1800012c2  lea     rax, [rbp+37h+var_70]
0x1800012c6  mov     [rbp+37h+var_40], rdx
0x1800012ca  mov     rdx, r10
0x1800012cd  mov     [rbp+37h+var_38], r8d
0x1800012d1  xor     r8d, r8d
0x1800012d4  mov     [rsp+0A0h+var_78], rax
0x1800012d9  mov     [rsp+0A0h+var_80], 6
0x1800012e1  mov     [rbp+37h+var_34], r9d
0x1800012e5  mov     [rbp+37h+var_48], 4
0x1800012ed  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012f2  mov     rcx, [rbp+37h+var_10]
0x1800012f6  xor     rcx, rsp; StackCookie
0x1800012f9  call    __security_check_cookie
0x1800012fe  add     rsp, 0A0h
0x180001305  pop     rbp
0x180001306  retn
```
