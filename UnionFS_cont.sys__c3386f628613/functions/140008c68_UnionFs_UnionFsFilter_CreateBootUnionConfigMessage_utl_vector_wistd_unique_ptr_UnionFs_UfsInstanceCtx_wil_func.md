# UnionFs::UnionFsFilter::CreateBootUnionConfigMessage(utl::vector<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>,utl::allocator<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>>> const &,utl::unique_ptr<UFS_MSG_CREATE_CONFIG_UNION,utl::default_delete<UFS_MSG_CREATE_CONFIG_UNION>> &,ulong *,UnionFs::StackEventTracer &)

- ea: `0x140008c68`
- end: `0x140009119`
- name: `?CreateBootUnionConfigMessage@UnionFsFilter@UnionFs@@AEAAJAEBV?$vector@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@@utl@@@utl@@AEAV?$unique_ptr@UUFS_MSG_CREATE_CONFIG_UNION@@U?$default_delete@UUFS_MSG_CREATE_CONFIG_UNION@@@utl@@@4@PEAKAEAVStackEventTracer@2@@Z`
- size: `1201`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140008b3c`

## callees

- `0x140008c68`
- `0x14000fdc8`
- `0x140056a50`
- `0x140056ac4`
- `0x14007b900`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008ca3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009087`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ca3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009087`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090f6`
- `ntoskrnl!ExAllocatePool2` at `0x140008dc5`
- `ntoskrnl!ExAllocatePool2` at `0x140008dc5`
- `ntoskrnl!ExUuidCreate` at `0x140008e06`
- `ntoskrnl!ExUuidCreate` at `0x140008e06`

## string_xrefs

