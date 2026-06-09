# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400016dc`
- end: `0x1400017ab`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `207`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000634c`
- `0x140006454`
- `0x1400074d0`

## callees

- `0x14000163c`
- `0x1400016dc`
- `0x140001cd0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        int **a6)
{
  __int64 v8; // rdx
  int *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  const unsigned __int16 *v12; // rcx
  int v13; // edx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v16; // [rsp+50h] [rbp-38h]
  int v17; // [rsp+58h] [rbp-30h]
  int v18; // [rsp+5Ch] [rbp-2Ch]
  int *v19; // [rsp+60h] [rbp-28h]
  int v20; // [rsp+68h] [rbp-20h]
  int v21; // [rsp+6Ch] [rbp-1Ch]

  v8 = -1;
  v9 = *a6;
  if ( *a6 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &dword_140009864;
    v11 = 2;
  }
  v20 = v11;
  v19 = v9;
  v21 = 0;
  v12 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_BYTE *)v12 + v8) );
    v13 = v8 + 1;
  }
  else
  {
    v12 = &byte_140009860;
    v13 = 1;
  }
  v16 = v12;
  v17 = v13;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 4u, &v15);
}

```

## disassembly

```asm
0x1400016dc  sub     rsp, 88h
0x1400016e3  mov     rax, cs:__security_cookie
0x1400016ea  xor     rax, rsp
0x1400016ed  mov     [rsp+88h+var_18], rax
0x1400016f2  mov     rax, [rsp+88h+arg_28]
0x1400016fa  mov     r11, rdx
0x1400016fd  mov     r10, rcx
0x140001700  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001704  xor     r8d, r8d
0x140001707  mov     rcx, [rax]
0x14000170a  test    rcx, rcx
0x14000170d  jz      short loc_140001725
0x14000170f  mov     rax, rdx
0x140001712  inc     rax
0x140001715  cmp     [rcx+rax*2], r8w
0x14000171a  jnz     short loc_140001712
0x14000171c  lea     eax, ds:2[rax*2]
0x140001723  jmp     short loc_140001731
0x140001725  lea     rcx, dword_140009864
0x14000172c  mov     eax, 2
0x140001731  mov     [rsp+88h+var_20], eax
0x140001735  mov     rax, [rsp+88h+arg_20]
0x14000173d  mov     [rsp+88h+var_28], rcx
0x140001742  mov     [rsp+88h+var_1C], r8d
0x140001747  mov     rcx, [rax]
0x14000174a  test    rcx, rcx
0x14000174d  jz      short loc_14000175C
0x14000174f  inc     rdx
0x140001752  cmp     [rcx+rdx], r8b
0x140001756  jnz     short loc_14000174F
0x140001758  inc     edx
0x14000175a  jmp     short loc_140001768
0x14000175c  lea     rcx, byte_140009860
0x140001763  mov     edx, 1
0x140001768  lea     rax, [rsp+88h+var_58]
0x14000176d  mov     [rsp+88h+var_38], rcx
0x140001772  mov     [rsp+88h+var_30], edx
0x140001776  xor     r9d, r9d
0x140001779  mov     [rsp+88h+var_60], rax
0x14000177e  mov     rdx, r11
0x140001781  mov     rcx, r10
0x140001784  mov     [rsp+88h+var_68], 4
0x14000178c  mov     [rsp+88h+var_2C], r8d
0x140001791  call    _tlgWriteTransfer_EventWriteTransfer
0x140001796  mov     rcx, [rsp+88h+var_18]
0x14000179b  xor     rcx, rsp; StackCookie
0x14000179e  call    __security_check_cookie
0x1400017a3  add     rsp, 88h
0x1400017aa  retn
```
