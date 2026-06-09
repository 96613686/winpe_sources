# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800010ea`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z`
- size: `226`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x180009050`
- `0x18000c2dc`
- `0x18000d480`
- `0x18000f180`
- `0x18001000c`
- `0x180016558`
- `0x18001a610`
- `0x18003197c`
- `0x18003dc00`
- `0x18004982c`
- `0x180049aa0`
- `0x180049bec`
- `0x18004aba0`
- `0x18004af00`
- `0x18004baec`
- `0x18004c42c`

## callees

- `0x180001008`
- `0x180001414`
- `0x18004c8e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 **a7,
        __int64 a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rdx
  _BYTE v16[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v17; // [rsp+50h] [rbp-19h]
  int v18; // [rsp+58h] [rbp-11h]
  int v19; // [rsp+5Ch] [rbp-Dh]
  __int64 v20; // [rsp+60h] [rbp-9h]
  __int64 v21; // [rsp+68h] [rbp-1h]
  __int64 *v22; // [rsp+70h] [rbp+7h]
  int v23; // [rsp+78h] [rbp+Fh]
  int v24; // [rsp+7Ch] [rbp+13h]
  __int64 v25; // [rsp+80h] [rbp+17h]
  __int64 v26; // [rsp+88h] [rbp+1Fh]

  v25 = a8;
  v9 = -1;
  v26 = 4;
  v10 = 1;
  v11 = *a7;
  if ( *a7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &qword_1800528B8;
    v13 = 1;
  }
  v23 = v13;
  v20 = a6;
  v22 = v11;
  v24 = 0;
  v21 = 4;
  v14 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v14 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v14 = &qword_1800528B8;
  }
  v17 = v14;
  v18 = v10;
  v19 = 0;
  return tlgWriteTransfer_GameInputEventWriteTransfer((__int64)&dword_180069000, a2, 0, 0, 6, (__int64)v16);
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
0x180001028  xor     r9d, r9d
0x18000102b  mov     [rbp+37h+var_20], rax
0x18000102f  mov     r10, rdx
0x180001032  mov     rax, [rbp+37h+arg_30]
0x180001036  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000103a  mov     [rbp+37h+var_18], 4
0x180001042  lea     r8d, [r9+1]
0x180001046  mov     rdx, [rax]
0x180001049  test    rdx, rdx
0x18000104c  jz      short loc_18000105E
0x18000104e  mov     rax, rcx
0x180001051  inc     rax
0x180001054  cmp     [rdx+rax], r9b
0x180001058  jnz     short loc_180001051
0x18000105a  inc     eax
0x18000105c  jmp     short loc_180001068
0x18000105e  lea     rdx, qword_1800528B8
0x180001065  mov     eax, r8d
0x180001068  mov     [rbp+37h+var_28], eax
0x18000106b  mov     rax, [rbp+37h+arg_28]
0x18000106f  mov     [rbp+37h+var_40], rax
0x180001073  mov     rax, [rbp+37h+arg_20]
0x180001077  mov     [rbp+37h+var_30], rdx
0x18000107b  mov     [rbp+37h+var_24], r9d
0x18000107f  mov     [rbp+37h+var_38], 4
0x180001087  mov     rdx, [rax]
0x18000108a  test    rdx, rdx
0x18000108d  jz      short loc_18000109E
0x18000108f  inc     rcx
0x180001092  cmp     [rdx+rcx], r9b
0x180001096  jnz     short loc_18000108F
0x180001098  lea     r8d, [rcx+1]
0x18000109c  jmp     short loc_1800010A5
0x18000109e  lea     rdx, qword_1800528B8
0x1800010a5  lea     rax, [rbp+37h+var_70]
0x1800010a9  mov     [rbp+37h+var_50], rdx
0x1800010ad  mov     [rbp+37h+var_48], r8d
0x1800010b1  lea     rcx, dword_180069000
0x1800010b8  mov     [rsp+0A0h+var_78], rax
0x1800010bd  xor     r8d, r8d
0x1800010c0  mov     rdx, r10
0x1800010c3  mov     [rsp+0A0h+var_80], 6
0x1800010cb  mov     [rbp+37h+var_44], r9d
0x1800010cf  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x1800010d4  mov     rcx, [rbp+37h+var_10]
0x1800010d8  xor     rcx, rsp; StackCookie
0x1800010db  call    __security_check_cookie
0x1800010e0  add     rsp, 0A0h
0x1800010e7  pop     rbp
0x1800010e8  retn
```
