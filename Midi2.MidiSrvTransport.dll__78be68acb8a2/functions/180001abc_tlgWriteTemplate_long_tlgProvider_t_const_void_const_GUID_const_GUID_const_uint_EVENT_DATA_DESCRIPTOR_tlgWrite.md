# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001abc`
- end: `0x180001bf5`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@44@Z`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010260`

## callees

- `0x18000163c`
- `0x180001abc`
- `0x180002470`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  __int64 v15; // rcx
  int v16; // r8d
  __int64 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rdx
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+30h] [rbp-B1h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-91h]
  int v24; // [rsp+58h] [rbp-89h]
  int v25; // [rsp+5Ch] [rbp-85h]
  __int64 v26; // [rsp+60h] [rbp-81h]
  __int64 v27; // [rsp+68h] [rbp-79h]
  __int64 *v28; // [rsp+70h] [rbp-71h]
  int v29; // [rsp+78h] [rbp-69h]
  int v30; // [rsp+7Ch] [rbp-65h]
  __int64 v31; // [rsp+80h] [rbp-61h]
  __int64 v32; // [rsp+88h] [rbp-59h]
  __int64 v33; // [rsp+90h] [rbp-51h]
  __int64 v34; // [rsp+98h] [rbp-49h]
  __int64 v35; // [rsp+A0h] [rbp-41h]
  __int64 v36; // [rsp+A8h] [rbp-39h]
  __int64 v37; // [rsp+B0h] [rbp-31h]
  __int64 v38; // [rsp+B8h] [rbp-29h]
  __int64 v39; // [rsp+C0h] [rbp-21h]
  __int64 v40; // [rsp+C8h] [rbp-19h]
  __int64 v41; // [rsp+D0h] [rbp-11h]
  __int64 v42; // [rsp+D8h] [rbp-9h]

  v41 = a13;
  v39 = a12;
  v15 = -1;
  v16 = 1;
  v37 = a11;
  v35 = a10;
  v33 = a9;
  v31 = a8;
  v42 = 8;
  v40 = 8;
  v38 = 1;
  v17 = *a7;
  v36 = 4;
  v34 = 4;
  v32 = 8;
  if ( v17 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = qword_180017FF0;
    v19 = 2;
  }
  v29 = v19;
  v26 = a6;
  v28 = v17;
  v30 = 0;
  v27 = 8;
  v20 = *a5;
  if ( *a5 )
  {
    do
      ++v15;
    while ( *((_BYTE *)v20 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v20 = &word_18001783A;
  }
  v23 = v20;
  v24 = v16;
  v25 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0xBu, &v22);
}

```

## disassembly

```asm
0x180001abc  push    rbp
0x180001abe  lea     rbp, [rsp-0Fh]
0x180001ac3  sub     rsp, 0F0h
0x180001aca  mov     rax, cs:__security_cookie
0x180001ad1  xor     rax, rsp
0x180001ad4  mov     [rbp+0Fh+var_10], rax
0x180001ad8  mov     rax, [rbp+0Fh+arg_60]
0x180001adc  xor     r9d, r9d
0x180001adf  mov     [rbp+0Fh+var_20], rax
0x180001ae3  mov     r11, rdx
0x180001ae6  mov     rax, [rbp+0Fh+arg_58]
0x180001aea  mov     r10, rcx
0x180001aed  mov     [rbp+0Fh+var_30], rax
0x180001af1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001af5  mov     rax, [rbp+0Fh+arg_50]
0x180001af9  lea     r8d, [r9+1]
0x180001afd  mov     [rbp+0Fh+var_40], rax
0x180001b01  mov     rax, [rbp+0Fh+arg_48]
0x180001b05  mov     [rbp+0Fh+var_50], rax
0x180001b09  mov     rax, [rbp+0Fh+arg_40]
0x180001b0d  mov     [rbp+0Fh+var_60], rax
0x180001b11  mov     rax, [rbp+0Fh+arg_38]
0x180001b15  mov     [rbp+0Fh+var_70], rax
0x180001b19  mov     rax, [rbp+0Fh+arg_30]
0x180001b1d  mov     [rbp+0Fh+var_18], 8
0x180001b25  mov     [rbp+0Fh+var_28], 8
0x180001b2d  mov     [rbp+0Fh+var_38], r8
0x180001b31  mov     rdx, [rax]
0x180001b34  mov     [rbp+0Fh+var_48], 4
0x180001b3c  mov     [rbp+0Fh+var_58], 4
0x180001b44  mov     [rbp+0Fh+var_68], 8
0x180001b4c  test    rdx, rdx
0x180001b4f  jz      short loc_180001B67
0x180001b51  mov     rax, rcx
0x180001b54  inc     rax
0x180001b57  cmp     [rdx+rax*2], r9w
0x180001b5c  jnz     short loc_180001B54
0x180001b5e  lea     eax, ds:2[rax*2]
0x180001b65  jmp     short loc_180001B73
0x180001b67  lea     rdx, qword_180017FF0
0x180001b6e  mov     eax, 2
0x180001b73  mov     [rbp+0Fh+var_78], eax
0x180001b76  mov     rax, [rbp+0Fh+arg_28]
0x180001b7a  mov     [rsp+0F0h+var_90], rax
0x180001b7f  mov     rax, [rbp+0Fh+arg_20]
0x180001b83  mov     [rbp+0Fh+var_80], rdx
0x180001b87  mov     [rbp+0Fh+var_74], r9d
0x180001b8b  mov     [rbp+0Fh+var_88], 8
0x180001b93  mov     rdx, [rax]
0x180001b96  test    rdx, rdx
0x180001b99  jz      short loc_180001BAA
0x180001b9b  inc     rcx
0x180001b9e  cmp     [rdx+rcx], r9b
0x180001ba2  jnz     short loc_180001B9B
0x180001ba4  lea     r8d, [rcx+1]
0x180001ba8  jmp     short loc_180001BB1
0x180001baa  lea     rdx, word_18001783A
0x180001bb1  lea     rax, [rsp+0F0h+var_C0]
0x180001bb6  mov     [rsp+0F0h+var_A0], rdx
0x180001bbb  mov     [rsp+0F0h+var_98], r8d
0x180001bc0  mov     rdx, r11
0x180001bc3  mov     [rsp+0F0h+var_C8], rax
0x180001bc8  xor     r8d, r8d
0x180001bcb  mov     rcx, r10
0x180001bce  mov     [rsp+0F0h+var_D0], 0Bh
0x180001bd6  mov     [rsp+0F0h+var_94], r9d
0x180001bdb  call    _tlgWriteTransfer_EventWriteTransfer
0x180001be0  mov     rcx, [rbp+0Fh+var_10]
0x180001be4  xor     rcx, rsp; StackCookie
0x180001be7  call    __security_check_cookie
0x180001bec  add     rsp, 0F0h
0x180001bf3  pop     rbp
0x180001bf4  retn
```
