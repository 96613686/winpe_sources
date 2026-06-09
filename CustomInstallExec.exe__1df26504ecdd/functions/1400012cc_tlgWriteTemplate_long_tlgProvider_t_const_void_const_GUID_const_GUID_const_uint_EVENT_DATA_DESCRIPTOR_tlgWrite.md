# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400012cc`
- end: `0x1400013df`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 *, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008964`

## callees

- `0x1400012cc`
- `0x1400025b8`
- `0x1400033b0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        const unsigned __int16 **a6,
        const unsigned __int16 **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v12; // rcx
  int v14; // r8d
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  _BYTE v20[32]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v21; // [rsp+50h] [rbp-59h]
  __int64 v22; // [rsp+58h] [rbp-51h]
  const unsigned __int16 *v23; // [rsp+60h] [rbp-49h]
  int v24; // [rsp+68h] [rbp-41h]
  int v25; // [rsp+6Ch] [rbp-3Dh]
  const unsigned __int16 *v26; // [rsp+70h] [rbp-39h]
  int v27; // [rsp+78h] [rbp-31h]
  int v28; // [rsp+7Ch] [rbp-2Dh]
  __int64 v29; // [rsp+80h] [rbp-29h]
  __int64 v30; // [rsp+88h] [rbp-21h]
  __int64 v31; // [rsp+90h] [rbp-19h]
  __int64 v32; // [rsp+98h] [rbp-11h]
  __int64 v33; // [rsp+A0h] [rbp-9h]
  __int64 v34; // [rsp+A8h] [rbp-1h]

  v33 = a10;
  v31 = a9;
  v12 = -1;
  v29 = a8;
  v14 = 2;
  v34 = 8;
  v32 = 4;
  v30 = 4;
  v15 = *a7;
  if ( *a7 )
  {
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &qword_140010DA8;
    v17 = 2;
  }
  v27 = v17;
  v26 = v15;
  v28 = 0;
  v18 = *a6;
  if ( *a6 )
  {
    do
      ++v12;
    while ( v18[v12] );
    v14 = 2 * v12 + 2;
  }
  else
  {
    v18 = &qword_140010DA8;
  }
  v23 = v18;
  v24 = v14;
  v25 = 0;
  v21 = *a5;
  v22 = 16;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 8, v20);
}

```

## disassembly

```asm
0x1400012cc  push    rbp
0x1400012ce  push    rbx
0x1400012cf  push    rdi
0x1400012d0  lea     rbp, [rsp-17h]
0x1400012d5  sub     rsp, 0C0h
0x1400012dc  mov     rax, cs:__security_cookie
0x1400012e3  xor     rax, rsp
0x1400012e6  mov     [rbp+27h+var_20], rax
0x1400012ea  mov     rax, [rbp+27h+arg_48]
0x1400012ee  xor     edi, edi
0x1400012f0  mov     [rbp+27h+var_30], rax
0x1400012f4  mov     r11, rdx
0x1400012f7  mov     rax, [rbp+27h+arg_40]
0x1400012fb  mov     r10, rcx
0x1400012fe  mov     [rbp+27h+var_40], rax
0x140001302  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001306  mov     rax, [rbp+27h+arg_38]
0x14000130a  mov     rbx, r8
0x14000130d  mov     [rbp+27h+var_50], rax
0x140001311  lea     r8d, [rdi+2]
0x140001315  mov     rax, [rbp+27h+arg_30]
0x140001319  mov     [rbp+27h+var_28], 8
0x140001321  mov     [rbp+27h+var_38], 4
0x140001329  mov     [rbp+27h+var_48], 4
0x140001331  mov     rdx, [rax]
0x140001334  test    rdx, rdx
0x140001337  jz      short loc_14000134E
0x140001339  mov     rax, rcx
0x14000133c  inc     rax
0x14000133f  cmp     [rdx+rax*2], di
0x140001343  jnz     short loc_14000133C
0x140001345  lea     eax, ds:2[rax*2]
0x14000134c  jmp     short loc_140001358
0x14000134e  lea     rdx, qword_140010DA8
0x140001355  mov     eax, r8d
0x140001358  mov     [rbp+27h+var_58], eax
0x14000135b  mov     rax, [rbp+27h+arg_28]
0x14000135f  mov     [rbp+27h+var_60], rdx
0x140001363  mov     [rbp+27h+var_54], edi
0x140001366  mov     rdx, [rax]
0x140001369  test    rdx, rdx
0x14000136c  jz      short loc_140001381
0x14000136e  inc     rcx
0x140001371  cmp     [rdx+rcx*2], di
0x140001375  jnz     short loc_14000136E
0x140001377  lea     r8d, ds:2[rcx*2]
0x14000137f  jmp     short loc_140001388
0x140001381  lea     rdx, qword_140010DA8
0x140001388  mov     rax, [rbp+27h+arg_20]
0x14000138c  mov     rcx, r10
0x14000138f  mov     [rbp+27h+var_70], rdx
0x140001393  mov     rdx, r11
0x140001396  mov     [rbp+27h+var_68], r8d
0x14000139a  mov     r8, rbx
0x14000139d  mov     [rbp+27h+var_64], edi
0x1400013a0  mov     r9, [rax]
0x1400013a3  lea     rax, [rbp+27h+var_A0]
0x1400013a7  mov     [rbp+27h+var_80], r9
0x1400013ab  xor     r9d, r9d
0x1400013ae  mov     [rsp+0D0h+var_A8], rax
0x1400013b3  mov     [rsp+0D0h+var_B0], 8
0x1400013bb  mov     [rbp+27h+var_78], 10h
0x1400013c3  call    _tlgWriteTransfer_EventWriteTransfer
0x1400013c8  mov     rcx, [rbp+27h+var_20]
0x1400013cc  xor     rcx, rsp; StackCookie
0x1400013cf  call    __security_check_cookie
0x1400013d4  add     rsp, 0C0h
0x1400013db  pop     rdi
0x1400013dc  pop     rbx
0x1400013dd  pop     rbp
0x1400013de  retn
```
