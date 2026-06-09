# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000135c`
- end: `0x180001472`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z`
- size: `278`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, int **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e184`

## callees

- `0x1800011c4`
- `0x18000135c`
- `0x180010f80`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        int **a6,
        int **a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  int *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  int *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  int *v16; // rdx
  _BYTE v18[32]; // [rsp+30h] [rbp-68h] BYREF
  int *v19; // [rsp+50h] [rbp-48h]
  int v20; // [rsp+58h] [rbp-40h]
  int v21; // [rsp+5Ch] [rbp-3Ch]
  int *v22; // [rsp+60h] [rbp-38h]
  int v23; // [rsp+68h] [rbp-30h]
  int v24; // [rsp+6Ch] [rbp-2Ch]
  int *v25; // [rsp+70h] [rbp-28h]
  int v26; // [rsp+78h] [rbp-20h]
  int v27; // [rsp+7Ch] [rbp-1Ch]

  v8 = -1;
  v9 = 2;
  v10 = *a7;
  if ( *a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &dword_18001490C;
    v12 = 2;
  }
  v26 = v12;
  v25 = v10;
  v27 = 0;
  v13 = *a6;
  if ( *a6 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &dword_18001490C;
    v15 = 2;
  }
  v23 = v15;
  v22 = v13;
  v24 = 0;
  v16 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_WORD *)v16 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v16 = &dword_18001490C;
  }
  v19 = v16;
  v20 = v9;
  v21 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180019000, a2, 0, 0, 5, v18);
}

```

## disassembly

```asm
0x18000135c  sub     rsp, 98h
0x180001363  mov     rax, cs:__security_cookie
0x18000136a  xor     rax, rsp
0x18000136d  mov     [rsp+98h+var_18], rax
0x180001375  mov     rax, [rsp+98h+arg_30]
0x18000137d  lea     r11, dword_18001490C
0x180001384  mov     r10, rdx
0x180001387  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000138b  xor     r9d, r9d
0x18000138e  mov     r8d, 2
0x180001394  mov     rdx, [rax]
0x180001397  test    rdx, rdx
0x18000139a  jz      short loc_1800013B2
0x18000139c  mov     rax, rcx
0x18000139f  inc     rax
0x1800013a2  cmp     [rdx+rax*2], r9w
0x1800013a7  jnz     short loc_18000139F
0x1800013a9  lea     eax, ds:2[rax*2]
0x1800013b0  jmp     short loc_1800013B8
0x1800013b2  mov     rdx, r11
0x1800013b5  mov     eax, r8d
0x1800013b8  mov     [rsp+98h+var_20], eax
0x1800013bc  mov     rax, [rsp+98h+arg_28]
0x1800013c4  mov     [rsp+98h+var_28], rdx
0x1800013c9  mov     [rsp+98h+var_1C], r9d
0x1800013ce  mov     rdx, [rax]
0x1800013d1  test    rdx, rdx
0x1800013d4  jz      short loc_1800013EC
0x1800013d6  mov     rax, rcx
0x1800013d9  inc     rax
0x1800013dc  cmp     [rdx+rax*2], r9w
0x1800013e1  jnz     short loc_1800013D9
0x1800013e3  lea     eax, ds:2[rax*2]
0x1800013ea  jmp     short loc_1800013F2
0x1800013ec  mov     rdx, r11
0x1800013ef  mov     eax, r8d
0x1800013f2  mov     [rsp+98h+var_30], eax
0x1800013f6  mov     rax, [rsp+98h+arg_20]
0x1800013fe  mov     [rsp+98h+var_38], rdx
0x180001403  mov     [rsp+98h+var_2C], r9d
0x180001408  mov     rdx, [rax]
0x18000140b  test    rdx, rdx
0x18000140e  jz      short loc_180001424
0x180001410  inc     rcx
0x180001413  cmp     [rdx+rcx*2], r9w
0x180001418  jnz     short loc_180001410
0x18000141a  lea     r8d, ds:2[rcx*2]
0x180001422  jmp     short loc_180001427
0x180001424  mov     rdx, r11
0x180001427  lea     rax, [rsp+98h+var_68]
0x18000142c  mov     [rsp+98h+var_48], rdx
0x180001431  mov     [rsp+98h+var_40], r8d
0x180001436  lea     rcx, dword_180019000
0x18000143d  mov     [rsp+98h+var_70], rax
0x180001442  xor     r8d, r8d
0x180001445  mov     rdx, r10
0x180001448  mov     [rsp+98h+var_78], 5
0x180001450  mov     [rsp+98h+var_3C], r9d
0x180001455  call    _tlgWriteTransfer_EventWriteTransfer
0x18000145a  mov     rcx, [rsp+98h+var_18]
0x180001462  xor     rcx, rsp; StackCookie
0x180001465  call    __security_check_cookie
0x18000146a  add     rsp, 98h
0x180001471  retn
```
