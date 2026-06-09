# Windows::Internal::Storage::Cloud::CloudStoreCache::SaveToDefaultLocalStorage(ushort const *,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreMetadata *,uchar *,ulong)

- ea: `0x18007e570`
- end: `0x18007e6cf`
- name: `?SaveToDefaultLocalStorage@CloudStoreCache@Cloud@Storage@Internal@Windows@@AEAAJPEBG00PEAVCloudStoreMetadata@2345@PEAEK@Z`
- size: `351`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::CloudStoreCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *, unsigned __int8 *Src, size_t Size)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007e130`

## callees

- `0x18007e570`
- `0x18007e75c`
- `0x1800c8458`
- `0x180123882`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e5dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e63f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e6a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e5dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e63f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e6a4`

## string_xrefs

- `0x18007e67f`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStoreCache::SaveToDefaultLocalStorage(
        Windows::Internal::Storage::Cloud::CloudStoreCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *a5,
        unsigned __int8 *Src,
        size_t Size)
{
  LPVOID *v11; // r10
  char v12; // r11
  void *v13; // r9
  int v14; // ebx
  void *v15; // rcx
  void *v16; // rcx
  __int64 v18; // rdx
  void *v19; // rcx
  int v20; // [rsp+20h] [rbp-58h]
  LPVOID pv[2]; // [rsp+40h] [rbp-38h] BYREF
  LPVOID *v22; // [rsp+50h] [rbp-28h]
  void *v23; // [rsp+58h] [rbp-20h] BYREF
  char v24; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  pv[0] = 0;
  v11 = pv;
  v22 = pv;
  v12 = 1;
  v24 = 1;
  v13 = 0;
  v23 = 0;
  if ( is_mul_ok((unsigned int)(Size + 16), 1u) )
  {
    v14 = CTCoAllocPolicy::Alloc((void *)(unsigned int)(Size + 16), 1u, (unsigned int)(Size + 16), &v23);
    v12 = v24;
    v13 = v23;
    v11 = v22;
  }
  else
  {
    v14 = -2147024362;
  }
  if ( v12 )
  {
    v15 = *v11;
    *v11 = v13;
    if ( v15 )
      CoTaskMemFree(v15);
  }
  if ( v14 < 0 )
  {
    v18 = 393;
  }
  else
  {
    *(_OWORD *)pv[0] = *(_OWORD *)a5;
    if ( (_DWORD)Size )
      memcpy_0((char *)pv[0] + 16, Src, (unsigned int)Size);
    v20 = (int)pv[0];
    v14 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(**((_QWORD **)this + 2) + 40LL))(
            *((_QWORD *)this + 2),
            a2,
            a3,
            a4);
    if ( v14 >= 0 )
    {
      v16 = pv[0];
      pv[0] = 0;
      if ( v16 )
        CoTaskMemFree(v16);
      return 0;
    }
    v18 = 401;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
    (const char *)(unsigned int)v14,
    v20);
  v19 = pv[0];
  pv[0] = 0;
  if ( v19 )
    CoTaskMemFree(v19);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18007e570  push    rbp
