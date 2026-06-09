# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000125c`
- end: `0x14000133d`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z`
- size: `225`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64 **, __int64, __int64 **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003624`
- `0x1400046a0`

## callees

- `0x1400010cc`
- `0x14000125c`
- `0x140007750`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 **a7,
        __int64 a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rdx
  _BYTE v16[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v17; // [rsp+50h] [rbp-19h]
  int v18; // [rsp+58h] [rbp-11h]
  int v19; // [rsp+5Ch] [rbp-Dh]
  __int64 v20; // [rsp+60h] [rbp-9h]
  __int64 v21; // [rsp+68h] [rbp-1h]
  __int64 *v22; // [rsp+70h] [rbp+7h]
  int v23; // [rsp+78h] [rbp+Fh]
  int v24; // [rsp+7Ch] [rbp+13h]
  __int64 v25; // [rsp+80h] [rbp+17h]
  __int64 v26; // [rsp+88h] [rbp+1Fh]

  v25 = a8;
  v9 = -1;
  v26 = 4;
  v10 = 1;
  v11 = *a7;
  if ( *a7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &qword_140009640;
    v13 = 1;
  }
  v23 = v13;
  v20 = a6;
  v22 = v11;
  v24 = 0;
  v21 = 4;
  v14 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v14 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v14 = &qword_140009640;
  }
  v17 = v14;
  v18 = v10;
  v19 = 0;
  return tlgWriteTransfer_GameInputEventWriteTransfer((unsigned int)&dword_14000E000, a2, 0, 0, 6, (__int64)v16);
}

```

## disassembly

```asm
0x14000125c  push    rbp
0x14000125e  lea     rbp, [rsp-37h]
0x140001263  sub     rsp, 0A0h
0x14000126a  mov     rax, cs:__security_cookie
0x140001271  xor     rax, rsp
0x140001274  mov     [rbp+37h+var_10], rax
0x140001278  mov     rax, [rbp+37h+arg_38]
0x14000127c  xor     r9d, r9d
0x14000127f  mov     [rbp+37h+var_20], rax
0x140001283  mov     r10, rdx
0x140001286  mov     rax, [rbp+37h+arg_30]
0x14000128a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000128e  mov     [rbp+37h+var_18], 4
0x140001296  lea     r8d, [r9+1]
0x14000129a  mov     rdx, [rax]
0x14000129d  test    rdx, rdx
0x1400012a0  jz      short loc_1400012B2
0x1400012a2  mov     rax, rcx
0x1400012a5  inc     rax
0x1400012a8  cmp     [rdx+rax], r9b
0x1400012ac  jnz     short loc_1400012A5
0x1400012ae  inc     eax
0x1400012b0  jmp     short loc_1400012BC
0x1400012b2  lea     rdx, qword_140009640
0x1400012b9  mov     eax, r8d
0x1400012bc  mov     [rbp+37h+var_28], eax
0x1400012bf  mov     rax, [rbp+37h+arg_28]
0x1400012c3  mov     [rbp+37h+var_40], rax
0x1400012c7  mov     rax, [rbp+37h+arg_20]
0x1400012cb  mov     [rbp+37h+var_30], rdx
0x1400012cf  mov     [rbp+37h+var_24], r9d
0x1400012d3  mov     [rbp+37h+var_38], 4
0x1400012db  mov     rdx, [rax]
0x1400012de  test    rdx, rdx
0x1400012e1  jz      short loc_1400012F2
0x1400012e3  inc     rcx
0x1400012e6  cmp     [rdx+rcx], r9b
0x1400012ea  jnz     short loc_1400012E3
0x1400012ec  lea     r8d, [rcx+1]
0x1400012f0  jmp     short loc_1400012F9
0x1400012f2  lea     rdx, qword_140009640
0x1400012f9  lea     rax, [rbp+37h+var_70]
0x1400012fd  mov     [rbp+37h+var_50], rdx
0x140001301  mov     [rbp+37h+var_48], r8d
0x140001305  lea     rcx, dword_14000E000
0x14000130c  mov     [rsp+0A0h+var_78], rax
0x140001311  xor     r8d, r8d
0x140001314  mov     rdx, r10
0x140001317  mov     [rsp+0A0h+var_80], 6
0x14000131f  mov     [rbp+37h+var_44], r9d
0x140001323  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x140001328  mov     rcx, [rbp+37h+var_10]
0x14000132c  xor     rcx, rsp; StackCookie
0x14000132f  call    __security_check_cookie
0x140001334  add     rsp, 0A0h
0x14000133b  pop     rbp
0x14000133c  retn
```
