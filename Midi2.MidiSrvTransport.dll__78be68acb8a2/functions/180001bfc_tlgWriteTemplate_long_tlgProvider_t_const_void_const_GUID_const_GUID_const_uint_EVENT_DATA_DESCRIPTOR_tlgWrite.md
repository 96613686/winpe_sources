# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001bfc`
- end: `0x180001d01`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@66@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010cc0`

## callees

- `0x18000163c`
- `0x180001bfc`
- `0x180002470`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v12; // rcx
  __int64 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  int v17; // ecx
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v20; // [rsp+50h] [rbp-49h]
  int v21; // [rsp+58h] [rbp-41h]
  int v22; // [rsp+5Ch] [rbp-3Dh]
  __int64 v23; // [rsp+60h] [rbp-39h]
  __int64 v24; // [rsp+68h] [rbp-31h]
  __int64 *v25; // [rsp+70h] [rbp-29h]
  int v26; // [rsp+78h] [rbp-21h]
  int v27; // [rsp+7Ch] [rbp-1Dh]
  __int64 v28; // [rsp+80h] [rbp-19h]
  __int64 v29; // [rsp+88h] [rbp-11h]
  __int64 v30; // [rsp+90h] [rbp-9h]
  __int64 v31; // [rsp+98h] [rbp-1h]
  __int64 v32; // [rsp+A0h] [rbp+7h]
  __int64 v33; // [rsp+A8h] [rbp+Fh]

  v32 = a10;
  v30 = a9;
  v12 = -1;
  v28 = a8;
  v33 = 4;
  v31 = 4;
  v29 = 4;
  v13 = *a7;
  if ( *a7 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = qword_180017FF0;
    v15 = 2;
  }
  v26 = v15;
  v23 = a6;
  v25 = v13;
  v27 = 0;
  v24 = 8;
  v16 = *a5;
  if ( *a5 )
  {
    do
      ++v12;
    while ( *((_BYTE *)v16 + v12) );
    v17 = v12 + 1;
  }
  else
  {
    v16 = &word_18001783A;
    v17 = 1;
  }
  v20 = v16;
  v21 = v17;
  v22 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 8u, &v19);
}

```

## disassembly

```asm
0x180001bfc  push    rbp
0x180001bfe  lea     rbp, [rsp-27h]
0x180001c03  sub     rsp, 0C0h
0x180001c0a  mov     rax, cs:__security_cookie
0x180001c11  xor     rax, rsp
0x180001c14  mov     [rbp+27h+var_10], rax
0x180001c18  mov     rax, [rbp+27h+arg_48]
0x180001c1c  mov     r11, rdx
0x180001c1f  mov     [rbp+27h+var_20], rax
0x180001c23  mov     r10, rcx
0x180001c26  mov     rax, [rbp+27h+arg_40]
0x180001c2a  xor     r8d, r8d
0x180001c2d  mov     [rbp+27h+var_30], rax
0x180001c31  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001c35  mov     rax, [rbp+27h+arg_38]
0x180001c39  mov     [rbp+27h+var_40], rax
0x180001c3d  mov     rax, [rbp+27h+arg_30]
0x180001c41  mov     [rbp+27h+var_18], 4
0x180001c49  mov     [rbp+27h+var_28], 4
0x180001c51  mov     [rbp+27h+var_38], 4
0x180001c59  mov     rdx, [rax]
0x180001c5c  test    rdx, rdx
0x180001c5f  jz      short loc_180001C77
0x180001c61  mov     rax, rcx
0x180001c64  inc     rax
0x180001c67  cmp     [rdx+rax*2], r8w
0x180001c6c  jnz     short loc_180001C64
0x180001c6e  lea     eax, ds:2[rax*2]
0x180001c75  jmp     short loc_180001C83
0x180001c77  lea     rdx, qword_180017FF0
0x180001c7e  mov     eax, 2
0x180001c83  mov     [rbp+27h+var_48], eax
0x180001c86  mov     r9d, 8
0x180001c8c  mov     rax, [rbp+27h+arg_28]
0x180001c90  mov     [rbp+27h+var_60], rax
0x180001c94  mov     rax, [rbp+27h+arg_20]
0x180001c98  mov     [rbp+27h+var_50], rdx
0x180001c9c  mov     [rbp+27h+var_44], r8d
0x180001ca0  mov     [rbp+27h+var_58], r9
0x180001ca4  mov     rdx, [rax]
0x180001ca7  test    rdx, rdx
0x180001caa  jz      short loc_180001CB9
0x180001cac  inc     rcx
0x180001caf  cmp     [rdx+rcx], r8b
0x180001cb3  jnz     short loc_180001CAC
0x180001cb5  inc     ecx
0x180001cb7  jmp     short loc_180001CC5
0x180001cb9  lea     rdx, word_18001783A
0x180001cc0  mov     ecx, 1
0x180001cc5  lea     rax, [rbp+27h+var_90]
0x180001cc9  mov     [rbp+27h+var_70], rdx
0x180001ccd  mov     [rsp+0C0h+var_98], rax
0x180001cd2  mov     rdx, r11
0x180001cd5  mov     [rsp+0C0h+var_A0], r9d
0x180001cda  xor     r9d, r9d
0x180001cdd  mov     [rbp+27h+var_68], ecx
0x180001ce0  mov     rcx, r10
0x180001ce3  mov     [rbp+27h+var_64], r8d
0x180001ce7  call    _tlgWriteTransfer_EventWriteTransfer
0x180001cec  mov     rcx, [rbp+27h+var_10]
0x180001cf0  xor     rcx, rsp; StackCookie
0x180001cf3  call    __security_check_cookie
0x180001cf8  add     rsp, 0C0h
0x180001cff  pop     rbp
0x180001d00  retn
```