0x18007e572  push    rbx
0x18007e573  push    rsi
0x18007e574  push    rdi
0x18007e575  push    r12
0x18007e577  push    r13
0x18007e579  push    r14
0x18007e57b  push    r15
0x18007e57d  mov     rbp, rsp
0x18007e580  sub     rsp, 78h
0x18007e584  mov     r14, r9
0x18007e587  mov     r15, r8
0x18007e58a  mov     r12, rdx
0x18007e58d  mov     r13, rcx
0x18007e590  mov     edi, dword ptr [rbp+Size]
0x18007e593  lea     esi, [rdi+10h]
0x18007e596  mov     [rbp+pv], 0
0x18007e59e  lea     r10, [rbp+pv]
0x18007e5a2  mov     [rbp+var_28], r10
0x18007e5a6  mov     r11d, 1
0x18007e5ac  mov     [rbp+var_18], r11b
0x18007e5b0  xor     r9d, r9d
0x18007e5b3  mov     [rbp+var_20], r9
0x18007e5b7  mov     ecx, esi; void *
0x18007e5b9  mov     eax, r11d
0x18007e5bc  mul     rcx
0x18007e5bf  test    rdx, rdx
0x18007e5c2  jz      loc_18007E658
0x18007e5c8  mov     ebx, 80070216h
0x18007e5cd  test    r11b, r11b
0x18007e5d0  jz      short loc_18007E5E3
0x18007e5d2  mov     rcx, [r10]; pv
0x18007e5d5  mov     [r10], r9
0x18007e5d8  test    rcx, rcx
0x18007e5db  jz      short loc_18007E5E3
0x18007e5dd  call    cs:__imp_CoTaskMemFree
0x18007e5e3  test    ebx, ebx
0x18007e5e5  js      loc_18007E6AE
0x18007e5eb  mov     rax, [rbp+arg_20]
0x18007e5ef  movups  xmm0, xmmword ptr [rax]
0x18007e5f2  mov     rax, [rbp+pv]
0x18007e5f6  movdqu  xmmword ptr [rax], xmm0
0x18007e5fa  test    edi, edi
0x18007e5fc  jnz     loc_18007E6B5
0x18007e602  mov     rcx, [r13+10h]
0x18007e606  mov     rdx, [rbp+pv]
0x18007e60a  mov     rax, [rcx]
0x18007e60d  mov     [rsp+78h+var_50], esi
0x18007e611  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18007e616  mov     r9, r14
0x18007e619  mov     r8, r15
0x18007e61c  mov     rdx, r12
0x18007e61f  mov     rax, [rax+28h]
0x18007e623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e628  mov     ebx, eax
0x18007e62a  test    eax, eax
0x18007e62c  js      short loc_18007E67A
0x18007e62e  mov     rcx, [rbp+pv]; pv
0x18007e632  mov     [rbp+pv], 0
0x18007e63a  test    rcx, rcx
0x18007e63d  jz      short loc_18007E645
0x18007e63f  call    cs:__imp_CoTaskMemFree
0x18007e645  xor     eax, eax
0x18007e647  add     rsp, 78h
0x18007e64b  pop     r15
0x18007e64d  pop     r14
0x18007e64f  pop     r13
0x18007e651  pop     r12
0x18007e653  pop     rdi
0x18007e654  pop     rsi
0x18007e655  pop     rbx
0x18007e656  pop     rbp
0x18007e657  retn
0x18007e658  lea     r9, [rbp+var_20]; void **
0x18007e65c  mov     r8, rax; unsigned __int64
0x18007e65f  mov     edx, r11d; unsigned int
0x18007e662  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18007e667  mov     ebx, eax
0x18007e669  mov     r11b, [rbp+var_18]
0x18007e66d  mov     r9, [rbp+var_20]
0x18007e671  mov     r10, [rbp+var_28]
0x18007e675  jmp     loc_18007E5CD
0x18007e67a  mov     edx, 191h; void *
0x18007e67f  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007e686  mov     r9d, ebx; char *
0x18007e689  mov     rcx, [rbp+40h]; this
0x18007e68d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e692  nop
0x18007e693  mov     rcx, [rbp+pv]; pv
0x18007e697  mov     [rbp+pv], 0
0x18007e69f  test    rcx, rcx
0x18007e6a2  jz      short loc_18007E6AA
0x18007e6a4  call    cs:__imp_CoTaskMemFree
0x18007e6aa  mov     eax, ebx
0x18007e6ac  jmp     short loc_18007E647
0x18007e6ae  mov     edx, 189h
0x18007e6b3  jmp     short loc_18007E67F
0x18007e6b5  mov     r8, rdi; Size
0x18007e6b8  mov     rcx, [rbp+pv]
0x18007e6bc  add     rcx, 10h; void *
0x18007e6c0  mov     rdx, [rbp+Src]; Src
0x18007e6c4  call    memcpy_0
0x18007e6c9  jmp     loc_18007E602
```
