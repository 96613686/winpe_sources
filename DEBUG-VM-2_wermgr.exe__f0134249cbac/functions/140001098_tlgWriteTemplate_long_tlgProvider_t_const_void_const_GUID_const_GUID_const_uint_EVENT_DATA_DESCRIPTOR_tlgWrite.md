# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x140001098`
- end: `0x14000116f`
- name: `??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b70c`

## callees

- `0x140001098`
- `0x14000162c`
- `0x140003200`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        int **a6)
{
  __int64 v7; // rcx
  int v8; // r8d
  int *v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  int *v12; // rdx
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-58h] BYREF
  int *v15; // [rsp+50h] [rbp-38h]
  int v16; // [rsp+58h] [rbp-30h]
  int v17; // [rsp+5Ch] [rbp-2Ch]
  int *v18; // [rsp+60h] [rbp-28h]
  int v19; // [rsp+68h] [rbp-20h]
  int v20; // [rsp+6Ch] [rbp-1Ch]

  v7 = -1;
  v8 = 2;
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
    v9 = &dword_1400241F4;
    v11 = 2;
  }
  v19 = v11;
  v18 = v9;
  v20 = 0;
  v12 = *a5;
  if ( *a5 )
  {
    do
      ++v7;
    while ( *((_WORD *)v12 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v12 = &dword_1400241F4;
  }
  v15 = v12;
  v16 = v8;
  v17 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002C000, a2, 0, 0, 4u, &v14);
}

```

## disassembly

```asm
0x140001098  sub     rsp, 88h
0x14000109f  mov     rax, cs:__security_cookie
0x1400010a6  xor     rax, rsp
0x1400010a9  mov     [rsp+88h+var_18], rax
0x1400010ae  mov     rax, [rsp+88h+arg_28]
0x1400010b6  mov     r10, rdx
0x1400010b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400010bd  xor     r9d, r9d
0x1400010c0  mov     r8d, 2
0x1400010c6  mov     rdx, [rax]
0x1400010c9  test    rdx, rdx
0x1400010cc  jz      short loc_1400010E4
0x1400010ce  mov     rax, rcx
0x1400010d1  inc     rax
0x1400010d4  cmp     [rdx+rax*2], r9w
0x1400010d9  jnz     short loc_1400010D1
0x1400010db  lea     eax, ds:2[rax*2]
0x1400010e2  jmp     short loc_1400010EE
0x1400010e4  lea     rdx, dword_1400241F4
0x1400010eb  mov     eax, r8d
0x1400010ee  mov     [rsp+88h+var_20], eax
0x1400010f2  mov     rax, [rsp+88h+arg_20]
0x1400010fa  mov     [rsp+88h+var_28], rdx
0x1400010ff  mov     [rsp+88h+var_1C], r9d
0x140001104  mov     rdx, [rax]
0x140001107  test    rdx, rdx
0x14000110a  jz      short loc_140001120
0x14000110c  inc     rcx
0x14000110f  cmp     [rdx+rcx*2], r9w
0x140001114  jnz     short loc_14000110C
0x140001116  lea     r8d, ds:2[rcx*2]
0x14000111e  jmp     short loc_140001127
0x140001120  lea     rdx, dword_1400241F4
0x140001127  lea     rax, [rsp+88h+var_58]
0x14000112c  mov     [rsp+88h+var_38], rdx
0x140001131  mov     [rsp+88h+var_30], r8d
0x140001136  lea     rcx, dword_14002C000
0x14000113d  mov     [rsp+88h+var_60], rax
0x140001142  xor     r8d, r8d
0x140001145  mov     rdx, r10
0x140001148  mov     [rsp+88h+var_68], 4
0x140001150  mov     [rsp+88h+var_2C], r9d
0x140001155  call    _tlgWriteTransfer_EventWriteTransfer
0x14000115a  mov     rcx, [rsp+88h+var_18]
0x14000115f  xor     rcx, rsp; StackCookie
0x140001162  call    __security_check_cookie
0x140001167  add     rsp, 88h
0x14000116e  retn
```
