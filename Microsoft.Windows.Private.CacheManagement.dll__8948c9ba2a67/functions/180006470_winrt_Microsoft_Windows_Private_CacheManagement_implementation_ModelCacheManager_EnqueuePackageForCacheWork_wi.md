# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueuePackageForCacheWork(winrt::hstring const &,std::optional<winrt::hstring>,bool)

- ea: `0x180006470`
- end: `0x180006743`
- name: `?EnqueuePackageForCacheWork@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXAEBUhstring@7@V?$optional@Uhstring@winrt@@@std@@_N@Z`
- size: `723`
- prototype: `int __fastcall(__int64, winrt::impl **, __int64, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800060e0`

## callees

- `0x180006470`
- `0x180009f70`
- `0x180011eb0`
- `0x1800127e0`
- `0x180016298`
- `0x18001629e`
- `0x1800165b8`
- `0x1800165c0`
- `0x18001700c`
- `0x1800181b0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006714`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000671f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006714`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000671f`

## pseudocode

```c
int __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueuePackageForCacheWork(
        __int64 a1,
        winrt::impl **a2,
        __int64 a3,
        char a4)
{
  __int64 v8; // rbx
  wchar_t *v9; // rdx
  __int64 *v10; // rdi
  __int64 *i; // rsi
  winrt::impl *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  size_t v15; // r8
  const wchar_t *v16; // r9
  bool v17; // al
  __int64 v18; // rax
  __int64 v19; // rcx
  winrt::impl *v20; // rax
  size_t v21; // r8
  const wchar_t *v22; // r9
  struct winrt::impl::hstring_header *v23; // rax
  struct winrt::impl::hstring_header *v24; // rdx
  __int64 v25; // rdi
  struct winrt::impl::hstring_header *v26; // rdx
  void *v27; // rdi
  int v28; // eax
  HANDLE ProcessHeap; // rax
  void *v30; // rdi
  int v31; // eax
  HANDLE v32; // rax
  int result; // eax
  winrt::impl *v34; // rbx
  int v35; // esi
  HANDLE v36; // rax
  LPVOID v37; // [rsp+40h] [rbp-78h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-70h]
  char v39; // [rsp+50h] [rbp-68h]
  char v40; // [rsp+58h] [rbp-60h]

  v8 = a1 + 80;
  if ( Mtx_lock((_Mtx_t)(a1 + 80)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v8 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v8 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v10 = *(__int64 **)(a1 + 40);
  for ( i = *(__int64 **)(a1 + 48); v10 != i; v10 += 4 )
  {
    v12 = *a2;
    if ( *a2 )
    {
      v13 = *((unsigned int *)v12 + 1);
      v9 = (wchar_t *)*((_QWORD *)v12 + 2);
    }
    else
    {
      v13 = 0;
      v9 = (wchar_t *)&S2;
    }
    v14 = *v10;
    if ( *v10 )
    {
      v15 = *(unsigned int *)(v14 + 4);
      v16 = *(const wchar_t **)(v14 + 16);
    }
    else
    {
      v15 = 0;
      v16 = &S2;
    }
    if ( v15 == v13 )
    {
      if ( v15 )
        v17 = wmemcmp(v16, v9, v15) == 0;
      else
        v17 = 1;
    }
    else
    {
      v17 = 0;
    }
    if ( *(_BYTE *)(a3 + 8) && *((_BYTE *)v10 + 16) )
    {
      if ( v17 )
      {
        v18 = v10[1];
        if ( v18 )
        {
          v19 = *(unsigned int *)(v18 + 4);
          v9 = *(wchar_t **)(v18 + 16);
        }
        else
        {
          v19 = 0;
          v9 = (wchar_t *)&S2;
        }
        v20 = *(winrt::impl **)a3;
        if ( *(_QWORD *)a3 )
        {
          v21 = *((unsigned int *)v20 + 1);
          v22 = (const wchar_t *)*((_QWORD *)v20 + 2);
        }
        else
        {
          v21 = 0;
          v22 = &S2;
        }
        if ( v21 == v19 && (!v21 || !wmemcmp(v22, v9, v21)) )
          break;
      }
    }
    else if ( v17 )
    {
      break;
    }
  }
  if ( v10 == *(__int64 **)(a1 + 48) )
  {
    v23 = winrt::impl::duplicate_hstring(*a2, (struct winrt::impl::hstring_header *)v9);
    v37 = v23;
    v39 = 0;
    if ( *(_BYTE *)(a3 + 8) )
    {
      lpMem = winrt::impl::duplicate_hstring(*(winrt::impl **)a3, v24);
      v39 = 1;
      v23 = (struct winrt::impl::hstring_header *)v37;
    }
    v40 = a4;
    v25 = *(_QWORD *)(a1 + 48);
    if ( v25 == *(_QWORD *)(a1 + 56) )
    {
      std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>::_Emplace_reallocate<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem &>(
        a1 + 40,
        *(_QWORD *)(a1 + 48),
        &v37);
    }
    else
    {
      *(_QWORD *)v25 = winrt::impl::duplicate_hstring(v23, v24);
      *(_BYTE *)(v25 + 16) = 0;
      if ( v39 )
      {
        *(_QWORD *)(v25 + 8) = winrt::impl::duplicate_hstring((winrt::impl *)lpMem, v26);
        *(_BYTE *)(v25 + 16) = 1;
      }
      *(_BYTE *)(v25 + 24) = v40;
      *(_QWORD *)(a1 + 48) += 32LL;
    }
    if ( v39 )
    {
      v27 = lpMem;
      if ( lpMem )
      {
        v28 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( v28 )
        {
          if ( v28 < 0 )
            goto LABEL_54;
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v27);
        }
        lpMem = 0;
      }
    }
    v30 = v37;
    if ( v37 )
    {
      v31 = _InterlockedDecrement((volatile signed __int32 *)v37 + 6);
      if ( !v31 )
      {
        v32 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v32, 0, v30);
        goto LABEL_47;
      }
      if ( v31 >= 0 )
        goto LABEL_47;
LABEL_54:
      abort();
    }
  }
LABEL_47:
  result = Mtx_unlock((_Mtx_t)v8);
  if ( *(_BYTE *)(a3 + 8) )
  {
    v34 = *(winrt::impl **)a3;
    if ( *(_QWORD *)a3 )
    {
      v35 = _InterlockedDecrement((volatile signed __int32 *)v34 + 6);
      if ( v35 )
      {
        if ( v35 < 0 )
          abort();
      }
      else
      {
        v36 = WINRT_IMPL_GetProcessHeap();
        result = WINRT_IMPL_HeapFree(v36, 0, v34);
      }
      *(_QWORD *)a3 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006470  push    rbx
0x180006472  push    rbp
0x180006473  push    rsi
0x180006474  push    rdi
0x180006475  push    r12
0x180006477  push    r13
0x180006479  push    r14
0x18000647b  push    r15
0x18000647d  sub     rsp, 78h
0x180006481  mov     rax, cs:__security_cookie
0x180006488  xor     rax, rsp
0x18000648b  mov     [rsp+0B8h+var_58], rax
0x180006490  movzx   r12d, r9b
0x180006494  mov     r15, r8
0x180006497  mov     r14, rdx
0x18000649a  mov     r13, rcx
0x18000649d  mov     [rsp+0B8h+var_80], r8
0x1800064a2  lea     rbx, [rcx+50h]
0x1800064a6  mov     [rsp+0B8h+var_98], rbx
0x1800064ab  mov     rcx, rbx; _Mtx_t
0x1800064ae  call    _Mtx_lock
0x1800064b3  test    eax, eax
0x1800064b5  jnz     loc_180006738
0x1800064bb  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800064c2  jz      loc_180006726
0x1800064c8  mov     rdi, [r13+28h]
0x1800064cc  mov     rsi, [r13+30h]
0x1800064d0  cmp     rdi, rsi
0x1800064d3  jz      loc_1800065A6
0x1800064d9  nop     dword ptr [rax+00000000h]
0x1800064e0  mov     rax, [r14]
0x1800064e3  test    rax, rax
0x1800064e6  jz      short loc_1800064F1
0x1800064e8  mov     ecx, [rax+4]
0x1800064eb  mov     rdx, [rax+10h]
0x1800064ef  jmp     short loc_1800064FA
0x1800064f1  xor     ecx, ecx
0x1800064f3  lea     rdx, S2; S2
0x1800064fa  mov     rax, [rdi]
0x1800064fd  test    rax, rax
0x180006500  jz      short loc_18000650C
0x180006502  mov     r8d, [rax+4]
0x180006506  mov     r9, [rax+10h]
0x18000650a  jmp     short loc_180006516
0x18000650c  xor     r8d, r8d; N
0x18000650f  lea     r9, S2
0x180006516  cmp     r8, rcx
0x180006519  jz      short loc_18000651F
0x18000651b  xor     al, al
0x18000651d  jmp     short loc_180006535
0x18000651f  test    r8, r8
0x180006522  jnz     short loc_180006528
0x180006524  mov     al, 1
0x180006526  jmp     short loc_180006535
0x180006528  mov     rcx, r9; S1
0x18000652b  call    wmemcmp
0x180006530  test    eax, eax
0x180006532  setz    al
0x180006535  cmp     byte ptr [r15+8], 0
0x18000653a  jz      short loc_180006595
0x18000653c  cmp     byte ptr [rdi+10h], 0
0x180006540  jz      short loc_180006595
0x180006542  test    al, al
0x180006544  jz      short loc_180006599
0x180006546  mov     rax, [rdi+8]
0x18000654a  test    rax, rax
0x18000654d  jz      short loc_180006558
0x18000654f  mov     ecx, [rax+4]
0x180006552  mov     rdx, [rax+10h]
0x180006556  jmp     short loc_180006561
0x180006558  xor     ecx, ecx
0x18000655a  lea     rdx, S2; S2
0x180006561  mov     rax, [r15]
0x180006564  test    rax, rax
0x180006567  jz      short loc_180006573
0x180006569  mov     r8d, [rax+4]
0x18000656d  mov     r9, [rax+10h]
0x180006571  jmp     short loc_18000657D
0x180006573  xor     r8d, r8d; N
0x180006576  lea     r9, S2
0x18000657d  cmp     r8, rcx
0x180006580  jnz     short loc_180006599
0x180006582  test    r8, r8
0x180006585  jz      short loc_1800065A6
0x180006587  mov     rcx, r9; S1
0x18000658a  call    wmemcmp
0x18000658f  test    eax, eax
0x180006591  jz      short loc_1800065A6
0x180006593  jmp     short loc_180006599
0x180006595  test    al, al
0x180006597  jnz     short loc_1800065A6
0x180006599  add     rdi, 20h ; ' '
0x18000659d  cmp     rdi, rsi
0x1800065a0  jnz     loc_1800064E0
0x1800065a6  mov     esi, 0FFFFFFFFh
0x1800065ab  cmp     rdi, [r13+30h]
0x1800065af  jnz     loc_1800066B7
0x1800065b5  mov     rcx, [r14]; this
0x1800065b8  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800065bd  mov     [rsp+0B8h+var_78], rax
0x1800065c2  mov     [rsp+0B8h+var_68], 0
0x1800065c7  cmp     byte ptr [r15+8], 0
0x1800065cc  jz      short loc_1800065E5
0x1800065ce  mov     rcx, [r15]; this
0x1800065d1  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800065d6  mov     [rsp+0B8h+lpMem], rax
0x1800065db  mov     [rsp+0B8h+var_68], 1
0x1800065e0  mov     rax, [rsp+0B8h+var_78]
0x1800065e5  mov     [rsp+0B8h+var_60], r12b
0x1800065ea  mov     rdi, [r13+30h]
0x1800065ee  cmp     rdi, [r13+38h]
0x1800065f2  jz      short loc_18000663A
0x1800065f4  mov     [rsp+0B8h+var_90], rdi
0x1800065f9  mov     rcx, rax; this
0x1800065fc  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180006601  mov     [rdi], rax
0x180006604  lea     r14, [rdi+8]
0x180006608  mov     [rsp+0B8h+var_88], r14
0x18000660d  mov     byte ptr [r14+8], 0
0x180006612  cmp     [rsp+0B8h+var_68], 0
0x180006617  jz      short loc_18000662B
0x180006619  mov     rcx, [rsp+0B8h+lpMem]; this
0x18000661e  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180006623  mov     [r14], rax
0x180006626  mov     byte ptr [r14+8], 1
0x18000662b  movzx   eax, [rsp+0B8h+var_60]
0x180006630  mov     [rdi+18h], al
0x180006633  add     qword ptr [r13+30h], 20h ; ' '
0x180006638  jmp     short loc_18000664C
0x18000663a  lea     r8, [rsp+0B8h+var_78]
0x18000663f  mov     rdx, rdi
0x180006642  lea     rcx, [r13+28h]
0x180006646  call    ??$_Emplace_reallocate@AEAUCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@?$vector@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@V?$allocator@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@std@@@std@@AEAAPEAUCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAU23456789@AEAU23456789@@Z; std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>::_Emplace_reallocate<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem &>(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem * const,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem &)
0x18000664b  nop
0x18000664c  cmp     [rsp+0B8h+var_68], 0
0x180006651  jz      short loc_18000668E
0x180006653  mov     rdi, [rsp+0B8h+lpMem]
0x180006658  test    rdi, rdi
0x18000665b  jz      short loc_18000668E
0x18000665d  mov     eax, esi
0x18000665f  lock xadd [rdi+18h], eax
0x180006664  sub     eax, 1
0x180006667  jnz     short loc_18000667D
0x180006669  call    WINRT_IMPL_GetProcessHeap
0x18000666e  mov     rcx, rax; hHeap
0x180006671  mov     r8, rdi; lpMem
0x180006674  xor     edx, edx; dwFlags
0x180006676  call    WINRT_IMPL_HeapFree
0x18000667b  jmp     short loc_180006685
0x18000667d  test    eax, eax
0x18000667f  js      loc_180006714
0x180006685  mov     [rsp+0B8h+lpMem], 0
0x18000668e  mov     rdi, [rsp+0B8h+var_78]
0x180006693  test    rdi, rdi
0x180006696  jz      short loc_1800066B7
0x180006698  mov     eax, esi
0x18000669a  lock xadd [rdi+18h], eax
0x18000669f  sub     eax, 1
0x1800066a2  jnz     short loc_180006710
0x1800066a4  call    WINRT_IMPL_GetProcessHeap
0x1800066a9  mov     rcx, rax; hHeap
0x1800066ac  mov     r8, rdi; lpMem
0x1800066af  xor     edx, edx; dwFlags
0x1800066b1  call    WINRT_IMPL_HeapFree
0x1800066b6  nop
0x1800066b7  mov     rcx, rbx; _Mtx_t
0x1800066ba  call    _Mtx_unlock
0x1800066bf  nop
0x1800066c0  cmp     byte ptr [r15+8], 0
0x1800066c5  jz      short loc_1800066F2
0x1800066c7  mov     rbx, [r15]
0x1800066ca  test    rbx, rbx
0x1800066cd  jz      short loc_1800066F2
0x1800066cf  lock xadd [rbx+18h], esi
0x1800066d4  sub     esi, 1
0x1800066d7  jnz     short loc_18000671B
0x1800066d9  call    WINRT_IMPL_GetProcessHeap
0x1800066de  mov     rcx, rax; hHeap
0x1800066e1  mov     r8, rbx; lpMem
0x1800066e4  xor     edx, edx; dwFlags
0x1800066e6  call    WINRT_IMPL_HeapFree
0x1800066eb  mov     qword ptr [r15], 0
0x1800066f2  mov     rcx, [rsp+0B8h+var_58]
0x1800066f7  xor     rcx, rsp; StackCookie
0x1800066fa  call    __security_check_cookie
0x1800066ff  add     rsp, 78h
0x180006703  pop     r15
0x180006705  pop     r14
0x180006707  pop     r13
0x180006709  pop     r12
0x18000670b  pop     rdi
0x18000670c  pop     rsi
0x18000670d  pop     rbp
0x18000670e  pop     rbx
0x18000670f  retn
0x180006710  test    eax, eax
0x180006712  jns     short loc_1800066B7
0x180006714  call    cs:__imp_abort
0x18000671b  test    esi, esi
0x18000671d  jns     short loc_1800066EB
0x18000671f  call    cs:__imp_abort
0x180006726  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18000672d  mov     ecx, 6; int
0x180006732  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180006738  mov     ecx, 5; int
0x18000673d  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
