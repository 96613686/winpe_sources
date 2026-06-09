# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400013e8`
- end: `0x1400014ac`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 *, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007ebc`

## callees

- `0x1400013e8`
- `0x1400025b8`
- `0x1400033b0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        const unsigned __int16 **a6,
        __int64 a7)
{
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v13; // [rsp+50h] [rbp-48h]
  __int64 v14; // [rsp+58h] [rbp-40h]
  const unsigned __int16 *v15; // [rsp+60h] [rbp-38h]
  int v16; // [rsp+68h] [rbp-30h]
  int v17; // [rsp+6Ch] [rbp-2Ch]
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int64 v19; // [rsp+78h] [rbp-20h]

  v18 = a7;
  v19 = 8;
  v8 = *a6;
  if ( *a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &qword_140010DA8;
    v10 = 2;
  }
  v16 = v10;
  v15 = v8;
  v17 = 0;
  v14 = 16;
  v13 = *a5;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5, v12);
}

```

## disassembly

```asm
0x1400013e8  sub     rsp, 98h
0x1400013ef  mov     rax, cs:__security_cookie
0x1400013f6  xor     rax, rsp
0x1400013f9  mov     [rsp+98h+var_18], rax
0x140001401  mov     rax, [rsp+98h+arg_30]
0x140001409  mov     r10, rcx
0x14000140c  mov     [rsp+98h+var_28], rax
0x140001411  xor     r9d, r9d
0x140001414  mov     rax, [rsp+98h+arg_28]
0x14000141c  mov     [rsp+98h+var_20], 8
0x140001425  mov     rcx, [rax]
0x140001428  test    rcx, rcx
0x14000142b  jz      short loc_140001444
0x14000142d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001431  inc     rax
0x140001434  cmp     [rcx+rax*2], r9w
0x140001439  jnz     short loc_140001431
0x14000143b  lea     eax, ds:2[rax*2]
0x140001442  jmp     short loc_140001450
0x140001444  lea     rcx, qword_140010DA8
0x14000144b  mov     eax, 2
0x140001450  mov     [rsp+98h+var_30], eax
0x140001454  mov     rax, [rsp+98h+arg_20]
0x14000145c  mov     [rsp+98h+var_38], rcx
0x140001461  mov     rcx, r10
0x140001464  mov     [rsp+98h+var_2C], r9d
0x140001469  mov     [rsp+98h+var_40], 10h
0x140001472  mov     r8, [rax]
0x140001475  lea     rax, [rsp+98h+var_68]
0x14000147a  mov     [rsp+98h+var_48], r8
0x14000147f  xor     r8d, r8d
0x140001482  mov     [rsp+98h+var_70], rax
0x140001487  mov     [rsp+98h+var_78], 5
0x14000148f  call    _tlgWriteTransfer_EventWriteTransfer
0x140001494  mov     rcx, [rsp+98h+var_18]
0x14000149c  xor     rcx, rsp; StackCookie
0x14000149f  call    __security_check_cookie
0x1400014a4  add     rsp, 98h
0x1400014ab  retn
```
