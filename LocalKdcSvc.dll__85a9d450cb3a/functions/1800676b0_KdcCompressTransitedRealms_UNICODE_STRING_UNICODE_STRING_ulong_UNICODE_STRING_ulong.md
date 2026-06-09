# KdcCompressTransitedRealms(_UNICODE_STRING *,_UNICODE_STRING *,ulong,_UNICODE_STRING *,ulong)

- ea: `0x1800676b0`
- end: `0x180067969`
- name: `?KdcCompressTransitedRealms@@YAJPEAU_UNICODE_STRING@@0K0K@Z`
- size: `697`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, struct _UNICODE_STRING *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067c28`

## callees

- `0x180002ad0`
- `0x1800038f0`
- `0x180010718`
- `0x1800107dc`
- `0x180067614`
- `0x1800676b0`
- `0x180067e10`
- `0x180071868`
- `0x18007c4d4`
- `0x180099be0`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18006771e`
- `ntdll!RtlInitUnicodeString` at `0x18006771e`

## pseudocode

```c
__int64 __fastcall KdcCompressTransitedRealms(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        unsigned int a3,
        struct _UNICODE_STRING *a4,
        unsigned int a5)
{
  unsigned int v5; // r13d
  struct _UNICODE_STRING *v6; // rsi
  struct _UNICODE_STRING *v7; // rbx
  int v8; // r15d
  __int64 v9; // rax
  PUNICODE_STRING v10; // r8
  unsigned __int8 v11; // r8
  unsigned int v12; // edi
  unsigned int v13; // r14d
  struct _UNICODE_STRING *v14; // r12
  struct _UNICODE_STRING *v15; // rcx
  unsigned int v16; // r13d
  USHORT Length; // si
  int v18; // ecx
  __int64 v19; // rbx
  unsigned int v20; // r12d
  struct _UNICODE_STRING *v21; // rdi
  unsigned __int64 v22; // rcx
  __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  _DWORD *v26; // rax
  unsigned int v27; // r14d
  struct _UNICODE_STRING *v28; // rsi
  struct _UNICODE_STRING *v29; // rcx
  USHORT v30; // r15
  PWSTR Buffer; // r13
  __int64 v33; // [rsp+0h] [rbp-20h] BYREF
  int v34; // [rsp+20h] [rbp+0h] BYREF
  unsigned int v35; // [rsp+24h] [rbp+4h]
  struct _UNICODE_STRING v36; // [rsp+28h] [rbp+8h] BYREF
  unsigned int v37; // [rsp+38h] [rbp+18h] BYREF
  struct _UNICODE_STRING *v38; // [rsp+40h] [rbp+20h]
  struct _UNICODE_STRING *v39; // [rsp+48h] [rbp+28h]
  struct _UNICODE_STRING *v40; // [rsp+50h] [rbp+30h]
  _BYTE v41[24]; // [rsp+58h] [rbp+38h] BYREF

  v38 = a4;
  v5 = a3;
  v35 = a3;
  v6 = a2;
  v39 = a2;
  v40 = a1;
  v36 = 0;
  v7 = 0;
  v8 = 0;
  v34 = 0;
  v9 = lambda_2a70c627909d6c04886f368e19249c19_::_lambda_2a70c627909d6c04886f368e19249c19_(&v37, &v36);
  wil::scope_exit__lambda_2a70c627909d6c04886f368e19249c19___(v41, v9);
  RtlInitUnicodeString(v10, 0);
  v12 = 0;
  v13 = a5;
  v14 = v38;
  do
  {
    v15 = v7;
    if ( v13 == v12 )
    {
      v7 = v14;
    }
    else
    {
      if ( v12 == v5 )
        break;
      v7 = &v6[v12];
    }
    v16 = v13;
    Length = v7->Length;
    if ( v15 && !(unsigned int)KerbCompareDomains(v15, v7, &v34) )
      Length = 2 * v34;
    v18 = v8 + 2;
    if ( !v8 )
      v18 = 0;
    v8 = v18 + Length;
    if ( v13 == v12 )
      v13 = -1;
    if ( v16 != v12 )
      ++v12;
    v5 = v35;
    v6 = v39;
  }
  while ( v12 <= v35 );
  v19 = (unsigned int)(v8 + 2);
  v20 = a5;
  if ( (unsigned int)v19 > 0xFFFF )
    goto LABEL_46;
  v21 = 0;
  if ( v8 == -2 )
    goto LABEL_49;
  if ( (unsigned int)v19 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_49;
  v22 = (unsigned int)v19 + g_ulAdditionalProbeSize + 8;
  if ( v22 < (unsigned int)v19 || !(unsigned int)VerifyStackAvailable(v22) )
    goto LABEL_49;
  v23 = v19 + 23;
  if ( v19 + 23 <= (unsigned __int64)(v19 + 8) )
    v23 = 0xFFFFFFFFFFFFFF0LL;
  v24 = alloca(v23 & 0xFFFFFFFFFFFFFFF0uLL);
  v25 = alloca(v23 & 0xFFFFFFFFFFFFFFF0uLL);
  v21 = (struct _UNICODE_STRING *)&v34;
  if ( &v33 == (__int64 *)-32LL || (v34 = 1801679955, (v21 = &v36) == 0) )
  {
LABEL_49:
    if ( v19 + 8 >= (unsigned __int64)(unsigned int)v19 )
    {
      v26 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v21 = (struct _UNICODE_STRING *)v26;
      if ( v26 )
      {
        *v26 = 1885431112;
        v21 = (struct _UNICODE_STRING *)(v26 + 2);
      }
    }
  }
  v36.Buffer = &v21->Length;
  if ( !v21 )
    goto LABEL_46;
  v27 = 0;
  v28 = 0;
  v36.MaximumLength = v8 + 2;
  v36.Length = 0;
  do
  {
    v29 = v28;
    if ( v20 == v27 )
    {
      v28 = v38;
    }
    else
    {
      if ( v27 == v5 )
        break;
      v28 = &v39[v27];
    }
    v37 = v20;
    v30 = v28->Length;
    Buffer = v28->Buffer;
    if ( v29 && !(unsigned int)KerbCompareDomains(v29, v28, &v34) )
      v30 = 2 * v34;
    if ( v36.Length )
    {
      v21->Length = 44;
      v21 = (struct _UNICODE_STRING *)((char *)v21 + 2);
      v36.Length += 2;
    }
    memcpy_0(v21, Buffer, v30);
    v21 = (struct _UNICODE_STRING *)((char *)v21 + 2 * ((unsigned __int64)v30 >> 1));
    v36.Length += v30;
    if ( v20 == v27 )
      v20 = -1;
    if ( v37 != v27 )
      ++v27;
    v5 = v35;
  }
  while ( v27 <= v35 );
  v21->Length = 0;
  if ( (int)KerbDuplicateStringEx(v40, &v36, v11) >= 0 )
  {
    wil::details::lambda_call__lambda_bc89abf44a0d89d4f80feed75c491ad4___::_lambda_call__lambda_bc89abf44a0d89d4f80feed75c491ad4___(v41);
    return 0;
  }
  else
  {
LABEL_46:
    wil::details::lambda_call__lambda_bc89abf44a0d89d4f80feed75c491ad4___::_lambda_call__lambda_bc89abf44a0d89d4f80feed75c491ad4___(v41);
    return 60;
  }
}

```

