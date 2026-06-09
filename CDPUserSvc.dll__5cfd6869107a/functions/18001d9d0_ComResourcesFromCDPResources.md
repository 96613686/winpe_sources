# ComResourcesFromCDPResources

- ea: `0x18001d9d0`
- end: `0x18001db6e`
- name: `ComResourcesFromCDPResources`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004ed30`

## callees

- `0x18001d9d0`
- `0x18001e798`
- `0x18002d1c8`
- `0x18004e8ec`
- `0x18004ec9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001da43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001da43`

## string_xrefs

- `0x18001d9fe`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18001dac2`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18001db30`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ComResourcesFromCDPResources(__int64 a1, unsigned int a2, LPVOID *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  SIZE_T v7; // rbx
  void *v8; // rax
  void *v9; // rcx
  unsigned __int16 i; // bx
  int v11; // eax
  unsigned int v12; // esi
  void *v13; // rbx
  unsigned __int16 v14; // di
  void *v16; // rcx
  int v17; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  LPVOID pv; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v20; // [rsp+68h] [rbp+28h]

  v20 = a2;
  if ( !a1 )
  {
    v5 = -2147467261;
    v6 = 275;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)v5,
      v17);
    return v5;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 276;
    goto LABEL_3;
  }
  *a3 = 0;
  pv = 0;
  v7 = 40LL * a2;
  v8 = CoTaskMemAlloc(v7);
  v9 = pv;
  pv = v8;
  if ( v9 )
  {
    CoTaskMemFree(v9);
    v8 = pv;
  }
  if ( !v8 )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x8007000ELL,
      v17);
    v16 = pv;
    pv = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    return v5;
  }
  memset_0(v8, 0, v7);
  for ( i = 0; ; ++i )
  {
    if ( i >= v20 )
    {
      *a3 = pv;
      return 0;
    }
    v11 = ComResourceFromCDPResource(*(_QWORD *)(a1 + 8LL * i), (char *)pv + 40 * i);
    v12 = v11;
    if ( v11 < 0 )
      break;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12D,
    (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
    (const char *)(unsigned int)v11,
    (int)&pv);
  v13 = pv;
  if ( pv )
  {
    v14 = 0;
    if ( v20 )
    {
      do
        FreeCDPComResource((__int64)v13 + 40 * v14++);
      while ( v14 < v20 );
      v13 = pv;
    }
  }
  pv = 0;
  if ( v13 )
    CoTaskMemFree(v13);
  return v12;
}

```

## disassembly

