# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x140002188`
- end: `0x14000226c`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018890`

## callees

- `0x140001f60`
- `0x140002188`
- `0x1400029c0`

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
    v11 = &byte_14001BCA1;
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
    v14 = &byte_14001BCA1;
  }
  v17 = a5;
  v19 = v14;
  v20 = v10;
  v21 = 0;
  v18 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140025000, a2, 0, 0, 6u, &v16);
}

```

## disassembly

```asm
0x140002188  push    rbp
0x14000218a  lea     rbp, [rsp-37h]
0x14000218f  sub     rsp, 0A0h
0x140002196  mov     rax, cs:__security_cookie
0x14000219d  xor     rax, rsp
0x1400021a0  mov     [rbp+37h+var_10], rax
0x1400021a4  mov     rax, [rbp+37h+arg_38]
0x1400021a8  mov     r10, rdx
0x1400021ab  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400021af  xor     r9d, r9d
0x1400021b2  mov     r8d, 1
0x1400021b8  mov     rdx, [rax]
0x1400021bb  test    rdx, rdx
0x1400021be  jz      short loc_1400021D0
0x1400021c0  mov     rax, rcx
0x1400021c3  inc     rax
0x1400021c6  cmp     [rdx+rax], r9b
0x1400021ca  jnz     short loc_1400021C3
0x1400021cc  inc     eax
0x1400021ce  jmp     short loc_1400021DA
0x1400021d0  lea     rdx, byte_14001BCA1
0x1400021d7  mov     eax, r8d
0x1400021da  mov     [rbp+37h+var_18], eax
0x1400021dd  mov     rax, [rbp+37h+arg_30]
0x1400021e1  mov     [rbp+37h+var_30], rax
0x1400021e5  mov     rax, [rbp+37h+arg_28]
0x1400021e9  mov     [rbp+37h+var_20], rdx
0x1400021ed  mov     [rbp+37h+var_14], r9d
0x1400021f1  mov     [rbp+37h+var_28], 8
0x1400021f9  mov     rdx, [rax]
0x1400021fc  test    rdx, rdx
0x1400021ff  jz      short loc_140002210
0x140002201  inc     rcx
0x140002204  cmp     [rdx+rcx], r9b
0x140002208  jnz     short loc_140002201
0x14000220a  lea     r8d, [rcx+1]
0x14000220e  jmp     short loc_140002217
0x140002210  lea     rdx, byte_14001BCA1
0x140002217  mov     rax, [rbp+37h+arg_20]
0x14000221b  lea     rcx, dword_140025000
0x140002222  mov     [rbp+37h+var_50], rax
0x140002226  lea     rax, [rbp+37h+var_70]
0x14000222a  mov     [rbp+37h+var_40], rdx
0x14000222e  mov     rdx, r10
0x140002231  mov     [rbp+37h+var_38], r8d
0x140002235  xor     r8d, r8d
0x140002238  mov     [rsp+0A0h+var_78], rax
0x14000223d  mov     [rsp+0A0h+var_80], 6
0x140002245  mov     [rbp+37h+var_34], r9d
0x140002249  mov     [rbp+37h+var_48], 4
0x140002251  call    _tlgWriteTransfer_EventWriteTransfer
0x140002256  mov     rcx, [rbp+37h+var_10]
0x14000225a  xor     rcx, rsp; StackCookie
0x14000225d  call    __security_check_cookie
0x140002262  add     rsp, 0A0h
0x140002269  pop     rbp
0x14000226a  retn
```
