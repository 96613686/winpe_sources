# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001878`
- end: `0x180001988`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z`
- size: `272`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180016740`
- `0x180016bec`
- `0x180017014`
- `0x180017670`
- `0x18001b1b0`
- `0x18001d680`

## callees

- `0x18000163c`
- `0x180001878`
- `0x1800038f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const wchar_t **a7,
        const wchar_t **a8)
{
  __int64 v10; // rcx
  int v11; // r8d
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const wchar_t *v15; // rdx
  __int64 v16; // rax
  const unsigned __int16 *v17; // rdx
  int v18; // ecx
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-19h]
  int v22; // [rsp+58h] [rbp-11h]
  int v23; // [rsp+5Ch] [rbp-Dh]
  __int64 v24; // [rsp+60h] [rbp-9h]
  __int64 v25; // [rsp+68h] [rbp-1h]
  const wchar_t *v26; // [rsp+70h] [rbp+7h]
  int v27; // [rsp+78h] [rbp+Fh]
  int v28; // [rsp+7Ch] [rbp+13h]
  const wchar_t *v29; // [rsp+80h] [rbp+17h]
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
    while ( v12[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &S2;
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
    while ( v15[v16] );
    v11 = 2 * v16 + 2;
  }
  else
  {
    v15 = &S2;
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
    v17 = &word_18002377A;
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
0x180001878  push    rbp
0x18000187a  lea     rbp, [rsp-37h]
0x18000187f  sub     rsp, 0A0h
0x180001886  mov     rax, cs:__security_cookie
0x18000188d  xor     rax, rsp
0x180001890  mov     [rbp+37h+var_10], rax
0x180001894  mov     rax, [rbp+37h+arg_38]
0x180001898  mov     r11, rdx
0x18000189b  mov     r10, rcx
0x18000189e  xor     r9d, r9d
0x1800018a1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800018a5  mov     r8d, 2
0x1800018ab  mov     rdx, [rax]
0x1800018ae  test    rdx, rdx
0x1800018b1  jz      short loc_1800018C9
0x1800018b3  mov     rax, rcx
0x1800018b6  inc     rax
0x1800018b9  cmp     [rdx+rax*2], r9w
0x1800018be  jnz     short loc_1800018B6
0x1800018c0  lea     eax, ds:2[rax*2]
0x1800018c7  jmp     short loc_1800018D3
0x1800018c9  lea     rdx, S2
0x1800018d0  mov     eax, r8d
0x1800018d3  mov     [rbp+37h+var_18], eax
0x1800018d6  mov     rax, [rbp+37h+arg_30]
0x1800018da  mov     [rbp+37h+var_20], rdx
0x1800018de  mov     [rbp+37h+var_14], r9d
0x1800018e2  mov     rdx, [rax]
0x1800018e5  test    rdx, rdx
0x1800018e8  jz      short loc_180001901
0x1800018ea  mov     rax, rcx
0x1800018ed  inc     rax
0x1800018f0  cmp     [rdx+rax*2], r9w
0x1800018f5  jnz     short loc_1800018ED
0x1800018f7  lea     r8d, ds:2[rax*2]
0x1800018ff  jmp     short loc_180001908
0x180001901  lea     rdx, S2
0x180001908  mov     rax, [rbp+37h+arg_28]
0x18000190c  mov     [rbp+37h+var_40], rax
0x180001910  mov     rax, [rbp+37h+arg_20]
0x180001914  mov     [rbp+37h+var_30], rdx
0x180001918  mov     [rbp+37h+var_28], r8d
0x18000191c  mov     [rbp+37h+var_24], r9d
0x180001920  mov     rdx, [rax]
0x180001923  mov     [rbp+37h+var_38], 8
0x18000192b  test    rdx, rdx
0x18000192e  jz      short loc_18000193D
0x180001930  inc     rcx
0x180001933  cmp     [rdx+rcx], r9b
0x180001937  jnz     short loc_180001930
0x180001939  inc     ecx
0x18000193b  jmp     short loc_180001949
0x18000193d  lea     rdx, word_18002377A
0x180001944  mov     ecx, 1
0x180001949  lea     rax, [rbp+37h+var_70]
0x18000194d  mov     [rbp+37h+var_50], rdx
0x180001951  mov     [rbp+37h+var_48], ecx
0x180001954  xor     r8d, r8d
0x180001957  mov     [rsp+0A0h+var_78], rax
0x18000195c  mov     rdx, r11
0x18000195f  mov     rcx, r10
0x180001962  mov     [rsp+0A0h+var_80], 6
0x18000196a  mov     [rbp+37h+var_44], r9d
0x18000196e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001973  mov     rcx, [rbp+37h+var_10]
0x180001977  xor     rcx, rsp; StackCookie
0x18000197a  call    __security_check_cookie
0x18000197f  add     rsp, 0A0h
0x180001986  pop     rbp
0x180001987  retn
```
