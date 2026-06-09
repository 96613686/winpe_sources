# GetSIDKeyFileNameFilter(ulong,int,ushort const *,ushort * *)

- ea: `0x18000bd0c`
- end: `0x18000be64`
- name: `?GetSIDKeyFileNameFilter@@YAJKHPEBGPEAPEAG@Z`
- size: `344`
- prototype: `int(unsigned int, int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000aef0`

## callees

- `0x180001630`
- `0x180001f34`
- `0x18000bd0c`
- `0x180010920`
- `0x18001a450`
- `0x18001a6ac`

## string_xrefs

- `0x18000bda2`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall GetSIDKeyFileNameFilter(unsigned int a1, int a2, const unsigned __int16 *a3, unsigned __int16 **a4)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  size_t v9; // rbx
  size_t v10; // rbp
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  unsigned int v13; // esi
  unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  unsigned __int16 *v16; // rbx
  _WORD Src[24]; // [rsp+20h] [rbp-78h] BYREF

  o__ui64tow_s_0(a1, Src, 21);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  v9 = v8;
  do
    ++v7;
  while ( Src[v7] );
  v10 = v7;
  v11 = (unsigned __int16 *)SIDKeyProvAlloc(v9 * 2 + 2 * v7 + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 30);
  v12 = v11;
  if ( v11 )
  {
    v13 = 0;
    memcpy_0(v11, a3, v9 * 2);
    v14 = &v12[v9 + 1];
    v12[v9] = asc_18001CD7C[0];
    if ( a2 )
    {
      *(_OWORD *)v14 = *(_OWORD *)L"PublicKey\\";
      *((_DWORD *)v14 + 4) = *(_DWORD *)L"y\\";
      v15 = 10;
    }
    else
    {
      v15 = 11;
      *(_OWORD *)v14 = *(_OWORD *)L"PrivateKey\\";
      *(_QWORD *)(v14 + 7) = *(_QWORD *)L"Key\\";
    }
    v16 = &v14[v15];
    memcpy_0(&v14[v15], Src, v10 * 2);
    *(_DWORD *)&v16[v10] = 2752557;
    *a4 = v12;
  }
  else
  {
    v13 = -2147024882;
    SidKeyDebugTraceError(
      0x8007000E,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0x21Eu);
  }
  return v13;
}

```

## disassembly

```asm
0x18000bd0c  mov     [rsp+arg_8], rbx
0x18000bd11  push    rbp
0x18000bd12  push    rsi
0x18000bd13  push    rdi
0x18000bd14  push    r12
0x18000bd16  push    r13
0x18000bd18  push    r14
0x18000bd1a  push    r15
0x18000bd1c  sub     rsp, 60h
0x18000bd20  mov     rax, cs:__security_cookie
0x18000bd27  xor     rax, rsp
0x18000bd2a  mov     [rsp+98h+var_48], rax
0x18000bd2f  mov     r12, r9
0x18000bd32  mov     ecx, ecx
0x18000bd34  mov     r9d, 0Ah
0x18000bd3a  mov     r14, r8
0x18000bd3d  mov     r15d, edx
0x18000bd40  lea     rdx, [rsp+98h+Src]
0x18000bd45  lea     r8d, [r9+0Bh]
0x18000bd49  call    _o__ui64tow_s_0
0x18000bd4e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000bd52  mov     rax, rcx
0x18000bd55  xor     r13d, r13d
0x18000bd58  inc     rax
0x18000bd5b  cmp     [r14+rax*2], r13w
0x18000bd60  jnz     short loc_18000BD58
0x18000bd62  lea     rbx, [rax+rax]
0x18000bd66  lea     rax, [rsp+98h+Src]
0x18000bd6b  inc     rcx
0x18000bd6e  cmp     [rax+rcx*2], r13w
0x18000bd73  jnz     short loc_18000BD6B
0x18000bd75  lea     rbp, [rcx+rcx]
0x18000bd79  mov     eax, r15d
0x18000bd7c  neg     eax
0x18000bd7e  sbb     rcx, rcx
0x18000bd81  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000bd85  add     rcx, 1Eh
0x18000bd89  add     rcx, rbp
0x18000bd8c  add     rcx, rbx; unsigned __int64
0x18000bd8f  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000bd94  mov     rdi, rax
0x18000bd97  test    rax, rax
0x18000bd9a  jnz     short loc_18000BDC1
0x18000bd9c  mov     r9d, 21Eh; unsigned int
0x18000bda2  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000bda9  lea     rdx, aHr; "hr"
0x18000bdb0  mov     ecx, 8007000Eh; unsigned int
0x18000bdb5  mov     esi, 8007000Eh
0x18000bdba  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000bdbf  jmp     short loc_18000BE3D
0x18000bdc1  mov     r8, rbx; Size
0x18000bdc4  mov     rdx, r14; Src
0x18000bdc7  mov     rcx, rdi; void *
0x18000bdca  mov     esi, r13d
0x18000bdcd  call    memcpy_0
0x18000bdd2  mov     eax, dword ptr cs:asc_18001CD7C; "\\"
0x18000bdd8  lea     rcx, [rdi+2]
0x18000bddc  add     rcx, rbx
0x18000bddf  mov     [rbx+rdi], ax
0x18000bde3  test    r15d, r15d
0x18000bde6  jz      short loc_18000BE02
0x18000bde8  movups  xmm0, xmmword ptr cs:aPublickey; "PublicKey\\"
0x18000bdef  movups  xmmword ptr [rcx], xmm0
0x18000bdf2  mov     eax, dword ptr cs:aPublickey+10h; "y\\"
0x18000bdf8  mov     [rcx+10h], eax
0x18000bdfb  mov     eax, 14h
0x18000be00  jmp     short loc_18000BE1E
0x18000be02  movups  xmm0, xmmword ptr cs:aPrivatekey; "PrivateKey\\"
0x18000be09  mov     eax, 16h
0x18000be0e  movups  xmmword ptr [rcx], xmm0
0x18000be11  movsd   xmm1, qword ptr cs:aPrivatekey+0Eh; "Key\\"
0x18000be19  movsd   qword ptr [rcx+0Eh], xmm1
0x18000be1e  lea     rbx, [rcx+rax]
0x18000be22  mov     r8, rbp; Size
0x18000be25  mov     rcx, rbx; void *
0x18000be28  lea     rdx, [rsp+98h+Src]; Src
0x18000be2d  call    memcpy_0
0x18000be32  mov     dword ptr [rbx+rbp], 2A002Dh
0x18000be39  mov     [r12], rdi
0x18000be3d  mov     eax, esi
0x18000be3f  mov     rcx, [rsp+98h+var_48]
0x18000be44  xor     rcx, rsp; StackCookie
0x18000be47  call    __security_check_cookie
0x18000be4c  mov     rbx, [rsp+98h+arg_8]
0x18000be54  add     rsp, 60h
0x18000be58  pop     r15
0x18000be5a  pop     r14
0x18000be5c  pop     r13
0x18000be5e  pop     r12
0x18000be60  pop     rdi
0x18000be61  pop     rsi
0x18000be62  pop     rbp
0x18000be63  retn
```
