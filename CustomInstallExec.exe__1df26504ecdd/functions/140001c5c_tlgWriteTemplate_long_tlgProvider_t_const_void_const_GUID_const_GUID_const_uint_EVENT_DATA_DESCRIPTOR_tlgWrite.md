# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001c5c`
- end: `0x140001d4a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@34@Z`
- size: `238`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64 *, const unsigned __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ad14`

## callees

- `0x140001c5c`
- `0x1400025b8`
- `0x1400033b0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 *a8,
        const unsigned __int16 **a9,
        __int64 a10,
        __int64 a11)
{
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  _BYTE v17[32]; // [rsp+30h] [rbp-81h] BYREF
  __int64 v18; // [rsp+50h] [rbp-61h]
  __int64 v19; // [rsp+58h] [rbp-59h]
  __int64 v20; // [rsp+60h] [rbp-51h]
  __int64 v21; // [rsp+68h] [rbp-49h]
  __int64 v22; // [rsp+70h] [rbp-41h]
  __int64 v23; // [rsp+78h] [rbp-39h]
  __int64 v24; // [rsp+80h] [rbp-31h]
  __int64 v25; // [rsp+88h] [rbp-29h]
  const unsigned __int16 *v26; // [rsp+90h] [rbp-21h]
  int v27; // [rsp+98h] [rbp-19h]
  int v28; // [rsp+9Ch] [rbp-15h]
  __int64 v29; // [rsp+A0h] [rbp-11h]
  __int64 v30; // [rsp+A8h] [rbp-9h]
  __int64 v31; // [rsp+B0h] [rbp-1h]
  __int64 v32; // [rsp+B8h] [rbp+7h]

  v31 = a11;
  v29 = a10;
  v32 = 4;
  v30 = 8;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &qword_140010DA8;
    v14 = 2;
  }
  v27 = v14;
  v26 = v12;
  v28 = 0;
  v25 = 16;
  v15 = *a8;
  v22 = a7;
  v20 = a6;
  v18 = a5;
  v24 = v15;
  v23 = 4;
  v21 = 4;
  v19 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 9, v17);
}

```

## disassembly

```asm
0x140001c5c  push    rbp
0x140001c5e  lea     rbp, [rsp-1Fh]
0x140001c63  sub     rsp, 0D0h
0x140001c6a  mov     rax, cs:__security_cookie
0x140001c71  xor     rax, rsp
0x140001c74  mov     [rbp+1Fh+var_10], rax
0x140001c78  mov     rax, [rbp+1Fh+arg_50]
0x140001c7c  mov     r10, rcx
0x140001c7f  mov     [rbp+1Fh+var_20], rax
0x140001c83  xor     r9d, r9d
0x140001c86  mov     rax, [rbp+1Fh+arg_48]
0x140001c8a  mov     [rbp+1Fh+var_30], rax
0x140001c8e  mov     rax, [rbp+1Fh+arg_40]
0x140001c92  mov     [rbp+1Fh+var_18], 4
0x140001c9a  mov     [rbp+1Fh+var_28], 8
0x140001ca2  mov     rcx, [rax]
0x140001ca5  test    rcx, rcx
0x140001ca8  jz      short loc_140001CC1
0x140001caa  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001cae  inc     rax
0x140001cb1  cmp     [rcx+rax*2], r9w
0x140001cb6  jnz     short loc_140001CAE
0x140001cb8  lea     eax, ds:2[rax*2]
0x140001cbf  jmp     short loc_140001CCD
0x140001cc1  lea     rcx, qword_140010DA8
0x140001cc8  mov     eax, 2
0x140001ccd  mov     [rbp+1Fh+var_38], eax
0x140001cd0  mov     rax, [rbp+1Fh+arg_38]
0x140001cd4  mov     [rbp+1Fh+var_40], rcx
0x140001cd8  mov     [rbp+1Fh+var_34], r9d
0x140001cdc  mov     [rbp+1Fh+var_48], 10h
0x140001ce4  mov     rcx, [rax]
0x140001ce7  mov     rax, [rbp+1Fh+arg_30]
0x140001ceb  mov     [rbp+1Fh+var_60], rax
0x140001cef  mov     rax, [rbp+1Fh+arg_28]
0x140001cf3  mov     [rbp+1Fh+var_70], rax
0x140001cf7  mov     rax, [rbp+1Fh+arg_20]
0x140001cfb  mov     [rbp+1Fh+var_80], rax
0x140001cff  lea     rax, [rsp+0D0h+var_A0]
0x140001d04  mov     [rbp+1Fh+var_50], rcx
0x140001d08  mov     rcx, r10
0x140001d0b  mov     [rsp+0D0h+var_A8], rax
0x140001d10  mov     [rsp+0D0h+var_B0], 9
0x140001d18  mov     [rbp+1Fh+var_58], 4
0x140001d20  mov     [rbp+1Fh+var_68], 4
0x140001d28  mov     [rbp+1Fh+var_78], 8
0x140001d30  call    _tlgWriteTransfer_EventWriteTransfer
0x140001d35  mov     rcx, [rbp+1Fh+var_10]
0x140001d39  xor     rcx, rsp; StackCookie
0x140001d3c  call    __security_check_cookie
0x140001d41  add     rsp, 0D0h
0x140001d48  pop     rbp
0x140001d49  retn
```
