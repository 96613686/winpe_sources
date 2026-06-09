# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)

- ea: `0x180001ab8`
- end: `0x180001c0a`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@U4@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@64AEBU?$_tlgWrapperByRef@$0BA@@@@Z`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b5f0`

## callees

- `0x18000163c`
- `0x180001ab8`
- `0x1800038f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const wchar_t **a7,
        const wchar_t **a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 *a12)
{
  __int64 v14; // rcx
  int v15; // r8d
  __int64 v16; // rcx
  const wchar_t *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  const wchar_t *v20; // rdx
  __int64 v21; // rax
  const unsigned __int16 *v22; // rdx
  int v23; // ecx
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+30h] [rbp-99h] BYREF
  const unsigned __int16 *v26; // [rsp+50h] [rbp-79h]
  int v27; // [rsp+58h] [rbp-71h]
  int v28; // [rsp+5Ch] [rbp-6Dh]
  __int64 v29; // [rsp+60h] [rbp-69h]
  __int64 v30; // [rsp+68h] [rbp-61h]
  const wchar_t *v31; // [rsp+70h] [rbp-59h]
  int v32; // [rsp+78h] [rbp-51h]
  int v33; // [rsp+7Ch] [rbp-4Dh]
  const wchar_t *v34; // [rsp+80h] [rbp-49h]
  int v35; // [rsp+88h] [rbp-41h]
  int v36; // [rsp+8Ch] [rbp-3Dh]
  __int64 v37; // [rsp+90h] [rbp-39h]
  __int64 v38; // [rsp+98h] [rbp-31h]
  __int64 v39; // [rsp+A0h] [rbp-29h]
  __int64 v40; // [rsp+A8h] [rbp-21h]
  __int64 v41; // [rsp+B0h] [rbp-19h]
  __int64 v42; // [rsp+B8h] [rbp-11h]
  __int64 v43; // [rsp+C0h] [rbp-9h]
  __int64 v44; // [rsp+C8h] [rbp-1h]

  v44 = 16;
  v42 = 8;
  v40 = 4;
  v14 = *a12;
  v15 = 2;
  v41 = a11;
  v39 = a10;
  v37 = a9;
  v43 = v14;
  v16 = -1;
  v38 = 4;
  v17 = *a8;
  if ( *a8 )
  {
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = &S2;
    v19 = 2;
  }
  v35 = v19;
  v34 = v17;
  v36 = 0;
  v20 = *a7;
  if ( *a7 )
  {
    v21 = -1;
    do
      ++v21;
    while ( v20[v21] );
    v15 = 2 * v21 + 2;
  }
  else
  {
    v20 = &S2;
  }
  v29 = a6;
  v31 = v20;
  v32 = v15;
  v33 = 0;
  v22 = *a5;
  v30 = 8;
  if ( v22 )
  {
    do
      ++v16;
    while ( *((_BYTE *)v22 + v16) );
    v23 = v16 + 1;
  }
  else
  {
    v22 = &word_18002377A;
    v23 = 1;
  }
  v26 = v22;
  v27 = v23;
  v28 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0xAu, &v25);
}

```

## disassembly

