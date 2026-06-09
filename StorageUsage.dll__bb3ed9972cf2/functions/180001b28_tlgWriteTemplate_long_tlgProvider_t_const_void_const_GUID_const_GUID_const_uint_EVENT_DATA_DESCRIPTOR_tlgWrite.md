# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001b28`
- end: `0x180001c6a`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U4@U1@U1@U1@U1@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@633336@Z`
- size: `322`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, int **, __int64 *, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b870`

## callees

- `0x180001010`
- `0x180001b28`
- `0x1800050f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int **a7,
        __int64 *a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15)
{
  int *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  _BYTE v19[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+58h] [rbp-A8h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  __int64 v23; // [rsp+68h] [rbp-98h]
  int *v24; // [rsp+70h] [rbp-90h]
  int v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+7Ch] [rbp-84h]
  __int64 v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  __int64 v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  __int64 v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  __int64 v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  __int64 v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  __int64 v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  __int64 v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h]

  v41 = a15;
  v39 = a14;
  v37 = a13;
  v35 = a12;
  v33 = a11;
  v31 = a10;
  v29 = a9;
  v42 = 8;
  v40 = 4;
  v38 = 4;
  v27 = *a8;
  v36 = 4;
  v34 = 4;
  v15 = *a7;
  v32 = 8;
  v30 = 8;
  v28 = 16;
  if ( v15 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &dword_180031EE4;
    v17 = 2;
  }
  v25 = v17;
  v22 = a6;
  v20 = a5;
  v24 = v15;
  v26 = 0;
  v23 = 4;
  v21 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180040010, a2, 0, 0, 13, v19);
}

```

## disassembly

```asm
0x180001b28  push    rbp
0x180001b2a  lea     rbp, [rsp-10h]
0x180001b2f  sub     rsp, 110h
0x180001b36  mov     rax, cs:__security_cookie
0x180001b3d  xor     rax, rsp
0x180001b40  mov     [rbp+10h+var_10], rax
0x180001b44  mov     rax, [rbp+10h+arg_70]
0x180001b4b  xor     r8d, r8d
0x180001b4e  mov     [rbp+10h+var_20], rax
0x180001b52  mov     rax, [rbp+10h+arg_68]
0x180001b59  mov     [rbp+10h+var_30], rax
0x180001b5d  mov     rax, [rbp+10h+arg_60]
0x180001b64  mov     [rbp+10h+var_40], rax
0x180001b68  mov     rax, [rbp+10h+arg_58]
0x180001b6c  mov     [rbp+10h+var_50], rax
0x180001b70  mov     rax, [rbp+10h+arg_50]
0x180001b74  mov     [rbp+10h+var_60], rax
0x180001b78  mov     rax, [rbp+10h+arg_48]
0x180001b7c  mov     [rbp+10h+var_70], rax
0x180001b80  mov     rax, [rbp+10h+arg_40]
0x180001b84  mov     [rbp+10h+var_80], rax
0x180001b88  mov     rax, [rbp+10h+arg_38]
0x180001b8c  mov     [rbp+10h+var_18], 8
0x180001b94  mov     [rbp+10h+var_28], 4
0x180001b9c  mov     [rbp+10h+var_38], 4
0x180001ba4  mov     rcx, [rax]
0x180001ba7  mov     rax, [rbp+10h+arg_30]
0x180001bab  mov     [rbp+10h+var_90], rcx
0x180001baf  mov     [rbp+10h+var_48], 4
0x180001bb7  mov     [rbp+10h+var_58], 4
0x180001bbf  mov     rcx, [rax]
0x180001bc2  mov     [rbp+10h+var_68], 8
0x180001bca  mov     [rbp+10h+var_78], 8
0x180001bd2  mov     [rbp+10h+var_88], 10h
0x180001bda  test    rcx, rcx
0x180001bdd  jz      short loc_180001BF6
0x180001bdf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001be3  inc     rax
0x180001be6  cmp     [rcx+rax*2], r8w
0x180001beb  jnz     short loc_180001BE3
0x180001bed  lea     eax, ds:2[rax*2]
0x180001bf4  jmp     short loc_180001C02
0x180001bf6  lea     rcx, dword_180031EE4
0x180001bfd  mov     eax, 2
0x180001c02  mov     [rsp+110h+var_98], eax
0x180001c06  xor     r9d, r9d
0x180001c09  mov     rax, [rbp+10h+arg_28]
0x180001c0d  mov     [rsp+110h+var_B0], rax
0x180001c12  mov     rax, [rbp+10h+arg_20]
0x180001c16  mov     [rsp+110h+var_C0], rax
0x180001c1b  lea     rax, [rsp+110h+var_E0]
0x180001c20  mov     [rsp+110h+var_A0], rcx
0x180001c25  lea     rcx, dword_180040010
0x180001c2c  mov     [rsp+110h+var_E8], rax
0x180001c31  mov     [rsp+110h+var_F0], 0Dh
0x180001c39  mov     [rsp+110h+var_94], r8d
0x180001c3e  mov     [rsp+110h+var_A8], 4
0x180001c47  mov     [rsp+110h+var_B8], 4
0x180001c50  call    _tlgWriteTransfer_EventWriteTransfer
0x180001c55  mov     rcx, [rbp+10h+var_10]
0x180001c59  xor     rcx, rsp; StackCookie
0x180001c5c  call    __security_check_cookie
0x180001c61  add     rsp, 110h
0x180001c68  pop     rbp
0x180001c69  retn
```
