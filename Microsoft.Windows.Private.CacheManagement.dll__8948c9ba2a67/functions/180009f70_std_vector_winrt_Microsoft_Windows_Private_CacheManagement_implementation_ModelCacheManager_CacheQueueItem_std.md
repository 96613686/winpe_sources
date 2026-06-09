# std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem,std::allocator<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>>::_Emplace_reallocate<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem &>(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem * const,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem &)

- ea: `0x180009f70`
- end: `0x18000a225`
- name: `??$_Emplace_reallocate@AEAUCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@?$vector@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@V?$allocator@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@std@@@std@@AEAAPEAUCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAU23456789@AEAU23456789@@Z`
- size: `693`
- prototype: `char *__fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem **, winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006470`

## callees

- `0x180002460`
- `0x1800025b0`
- `0x1800059e0`
- `0x180009f70`
- `0x18000b7a0`
- `0x1800127e0`
- `0x180018238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a212`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a212`

## pseudocode

```c
char *__fastcall std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>::_Emplace_reallocate<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem &>(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem **a1,
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *a2,
        __int64 a3)
{
  signed __int64 v6; // rbx
  __int64 v7; // rax
  unsigned __int64 v8; // r12
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rbp
  _QWORD *v12; // r13
  _QWORD *v13; // rbx
  struct winrt::impl::hstring_header *v14; // rdx
  struct winrt::impl::hstring_header *v15; // rdx
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *v16; // r8
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *v17; // rax
  _BYTE *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  _BYTE *v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *v24; // r8
  __int64 *v25; // rcx
  _BYTE *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *v29; // rbx
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *i; // rsi
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *v31; // rcx
  unsigned __int64 v32; // rdx
  char *v34; // [rsp+30h] [rbp-88h]

  v6 = a2 - *a1;
  v7 = (a1[1] - *a1) >> 5;
  if ( v7 == 0x7FFFFFFFFFFFFFFLL )
    std::vector<winrt::hstring>::_Xlength();
  v8 = v7 + 1;
  v9 = (a1[2] - *a1) >> 5;
  v10 = v9 >> 1;
  if ( v9 <= 0x7FFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v11 = v7 + 1;
    if ( v10 + v9 >= v8 )
      v11 = v10 + v9;
    if ( v11 > 0x7FFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v11 = 0x7FFFFFFFFFFFFFFLL;
  }
  _mm_lfence();
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(32 * v11);
  v34 = (char *)v12 + (v6 & 0xFFFFFFFFFFFFFFE0uLL);
  v13 = v34 + 32;
  *(_QWORD *)v34 = winrt::impl::duplicate_hstring(*(winrt::impl **)a3, v14);
  v34[16] = 0;
  if ( *(_BYTE *)(a3 + 16) )
  {
    *((_QWORD *)v34 + 1) = winrt::impl::duplicate_hstring(*(winrt::impl **)(a3 + 8), v15);
    v34[16] = 1;
  }
  v34[24] = *(_BYTE *)(a3 + 24);
  v16 = a1[1];
  v17 = *a1;
  if ( a2 == v16 )
  {
    if ( v17 != v16 )
    {
      v18 = v12 + 2;
      do
      {
        v19 = *(_QWORD *)v17;
        *(_QWORD *)v17 = 0;
        *((_QWORD *)v18 - 2) = v19;
        *v18 = 0;
        if ( *((_BYTE *)v17 + 16) )
        {
          v20 = *((_QWORD *)v17 + 1);
          *((_QWORD *)v17 + 1) = 0;
          *((_QWORD *)v18 - 1) = v20;
          *v18 = 1;
        }
        v18[8] = *((_BYTE *)v17 + 24);
        v18 += 32;
        v17 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)((char *)v17 + 32);
      }
      while ( v17 != v16 );
    }
  }
  else
  {
    if ( v17 != a2 )
    {
      v21 = v12 + 2;
      do
      {
        v22 = *(_QWORD *)v17;
        *(_QWORD *)v17 = 0;
        *((_QWORD *)v21 - 2) = v22;
        *v21 = 0;
        if ( *((_BYTE *)v17 + 16) )
        {
          v23 = *((_QWORD *)v17 + 1);
          *((_QWORD *)v17 + 1) = 0;
          *((_QWORD *)v21 - 1) = v23;
          *v21 = 1;
        }
        v21[8] = *((_BYTE *)v17 + 24);
        v21 += 32;
        v17 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)((char *)v17 + 32);
      }
      while ( v17 != a2 );
    }
    v24 = a1[1];
    if ( a2 != v24 )
    {
      v25 = (__int64 *)((char *)a2 + 8);
      v26 = v34 + 48;
      do
      {
        v27 = *(v25 - 1);
        *(v25 - 1) = 0;
        *v13 = v27;
        *v26 = 0;
        if ( *((_BYTE *)v25 + 8) )
        {
          v28 = *v25;
          *v25 = 0;
          *((_QWORD *)v26 - 1) = v28;
          *v26 = 1;
        }
        v26[8] = *((_BYTE *)v25 + 16);
        v13 += 4;
        v26 += 32;
        v25 += 4;
      }
      while ( v25 - 1 != (__int64 *)v24 );
    }
  }
  v29 = *a1;
  if ( *a1 )
  {
    for ( i = a1[1];
          v29 != i;
          v29 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)((char *)v29 + 32) )
    {
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem(v29);
    }
    v31 = *a1;
    v32 = (a1[2] - *a1) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v32 >= 0x1000 )
    {
      _mm_lfence();
      v32 += 39LL;
      if ( (unsigned __int64)v31 - *((_QWORD *)v31 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v31 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)*((_QWORD *)v31 - 1);
    }
    operator delete(v31, v32);
  }
  *a1 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)v12;
  a1[1] = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)&v12[4 * v8];
  a1[2] = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)&v12[4 * v11];
  _mm_lfence();
  return v34;
}

