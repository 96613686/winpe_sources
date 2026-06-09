# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)

- ea: `0x180001990`
- end: `0x180001ab1`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByRef@$0BA@@@@Z`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b1b0`

## callees

- `0x18000163c`
- `0x180001990`
- `0x1800038f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const wchar_t **a7,
        const wchar_t **a8,
        __int64 *a9)
{
  int v11; // r8d
  __int64 v12; // rcx
  const wchar_t *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const wchar_t *v16; // rdx
  __int64 v17; // rax
  const unsigned __int16 *v18; // rdx
  int v19; // ecx
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-31h]
  int v23; // [rsp+58h] [rbp-29h]
  int v24; // [rsp+5Ch] [rbp-25h]
  __int64 v25; // [rsp+60h] [rbp-21h]
  __int64 v26; // [rsp+68h] [rbp-19h]
  const wchar_t *v27; // [rsp+70h] [rbp-11h]
  int v28; // [rsp+78h] [rbp-9h]
  int v29; // [rsp+7Ch] [rbp-5h]
  const wchar_t *v30; // [rsp+80h] [rbp-1h]
  int v31; // [rsp+88h] [rbp+7h]
  int v32; // [rsp+8Ch] [rbp+Bh]
  __int64 v33; // [rsp+90h] [rbp+Fh]
  __int64 v34; // [rsp+98h] [rbp+17h]

  v34 = 16;
  v11 = 2;
  v33 = *a9;
  v12 = -1;
  v13 = *a8;
  if ( *a8 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &S2;
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
    while ( v16[v17] );
    v11 = 2 * v17 + 2;
  }
  else
  {
    v16 = &S2;
  }
  v25 = a6;
  v27 = v16;
  v28 = v11;
  v29 = 0;
  v18 = *a5;
  v26 = 8;
  if ( v18 )
  {
    do
      ++v12;
    while ( *((_BYTE *)v18 + v12) );
    v19 = v12 + 1;
  }
  else
  {
    v18 = &word_18002377A;
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
0x180001990  push    rbp
0x180001992  lea     rbp, [rsp-2Fh]
0x180001997  sub     rsp, 0B0h
0x18000199e  mov     rax, cs:__security_cookie
0x1800019a5  xor     rax, rsp
0x1800019a8  mov     [rbp+2Fh+var_10], rax
0x1800019ac  mov     rax, [rbp+2Fh+arg_40]
0x1800019b0  mov     r10, rcx
0x1800019b3  xor     r9d, r9d
0x1800019b6  mov     [rbp+2Fh+var_18], 10h
0x1800019be  mov     r11, rdx
0x1800019c1  mov     rcx, [rax]
0x1800019c4  mov     rax, [rbp+2Fh+arg_38]
0x1800019c8  lea     r8d, [r9+2]
0x1800019cc  mov     [rbp+2Fh+var_20], rcx
0x1800019d0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800019d4  mov     rdx, [rax]
0x1800019d7  test    rdx, rdx
0x1800019da  jz      short loc_1800019F2
0x1800019dc  mov     rax, rcx
0x1800019df  inc     rax
0x1800019e2  cmp     [rdx+rax*2], r9w
0x1800019e7  jnz     short loc_1800019DF
0x1800019e9  lea     eax, ds:2[rax*2]
0x1800019f0  jmp     short loc_1800019FC
0x1800019f2  lea     rdx, S2
0x1800019f9  mov     eax, r8d
0x1800019fc  mov     [rbp+2Fh+var_28], eax
0x1800019ff  mov     rax, [rbp+2Fh+arg_30]
0x180001a03  mov     [rbp+2Fh+var_30], rdx
0x180001a07  mov     [rbp+2Fh+var_24], r9d
0x180001a0b  mov     rdx, [rax]
0x180001a0e  test    rdx, rdx
0x180001a11  jz      short loc_180001A2A
0x180001a13  mov     rax, rcx
0x180001a16  inc     rax
0x180001a19  cmp     [rdx+rax*2], r9w
0x180001a1e  jnz     short loc_180001A16
0x180001a20  lea     r8d, ds:2[rax*2]
0x180001a28  jmp     short loc_180001A31
0x180001a2a  lea     rdx, S2
0x180001a31  mov     rax, [rbp+2Fh+arg_28]
0x180001a35  mov     [rbp+2Fh+var_50], rax
0x180001a39  mov     rax, [rbp+2Fh+arg_20]
0x180001a3d  mov     [rbp+2Fh+var_40], rdx
0x180001a41  mov     [rbp+2Fh+var_38], r8d
0x180001a45  mov     [rbp+2Fh+var_34], r9d
0x180001a49  mov     rdx, [rax]
0x180001a4c  mov     [rbp+2Fh+var_48], 8
0x180001a54  test    rdx, rdx
0x180001a57  jz      short loc_180001A66
0x180001a59  inc     rcx
0x180001a5c  cmp     [rdx+rcx], r9b
0x180001a60  jnz     short loc_180001A59
0x180001a62  inc     ecx
0x180001a64  jmp     short loc_180001A72
0x180001a66  lea     rdx, word_18002377A
0x180001a6d  mov     ecx, 1
0x180001a72  lea     rax, [rbp+2Fh+var_80]
0x180001a76  mov     [rbp+2Fh+var_60], rdx
0x180001a7a  mov     [rbp+2Fh+var_58], ecx
0x180001a7d  xor     r8d, r8d
0x180001a80  mov     [rsp+0B0h+var_88], rax
0x180001a85  mov     rdx, r11
0x180001a88  mov     rcx, r10
0x180001a8b  mov     [rsp+0B0h+var_90], 7
0x180001a93  mov     [rbp+2Fh+var_54], r9d
0x180001a97  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a9c  mov     rcx, [rbp+2Fh+var_10]
0x180001aa0  xor     rcx, rsp; StackCookie
0x180001aa3  call    __security_check_cookie
0x180001aa8  add     rsp, 0B0h
0x180001aaf  pop     rbp
0x180001ab0  retn
```
