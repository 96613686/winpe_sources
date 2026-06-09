# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)

- ea: `0x1800029b4`
- end: `0x180002ac2`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperArray@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperArray@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, int **, __int64, __int64 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e310`

## callees

- `0x180001010`
- `0x1800029b4`
- `0x1800050f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int **a7,
        __int64 a8,
        __int64 *a9,
        unsigned __int16 **a10)
{
  int v11; // edx
  int v12; // ecx
  int *v13; // rcx
  __int64 v14; // rax
  _BYTE v16[32]; // [rsp+30h] [rbp-89h] BYREF
  __int64 v17; // [rsp+50h] [rbp-69h]
  __int64 v18; // [rsp+58h] [rbp-61h]
  __int64 v19; // [rsp+60h] [rbp-59h]
  __int64 v20; // [rsp+68h] [rbp-51h]
  int *v21; // [rsp+70h] [rbp-49h]
  int v22; // [rsp+78h] [rbp-41h]
  int v23; // [rsp+7Ch] [rbp-3Dh]
  __int64 v24; // [rsp+80h] [rbp-39h]
  __int64 v25; // [rsp+88h] [rbp-31h]
  __int64 *v26; // [rsp+90h] [rbp-29h]
  __int64 v27; // [rsp+98h] [rbp-21h]
  __int64 v28; // [rsp+A0h] [rbp-19h]
  int v29; // [rsp+A8h] [rbp-11h]
  int v30; // [rsp+ACh] [rbp-Dh]
  _DWORD *v31; // [rsp+B0h] [rbp-9h]
  __int64 v32; // [rsp+B8h] [rbp-1h]
  __int64 v33; // [rsp+C0h] [rbp+7h]
  _DWORD v34[2]; // [rsp+C8h] [rbp+Fh] BYREF

  v31 = v34;
  v11 = 2;
  v32 = 2;
  v12 = **a10;
  v33 = *((_QWORD *)*a10 + 1);
  v34[0] = v12;
  v34[1] = 0;
  v27 = 2;
  v30 = 0;
  v28 = *a9;
  v29 = 8 * *((unsigned __int16 *)a9 + 4);
  v24 = a8;
  v26 = a9 + 1;
  v25 = 4;
  v13 = *a7;
  if ( *a7 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    v11 = 2 * v14 + 2;
  }
  else
  {
    v13 = &dword_180031EE4;
  }
  v19 = a6;
  v17 = a5;
  v21 = v13;
  v22 = v11;
  v23 = 0;
  v20 = 4;
  v18 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180040010, a2, 0, 0, 10, v16);
}

```

## disassembly

```asm
0x1800029b4  push    rbp
0x1800029b6  lea     rbp, [rsp-27h]
0x1800029bb  sub     rsp, 0E0h
0x1800029c2  mov     rax, cs:__security_cookie
0x1800029c9  xor     rax, rsp
0x1800029cc  mov     [rbp+27h+var_10], rax
0x1800029d0  lea     rax, [rbp+27h+var_18]
0x1800029d4  xor     r8d, r8d
0x1800029d7  mov     [rbp+27h+var_30], rax
0x1800029db  mov     r10, rdx
0x1800029de  mov     rax, [rbp+27h+arg_48]
0x1800029e2  mov     edx, 2
0x1800029e7  mov     [rbp+27h+var_28], rdx
0x1800029eb  mov     rax, [rax]
0x1800029ee  movzx   ecx, word ptr [rax]
0x1800029f1  mov     rax, [rax+8]
0x1800029f5  mov     [rbp+27h+var_20], rax
0x1800029f9  mov     rax, [rbp+27h+arg_40]
0x1800029fd  mov     [rbp+27h+var_18], ecx
0x180002a00  mov     [rbp+27h+var_14], r8d
0x180002a04  mov     [rbp+27h+var_48], rdx
0x180002a08  lea     rcx, [rax+8]
0x180002a0c  mov     [rbp+27h+var_34], r8d
0x180002a10  mov     rax, [rax]
0x180002a13  mov     [rbp+27h+var_40], rax
0x180002a17  movzx   eax, word ptr [rcx]
0x180002a1a  shl     eax, 3
0x180002a1d  mov     [rbp+27h+var_38], eax
0x180002a20  mov     rax, [rbp+27h+arg_38]
0x180002a24  mov     [rbp+27h+var_60], rax
0x180002a28  mov     rax, [rbp+27h+arg_30]
0x180002a2c  mov     [rbp+27h+var_50], rcx
0x180002a30  mov     [rbp+27h+var_58], 4
0x180002a38  mov     rcx, [rax]
0x180002a3b  test    rcx, rcx
0x180002a3e  jz      short loc_180002A57
0x180002a40  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002a44  inc     rax
0x180002a47  cmp     [rcx+rax*2], r8w
0x180002a4c  jnz     short loc_180002A44
0x180002a4e  lea     edx, ds:2[rax*2]
0x180002a55  jmp     short loc_180002A5E
0x180002a57  lea     rcx, dword_180031EE4
0x180002a5e  mov     rax, [rbp+27h+arg_28]
0x180002a62  xor     r9d, r9d
0x180002a65  mov     [rbp+27h+var_80], rax
0x180002a69  mov     rax, [rbp+27h+arg_20]
0x180002a6d  mov     [rbp+27h+var_90], rax
0x180002a71  lea     rax, [rsp+0E0h+var_B0]
0x180002a76  mov     [rbp+27h+var_70], rcx
0x180002a7a  lea     rcx, dword_180040010
0x180002a81  mov     [rbp+27h+var_68], edx
0x180002a84  mov     rdx, r10
0x180002a87  mov     [rsp+0E0h+var_B8], rax
0x180002a8c  mov     [rsp+0E0h+var_C0], 0Ah
0x180002a94  mov     [rbp+27h+var_64], r8d
0x180002a98  mov     [rbp+27h+var_78], 4
0x180002aa0  mov     [rbp+27h+var_88], 8
0x180002aa8  call    _tlgWriteTransfer_EventWriteTransfer
0x180002aad  mov     rcx, [rbp+27h+var_10]
0x180002ab1  xor     rcx, rsp; StackCookie
0x180002ab4  call    __security_check_cookie
0x180002ab9  add     rsp, 0E0h
0x180002ac0  pop     rbp
0x180002ac1  retn
```