```

## disassembly

```asm
0x180009f70  mov     [rsp+arg_18], rbx
0x180009f75  push    rbp
0x180009f76  push    rsi
0x180009f77  push    rdi
0x180009f78  push    r12
0x180009f7a  push    r13
0x180009f7c  push    r14
0x180009f7e  push    r15
0x180009f80  sub     rsp, 80h
0x180009f87  mov     r14, r8
0x180009f8a  mov     rsi, rdx
0x180009f8d  mov     rdi, rcx
0x180009f90  mov     rdx, [rcx]
0x180009f93  mov     rbx, rsi
0x180009f96  sub     rbx, rdx
0x180009f99  mov     rax, [rcx+8]
0x180009f9d  sub     rax, rdx
0x180009fa0  sar     rax, 5
0x180009fa4  mov     r8, 7FFFFFFFFFFFFFFh
0x180009fae  cmp     rax, r8
0x180009fb1  jz      loc_18000A219
0x180009fb7  lea     r12, [rax+1]
0x180009fbb  mov     rcx, [rcx+10h]
0x180009fbf  sub     rcx, rdx
0x180009fc2  sar     rcx, 5
0x180009fc6  mov     rdx, rcx
0x180009fc9  shr     rdx, 1
0x180009fcc  mov     rax, r8
0x180009fcf  sub     rax, rdx
0x180009fd2  cmp     rcx, rax
0x180009fd5  jbe     loc_18000A0BC
0x180009fdb  mov     rbp, r8
0x180009fde  lfence
0x180009fe1  mov     rax, rbp
0x180009fe4  shl     rax, 5
0x180009fe8  mov     [rsp+0B8h+var_80], rax
0x180009fed  mov     rcx, rax
0x180009ff0  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009ff5  mov     r13, rax
0x180009ff8  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180009ffc  lea     r15, [rbx+rax]
0x18000a000  mov     [rsp+0B8h+var_88], r15
0x18000a005  lea     rbx, [r15+20h]
0x18000a009  mov     [rsp+0B8h+var_68], rdi
0x18000a00e  mov     [rsp+0B8h+var_60], rax
0x18000a013  mov     [rsp+0B8h+var_58], rbp
0x18000a018  mov     [rsp+0B8h+var_50], rbx
0x18000a01d  mov     [rsp+0B8h+var_48], rbx
0x18000a022  mov     [rsp+0B8h+var_78], r15
0x18000a027  mov     rcx, [r14]; this
0x18000a02a  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000a02f  mov     [r15], rax
0x18000a032  add     r15, 8
0x18000a036  mov     [rsp+0B8h+var_70], r15
0x18000a03b  mov     byte ptr [r15+8], 0
0x18000a040  cmp     byte ptr [r14+10h], 0
0x18000a045  jz      short loc_18000A058
0x18000a047  mov     rcx, [r14+8]; this
0x18000a04b  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000a050  mov     [r15], rax
0x18000a053  mov     byte ptr [r15+8], 1
0x18000a058  movzx   eax, byte ptr [r14+18h]
0x18000a05d  mov     r14, [rsp+0B8h+var_88]
0x18000a062  mov     [r14+18h], al
0x18000a066  mov     r8, [rdi+8]
0x18000a06a  mov     rax, [rdi]
0x18000a06d  xor     ebp, ebp
0x18000a06f  cmp     rsi, r8
0x18000a072  jnz     short loc_18000A0D8
0x18000a074  cmp     rax, r8
0x18000a077  jz      loc_18000A16D
0x18000a07d  lea     rdx, [r13+10h]
0x18000a081  mov     rcx, [rax]
0x18000a084  mov     [rax], rbp
0x18000a087  mov     [rdx-10h], rcx
0x18000a08b  mov     [rdx], bpl
0x18000a08e  cmp     [rax+10h], bpl
0x18000a092  jz      short loc_18000A0A3
0x18000a094  mov     rcx, [rax+8]
0x18000a098  mov     [rax+8], rbp
0x18000a09c  mov     [rdx-8], rcx
0x18000a0a0  mov     byte ptr [rdx], 1
0x18000a0a3  movzx   ecx, byte ptr [rax+18h]
0x18000a0a7  mov     [rdx+8], cl
0x18000a0aa  add     rdx, 20h ; ' '
0x18000a0ae  add     rax, 20h ; ' '
0x18000a0b2  cmp     rax, r8
0x18000a0b5  jnz     short loc_18000A081
0x18000a0b7  jmp     loc_18000A16D
0x18000a0bc  lea     rax, [rdx+rcx]
0x18000a0c0  mov     rbp, r12
0x18000a0c3  cmp     rax, r12
0x18000a0c6  cmovnb  rbp, rax
0x18000a0ca  cmp     rbp, r8
0x18000a0cd  ja      loc_18000A21F
0x18000a0d3  jmp     loc_180009FDE
0x18000a0d8  cmp     rax, rsi
0x18000a0db  jz      short loc_18000A117
0x18000a0dd  lea     rdx, [r13+10h]
0x18000a0e1  mov     rcx, [rax]
0x18000a0e4  mov     [rax], rbp
0x18000a0e7  mov     [rdx-10h], rcx
0x18000a0eb  mov     [rdx], bpl
0x18000a0ee  cmp     [rax+10h], bpl
0x18000a0f2  jz      short loc_18000A103
0x18000a0f4  mov     rcx, [rax+8]
0x18000a0f8  mov     [rax+8], rbp
0x18000a0fc  mov     [rdx-8], rcx
0x18000a100  mov     byte ptr [rdx], 1
0x18000a103  movzx   ecx, byte ptr [rax+18h]
0x18000a107  mov     [rdx+8], cl
0x18000a10a  add     rdx, 20h ; ' '
0x18000a10e  add     rax, 20h ; ' '
0x18000a112  cmp     rax, rsi
0x18000a115  jnz     short loc_18000A0E1
0x18000a117  mov     r8, [rdi+8]
0x18000a11b  cmp     rsi, r8
0x18000a11e  jz      short loc_18000A16D
0x18000a120  lea     rcx, [rsi+8]
0x18000a124  lea     rdx, [rbx+10h]
0x18000a128  nop     dword ptr [rax+rax+00000000h]
0x18000a130  mov     rax, [rcx-8]
0x18000a134  mov     [rcx-8], rbp
0x18000a138  mov     [rbx], rax
0x18000a13b  mov     [rdx], bpl
0x18000a13e  cmp     [rcx+8], bpl
0x18000a142  jz      short loc_18000A151
0x18000a144  mov     rax, [rcx]
0x18000a147  mov     [rcx], rbp
0x18000a14a  mov     [rdx-8], rax
0x18000a14e  mov     byte ptr [rdx], 1
0x18000a151  movzx   eax, byte ptr [rcx+10h]
0x18000a155  mov     [rdx+8], al
0x18000a158  add     rbx, 20h ; ' '
0x18000a15c  add     rdx, 20h ; ' '
0x18000a160  add     rcx, 20h ; ' '
0x18000a164  lea     rax, [rcx-8]
0x18000a168  cmp     rax, r8
0x18000a16b  jnz     short loc_18000A130
0x18000a16d  mov     rbx, [rdi]
0x18000a170  test    rbx, rbx
0x18000a173  jz      short loc_18000A1C8
0x18000a175  mov     rsi, [rdi+8]
0x18000a179  cmp     rbx, rsi
0x18000a17c  jz      short loc_18000A191
0x18000a17e  xchg    ax, ax
0x18000a180  mov     rcx, rbx; this
0x18000a183  call    ??1CacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem(void)
0x18000a188  add     rbx, 20h ; ' '
0x18000a18c  cmp     rbx, rsi
0x18000a18f  jnz     short loc_18000A180
0x18000a191  mov     rcx, [rdi]
0x18000a194  mov     rdx, [rdi+10h]
0x18000a198  sub     rdx, rcx
0x18000a19b  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18000a19f  cmp     rdx, 1000h
0x18000a1a6  jb      short loc_18000A1C3
0x18000a1a8  lfence
0x18000a1ab  add     rdx, 27h ; '''; unsigned __int64
0x18000a1af  mov     rax, [rcx-8]
0x18000a1b3  sub     rcx, rax
0x18000a1b6  sub     rcx, 8
0x18000a1ba  cmp     rcx, 1Fh
0x18000a1be  ja      short loc_18000A203
0x18000a1c0  mov     rcx, rax; void *
0x18000a1c3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a1c8  mov     [rdi], r13
0x18000a1cb  shl     r12, 5
0x18000a1cf  add     r12, r13
0x18000a1d2  mov     [rdi+8], r12
0x18000a1d6  mov     rcx, [rsp+0B8h+var_80]
0x18000a1db  add     rcx, r13
0x18000a1de  mov     [rdi+10h], rcx
0x18000a1e2  lfence
0x18000a1e5  mov     rax, r14
0x18000a1e8  mov     rbx, [rsp+0B8h+arg_18]
0x18000a1f0  add     rsp, 80h
0x18000a1f7  pop     r15
0x18000a1f9  pop     r14
0x18000a1fb  pop     r13
0x18000a1fd  pop     r12
0x18000a1ff  pop     rdi
0x18000a200  pop     rsi
0x18000a201  pop     rbp
0x18000a202  retn
0x18000a203  mov     [rsp+0B8h+Reserved], rbp; Reserved
0x18000a208  xor     r9d, r9d; LineNo
0x18000a20b  xor     r8d, r8d; FileName
0x18000a20e  xor     edx, edx; FunctionName
0x18000a210  xor     ecx, ecx; Expression
0x18000a212  call    cs:__imp__invoke_watson
0x18000a219  call    ?_Xlength@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@CAXXZ; std::vector<winrt::hstring>::_Xlength(void)
0x18000a21f  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
