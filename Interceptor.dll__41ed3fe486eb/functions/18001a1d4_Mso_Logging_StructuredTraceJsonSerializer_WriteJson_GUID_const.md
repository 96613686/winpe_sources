# Mso::Logging::StructuredTraceJsonSerializer::WriteJson(_GUID const &)

- ea: `0x18001a1d4`
- end: `0x18001a362`
- name: `?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBU_GUID@@@Z`
- size: `398`
- prototype: `bool __fastcall(Mso::Logging::StructuredTraceJsonSerializer *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180016b70`
- `0x1800181a0`

## callees

- `0x1800045ec`
- `0x180012318`
- `0x180012960`
- `0x18001a1d4`
- `0x1800266e0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001a26e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001a31f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001a26e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001a31f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001a275`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001a329`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001a275`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001a329`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Mso::Logging::StructuredTraceJsonSerializer::WriteJson(
        Mso::Logging::StructuredTraceJsonSerializer *this,
        const struct _GUID *a2)
{
  __m128i si128; // xmm6
  __int64 v4; // rbx
  void *v5; // rcx
  __int64 v6; // rcx
  void **v7; // rdx
  char v8; // bl
  void *v9; // rdx
  void *Block[2]; // [rsp+38h] [rbp-19h] BYREF
  __m128i v12; // [rsp+48h] [rbp-9h]
  _BYTE v13[32]; // [rsp+58h] [rbp+7h] BYREF

  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v12 = si128;
  LOWORD(Block[0]) = 0;
  v4 = OGuid::ToString(v13, a2);
  if ( Block != (void **)v4 )
  {
    if ( v12.m128i_i64[1] > 7uLL )
    {
      v5 = Block[0];
      if ( (unsigned __int64)(2 * v12.m128i_i64[1] + 2) >= 0x1000 )
      {
        v5 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v5 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v5);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v12 = si128;
    LOWORD(Block[0]) = 0;
    *(_OWORD *)Block = *(_OWORD *)v4;
    v12 = *(__m128i *)(v4 + 16);
    *(_QWORD *)(v4 + 16) = 0;
    *(_QWORD *)(v4 + 24) = 7;
    *(_WORD *)v4 = 0;
  }
  std::wstring::_Tidy_deallocate(v13);
  v6 = *((_QWORD *)this + 1);
  if ( !v6 )
    CrashWithRecovery(0x1E3C3840u, 0);
  v7 = Block;
  if ( v12.m128i_i64[1] > 7uLL )
    v7 = (void **)Block[0];
  v8 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v6 + 56LL))(v6, v7);
  if ( v12.m128i_i64[1] > 7uLL )
  {
    v9 = Block[0];
    if ( (unsigned __int64)(2 * v12.m128i_i64[1] + 2) >= 0x1000 )
    {
      v9 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x18001a1d4  mov     rax, rsp
0x18001a1d7  mov     [rax+18h], rbx
0x18001a1db  push    rbp
0x18001a1dc  push    rsi
0x18001a1dd  push    rdi
0x18001a1de  lea     rbp, [rax-5Fh]
0x18001a1e2  sub     rsp, 90h
0x18001a1e9  movaps  xmmword ptr [rax-28h], xmm6
0x18001a1ed  mov     rax, cs:__security_cookie
0x18001a1f4  xor     rax, rsp
0x18001a1f7  mov     [rbp+57h+var_30], rax
0x18001a1fb  mov     rdi, rcx
0x18001a1fe  xorps   xmm0, xmm0
0x18001a201  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18001a205  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18001a20d  movdqu  [rbp+57h+var_60], xmm6
0x18001a212  xor     esi, esi
0x18001a214  mov     word ptr [rbp+57h+Block], si
0x18001a218  lea     rcx, [rbp+57h+var_50]
0x18001a21c  call    ?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; OGuid::ToString(_GUID const &,bool)
0x18001a221  mov     rbx, rax
0x18001a224  lea     rax, [rbp+57h+Block]
0x18001a228  cmp     rax, rbx
0x18001a22b  jz      short loc_18001A2AA
0x18001a22d  mov     rax, qword ptr [rbp+57h+var_60+8]
0x18001a231  cmp     rax, 7
0x18001a235  jbe     short loc_18001A283
0x18001a237  mov     rcx, [rbp+57h+Block]; Block
0x18001a23b  mov     rdx, rcx
0x18001a23e  lea     rax, ds:2[rax*2]
0x18001a246  cmp     rax, 1000h
0x18001a24c  jb      short loc_18001A275
0x18001a24e  mov     rcx, [rcx-8]
0x18001a252  sub     rdx, rcx
0x18001a255  lea     rax, [rdx-8]
0x18001a259  cmp     rax, 1Fh
0x18001a25d  jbe     short loc_18001A275
0x18001a25f  mov     [rsp+0A0h+Reserved], rsi; Reserved
0x18001a264  xor     r9d, r9d; LineNo
0x18001a267  xor     r8d, r8d; FileName
0x18001a26a  xor     edx, edx; FunctionName
0x18001a26c  xor     ecx, ecx; Expression
0x18001a26e  call    cs:__imp__invoke_watson
0x18001a275  call    cs:__imp_free
0x18001a27b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18001a283  movdqu  [rbp+57h+var_60], xmm6
0x18001a288  mov     word ptr [rbp+57h+Block], si
0x18001a28c  movups  xmm0, xmmword ptr [rbx]
0x18001a28f  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18001a293  movups  xmm1, xmmword ptr [rbx+10h]
0x18001a297  movups  [rbp+57h+var_60], xmm1
0x18001a29b  mov     [rbx+10h], rsi
0x18001a29f  mov     qword ptr [rbx+18h], 7
0x18001a2a7  mov     [rbx], si
0x18001a2aa  lea     rcx, [rbp+57h+var_50]
0x18001a2ae  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a2b3  mov     rcx, [rdi+8]
0x18001a2b7  test    rcx, rcx
0x18001a2ba  jz      loc_18001A355
0x18001a2c0  mov     rax, [rcx]
0x18001a2c3  lea     rdx, [rbp+57h+Block]
0x18001a2c7  cmp     qword ptr [rbp+57h+var_60+8], 7
0x18001a2cc  cmova   rdx, [rbp+57h+Block]
0x18001a2d1  mov     rax, [rax+38h]
0x18001a2d5  call    cs:__guard_dispatch_icall_fptr
0x18001a2db  mov     bl, al
0x18001a2dd  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x18001a2e1  cmp     rcx, 7
0x18001a2e5  jbe     short loc_18001A32F
0x18001a2e7  mov     rdx, [rbp+57h+Block]
0x18001a2eb  mov     rax, rdx
0x18001a2ee  lea     rcx, ds:2[rcx*2]
0x18001a2f6  cmp     rcx, 1000h
0x18001a2fd  jb      short loc_18001A326
0x18001a2ff  mov     rdx, [rdx-8]
0x18001a303  sub     rax, rdx
0x18001a306  add     rax, 0FFFFFFFFFFFFFFF8h
0x18001a30a  cmp     rax, 1Fh
0x18001a30e  jbe     short loc_18001A326
0x18001a310  mov     [rsp+0A0h+Reserved], rsi; Reserved
0x18001a315  xor     r9d, r9d; LineNo
0x18001a318  xor     r8d, r8d; FileName
0x18001a31b  xor     edx, edx; FunctionName
0x18001a31d  xor     ecx, ecx; Expression
0x18001a31f  call    cs:__imp__invoke_watson
0x18001a326  mov     rcx, rdx; Block
0x18001a329  call    cs:__imp_free
0x18001a32f  mov     al, bl
0x18001a331  mov     rcx, [rbp+57h+var_30]
0x18001a335  xor     rcx, rsp; StackCookie
0x18001a338  call    __security_check_cookie
0x18001a33d  lea     r11, [rsp+0A0h+var_10]
0x18001a345  mov     rbx, [r11+30h]
0x18001a349  movaps  xmm6, xmmword ptr [r11-10h]
0x18001a34e  mov     rsp, r11
0x18001a351  pop     rdi
0x18001a352  pop     rsi
0x18001a353  pop     rbp
0x18001a354  retn
0x18001a355  xor     edx, edx; struct CrashContext *
0x18001a357  mov     ecx, 1E3C3840h; unsigned int
0x18001a35c  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
