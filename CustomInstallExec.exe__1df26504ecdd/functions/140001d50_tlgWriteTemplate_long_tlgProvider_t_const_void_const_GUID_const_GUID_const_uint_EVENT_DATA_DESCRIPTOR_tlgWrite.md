# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001d50`
- end: `0x140001e8e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@644@Z`
- size: `318`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64 *, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000afd4`

## callees

- `0x140001d50`
- `0x1400025b8`
- `0x1400033b0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 *a8,
        const unsigned __int16 **a9,
        const unsigned __int16 **a10,
        __int64 a11,
        __int64 a12)
{
  __int64 v14; // rcx
  int v16; // r8d
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rdx
  __int64 v21; // rcx
  _BYTE v23[32]; // [rsp+30h] [rbp-99h] BYREF
  __int64 v24; // [rsp+50h] [rbp-79h]
  __int64 v25; // [rsp+58h] [rbp-71h]
  __int64 v26; // [rsp+60h] [rbp-69h]
  __int64 v27; // [rsp+68h] [rbp-61h]
  __int64 v28; // [rsp+70h] [rbp-59h]
  __int64 v29; // [rsp+78h] [rbp-51h]
  __int64 v30; // [rsp+80h] [rbp-49h]
  __int64 v31; // [rsp+88h] [rbp-41h]
  const unsigned __int16 *v32; // [rsp+90h] [rbp-39h]
  int v33; // [rsp+98h] [rbp-31h]
  int v34; // [rsp+9Ch] [rbp-2Dh]
  const unsigned __int16 *v35; // [rsp+A0h] [rbp-29h]
  int v36; // [rsp+A8h] [rbp-21h]
  int v37; // [rsp+ACh] [rbp-1Dh]
  __int64 v38; // [rsp+B0h] [rbp-19h]
  __int64 v39; // [rsp+B8h] [rbp-11h]
  __int64 v40; // [rsp+C0h] [rbp-9h]
  __int64 v41; // [rsp+C8h] [rbp-1h]

  v40 = a12;
  v38 = a11;
  v14 = -1;
  v41 = 4;
  v16 = 2;
  v39 = 4;
  v17 = *a10;
  if ( *a10 )
  {
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = &qword_140010DA8;
    v19 = 2;
  }
  v36 = v19;
  v35 = v17;
  v37 = 0;
  v20 = *a9;
  if ( *a9 )
  {
    do
      ++v14;
    while ( v20[v14] );
    v16 = 2 * v14 + 2;
  }
  else
  {
    v20 = &qword_140010DA8;
  }
  v32 = v20;
  v33 = v16;
  v34 = 0;
  v21 = *a8;
  v28 = a7;
  v26 = a6;
  v24 = a5;
  v30 = v21;
  v31 = 16;
  v29 = 4;
  v27 = 4;
  v25 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 10, v23);
}

```

## disassembly

```asm
0x140001d50  mov     [rsp-8+arg_18], rbx
0x140001d55  push    rbp
0x140001d56  lea     rbp, [rsp-17h]
0x140001d5b  sub     rsp, 0E0h
0x140001d62  mov     rax, cs:__security_cookie
0x140001d69  xor     rax, rsp
0x140001d6c  mov     [rbp+17h+var_10], rax
0x140001d70  mov     rax, [rbp+17h+arg_58]
0x140001d74  xor     r9d, r9d
0x140001d77  mov     [rbp+17h+var_20], rax
0x140001d7b  mov     r11, rdx
0x140001d7e  mov     rax, [rbp+17h+arg_50]
0x140001d82  mov     r10, rcx
0x140001d85  mov     [rbp+17h+var_30], rax
0x140001d89  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001d8d  mov     rax, [rbp+17h+arg_48]
0x140001d91  mov     rbx, r8
0x140001d94  mov     [rbp+17h+var_18], 4
0x140001d9c  lea     r8d, [r9+2]
0x140001da0  mov     [rbp+17h+var_28], 4
0x140001da8  mov     rdx, [rax]
0x140001dab  test    rdx, rdx
0x140001dae  jz      short loc_140001DC6
0x140001db0  mov     rax, rcx
0x140001db3  inc     rax
0x140001db6  cmp     [rdx+rax*2], r9w
0x140001dbb  jnz     short loc_140001DB3
0x140001dbd  lea     eax, ds:2[rax*2]
0x140001dc4  jmp     short loc_140001DD0
0x140001dc6  lea     rdx, qword_140010DA8
0x140001dcd  mov     eax, r8d
0x140001dd0  mov     [rbp+17h+var_38], eax
0x140001dd3  mov     rax, [rbp+17h+arg_40]
0x140001dd7  mov     [rbp+17h+var_40], rdx
0x140001ddb  mov     [rbp+17h+var_34], r9d
0x140001ddf  mov     rdx, [rax]
0x140001de2  test    rdx, rdx
0x140001de5  jz      short loc_140001DFB
0x140001de7  inc     rcx
0x140001dea  cmp     [rdx+rcx*2], r9w
0x140001def  jnz     short loc_140001DE7
0x140001df1  lea     r8d, ds:2[rcx*2]
0x140001df9  jmp     short loc_140001E02
0x140001dfb  lea     rdx, qword_140010DA8
0x140001e02  mov     rax, [rbp+17h+arg_38]
0x140001e06  mov     [rbp+17h+var_50], rdx
0x140001e0a  mov     rdx, r11
0x140001e0d  mov     [rbp+17h+var_48], r8d
0x140001e11  mov     r8, rbx
0x140001e14  mov     [rbp+17h+var_44], r9d
0x140001e18  mov     rcx, [rax]
0x140001e1b  mov     rax, [rbp+17h+arg_30]
0x140001e1f  mov     [rbp+17h+var_70], rax
0x140001e23  mov     rax, [rbp+17h+arg_28]
0x140001e27  mov     [rbp+17h+var_80], rax
0x140001e2b  mov     rax, [rbp+17h+arg_20]
0x140001e2f  mov     [rbp+17h+var_90], rax
0x140001e33  lea     rax, [rsp+0E0h+var_B0]
0x140001e38  mov     [rbp+17h+var_60], rcx
0x140001e3c  mov     rcx, r10
0x140001e3f  mov     [rsp+0E0h+var_B8], rax
0x140001e44  mov     [rsp+0E0h+var_C0], 0Ah
0x140001e4c  mov     [rbp+17h+var_58], 10h
0x140001e54  mov     [rbp+17h+var_68], 4
0x140001e5c  mov     [rbp+17h+var_78], 4
0x140001e64  mov     [rbp+17h+var_88], 8
0x140001e6c  call    _tlgWriteTransfer_EventWriteTransfer
0x140001e71  mov     rcx, [rbp+17h+var_10]
0x140001e75  xor     rcx, rsp; StackCookie
0x140001e78  call    __security_check_cookie
0x140001e7d  mov     rbx, [rsp+0E0h+arg_18]
0x140001e85  add     rsp, 0E0h
0x140001e8c  pop     rbp
0x140001e8d  retn
```
