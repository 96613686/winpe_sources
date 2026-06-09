# Speller::CVerifyProcessor::CaseCompare(Speller::CWord &,Speller::CLexEntry &,unsigned __int64)

- ea: `0x18003f198`
- end: `0x18003f347`
- name: `?CaseCompare@CVerifyProcessor@Speller@@AEAA_NAEAVCWord@2@AEAVCLexEntry@2@_K@Z`
- size: `431`
- prototype: `bool(Speller::CVerifyProcessor *__hidden this, struct Speller::CWord *, struct Speller::CLexEntry *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010780`

## callees

- `0x180007878`
- `0x18003a350`
- `0x18003f198`
- `0x180054b80`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f223`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f2b9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f223`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f2b9`

## pseudocode

```c
bool __fastcall Speller::CVerifyProcessor::CaseCompare(
        Speller::CVerifyProcessor *this,
        struct Speller::CWord *a2,
        struct Speller::CLexEntry *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdi
  const WCHAR *v8; // rbp
  _QWORD *v9; // r14
  _DWORD *v10; // r15
  const WCHAR *lpString2; // rsi
  int cchCount2; // eax
  int v13; // edx
  __int64 v14; // r8
  int v15; // eax
  __int16 v16; // ax
  int v17; // ecx

  v6 = a4;
  v8 = (const WCHAR *)((char *)a2 + 2 * a4);
  v9 = (_QWORD *)((char *)a3 + 8);
  v10 = (_DWORD *)((char *)a2 + 176);
  lpString2 = (const WCHAR *)(CArray<unsigned short,CArrayAllocator_malloc>::ElementAt(a3, 0) + 2 * a4);
  if ( *((_DWORD *)a2 + 55) == 6 )
  {
    cchCount2 = SSIZETToIntRtlAsserted(*v9 - v6 - 1);
    if ( CompareStringW(*(_WORD *)(*((_QWORD *)this + 1) + 16LL) & 0x3FF, 1u, v8 + 24, *v10 - v6, lpString2, cchCount2) == 2 )
      return 1;
  }
  v13 = *(_DWORD *)(*((_QWORD *)this + 1) + 588LL);
  if ( v13 > 0 && Speller::CLexEntry::IsInvariableCase(a3, v13) )
  {
    if ( *(_QWORD *)v10 == *v9 - 1LL )
    {
      while ( v6 < *(_QWORD *)v10 )
      {
        if ( *((_WORD *)a2 + v6 + 24) != *(_WORD *)(v14 + 2 * v6) )
          return 0;
        ++v6;
      }
      return 1;
    }
    return 0;
  }
  v15 = SSIZETToIntRtlAsserted(*v9 - 1LL);
  if ( CompareStringW(
         *(_WORD *)(*((_QWORD *)this + 1) + 16LL) & 0x3FF,
         0,
         v8 + 25,
         ~(_DWORD)v6 + *v10,
         lpString2 + 1,
         v15 + ~(_DWORD)v6) != 2 )
    return 0;
  if ( v8[24] == *lpString2 )
    return 1;
  if ( *((_DWORD *)a2 + 55) == 2 )
  {
    if ( *(_WORD *)(*((_QWORD *)this + 1) + 1584LL) != 31 || (v16 = 305, v8[24] != 73) && v8[24] != 305 )
    {
      v17 = *((unsigned __int8 *)&s_rgDiacriticSegmentMap + ((unsigned __int64)v8[24] >> 8));
      if ( v17 == 255 )
        return 0;
      v16 = *((_WORD *)&(&s_LowercaseMapTable)[64 * v17] + (unsigned int)*((unsigned __int8 *)v8 + 48));
    }
    return v16 == *lpString2;
  }
  return 0;
}

