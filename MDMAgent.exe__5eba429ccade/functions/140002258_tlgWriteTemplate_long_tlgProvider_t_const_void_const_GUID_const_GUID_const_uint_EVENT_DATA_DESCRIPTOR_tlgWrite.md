# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x140002258`
- end: `0x140002314`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x140017808`
- `0x1400178e8`
- `0x140017978`
- `0x1400179f0`
- `0x140017a80`
- `0x140017b10`
- `0x140017c2c`
- `0x140017cbc`
- `0x140017dec`

## callees

- `0x140001f48`
- `0x140002258`
- `0x140002930`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7)
{
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+58h] [rbp-40h]
  __int64 v14; // [rsp+60h] [rbp-38h]
  __int64 v15; // [rsp+68h] [rbp-30h]
  const unsigned __int16 *v16; // [rsp+70h] [rbp-28h]
  int v17; // [rsp+78h] [rbp-20h]
  int v18; // [rsp+7Ch] [rbp-1Ch]

  v7 = *a7;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &byte_14001ACA1;
    v9 = 1;
  }
  v17 = v9;
  v14 = a6;
  v12 = a5;
  v16 = v7;
  v18 = 0;
  v15 = 8;
  v13 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140024000, a2, 0, 0, 5, v11);
}

```

## disassembly

```asm
0x140002258  sub     rsp, 98h
0x14000225f  mov     rax, cs:__security_cookie
0x140002266  xor     rax, rsp
0x140002269  mov     [rsp+98h+var_18], rax
0x140002271  mov     rax, [rsp+98h+arg_30]
0x140002279  xor     r8d, r8d
0x14000227c  mov     rcx, [rax]
0x14000227f  test    rcx, rcx
0x140002282  jz      short loc_140002295
0x140002284  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002288  inc     rax
0x14000228b  cmp     [rcx+rax], r8b
0x14000228f  jnz     short loc_140002288
0x140002291  inc     eax
0x140002293  jmp     short loc_1400022A1
0x140002295  lea     rcx, byte_14001ACA1
0x14000229c  mov     eax, 1
0x1400022a1  mov     [rsp+98h+var_20], eax
0x1400022a5  xor     r9d, r9d
0x1400022a8  mov     rax, [rsp+98h+arg_28]
0x1400022b0  mov     [rsp+98h+var_38], rax
0x1400022b5  mov     rax, [rsp+98h+arg_20]
0x1400022bd  mov     [rsp+98h+var_48], rax
0x1400022c2  lea     rax, [rsp+98h+var_68]
0x1400022c7  mov     [rsp+98h+var_28], rcx
0x1400022cc  lea     rcx, dword_140024000
0x1400022d3  mov     [rsp+98h+var_70], rax
0x1400022d8  mov     [rsp+98h+var_78], 5
0x1400022e0  mov     [rsp+98h+var_1C], r8d
0x1400022e5  mov     [rsp+98h+var_30], 8
0x1400022ee  mov     [rsp+98h+var_40], 4
0x1400022f7  call    _tlgWriteTransfer_EventWriteTransfer
0x1400022fc  mov     rcx, [rsp+98h+var_18]
0x140002304  xor     rcx, rsp; StackCookie
0x140002307  call    __security_check_cookie
0x14000230c  add     rsp, 98h
0x140002313  retn
```
