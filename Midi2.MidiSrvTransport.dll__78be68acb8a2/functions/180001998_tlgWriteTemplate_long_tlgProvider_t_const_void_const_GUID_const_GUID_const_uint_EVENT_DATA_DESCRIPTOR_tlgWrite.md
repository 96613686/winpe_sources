# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001998`
- end: `0x180001ab6`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@54@Z`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c480`
- `0x180013bf4`

## callees

- `0x18000163c`
- `0x180001998`
- `0x180002470`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 **a7,
        __int64 **a8,
        __int64 a9)
{
  __int64 v11; // rcx
  int v12; // r8d
  __int64 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  __int64 *v16; // rdx
  __int64 v17; // rax
  const unsigned __int16 *v18; // rdx
  int v19; // ecx
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-31h]
  int v23; // [rsp+58h] [rbp-29h]
  int v24; // [rsp+5Ch] [rbp-25h]
  __int64 v25; // [rsp+60h] [rbp-21h]
  __int64 v26; // [rsp+68h] [rbp-19h]
  __int64 *v27; // [rsp+70h] [rbp-11h]
  int v28; // [rsp+78h] [rbp-9h]
  int v29; // [rsp+7Ch] [rbp-5h]
  __int64 *v30; // [rsp+80h] [rbp-1h]
  int v31; // [rsp+88h] [rbp+7h]
  int v32; // [rsp+8Ch] [rbp+Bh]
  __int64 v33; // [rsp+90h] [rbp+Fh]
  __int64 v34; // [rsp+98h] [rbp+17h]

  v33 = a9;
  v11 = -1;
  v34 = 8;
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
    v13 = qword_180017FF0;
    v15 = 2;
  }
  v31 = v15;
  v30 = v13;
  v32 = 0;
  v16 = *a7;
  if ( *a7 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v16 + v17) );
    v12 = 2 * v17 + 2;
  }
  else
  {
    v16 = qword_180017FF0;
  }
  v25 = a6;
  v27 = v16;
  v28 = v12;
  v29 = 0;
  v18 = *a5;
  v26 = 8;
  if ( v18 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v18 + v11) );
    v19 = v11 + 1;
  }
  else
  {
    v18 = &word_18001783A;
    v19 = 1;
  }
  v22 = v18;
  v23 = v19;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 7u, &v21);
}

```

## disassembly

```asm
0x180001998  push    rbp
0x18000199a  lea     rbp, [rsp-2Fh]
0x18000199f  sub     rsp, 0B0h
0x1800019a6  mov     rax, cs:__security_cookie
0x1800019ad  xor     rax, rsp
0x1800019b0  mov     [rbp+2Fh+var_10], rax
0x1800019b4  mov     rax, [rbp+2Fh+arg_40]
0x1800019b8  xor     r9d, r9d
0x1800019bb  mov     [rbp+2Fh+var_20], rax
0x1800019bf  mov     r11, rdx
0x1800019c2  mov     rax, [rbp+2Fh+arg_38]
0x1800019c6  mov     r10, rcx
0x1800019c9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800019cd  mov     [rbp+2Fh+var_18], 8
0x1800019d5  lea     r8d, [r9+2]
0x1800019d9  mov     rdx, [rax]
0x1800019dc  test    rdx, rdx
0x1800019df  jz      short loc_1800019F7
0x1800019e1  mov     rax, rcx
0x1800019e4  inc     rax
0x1800019e7  cmp     [rdx+rax*2], r9w
0x1800019ec  jnz     short loc_1800019E4
0x1800019ee  lea     eax, ds:2[rax*2]
0x1800019f5  jmp     short loc_180001A01
0x1800019f7  lea     rdx, qword_180017FF0
0x1800019fe  mov     eax, r8d
0x180001a01  mov     [rbp+2Fh+var_28], eax
0x180001a04  mov     rax, [rbp+2Fh+arg_30]
0x180001a08  mov     [rbp+2Fh+var_30], rdx
0x180001a0c  mov     [rbp+2Fh+var_24], r9d
0x180001a10  mov     rdx, [rax]
0x180001a13  test    rdx, rdx
0x180001a16  jz      short loc_180001A2F
0x180001a18  mov     rax, rcx
0x180001a1b  inc     rax
0x180001a1e  cmp     [rdx+rax*2], r9w
0x180001a23  jnz     short loc_180001A1B
0x180001a25  lea     r8d, ds:2[rax*2]
0x180001a2d  jmp     short loc_180001A36
0x180001a2f  lea     rdx, qword_180017FF0
0x180001a36  mov     rax, [rbp+2Fh+arg_28]
0x180001a3a  mov     [rbp+2Fh+var_50], rax
0x180001a3e  mov     rax, [rbp+2Fh+arg_20]
0x180001a42  mov     [rbp+2Fh+var_40], rdx
0x180001a46  mov     [rbp+2Fh+var_38], r8d
0x180001a4a  mov     [rbp+2Fh+var_34], r9d
0x180001a4e  mov     rdx, [rax]
0x180001a51  mov     [rbp+2Fh+var_48], 8
0x180001a59  test    rdx, rdx
0x180001a5c  jz      short loc_180001A6B
0x180001a5e  inc     rcx
0x180001a61  cmp     [rdx+rcx], r9b
0x180001a65  jnz     short loc_180001A5E
0x180001a67  inc     ecx
0x180001a69  jmp     short loc_180001A77
0x180001a6b  lea     rdx, word_18001783A
0x180001a72  mov     ecx, 1
0x180001a77  lea     rax, [rbp+2Fh+var_80]
0x180001a7b  mov     [rbp+2Fh+var_60], rdx
0x180001a7f  mov     [rbp+2Fh+var_58], ecx
0x180001a82  xor     r8d, r8d
0x180001a85  mov     [rsp+0B0h+var_88], rax
0x180001a8a  mov     rdx, r11
0x180001a8d  mov     rcx, r10
0x180001a90  mov     [rsp+0B0h+var_90], 7
0x180001a98  mov     [rbp+2Fh+var_54], r9d
0x180001a9c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001aa1  mov     rcx, [rbp+2Fh+var_10]
0x180001aa5  xor     rcx, rsp; StackCookie
0x180001aa8  call    __security_check_cookie
0x180001aad  add     rsp, 0B0h
0x180001ab4  pop     rbp
0x180001ab5  retn
```
