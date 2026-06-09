# FreeObject(tagUpdateDeploymentReportingData *)

- ea: `0x18000c30c`
- end: `0x18000c5d8`
- name: `?FreeObject@@YAXPEAUtagUpdateDeploymentReportingData@@@Z`
- size: `716`
- prototype: `void __fastcall(struct tagUpdateDeploymentReportingData *)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c5e0`
- `0x180014138`
- `0x18001d408`
- `0x1800330b8`
- `0x180036df0`
- `0x180036e18`

## callees

- `0x18000c30c`
- `0x18000cd48`
- `0x18000dce4`
- `0x18000de94`
- `0x180061d54`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c53b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c55e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c574`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c53b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c55e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c574`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c583`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c331`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c34a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c358`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c366`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c377`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c3af`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c3fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c40e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c422`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c449`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c45d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c471`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c331`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c34a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c358`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c366`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c377`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c3af`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c3fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c40e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c422`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c449`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c45d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c471`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
void __fastcall FreeObject(struct tagUpdateDeploymentReportingData *a1)
{
  void *v2; // rcx
  unsigned __int64 v3; // rcx
  wchar_t **v4; // rdx
  unsigned int v5; // esi
  void *v6; // rcx
  unsigned int v7; // esi
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  if ( a1 )
  {
    SysFreeString(*(BSTR *)a1);
    *(_QWORD *)a1 = 0;
    SafeBstrArrayFree(*((unsigned int *)a1 + 6), *((wchar_t ***)a1 + 4));
    SysFreeString(*((BSTR *)a1 + 9));
    *((_QWORD *)a1 + 9) = 0;
    SysFreeString(*((BSTR *)a1 + 10));
    *((_QWORD *)a1 + 10) = 0;
    SysFreeString(*((BSTR *)a1 + 13));
    *((_QWORD *)a1 + 13) = 0;
    SysFreeString(*((BSTR *)a1 + 18));
    *((_QWORD *)a1 + 18) = 0;
    SafeBstrArrayFree(*((unsigned int *)a1 + 40), *((wchar_t ***)a1 + 21));
    SafeBstrArrayFree(*((unsigned int *)a1 + 44), *((wchar_t ***)a1 + 23));
    SysFreeString(*((BSTR *)a1 + 24));
    *((_QWORD *)a1 + 24) = 0;
    SafeBstrArrayFree(*((unsigned int *)a1 + 51), *((wchar_t ***)a1 + 26));
    SafeBstrArrayFree(*((unsigned int *)a1 + 54), *((wchar_t ***)a1 + 28));
    SusFree(*((void **)a1 + 36));
    *((_QWORD *)a1 + 36) = 0;
    SysFreeString(*((BSTR *)a1 + 40));
    *((_QWORD *)a1 + 40) = 0;
    SysFreeString(*((BSTR *)a1 + 41));
    *((_QWORD *)a1 + 41) = 0;
    SysFreeString(*((BSTR *)a1 + 42));
    *((_QWORD *)a1 + 42) = 0;
    SusFree(*((void **)a1 + 43));
    *((_QWORD *)a1 + 43) = 0;
    SysFreeString(*((BSTR *)a1 + 44));
    *((_QWORD *)a1 + 44) = 0;
    SysFreeString(*((BSTR *)a1 + 51));
    *((_QWORD *)a1 + 51) = 0;
    SysFreeString(*((BSTR *)a1 + 52));
    *((_QWORD *)a1 + 52) = 0;
    operator delete(*((void **)a1 + 54), (const struct std::nothrow_t *)1);
    v2 = (void *)*((_QWORD *)a1 + 55);
    *((_QWORD *)a1 + 54) = 0;
    operator delete(v2, (const struct std::nothrow_t *)1);
    v3 = *((unsigned int *)a1 + 113);
    v4 = (wchar_t **)*((_QWORD *)a1 + 57);
    *((_QWORD *)a1 + 55) = 0;
    SafeBstrArrayFree(v3, v4);
    SafeBstrArrayFree(*((unsigned int *)a1 + 113), *((wchar_t ***)a1 + 58));
    SafeBstrArrayFree(*((unsigned int *)a1 + 120), *((wchar_t ***)a1 + 61));
    SusFree(*((void **)a1 + 62));
    *((_QWORD *)a1 + 62) = 0;
    SusFree(*((void **)a1 + 63));
    *((_QWORD *)a1 + 63) = 0;
    SusFree(*((void **)a1 + 66));
    *((_QWORD *)a1 + 66) = 0;
    if ( a1 != (struct tagUpdateDeploymentReportingData *)-544LL )
    {
      if ( *((_DWORD *)a1 + 141) )
      {
        v5 = 0;
        do
        {
          v6 = *(void **)(*((_QWORD *)a1 + 71) + 8LL * v5);
          if ( v6 )
            CoTaskMemFree(v6);
          ++v5;
        }
        while ( v5 < *((_DWORD *)a1 + 141) );
      }
      if ( *((_DWORD *)a1 + 144) )
      {
        v7 = 0;
        do
        {
          v8 = *(void **)(*((_QWORD *)a1 + 73) + 8LL * v7);
          if ( v8 )
            CoTaskMemFree(v8);
          ++v7;
        }
        while ( v7 < *((_DWORD *)a1 + 144) );
      }
      v9 = (void *)*((_QWORD *)a1 + 71);
      if ( v9 )
        CoTaskMemFree(v9);
      v10 = (void *)*((_QWORD *)a1 + 73);
      if ( v10 )
        CoTaskMemFree(v10);
      *((_OWORD *)a1 + 34) = 0;
      *((_OWORD *)a1 + 35) = 0;
      *((_OWORD *)a1 + 36) = 0;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
      SusFree(*((void **)a1 + 76));
    memset(a1, 0, 0x288u);
  }
}

```

