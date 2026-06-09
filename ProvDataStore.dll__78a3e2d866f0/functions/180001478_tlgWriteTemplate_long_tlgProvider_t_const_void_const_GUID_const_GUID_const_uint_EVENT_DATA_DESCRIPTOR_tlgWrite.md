# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001478`
- end: `0x1800015de`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3333@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, int **, int **, int **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e184`

## callees

- `0x1800011c4`
- `0x180001478`
- `0x180010f80`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        int **a6,
        int **a7,
        int **a8,
        int **a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  int *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  int *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  int *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  int *v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  int *v24; // rdx
  _BYTE v26[32]; // [rsp+30h] [rbp-51h] BYREF
  int *v27; // [rsp+50h] [rbp-31h]
  int v28; // [rsp+58h] [rbp-29h]
  int v29; // [rsp+5Ch] [rbp-25h]
  int *v30; // [rsp+60h] [rbp-21h]
  int v31; // [rsp+68h] [rbp-19h]
  int v32; // [rsp+6Ch] [rbp-15h]
  int *v33; // [rsp+70h] [rbp-11h]
  int v34; // [rsp+78h] [rbp-9h]
  int v35; // [rsp+7Ch] [rbp-5h]
  int *v36; // [rsp+80h] [rbp-1h]
  int v37; // [rsp+88h] [rbp+7h]
  int v38; // [rsp+8Ch] [rbp+Bh]
  int *v39; // [rsp+90h] [rbp+Fh]
  int v40; // [rsp+98h] [rbp+17h]
  int v41; // [rsp+9Ch] [rbp+1Bh]

  v10 = -1;
  v11 = 2;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &dword_18001490C;
    v14 = 2;
  }
  v40 = v14;
  v39 = v12;
  v41 = 0;
  v15 = *a8;
  if ( *a8 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &dword_18001490C;
    v17 = 2;
  }
  v37 = v17;
  v36 = v15;
  v38 = 0;
  v18 = *a7;
  if ( *a7 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    v20 = 2 * v19 + 2;
  }
  else
  {
    v18 = &dword_18001490C;
    v20 = 2;
  }
  v34 = v20;
  v33 = v18;
  v35 = 0;
  v21 = *a6;
  if ( *a6 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v21 + v22) );
    v23 = 2 * v22 + 2;
  }
  else
  {
    v21 = &dword_18001490C;
    v23 = 2;
  }
  v31 = v23;
  v30 = v21;
  v32 = 0;
  v24 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( *((_WORD *)v24 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v24 = &dword_18001490C;
  }
  v27 = v24;
  v28 = v11;
  v29 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180019000, a2, 0, 0, 7, v26);
}

```

## disassembly

