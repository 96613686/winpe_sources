# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001300`
- end: `0x1400013e5`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U3@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@533@Z`
- size: `229`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140014b10`
- `0x140020ed8`
- `0x1400212ec`

## callees

- `0x1400010b4`
- `0x140001300`
- `0x140047e50`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int **a6,
        __int64 *a7,
        __int64 *a8,
        __int64 a9,
        __int64 a10)
{
  int *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-69h] BYREF
  __int64 v15; // [rsp+50h] [rbp-49h]
  __int64 v16; // [rsp+58h] [rbp-41h]
  int *v17; // [rsp+60h] [rbp-39h]
  int v18; // [rsp+68h] [rbp-31h]
  int v19; // [rsp+6Ch] [rbp-2Dh]
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
  v27 = 4;
  v25 = 4;
  v23 = 16;
  v22 = *a8;
  v21 = 16;
  v20 = *a7;
  v10 = *a6;
  if ( *a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &dword_14004E69C;
    v12 = 2;
  }
  v18 = v12;
  v15 = a5;
  v17 = v10;
  v19 = 0;
  v16 = 4;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14005E0C8, a2, 0, 0, 8u, &v14);
}

```

## disassembly

```asm
0x140001300  push    rbp
0x140001302  lea     rbp, [rsp-27h]
0x140001307  sub     rsp, 0C0h
0x14000130e  mov     rax, cs:__security_cookie
0x140001315  xor     rax, rsp
0x140001318  mov     [rbp+27h+var_10], rax
0x14000131c  mov     rax, [rbp+27h+arg_48]
0x140001320  xor     r9d, r9d
0x140001323  mov     [rbp+27h+var_20], rax
0x140001327  mov     rax, [rbp+27h+arg_40]
0x14000132b  mov     [rbp+27h+var_30], rax
0x14000132f  mov     rax, [rbp+27h+arg_38]
0x140001333  mov     [rbp+27h+var_18], 4
0x14000133b  mov     [rbp+27h+var_28], 4
0x140001343  mov     [rbp+27h+var_38], 10h
0x14000134b  mov     rcx, [rax]
0x14000134e  mov     rax, [rbp+27h+arg_30]
0x140001352  mov     [rbp+27h+var_40], rcx
0x140001356  mov     [rbp+27h+var_48], 10h
0x14000135e  mov     rcx, [rax]
0x140001361  mov     rax, [rbp+27h+arg_28]
0x140001365  mov     [rbp+27h+var_50], rcx
0x140001369  mov     rcx, [rax]
0x14000136c  test    rcx, rcx
0x14000136f  jz      short loc_140001388
0x140001371  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001375  inc     rax
0x140001378  cmp     [rcx+rax*2], r9w
0x14000137d  jnz     short loc_140001375
0x14000137f  lea     eax, ds:2[rax*2]
0x140001386  jmp     short loc_140001394
0x140001388  lea     rcx, dword_14004E69C
0x14000138f  mov     eax, 2
0x140001394  mov     [rbp+27h+var_58], eax
0x140001397  xor     r8d, r8d
0x14000139a  mov     rax, [rbp+27h+arg_20]
0x14000139e  mov     [rbp+27h+var_70], rax
0x1400013a2  lea     rax, [rbp+27h+var_90]
0x1400013a6  mov     [rbp+27h+var_60], rcx
0x1400013aa  lea     rcx, dword_14005E0C8
0x1400013b1  mov     [rsp+0C0h+var_98], rax
0x1400013b6  mov     [rsp+0C0h+var_A0], 8
0x1400013be  mov     [rbp+27h+var_54], r9d
0x1400013c2  mov     [rbp+27h+var_68], 4
0x1400013ca  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400013cf  mov     rcx, [rbp+27h+var_10]
0x1400013d3  xor     rcx, rsp; StackCookie
0x1400013d6  call    __security_check_cookie
0x1400013db  add     rsp, 0C0h
0x1400013e2  pop     rbp
0x1400013e3  retn
```
