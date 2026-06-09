# UnionFs::UnionFsFilter::CreateBootUnionConfigMessage(utl::vector<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>,utl::allocator<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>>> const &,utl::unique_ptr<UFS_MSG_CREATE_CONFIG_UNION,utl::default_delete<UFS_MSG_CREATE_CONFIG_UNION>> &,ulong *,UnionFs::StackEventTracer &)

- ea: `0x140008c38`
- end: `0x1400090e9`
- name: `?CreateBootUnionConfigMessage@UnionFsFilter@UnionFs@@AEAAJAEBV?$vector@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@@utl@@@utl@@AEAV?$unique_ptr@UUFS_MSG_CREATE_CONFIG_UNION@@U?$default_delete@UUFS_MSG_CREATE_CONFIG_UNION@@@utl@@@4@PEAKAEAVStackEventTracer@2@@Z`
- size: `1201`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140008b0c`

## callees

- `0x140008c38`
- `0x14000fde8`
- `0x140056bd0`
- `0x140056c44`
- `0x14007bc40`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009057`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009077`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009057`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009077`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090c6`
- `ntoskrnl!ExAllocatePool2` at `0x140008d95`
- `ntoskrnl!ExAllocatePool2` at `0x140008d95`
- `ntoskrnl!ExUuidCreate` at `0x140008dd6`
- `ntoskrnl!ExUuidCreate` at `0x140008dd6`

## string_xrefs

