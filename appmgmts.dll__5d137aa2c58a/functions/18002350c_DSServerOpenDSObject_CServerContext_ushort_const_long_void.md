# DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)

- ea: `0x18002350c`
- end: `0x180023663`
- name: `?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z`
- size: `343`
- prototype: `__int64 __fastcall(const unsigned __int16 **, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `21`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c258`
- `0x18001e8ac`
- `0x18001eec0`
- `0x18001f0b0`
- `0x18001f570`
- `0x18001f800`
- `0x18001fa10`
- `0x1800205f4`
- `0x180021dd0`
- `0x1800223b4`
- `0x180022610`
- `0x1800226f0`
- `0x180022870`
- `0x180022940`
- `0x180022e00`
- `0x180023050`
- `0x180023330`
- `0x18002371c`
- `0x180023bc0`
- `0x180023cdc`
- `0x180028190`

## callees

- `0x180002aa0`
- `0x18000cc10`
- `0x18002350c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002364a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002364a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800235d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800235d2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023566`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023566`
- `adsldpc!ADSIOpenDSObject` at `0x18002363a`
- `adsldpc!ADSIOpenDSObject` at `0x18002363a`

## pseudocode

```c
__int64 __fastcall DSServerOpenDSObject(
        const unsigned __int16 **a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        void **a4)
{
  const unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // rdi
  const unsigned __int16 *v8; // rbp
  const unsigned __int16 *v9; // r15
  int v10; // eax
  const unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  SIZE_T v16; // rax
  unsigned __int16 *v17; // rax
  unsigned int v19; // ebx

  v6 = a2;
  v7 = 0;
  if ( a1 )
  {
    v8 = *a1;
    if ( *a1 )
    {
      v9 = a2 + 7;
      v10 = CompareStringW(0x7Fu, 1u, a2, 7, L"LDAP://", 7);
      v11 = v9;
      if ( v10 != 2 )
        v11 = v6;
      if ( !v11 )
        goto LABEL_10;
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      if ( v12 <= 2 || v11[2] == 61 )
      {
LABEL_10:
        v13 = -1;
        do
          ++v13;
        while ( v6[v13] );
        v14 = -1;
        do
          ++v14;
        while ( v8[v14] );
        v15 = (unsigned int)(v14 + v13 + 2);
        v16 = 2 * v15;
        if ( !is_mul_ok(v15, 2u) )
          v16 = -1;
        v17 = (unsigned __int16 *)LocalAlloc(0, v16);
        v7 = v17;
        if ( !v17 )
          return 2147942414LL;
        StringCchCopyW(v17, v15, L"LDAP://");
        StringCchCatW(v7, v15, v8);
        StringCchCatW(v7, v15, L"/");
        StringCchCatW(v7, v15, v9);
        v6 = v7;
      }
      a3 |= 0x200u;
    }
  }
  v19 = ADSIOpenDSObject(v6, 0, 0, a3, a4);
  if ( v7 )
    LocalFree(v7);
  return v19;
}

