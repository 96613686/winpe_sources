# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x14000124c`
- end: `0x140001323`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z`
- size: `215`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, int **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006e18`
- `0x140008b38`

## callees

- `0x1400011ac`
- `0x14000124c`
- `0x14000a370`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
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
  _BYTE v14[32]; // [rsp+30h] [rbp-58h] BYREF
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
    v9 = &dword_14000C834;
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
    v12 = &dword_14000C834;
  }
  v15 = v12;
  v16 = v8;
  v17 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140010000, a2, 0, 0, 4, v14);
}

```

## disassembly

```asm
0x14000124c  sub     rsp, 88h
0x140001253  mov     rax, cs:__security_cookie
0x14000125a  xor     rax, rsp
0x14000125d  mov     [rsp+88h+var_18], rax
0x140001262  mov     rax, [rsp+88h+arg_28]
0x14000126a  mov     r10, rdx
0x14000126d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001271  xor     r9d, r9d
0x140001274  mov     r8d, 2
0x14000127a  mov     rdx, [rax]
0x14000127d  test    rdx, rdx
0x140001280  jz      short loc_140001298
0x140001282  mov     rax, rcx
0x140001285  inc     rax
0x140001288  cmp     [rdx+rax*2], r9w
0x14000128d  jnz     short loc_140001285
0x14000128f  lea     eax, ds:2[rax*2]
0x140001296  jmp     short loc_1400012A2
0x140001298  lea     rdx, dword_14000C834
0x14000129f  mov     eax, r8d
0x1400012a2  mov     [rsp+88h+var_20], eax
0x1400012a6  mov     rax, [rsp+88h+arg_20]
0x1400012ae  mov     [rsp+88h+var_28], rdx
0x1400012b3  mov     [rsp+88h+var_1C], r9d
0x1400012b8  mov     rdx, [rax]
0x1400012bb  test    rdx, rdx
0x1400012be  jz      short loc_1400012D4
0x1400012c0  inc     rcx
0x1400012c3  cmp     [rdx+rcx*2], r9w
0x1400012c8  jnz     short loc_1400012C0
0x1400012ca  lea     r8d, ds:2[rcx*2]
0x1400012d2  jmp     short loc_1400012DB
0x1400012d4  lea     rdx, dword_14000C834
0x1400012db  lea     rax, [rsp+88h+var_58]
0x1400012e0  mov     [rsp+88h+var_38], rdx
0x1400012e5  mov     [rsp+88h+var_30], r8d
0x1400012ea  lea     rcx, dword_140010000
0x1400012f1  mov     [rsp+88h+var_60], rax
0x1400012f6  xor     r8d, r8d
0x1400012f9  mov     rdx, r10
0x1400012fc  mov     [rsp+88h+var_68], 4
0x140001304  mov     [rsp+88h+var_2C], r9d
0x140001309  call    _tlgWriteTransfer_EventWriteTransfer
0x14000130e  mov     rcx, [rsp+88h+var_18]
0x140001313  xor     rcx, rsp; StackCookie
0x140001316  call    __security_check_cookie
0x14000131b  add     rsp, 88h
0x140001322  retn
```
