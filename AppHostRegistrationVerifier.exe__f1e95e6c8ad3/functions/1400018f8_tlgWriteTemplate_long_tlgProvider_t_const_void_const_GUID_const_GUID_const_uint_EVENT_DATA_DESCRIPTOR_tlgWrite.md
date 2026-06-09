# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400018f8`
- end: `0x1400019e7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z`
- size: `239`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, int **, int **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e0ec`
- `0x14000e1e0`

## callees

- `0x1400018f8`
- `0x140001b78`
- `0x140002210`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int **a7,
        int **a8)
{
  __int64 v10; // rcx
  int v12; // r8d
  int *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  int *v16; // rdx
  _BYTE v18[32]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v19; // [rsp+50h] [rbp-29h]
  __int64 v20; // [rsp+58h] [rbp-21h]
  __int64 v21; // [rsp+60h] [rbp-19h]
  __int64 v22; // [rsp+68h] [rbp-11h]
  int *v23; // [rsp+70h] [rbp-9h]
  int v24; // [rsp+78h] [rbp-1h]
  int v25; // [rsp+7Ch] [rbp+3h]
  int *v26; // [rsp+80h] [rbp+7h]
  int v27; // [rsp+88h] [rbp+Fh]
  int v28; // [rsp+8Ch] [rbp+13h]

  v10 = -1;
  v12 = 2;
  v13 = *a8;
  if ( *a8 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &dword_1400140E4;
    v15 = 2;
  }
  v27 = v15;
  v26 = v13;
  v28 = 0;
  v16 = *a7;
  if ( *a7 )
  {
    do
      ++v10;
    while ( *((_WORD *)v16 + v10) );
    v12 = 2 * v10 + 2;
  }
  else
  {
    v16 = &dword_1400140E4;
  }
  v21 = a6;
  v19 = a5;
  v23 = v16;
  v24 = v12;
  v25 = 0;
  v22 = 4;
  v20 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 6, v18);
}

```

## disassembly

```asm
0x1400018f8  push    rbp
0x1400018fa  push    rbx
0x1400018fb  push    rdi
0x1400018fc  lea     rbp, [rsp-27h]
0x140001901  sub     rsp, 0A0h
0x140001908  mov     rax, cs:__security_cookie
0x14000190f  xor     rax, rsp
0x140001912  mov     [rbp+37h+var_20], rax
0x140001916  mov     rax, [rbp+37h+arg_38]
0x14000191a  mov     r11, rdx
0x14000191d  mov     r10, rcx
0x140001920  xor     edi, edi
0x140001922  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001926  mov     rbx, r8
0x140001929  mov     r8d, 2
0x14000192f  mov     rdx, [rax]
0x140001932  test    rdx, rdx
0x140001935  jz      short loc_14000194C
0x140001937  mov     rax, rcx
0x14000193a  inc     rax
0x14000193d  cmp     [rdx+rax*2], di
0x140001941  jnz     short loc_14000193A
0x140001943  lea     eax, ds:2[rax*2]
0x14000194a  jmp     short loc_140001956
0x14000194c  lea     rdx, dword_1400140E4
0x140001953  mov     eax, r8d
0x140001956  mov     [rbp+37h+var_28], eax
0x140001959  mov     rax, [rbp+37h+arg_30]
0x14000195d  mov     [rbp+37h+var_30], rdx
0x140001961  mov     [rbp+37h+var_24], edi
0x140001964  mov     rdx, [rax]
0x140001967  test    rdx, rdx
0x14000196a  jz      short loc_14000197F
0x14000196c  inc     rcx
0x14000196f  cmp     [rdx+rcx*2], di
0x140001973  jnz     short loc_14000196C
0x140001975  lea     r8d, ds:2[rcx*2]
0x14000197d  jmp     short loc_140001986
0x14000197f  lea     rdx, dword_1400140E4
0x140001986  mov     rax, [rbp+37h+arg_28]
0x14000198a  mov     rcx, r10
0x14000198d  mov     [rbp+37h+var_50], rax
0x140001991  mov     rax, [rbp+37h+arg_20]
0x140001995  mov     [rbp+37h+var_60], rax
0x140001999  lea     rax, [rbp+37h+var_80]
0x14000199d  mov     [rbp+37h+var_40], rdx
0x1400019a1  mov     rdx, r11
0x1400019a4  mov     [rbp+37h+var_38], r8d
0x1400019a8  mov     r8, rbx
0x1400019ab  mov     [rsp+0B0h+var_88], rax
0x1400019b0  mov     [rsp+0B0h+var_90], 6
0x1400019b8  mov     [rbp+37h+var_34], edi
0x1400019bb  mov     [rbp+37h+var_48], 4
0x1400019c3  mov     [rbp+37h+var_58], 8
0x1400019cb  call    _tlgWriteTransfer_EventWriteTransfer
0x1400019d0  mov     rcx, [rbp+37h+var_20]
0x1400019d4  xor     rcx, rsp; StackCookie
0x1400019d7  call    __security_check_cookie
0x1400019dc  add     rsp, 0A0h
0x1400019e3  pop     rdi
0x1400019e4  pop     rbx
0x1400019e5  pop     rbp
0x1400019e6  retn
```