## disassembly

```asm
0x1800676b0  push    rbp
0x1800676b2  push    rbx
0x1800676b3  push    rsi
0x1800676b4  push    rdi
0x1800676b5  push    r12
0x1800676b7  push    r13
0x1800676b9  push    r14
0x1800676bb  push    r15
0x1800676bd  sub     rsp, 88h
0x1800676c4  lea     rbp, [rsp+20h]
0x1800676c9  mov     rax, cs:__security_cookie
0x1800676d0  xor     rax, rbp
0x1800676d3  mov     [rbp+0A0h+var_50], rax
0x1800676d7  mov     [rbp+0A0h+var_80], r9
0x1800676db  mov     r13d, r8d
0x1800676de  mov     [rbp+0A0h+var_9C], r8d
0x1800676e2  mov     rsi, rdx
0x1800676e5  mov     [rbp+0A0h+var_78], rdx
0x1800676e9  mov     r8, rcx
0x1800676ec  mov     [rbp+0A0h+var_70], rcx
0x1800676f0  xorps   xmm0, xmm0
0x1800676f3  movups  xmmword ptr [rbp+0A0h+var_98.Length], xmm0
0x1800676f7  xor     ebx, ebx
0x1800676f9  mov     r15d, ebx
0x1800676fc  mov     [rbp+0A0h+var_A0], ebx
0x1800676ff  lea     rdx, [rbp+0A0h+var_98]
0x180067703  lea     rcx, [rbp+0A0h+var_88]
0x180067707  call    _lambda_2a70c627909d6c04886f368e19249c19____lambda_2a70c627909d6c04886f368e19249c19_
0x18006770c  mov     rdx, rax
0x18006770f  lea     rcx, [rbp+0A0h+var_68]
0x180067713  call    wil__scope_exit__lambda_2a70c627909d6c04886f368e19249c19___
0x180067718  nop
0x180067719  xor     edx, edx; SourceString
0x18006771b  mov     rcx, r8; DestinationString
0x18006771e  call    cs:__imp_RtlInitUnicodeString
0x180067724  mov     edi, ebx
0x180067726  mov     r14d, [rbp+0A0h+arg_20]
0x18006772d  mov     r12, [rbp+0A0h+var_80]
0x180067731  mov     rcx, rbx
0x180067734  cmp     r14d, edi
0x180067737  jnz     short loc_18006773E
0x180067739  mov     rbx, r12
0x18006773c  jmp     short loc_18006774C
0x18006773e  cmp     edi, r13d
0x180067741  jz      short loc_1800677A2
0x180067743  mov     ebx, edi
0x180067745  shl     rbx, 4
0x180067749  add     rbx, rsi
0x18006774c  mov     r13d, r14d
0x18006774f  movzx   esi, word ptr [rbx]
0x180067752  test    rcx, rcx
0x180067755  jz      short loc_18006776E
0x180067757  lea     r8, [rbp+0A0h+var_A0]
0x18006775b  mov     rdx, rbx
0x18006775e  call    ?KerbCompareDomains@@YA?AW4_KERB_DOMAIN_COMPARISON@@PEAU_UNICODE_STRING@@0PEAK@Z; KerbCompareDomains(_UNICODE_STRING *,_UNICODE_STRING *,ulong *)
0x180067763  test    eax, eax
0x180067765  jnz     short loc_18006776E
0x180067767  movzx   esi, word ptr [rbp+0A0h+var_A0]
0x18006776b  add     si, si
0x18006776e  lea     ecx, [r15+2]
0x180067772  test    r15d, r15d
0x180067775  cmovz   ecx, r15d
0x180067779  movzx   r15d, si
0x18006777d  add     r15d, ecx
0x180067780  cmp     r14d, edi
0x180067783  mov     eax, 0FFFFFFFFh
0x180067788  cmovz   r14d, eax
0x18006778c  lea     ecx, [rdi+1]
0x18006778f  cmp     r13d, edi
0x180067792  cmovnz  edi, ecx
0x180067795  mov     r13d, [rbp+0A0h+var_9C]
0x180067799  cmp     edi, r13d
0x18006779c  mov     rsi, [rbp+0A0h+var_78]
0x1800677a0  jbe     short loc_180067731
0x1800677a2  lea     ebx, [r15+2]
0x1800677a6  cmp     ebx, 0FFFFh
0x1800677ac  mov     r12d, [rbp+0A0h+arg_20]
0x1800677b3  ja      loc_18006793E
0x1800677b9  xor     r15d, r15d
0x1800677bc  mov     edi, r15d
0x1800677bf  test    ebx, ebx
0x1800677c1  jz      short loc_180067826
0x1800677c3  mov     esi, ebx
0x1800677c5  cmp     rsi, cs:g_ulMaxStackAllocSize
0x1800677cc  ja      short loc_180067826
0x1800677ce  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800677d5  add     rcx, 8
0x1800677d9  add     rcx, rsi
0x1800677dc  cmp     rcx, rsi
0x1800677df  jb      short loc_180067826
0x1800677e1  call    VerifyStackAvailable
0x1800677e6  test    eax, eax
0x1800677e8  jz      short loc_180067826
0x1800677ea  lea     rax, [rbx+8]
0x1800677ee  lea     rcx, [rax+0Fh]
0x1800677f2  cmp     rcx, rax
0x1800677f5  ja      short loc_180067801
0x1800677f7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180067801  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180067805  mov     rax, rcx
0x180067808  call    _alloca_probe
0x18006780d  sub     rsp, rcx
0x180067810  lea     rdi, [rsp+0C0h+var_A0]
0x180067815  test    rdi, rdi
0x180067818  jz      short loc_180067826
0x18006781a  mov     dword ptr [rdi], 6B637453h
0x180067820  add     rdi, 8
0x180067824  jnz     short loc_18006784F
0x180067826  mov     eax, ebx
0x180067828  lea     rcx, [rbx+8]
0x18006782c  cmp     rcx, rax
0x18006782f  jb      short loc_18006784F
0x180067831  mov     rax, cs:g_pfnAllocate
0x180067838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006783d  mov     rdi, rax
0x180067840  test    rax, rax
0x180067843  jz      short loc_18006784F
0x180067845  mov     dword ptr [rax], 70616548h
0x18006784b  add     rdi, 8
0x18006784f  mov     [rbp+0A0h+var_98.Buffer], rdi
0x180067853  test    rdi, rdi
0x180067856  jz      loc_18006793E
0x18006785c  mov     r14d, r15d
0x18006785f  mov     rsi, r15
0x180067862  mov     [rbp+0A0h+var_98.MaximumLength], bx
0x180067866  mov     [rbp+0A0h+var_98.Length], r15w
0x18006786b  mov     edx, 2
0x180067870  mov     rcx, rsi
0x180067873  cmp     r12d, r14d
0x180067876  jnz     short loc_18006787E
0x180067878  mov     rsi, [rbp+0A0h+var_80]
0x18006787c  jmp     short loc_180067892
0x18006787e  cmp     r14d, r13d
0x180067881  jz      loc_18006791B
0x180067887  mov     esi, r14d
0x18006788a  shl     rsi, 4
0x18006788e  add     rsi, [rbp+0A0h+var_78]
0x180067892  mov     [rbp+0A0h+var_88], r12d
0x180067896  movzx   r15d, word ptr [rsi]
0x18006789a  mov     r13, [rsi+8]
0x18006789e  xor     ebx, ebx
0x1800678a0  test    rcx, rcx
0x1800678a3  jz      short loc_1800678C1
0x1800678a5  lea     r8, [rbp+0A0h+var_A0]
0x1800678a9  mov     rdx, rsi
0x1800678ac  call    ?KerbCompareDomains@@YA?AW4_KERB_DOMAIN_COMPARISON@@PEAU_UNICODE_STRING@@0PEAK@Z; KerbCompareDomains(_UNICODE_STRING *,_UNICODE_STRING *,ulong *)
0x1800678b1  lea     edx, [rbx+2]
0x1800678b4  test    eax, eax
0x1800678b6  jnz     short loc_1800678C1
0x1800678b8  movzx   r15d, word ptr [rbp+0A0h+var_A0]
0x1800678bd  add     r15w, r15w
0x1800678c1  cmp     [rbp+0A0h+var_98.Length], bx
0x1800678c5  jz      short loc_1800678D3
0x1800678c7  mov     word ptr [rdi], 2Ch ; ','
0x1800678cc  add     rdi, rdx
0x1800678cf  add     [rbp+0A0h+var_98.Length], dx
0x1800678d3  movzx   ebx, r15w
0x1800678d7  mov     r8d, ebx; Size
0x1800678da  mov     rdx, r13; Src
0x1800678dd  mov     rcx, rdi; void *
0x1800678e0  call    memcpy_0
0x1800678e5  shr     rbx, 1
0x1800678e8  lea     rdi, [rdi+rbx*2]
0x1800678ec  add     [rbp+0A0h+var_98.Length], r15w
0x1800678f1  cmp     r12d, r14d
0x1800678f4  mov     eax, 0FFFFFFFFh
0x1800678f9  cmovz   r12d, eax
0x1800678fd  lea     ecx, [r14+1]
0x180067901  cmp     [rbp+0A0h+var_88], r14d
0x180067905  cmovnz  r14d, ecx
0x180067909  mov     r13d, [rbp+0A0h+var_9C]
0x18006790d  cmp     r14d, r13d
0x180067910  mov     edx, 2
0x180067915  jbe     loc_180067870
0x18006791b  xor     ebx, ebx
0x18006791d  mov     [rdi], bx
0x180067920  lea     rdx, [rbp+0A0h+var_98]; struct _UNICODE_STRING *
0x180067924  mov     rcx, [rbp+0A0h+var_70]; struct _UNICODE_STRING *
0x180067928  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18006792d  test    eax, eax
0x18006792f  js      short loc_18006793E
0x180067931  lea     rcx, [rbp+0A0h+var_68]
0x180067935  call    wil__details__lambda_call__lambda_bc89abf44a0d89d4f80feed75c491ad4______lambda_call__lambda_bc89abf44a0d89d4f80feed75c491ad4___
0x18006793a  xor     eax, eax
0x18006793c  jmp     short loc_18006794C
0x18006793e  lea     rcx, [rbp+0A0h+var_68]
0x180067942  call    wil__details__lambda_call__lambda_bc89abf44a0d89d4f80feed75c491ad4______lambda_call__lambda_bc89abf44a0d89d4f80feed75c491ad4___
0x180067947  mov     eax, 3Ch ; '<'
0x18006794c  mov     rcx, [rbp+0A0h+var_50]
0x180067950  xor     rcx, rbp; StackCookie
0x180067953  call    __security_check_cookie
0x180067958  lea     rsp, [rbp+68h]
0x18006795c  pop     r15
0x18006795e  pop     r14
0x180067960  pop     r13
0x180067962  pop     r12
0x180067964  pop     rdi
0x180067965  pop     rsi
0x180067966  pop     rbx
0x180067967  pop     rbp
0x180067968  retn
```
