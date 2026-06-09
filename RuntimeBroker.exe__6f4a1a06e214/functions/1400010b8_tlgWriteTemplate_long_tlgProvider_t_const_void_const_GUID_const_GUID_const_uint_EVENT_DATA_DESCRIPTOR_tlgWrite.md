# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &)

- ea: `0x1400010b8`
- end: `0x140001207`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$01@@@Z`
- size: `335`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000dc6c`
- `0x14000df40`
- `0x14000e8e4`

## callees

- `0x1400010b8`
- `0x140001898`
- `0x140008c80`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        const size_t **a7,
        const unsigned __int16 **a8,
        const unsigned __int16 **a9,
        __int64 a10)
{
  int v10; // r9d
  __int64 v13; // rcx
  int v14; // r8d
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  const size_t *v21; // rdx
  __int64 v22; // rax
  const unsigned __int16 *v23; // rdx
  _BYTE v25[32]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v26; // [rsp+50h] [rbp-49h]
  __int64 v27; // [rsp+58h] [rbp-41h]
  const unsigned __int16 *v28; // [rsp+60h] [rbp-39h]
  int v29; // [rsp+68h] [rbp-31h]
  int v30; // [rsp+6Ch] [rbp-2Dh]
  const size_t *v31; // [rsp+70h] [rbp-29h]
  int v32; // [rsp+78h] [rbp-21h]
  int v33; // [rsp+7Ch] [rbp-1Dh]
  const unsigned __int16 *v34; // [rsp+80h] [rbp-19h]
  int v35; // [rsp+88h] [rbp-11h]
  int v36; // [rsp+8Ch] [rbp-Dh]
  const unsigned __int16 *v37; // [rsp+90h] [rbp-9h]
  int v38; // [rsp+98h] [rbp-1h]
  int v39; // [rsp+9Ch] [rbp+3h]
  __int64 v40; // [rsp+A0h] [rbp+7h]
  __int64 v41; // [rsp+A8h] [rbp+Fh]

  v10 = 2;
  v40 = a10;
  v41 = 2;
  v13 = -1;
  v14 = 1;
  v15 = *a9;
  if ( *a9 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_BYTE *)v15 + v16) );
    v17 = v16 + 1;
  }
  else
  {
    v15 = &dword_1400135E4;
    v17 = 1;
  }
  v38 = v17;
  v37 = v15;
  v39 = 0;
  v18 = *a8;
  if ( *a8 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_BYTE *)v18 + v19) );
    v20 = v19 + 1;
  }
  else
  {
    v18 = &dword_1400135E4;
    v20 = 1;
  }
  v35 = v20;
  v34 = v18;
  v36 = 0;
  v21 = *a7;
  if ( *a7 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v21 + v22) );
    v10 = 2 * v22 + 2;
  }
  else
  {
    v21 = &Format;
  }
  v31 = v21;
  v32 = v10;
  v33 = 0;
  v23 = *a6;
  if ( *a6 )
  {
    do
      ++v13;
    while ( *((_BYTE *)v23 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v23 = &dword_1400135E4;
  }
  v26 = a5;
  v28 = v23;
  v29 = v14;
  v30 = 0;
  v27 = 4;
  return tlgWriteTransfer_EtwEventWriteTransfer(a1, a2, 0, 0, 8, (__int64)v25);
}

```

## disassembly

```asm
0x1400010b8  mov     [rsp-8+arg_10], rbx
0x1400010bd  push    rbp
0x1400010be  lea     rbp, [rsp-27h]
0x1400010c3  sub     rsp, 0C0h
0x1400010ca  mov     rax, cs:__security_cookie
0x1400010d1  xor     rax, rsp
0x1400010d4  mov     [rbp+27h+var_10], rax
0x1400010d8  mov     rax, [rbp+27h+arg_48]
0x1400010dc  mov     r9d, 2
0x1400010e2  mov     [rbp+27h+var_20], rax
0x1400010e6  mov     r11, rdx
0x1400010e9  mov     rax, [rbp+27h+arg_40]
0x1400010ed  mov     r10, rcx
0x1400010f0  xor     ebx, ebx
0x1400010f2  mov     [rbp+27h+var_18], r9
0x1400010f6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400010fa  lea     r8d, [r9-1]
0x1400010fe  mov     rdx, [rax]
0x140001101  test    rdx, rdx
0x140001104  jz      short loc_140001115
0x140001106  mov     rax, rcx
0x140001109  inc     rax
0x14000110c  cmp     [rdx+rax], bl
0x14000110f  jnz     short loc_140001109
0x140001111  inc     eax
0x140001113  jmp     short loc_14000111F
0x140001115  lea     rdx, dword_1400135E4
0x14000111c  mov     eax, r8d
0x14000111f  mov     [rbp+27h+var_28], eax
0x140001122  mov     rax, [rbp+27h+arg_38]
0x140001126  mov     [rbp+27h+var_30], rdx
0x14000112a  mov     [rbp+27h+var_24], ebx
0x14000112d  mov     rdx, [rax]
0x140001130  test    rdx, rdx
0x140001133  jz      short loc_140001144
0x140001135  mov     rax, rcx
0x140001138  inc     rax
0x14000113b  cmp     [rdx+rax], bl
0x14000113e  jnz     short loc_140001138
0x140001140  inc     eax
0x140001142  jmp     short loc_14000114E
0x140001144  lea     rdx, dword_1400135E4
0x14000114b  mov     eax, r8d
0x14000114e  mov     [rbp+27h+var_38], eax
0x140001151  mov     rax, [rbp+27h+arg_30]
0x140001155  mov     [rbp+27h+var_40], rdx
0x140001159  mov     [rbp+27h+var_34], ebx
0x14000115c  mov     rdx, [rax]
0x14000115f  test    rdx, rdx
0x140001162  jz      short loc_14000117A
0x140001164  mov     rax, rcx
0x140001167  inc     rax
0x14000116a  cmp     [rdx+rax*2], bx
0x14000116e  jnz     short loc_140001167
0x140001170  lea     r9d, ds:2[rax*2]
0x140001178  jmp     short loc_140001181
0x14000117a  lea     rdx, Format
0x140001181  mov     rax, [rbp+27h+arg_28]
0x140001185  mov     [rbp+27h+var_50], rdx
0x140001189  mov     [rbp+27h+var_48], r9d
0x14000118d  mov     [rbp+27h+var_44], ebx
0x140001190  mov     rdx, [rax]
0x140001193  test    rdx, rdx
0x140001196  jz      short loc_1400011A6
0x140001198  inc     rcx
0x14000119b  cmp     [rdx+rcx], bl
0x14000119e  jnz     short loc_140001198
0x1400011a0  lea     r8d, [rcx+1]
0x1400011a4  jmp     short loc_1400011AD
0x1400011a6  lea     rdx, dword_1400135E4
0x1400011ad  mov     rax, [rbp+27h+arg_20]
0x1400011b1  xor     r9d, r9d
0x1400011b4  mov     [rbp+27h+var_70], rax
0x1400011b8  mov     rcx, r10
0x1400011bb  lea     rax, [rbp+27h+var_90]
0x1400011bf  mov     [rbp+27h+var_60], rdx
0x1400011c3  mov     [rbp+27h+var_58], r8d
0x1400011c7  mov     rdx, r11
0x1400011ca  mov     [rsp+0C0h+var_98], rax
0x1400011cf  xor     r8d, r8d
0x1400011d2  mov     [rsp+0C0h+var_A0], 8
0x1400011da  mov     [rbp+27h+var_54], ebx
0x1400011dd  mov     [rbp+27h+var_68], 4
0x1400011e5  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1400011ea  mov     rcx, [rbp+27h+var_10]
0x1400011ee  xor     rcx, rsp; StackCookie
0x1400011f1  call    __security_check_cookie
0x1400011f6  mov     rbx, [rsp+0C0h+arg_10]
0x1400011fe  add     rsp, 0C0h
0x140001205  pop     rbp
0x140001206  retn
```
