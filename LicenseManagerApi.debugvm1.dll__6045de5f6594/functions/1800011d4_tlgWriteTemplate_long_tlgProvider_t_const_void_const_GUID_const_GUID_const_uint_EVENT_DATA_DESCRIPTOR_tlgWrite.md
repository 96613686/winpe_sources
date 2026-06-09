# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800011d4`
- end: `0x180001292`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `190`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f060`
- `0x18000fdd0`
- `0x180010cc0`

## callees

- `0x1800011d4`
- `0x180001298`
- `0x180001960`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        void **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  _WORD *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-39h] BYREF
  _WORD *v13; // [rsp+50h] [rbp-19h]
  int v14; // [rsp+58h] [rbp-11h]
  int v15; // [rsp+5Ch] [rbp-Dh]
  __int64 v16; // [rsp+60h] [rbp-9h]
  __int64 v17; // [rsp+68h] [rbp-1h]
  __int64 v18; // [rsp+70h] [rbp+7h]
  __int64 v19; // [rsp+78h] [rbp+Fh]
  __int64 v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]

  v20 = a8;
  v18 = a7;
  v16 = a6;
  v21 = 4;
  v19 = 8;
  v17 = 4;
  v8 = *a5;
  if ( *a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &unk_180016038;
    v10 = 2;
  }
  v14 = v10;
  v13 = v8;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001A010, a2, 0, 0, 6u, &v12);
}

```

## disassembly

```asm
0x1800011d4  push    rbp
0x1800011d6  lea     rbp, [rsp-37h]
0x1800011db  sub     rsp, 0A0h
0x1800011e2  mov     rax, cs:__security_cookie
0x1800011e9  xor     rax, rsp
0x1800011ec  mov     [rbp+37h+var_10], rax
0x1800011f0  mov     rax, [rbp+37h+arg_38]
0x1800011f4  xor     r8d, r8d
0x1800011f7  mov     [rbp+37h+var_20], rax
0x1800011fb  mov     rax, [rbp+37h+arg_30]
0x1800011ff  mov     [rbp+37h+var_30], rax
0x180001203  mov     rax, [rbp+37h+arg_28]
0x180001207  mov     [rbp+37h+var_40], rax
0x18000120b  mov     rax, [rbp+37h+arg_20]
0x18000120f  mov     [rbp+37h+var_18], 4
0x180001217  mov     [rbp+37h+var_28], 8
0x18000121f  mov     [rbp+37h+var_38], 4
0x180001227  mov     rcx, [rax]
0x18000122a  test    rcx, rcx
0x18000122d  jz      short loc_180001246
0x18000122f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001233  inc     rax
0x180001236  cmp     [rcx+rax*2], r8w
0x18000123b  jnz     short loc_180001233
0x18000123d  lea     eax, ds:2[rax*2]
0x180001244  jmp     short loc_180001252
0x180001246  lea     rcx, unk_180016038
0x18000124d  mov     eax, 2
0x180001252  mov     [rbp+37h+var_48], eax
0x180001255  xor     r9d, r9d
0x180001258  lea     rax, [rbp+37h+var_70]
0x18000125c  mov     [rbp+37h+var_50], rcx
0x180001260  mov     [rsp+0A0h+var_78], rax
0x180001265  lea     rcx, dword_18001A010
0x18000126c  mov     [rsp+0A0h+var_80], 6
0x180001274  mov     [rbp+37h+var_44], r8d
0x180001278  call    _tlgWriteTransfer_EventWriteTransfer
0x18000127d  mov     rcx, [rbp+37h+var_10]
0x180001281  xor     rcx, rsp; StackCookie
0x180001284  call    __security_check_cookie
0x180001289  add     rsp, 0A0h
0x180001290  pop     rbp
0x180001291  retn
```
