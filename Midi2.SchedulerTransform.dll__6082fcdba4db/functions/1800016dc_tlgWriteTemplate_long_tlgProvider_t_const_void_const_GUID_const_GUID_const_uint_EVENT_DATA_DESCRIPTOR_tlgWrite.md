# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800016dc`
- end: `0x1800017ec`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z`
- size: `272`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18000abe0`
- `0x18000af80`
- `0x18000b540`
- `0x18000b964`
- `0x18000ba70`
- `0x18000cf13`
- `0x18000cfbc`
- `0x18000d09b`
- `0x18000d16e`
- `0x18000d20c`
- `0x18000d2b5`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x180002000`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 **a7,
        __int64 **a8)
{
  __int64 v10; // rcx
  int v11; // r8d
  __int64 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // rdx
  __int64 v16; // rax
  const unsigned __int16 *v17; // rdx
  int v18; // ecx
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-19h]
  int v22; // [rsp+58h] [rbp-11h]
  int v23; // [rsp+5Ch] [rbp-Dh]
  __int64 v24; // [rsp+60h] [rbp-9h]
  __int64 v25; // [rsp+68h] [rbp-1h]
  __int64 *v26; // [rsp+70h] [rbp+7h]
  int v27; // [rsp+78h] [rbp+Fh]
  int v28; // [rsp+7Ch] [rbp+13h]
  __int64 *v29; // [rsp+80h] [rbp+17h]
  int v30; // [rsp+88h] [rbp+1Fh]
  int v31; // [rsp+8Ch] [rbp+23h]

  v10 = -1;
  v11 = 2;
  v12 = *a8;
  if ( *a8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &qword_1800105E0;
    v14 = 2;
  }
  v30 = v14;
  v29 = v12;
  v31 = 0;
  v15 = *a7;
  if ( *a7 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v11 = 2 * v16 + 2;
  }
  else
  {
    v15 = &qword_1800105E0;
  }
  v24 = a6;
  v26 = v15;
  v27 = v11;
  v28 = 0;
  v17 = *a5;
  v25 = 8;
  if ( v17 )
  {
    do
      ++v10;
    while ( *((_BYTE *)v17 + v10) );
    v18 = v10 + 1;
  }
  else
  {
    v17 = &word_18000FE2A;
    v18 = 1;
  }
  v21 = v17;
  v22 = v18;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 6u, &v20);
}

```

## disassembly

```asm
0x1800016dc  push    rbp
0x1800016de  lea     rbp, [rsp-37h]
0x1800016e3  sub     rsp, 0A0h
0x1800016ea  mov     rax, cs:__security_cookie
0x1800016f1  xor     rax, rsp
0x1800016f4  mov     [rbp+37h+var_10], rax
0x1800016f8  mov     rax, [rbp+37h+arg_38]
0x1800016fc  mov     r11, rdx
0x1800016ff  mov     r10, rcx
0x180001702  xor     r9d, r9d
0x180001705  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001709  mov     r8d, 2
0x18000170f  mov     rdx, [rax]
0x180001712  test    rdx, rdx
0x180001715  jz      short loc_18000172D
0x180001717  mov     rax, rcx
0x18000171a  inc     rax
0x18000171d  cmp     [rdx+rax*2], r9w
0x180001722  jnz     short loc_18000171A
0x180001724  lea     eax, ds:2[rax*2]
0x18000172b  jmp     short loc_180001737
0x18000172d  lea     rdx, qword_1800105E0
0x180001734  mov     eax, r8d
0x180001737  mov     [rbp+37h+var_18], eax
0x18000173a  mov     rax, [rbp+37h+arg_30]
0x18000173e  mov     [rbp+37h+var_20], rdx
0x180001742  mov     [rbp+37h+var_14], r9d
0x180001746  mov     rdx, [rax]
0x180001749  test    rdx, rdx
0x18000174c  jz      short loc_180001765
0x18000174e  mov     rax, rcx
0x180001751  inc     rax
0x180001754  cmp     [rdx+rax*2], r9w
0x180001759  jnz     short loc_180001751
0x18000175b  lea     r8d, ds:2[rax*2]
0x180001763  jmp     short loc_18000176C
0x180001765  lea     rdx, qword_1800105E0
0x18000176c  mov     rax, [rbp+37h+arg_28]
0x180001770  mov     [rbp+37h+var_40], rax
0x180001774  mov     rax, [rbp+37h+arg_20]
0x180001778  mov     [rbp+37h+var_30], rdx
0x18000177c  mov     [rbp+37h+var_28], r8d
0x180001780  mov     [rbp+37h+var_24], r9d
0x180001784  mov     rdx, [rax]
0x180001787  mov     [rbp+37h+var_38], 8
0x18000178f  test    rdx, rdx
0x180001792  jz      short loc_1800017A1
0x180001794  inc     rcx
0x180001797  cmp     [rdx+rcx], r9b
0x18000179b  jnz     short loc_180001794
0x18000179d  inc     ecx
0x18000179f  jmp     short loc_1800017AD
0x1800017a1  lea     rdx, word_18000FE2A
0x1800017a8  mov     ecx, 1
0x1800017ad  lea     rax, [rbp+37h+var_70]
0x1800017b1  mov     [rbp+37h+var_50], rdx
0x1800017b5  mov     [rbp+37h+var_48], ecx
0x1800017b8  xor     r8d, r8d
0x1800017bb  mov     [rsp+0A0h+var_78], rax
0x1800017c0  mov     rdx, r11
0x1800017c3  mov     rcx, r10
0x1800017c6  mov     [rsp+0A0h+var_80], 6
0x1800017ce  mov     [rbp+37h+var_44], r9d
0x1800017d2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800017d7  mov     rcx, [rbp+37h+var_10]
0x1800017db  xor     rcx, rsp; StackCookie
0x1800017de  call    __security_check_cookie
0x1800017e3  add     rsp, 0A0h
0x1800017ea  pop     rbp
0x1800017eb  retn
```