```

## disassembly

```asm
0x18003f198  push    rbx
0x18003f19a  push    rbp
0x18003f19b  push    rsi
0x18003f19c  push    rdi
0x18003f19d  push    r12
0x18003f19f  push    r13
0x18003f1a1  push    r14
0x18003f1a3  push    r15
0x18003f1a5  sub     rsp, 38h
0x18003f1a9  mov     r13, rdx
0x18003f1ac  mov     rbx, rcx
0x18003f1af  xor     edx, edx
0x18003f1b1  mov     rcx, r8
0x18003f1b4  mov     rdi, r9
0x18003f1b7  mov     r12, r8
0x18003f1ba  call    ?ElementAt@?$CArray@GVCArrayAllocator_malloc@@@@QEBAAEAG_J@Z; CArray<ushort,CArrayAllocator_malloc>::ElementAt(__int64)
0x18003f1bf  lea     rbp, ds:0[rdi*2]
0x18003f1c7  mov     [rsp+78h+arg_8], rax
0x18003f1cf  add     rbp, r13
0x18003f1d2  lea     r14, [r12+8]
0x18003f1d7  cmp     dword ptr [r13+0DCh], 6
0x18003f1df  lea     r15, [r13+0B0h]
0x18003f1e6  mov     r8, rax
0x18003f1e9  lea     rsi, [rax+rdi*2]
0x18003f1ed  jnz     short loc_18003F23A
0x18003f1ef  mov     rcx, [r14]
0x18003f1f2  sub     rcx, rdi
0x18003f1f5  dec     rcx; unsigned __int64
0x18003f1f8  call    ?SSIZETToIntRtlAsserted@@YAH_J@Z; SSIZETToIntRtlAsserted(__int64)
0x18003f1fd  mov     rcx, [rbx+8]
0x18003f201  lea     r8, [rbp+30h]; lpString1
0x18003f205  mov     r9d, [r15]
0x18003f208  mov     edx, 1; dwCmpFlags
0x18003f20d  mov     [rsp+78h+cchCount2], eax; cchCount2
0x18003f211  sub     r9d, edi; cchCount1
0x18003f214  mov     [rsp+78h+lpString2], rsi; lpString2
0x18003f219  movzx   ecx, word ptr [rcx+10h]
0x18003f21d  and     ecx, 3FFh; Locale
0x18003f223  call    cs:__imp_CompareStringW
0x18003f229  cmp     eax, 2
0x18003f22c  jz      loc_18003F330
0x18003f232  mov     r8, [rsp+78h+arg_8]
0x18003f23a  mov     rax, [rbx+8]
0x18003f23e  mov     edx, [rax+24Ch]; int
0x18003f244  test    edx, edx
0x18003f246  jle     short loc_18003F282
0x18003f248  mov     rcx, r12; this
0x18003f24b  call    ?IsInvariableCase@CLexEntry@Speller@@QEBA_NH@Z; Speller::CLexEntry::IsInvariableCase(int)
0x18003f250  test    al, al
0x18003f252  jz      short loc_18003F282
0x18003f254  mov     rax, [r14]
0x18003f257  dec     rax
0x18003f25a  cmp     [r15], rax
0x18003f25d  jnz     loc_18003F334
0x18003f263  cmp     rdi, [r15]
0x18003f266  jnb     loc_18003F330
0x18003f26c  movzx   eax, word ptr [r8+rdi*2]
0x18003f271  cmp     [r13+rdi*2+30h], ax
0x18003f277  jnz     loc_18003F334
0x18003f27d  inc     rdi
0x18003f280  jmp     short loc_18003F263
0x18003f282  mov     rcx, [r14]
0x18003f285  not     edi
0x18003f287  dec     rcx; unsigned __int64
0x18003f28a  call    ?SSIZETToIntRtlAsserted@@YAH_J@Z; SSIZETToIntRtlAsserted(__int64)
0x18003f28f  mov     r9d, [r15]
0x18003f292  lea     r10, [rsi+2]
0x18003f296  add     r9d, edi; cchCount1
0x18003f299  lea     r8, [rbp+32h]; lpString1
0x18003f29d  lea     edx, [rax+rdi]
0x18003f2a0  mov     rax, [rbx+8]
0x18003f2a4  mov     [rsp+78h+cchCount2], edx; cchCount2
0x18003f2a8  xor     edx, edx; dwCmpFlags
0x18003f2aa  mov     [rsp+78h+lpString2], r10; lpString2
0x18003f2af  movzx   ecx, word ptr [rax+10h]
0x18003f2b3  and     ecx, 3FFh; Locale
0x18003f2b9  call    cs:__imp_CompareStringW
0x18003f2bf  cmp     eax, 2
0x18003f2c2  jnz     short loc_18003F334
0x18003f2c4  movzx   edx, word ptr [rsi]
0x18003f2c7  cmp     [rbp+30h], dx
0x18003f2cb  jz      short loc_18003F330
0x18003f2cd  cmp     [r13+0DCh], eax
0x18003f2d4  jnz     short loc_18003F334
0x18003f2d6  mov     rax, [rbx+8]
0x18003f2da  cmp     word ptr [rax+630h], 1Fh
0x18003f2e2  jnz     short loc_18003F2F6
0x18003f2e4  cmp     word ptr [rbp+30h], 49h ; 'I'
0x18003f2e9  mov     eax, 131h
0x18003f2ee  jz      short loc_18003F328
0x18003f2f0  cmp     [rbp+30h], ax
0x18003f2f4  jz      short loc_18003F328
0x18003f2f6  movzx   eax, word ptr [rbp+30h]
0x18003f2fa  lea     r8, __ImageBase
0x18003f301  shr     rax, 8
0x18003f305  movzx   ecx, byte ptr [rax+r8+0EC740h]
0x18003f30e  cmp     ecx, 0FFh
0x18003f314  jz      short loc_18003F334
0x18003f316  movzx   eax, byte ptr [rbp+30h]
0x18003f31a  shl     ecx, 8
0x18003f31d  add     eax, ecx
0x18003f31f  movzx   eax, ds:rva ?s_LowercaseMapTable@@3QBGB[r8+rax*2]; ushort const near * const s_LowercaseMapTable ...
0x18003f328  cmp     ax, dx
0x18003f32b  setz    al
0x18003f32e  jmp     short loc_18003F336
0x18003f330  mov     al, 1
0x18003f332  jmp     short loc_18003F336
0x18003f334  xor     al, al
0x18003f336  add     rsp, 38h
0x18003f33a  pop     r15
0x18003f33c  pop     r14
0x18003f33e  pop     r13
0x18003f340  pop     r12
0x18003f342  pop     rdi
0x18003f343  pop     rsi
0x18003f344  pop     rbp
0x18003f345  pop     rbx
0x18003f346  retn
```
