# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x14000172c`
- end: `0x140001820`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017098`

## callees

- `0x14000172c`
- `0x140001f60`
- `0x1400029c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        const WCHAR **a9)
{
  __int64 v11; // rcx
  const WCHAR *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  int v16; // ecx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-51h] BYREF
  __int64 v19; // [rsp+50h] [rbp-31h]
  __int64 v20; // [rsp+58h] [rbp-29h]
  __int64 v21; // [rsp+60h] [rbp-21h]
  __int64 v22; // [rsp+68h] [rbp-19h]
  __int64 v23; // [rsp+70h] [rbp-11h]
  __int64 v24; // [rsp+78h] [rbp-9h]
  const unsigned __int16 *v25; // [rsp+80h] [rbp-1h]
  int v26; // [rsp+88h] [rbp+7h]
  int v27; // [rsp+8Ch] [rbp+Bh]
  const WCHAR *v28; // [rsp+90h] [rbp+Fh]
  int v29; // [rsp+98h] [rbp+17h]
  int v30; // [rsp+9Ch] [rbp+1Bh]

  v11 = -1;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &sourceString;
    v14 = 2;
  }
  v29 = v14;
  v28 = v12;
  v30 = 0;
  v15 = *a8;
  if ( *a8 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v15 + v11) );
    v16 = v11 + 1;
  }
  else
  {
    v15 = &byte_14001BCA1;
    v16 = 1;
  }
  v23 = a7;
  v21 = a6;
  v19 = a5;
  v25 = v15;
  v26 = v16;
  v27 = 0;
  v24 = 4;
  v22 = 4;
  v20 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 7u, &v18);
}

```

## disassembly

```asm
0x14000172c  push    rbp
0x14000172e  lea     rbp, [rsp-2Fh]
0x140001733  sub     rsp, 0B0h
0x14000173a  mov     rax, cs:__security_cookie
0x140001741  xor     rax, rsp
0x140001744  mov     [rbp+2Fh+var_10], rax
0x140001748  mov     rax, [rbp+2Fh+arg_40]
0x14000174c  mov     r11, rdx
0x14000174f  mov     r10, rcx
0x140001752  xor     r9d, r9d
0x140001755  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001759  mov     rdx, [rax]
0x14000175c  test    rdx, rdx
0x14000175f  jz      short loc_140001777
0x140001761  mov     rax, rcx
0x140001764  inc     rax
0x140001767  cmp     [rdx+rax*2], r9w
0x14000176c  jnz     short loc_140001764
0x14000176e  lea     eax, ds:2[rax*2]
0x140001775  jmp     short loc_140001783
0x140001777  lea     rdx, sourceString
0x14000177e  mov     eax, 2
0x140001783  mov     [rbp+2Fh+var_18], eax
0x140001786  mov     rax, [rbp+2Fh+arg_38]
0x14000178a  mov     [rbp+2Fh+var_20], rdx
0x14000178e  mov     [rbp+2Fh+var_14], r9d
0x140001792  mov     rdx, [rax]
0x140001795  test    rdx, rdx
0x140001798  jz      short loc_1400017A7
0x14000179a  inc     rcx
0x14000179d  cmp     [rdx+rcx], r9b
0x1400017a1  jnz     short loc_14000179A
0x1400017a3  inc     ecx
0x1400017a5  jmp     short loc_1400017B3
0x1400017a7  lea     rdx, byte_14001BCA1
0x1400017ae  mov     ecx, 1
0x1400017b3  mov     rax, [rbp+2Fh+arg_30]
0x1400017b7  mov     [rbp+2Fh+var_40], rax
0x1400017bb  mov     rax, [rbp+2Fh+arg_28]
0x1400017bf  mov     [rbp+2Fh+var_50], rax
0x1400017c3  mov     rax, [rbp+2Fh+arg_20]
0x1400017c7  mov     [rbp+2Fh+var_60], rax
0x1400017cb  lea     rax, [rbp+2Fh+var_80]
0x1400017cf  mov     [rbp+2Fh+var_30], rdx
0x1400017d3  mov     rdx, r11
0x1400017d6  mov     [rbp+2Fh+var_28], ecx
0x1400017d9  mov     rcx, r10
0x1400017dc  mov     [rsp+0B0h+var_88], rax
0x1400017e1  mov     [rsp+0B0h+var_90], 7
0x1400017e9  mov     [rbp+2Fh+var_24], r9d
0x1400017ed  mov     [rbp+2Fh+var_38], 4
0x1400017f5  mov     [rbp+2Fh+var_48], 4
0x1400017fd  mov     [rbp+2Fh+var_58], 8
0x140001805  call    _tlgWriteTransfer_EventWriteTransfer
0x14000180a  mov     rcx, [rbp+2Fh+var_10]
0x14000180e  xor     rcx, rsp; StackCookie
0x140001811  call    __security_check_cookie
0x140001816  add     rsp, 0B0h
0x14000181d  pop     rbp
0x14000181e  retn
```
