# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400011e8`
- end: `0x1400012aa`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const WCHAR **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007dcc`

## callees

- `0x1400011e8`
- `0x140001498`
- `0x1400134a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const WCHAR **a6,
        __int64 a7)
{
  const WCHAR *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+58h] [rbp-40h]
  const WCHAR *v14; // [rsp+60h] [rbp-38h]
  int v15; // [rsp+68h] [rbp-30h]
  int v16; // [rsp+6Ch] [rbp-2Ch]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v18 = 8;
  v7 = *a6;
  if ( *a6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &psz;
    v9 = 2;
  }
  v15 = v9;
  v12 = a5;
  v14 = v7;
  v16 = 0;
  v13 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140019000, a2, 0, 0, 5, v11);
}

```

## disassembly

```asm
0x1400011e8  sub     rsp, 98h
0x1400011ef  mov     rax, cs:__security_cookie
0x1400011f6  xor     rax, rsp
0x1400011f9  mov     [rsp+98h+var_18], rax
0x140001201  mov     rax, [rsp+98h+arg_30]
0x140001209  xor     r8d, r8d
0x14000120c  mov     [rsp+98h+var_28], rax
0x140001211  mov     rax, [rsp+98h+arg_28]
0x140001219  mov     [rsp+98h+var_20], 8
0x140001222  mov     rcx, [rax]
0x140001225  test    rcx, rcx
0x140001228  jz      short loc_140001241
0x14000122a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000122e  inc     rax
0x140001231  cmp     [rcx+rax*2], r8w
0x140001236  jnz     short loc_14000122E
0x140001238  lea     eax, ds:2[rax*2]
0x14000123f  jmp     short loc_14000124D
0x140001241  lea     rcx, psz
0x140001248  mov     eax, 2
0x14000124d  mov     [rsp+98h+var_30], eax
0x140001251  xor     r9d, r9d
0x140001254  mov     rax, [rsp+98h+arg_20]
0x14000125c  mov     [rsp+98h+var_48], rax
0x140001261  lea     rax, [rsp+98h+var_68]
0x140001266  mov     [rsp+98h+var_38], rcx
0x14000126b  lea     rcx, dword_140019000
0x140001272  mov     [rsp+98h+var_70], rax
0x140001277  mov     [rsp+98h+var_78], 5
0x14000127f  mov     [rsp+98h+var_2C], r8d
0x140001284  mov     [rsp+98h+var_40], 4
0x14000128d  call    _tlgWriteTransfer_EventWriteTransfer
0x140001292  mov     rcx, [rsp+98h+var_18]
0x14000129a  xor     rcx, rsp; StackCookie
0x14000129d  call    __security_check_cookie
0x1400012a2  add     rsp, 98h
0x1400012a9  retn
```
