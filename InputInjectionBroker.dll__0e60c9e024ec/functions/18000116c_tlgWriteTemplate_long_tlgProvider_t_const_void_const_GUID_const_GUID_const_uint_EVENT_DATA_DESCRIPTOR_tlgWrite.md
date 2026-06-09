# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000116c`
- end: `0x180001255`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44444@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010858`
- `0x180010c80`

## callees

- `0x18000116c`
- `0x18000125c`
- `0x180011460`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  _BYTE v15[32]; // [rsp+30h] [rbp-81h] BYREF
  const unsigned __int16 *v16; // [rsp+50h] [rbp-61h]
  int v17; // [rsp+58h] [rbp-59h]
  int v18; // [rsp+5Ch] [rbp-55h]
  __int64 v19; // [rsp+60h] [rbp-51h]
  __int64 v20; // [rsp+68h] [rbp-49h]
  __int64 v21; // [rsp+70h] [rbp-41h]
  __int64 v22; // [rsp+78h] [rbp-39h]
  __int64 v23; // [rsp+80h] [rbp-31h]
  __int64 v24; // [rsp+88h] [rbp-29h]
  __int64 v25; // [rsp+90h] [rbp-21h]
  __int64 v26; // [rsp+98h] [rbp-19h]
  __int64 v27; // [rsp+A0h] [rbp-11h]
  __int64 v28; // [rsp+A8h] [rbp-9h]
  __int64 v29; // [rsp+B0h] [rbp-1h]
  __int64 v30; // [rsp+B8h] [rbp+7h]

  v29 = a11;
  v27 = a10;
  v25 = a9;
  v23 = a8;
  v21 = a7;
  v19 = a6;
  v30 = 4;
  v28 = 4;
  v26 = 4;
  v11 = *a5;
  v24 = 4;
  v22 = 4;
  v20 = 4;
  if ( v11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &qword_18001B630;
    v13 = 1;
  }
  v17 = v13;
  v16 = v11;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180022000, a2, 0, 0, 9, v15);
}

```

## disassembly

```asm
0x18000116c  push    rbp
0x18000116e  lea     rbp, [rsp-1Fh]
0x180001173  sub     rsp, 0D0h
0x18000117a  mov     rax, cs:__security_cookie
0x180001181  xor     rax, rsp
0x180001184  mov     [rbp+1Fh+var_10], rax
0x180001188  mov     rax, [rbp+1Fh+arg_50]
0x18000118c  xor     r8d, r8d
0x18000118f  mov     [rbp+1Fh+var_20], rax
0x180001193  mov     rax, [rbp+1Fh+arg_48]
0x180001197  mov     [rbp+1Fh+var_30], rax
0x18000119b  mov     rax, [rbp+1Fh+arg_40]
0x18000119f  mov     [rbp+1Fh+var_40], rax
0x1800011a3  mov     rax, [rbp+1Fh+arg_38]
0x1800011a7  mov     [rbp+1Fh+var_50], rax
0x1800011ab  mov     rax, [rbp+1Fh+arg_30]
0x1800011af  mov     [rbp+1Fh+var_60], rax
0x1800011b3  mov     rax, [rbp+1Fh+arg_28]
0x1800011b7  mov     [rbp+1Fh+var_70], rax
0x1800011bb  mov     rax, [rbp+1Fh+arg_20]
0x1800011bf  mov     [rbp+1Fh+var_18], 4
0x1800011c7  mov     [rbp+1Fh+var_28], 4
0x1800011cf  mov     [rbp+1Fh+var_38], 4
0x1800011d7  mov     rcx, [rax]
0x1800011da  mov     [rbp+1Fh+var_48], 4
0x1800011e2  mov     [rbp+1Fh+var_58], 4
0x1800011ea  mov     [rbp+1Fh+var_68], 4
0x1800011f2  test    rcx, rcx
0x1800011f5  jz      short loc_180001208
0x1800011f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011fb  inc     rax
0x1800011fe  cmp     [rcx+rax], r8b
0x180001202  jnz     short loc_1800011FB
0x180001204  inc     eax
0x180001206  jmp     short loc_180001214
0x180001208  lea     rcx, qword_18001B630
0x18000120f  mov     eax, 1
0x180001214  mov     [rbp+1Fh+var_78], eax
0x180001217  xor     r9d, r9d
0x18000121a  lea     rax, [rsp+0D0h+var_A0]
0x18000121f  mov     [rbp+1Fh+var_80], rcx
0x180001223  mov     [rsp+0D0h+var_A8], rax
0x180001228  lea     rcx, dword_180022000
0x18000122f  mov     [rsp+0D0h+var_B0], 9
0x180001237  mov     [rbp+1Fh+var_74], r8d
0x18000123b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001240  mov     rcx, [rbp+1Fh+var_10]
0x180001244  xor     rcx, rsp; StackCookie
0x180001247  call    __security_check_cookie
0x18000124c  add     rsp, 0D0h
0x180001253  pop     rbp
0x180001254  retn
```