```asm
0x180001ab8  push    rbp
0x180001aba  lea     rbp, [rsp-17h]
0x180001abf  sub     rsp, 0E0h
0x180001ac6  mov     rax, cs:__security_cookie
0x180001acd  xor     rax, rsp
0x180001ad0  mov     [rbp+17h+var_10], rax
0x180001ad4  mov     rax, [rbp+17h+arg_58]
0x180001ad8  mov     r10, rcx
0x180001adb  xor     r9d, r9d
0x180001ade  mov     [rbp+17h+var_18], 10h
0x180001ae6  mov     r11, rdx
0x180001ae9  mov     [rbp+17h+var_28], 8
0x180001af1  mov     [rbp+17h+var_38], 4
0x180001af9  mov     rcx, [rax]
0x180001afc  mov     rax, [rbp+17h+arg_50]
0x180001b00  lea     r8d, [r9+2]
0x180001b04  mov     [rbp+17h+var_30], rax
0x180001b08  mov     rax, [rbp+17h+arg_48]
0x180001b0c  mov     [rbp+17h+var_40], rax
0x180001b10  mov     rax, [rbp+17h+arg_40]
0x180001b14  mov     [rbp+17h+var_50], rax
0x180001b18  mov     rax, [rbp+17h+arg_38]
0x180001b1c  mov     [rbp+17h+var_20], rcx
0x180001b20  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001b24  mov     [rbp+17h+var_48], 4
0x180001b2c  mov     rdx, [rax]
0x180001b2f  test    rdx, rdx
0x180001b32  jz      short loc_180001B4A
0x180001b34  mov     rax, rcx
0x180001b37  inc     rax
0x180001b3a  cmp     [rdx+rax*2], r9w
0x180001b3f  jnz     short loc_180001B37
0x180001b41  lea     eax, ds:2[rax*2]
0x180001b48  jmp     short loc_180001B54
0x180001b4a  lea     rdx, S2
0x180001b51  mov     eax, r8d
0x180001b54  mov     [rbp+17h+var_58], eax
0x180001b57  mov     rax, [rbp+17h+arg_30]
0x180001b5b  mov     [rbp+17h+var_60], rdx
0x180001b5f  mov     [rbp+17h+var_54], r9d
0x180001b63  mov     rdx, [rax]
0x180001b66  test    rdx, rdx
0x180001b69  jz      short loc_180001B82
0x180001b6b  mov     rax, rcx
0x180001b6e  inc     rax
0x180001b71  cmp     [rdx+rax*2], r9w
0x180001b76  jnz     short loc_180001B6E
0x180001b78  lea     r8d, ds:2[rax*2]
0x180001b80  jmp     short loc_180001B89
0x180001b82  lea     rdx, S2
0x180001b89  mov     rax, [rbp+17h+arg_28]
0x180001b8d  mov     [rbp+17h+var_80], rax
0x180001b91  mov     rax, [rbp+17h+arg_20]
0x180001b95  mov     [rbp+17h+var_70], rdx
0x180001b99  mov     [rbp+17h+var_68], r8d
0x180001b9d  mov     [rbp+17h+var_64], r9d
0x180001ba1  mov     rdx, [rax]
0x180001ba4  mov     [rbp+17h+var_78], 8
0x180001bac  test    rdx, rdx
0x180001baf  jz      short loc_180001BBE
0x180001bb1  inc     rcx
0x180001bb4  cmp     [rdx+rcx], r9b
0x180001bb8  jnz     short loc_180001BB1
0x180001bba  inc     ecx
0x180001bbc  jmp     short loc_180001BCA
0x180001bbe  lea     rdx, word_18002377A
0x180001bc5  mov     ecx, 1
0x180001bca  lea     rax, [rsp+0E0h+var_B0]
0x180001bcf  mov     [rbp+17h+var_90], rdx
0x180001bd3  mov     [rbp+17h+var_88], ecx
0x180001bd6  xor     r8d, r8d
0x180001bd9  mov     [rsp+0E0h+var_B8], rax
0x180001bde  mov     rdx, r11
0x180001be1  mov     rcx, r10
0x180001be4  mov     [rsp+0E0h+var_C0], 0Ah
0x180001bec  mov     [rbp+17h+var_84], r9d
0x180001bf0  call    _tlgWriteTransfer_EventWriteTransfer
0x180001bf5  mov     rcx, [rbp+17h+var_10]
0x180001bf9  xor     rcx, rsp; StackCookie
0x180001bfc  call    __security_check_cookie
0x180001c01  add     rsp, 0E0h
0x180001c08  pop     rbp
0x180001c09  retn
```
