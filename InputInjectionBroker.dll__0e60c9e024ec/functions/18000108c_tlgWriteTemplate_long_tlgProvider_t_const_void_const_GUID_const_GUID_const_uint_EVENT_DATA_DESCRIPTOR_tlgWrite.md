# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000108c`
- end: `0x180001164`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4444@Z`
- size: `216`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800106f0`
- `0x1800107a4`

## callees

- `0x18000108c`
- `0x18000125c`
- `0x180011460`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  const unsigned __int16 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  _BYTE v14[32]; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v15; // [rsp+50h] [rbp-49h]
  int v16; // [rsp+58h] [rbp-41h]
  int v17; // [rsp+5Ch] [rbp-3Dh]
  __int64 v18; // [rsp+60h] [rbp-39h]
  __int64 v19; // [rsp+68h] [rbp-31h]
  __int64 v20; // [rsp+70h] [rbp-29h]
  __int64 v21; // [rsp+78h] [rbp-21h]
  __int64 v22; // [rsp+80h] [rbp-19h]
  __int64 v23; // [rsp+88h] [rbp-11h]
  __int64 v24; // [rsp+90h] [rbp-9h]
  __int64 v25; // [rsp+98h] [rbp-1h]
  __int64 v26; // [rsp+A0h] [rbp+7h]
  __int64 v27; // [rsp+A8h] [rbp+Fh]

  v26 = a10;
  v24 = a9;
  v22 = a8;
  v20 = a7;
  v18 = a6;
  v27 = 4;
  v25 = 4;
  v23 = 4;
  v10 = *a5;
  v21 = 4;
  v19 = 4;
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_BYTE *)v10 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v10 = &qword_18001B630;
    v12 = 1;
  }
  v16 = v12;
  v15 = v10;
  v17 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180022000, a2, 0, 0, 8, v14);
}

```

## disassembly

```asm
0x18000108c  push    rbp
0x18000108e  lea     rbp, [rsp-27h]
0x180001093  sub     rsp, 0C0h
0x18000109a  mov     rax, cs:__security_cookie
0x1800010a1  xor     rax, rsp
0x1800010a4  mov     [rbp+27h+var_10], rax
0x1800010a8  mov     rax, [rbp+27h+arg_48]
0x1800010ac  xor     r8d, r8d
0x1800010af  mov     [rbp+27h+var_20], rax
0x1800010b3  mov     rax, [rbp+27h+arg_40]
0x1800010b7  mov     [rbp+27h+var_30], rax
0x1800010bb  mov     rax, [rbp+27h+arg_38]
0x1800010bf  mov     [rbp+27h+var_40], rax
0x1800010c3  mov     rax, [rbp+27h+arg_30]
0x1800010c7  mov     [rbp+27h+var_50], rax
0x1800010cb  mov     rax, [rbp+27h+arg_28]
0x1800010cf  mov     [rbp+27h+var_60], rax
0x1800010d3  mov     rax, [rbp+27h+arg_20]
0x1800010d7  mov     [rbp+27h+var_18], 4
0x1800010df  mov     [rbp+27h+var_28], 4
0x1800010e7  mov     [rbp+27h+var_38], 4
0x1800010ef  mov     rcx, [rax]
0x1800010f2  mov     [rbp+27h+var_48], 4
0x1800010fa  mov     [rbp+27h+var_58], 4
0x180001102  test    rcx, rcx
0x180001105  jz      short loc_180001118
0x180001107  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000110b  inc     rax
0x18000110e  cmp     [rcx+rax], r8b
0x180001112  jnz     short loc_18000110B
0x180001114  inc     eax
0x180001116  jmp     short loc_180001124
0x180001118  lea     rcx, qword_18001B630
0x18000111f  mov     eax, 1
0x180001124  mov     [rbp+27h+var_68], eax
0x180001127  xor     r9d, r9d
0x18000112a  lea     rax, [rbp+27h+var_90]
0x18000112e  mov     [rbp+27h+var_70], rcx
0x180001132  mov     [rsp+0C0h+var_98], rax
0x180001137  lea     rcx, dword_180022000
0x18000113e  mov     [rsp+0C0h+var_A0], 8
0x180001146  mov     [rbp+27h+var_64], r8d
0x18000114a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000114f  mov     rcx, [rbp+27h+var_10]
0x180001153  xor     rcx, rsp; StackCookie
0x180001156  call    __security_check_cookie
0x18000115b  add     rsp, 0C0h
0x180001162  pop     rbp
0x180001163  retn
```