```asm
0x18001d9d0  mov     [rsp-18h+arg_10], rbx
0x18001d9d5  mov     [rsp-18h+arg_18], rsi
0x18001d9da  mov     [rsp-18h+arg_8], edx
0x18001d9de  push    rbp
0x18001d9df  push    rdi
0x18001d9e0  push    r14
0x18001d9e2  mov     rbp, rsp
0x18001d9e5  sub     rsp, 40h
0x18001d9e9  mov     rdi, r8
0x18001d9ec  mov     r14, rcx
0x18001d9ef  test    rcx, rcx
0x18001d9f2  jnz     short loc_18001DA16
0x18001d9f4  mov     ebx, 80004003h
0x18001d9f9  mov     edx, 113h; void *
0x18001d9fe  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18001da05  mov     r9d, ebx; char *
0x18001da08  mov     rcx, [rbp+18h]; this
0x18001da0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da11  jmp     loc_18001DB59
0x18001da16  test    rdi, rdi
0x18001da19  jnz     short loc_18001DA27
0x18001da1b  mov     ebx, 80070057h
0x18001da20  mov     edx, 114h
0x18001da25  jmp     short loc_18001D9FE
0x18001da27  mov     qword ptr [r8], 0
0x18001da2e  mov     [rbp+pv], 0
0x18001da36  mov     eax, edx
0x18001da38  lea     rbx, [rax+rax*4]
0x18001da3c  shl     rbx, 3
0x18001da40  mov     rcx, rbx; cb
0x18001da43  call    cs:__imp_CoTaskMemAlloc
0x18001da49  mov     rcx, [rbp+pv]; pv
0x18001da4d  mov     [rbp+pv], rax
0x18001da51  test    rcx, rcx
0x18001da54  jz      short loc_18001DA60
0x18001da56  call    cs:__imp_CoTaskMemFree
0x18001da5c  mov     rax, [rbp+pv]
0x18001da60  test    rax, rax
0x18001da63  jz      loc_18001DB24
0x18001da69  mov     r8, rbx; Size
0x18001da6c  xor     edx, edx; Val
0x18001da6e  mov     rcx, rax; void *
0x18001da71  call    memset_0
0x18001da76  lea     rax, [rbp+pv]
0x18001da7a  mov     [rbp+var_20], rax
0x18001da7e  lea     rax, [rbp+arg_8]
0x18001da82  mov     [rbp+var_18], rax
0x18001da86  mov     [rbp+var_10], 1
0x18001da8a  xor     ebx, ebx
0x18001da8c  movzx   eax, bx
0x18001da8f  cmp     eax, [rbp+arg_8]
0x18001da92  mov     rax, [rbp+pv]
0x18001da96  jnb     loc_18001DB1D
0x18001da9c  movzx   ecx, bx
0x18001da9f  lea     rdx, [rcx+rcx*4]
0x18001daa3  lea     rdx, [rax+rdx*8]
0x18001daa7  mov     rcx, [r14+rcx*8]
0x18001daab  call    ComResourceFromCDPResource
0x18001dab0  mov     esi, eax
0x18001dab2  test    eax, eax
0x18001dab4  js      short loc_18001DABB
0x18001dab6  inc     bx
0x18001dab9  jmp     short loc_18001DA8C
0x18001dabb  mov     rcx, [rbp+18h]; this
0x18001dabf  mov     r9d, esi; char *
0x18001dac2  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18001dac9  mov     edx, 12Dh; void *
0x18001dace  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dad3  nop
0x18001dad4  mov     rbx, [rbp+pv]
0x18001dad8  test    rbx, rbx
0x18001dadb  jz      short loc_18001DB03
0x18001dadd  xor     edi, edi
0x18001dadf  cmp     [rbp+arg_8], edi
0x18001dae2  jbe     short loc_18001DB03
0x18001dae4  movzx   eax, di
0x18001dae7  lea     rcx, [rax+rax*4]
0x18001daeb  lea     rcx, [rbx+rcx*8]
0x18001daef  call    FreeCDPComResource
0x18001daf4  inc     di
0x18001daf7  movzx   eax, di
0x18001dafa  cmp     eax, [rbp+arg_8]
0x18001dafd  jb      short loc_18001DAE4
0x18001daff  mov     rbx, [rbp+pv]
0x18001db03  mov     [rbp+pv], 0
0x18001db0b  test    rbx, rbx
0x18001db0e  jz      short loc_18001DB19
0x18001db10  mov     rcx, rbx; pv
0x18001db13  call    cs:__imp_CoTaskMemFree
0x18001db19  mov     eax, esi
0x18001db1b  jmp     short loc_18001DB5B
0x18001db1d  mov     [rdi], rax
0x18001db20  xor     eax, eax
0x18001db22  jmp     short loc_18001DB5B
0x18001db24  mov     rcx, [rbp+18h]; this
0x18001db28  mov     ebx, 8007000Eh
0x18001db2d  mov     r9d, ebx; char *
0x18001db30  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18001db37  mov     edx, 11Ch; void *
0x18001db3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db41  nop
0x18001db42  mov     rcx, [rbp+pv]; pv
0x18001db46  mov     [rbp+pv], 0
0x18001db4e  test    rcx, rcx
0x18001db51  jz      short loc_18001DB59
0x18001db53  call    cs:__imp_CoTaskMemFree
0x18001db59  mov     eax, ebx
0x18001db5b  mov     rbx, [rsp+40h+arg_10]
0x18001db60  mov     rsi, [rsp+40h+arg_18]
0x18001db65  add     rsp, 40h
0x18001db69  pop     r14
0x18001db6b  pop     rdi
0x18001db6c  pop     rbp
0x18001db6d  retn
```
