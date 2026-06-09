# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001008`
- end: `0x1400010c3`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `187`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64 **, __int64, __int64)`
- caller_count: `25`
- callee_count: `3`
- tags: ``

## callers

- `0x1400017c8`
- `0x14000199c`
- `0x140001cec`
- `0x140001d80`
- `0x140001e5c`
- `0x1400021f4`
- `0x140002340`
- `0x1400025fc`
- `0x140002798`
- `0x1400028f8`
- `0x140002ac0`
- `0x140003624`
- `0x140003a18`
- `0x140003c5c`
- `0x140003e54`
- `0x140004b48`
- `0x140004c20`
- `0x14000563c`
- `0x14000578c`
- `0x140005930`
- `0x1400059bc`
- `0x140005a88`
- `0x140006b74`
- `0x140006c94`
- `0x140006de4`

## callees

- `0x140001008`
- `0x1400010cc`
- `0x140007750`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 a7)
{
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v12; // [rsp+50h] [rbp-48h]
  int v13; // [rsp+58h] [rbp-40h]
  int v14; // [rsp+5Ch] [rbp-3Ch]
  __int64 v15; // [rsp+60h] [rbp-38h]
  __int64 v16; // [rsp+68h] [rbp-30h]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v15 = a6;
  v18 = 4;
  v16 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &qword_140009640;
    v9 = 1;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_GameInputEventWriteTransfer((unsigned int)&dword_14000E000, a2, 0, 0, 5, (__int64)v11);
}

```

## disassembly

```asm
0x140001008  mov     r11, rsp
0x14000100b  sub     rsp, 98h
0x140001012  mov     rax, cs:__security_cookie
0x140001019  xor     rax, rsp
0x14000101c  mov     [rsp+98h+var_18], rax
0x140001024  mov     rax, [rsp+98h+arg_30]
0x14000102c  xor     r8d, r8d
0x14000102f  mov     [r11-28h], rax
0x140001033  mov     rax, [rsp+98h+arg_28]
0x14000103b  mov     [r11-38h], rax
0x14000103f  mov     rax, [rsp+98h+arg_20]
0x140001047  mov     qword ptr [r11-20h], 4
0x14000104f  mov     qword ptr [r11-30h], 4
0x140001057  mov     rcx, [rax]
0x14000105a  test    rcx, rcx
0x14000105d  jz      short loc_140001070
0x14000105f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001063  inc     rax
0x140001066  cmp     [rcx+rax], r8b
0x14000106a  jnz     short loc_140001063
0x14000106c  inc     eax
0x14000106e  jmp     short loc_14000107C
0x140001070  lea     rcx, qword_140009640
0x140001077  mov     eax, 1
0x14000107c  mov     [rsp+98h+var_40], eax
0x140001080  xor     r9d, r9d
0x140001083  lea     rax, [rsp+98h+var_68]
0x140001088  mov     [rsp+98h+var_48], rcx
0x14000108d  mov     [rsp+98h+var_70], rax
0x140001092  lea     rcx, dword_14000E000
0x140001099  mov     [rsp+98h+var_78], 5
0x1400010a1  mov     [rsp+98h+var_3C], r8d
0x1400010a6  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x1400010ab  mov     rcx, [rsp+98h+var_18]
0x1400010b3  xor     rcx, rsp; StackCookie
0x1400010b6  call    __security_check_cookie
0x1400010bb  add     rsp, 98h
0x1400010c2  retn
```
