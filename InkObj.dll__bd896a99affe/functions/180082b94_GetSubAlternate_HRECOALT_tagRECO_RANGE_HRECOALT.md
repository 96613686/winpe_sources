# GetSubAlternate(HRECOALT__ *,tagRECO_RANGE *,HRECOALT__ * *)

- ea: `0x180082b94`
- end: `0x180082cd4`
- name: `?GetSubAlternate@@YAJPEAUHRECOALT__@@PEAUtagRECO_RANGE@@PEAPEAU1@@Z`
- size: `320`
- prototype: `__int64 __fastcall(HRECOALT, struct tagRECO_RANGE *, HRECOALT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d2c20`

## callees

- `0x180044ac6`
- `0x180080a30`
- `0x180082b94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082bf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082c39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082bf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082c39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082c6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082c6d`

## pseudocode

```c
__int64 __fastcall GetSubAlternate(struct tagWispAlternate *a1, struct tagRECO_RANGE *a2, HRECOALT *a3)
{
  int LatticeAltRange; // ebp
  HRECOALT v6; // rax
  HRECOALT v7; // rdi
  SIZE_T v9; // rcx
  LPVOID v10; // rax
  LPVOID v11; // rax
  void *v12; // rcx
  __int64 v13; // rbx
  struct tagRECO_RANGE v14; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v15; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  v16 = 0;
  v14 = 0;
  if ( !a1 || !a3 )
    return 2147500035LL;
  LatticeAltRange = GetLatticeAltRange(a2, a1, &v15, &v16, &v14);
  if ( LatticeAltRange >= 0 )
  {
    v6 = (HRECOALT)CoTaskMemAlloc(0x28u);
    v7 = v6;
    if ( !v6 )
      return 2147942414LL;
    *(_OWORD *)v6 = 0;
    *((_OWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 4) = 0;
    *(_QWORD *)v6 = *(_QWORD *)a1;
    v9 = 4LL * (v16 - v15 + 1);
    *((_DWORD *)v6 + 2) = v16 - v15 + 1;
    v10 = CoTaskMemAlloc(v9);
    *((_QWORD *)v7 + 2) = v10;
    if ( !v10 )
    {
LABEL_7:
      CoTaskMemFree(v7);
      return 2147942414LL;
    }
    v11 = CoTaskMemAlloc(4LL * *((unsigned int *)v7 + 2));
    v12 = (void *)*((_QWORD *)v7 + 2);
    *((_QWORD *)v7 + 3) = v11;
    if ( !v11 )
    {
      CoTaskMemFree(v12);
      goto LABEL_7;
    }
    v13 = v15;
    memcpy_0(v12, (const void *)(*((_QWORD *)a1 + 2) + 4LL * v15), 4LL * *((unsigned int *)v7 + 2));
    memcpy_0(*((void **)v7 + 3), (const void *)(*((_QWORD *)a1 + 3) + 4 * v13), 4LL * *((unsigned int *)v7 + 2));
    *((struct tagRECO_RANGE *)v7 + 4) = v14;
    *a3 = v7;
  }
  return (unsigned int)LatticeAltRange;
}

```

## disassembly

