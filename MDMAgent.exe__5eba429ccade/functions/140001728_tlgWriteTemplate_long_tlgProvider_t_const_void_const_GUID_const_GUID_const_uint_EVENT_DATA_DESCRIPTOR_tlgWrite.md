# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001728`
- end: `0x14000181b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, const WCHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400163f8`

## callees

- `0x140001728`
- `0x140001f48`
- `0x140002930`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
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
  _BYTE v18[32]; // [rsp+30h] [rbp-51h] BYREF
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
    v15 = &byte_14001ACA1;
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 7, v18);
}

```

## disassembly

```asm
0x140001728  push    rbp
0x14000172a  lea     rbp, [rsp-2Fh]
0x14000172f  sub     rsp, 0B0h
0x140001736  mov     rax, cs:__security_cookie
0x14000173d  xor     rax, rsp
0x140001740  mov     [rbp+2Fh+var_10], rax
0x140001744  mov     rax, [rbp+2Fh+arg_40]
0x140001748  mov     r11, rdx
0x14000174b  mov     r10, rcx
0x14000174e  xor     r9d, r9d
0x140001751  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001755  mov     rdx, [rax]
0x140001758  test    rdx, rdx
0x14000175b  jz      short loc_140001773
0x14000175d  mov     rax, rcx
0x140001760  inc     rax
0x140001763  cmp     [rdx+rax*2], r9w
0x140001768  jnz     short loc_140001760
0x14000176a  lea     eax, ds:2[rax*2]
0x140001771  jmp     short loc_14000177F
0x140001773  lea     rdx, sourceString
0x14000177a  mov     eax, 2
0x14000177f  mov     [rbp+2Fh+var_18], eax
0x140001782  mov     rax, [rbp+2Fh+arg_38]
0x140001786  mov     [rbp+2Fh+var_20], rdx
0x14000178a  mov     [rbp+2Fh+var_14], r9d
0x14000178e  mov     rdx, [rax]
0x140001791  test    rdx, rdx
0x140001794  jz      short loc_1400017A3
0x140001796  inc     rcx
0x140001799  cmp     [rdx+rcx], r9b
0x14000179d  jnz     short loc_140001796
0x14000179f  inc     ecx
0x1400017a1  jmp     short loc_1400017AF
0x1400017a3  lea     rdx, byte_14001ACA1
0x1400017aa  mov     ecx, 1
0x1400017af  mov     rax, [rbp+2Fh+arg_30]
0x1400017b3  mov     [rbp+2Fh+var_40], rax
0x1400017b7  mov     rax, [rbp+2Fh+arg_28]
0x1400017bb  mov     [rbp+2Fh+var_50], rax
0x1400017bf  mov     rax, [rbp+2Fh+arg_20]
0x1400017c3  mov     [rbp+2Fh+var_60], rax
0x1400017c7  lea     rax, [rbp+2Fh+var_80]
0x1400017cb  mov     [rbp+2Fh+var_30], rdx
0x1400017cf  mov     rdx, r11
0x1400017d2  mov     [rbp+2Fh+var_28], ecx
0x1400017d5  mov     rcx, r10
0x1400017d8  mov     [rsp+0B0h+var_88], rax
0x1400017dd  mov     [rsp+0B0h+var_90], 7
0x1400017e5  mov     [rbp+2Fh+var_24], r9d
0x1400017e9  mov     [rbp+2Fh+var_38], 4
0x1400017f1  mov     [rbp+2Fh+var_48], 4
0x1400017f9  mov     [rbp+2Fh+var_58], 8
0x140001801  call    _tlgWriteTransfer_EventWriteTransfer
0x140001806  mov     rcx, [rbp+2Fh+var_10]
0x14000180a  xor     rcx, rsp; StackCookie
0x14000180d  call    __security_check_cookie
0x140001812  add     rsp, 0B0h
0x140001819  pop     rbp
0x14000181a  retn
```
