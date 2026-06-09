# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x14000116c`
- end: `0x140001254`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64 **, __int64, __int64 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140003624`
- `0x140003b3c`
- `0x1400046a0`

## callees

- `0x1400010cc`
- `0x14000116c`
- `0x140007750`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 **a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rdx
  _BYTE v15[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+5Ch] [rbp-3Ch]
  __int64 v19; // [rsp+60h] [rbp-38h]
  __int64 v20; // [rsp+68h] [rbp-30h]
  __int64 *v21; // [rsp+70h] [rbp-28h]
  int v22; // [rsp+78h] [rbp-20h]
  int v23; // [rsp+7Ch] [rbp-1Ch]

  v8 = -1;
  v9 = 1;
  v10 = *a7;
  if ( *a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_BYTE *)v10 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v10 = &qword_140009640;
    v12 = 1;
  }
  v22 = v12;
  v19 = a6;
  v21 = v10;
  v23 = 0;
  v20 = 4;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_BYTE *)v13 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v13 = &qword_140009640;
  }
  v16 = v13;
  v17 = v9;
  v18 = 0;
  return tlgWriteTransfer_GameInputEventWriteTransfer((unsigned int)&dword_14000E000, a2, 0, 0, 5, (__int64)v15);
}

```

## disassembly

```asm
0x14000116c  sub     rsp, 98h
0x140001173  mov     rax, cs:__security_cookie
0x14000117a  xor     rax, rsp
0x14000117d  mov     [rsp+98h+var_18], rax
0x140001185  mov     rax, [rsp+98h+arg_30]
0x14000118d  mov     r10, rdx
0x140001190  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001194  xor     r9d, r9d
0x140001197  mov     r8d, 1
0x14000119d  mov     rdx, [rax]
0x1400011a0  test    rdx, rdx
0x1400011a3  jz      short loc_1400011B5
0x1400011a5  mov     rax, rcx
0x1400011a8  inc     rax
0x1400011ab  cmp     [rdx+rax], r9b
0x1400011af  jnz     short loc_1400011A8
0x1400011b1  inc     eax
0x1400011b3  jmp     short loc_1400011BF
0x1400011b5  lea     rdx, qword_140009640
0x1400011bc  mov     eax, r8d
0x1400011bf  mov     [rsp+98h+var_20], eax
0x1400011c3  mov     rax, [rsp+98h+arg_28]
0x1400011cb  mov     [rsp+98h+var_38], rax
0x1400011d0  mov     rax, [rsp+98h+arg_20]
0x1400011d8  mov     [rsp+98h+var_28], rdx
0x1400011dd  mov     [rsp+98h+var_1C], r9d
0x1400011e2  mov     [rsp+98h+var_30], 4
0x1400011eb  mov     rdx, [rax]
0x1400011ee  test    rdx, rdx
0x1400011f1  jz      short loc_140001202
0x1400011f3  inc     rcx
0x1400011f6  cmp     [rdx+rcx], r9b
0x1400011fa  jnz     short loc_1400011F3
0x1400011fc  lea     r8d, [rcx+1]
0x140001200  jmp     short loc_140001209
0x140001202  lea     rdx, qword_140009640
0x140001209  lea     rax, [rsp+98h+var_68]
0x14000120e  mov     [rsp+98h+var_48], rdx
0x140001213  mov     [rsp+98h+var_40], r8d
0x140001218  lea     rcx, dword_14000E000
0x14000121f  mov     [rsp+98h+var_70], rax
0x140001224  xor     r8d, r8d
0x140001227  mov     rdx, r10
0x14000122a  mov     [rsp+98h+var_78], 5
0x140001232  mov     [rsp+98h+var_3C], r9d
0x140001237  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x14000123c  mov     rcx, [rsp+98h+var_18]
0x140001244  xor     rcx, rsp; StackCookie
0x140001247  call    __security_check_cookie
0x14000124c  add     rsp, 98h
0x140001253  retn
```