```asm
0x180082b94  mov     r11, rsp
0x180082b97  mov     [r11+10h], rbx
0x180082b9b  mov     [r11+18h], rbp
0x180082b9f  push    rsi
0x180082ba0  push    rdi
0x180082ba1  push    r14
0x180082ba3  sub     rsp, 40h
0x180082ba7  xor     ebx, ebx
0x180082ba9  mov     r14, r8
0x180082bac  mov     [rsp+58h+arg_0], ebx
0x180082bb0  mov     rax, rdx
0x180082bb3  mov     [rsp+58h+arg_18], ebx
0x180082bb7  mov     rsi, rcx
0x180082bba  mov     [r11-28h], rbx
0x180082bbe  test    rcx, rcx
0x180082bc1  jz      loc_180082CBC
0x180082bc7  test    r8, r8
0x180082bca  jz      loc_180082CBC
0x180082bd0  lea     rcx, [r11-28h]
0x180082bd4  mov     rdx, rsi; struct tagWispAlternate *
0x180082bd7  mov     [r11-38h], rcx
0x180082bdb  lea     r9, [r11+20h]; unsigned int *
0x180082bdf  mov     rcx, rax; struct tagRECO_RANGE *
0x180082be2  lea     r8, [r11+8]; unsigned int *
0x180082be6  call    ?GetLatticeAltRange@@YAJPEAUtagRECO_RANGE@@PEAUtagWispAlternate@@PEAK20@Z; GetLatticeAltRange(tagRECO_RANGE *,tagWispAlternate *,ulong *,ulong *,tagRECO_RANGE *)
0x180082beb  mov     ebp, eax
0x180082bed  test    eax, eax
0x180082bef  js      loc_180082CB8
0x180082bf5  lea     ecx, [rbx+28h]; cb
0x180082bf8  call    cs:__imp_CoTaskMemAlloc
0x180082bfe  mov     rdi, rax
0x180082c01  test    rax, rax
0x180082c04  jnz     short loc_180082C10
0x180082c06  mov     eax, 8007000Eh
0x180082c0b  jmp     loc_180082CC1
0x180082c10  xor     eax, eax
0x180082c12  xorps   xmm0, xmm0
0x180082c15  movups  xmmword ptr [rdi], xmm0
0x180082c18  movups  xmmword ptr [rdi+10h], xmm0
0x180082c1c  mov     [rdi+20h], rax
0x180082c20  mov     rax, [rsi]
0x180082c23  mov     [rdi], rax
0x180082c26  mov     eax, [rsp+58h+arg_18]
0x180082c2a  sub     eax, [rsp+58h+arg_0]
0x180082c2e  inc     eax
0x180082c30  mov     ecx, eax
0x180082c32  shl     rcx, 2; cb
0x180082c36  mov     [rdi+8], eax
0x180082c39  call    cs:__imp_CoTaskMemAlloc
0x180082c3f  mov     [rdi+10h], rax
0x180082c43  test    rax, rax
0x180082c46  jnz     short loc_180082C53
0x180082c48  mov     rcx, rdi; pv
0x180082c4b  call    cs:__imp_CoTaskMemFree
0x180082c51  jmp     short loc_180082C06
0x180082c53  mov     ecx, [rdi+8]
0x180082c56  shl     rcx, 2; cb
0x180082c5a  call    cs:__imp_CoTaskMemAlloc
0x180082c60  mov     rcx, [rdi+10h]; void *
0x180082c64  mov     [rdi+18h], rax
0x180082c68  test    rax, rax
0x180082c6b  jnz     short loc_180082C75
0x180082c6d  call    cs:__imp_CoTaskMemFree
0x180082c73  jmp     short loc_180082C48
0x180082c75  mov     rax, [rsi+10h]
0x180082c79  mov     r8d, [rdi+8]
0x180082c7d  mov     ebx, [rsp+58h+arg_0]
0x180082c81  shl     r8, 2; Size
0x180082c85  lea     rdx, [rax+rbx*4]; Src
0x180082c89  call    memcpy_0
0x180082c8e  mov     rax, [rsi+18h]
0x180082c92  mov     r8d, [rdi+8]
0x180082c96  mov     rcx, [rdi+18h]; void *
0x180082c9a  shl     r8, 2; Size
0x180082c9e  lea     rdx, [rax+rbx*4]; Src
0x180082ca2  call    memcpy_0
0x180082ca7  mov     eax, [rsp+58h+var_28]
0x180082cab  mov     [rdi+20h], eax
0x180082cae  mov     eax, [rsp+58h+var_24]
0x180082cb2  mov     [rdi+24h], eax
0x180082cb5  mov     [r14], rdi
0x180082cb8  mov     eax, ebp
0x180082cba  jmp     short loc_180082CC1
0x180082cbc  mov     eax, 80004003h
0x180082cc1  mov     rbx, [rsp+58h+arg_8]
0x180082cc6  mov     rbp, [rsp+58h+arg_10]
0x180082ccb  add     rsp, 40h
0x180082ccf  pop     r14
0x180082cd1  pop     rdi
0x180082cd2  pop     rsi
0x180082cd3  retn
```
