# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001878`
- end: `0x18000198f`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@464@Z`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000baa0`
- `0x18000beb0`

## callees

- `0x18000163c`
- `0x180001878`
- `0x180002470`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
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
        __int64 a11)
{
  __int64 v13; // rcx
  __int64 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // ecx
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-81h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-61h]
  int v22; // [rsp+58h] [rbp-59h]
  int v23; // [rsp+5Ch] [rbp-55h]
  __int64 v24; // [rsp+60h] [rbp-51h]
  __int64 v25; // [rsp+68h] [rbp-49h]
  __int64 *v26; // [rsp+70h] [rbp-41h]
  int v27; // [rsp+78h] [rbp-39h]
  int v28; // [rsp+7Ch] [rbp-35h]
  __int64 v29; // [rsp+80h] [rbp-31h]
  __int64 v30; // [rsp+88h] [rbp-29h]
  __int64 v31; // [rsp+90h] [rbp-21h]
  __int64 v32; // [rsp+98h] [rbp-19h]
  __int64 v33; // [rsp+A0h] [rbp-11h]
  __int64 v34; // [rsp+A8h] [rbp-9h]
  __int64 v35; // [rsp+B0h] [rbp-1h]
  __int64 v36; // [rsp+B8h] [rbp+7h]

  v35 = a11;
  v33 = a10;
  v13 = -1;
  v31 = a9;
  v29 = a8;
  v36 = 8;
  v34 = 4;
  v32 = 8;
  v14 = *a7;
  v30 = 4;
  if ( v14 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = qword_180017FF0;
    v16 = 2;
  }
  v27 = v16;
  v24 = a6;
  v26 = v14;
  v28 = 0;
  v25 = 8;
  v17 = *a5;
  if ( *a5 )
  {
    do
      ++v13;
    while ( *((_BYTE *)v17 + v13) );
    v18 = v13 + 1;
  }
  else
  {
    v17 = &word_18001783A;
    v18 = 1;
  }
  v21 = v17;
  v22 = v18;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 9u, &v20);
}

```

## disassembly

```asm
0x180001878  push    rbp
0x18000187a  lea     rbp, [rsp-1Fh]
0x18000187f  sub     rsp, 0D0h
0x180001886  mov     rax, cs:__security_cookie
0x18000188d  xor     rax, rsp
0x180001890  mov     [rbp+1Fh+var_10], rax
0x180001894  mov     rax, [rbp+1Fh+arg_50]
0x180001898  mov     r11, rdx
0x18000189b  mov     [rbp+1Fh+var_20], rax
0x18000189f  mov     r10, rcx
0x1800018a2  mov     rax, [rbp+1Fh+arg_48]
0x1800018a6  xor     r8d, r8d
0x1800018a9  mov     [rbp+1Fh+var_30], rax
0x1800018ad  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800018b1  mov     rax, [rbp+1Fh+arg_40]
0x1800018b5  mov     [rbp+1Fh+var_40], rax
0x1800018b9  mov     rax, [rbp+1Fh+arg_38]
0x1800018bd  mov     [rbp+1Fh+var_50], rax
0x1800018c1  mov     rax, [rbp+1Fh+arg_30]
0x1800018c5  mov     [rbp+1Fh+var_18], 8
0x1800018cd  mov     [rbp+1Fh+var_28], 4
0x1800018d5  mov     [rbp+1Fh+var_38], 8
0x1800018dd  mov     rdx, [rax]
0x1800018e0  mov     [rbp+1Fh+var_48], 4
0x1800018e8  test    rdx, rdx
0x1800018eb  jz      short loc_180001903
0x1800018ed  mov     rax, rcx
0x1800018f0  inc     rax
0x1800018f3  cmp     [rdx+rax*2], r8w
0x1800018f8  jnz     short loc_1800018F0
0x1800018fa  lea     eax, ds:2[rax*2]
0x180001901  jmp     short loc_18000190F
0x180001903  lea     rdx, qword_180017FF0
0x18000190a  mov     eax, 2
0x18000190f  mov     [rbp+1Fh+var_58], eax
0x180001912  mov     rax, [rbp+1Fh+arg_28]
0x180001916  mov     [rbp+1Fh+var_70], rax
0x18000191a  mov     rax, [rbp+1Fh+arg_20]
0x18000191e  mov     [rbp+1Fh+var_60], rdx
0x180001922  mov     [rbp+1Fh+var_54], r8d
0x180001926  mov     [rbp+1Fh+var_68], 8
0x18000192e  mov     rdx, [rax]
0x180001931  test    rdx, rdx
0x180001934  jz      short loc_180001943
0x180001936  inc     rcx
0x180001939  cmp     [rdx+rcx], r8b
0x18000193d  jnz     short loc_180001936
0x18000193f  inc     ecx
0x180001941  jmp     short loc_18000194F
0x180001943  lea     rdx, word_18001783A
0x18000194a  mov     ecx, 1
0x18000194f  lea     rax, [rsp+0D0h+var_A0]
0x180001954  mov     [rbp+1Fh+var_80], rdx
0x180001958  mov     [rbp+1Fh+var_78], ecx
0x18000195b  xor     r9d, r9d
0x18000195e  mov     [rsp+0D0h+var_A8], rax
0x180001963  mov     rdx, r11
0x180001966  mov     rcx, r10
0x180001969  mov     [rsp+0D0h+var_B0], 9
0x180001971  mov     [rbp+1Fh+var_74], r8d
0x180001975  call    _tlgWriteTransfer_EventWriteTransfer
0x18000197a  mov     rcx, [rbp+1Fh+var_10]
0x18000197e  xor     rcx, rsp; StackCookie
0x180001981  call    __security_check_cookie
0x180001986  add     rsp, 0D0h
0x18000198d  pop     rbp
0x18000198e  retn
```
