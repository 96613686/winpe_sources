# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001fe0`
- end: `0x1400020cb`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011508`

## callees

- `0x14000198c`
- `0x140001fe0`
- `0x140002a30`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        const unsigned __int16 **a7,
        __int64 a8)
{
  __int64 v10; // rcx
  int v11; // r8d
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  _BYTE v17[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v18; // [rsp+50h] [rbp-19h]
  __int64 v19; // [rsp+58h] [rbp-11h]
  const unsigned __int16 *v20; // [rsp+60h] [rbp-9h]
  int v21; // [rsp+68h] [rbp-1h]
  int v22; // [rsp+6Ch] [rbp+3h]
  const unsigned __int16 *v23; // [rsp+70h] [rbp+7h]
  int v24; // [rsp+78h] [rbp+Fh]
  int v25; // [rsp+7Ch] [rbp+13h]
  __int64 v26; // [rsp+80h] [rbp+17h]
  __int64 v27; // [rsp+88h] [rbp+1Fh]

  v26 = a8;
  v10 = -1;
  v27 = 4;
  v11 = 2;
  v12 = *a7;
  if ( *a7 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &dword_1400158BC;
    v14 = 2;
  }
  v24 = v14;
  v23 = v12;
  v25 = 0;
  v15 = *a6;
  if ( *a6 )
  {
    do
      ++v10;
    while ( v15[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v15 = &dword_1400158BC;
  }
  v18 = a5;
  v20 = v15;
  v21 = v11;
  v22 = 0;
  v19 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 6, v17);
}

```

## disassembly

```asm
0x140001fe0  push    rbp
0x140001fe2  lea     rbp, [rsp-37h]
0x140001fe7  sub     rsp, 0A0h
0x140001fee  mov     rax, cs:__security_cookie
0x140001ff5  xor     rax, rsp
0x140001ff8  mov     [rbp+37h+var_10], rax
0x140001ffc  mov     rax, [rbp+37h+arg_38]
0x140002000  xor     r9d, r9d
0x140002003  mov     [rbp+37h+var_20], rax
0x140002007  mov     r11, rdx
0x14000200a  mov     rax, [rbp+37h+arg_30]
0x14000200e  mov     r10, rcx
0x140002011  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140002015  mov     [rbp+37h+var_18], 4
0x14000201d  lea     r8d, [r9+2]
0x140002021  mov     rdx, [rax]
0x140002024  test    rdx, rdx
0x140002027  jz      short loc_14000203F
0x140002029  mov     rax, rcx
0x14000202c  inc     rax
0x14000202f  cmp     [rdx+rax*2], r9w
0x140002034  jnz     short loc_14000202C
0x140002036  lea     eax, ds:2[rax*2]
0x14000203d  jmp     short loc_140002049
0x14000203f  lea     rdx, dword_1400158BC
0x140002046  mov     eax, r8d
0x140002049  mov     [rbp+37h+var_28], eax
0x14000204c  mov     rax, [rbp+37h+arg_28]
0x140002050  mov     [rbp+37h+var_30], rdx
0x140002054  mov     [rbp+37h+var_24], r9d
0x140002058  mov     rdx, [rax]
0x14000205b  test    rdx, rdx
0x14000205e  jz      short loc_140002074
0x140002060  inc     rcx
0x140002063  cmp     [rdx+rcx*2], r9w
0x140002068  jnz     short loc_140002060
0x14000206a  lea     r8d, ds:2[rcx*2]
0x140002072  jmp     short loc_14000207B
0x140002074  lea     rdx, dword_1400158BC
0x14000207b  mov     rax, [rbp+37h+arg_20]
0x14000207f  mov     rcx, r10
0x140002082  mov     [rbp+37h+var_50], rax
0x140002086  lea     rax, [rbp+37h+var_70]
0x14000208a  mov     [rbp+37h+var_40], rdx
0x14000208e  mov     rdx, r11
0x140002091  mov     [rbp+37h+var_38], r8d
0x140002095  xor     r8d, r8d
0x140002098  mov     [rsp+0A0h+var_78], rax
0x14000209d  mov     [rsp+0A0h+var_80], 6
0x1400020a5  mov     [rbp+37h+var_34], r9d
0x1400020a9  mov     [rbp+37h+var_48], 8
0x1400020b1  call    _tlgWriteTransfer_EventWriteTransfer
0x1400020b6  mov     rcx, [rbp+37h+var_10]
0x1400020ba  xor     rcx, rsp; StackCookie
0x1400020bd  call    __security_check_cookie
0x1400020c2  add     rsp, 0A0h
0x1400020c9  pop     rbp
0x1400020ca  retn
```
