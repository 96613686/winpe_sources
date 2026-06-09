# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x14000216c`
- end: `0x14000224f`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `227`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017ba0`

## callees

- `0x140001f48`
- `0x14000216c`
- `0x140002930`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
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
  _BYTE v16[32]; // [rsp+30h] [rbp-39h] BYREF
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
    v11 = &byte_14001ACA1;
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
    v14 = &byte_14001ACA1;
  }
  v17 = a5;
  v19 = v14;
  v20 = v10;
  v21 = 0;
  v18 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140024000, a2, 0, 0, 6, v16);
}

```

## disassembly

```asm
0x14000216c  push    rbp
0x14000216e  lea     rbp, [rsp-37h]
0x140002173  sub     rsp, 0A0h
0x14000217a  mov     rax, cs:__security_cookie
0x140002181  xor     rax, rsp
0x140002184  mov     [rbp+37h+var_10], rax
0x140002188  mov     rax, [rbp+37h+arg_38]
0x14000218c  mov     r10, rdx
0x14000218f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140002193  xor     r9d, r9d
0x140002196  mov     r8d, 1
0x14000219c  mov     rdx, [rax]
0x14000219f  test    rdx, rdx
0x1400021a2  jz      short loc_1400021B4
0x1400021a4  mov     rax, rcx
0x1400021a7  inc     rax
0x1400021aa  cmp     [rdx+rax], r9b
0x1400021ae  jnz     short loc_1400021A7
0x1400021b0  inc     eax
0x1400021b2  jmp     short loc_1400021BE
0x1400021b4  lea     rdx, byte_14001ACA1
0x1400021bb  mov     eax, r8d
0x1400021be  mov     [rbp+37h+var_18], eax
0x1400021c1  mov     rax, [rbp+37h+arg_30]
0x1400021c5  mov     [rbp+37h+var_30], rax
0x1400021c9  mov     rax, [rbp+37h+arg_28]
0x1400021cd  mov     [rbp+37h+var_20], rdx
0x1400021d1  mov     [rbp+37h+var_14], r9d
0x1400021d5  mov     [rbp+37h+var_28], 8
0x1400021dd  mov     rdx, [rax]
0x1400021e0  test    rdx, rdx
0x1400021e3  jz      short loc_1400021F4
0x1400021e5  inc     rcx
0x1400021e8  cmp     [rdx+rcx], r9b
0x1400021ec  jnz     short loc_1400021E5
0x1400021ee  lea     r8d, [rcx+1]
0x1400021f2  jmp     short loc_1400021FB
0x1400021f4  lea     rdx, byte_14001ACA1
0x1400021fb  mov     rax, [rbp+37h+arg_20]
0x1400021ff  lea     rcx, dword_140024000
0x140002206  mov     [rbp+37h+var_50], rax
0x14000220a  lea     rax, [rbp+37h+var_70]
0x14000220e  mov     [rbp+37h+var_40], rdx
0x140002212  mov     rdx, r10
0x140002215  mov     [rbp+37h+var_38], r8d
0x140002219  xor     r8d, r8d
0x14000221c  mov     [rsp+0A0h+var_78], rax
0x140002221  mov     [rsp+0A0h+var_80], 6
0x140002229  mov     [rbp+37h+var_34], r9d
0x14000222d  mov     [rbp+37h+var_48], 4
0x140002235  call    _tlgWriteTransfer_EventWriteTransfer
0x14000223a  mov     rcx, [rbp+37h+var_10]
0x14000223e  xor     rcx, rsp; StackCookie
0x140002241  call    __security_check_cookie
0x140002246  add     rsp, 0A0h
0x14000224d  pop     rbp
0x14000224e  retn
```
