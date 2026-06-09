# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400015a8`
- end: `0x1400016db`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, int **, int **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008628`

## callees

- `0x1400011ac`
- `0x1400015a8`
- `0x14000a370`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        int **a6,
        int **a7,
        int **a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  int *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  int *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  int *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  int *v20; // rdx
  _BYTE v22[32]; // [rsp+30h] [rbp-39h] BYREF
  int *v23; // [rsp+50h] [rbp-19h]
  int v24; // [rsp+58h] [rbp-11h]
  int v25; // [rsp+5Ch] [rbp-Dh]
  int *v26; // [rsp+60h] [rbp-9h]
  int v27; // [rsp+68h] [rbp-1h]
  int v28; // [rsp+6Ch] [rbp+3h]
  int *v29; // [rsp+70h] [rbp+7h]
  int v30; // [rsp+78h] [rbp+Fh]
  int v31; // [rsp+7Ch] [rbp+13h]
  int *v32; // [rsp+80h] [rbp+17h]
  int v33; // [rsp+88h] [rbp+1Fh]
  int v34; // [rsp+8Ch] [rbp+23h]

  v9 = -1;
  v10 = 2;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &dword_14000C834;
    v13 = 2;
  }
  v33 = v13;
  v32 = v11;
  v34 = 0;
  v14 = *a7;
  if ( *a7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &dword_14000C834;
    v16 = 2;
  }
  v30 = v16;
  v29 = v14;
  v31 = 0;
  v17 = *a6;
  if ( *a6 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = &dword_14000C834;
    v19 = 2;
  }
  v27 = v19;
  v26 = v17;
  v28 = 0;
  v20 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_WORD *)v20 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v20 = &dword_14000C834;
  }
  v23 = v20;
  v24 = v10;
  v25 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140010000, a2, 0, 0, 6, v22);
}

```

## disassembly

```asm
0x1400015a8  push    rbp
0x1400015aa  lea     rbp, [rsp-37h]
0x1400015af  sub     rsp, 0A0h
0x1400015b6  mov     rax, cs:__security_cookie
0x1400015bd  xor     rax, rsp
0x1400015c0  mov     [rbp+37h+var_10], rax
0x1400015c4  mov     rax, [rbp+37h+arg_38]
0x1400015c8  lea     r11, dword_14000C834
0x1400015cf  mov     r10, rdx
0x1400015d2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400015d6  xor     r9d, r9d
0x1400015d9  mov     r8d, 2
0x1400015df  mov     rdx, [rax]
0x1400015e2  test    rdx, rdx
0x1400015e5  jz      short loc_1400015FD
0x1400015e7  mov     rax, rcx
0x1400015ea  inc     rax
0x1400015ed  cmp     [rdx+rax*2], r9w
0x1400015f2  jnz     short loc_1400015EA
0x1400015f4  lea     eax, ds:2[rax*2]
0x1400015fb  jmp     short loc_140001603
0x1400015fd  mov     rdx, r11
0x140001600  mov     eax, r8d
0x140001603  mov     [rbp+37h+var_18], eax
0x140001606  mov     rax, [rbp+37h+arg_30]
0x14000160a  mov     [rbp+37h+var_20], rdx
0x14000160e  mov     [rbp+37h+var_14], r9d
0x140001612  mov     rdx, [rax]
0x140001615  test    rdx, rdx
0x140001618  jz      short loc_140001630
0x14000161a  mov     rax, rcx
0x14000161d  inc     rax
0x140001620  cmp     [rdx+rax*2], r9w
0x140001625  jnz     short loc_14000161D
0x140001627  lea     eax, ds:2[rax*2]
0x14000162e  jmp     short loc_140001636
0x140001630  mov     rdx, r11
0x140001633  mov     eax, r8d
0x140001636  mov     [rbp+37h+var_28], eax
0x140001639  mov     rax, [rbp+37h+arg_28]
0x14000163d  mov     [rbp+37h+var_30], rdx
0x140001641  mov     [rbp+37h+var_24], r9d
0x140001645  mov     rdx, [rax]
0x140001648  test    rdx, rdx
0x14000164b  jz      short loc_140001663
0x14000164d  mov     rax, rcx
0x140001650  inc     rax
0x140001653  cmp     [rdx+rax*2], r9w
0x140001658  jnz     short loc_140001650
0x14000165a  lea     eax, ds:2[rax*2]
0x140001661  jmp     short loc_140001669
0x140001663  mov     rdx, r11
0x140001666  mov     eax, r8d
0x140001669  mov     [rbp+37h+var_38], eax
0x14000166c  mov     rax, [rbp+37h+arg_20]
0x140001670  mov     [rbp+37h+var_40], rdx
0x140001674  mov     [rbp+37h+var_34], r9d
0x140001678  mov     rdx, [rax]
0x14000167b  test    rdx, rdx
0x14000167e  jz      short loc_140001694
0x140001680  inc     rcx
0x140001683  cmp     [rdx+rcx*2], r9w
0x140001688  jnz     short loc_140001680
0x14000168a  lea     r8d, ds:2[rcx*2]
0x140001692  jmp     short loc_140001697
0x140001694  mov     rdx, r11
0x140001697  lea     rax, [rbp+37h+var_70]
0x14000169b  mov     [rbp+37h+var_50], rdx
0x14000169f  mov     [rbp+37h+var_48], r8d
0x1400016a3  lea     rcx, dword_140010000
0x1400016aa  mov     [rsp+0A0h+var_78], rax
0x1400016af  xor     r8d, r8d
0x1400016b2  mov     rdx, r10
0x1400016b5  mov     [rsp+0A0h+var_80], 6
0x1400016bd  mov     [rbp+37h+var_44], r9d
0x1400016c1  call    _tlgWriteTransfer_EventWriteTransfer
0x1400016c6  mov     rcx, [rbp+37h+var_10]
0x1400016ca  xor     rcx, rsp; StackCookie
0x1400016cd  call    __security_check_cookie
0x1400016d2  add     rsp, 0A0h
0x1400016d9  pop     rbp
0x1400016da  retn
```
