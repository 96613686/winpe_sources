# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001630`
- end: `0x180001722`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@344@Z`
- size: `242`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180013d48`
- `0x180014070`
- `0x18001d384`
- `0x18001e09c`
- `0x18001e408`
- `0x18003b238`
- `0x18003dc00`
- `0x180041020`

## callees

- `0x180001414`
- `0x180001630`
- `0x18004c8e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 **a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  __int64 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // rdx
  _BYTE v17[32]; // [rsp+30h] [rbp-51h] BYREF
  __int64 *v18; // [rsp+50h] [rbp-31h]
  int v19; // [rsp+58h] [rbp-29h]
  int v20; // [rsp+5Ch] [rbp-25h]
  __int64 v21; // [rsp+60h] [rbp-21h]
  __int64 v22; // [rsp+68h] [rbp-19h]
  __int64 *v23; // [rsp+70h] [rbp-11h]
  int v24; // [rsp+78h] [rbp-9h]
  int v25; // [rsp+7Ch] [rbp-5h]
  __int64 v26; // [rsp+80h] [rbp-1h]
  __int64 v27; // [rsp+88h] [rbp+7h]
  __int64 v28; // [rsp+90h] [rbp+Fh]
  __int64 v29; // [rsp+98h] [rbp+17h]

  v28 = a9;
  v10 = -1;
  v26 = a8;
  v11 = 1;
  v29 = 4;
  v27 = 4;
  v12 = *a7;
  if ( *a7 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &qword_1800528B8;
    v14 = 1;
  }
  v24 = v14;
  v21 = a6;
  v23 = v12;
  v25 = 0;
  v22 = 4;
  v15 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( *((_BYTE *)v15 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v15 = &qword_1800528B8;
  }
  v18 = v15;
  v19 = v11;
  v20 = 0;
  return tlgWriteTransfer_GameInputEventWriteTransfer((__int64)&dword_180069000, a2, 0, 0, 7, (__int64)v17);
}

```

## disassembly

```asm
0x180001630  push    rbp
0x180001632  lea     rbp, [rsp-2Fh]
0x180001637  sub     rsp, 0B0h
0x18000163e  mov     rax, cs:__security_cookie
0x180001645  xor     rax, rsp
0x180001648  mov     [rbp+2Fh+var_10], rax
0x18000164c  mov     rax, [rbp+2Fh+arg_40]
0x180001650  xor     r9d, r9d
0x180001653  mov     [rbp+2Fh+var_20], rax
0x180001657  mov     r10, rdx
0x18000165a  mov     rax, [rbp+2Fh+arg_38]
0x18000165e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001662  mov     [rbp+2Fh+var_30], rax
0x180001666  mov     rax, [rbp+2Fh+arg_30]
0x18000166a  lea     r8d, [r9+1]
0x18000166e  mov     [rbp+2Fh+var_18], 4
0x180001676  mov     [rbp+2Fh+var_28], 4
0x18000167e  mov     rdx, [rax]
0x180001681  test    rdx, rdx
0x180001684  jz      short loc_180001696
0x180001686  mov     rax, rcx
0x180001689  inc     rax
0x18000168c  cmp     [rdx+rax], r9b
0x180001690  jnz     short loc_180001689
0x180001692  inc     eax
0x180001694  jmp     short loc_1800016A0
0x180001696  lea     rdx, qword_1800528B8
0x18000169d  mov     eax, r8d
0x1800016a0  mov     [rbp+2Fh+var_38], eax
0x1800016a3  mov     rax, [rbp+2Fh+arg_28]
0x1800016a7  mov     [rbp+2Fh+var_50], rax
0x1800016ab  mov     rax, [rbp+2Fh+arg_20]
0x1800016af  mov     [rbp+2Fh+var_40], rdx
0x1800016b3  mov     [rbp+2Fh+var_34], r9d
0x1800016b7  mov     [rbp+2Fh+var_48], 4
0x1800016bf  mov     rdx, [rax]
0x1800016c2  test    rdx, rdx
0x1800016c5  jz      short loc_1800016D6
0x1800016c7  inc     rcx
0x1800016ca  cmp     [rdx+rcx], r9b
0x1800016ce  jnz     short loc_1800016C7
0x1800016d0  lea     r8d, [rcx+1]
0x1800016d4  jmp     short loc_1800016DD
0x1800016d6  lea     rdx, qword_1800528B8
0x1800016dd  lea     rax, [rbp+2Fh+var_80]
0x1800016e1  mov     [rbp+2Fh+var_60], rdx
0x1800016e5  mov     [rbp+2Fh+var_58], r8d
0x1800016e9  lea     rcx, dword_180069000
0x1800016f0  mov     [rsp+0B0h+var_88], rax
0x1800016f5  xor     r8d, r8d
0x1800016f8  mov     rdx, r10
0x1800016fb  mov     [rsp+0B0h+var_90], 7
0x180001703  mov     [rbp+2Fh+var_54], r9d
0x180001707  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x18000170c  mov     rcx, [rbp+2Fh+var_10]
0x180001710  xor     rcx, rsp; StackCookie
0x180001713  call    __security_check_cookie
0x180001718  add     rsp, 0B0h
0x18000171f  pop     rbp
0x180001720  retn
```
