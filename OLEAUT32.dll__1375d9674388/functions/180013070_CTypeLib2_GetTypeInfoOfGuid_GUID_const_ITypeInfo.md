# CTypeLib2::GetTypeInfoOfGuid(_GUID const &,ITypeInfo * *)

- ea: `0x180013070`
- end: `0x1800131cc`
- name: `?GetTypeInfoOfGuid@CTypeLib2@@UEAAJAEBU_GUID@@PEAPEAUITypeInfo@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(CTypeLib2 *__hidden this, const struct _GUID *, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180013070`
- `0x180013634`
- `0x18004d900`
- `0x18004ebb0`
- `0x18006df28`

## import_xrefs

- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapConfiguredClsidToReferenceClsid` at `0x1800130c2`
- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapConfiguredClsidToReferenceClsid` at `0x1800130c2`

## pseudocode

```c
__int64 __fastcall CTypeLib2::GetTypeInfoOfGuid(CTypeLib2 *this, __m128 *a2, struct ITypeInfo **a3)
{
  __m128 v6; // xmm1
  __m128 v7; // xmm1
  unsigned int v8; // eax
  unsigned int v9; // edx
  __int64 result; // rax
  unsigned int v11; // r8d
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // ecx
  struct ITypeInfo *v16; // rcx
  struct CTypeInfo2 *v17; // [rsp+20h] [rbp-38h] BYREF
  __m128 v18; // [rsp+28h] [rbp-30h] BYREF

  v17 = 0;
  v18 = 0;
  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  if ( (unsigned __int8)IsSxsOleAut32MapConfiguredClsidToReferenceClsidPresent(this)
    && (unsigned int)SxsOleAut32MapConfiguredClsidToReferenceClsid(a2, &v18) != 1 )
  {
    v6 = (__m128)_mm_loadu_si128((const __m128i *)&v18);
  }
  else
  {
    v6 = *a2;
    v18 = *a2;
  }
  v7 = _mm_xor_ps(v6, (__m128)_mm_srli_si128((__m128i)v6, 8));
  v8 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v7, (__m128)_mm_srli_si128((__m128i)v7, 4)));
  v9 = *(_DWORD *)(*((_QWORD *)this + 18)
                 + 4 * (((unsigned __int16)v8 ^ (unsigned __int64)HIWORD(v8)) % *((unsigned int *)this + 114)));
  if ( v9 == -1 )
    return 2147647531LL;
  v11 = *((_DWORD *)this + 39);
  do
  {
    if ( v9 >= v11 )
      v12 = 0;
    else
      v12 = *((_QWORD *)this + 21) + v9;
    v13 = *(_QWORD *)v12 - v18.m128_u64[0];
    if ( *(_QWORD *)v12 == v18.m128_u64[0] )
      v13 = *(_QWORD *)(v12 + 8) - v18.m128_u64[1];
    if ( !v13 )
      break;
    v9 = *(_DWORD *)(v12 + 20);
  }
  while ( v9 != -1 );
  if ( v9 == -1 )
    return 2147647531LL;
  v14 = v9 >= v11 ? 0LL : *((_QWORD *)this + 21) + v9;
  if ( !IsInfoDef(*(_DWORD *)(v14 + 16)) )
    return 2147647531LL;
  result = CTypeLib2::GetTypeInfoOfInfoDef(this, v15, &v17);
  if ( (int)result >= 0 )
  {
    v16 = (struct ITypeInfo *)v17;
    if ( v17 )
      v16 = (struct ITypeInfo *)((char *)v17 + 8);
    *a3 = v16;
  }
  return result;
}

```

## disassembly

