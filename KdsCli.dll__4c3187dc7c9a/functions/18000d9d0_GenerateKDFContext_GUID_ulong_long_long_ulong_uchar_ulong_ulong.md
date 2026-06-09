# GenerateKDFContext(_GUID,ulong,long,long,ulong,uchar * *,ulong *,ulong *)

- ea: `0x18000d9d0`
- end: `0x18000da82`
- name: `?GenerateKDFContext@@YAJU_GUID@@KJJKPEAPEAEPEAK2@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned int, int, int, unsigned int, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004624`
- `0x180008570`
- `0x180008850`
- `0x180018298`

## callees

- `0x18000d9d0`
- `0x180010920`
- `0x18001a450`

## string_xrefs

- `0x18000d9fb`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeykdf.cxx`

## pseudocode

```c
__int64 __fastcall GenerateKDFContext(
        struct _GUID *a1,
        int a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned __int8 **a6,
        unsigned int *a7,
        unsigned int *a8)
{
  unsigned __int8 *v12; // rax
  unsigned int v13; // ebx
  unsigned int v14; // edx

  v12 = (unsigned __int8 *)SIDKeyProvAlloc(0x1Cu);
  if ( v12 )
  {
    v13 = 0;
    *(struct _GUID *)v12 = *a1;
    *((_DWORD *)v12 + 4) = a2;
    v14 = 16;
    if ( a5 && a8 )
      v14 = 20;
    *((_DWORD *)v12 + 5) = a3;
    if ( a5 >= 2 && a8 )
      v14 += 4;
    *((_DWORD *)v12 + 6) = a4;
    *a6 = v12;
    *a7 = 28;
    if ( a8 )
      *a8 = v14;
  }
  else
  {
    v13 = -2147024882;
    SidKeyDebugTraceError(14, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeykdf.cxx", 189);
  }
  return v13;
}

```

## disassembly

```asm
0x18000d9d0  push    rbx
0x18000d9d2  push    rbp
0x18000d9d3  push    rsi
0x18000d9d4  push    rdi
0x18000d9d5  push    r14
0x18000d9d7  sub     rsp, 20h
0x18000d9db  mov     rsi, rcx
0x18000d9de  mov     r14d, r9d
0x18000d9e1  mov     ecx, 1Ch; unsigned __int64
0x18000d9e6  mov     ebp, r8d
0x18000d9e9  mov     edi, edx
0x18000d9eb  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000d9f0  test    rax, rax
0x18000d9f3  jnz     short loc_18000DA1A
0x18000d9f5  mov     r9d, 0BDh; unsigned int
0x18000d9fb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000da02  lea     rdx, aHr; "hr"
0x18000da09  mov     ecx, 8007000Eh; unsigned int
0x18000da0e  mov     ebx, 8007000Eh
0x18000da13  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000da18  jmp     short loc_18000DA75
0x18000da1a  movups  xmm0, xmmword ptr [rsi]
0x18000da1d  mov     r8, [rsp+48h+arg_38]
0x18000da25  xor     ebx, ebx
0x18000da27  cmp     [rsp+48h+arg_20], 1
0x18000da2c  movdqu  xmmword ptr [rax], xmm0
0x18000da30  mov     [rax+10h], edi
0x18000da33  lea     edx, [rbx+10h]
0x18000da36  jb      short loc_18000DA41
0x18000da38  test    r8, r8
0x18000da3b  lea     ecx, [rbx+14h]
0x18000da3e  cmovnz  edx, ecx
0x18000da41  cmp     [rsp+48h+arg_20], 2
0x18000da46  mov     [rax+14h], ebp
0x18000da49  jb      short loc_18000DA53
0x18000da4b  test    r8, r8
0x18000da4e  jz      short loc_18000DA53
0x18000da50  add     edx, 4
0x18000da53  mov     rcx, [rsp+48h+arg_28]
0x18000da58  mov     [rax+18h], r14d
0x18000da5c  mov     [rcx], rax
0x18000da5f  mov     rcx, [rsp+48h+arg_30]
0x18000da67  mov     dword ptr [rcx], 1Ch
0x18000da6d  test    r8, r8
0x18000da70  jz      short loc_18000DA75
0x18000da72  mov     [r8], edx
0x18000da75  mov     eax, ebx
0x18000da77  add     rsp, 20h
0x18000da7b  pop     r14
0x18000da7d  pop     rdi
0x18000da7e  pop     rsi
0x18000da7f  pop     rbp
0x18000da80  pop     rbx
0x18000da81  retn
```
