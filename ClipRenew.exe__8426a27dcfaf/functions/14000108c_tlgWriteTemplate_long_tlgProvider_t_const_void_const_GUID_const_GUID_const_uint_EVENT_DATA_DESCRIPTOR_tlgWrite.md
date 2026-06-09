# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x14000108c`
- end: `0x14000114a`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const WCHAR **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007dcc`

## callees

- `0x14000108c`
- `0x140001498`
- `0x1400134a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const WCHAR **a7,
        __int64 a8)
{
  const WCHAR *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+50h] [rbp-19h]
  __int64 v14; // [rsp+58h] [rbp-11h]
  __int64 v15; // [rsp+60h] [rbp-9h]
  __int64 v16; // [rsp+68h] [rbp-1h]
  const WCHAR *v17; // [rsp+70h] [rbp+7h]
  int v18; // [rsp+78h] [rbp+Fh]
  int v19; // [rsp+7Ch] [rbp+13h]
  __int64 v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]

  v20 = a8;
  v21 = 8;
  v8 = *a7;
  if ( *a7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &psz;
    v10 = 2;
  }
  v18 = v10;
  v15 = a6;
  v13 = a5;
  v17 = v8;
  v19 = 0;
  v16 = 4;
  v14 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140019000, a2, 0, 0, 6, v12);
}

```

## disassembly

```asm
0x14000108c  push    rbp
0x14000108e  lea     rbp, [rsp-37h]
0x140001093  sub     rsp, 0A0h
0x14000109a  mov     rax, cs:__security_cookie
0x1400010a1  xor     rax, rsp
0x1400010a4  mov     [rbp+37h+var_10], rax
0x1400010a8  mov     rax, [rbp+37h+arg_38]
0x1400010ac  xor     r8d, r8d
0x1400010af  mov     [rbp+37h+var_20], rax
0x1400010b3  mov     rax, [rbp+37h+arg_30]
0x1400010b7  mov     [rbp+37h+var_18], 8
0x1400010bf  mov     rcx, [rax]
0x1400010c2  test    rcx, rcx
0x1400010c5  jz      short loc_1400010DE
0x1400010c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400010cb  inc     rax
0x1400010ce  cmp     [rcx+rax*2], r8w
0x1400010d3  jnz     short loc_1400010CB
0x1400010d5  lea     eax, ds:2[rax*2]
0x1400010dc  jmp     short loc_1400010EA
0x1400010de  lea     rcx, psz
0x1400010e5  mov     eax, 2
0x1400010ea  mov     [rbp+37h+var_28], eax
0x1400010ed  xor     r9d, r9d
0x1400010f0  mov     rax, [rbp+37h+arg_28]
0x1400010f4  mov     [rbp+37h+var_40], rax
0x1400010f8  mov     rax, [rbp+37h+arg_20]
0x1400010fc  mov     [rbp+37h+var_50], rax
0x140001100  lea     rax, [rbp+37h+var_70]
0x140001104  mov     [rbp+37h+var_30], rcx
0x140001108  lea     rcx, dword_140019000
0x14000110f  mov     [rsp+0A0h+var_78], rax
0x140001114  mov     [rsp+0A0h+var_80], 6
0x14000111c  mov     [rbp+37h+var_24], r8d
0x140001120  mov     [rbp+37h+var_38], 4
0x140001128  mov     [rbp+37h+var_48], 4
0x140001130  call    _tlgWriteTransfer_EventWriteTransfer
0x140001135  mov     rcx, [rbp+37h+var_10]
0x140001139  xor     rcx, rsp; StackCookie
0x14000113c  call    __security_check_cookie
0x140001141  add     rsp, 0A0h
0x140001148  pop     rbp
0x140001149  retn
```