- `0x140008dfb`: `UnionFs::UnionFsFilter::CreateBootUnionConfigMessage`
- `0x140008e5b`: `UnionFs::UnionFsFilter::CreateBootUnionConfigMessage`
- `0x140008ebc`: `UnionFs::UnionFsFilter::CreateBootUnionConfigMessage`
- `0x140009096`: `UnionFs::UnionFsFilter::CreateBootUnionConfigMessage`
- `0x14000908f`: `ORIGIN: Allocating CIM union config buffer`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::CreateBootUnionConfigMessage(
        __int64 a1,
        __int64 *a2,
        void **a3,
        unsigned int *a4,
        int a5)
{
  void *v6; // rcx
  unsigned int *v7; // r12
  void **v8; // r15
  __m128i si128; // xmm0
  unsigned __int64 v11; // rbx
  __int64 v12; // rdx
  unsigned int v13; // r14d
  _WORD *v14; // rbx
  unsigned int v15; // r9d
  unsigned __int16 v16; // cx
  unsigned __int16 v17; // r8
  __int64 v18; // rdx
  UUID *Pool2; // rax
  UUID *v20; // rdi
  NTSTATUS v21; // ebp
  PVOID v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // eax
  unsigned int v27; // ebp
  __int64 v28; // rdx
  _WORD *v29; // r12
  __int64 v30; // r13
  size_t v31; // r11
  __int64 v32; // r9
  __int64 v33; // rax
  void *v34; // rcx
  const char *v35; // [rsp+28h] [rbp-70h]
  PVOID P[2]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v37; // [rsp+48h] [rbp-50h]
  int v39; // [rsp+A8h] [rbp+10h]

  v6 = *a3;
  v7 = a4;
  *a3 = 0;
  v8 = a3;
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v11 = (a2[1] - *a2) >> 3;
  *v7 = 0;
  v37 = -1;
  *(__m128i *)P = si128;
  if ( v11 )
  {
    if ( v11 >= 0x4000000000000000LL
      || !(unsigned __int8)utl::vector<unsigned short,utl::allocator<unsigned short>>::_SetCapacity(P) )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        a5,
        (struct UnionFs::StackEventTracer *)0xE800010F7BLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::CreateBootUnionConfigMessage",
        "ORIGIN: Allocating rootid sizes vector",
        v35);
      v23 = P[0];
      if ( P[0] == (PVOID)-1LL || !P[0] )
        return 3221225626LL;
      goto LABEL_49;
    }
    memset(P[1], 0, 2 * v11);
  }
  v12 = *a2;
  v13 = 8 * v11 + 48;
  v14 = P[0];
  if ( !((a2[1] - *a2) >> 3) )
  {
LABEL_14:
    v18 = v13;
    if ( !v13 )
      v18 = 1;
    Pool2 = (UUID *)ExAllocatePool2(256, v18, 1868711509);
    v20 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, v13);
      v20->Data1 = v13;
      *(_DWORD *)&v20->Data2 = 10;
      *(_DWORD *)v20->Data4 = (a2[1] - *a2) >> 3;
      v21 = ExUuidCreate(v20 + 1);
      if ( v21 >= 0 )
      {
        v25 = *a2;
        if ( (a2[1] - *a2) >> 3 )
        {
          v26 = *(_DWORD *)v20->Data4;
          v27 = 0;
          v28 = (unsigned int)(8 * v26 + 48);
          v39 = 8 * v26 + 48;
          do
          {
            v29 = (_WORD *)((char *)v20 + v28);
            v30 = v27 - 1;
            *(_DWORD *)&v20[2].Data4[8 * v27] = v28;
            *(_WORD *)&v20[2].Data4[8 * v27 + 4] = v14[v27];
            *v29 = v14[v27];
            v31 = *(unsigned __int16 *)(*(_QWORD *)(v25 + 8LL * v27) + 120LL);
            v29[1] = v31;
            v29[2] = v31 + 2;
            if ( v27 )
              v29[2] = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 208) + 16LL) + 24 * v30 + 8) + v31 + 2;
            memmove(
              (char *)&v20->Data3 + (unsigned int)v28,
              *(const void **)(*(_QWORD *)(v25 + 8LL * v27) + 128LL),
              v31);
            v29[((unsigned __int64)(unsigned __int16)v29[2] >> 1) + 2] = 92;
            if ( v27 )
            {
              v32 = *(_QWORD *)(*(_QWORD *)(a1 + 208) + 16LL);
              if ( *(_WORD *)(v32 + 24 * v30 + 8) )
                memmove(
                  &v29[((unsigned __int64)(unsigned __int16)v29[1] >> 1) + 4],
                  *(const void **)(v32 + 24 * v30 + 16),
                  *(unsigned __int16 *)(v32 + 24 * v30 + 8));
            }
            v25 = *a2;
            v33 = v27++;
            v28 = (unsigned int)*(unsigned __int16 *)&v20[2].Data4[8 * v33 + 4] + v39;
            v39 += *(unsigned __int16 *)&v20[2].Data4[8 * v33 + 4];
          }
          while ( v27 < (unsigned __int64)((a2[1] - *a2) >> 3) );
          v8 = a3;
          v7 = a4;
        }
        v34 = *v8;
        *v8 = v20;
        if ( v34 )
          ExFreePoolWithTag(v34, 0);
        *v7 = v13;
        if ( v14 != (_WORD *)-1LL && v14 )
          ExFreePoolWithTag(v14, 0);
        return 0;
      }
      else
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v21,
          a5,
          (struct UnionFs::StackEventTracer *)0x1C00010FA9LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::CreateBootUnionConfigMessage",
          "API: Generating boot union ID",
          v35);
        ExFreePoolWithTag(v20, 0);
        if ( v14 != (_WORD *)-1LL )
        {
          if ( v14 )
            ExFreePoolWithTag(v14, 0);
        }
        return (unsigned int)v21;
      }
    }
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x7400010F9ELL,
      (unsigned __int64)"UnionFs::UnionFsFilter::CreateBootUnionConfigMessage",
      "ORIGIN: Allocating CIM union config buffer",
      v35);
    if ( v14 == (_WORD *)-1LL || !v14 )
      return 3221225626LL;
    v23 = v14;
LABEL_49:
    ExFreePoolWithTag(v23, 0);
    return 3221225626LL;
  }
  v15 = 0;
  while ( 1 )
  {
    v16 = *(_WORD *)(*(_QWORD *)(v12 + 8LL * v15) + 120LL) + 6;
    if ( v16 < 6u )
      break;
    v17 = *(_WORD *)(*(_QWORD *)(v12 + 8LL * v15) + 120LL) + 8;
    if ( (unsigned __int16)(v16 + 2) < v16 )
    {
      v24 = 0x5EC00010F8BLL;
      goto LABEL_27;
    }
    if ( v15 )
      v17 += *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 208) + 16LL) + 24LL * (v15 - 1) + 8);
    v14[v15++] = v17;
    v12 = *a2;
    v13 += v17;
    if ( v15 >= (unsigned __int64)((a2[1] - *a2) >> 3) )
      goto LABEL_14;
  }
  v24 = 0x5EB00010F86LL;
