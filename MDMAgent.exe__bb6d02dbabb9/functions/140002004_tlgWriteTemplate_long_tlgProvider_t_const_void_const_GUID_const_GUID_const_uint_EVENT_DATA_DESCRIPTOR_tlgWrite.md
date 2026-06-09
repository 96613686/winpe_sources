# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x140002004`
- end: `0x1400020dc`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018a48`

## callees

- `0x140001f60`
- `0x140002004`
- `0x1400029c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        const unsigned __int16 **a10)
{
  const unsigned __int16 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-69h] BYREF
  __int64 v15; // [rsp+50h] [rbp-49h]
  __int64 v16; // [rsp+58h] [rbp-41h]
  __int64 v17; // [rsp+60h] [rbp-39h]
  __int64 v18; // [rsp+68h] [rbp-31h]
  __int64 v19; // [rsp+70h] [rbp-29h]
  __int64 v20; // [rsp+78h] [rbp-21h]
  __int64 v21; // [rsp+80h] [rbp-19h]
  __int64 v22; // [rsp+88h] [rbp-11h]
  __int64 v23; // [rsp+90h] [rbp-9h]
  __int64 v24; // [rsp+98h] [rbp-1h]
  const unsigned __int16 *v25; // [rsp+A0h] [rbp+7h]
  int v26; // [rsp+A8h] [rbp+Fh]
  int v27; // [rsp+ACh] [rbp+13h]

  v10 = *a10;
  if ( *a10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_BYTE *)v10 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v10 = &byte_14001BCA1;
    v12 = 1;
  }
  v26 = v12;
  v23 = a9;
  v21 = a8;
  v19 = a7;
  v17 = a6;
  v15 = a5;
  v25 = v10;
  v24 = 8;
  v27 = 0;
  v22 = 4;
  v20 = 4;
  v18 = 4;
  v16 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140025000, a2, 0, 0, 8u, &v14);
}

```

## disassembly

```asm
0x140002004  push    rbp
0x140002006  lea     rbp, [rsp-27h]
0x14000200b  sub     rsp, 0C0h
0x140002012  mov     rax, cs:__security_cookie
0x140002019  xor     rax, rsp
0x14000201c  mov     [rbp+27h+var_10], rax
0x140002020  mov     rax, [rbp+27h+arg_48]
0x140002024  xor     r9d, r9d
0x140002027  mov     rcx, [rax]
0x14000202a  test    rcx, rcx
0x14000202d  jz      short loc_140002040
0x14000202f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002033  inc     rax
0x140002036  cmp     [rcx+rax], r9b
0x14000203a  jnz     short loc_140002033
0x14000203c  inc     eax
0x14000203e  jmp     short loc_14000204C
0x140002040  lea     rcx, byte_14001BCA1
0x140002047  mov     eax, 1
0x14000204c  mov     [rbp+27h+var_18], eax
0x14000204f  mov     r8d, 8
0x140002055  mov     rax, [rbp+27h+arg_40]
0x140002059  mov     [rbp+27h+var_30], rax
0x14000205d  mov     rax, [rbp+27h+arg_38]
0x140002061  mov     [rbp+27h+var_40], rax
0x140002065  mov     rax, [rbp+27h+arg_30]
0x140002069  mov     [rbp+27h+var_50], rax
0x14000206d  mov     rax, [rbp+27h+arg_28]
0x140002071  mov     [rbp+27h+var_60], rax
0x140002075  mov     rax, [rbp+27h+arg_20]
0x140002079  mov     [rbp+27h+var_70], rax
0x14000207d  lea     rax, [rbp+27h+var_90]
0x140002081  mov     [rsp+0C0h+var_98], rax
0x140002086  mov     [rsp+0C0h+var_A0], r8d
0x14000208b  mov     [rbp+27h+var_20], rcx
0x14000208f  lea     rcx, dword_140025000
0x140002096  mov     [rbp+27h+var_28], r8
0x14000209a  xor     r8d, r8d
0x14000209d  mov     [rbp+27h+var_14], r9d
0x1400020a1  mov     [rbp+27h+var_38], 4
0x1400020a9  mov     [rbp+27h+var_48], 4
0x1400020b1  mov     [rbp+27h+var_58], 4
0x1400020b9  mov     [rbp+27h+var_68], 4
0x1400020c1  call    _tlgWriteTransfer_EventWriteTransfer
0x1400020c6  mov     rcx, [rbp+27h+var_10]
0x1400020ca  xor     rcx, rsp; StackCookie
0x1400020cd  call    __security_check_cookie
0x1400020d2  add     rsp, 0C0h
0x1400020d9  pop     rbp
0x1400020da  retn
```
