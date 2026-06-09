# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400013c4`
- end: `0x140001492`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@33@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const WCHAR **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007dcc`

## callees

- `0x1400013c4`
- `0x140001498`
- `0x1400134a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const WCHAR **a7,
        __int64 a8,
        __int64 a9)
{
  const WCHAR *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-51h] BYREF
  __int64 v14; // [rsp+50h] [rbp-31h]
  __int64 v15; // [rsp+58h] [rbp-29h]
  __int64 v16; // [rsp+60h] [rbp-21h]
  __int64 v17; // [rsp+68h] [rbp-19h]
  const WCHAR *v18; // [rsp+70h] [rbp-11h]
  int v19; // [rsp+78h] [rbp-9h]
  int v20; // [rsp+7Ch] [rbp-5h]
  __int64 v21; // [rsp+80h] [rbp-1h]
  __int64 v22; // [rsp+88h] [rbp+7h]
  __int64 v23; // [rsp+90h] [rbp+Fh]
  __int64 v24; // [rsp+98h] [rbp+17h]

  v23 = a9;
  v21 = a8;
  v24 = 8;
  v22 = 8;
  v9 = *a7;
  if ( *a7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &psz;
    v11 = 2;
  }
  v19 = v11;
  v16 = a6;
  v14 = a5;
  v18 = v9;
  v20 = 0;
  v17 = 4;
  v15 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140019000, a2, 0, 0, 7, v13);
}

```

## disassembly

```asm
0x1400013c4  push    rbp
0x1400013c6  lea     rbp, [rsp-2Fh]
0x1400013cb  sub     rsp, 0B0h
0x1400013d2  mov     rax, cs:__security_cookie
0x1400013d9  xor     rax, rsp
0x1400013dc  mov     [rbp+2Fh+var_10], rax
0x1400013e0  mov     rax, [rbp+2Fh+arg_40]
0x1400013e4  xor     r8d, r8d
0x1400013e7  mov     [rbp+2Fh+var_20], rax
0x1400013eb  mov     rax, [rbp+2Fh+arg_38]
0x1400013ef  mov     [rbp+2Fh+var_30], rax
0x1400013f3  mov     rax, [rbp+2Fh+arg_30]
0x1400013f7  mov     [rbp+2Fh+var_18], 8
0x1400013ff  mov     [rbp+2Fh+var_28], 8
0x140001407  mov     rcx, [rax]
0x14000140a  test    rcx, rcx
0x14000140d  jz      short loc_140001426
0x14000140f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001413  inc     rax
0x140001416  cmp     [rcx+rax*2], r8w
0x14000141b  jnz     short loc_140001413
0x14000141d  lea     eax, ds:2[rax*2]
0x140001424  jmp     short loc_140001432
0x140001426  lea     rcx, psz
0x14000142d  mov     eax, 2
0x140001432  mov     [rbp+2Fh+var_38], eax
0x140001435  xor     r9d, r9d
0x140001438  mov     rax, [rbp+2Fh+arg_28]
0x14000143c  mov     [rbp+2Fh+var_50], rax
0x140001440  mov     rax, [rbp+2Fh+arg_20]
0x140001444  mov     [rbp+2Fh+var_60], rax
0x140001448  lea     rax, [rbp+2Fh+var_80]
0x14000144c  mov     [rbp+2Fh+var_40], rcx
0x140001450  lea     rcx, dword_140019000
0x140001457  mov     [rsp+0B0h+var_88], rax
0x14000145c  mov     [rsp+0B0h+var_90], 7
0x140001464  mov     [rbp+2Fh+var_34], r8d
0x140001468  mov     [rbp+2Fh+var_48], 4
0x140001470  mov     [rbp+2Fh+var_58], 8
0x140001478  call    _tlgWriteTransfer_EventWriteTransfer
0x14000147d  mov     rcx, [rbp+2Fh+var_10]
0x140001481  xor     rcx, rsp; StackCookie
0x140001484  call    __security_check_cookie
0x140001489  add     rsp, 0B0h
0x140001490  pop     rbp
0x140001491  retn
```
