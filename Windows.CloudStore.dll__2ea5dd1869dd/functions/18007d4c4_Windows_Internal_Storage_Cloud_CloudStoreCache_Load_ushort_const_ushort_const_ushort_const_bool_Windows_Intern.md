# Windows::Internal::Storage::Cloud::CloudStoreCache::Load(ushort const *,ushort const *,ushort const *,bool,Windows::Internal::Storage::Cloud::CloudStoreMetadata *,uchar * *,ulong *)

- ea: `0x18007d4c4`
- end: `0x18007d95a`
- name: `?Load@CloudStoreCache@Cloud@Storage@Internal@Windows@@QEAAJPEBG00_NPEAVCloudStoreMetadata@2345@PEAPEAEPEAK@Z`
- size: `1174`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::CloudStoreCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, bool, struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *, unsigned __int8 **, unsigned int *)`
- caller_count: `4`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007d420`
- `0x1800c7440`
- `0x1800c78f0`
- `0x1801a93a4`

## callees

- `0x18005b770`
- `0x18007d4c4`
- `0x18007e064`
- `0x18007e0c8`
- `0x18007e0f8`
- `0x18007e75c`
- `0x180091b04`
- `0x1800c8458`
- `0x1800e93e0`
- `0x180120c94`
- `0x180123882`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d550`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d61d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d6a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d6c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d787`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d7e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d7fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d550`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d61d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d6a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d6c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d787`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d7e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d7fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d5e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d5e2`

## string_xrefs

- `0x18007d864`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstoremetadata.cpp`
- `0x18007d6e1`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x18007d7c9`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x18007d811`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x18007d87e`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x18007d948`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStoreCache::Load(
        Windows::Internal::Storage::Cloud::CloudStoreCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5,
        struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  __int64 *v8; // rcx
  __int64 v9; // rax
  void *v10; // rcx
  int v11; // ebx
  void *v12; // rcx
  void *v14; // rcx
  int v15; // [rsp+20h] [rbp-58h]
  LPVOID v16; // [rsp+48h] [rbp-30h] BYREF
  LPVOID *v17; // [rsp+58h] [rbp-20h]
  void *v18; // [rsp+60h] [rbp-18h] BYREF
  char v19; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  *a7 = 0;
  *a8 = 0;
  v16 = 0;
  v8 = (__int64 *)*((_QWORD *)this + 2);
  v9 = *v8;
  v17 = &v16;
  v18 = 0;
  v19 = 1;
  v11 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *))(v9 + 32))(v8, a2);
  if ( v19 )
  {
    v10 = *v17;
    *v17 = v18;
    if ( v10 )
      CoTaskMemFree(v10);
  }
  if ( v11 == -2147024894 )
  {
    v12 = v16;
    v16 = 0;
LABEL_8:
    if ( v12 )
      CoTaskMemFree(v12);
    return 2147942402LL;
  }
  if ( v11 >= 0 )
  {
    *(_DWORD *)a6 = 2;
    *(_QWORD *)((char *)a6 + 4) = 0;
    *((_DWORD *)a6 + 3) = 0;
    if ( (Microsoft_Windows_CloudStoreEnableBits & 1) != 0 )
      McTemplateU0sq_EventWriteTransfer(v10, HealingStore, "Unavailable", 2147942487LL);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstoremetadata.cpp",
      (const char *)0x80070002LL,
      (int)&v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
      (const char *)0x80070002LL,
      v15);
    v12 = v16;
    v16 = 0;
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA9,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
    (const char *)(unsigned int)v11,
    (int)&v18);
  v14 = v16;
  v16 = 0;
  if ( v14 )
    CoTaskMemFree(v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18007d4c4  push    rbp
0x18007d4c6  push    rbx
0x18007d4c7  push    rsi
0x18007d4c8  push    rdi
0x18007d4c9  push    r12
0x18007d4cb  push    r13
0x18007d4cd  push    r14
0x18007d4cf  push    r15
0x18007d4d1  mov     rbp, rsp
0x18007d4d4  sub     rsp, 78h
0x18007d4d8  mov     r14, r9
0x18007d4db  mov     r15, r8
0x18007d4de  mov     r12, rdx
0x18007d4e1  mov     r13, rcx
0x18007d4e4  xor     esi, esi
0x18007d4e6  mov     rax, [rbp+arg_30]
0x18007d4ea  mov     [rax], rsi
0x18007d4ed  mov     rax, [rbp+arg_38]
0x18007d4f4  mov     [rax], esi
0x18007d4f6  mov     [rbp+arg_0], esi
0x18007d4f9  mov     [rbp+var_30], rsi
0x18007d4fd  mov     rcx, [rcx+10h]
0x18007d501  mov     rax, [rcx]
0x18007d504  lea     rdx, [rbp+var_30]
0x18007d508  mov     [rbp+var_20], rdx
0x18007d50c  mov     [rbp+var_18], rsi
0x18007d510  lea     edi, [rsi+1]
0x18007d513  mov     [rbp+var_10], dil
0x18007d517  lea     rdx, [rbp+arg_0]
0x18007d51b  mov     [rsp+78h+var_50], rdx
0x18007d520  lea     rdx, [rbp+var_18]
0x18007d524  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18007d529  mov     rdx, r12
0x18007d52c  mov     rax, [rax+20h]
0x18007d530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d535  mov     ebx, eax
0x18007d537  cmp     [rbp+var_10], sil
0x18007d53b  jz      short loc_18007D556
0x18007d53d  mov     r8, [rbp+var_20]
0x18007d541  mov     rcx, [r8]; pv
0x18007d544  mov     rdx, [rbp+var_18]
0x18007d548  mov     [r8], rdx
0x18007d54b  test    rcx, rcx
0x18007d54e  jz      short loc_18007D556
0x18007d550  call    cs:__imp_CoTaskMemFree
0x18007d556  cmp     ebx, 80070002h
0x18007d55c  jz      loc_18007D6BC
0x18007d562  test    ebx, ebx
0x18007d564  js      loc_18007D80A
0x18007d56a  mov     rax, [rbp+arg_28]
0x18007d56e  mov     dword ptr [rax], 2
0x18007d574  mov     [rax+4], rsi
0x18007d578  mov     [rax+0Ch], esi
0x18007d57b  mov     esi, [rbp+arg_0]
0x18007d57e  cmp     esi, 10h
0x18007d581  jb      loc_18007D830
0x18007d587  mov     rdx, [rbp+var_30]
0x18007d58b  cmp     dword ptr [rdx], 2
0x18007d58e  jnz     loc_18007D859
0x18007d594  movups  xmm0, xmmword ptr [rdx]
0x18007d597  movdqu  xmmword ptr [rax], xmm0
0x18007d59b  add     esi, 0FFFFFFF0h
0x18007d59e  mov     [rbp+pv], 0
0x18007d5a6  cmp     [rax+0Ch], edi
0x18007d5a9  jz      loc_18007D8A1
0x18007d5af  mov     r15d, esi
0x18007d5b2  xor     r13d, r13d
0x18007d5b5  test    esi, esi
0x18007d5b7  jz      loc_18007D66E
0x18007d5bd  lea     rax, [rbp+pv]
0x18007d5c1  mov     [rbp+var_20], rax
0x18007d5c5  mov     [rbp+var_10], dil
0x18007d5c9  mov     ebx, r13d
0x18007d5cc  mov     rax, rdi
0x18007d5cf  mul     r15
0x18007d5d2  test    rdx, rdx
0x18007d5d5  jz      short loc_18007D5DF
0x18007d5d7  mov     r14d, 80070216h
0x18007d5dd  jmp     short loc_18007D610
0x18007d5df  mov     rcx, rax; cb
0x18007d5e2  call    cs:__imp_CoTaskMemAlloc
0x18007d5e8  mov     rbx, rax
0x18007d5eb  mov     [rbp+var_18], rax
0x18007d5ef  test    rax, rax
0x18007d5f2  jz      loc_18007D6D6
0x18007d5f8  mov     rcx, rax; void *
0x18007d5fb  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18007d600  mov     r8, rax; Size
0x18007d603  xor     edx, edx; Val
0x18007d605  mov     rcx, rbx; void *
0x18007d608  call    memset_0
0x18007d60d  mov     r14d, r13d
0x18007d610  mov     rcx, [rbp+pv]; pv
0x18007d614  mov     [rbp+pv], rbx
0x18007d618  test    rcx, rcx
0x18007d61b  jz      short loc_18007D627
0x18007d61d  call    cs:__imp_CoTaskMemFree
0x18007d623  mov     rbx, [rbp+pv]
0x18007d627  test    r14d, r14d
0x18007d62a  js      loc_18007D7C2
0x18007d630  mov     rdx, [rbp+var_30]
0x18007d634  add     rdx, 10h; Src
0x18007d638  mov     r8, r15; Size
0x18007d63b  mov     rcx, rbx; void *
0x18007d63e  call    memcpy_0
0x18007d643  test    esi, esi
0x18007d645  jz      short loc_18007D66E
0x18007d647  cmp     r15, 4
0x18007d64b  jb      short loc_18007D671
0x18007d64d  mov     rdx, r13
0x18007d650  cmp     rdx, 4
0x18007d654  jnb     short loc_18007D66E
0x18007d656  lea     rcx, qword_18022A7F0
0x18007d65d  mov     cl, [rdx+rcx]
0x18007d660  mov     rax, [rbp+pv]
0x18007d664  cmp     [rdx+rax], cl
0x18007d667  jnz     short loc_18007D671
0x18007d669  add     rdx, rdi
0x18007d66c  jmp     short loc_18007D650
0x18007d66e  mov     dil, r13b
0x18007d671  mov     rcx, [rbp+40h]; this
0x18007d675  test    dil, dil
0x18007d678  jnz     loc_18007D93D
0x18007d67e  mov     rax, [rbp+arg_38]
0x18007d685  mov     [rax], esi
0x18007d687  mov     rax, [rbp+pv]
0x18007d68b  mov     rcx, [rbp+arg_30]
0x18007d68f  mov     [rcx], rax
0x18007d692  mov     [rbp+pv], r13
0x18007d696  mov     rcx, [rbp+var_30]; pv
0x18007d69a  mov     [rbp+var_30], r13
0x18007d69e  test    rcx, rcx
0x18007d6a1  jz      short loc_18007D6A9
0x18007d6a3  call    cs:__imp_CoTaskMemFree
0x18007d6a9  xor     eax, eax
0x18007d6ab  add     rsp, 78h
0x18007d6af  pop     r15
0x18007d6b1  pop     r14
0x18007d6b3  pop     r13
0x18007d6b5  pop     r12
0x18007d6b7  pop     rdi
0x18007d6b8  pop     rsi
0x18007d6b9  pop     rbx
0x18007d6ba  pop     rbp
0x18007d6bb  retn
0x18007d6bc  mov     rcx, [rbp+var_30]; pv
0x18007d6c0  mov     [rbp+var_30], rsi
0x18007d6c4  test    rcx, rcx
0x18007d6c7  jz      short loc_18007D6CF
0x18007d6c9  call    cs:__imp_CoTaskMemFree
0x18007d6cf  mov     eax, 80070002h
0x18007d6d4  jmp     short loc_18007D6AB
0x18007d6d6  mov     r14d, 8007000Eh
0x18007d6dc  jmp     loc_18007D610
0x18007d6e1  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007d6e8  mov     r9d, ebx; char *
0x18007d6eb  mov     rcx, [rbp+40h]; this
0x18007d6ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d6f4  nop
0x18007d6f5  mov     rcx, [rbp+pv]; pv
0x18007d6f9  mov     [rbp+pv], r13
0x18007d6fd  test    rcx, rcx
0x18007d700  jz      short loc_18007D709
0x18007d702  call    cs:__imp_CoTaskMemFree
0x18007d708  nop
0x18007d709  mov     rcx, [rbp+var_30]; pv
0x18007d70d  mov     [rbp+var_30], r13
0x18007d711  test    rcx, rcx
0x18007d714  jz      short loc_18007D71C
0x18007d716  call    cs:__imp_CoTaskMemFree
0x18007d71c  mov     eax, ebx
0x18007d71e  jmp     short loc_18007D6AB
0x18007d720  lea     rax, [rbp+pv]
0x18007d724  mov     [rbp+var_20], rax
0x18007d728  mov     [rbp+var_10], dil
0x18007d72c  xor     r13d, r13d
0x18007d72f  mov     [rbp+var_18], r13
0x18007d733  mov     [rbp+var_38], r13
0x18007d737  mov     r14d, esi
0x18007d73a  lea     r8, [rbp+var_38]; unsigned __int64 *
0x18007d73e  mov     rdx, rdi; unsigned __int64
0x18007d741  mov     ecx, esi; unsigned __int64
0x18007d743  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007d748  mov     ebx, eax
0x18007d74a  test    eax, eax
0x18007d74c  js      short loc_18007D75F
0x18007d74e  lea     r9, [rbp+var_18]; void **
0x18007d752  mov     r8, [rbp+var_38]; unsigned __int64
0x18007d756  mov     edx, edi; unsigned int
0x18007d758  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18007d75d  mov     ebx, eax
0x18007d75f  lea     rcx, [rbp+var_20]
0x18007d763  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007d768  test    ebx, ebx
0x18007d76a  jns     loc_18007D922
0x18007d770  mov     edx, 0BDh; void *
0x18007d775  jmp     loc_18007D6E1
0x18007d77a  mov     rcx, [rbp+pv]; pv
0x18007d77e  mov     [rbp+pv], r13
0x18007d782  test    rcx, rcx
0x18007d785  jz      short loc_18007D78E
0x18007d787  call    cs:__imp_CoTaskMemFree
0x18007d78d  nop
0x18007d78e  mov     rcx, [rbp+var_30]
0x18007d792  mov     [rbp+var_30], r13
0x18007d796  jmp     loc_18007D6C4
0x18007d79b  mov     esi, dword ptr [rbp+var_38]
0x18007d79e  mov     r10, [rbp+40h]
0x18007d7a2  mov     edx, esi; unsigned __int64
0x18007d7a4  mov     rcx, [rbp+pv]; unsigned __int8 *
0x18007d7a8  call    ?IsValidBlob@@YA_NPEBE_K@Z; IsValidBlob(uchar const *,unsigned __int64)
0x18007d7ad  test    al, al
0x18007d7af  jnz     loc_18007D67E
0x18007d7b5  mov     edx, 0B8h
0x18007d7ba  mov     rcx, r10
0x18007d7bd  jmp     loc_18007D942
0x18007d7c2  mov     rcx, [rbp+40h]; this
0x18007d7c6  mov     r9d, r14d; char *
0x18007d7c9  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007d7d0  mov     edx, 0C9h; void *
0x18007d7d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d7da  nop
0x18007d7db  mov     rcx, [rbp+pv]; pv
0x18007d7df  mov     [rbp+pv], r13
0x18007d7e3  test    rcx, rcx
0x18007d7e6  jz      short loc_18007D7EF
0x18007d7e8  call    cs:__imp_CoTaskMemFree
0x18007d7ee  nop
0x18007d7ef  mov     rcx, [rbp+var_30]; pv
0x18007d7f3  mov     [rbp+var_30], r13
0x18007d7f7  test    rcx, rcx
0x18007d7fa  jz      short loc_18007D802
0x18007d7fc  call    cs:__imp_CoTaskMemFree
0x18007d802  mov     eax, r14d
0x18007d805  jmp     loc_18007D6AB
0x18007d80a  mov     rcx, [rbp+40h]; this
0x18007d80e  mov     r9d, ebx; char *
0x18007d811  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007d818  mov     edx, 0A9h; void *
0x18007d81d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d822  nop
0x18007d823  mov     rcx, [rbp+var_30]
0x18007d827  mov     [rbp+var_30], rsi
0x18007d82b  jmp     loc_18007D711
0x18007d830  test    cs:Microsoft_Windows_CloudStoreEnableBits, dil
0x18007d837  jz      short loc_18007D852
0x18007d839  mov     r9d, 80070057h
0x18007d83f  lea     r8, aUnavailable; "Unavailable"
0x18007d846  lea     rdx, HealingStore
0x18007d84d  call    McTemplateU0sq_EventWriteTransfer
0x18007d852  mov     edx, 46h ; 'F'
0x18007d857  jmp     short loc_18007D85E
0x18007d859  mov     edx, 52h ; 'R'; void *
0x18007d85e  mov     r9d, 80070002h; char *
0x18007d864  lea     r8, aOnecoreuapShel_90; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007d86b  mov     rcx, [rbp+40h]; this
0x18007d86f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d874  mov     rcx, [rbp+40h]; this
0x18007d878  mov     r9d, 80070002h; char *
0x18007d87e  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007d885  mov     edx, 0ABh; void *
0x18007d88a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d88f  nop
0x18007d890  mov     rcx, [rbp+var_30]
0x18007d894  mov     [rbp+var_30], 0
0x18007d89c  jmp     loc_18007D6C4
0x18007d8a1  cmp     [rbp+arg_20], 0
0x18007d8a5  jz      loc_18007D720
0x18007d8ab  mov     dword ptr [rbp+var_38], 0
0x18007d8b2  mov     rcx, [r13+18h]
0x18007d8b6  mov     rax, [rcx]
0x18007d8b9  lea     r8, [rbp+pv]
0x18007d8bd  mov     [rbp+var_20], r8
0x18007d8c1  xor     r13d, r13d
0x18007d8c4  mov     [rbp+var_18], r13
0x18007d8c8  mov     [rbp+var_10], dil
0x18007d8cc  add     rdx, 10h
0x18007d8d0  lea     r8, [rbp+var_38]
0x18007d8d4  mov     [rsp+78h+var_48], r8
0x18007d8d9  lea     r8, [rbp+var_18]
0x18007d8dd  mov     [rsp+78h+var_50], r8
0x18007d8e2  mov     qword ptr [rsp+78h+var_58], rdx
0x18007d8e7  mov     r9, r14
0x18007d8ea  mov     r8, r15
0x18007d8ed  mov     rdx, r12
0x18007d8f0  mov     rax, [rax+20h]
0x18007d8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8f9  mov     ebx, eax
0x18007d8fb  lea     rcx, [rbp+var_20]
0x18007d8ff  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007d904  cmp     ebx, 80070002h
0x18007d90a  jz      loc_18007D77A
0x18007d910  test    ebx, ebx
0x18007d912  jns     loc_18007D79B
0x18007d918  mov     edx, 0B5h
0x18007d91d  jmp     loc_18007D6E1
0x18007d922  mov     rdx, [rbp+var_30]
0x18007d926  add     rdx, 10h; Src
0x18007d92a  mov     r8, r14; Size
0x18007d92d  mov     rcx, [rbp+pv]; void *
  ... truncated ...
```
