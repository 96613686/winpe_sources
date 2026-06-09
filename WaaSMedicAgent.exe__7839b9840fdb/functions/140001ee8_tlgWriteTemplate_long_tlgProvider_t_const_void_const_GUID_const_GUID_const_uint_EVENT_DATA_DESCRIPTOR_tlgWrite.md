# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001ee8`
- end: `0x140001fda`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z`
- size: `242`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001002c`

## callees

- `0x14000198c`
- `0x140001ee8`
- `0x140002a30`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        const unsigned __int16 **a7)
{
  __int64 v9; // rcx
  int v10; // r8d
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  _BYTE v16[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v17; // [rsp+50h] [rbp-48h]
  __int64 v18; // [rsp+58h] [rbp-40h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-38h]
  int v20; // [rsp+68h] [rbp-30h]
  int v21; // [rsp+6Ch] [rbp-2Ch]
  const unsigned __int16 *v22; // [rsp+70h] [rbp-28h]
  int v23; // [rsp+78h] [rbp-20h]
  int v24; // [rsp+7Ch] [rbp-1Ch]

  v9 = -1;
  v10 = 2;
  v11 = *a7;
  if ( *a7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &dword_1400158BC;
    v13 = 2;
  }
  v23 = v13;
  v22 = v11;
  v24 = 0;
  v14 = *a6;
  if ( *a6 )
  {
    do
      ++v9;
    while ( v14[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v14 = &dword_1400158BC;
  }
  v17 = a5;
  v19 = v14;
  v20 = v10;
  v21 = 0;
  v18 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5, v16);
}

```

## disassembly

```asm
0x140001ee8  sub     rsp, 98h
0x140001eef  mov     rax, cs:__security_cookie
0x140001ef6  xor     rax, rsp
0x140001ef9  mov     [rsp+98h+var_18], rax
0x140001f01  mov     rax, [rsp+98h+arg_30]
0x140001f09  mov     r11, rdx
0x140001f0c  mov     r10, rcx
0x140001f0f  xor     r9d, r9d
0x140001f12  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001f16  mov     r8d, 2
0x140001f1c  mov     rdx, [rax]
0x140001f1f  test    rdx, rdx
0x140001f22  jz      short loc_140001F3A
0x140001f24  mov     rax, rcx
0x140001f27  inc     rax
0x140001f2a  cmp     [rdx+rax*2], r9w
0x140001f2f  jnz     short loc_140001F27
0x140001f31  lea     eax, ds:2[rax*2]
0x140001f38  jmp     short loc_140001F44
0x140001f3a  lea     rdx, dword_1400158BC
0x140001f41  mov     eax, r8d
0x140001f44  mov     [rsp+98h+var_20], eax
0x140001f48  mov     rax, [rsp+98h+arg_28]
0x140001f50  mov     [rsp+98h+var_28], rdx
0x140001f55  mov     [rsp+98h+var_1C], r9d
0x140001f5a  mov     rdx, [rax]
0x140001f5d  test    rdx, rdx
0x140001f60  jz      short loc_140001F76
0x140001f62  inc     rcx
0x140001f65  cmp     [rdx+rcx*2], r9w
0x140001f6a  jnz     short loc_140001F62
0x140001f6c  lea     r8d, ds:2[rcx*2]
0x140001f74  jmp     short loc_140001F7D
0x140001f76  lea     rdx, dword_1400158BC
0x140001f7d  mov     rax, [rsp+98h+arg_20]
0x140001f85  mov     rcx, r10
0x140001f88  mov     [rsp+98h+var_48], rax
0x140001f8d  lea     rax, [rsp+98h+var_68]
0x140001f92  mov     [rsp+98h+var_38], rdx
0x140001f97  mov     rdx, r11
0x140001f9a  mov     [rsp+98h+var_30], r8d
0x140001f9f  xor     r8d, r8d
0x140001fa2  mov     [rsp+98h+var_70], rax
0x140001fa7  mov     [rsp+98h+var_78], 5
0x140001faf  mov     [rsp+98h+var_2C], r9d
0x140001fb4  mov     [rsp+98h+var_40], 8
0x140001fbd  call    _tlgWriteTransfer_EventWriteTransfer
0x140001fc2  mov     rcx, [rsp+98h+var_18]
0x140001fca  xor     rcx, rsp; StackCookie
0x140001fcd  call    __security_check_cookie
0x140001fd2  add     rsp, 98h
0x140001fd9  retn
```