## disassembly

```asm
0x18000c30c  test    rcx, rcx
0x18000c30f  jz      locret_18000C5D7
0x18000c315  mov     [rsp+arg_0], rbx
0x18000c31a  mov     [rsp+arg_8], rbp
0x18000c31f  mov     [rsp+arg_10], rsi
0x18000c324  push    rdi
0x18000c325  sub     rsp, 20h
0x18000c329  mov     rdi, rcx
0x18000c32c  xor     ebp, ebp
0x18000c32e  mov     rcx, [rcx]; bstrString
0x18000c331  call    cs:__imp_SysFreeString
0x18000c337  mov     [rdi], rbp
0x18000c33a  mov     ecx, [rdi+18h]; unsigned __int64
0x18000c33d  mov     rdx, [rdi+20h]; wchar_t **
0x18000c341  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18000c346  mov     rcx, [rdi+48h]; bstrString
0x18000c34a  call    cs:__imp_SysFreeString
0x18000c350  mov     [rdi+48h], rbp
0x18000c354  mov     rcx, [rdi+50h]; bstrString
0x18000c358  call    cs:__imp_SysFreeString
0x18000c35e  mov     [rdi+50h], rbp
0x18000c362  mov     rcx, [rdi+68h]; bstrString
0x18000c366  call    cs:__imp_SysFreeString
0x18000c36c  mov     [rdi+68h], rbp
0x18000c370  mov     rcx, [rdi+90h]; bstrString
0x18000c377  call    cs:__imp_SysFreeString
0x18000c37d  mov     [rdi+90h], rbp
0x18000c384  mov     ecx, [rdi+0A0h]; unsigned __int64
0x18000c38a  mov     rdx, [rdi+0A8h]; wchar_t **
0x18000c391  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18000c396  mov     ecx, [rdi+0B0h]; unsigned __int64
0x18000c39c  mov     rdx, [rdi+0B8h]; wchar_t **
0x18000c3a3  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18000c3a8  mov     rcx, [rdi+0C0h]; bstrString
0x18000c3af  call    cs:__imp_SysFreeString
0x18000c3b5  mov     [rdi+0C0h], rbp
0x18000c3bc  mov     ecx, [rdi+0CCh]; unsigned __int64
0x18000c3c2  mov     rdx, [rdi+0D0h]; wchar_t **
0x18000c3c9  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18000c3ce  mov     ecx, [rdi+0D8h]; unsigned __int64
0x18000c3d4  mov     rdx, [rdi+0E0h]; wchar_t **
0x18000c3db  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18000c3e0  mov     rcx, [rdi+120h]; lpMem
0x18000c3e7  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000c3ec  mov     [rdi+120h], rbp
0x18000c3f3  mov     rcx, [rdi+140h]; bstrString
0x18000c3fa  call    cs:__imp_SysFreeString
0x18000c400  mov     [rdi+140h], rbp
0x18000c407  mov     rcx, [rdi+148h]; bstrString
0x18000c40e  call    cs:__imp_SysFreeString
0x18000c414  mov     [rdi+148h], rbp
0x18000c41b  mov     rcx, [rdi+150h]; bstrString
0x18000c422  call    cs:__imp_SysFreeString
0x18000c428  mov     [rdi+150h], rbp
0x18000c42f  mov     rcx, [rdi+158h]; lpMem
0x18000c436  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000c43b  mov     [rdi+158h], rbp
0x18000c442  mov     rcx, [rdi+160h]; bstrString
0x18000c449  call    cs:__imp_SysFreeString
0x18000c44f  mov     [rdi+160h], rbp
0x18000c456  mov     rcx, [rdi+198h]; bstrString
0x18000c45d  call    cs:__imp_SysFreeString
0x18000c463  mov     [rdi+198h], rbp
0x18000c46a  mov     rcx, [rdi+1A0h]; bstrString
0x18000c471  call    cs:__imp_SysFreeString
0x18000c477  mov     [rdi+1A0h], rbp
0x18000c47e  lea     edx, [rbp+1]; struct std::nothrow_t *
0x18000c481  mov     rcx, [rdi+1B0h]; void *
0x18000c488  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c48d  mov     rcx, [rdi+1B8h]; void *
0x18000c494  lea     edx, [rbp+1]; struct std::nothrow_t *
0x18000c497  mov     [rdi+1B0h], rbp
0x18000c49e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c4a3  mov     ecx, [rdi+1C4h]; unsigned __int64
0x18000c4a9  mov     rdx, [rdi+1C8h]; wchar_t **
0x18000c4b0  mov     [rdi+1B8h], rbp
0x18000c4b7  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18000c4bc  mov     ecx, [rdi+1C4h]; unsigned __int64
0x18000c4c2  mov     rdx, [rdi+1D0h]; wchar_t **
0x18000c4c9  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18000c4ce  mov     ecx, [rdi+1E0h]; unsigned __int64
0x18000c4d4  mov     rdx, [rdi+1E8h]; wchar_t **
0x18000c4db  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18000c4e0  mov     rcx, [rdi+1F0h]; lpMem
0x18000c4e7  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000c4ec  mov     [rdi+1F0h], rbp
0x18000c4f3  mov     rcx, [rdi+1F8h]; lpMem
0x18000c4fa  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000c4ff  mov     [rdi+1F8h], rbp
0x18000c506  mov     rcx, [rdi+210h]; lpMem
0x18000c50d  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000c512  lea     rbx, [rdi+220h]
0x18000c519  mov     [rdi+210h], rbp
0x18000c520  test    rbx, rbx
0x18000c523  jz      short loc_18000C597
0x18000c525  cmp     [rbx+14h], ebp
0x18000c528  jbe     short loc_18000C548
0x18000c52a  mov     esi, ebp
0x18000c52c  mov     rax, [rbx+18h]
0x18000c530  mov     ecx, esi
0x18000c532  mov     rcx, [rax+rcx*8]; pv
0x18000c536  test    rcx, rcx
0x18000c539  jz      short loc_18000C541
0x18000c53b  call    cs:__imp_CoTaskMemFree
0x18000c541  inc     esi
0x18000c543  cmp     esi, [rbx+14h]
0x18000c546  jb      short loc_18000C52C
0x18000c548  cmp     [rbx+20h], ebp
0x18000c54b  jbe     short loc_18000C56B
0x18000c54d  mov     esi, ebp
0x18000c54f  mov     rax, [rbx+28h]
0x18000c553  mov     ecx, esi
0x18000c555  mov     rcx, [rax+rcx*8]; pv
0x18000c559  test    rcx, rcx
0x18000c55c  jz      short loc_18000C564
0x18000c55e  call    cs:__imp_CoTaskMemFree
0x18000c564  inc     esi
0x18000c566  cmp     esi, [rbx+20h]
0x18000c569  jb      short loc_18000C54F
0x18000c56b  mov     rcx, [rbx+18h]; pv
0x18000c56f  test    rcx, rcx
0x18000c572  jz      short loc_18000C57A
0x18000c574  call    cs:__imp_CoTaskMemFree
0x18000c57a  mov     rcx, [rbx+28h]; pv
0x18000c57e  test    rcx, rcx
0x18000c581  jz      short loc_18000C589
0x18000c583  call    cs:__imp_CoTaskMemFree
0x18000c589  xorps   xmm0, xmm0
0x18000c58c  movups  xmmword ptr [rbx], xmm0
0x18000c58f  movups  xmmword ptr [rbx+10h], xmm0
0x18000c593  movups  xmmword ptr [rbx+20h], xmm0
0x18000c597  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration> `wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl(void)'::`2'::impl
0x18000c59e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(void)
0x18000c5a3  test    al, al
0x18000c5a5  jz      short loc_18000C5B3
0x18000c5a7  mov     rcx, [rdi+260h]; lpMem
0x18000c5ae  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000c5b3  xor     edx, edx; Val
0x18000c5b5  mov     r8d, 288h; Size
0x18000c5bb  mov     rcx, rdi; void *
0x18000c5be  call    memset
0x18000c5c3  mov     rbx, [rsp+28h+arg_0]
0x18000c5c8  mov     rbp, [rsp+28h+arg_8]
0x18000c5cd  mov     rsi, [rsp+28h+arg_10]
0x18000c5d2  add     rsp, 20h
0x18000c5d6  pop     rdi
0x18000c5d7  retn
```