```asm
0x180001478  push    rbp
0x18000147a  lea     rbp, [rsp-2Fh]
0x18000147f  sub     rsp, 0B0h
0x180001486  mov     rax, cs:__security_cookie
0x18000148d  xor     rax, rsp
0x180001490  mov     [rbp+2Fh+var_10], rax
0x180001494  mov     rax, [rbp+2Fh+arg_40]
0x180001498  lea     r11, dword_18001490C
0x18000149f  mov     r10, rdx
0x1800014a2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800014a6  xor     r9d, r9d
0x1800014a9  mov     r8d, 2
0x1800014af  mov     rdx, [rax]
0x1800014b2  test    rdx, rdx
0x1800014b5  jz      short loc_1800014CD
0x1800014b7  mov     rax, rcx
0x1800014ba  inc     rax
0x1800014bd  cmp     [rdx+rax*2], r9w
0x1800014c2  jnz     short loc_1800014BA
0x1800014c4  lea     eax, ds:2[rax*2]
0x1800014cb  jmp     short loc_1800014D3
0x1800014cd  mov     rdx, r11
0x1800014d0  mov     eax, r8d
0x1800014d3  mov     [rbp+2Fh+var_18], eax
0x1800014d6  mov     rax, [rbp+2Fh+arg_38]
0x1800014da  mov     [rbp+2Fh+var_20], rdx
0x1800014de  mov     [rbp+2Fh+var_14], r9d
0x1800014e2  mov     rdx, [rax]
0x1800014e5  test    rdx, rdx
0x1800014e8  jz      short loc_180001500
0x1800014ea  mov     rax, rcx
0x1800014ed  inc     rax
0x1800014f0  cmp     [rdx+rax*2], r9w
0x1800014f5  jnz     short loc_1800014ED
0x1800014f7  lea     eax, ds:2[rax*2]
0x1800014fe  jmp     short loc_180001506
0x180001500  mov     rdx, r11
0x180001503  mov     eax, r8d
0x180001506  mov     [rbp+2Fh+var_28], eax
0x180001509  mov     rax, [rbp+2Fh+arg_30]
0x18000150d  mov     [rbp+2Fh+var_30], rdx
0x180001511  mov     [rbp+2Fh+var_24], r9d
0x180001515  mov     rdx, [rax]
0x180001518  test    rdx, rdx
0x18000151b  jz      short loc_180001533
0x18000151d  mov     rax, rcx
0x180001520  inc     rax
0x180001523  cmp     [rdx+rax*2], r9w
0x180001528  jnz     short loc_180001520
0x18000152a  lea     eax, ds:2[rax*2]
0x180001531  jmp     short loc_180001539
0x180001533  mov     rdx, r11
0x180001536  mov     eax, r8d
0x180001539  mov     [rbp+2Fh+var_38], eax
0x18000153c  mov     rax, [rbp+2Fh+arg_28]
0x180001540  mov     [rbp+2Fh+var_40], rdx
0x180001544  mov     [rbp+2Fh+var_34], r9d
0x180001548  mov     rdx, [rax]
0x18000154b  test    rdx, rdx
0x18000154e  jz      short loc_180001566
0x180001550  mov     rax, rcx
0x180001553  inc     rax
0x180001556  cmp     [rdx+rax*2], r9w
0x18000155b  jnz     short loc_180001553
0x18000155d  lea     eax, ds:2[rax*2]
0x180001564  jmp     short loc_18000156C
0x180001566  mov     rdx, r11
0x180001569  mov     eax, r8d
0x18000156c  mov     [rbp+2Fh+var_48], eax
0x18000156f  mov     rax, [rbp+2Fh+arg_20]
0x180001573  mov     [rbp+2Fh+var_50], rdx
0x180001577  mov     [rbp+2Fh+var_44], r9d
0x18000157b  mov     rdx, [rax]
0x18000157e  test    rdx, rdx
0x180001581  jz      short loc_180001597
0x180001583  inc     rcx
0x180001586  cmp     [rdx+rcx*2], r9w
0x18000158b  jnz     short loc_180001583
0x18000158d  lea     r8d, ds:2[rcx*2]
0x180001595  jmp     short loc_18000159A
0x180001597  mov     rdx, r11
0x18000159a  lea     rax, [rbp+2Fh+var_80]
0x18000159e  mov     [rbp+2Fh+var_60], rdx
0x1800015a2  mov     [rbp+2Fh+var_58], r8d
0x1800015a6  lea     rcx, dword_180019000
0x1800015ad  mov     [rsp+0B0h+var_88], rax
0x1800015b2  xor     r8d, r8d
0x1800015b5  mov     rdx, r10
0x1800015b8  mov     [rsp+0B0h+var_90], 7
0x1800015c0  mov     [rbp+2Fh+var_54], r9d
0x1800015c4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800015c9  mov     rcx, [rbp+2Fh+var_10]
0x1800015cd  xor     rcx, rsp; StackCookie
0x1800015d0  call    __security_check_cookie
0x1800015d5  add     rsp, 0B0h
0x1800015dc  pop     rbp
0x1800015dd  retn
```