LABEL_27:
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)0xC0000095LL,
    a5,
    (struct UnionFs::StackEventTracer *)v24,
    (unsigned __int64)"UnionFs::UnionFsFilter::CreateBootUnionConfigMessage",
    "API: Root Id Size",
    v35);
  if ( v14 != (_WORD *)-1LL && v14 )
    ExFreePoolWithTag(v14, 0);
  return 3221225621LL;
}

```

## disassembly

```asm
0x140008c38  mov     [rsp+arg_18], r9
0x140008c3d  mov     [rsp+arg_10], r8
0x140008c42  mov     [rsp+arg_0], rcx
0x140008c47  push    rbx
0x140008c48  push    rbp
0x140008c49  push    rsi
0x140008c4a  push    rdi
0x140008c4b  push    r12
0x140008c4d  push    r13
0x140008c4f  push    r14
0x140008c51  push    r15
0x140008c53  sub     rsp, 58h
0x140008c57  xor     r13d, r13d
0x140008c5a  mov     rdi, rcx
0x140008c5d  mov     rcx, [r8]; P
0x140008c60  mov     r12, r9
0x140008c63  mov     [r8], r13
0x140008c66  mov     r15, r8
0x140008c69  mov     rsi, rdx
0x140008c6c  test    rcx, rcx
0x140008c6f  jz      short loc_140008C7F
0x140008c71  xor     edx, edx; Tag
0x140008c73  call    cs:__imp_ExFreePoolWithTag
0x140008c7a  nop     dword ptr [rax+rax+00h]
0x140008c7f  mov     rbx, [rsi+8]
0x140008c83  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140008c87  sub     rbx, [rsi]
0x140008c8a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140008c92  sar     rbx, 3
0x140008c96  mov     [r12], r13d
0x140008c9a  mov     [rsp+98h+var_50], rbp
0x140008c9f  movdqu  xmmword ptr [rsp+98h+P], xmm0
0x140008ca5  test    rbx, rbx
0x140008ca8  jz      short loc_140008CEA
0x140008caa  lea     edx, [rbp+9]
0x140008cad  cmp     rbx, rdx
0x140008cb0  jbe     short loc_140008CC8
0x140008cb2  mov     rax, 3FFFFFFFFFFFFFFFh
0x140008cbc  cmp     rbx, rax
0x140008cbf  ja      loc_140008E4C
0x140008cc5  mov     rdx, rbx
0x140008cc8  lea     rcx, [rsp+98h+P]
0x140008ccd  call    ?_SetCapacity@?$vector@GV?$allocator@G@utl@@@utl@@AEAA_N_K@Z; utl::vector<ushort,utl::allocator<ushort>>::_SetCapacity(unsigned __int64)
0x140008cd2  test    al, al
0x140008cd4  jz      loc_140008E4C
0x140008cda  mov     rcx, [rsp+98h+P+8]; void *
0x140008cdf  lea     r8, [rbx+rbx]; Size
0x140008ce3  xor     edx, edx; Val
0x140008ce5  call    memset
0x140008cea  mov     rdx, [rsi]
0x140008ced  lea     r14d, ds:30h[rbx*8]
0x140008cf5  mov     rax, [rsi+8]
0x140008cf9  mov     r11d, 1
0x140008cff  mov     rbx, [rsp+98h+P]
0x140008d04  sub     rax, rdx
0x140008d07  sar     rax, 3
0x140008d0b  test    rax, rax
0x140008d0e  jz      short loc_140008D7D
0x140008d10  mov     r9d, r13d
0x140008d13  mov     r10d, r9d
0x140008d16  mov     rax, [rdx+r10*8]
0x140008d1a  movzx   ecx, word ptr [rax+78h]
0x140008d1e  add     cx, 6
0x140008d22  cmp     cx, 6
0x140008d26  jb      loc_140008EA3
0x140008d2c  lea     r8d, [rcx+2]
0x140008d30  cmp     r8w, cx
0x140008d34  jb      loc_140008E97
0x140008d3a  test    r9d, r9d
0x140008d3d  jz      short loc_140008D58
0x140008d3f  lea     eax, [r9-1]
0x140008d43  lea     rdx, [rax+rax*2]
0x140008d47  mov     rax, [rdi+0D0h]
0x140008d4e  mov     rcx, [rax+10h]
0x140008d52  add     r8w, [rcx+rdx*8+8]
0x140008d58  mov     [rbx+r10*2], r8w
0x140008d5d  add     r9d, r11d
0x140008d60  mov     rdx, [rsi]
0x140008d63  mov     rcx, [rsi+8]
0x140008d67  movzx   eax, r8w
0x140008d6b  sub     rcx, rdx
0x140008d6e  add     r14d, eax
0x140008d71  sar     rcx, 3
0x140008d75  mov     eax, r9d
0x140008d78  cmp     rax, rcx
0x140008d7b  jb      short loc_140008D13
0x140008d7d  test    r14d, r14d
0x140008d80  mov     edx, r14d
0x140008d83  mov     ecx, 100h
0x140008d88  mov     ebp, r14d
0x140008d8b  cmovz   rdx, r11
0x140008d8f  mov     r8d, 6F624655h
0x140008d95  call    cs:__imp_ExAllocatePool2
0x140008d9c  nop     dword ptr [rax+rax+00h]
0x140008da1  mov     rdi, rax
0x140008da4  test    rax, rax
0x140008da7  jz      loc_140009087
0x140008dad  mov     r8d, ebp; Size
0x140008db0  xor     edx, edx; Val
0x140008db2  mov     rcx, rax; void *
0x140008db5  call    memset
0x140008dba  mov     [rdi], r14d
0x140008dbd  lea     rcx, [rdi+10h]; Uuid
0x140008dc1  mov     dword ptr [rdi+4], 0Ah
0x140008dc8  mov     rdx, [rsi+8]
0x140008dcc  sub     rdx, [rsi]
0x140008dcf  sar     rdx, 3
0x140008dd3  mov     [rdi+8], edx
0x140008dd6  call    cs:__imp_ExUuidCreate
0x140008ddd  nop     dword ptr [rax+rax+00h]
0x140008de2  mov     ebp, eax
0x140008de4  test    eax, eax
0x140008de6  jns     loc_140008EF7
0x140008dec  mov     rdx, qword ptr [rsp+98h+arg_20]; int
0x140008df4  lea     rax, aApiGeneratingB; "API: Generating boot union ID"
0x140008dfb  lea     r9, aUnionfsUnionfs_17; "UnionFs::UnionFsFilter::CreateBootUnion"...
0x140008e02  mov     [rsp+98h+var_78], rax; char *
0x140008e07  mov     r8, 1C00010FA9h; struct UnionFs::StackEventTracer *
0x140008e11  mov     ecx, ebp; this
0x140008e13  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140008e18  xor     edx, edx; Tag
0x140008e1a  mov     rcx, rdi; P
0x140008e1d  call    cs:__imp_ExFreePoolWithTag
0x140008e24  nop     dword ptr [rax+rax+00h]
0x140008e29  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140008e2d  jz      short loc_140008E45
0x140008e2f  test    rbx, rbx
0x140008e32  jz      short loc_140008E45
0x140008e34  xor     edx, edx; Tag
0x140008e36  mov     rcx, rbx; P
0x140008e39  call    cs:__imp_ExFreePoolWithTag
0x140008e40  nop     dword ptr [rax+rax+00h]
0x140008e45  mov     eax, ebp
0x140008e47  jmp     loc_1400090D7
0x140008e4c  mov     rdx, qword ptr [rsp+98h+arg_20]; int
0x140008e54  lea     rax, aOriginAllocati_78; "ORIGIN: Allocating rootid sizes vector"
0x140008e5b  lea     r9, aUnionfsUnionfs_17; "UnionFs::UnionFsFilter::CreateBootUnion"...
0x140008e62  mov     [rsp+98h+var_78], rax; char *
0x140008e67  mov     r8, 0E800010F7Bh; struct UnionFs::StackEventTracer *
0x140008e71  mov     ecx, 0C000009Ah; this
0x140008e76  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140008e7b  mov     rcx, [rsp+98h+P]
0x140008e80  cmp     rcx, rbp
0x140008e83  jz      loc_1400090D2
0x140008e89  test    rcx, rcx
0x140008e8c  jz      loc_1400090D2
0x140008e92  jmp     loc_1400090C4
0x140008e97  mov     r8, 5EC00010F8Bh
0x140008ea1  jmp     short loc_140008EAD
0x140008ea3  mov     r8, 5EB00010F86h; struct UnionFs::StackEventTracer *
0x140008ead  mov     rdx, qword ptr [rsp+98h+arg_20]; int
0x140008eb5  lea     rax, aApiRootIdSize; "API: Root Id Size"
0x140008ebc  lea     r9, aUnionfsUnionfs_17; "UnionFs::UnionFsFilter::CreateBootUnion"...
0x140008ec3  mov     [rsp+98h+var_78], rax; char *
0x140008ec8  mov     ecx, 0C0000095h; this
0x140008ecd  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140008ed2  cmp     rbx, rbp
0x140008ed5  jz      short loc_140008EED
0x140008ed7  test    rbx, rbx
0x140008eda  jz      short loc_140008EED
0x140008edc  xor     edx, edx; Tag
0x140008ede  mov     rcx, rbx; P
0x140008ee1  call    cs:__imp_ExFreePoolWithTag
0x140008ee8  nop     dword ptr [rax+rax+00h]
0x140008eed  mov     eax, 0C0000095h
0x140008ef2  jmp     loc_1400090D7
0x140008ef7  mov     r9, [rsi]
0x140008efa  mov     rax, [rsi+8]
0x140008efe  sub     rax, r9
0x140008f01  sar     rax, 3
0x140008f05  test    rax, rax
0x140008f08  jz      loc_14000904A
0x140008f0e  mov     eax, [rdi+8]
0x140008f11  mov     ebp, r13d
0x140008f14  mov     r15, [rsp+98h+arg_0]
0x140008f1c  lea     edx, ds:30h[rax*8]
0x140008f23  mov     [rsp+98h+arg_8], edx
0x140008f2a  mov     r10d, ebp
0x140008f2d  lea     r12, [rdi+rdx]
0x140008f31  lea     r13d, [rbp-1]
0x140008f35  mov     [rdi+r10*8+28h], edx
0x140008f3a  movzx   eax, word ptr [rbx+r10*2]
0x140008f3f  mov     [rdi+r10*8+2Ch], ax
0x140008f45  mov     eax, edx
0x140008f47  mov     [rsp+98h+var_68], rax
0x140008f4c  movzx   eax, word ptr [rbx+r10*2]
0x140008f51  mov     [r12], ax
0x140008f56  mov     rax, [r9+r10*8]
0x140008f5a  movzx   r11d, word ptr [rax+78h]
0x140008f5f  mov     [r12+2], r11w
0x140008f65  lea     r8d, [r11+2]
0x140008f69  mov     [r12+4], r8w
0x140008f6f  test    ebp, ebp
0x140008f71  jz      short loc_140008F95
0x140008f73  mov     rax, [r15+0D0h]
0x140008f7a  lea     rdx, ds:0[r13*2]
0x140008f82  add     rdx, r13
0x140008f85  mov     rcx, [rax+10h]
0x140008f89  add     r8w, [rcx+rdx*8+8]
0x140008f8f  mov     [r12+4], r8w
0x140008f95  mov     rdx, [r9+r10*8]
0x140008f99  mov     r8, r11; Size
0x140008f9c  mov     rcx, [rsp+98h+var_68]
0x140008fa1  add     rcx, 6
0x140008fa5  add     rcx, rdi; void *
0x140008fa8  mov     rdx, [rdx+80h]; Src
0x140008faf  call    memmove
0x140008fb4  movzx   eax, word ptr [r12+4]
0x140008fba  shr     rax, 1
0x140008fbd  mov     word ptr [r12+rax*2+4], 5Ch ; '\'
0x140008fc5  test    ebp, ebp
0x140008fc7  jz      short loc_140009008
0x140008fc9  mov     rax, [r15+0D0h]
0x140008fd0  lea     rdx, ds:0[r13*2]
0x140008fd8  add     rdx, r13
0x140008fdb  mov     r9, [rax+10h]
0x140008fdf  movzx   eax, word ptr [r9+rdx*8+8]
0x140008fe5  test    ax, ax
0x140008fe8  jz      short loc_140009008
0x140008fea  mov     rdx, [r9+rdx*8+10h]; Src
0x140008fef  mov     r8d, eax; Size
0x140008ff2  movzx   eax, word ptr [r12+2]
0x140008ff8  shr     rax, 1
0x140008ffb  add     rax, 4
0x140008fff  lea     rcx, [r12+rax*2]; void *
0x140009003  call    memmove
0x140009008  mov     edx, [rsp+98h+arg_8]
0x14000900f  mov     r9, [rsi]
0x140009012  mov     rcx, [rsi+8]
0x140009016  mov     eax, ebp
0x140009018  sub     rcx, r9
0x14000901b  inc     ebp
0x14000901d  sar     rcx, 3
0x140009021  movzx   eax, word ptr [rdi+rax*8+2Ch]
0x140009026  add     edx, eax
0x140009028  mov     eax, ebp
0x14000902a  mov     [rsp+98h+arg_8], edx
0x140009031  cmp     rax, rcx
0x140009034  jb      loc_140008F2A
0x14000903a  mov     r15, [rsp+98h+arg_10]
0x140009042  mov     r12, [rsp+98h+arg_18]
0x14000904a  mov     rcx, [r15]; P
0x14000904d  mov     [r15], rdi
0x140009050  test    rcx, rcx
0x140009053  jz      short loc_140009063
0x140009055  xor     edx, edx; Tag
0x140009057  call    cs:__imp_ExFreePoolWithTag
0x14000905e  nop     dword ptr [rax+rax+00h]
0x140009063  mov     [r12], r14d
0x140009067  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000906b  jz      short loc_140009083
0x14000906d  test    rbx, rbx
0x140009070  jz      short loc_140009083
0x140009072  xor     edx, edx; Tag
0x140009074  mov     rcx, rbx; P
0x140009077  call    cs:__imp_ExFreePoolWithTag
0x14000907e  nop     dword ptr [rax+rax+00h]
0x140009083  xor     eax, eax
0x140009085  jmp     short loc_1400090D7
0x140009087  mov     rdx, qword ptr [rsp+98h+arg_20]; int
0x14000908f  lea     rax, aOriginAllocati_54; "ORIGIN: Allocating CIM union config buf"...
0x140009096  lea     r9, aUnionfsUnionfs_17; "UnionFs::UnionFsFilter::CreateBootUnion"...
0x14000909d  mov     [rsp+98h+var_78], rax; char *
0x1400090a2  mov     r8, 7400010F9Eh; struct UnionFs::StackEventTracer *
0x1400090ac  mov     ecx, 0C000009Ah; this
0x1400090b1  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400090b6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400090ba  jz      short loc_1400090D2
0x1400090bc  test    rbx, rbx
0x1400090bf  jz      short loc_1400090D2
0x1400090c1  mov     rcx, rbx; P
0x1400090c4  xor     edx, edx; Tag
0x1400090c6  call    cs:__imp_ExFreePoolWithTag
0x1400090cd  nop     dword ptr [rax+rax+00h]
0x1400090d2  mov     eax, 0C000009Ah
0x1400090d7  add     rsp, 58h
0x1400090db  pop     r15
0x1400090dd  pop     r14
0x1400090df  pop     r13
0x1400090e1  pop     r12
0x1400090e3  pop     rdi
0x1400090e4  pop     rsi
0x1400090e5  pop     rbp
0x1400090e6  pop     rbx
0x1400090e7  retn
```