- `0x140008e2b`: `UnionFs::UnionFsFilter::CreateBootUnionConfigMessage`
- `0x140008e8b`: `UnionFs::UnionFsFilter::CreateBootUnionConfigMessage`
- `0x140008eec`: `UnionFs::UnionFsFilter::CreateBootUnionConfigMessage`
- `0x1400090c6`: `UnionFs::UnionFsFilter::CreateBootUnionConfigMessage`
- `0x1400090bf`: `ORIGIN: Allocating CIM union config buffer`

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
        (struct UnionFs::StackEventTracer *)0xE800010F6ELL,
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
          (struct UnionFs::StackEventTracer *)0x1C00010F9CLL,
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
      (struct UnionFs::StackEventTracer *)0x7400010F91LL,
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
      v24 = 0x5EC00010F7ELL;
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
  v24 = 0x5EB00010F79LL;
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
0x140008c68  mov     [rsp+arg_18], r9
0x140008c6d  mov     [rsp+arg_10], r8
0x140008c72  mov     [rsp+arg_0], rcx
0x140008c77  push    rbx
0x140008c78  push    rbp
0x140008c79  push    rsi
0x140008c7a  push    rdi
0x140008c7b  push    r12
0x140008c7d  push    r13
0x140008c7f  push    r14
0x140008c81  push    r15
0x140008c83  sub     rsp, 58h
0x140008c87  xor     r13d, r13d
0x140008c8a  mov     rdi, rcx
0x140008c8d  mov     rcx, [r8]; P
0x140008c90  mov     r12, r9
0x140008c93  mov     [r8], r13
0x140008c96  mov     r15, r8
0x140008c99  mov     rsi, rdx
0x140008c9c  test    rcx, rcx
0x140008c9f  jz      short loc_140008CAF
0x140008ca1  xor     edx, edx; Tag
0x140008ca3  call    cs:__imp_ExFreePoolWithTag
0x140008caa  nop     dword ptr [rax+rax+00h]
0x140008caf  mov     rbx, [rsi+8]
0x140008cb3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140008cb7  sub     rbx, [rsi]
0x140008cba  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140008cc2  sar     rbx, 3
0x140008cc6  mov     [r12], r13d
0x140008cca  mov     [rsp+98h+var_50], rbp
0x140008ccf  movdqu  xmmword ptr [rsp+98h+P], xmm0
0x140008cd5  test    rbx, rbx
0x140008cd8  jz      short loc_140008D1A
0x140008cda  lea     edx, [rbp+9]
0x140008cdd  cmp     rbx, rdx
0x140008ce0  jbe     short loc_140008CF8
0x140008ce2  mov     rax, 3FFFFFFFFFFFFFFFh
0x140008cec  cmp     rbx, rax
0x140008cef  ja      loc_140008E7C
0x140008cf5  mov     rdx, rbx
0x140008cf8  lea     rcx, [rsp+98h+P]
0x140008cfd  call    ?_SetCapacity@?$vector@GV?$allocator@G@utl@@@utl@@AEAA_N_K@Z; utl::vector<ushort,utl::allocator<ushort>>::_SetCapacity(unsigned __int64)
0x140008d02  test    al, al
0x140008d04  jz      loc_140008E7C
0x140008d0a  mov     rcx, [rsp+98h+P+8]; void *
0x140008d0f  lea     r8, [rbx+rbx]; Size
0x140008d13  xor     edx, edx; Val
0x140008d15  call    memset
0x140008d1a  mov     rdx, [rsi]
0x140008d1d  lea     r14d, ds:30h[rbx*8]
0x140008d25  mov     rax, [rsi+8]
0x140008d29  mov     r11d, 1
0x140008d2f  mov     rbx, [rsp+98h+P]
0x140008d34  sub     rax, rdx
0x140008d37  sar     rax, 3
0x140008d3b  test    rax, rax
0x140008d3e  jz      short loc_140008DAD
0x140008d40  mov     r9d, r13d
0x140008d43  mov     r10d, r9d
0x140008d46  mov     rax, [rdx+r10*8]
0x140008d4a  movzx   ecx, word ptr [rax+78h]
0x140008d4e  add     cx, 6
0x140008d52  cmp     cx, 6
0x140008d56  jb      loc_140008ED3
0x140008d5c  lea     r8d, [rcx+2]
0x140008d60  cmp     r8w, cx
0x140008d64  jb      loc_140008EC7
0x140008d6a  test    r9d, r9d
0x140008d6d  jz      short loc_140008D88
0x140008d6f  lea     eax, [r9-1]
0x140008d73  lea     rdx, [rax+rax*2]
0x140008d77  mov     rax, [rdi+0D0h]
0x140008d7e  mov     rcx, [rax+10h]
0x140008d82  add     r8w, [rcx+rdx*8+8]
0x140008d88  mov     [rbx+r10*2], r8w
0x140008d8d  add     r9d, r11d
0x140008d90  mov     rdx, [rsi]
0x140008d93  mov     rcx, [rsi+8]
0x140008d97  movzx   eax, r8w
0x140008d9b  sub     rcx, rdx
0x140008d9e  add     r14d, eax
0x140008da1  sar     rcx, 3
0x140008da5  mov     eax, r9d
0x140008da8  cmp     rax, rcx
0x140008dab  jb      short loc_140008D43
0x140008dad  test    r14d, r14d
0x140008db0  mov     edx, r14d
0x140008db3  mov     ecx, 100h
0x140008db8  mov     ebp, r14d
0x140008dbb  cmovz   rdx, r11
0x140008dbf  mov     r8d, 6F624655h
0x140008dc5  call    cs:__imp_ExAllocatePool2
0x140008dcc  nop     dword ptr [rax+rax+00h]
0x140008dd1  mov     rdi, rax
0x140008dd4  test    rax, rax
0x140008dd7  jz      loc_1400090B7
0x140008ddd  mov     r8d, ebp; Size
0x140008de0  xor     edx, edx; Val
0x140008de2  mov     rcx, rax; void *
0x140008de5  call    memset
0x140008dea  mov     [rdi], r14d
0x140008ded  lea     rcx, [rdi+10h]; Uuid
0x140008df1  mov     dword ptr [rdi+4], 0Ah
0x140008df8  mov     rdx, [rsi+8]
0x140008dfc  sub     rdx, [rsi]
0x140008dff  sar     rdx, 3
0x140008e03  mov     [rdi+8], edx
0x140008e06  call    cs:__imp_ExUuidCreate
0x140008e0d  nop     dword ptr [rax+rax+00h]
0x140008e12  mov     ebp, eax
0x140008e14  test    eax, eax
0x140008e16  jns     loc_140008F27
0x140008e1c  mov     rdx, qword ptr [rsp+98h+arg_20]; int
0x140008e24  lea     rax, aApiGeneratingB; "API: Generating boot union ID"
0x140008e2b  lea     r9, aUnionfsUnionfs_17; "UnionFs::UnionFsFilter::CreateBootUnion"...
0x140008e32  mov     [rsp+98h+var_78], rax; char *
0x140008e37  mov     r8, 1C00010F9Ch; struct UnionFs::StackEventTracer *
0x140008e41  mov     ecx, ebp; this
0x140008e43  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140008e48  xor     edx, edx; Tag
0x140008e4a  mov     rcx, rdi; P
0x140008e4d  call    cs:__imp_ExFreePoolWithTag
0x140008e54  nop     dword ptr [rax+rax+00h]
0x140008e59  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140008e5d  jz      short loc_140008E75
0x140008e5f  test    rbx, rbx
0x140008e62  jz      short loc_140008E75
0x140008e64  xor     edx, edx; Tag
0x140008e66  mov     rcx, rbx; P
0x140008e69  call    cs:__imp_ExFreePoolWithTag
0x140008e70  nop     dword ptr [rax+rax+00h]
0x140008e75  mov     eax, ebp
0x140008e77  jmp     loc_140009107
0x140008e7c  mov     rdx, qword ptr [rsp+98h+arg_20]; int
0x140008e84  lea     rax, aOriginAllocati_77; "ORIGIN: Allocating rootid sizes vector"
0x140008e8b  lea     r9, aUnionfsUnionfs_17; "UnionFs::UnionFsFilter::CreateBootUnion"...
0x140008e92  mov     [rsp+98h+var_78], rax; char *
0x140008e97  mov     r8, 0E800010F6Eh; struct UnionFs::StackEventTracer *
0x140008ea1  mov     ecx, 0C000009Ah; this
0x140008ea6  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140008eab  mov     rcx, [rsp+98h+P]
0x140008eb0  cmp     rcx, rbp
0x140008eb3  jz      loc_140009102
0x140008eb9  test    rcx, rcx
0x140008ebc  jz      loc_140009102
0x140008ec2  jmp     loc_1400090F4
0x140008ec7  mov     r8, 5EC00010F7Eh
0x140008ed1  jmp     short loc_140008EDD
0x140008ed3  mov     r8, 5EB00010F79h; struct UnionFs::StackEventTracer *
0x140008edd  mov     rdx, qword ptr [rsp+98h+arg_20]; int
0x140008ee5  lea     rax, aApiRootIdSize; "API: Root Id Size"
0x140008eec  lea     r9, aUnionfsUnionfs_17; "UnionFs::UnionFsFilter::CreateBootUnion"...
0x140008ef3  mov     [rsp+98h+var_78], rax; char *
0x140008ef8  mov     ecx, 0C0000095h; this
0x140008efd  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140008f02  cmp     rbx, rbp
0x140008f05  jz      short loc_140008F1D
0x140008f07  test    rbx, rbx
0x140008f0a  jz      short loc_140008F1D
0x140008f0c  xor     edx, edx; Tag
0x140008f0e  mov     rcx, rbx; P
0x140008f11  call    cs:__imp_ExFreePoolWithTag
0x140008f18  nop     dword ptr [rax+rax+00h]
0x140008f1d  mov     eax, 0C0000095h
0x140008f22  jmp     loc_140009107
0x140008f27  mov     r9, [rsi]
0x140008f2a  mov     rax, [rsi+8]
0x140008f2e  sub     rax, r9
0x140008f31  sar     rax, 3
0x140008f35  test    rax, rax
0x140008f38  jz      loc_14000907A
0x140008f3e  mov     eax, [rdi+8]
0x140008f41  mov     ebp, r13d
0x140008f44  mov     r15, [rsp+98h+arg_0]
0x140008f4c  lea     edx, ds:30h[rax*8]
0x140008f53  mov     [rsp+98h+arg_8], edx
0x140008f5a  mov     r10d, ebp
0x140008f5d  lea     r12, [rdi+rdx]
0x140008f61  lea     r13d, [rbp-1]
0x140008f65  mov     [rdi+r10*8+28h], edx
0x140008f6a  movzx   eax, word ptr [rbx+r10*2]
0x140008f6f  mov     [rdi+r10*8+2Ch], ax
0x140008f75  mov     eax, edx
0x140008f77  mov     [rsp+98h+var_68], rax
0x140008f7c  movzx   eax, word ptr [rbx+r10*2]
0x140008f81  mov     [r12], ax
0x140008f86  mov     rax, [r9+r10*8]
0x140008f8a  movzx   r11d, word ptr [rax+78h]
0x140008f8f  mov     [r12+2], r11w
0x140008f95  lea     r8d, [r11+2]
0x140008f99  mov     [r12+4], r8w
0x140008f9f  test    ebp, ebp
0x140008fa1  jz      short loc_140008FC5
0x140008fa3  mov     rax, [r15+0D0h]
0x140008faa  lea     rdx, ds:0[r13*2]
0x140008fb2  add     rdx, r13
0x140008fb5  mov     rcx, [rax+10h]
0x140008fb9  add     r8w, [rcx+rdx*8+8]
0x140008fbf  mov     [r12+4], r8w
0x140008fc5  mov     rdx, [r9+r10*8]
0x140008fc9  mov     r8, r11; Size
0x140008fcc  mov     rcx, [rsp+98h+var_68]
0x140008fd1  add     rcx, 6
0x140008fd5  add     rcx, rdi; void *
0x140008fd8  mov     rdx, [rdx+80h]; Src
0x140008fdf  call    memmove
0x140008fe4  movzx   eax, word ptr [r12+4]
0x140008fea  shr     rax, 1
0x140008fed  mov     word ptr [r12+rax*2+4], 5Ch ; '\'
0x140008ff5  test    ebp, ebp
0x140008ff7  jz      short loc_140009038
0x140008ff9  mov     rax, [r15+0D0h]
0x140009000  lea     rdx, ds:0[r13*2]
0x140009008  add     rdx, r13
0x14000900b  mov     r9, [rax+10h]
0x14000900f  movzx   eax, word ptr [r9+rdx*8+8]
0x140009015  test    ax, ax
0x140009018  jz      short loc_140009038
0x14000901a  mov     rdx, [r9+rdx*8+10h]; Src
0x14000901f  mov     r8d, eax; Size
0x140009022  movzx   eax, word ptr [r12+2]
0x140009028  shr     rax, 1
0x14000902b  add     rax, 4
0x14000902f  lea     rcx, [r12+rax*2]; void *
0x140009033  call    memmove
0x140009038  mov     edx, [rsp+98h+arg_8]
0x14000903f  mov     r9, [rsi]
0x140009042  mov     rcx, [rsi+8]
0x140009046  mov     eax, ebp
0x140009048  sub     rcx, r9
0x14000904b  inc     ebp
0x14000904d  sar     rcx, 3
0x140009051  movzx   eax, word ptr [rdi+rax*8+2Ch]
0x140009056  add     edx, eax
0x140009058  mov     eax, ebp
0x14000905a  mov     [rsp+98h+arg_8], edx
0x140009061  cmp     rax, rcx
0x140009064  jb      loc_140008F5A
0x14000906a  mov     r15, [rsp+98h+arg_10]
0x140009072  mov     r12, [rsp+98h+arg_18]
0x14000907a  mov     rcx, [r15]; P
0x14000907d  mov     [r15], rdi
0x140009080  test    rcx, rcx
0x140009083  jz      short loc_140009093
0x140009085  xor     edx, edx; Tag
0x140009087  call    cs:__imp_ExFreePoolWithTag
0x14000908e  nop     dword ptr [rax+rax+00h]
0x140009093  mov     [r12], r14d
0x140009097  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000909b  jz      short loc_1400090B3
0x14000909d  test    rbx, rbx
0x1400090a0  jz      short loc_1400090B3
0x1400090a2  xor     edx, edx; Tag
0x1400090a4  mov     rcx, rbx; P
0x1400090a7  call    cs:__imp_ExFreePoolWithTag
0x1400090ae  nop     dword ptr [rax+rax+00h]
0x1400090b3  xor     eax, eax
0x1400090b5  jmp     short loc_140009107
0x1400090b7  mov     rdx, qword ptr [rsp+98h+arg_20]; int
0x1400090bf  lea     rax, aOriginAllocati_53; "ORIGIN: Allocating CIM union config buf"...
0x1400090c6  lea     r9, aUnionfsUnionfs_17; "UnionFs::UnionFsFilter::CreateBootUnion"...
0x1400090cd  mov     [rsp+98h+var_78], rax; char *
0x1400090d2  mov     r8, 7400010F91h; struct UnionFs::StackEventTracer *
0x1400090dc  mov     ecx, 0C000009Ah; this
0x1400090e1  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400090e6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400090ea  jz      short loc_140009102
0x1400090ec  test    rbx, rbx
0x1400090ef  jz      short loc_140009102
0x1400090f1  mov     rcx, rbx; P
0x1400090f4  xor     edx, edx; Tag
0x1400090f6  call    cs:__imp_ExFreePoolWithTag
0x1400090fd  nop     dword ptr [rax+rax+00h]
0x140009102  mov     eax, 0C000009Ah
0x140009107  add     rsp, 58h
0x14000910b  pop     r15
0x14000910d  pop     r14
0x14000910f  pop     r13
0x140009111  pop     r12
0x140009113  pop     rdi
0x140009114  pop     rsi
0x140009115  pop     rbp
0x140009116  pop     rbx
0x140009117  retn
```