```

## disassembly

```asm
0x18002350c  push    rbx
0x18002350e  push    rbp
0x18002350f  push    rsi
0x180023510  push    rdi
0x180023511  push    r12
0x180023513  push    r13
0x180023515  push    r14
0x180023517  push    r15
0x180023519  sub     rsp, 38h
0x18002351d  xor     r12d, r12d
0x180023520  mov     r14, r9
0x180023523  mov     esi, r8d
0x180023526  mov     rbx, rdx
0x180023529  mov     edi, r12d
0x18002352c  test    rcx, rcx
0x18002352f  jz      loc_18002362A
0x180023535  mov     rbp, [rcx]
0x180023538  test    rbp, rbp
0x18002353b  jz      loc_18002362A
0x180023541  lea     r15, [rdx+0Eh]
0x180023545  mov     r8, rdx; lpString1
0x180023548  lea     edx, [r12+1]; dwCmpFlags
0x18002354d  lea     r9d, [r12+7]; cchCount1
0x180023552  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180023557  lea     r13, aLdap; "LDAP://"
0x18002355e  lea     ecx, [rdx+7Eh]; Locale
0x180023561  mov     [rsp+78h+lpString2], r13; lpString2
0x180023566  call    cs:__imp_CompareStringW
0x18002356c  cmp     eax, 2
0x18002356f  mov     rcx, r15
0x180023572  cmovnz  rcx, rbx
0x180023576  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002357a  test    rcx, rcx
0x18002357d  jz      short loc_18002359D
0x18002357f  mov     rax, r8
0x180023582  inc     rax
0x180023585  cmp     [rcx+rax*2], r12w
0x18002358a  jnz     short loc_180023582
0x18002358c  cmp     rax, 2
0x180023590  jbe     short loc_18002359D
0x180023592  cmp     word ptr [rcx+4], 3Dh ; '='
0x180023597  jnz     loc_180023626
0x18002359d  mov     rdx, r8
0x1800235a0  inc     rdx
0x1800235a3  cmp     [rbx+rdx*2], r12w
0x1800235a8  jnz     short loc_1800235A0
0x1800235aa  mov     rcx, r8
0x1800235ad  inc     rcx
0x1800235b0  cmp     [rbp+rcx*2+0], r12w
0x1800235b6  jnz     short loc_1800235AD
0x1800235b8  lea     rbx, [rdx+2]
0x1800235bc  mov     eax, 2
0x1800235c1  add     rbx, rcx
0x1800235c4  mov     ebx, ebx
0x1800235c6  mul     rbx
0x1800235c9  cmovb   rax, r8
0x1800235cd  xor     ecx, ecx; uFlags
0x1800235cf  mov     rdx, rax; uBytes
0x1800235d2  call    cs:__imp_LocalAlloc
0x1800235d8  mov     rdi, rax
0x1800235db  test    rax, rax
0x1800235de  jnz     short loc_1800235E7
0x1800235e0  mov     eax, 8007000Eh
0x1800235e5  jmp     short loc_180023652
0x1800235e7  mov     r8, r13; unsigned __int16 *
0x1800235ea  mov     rdx, rbx; unsigned __int64
0x1800235ed  mov     rcx, rdi; unsigned __int16 *
0x1800235f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800235f5  mov     r8, rbp; unsigned __int16 *
0x1800235f8  mov     rdx, rbx; unsigned __int64
0x1800235fb  mov     rcx, rdi; unsigned __int16 *
0x1800235fe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023603  lea     r8, asc_18002EE34; "/"
0x18002360a  mov     rdx, rbx; unsigned __int64
0x18002360d  mov     rcx, rdi; unsigned __int16 *
0x180023610  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023615  mov     r8, r15; unsigned __int16 *
0x180023618  mov     rdx, rbx; unsigned __int64
0x18002361b  mov     rcx, rdi; unsigned __int16 *
0x18002361e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023623  mov     rbx, rdi
0x180023626  bts     esi, 9
0x18002362a  mov     r9d, esi
0x18002362d  mov     [rsp+78h+lpString2], r14
0x180023632  xor     r8d, r8d
0x180023635  xor     edx, edx
0x180023637  mov     rcx, rbx
0x18002363a  call    cs:__imp_ADSIOpenDSObject
0x180023640  mov     ebx, eax
0x180023642  test    rdi, rdi
0x180023645  jz      short loc_180023650
0x180023647  mov     rcx, rdi; hMem
0x18002364a  call    cs:__imp_LocalFree
0x180023650  mov     eax, ebx
0x180023652  add     rsp, 38h
0x180023656  pop     r15
0x180023658  pop     r14
0x18002365a  pop     r13
0x18002365c  pop     r12
0x18002365e  pop     rdi
0x18002365f  pop     rsi
0x180023660  pop     rbp
0x180023661  pop     rbx
0x180023662  retn
```