```asm
0x180013070  push    rbx
0x180013072  push    rsi
0x180013073  push    rdi
0x180013074  sub     rsp, 40h
0x180013078  mov     rax, cs:__security_cookie
0x18001307f  xor     rax, rsp
0x180013082  mov     [rsp+58h+var_20], rax
0x180013087  mov     [rsp+58h+var_38], 0
0x180013090  xorps   xmm0, xmm0
0x180013093  mov     rdi, r8
0x180013096  mov     rsi, rdx
0x180013099  mov     rbx, rcx
0x18001309c  movups  [rsp+58h+var_30], xmm0
0x1800130a1  test    r8, r8
0x1800130a4  jz      loc_1800131B8
0x1800130aa  mov     qword ptr [r8], 0
0x1800130b1  call    IsSxsOleAut32MapConfiguredClsidToReferenceClsidPresent
0x1800130b6  test    al, al
0x1800130b8  jz      short loc_1800130CD
0x1800130ba  lea     rdx, [rsp+58h+var_30]
0x1800130bf  mov     rcx, rsi
0x1800130c2  call    cs:__imp_SxsOleAut32MapConfiguredClsidToReferenceClsid
0x1800130c8  cmp     eax, 1
0x1800130cb  jnz     short loc_180013131
0x1800130cd  movups  xmm1, xmmword ptr [rsi]
0x1800130d0  movdqu  [rsp+58h+var_30], xmm1
0x1800130d6  movdqa  xmm0, xmm1
0x1800130da  xor     edx, edx
0x1800130dc  psrldq  xmm0, 8
0x1800130e1  or      r9d, 0FFFFFFFFh
0x1800130e5  xorps   xmm1, xmm0
0x1800130e8  movdqa  xmm0, xmm1
0x1800130ec  psrldq  xmm0, 4
0x1800130f1  xorps   xmm1, xmm0
0x1800130f4  movd    ecx, xmm1
0x1800130f8  mov     eax, ecx
0x1800130fa  movzx   ecx, cx
0x1800130fd  shr     eax, 10h
0x180013100  xor     eax, ecx
0x180013102  div     dword ptr [rbx+1C8h]
0x180013108  mov     rax, [rbx+90h]
0x18001310f  mov     edx, [rax+rdx*4]
0x180013112  cmp     edx, r9d
0x180013115  jnz     short loc_180013139
0x180013117  mov     eax, 8002802Bh
0x18001311c  mov     rcx, [rsp+58h+var_20]
0x180013121  xor     rcx, rsp; StackCookie
0x180013124  call    __security_check_cookie
0x180013129  add     rsp, 40h
0x18001312d  pop     rdi
0x18001312e  pop     rsi
0x18001312f  pop     rbx
0x180013130  retn
0x180013131  movdqu  xmm1, [rsp+58h+var_30]
0x180013137  jmp     short loc_1800130D6
0x180013139  mov     r8d, [rbx+9Ch]
0x180013140  cmp     edx, r8d
0x180013143  jnb     short loc_1800131C4
0x180013145  mov     eax, edx
0x180013147  add     rax, [rbx+0A8h]
0x18001314e  mov     rcx, [rax]
0x180013151  sub     rcx, qword ptr [rsp+58h+var_30]
0x180013156  jnz     short loc_180013161
0x180013158  mov     rcx, [rax+8]
0x18001315c  sub     rcx, qword ptr [rsp+58h+var_30+8]
0x180013161  test    rcx, rcx
0x180013164  jnz     short loc_1800131AE
0x180013166  cmp     edx, r9d
0x180013169  jz      short loc_180013117
0x18001316b  cmp     edx, r8d
0x18001316e  jnb     short loc_1800131C8
0x180013170  mov     eax, edx
0x180013172  add     rax, [rbx+0A8h]
0x180013179  mov     ecx, [rax+10h]; unsigned int
0x18001317c  call    ?IsInfoDef@@YAEK@Z; IsInfoDef(ulong)
0x180013181  test    al, al
0x180013183  jz      short loc_180013117
0x180013185  mov     edx, ecx; unsigned int
0x180013187  lea     r8, [rsp+58h+var_38]; struct CTypeInfo2 **
0x18001318c  mov     rcx, rbx; this
0x18001318f  call    ?GetTypeInfoOfInfoDef@CTypeLib2@@QEAAJKPEAPEAVCTypeInfo2@@@Z; CTypeLib2::GetTypeInfoOfInfoDef(ulong,CTypeInfo2 * *)
0x180013194  test    eax, eax
0x180013196  js      short loc_18001311C
0x180013198  mov     rcx, [rsp+58h+var_38]
0x18001319d  test    rcx, rcx
0x1800131a0  jz      short loc_1800131C2
0x1800131a2  add     rcx, 8
0x1800131a6  mov     [rdi], rcx
0x1800131a9  jmp     loc_18001311C
0x1800131ae  mov     edx, [rax+14h]
0x1800131b1  cmp     edx, r9d
0x1800131b4  jnz     short loc_180013140
0x1800131b6  jmp     short loc_180013166
0x1800131b8  mov     eax, 80070057h
0x1800131bd  jmp     loc_18001311C
0x1800131c2  jmp     short loc_1800131A6
0x1800131c4  xor     eax, eax
0x1800131c6  jmp     short loc_18001314E
0x1800131c8  xor     eax, eax
0x1800131ca  jmp     short loc_180013179
```
