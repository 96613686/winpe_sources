# HierarchicalCache::HierarchicalCache(ShaderCacheDesc &)

- ea: `0x180042f8c`
- end: `0x1800431ab`
- name: `??0HierarchicalCache@@QEAA@AEAUShaderCacheDesc@@@Z`
- size: `543`
- prototype: `HierarchicalCache *__fastcall(HierarchicalCache *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001f410`

## callees

- `0x180001d30`
- `0x18003b170`
- `0x18003ed98`
- `0x180042f8c`
- `0x1800431b4`
- `0x180045374`
- `0x18004b274`
- `0x18004b41c`
- `0x18004d23c`
- `0x180050830`
- `0x1800509a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180042fc9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180042fc9`

## pseudocode

```c
HierarchicalCache *__fastcall HierarchicalCache::HierarchicalCache(HierarchicalCache *this, unsigned __int64 a2)
{
  __int64 v4; // r8
  _QWORD *v5; // r15
  _QWORD *v6; // r14
  ShaderDiskCacheSQLite *v7; // rbx
  int v8; // eax
  __int64 (__fastcall **v10)(); // [rsp+20h] [rbp-40h] BYREF
  ShaderDiskCacheSQLite *v11; // [rsp+28h] [rbp-38h]
  unsigned __int64 v12; // [rsp+30h] [rbp-30h]
  char v13; // [rsp+38h] [rbp-28h]
  int v14; // [rsp+39h] [rbp-27h]
  __int16 v15; // [rsp+3Dh] [rbp-23h]
  char v16; // [rsp+3Fh] [rbp-21h]
  __int64 (__fastcall ***v17)(); // [rsp+58h] [rbp-8h]

  memset_0(this, 0, 0xA0u);
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 4, 0xFA0u);
  *((_BYTE *)this + 200) = *(_DWORD *)a2 & 1;
  v10 = off_1800A9430;
  v11 = this;
  v12 = a2;
  v13 = 1;
  v14 = a2 >> 8;
  v15 = HIDWORD(a2) >> 8;
  v16 = HIBYTE(a2);
  v17 = &v10;
  v4 = 0xFFFFFFFFLL;
  if ( *(_DWORD *)(a2 + 36) != 1 )
    v4 = 1;
  RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>(
    (__int64)this + 208,
    (__int64)&v10,
    v4);
  *((_QWORD *)this + 58) = 2;
  *(_OWORD *)((char *)this + 488) = 0;
  *(_OWORD *)((char *)this + 504) = 0;
  *(_OWORD *)((char *)this + 520) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_DWORD *)this + 134) = -1;
  *((_DWORD *)this + 135) = 0;
  *((_BYTE *)this + 544) = (*(_DWORD *)a2 & 0x800) != 0;
  *((_BYTE *)this + 545) = 0;
  v5 = (_QWORD *)((char *)this + 552);
  *(_OWORD *)((char *)this + 552) = 0;
  *(_OWORD *)((char *)this + 568) = 0;
  *(_OWORD *)((char *)this + 584) = 0;
  v6 = (_QWORD *)((char *)this + 600);
  std::wstring::wstring((char *)this + 600);
  std::wstring::wstring((char *)this + 632);
  std::wstring::wstring((char *)this + 664);
  *((_BYTE *)this + 696) = 0;
  *((_OWORD *)this + 44) = 0;
  *((_QWORD *)this + 90) = 0;
  std::wstring::wstring((char *)this + 728);
  RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::RetrieveForWrite((char *)this + 208, &v10);
  v7 = v11;
  if ( *(_DWORD *)(a2 + 36) == 1 )
  {
    ShaderDiskCacheSQLite::LoadApplicationIdentity(
      v11,
      lambda_4f1f0f58546a805377ccb5361a3d45a7_::_lambda_invoker_cdecl_,
      this);
    ShaderDiskCacheSQLite::LoadCompilerIdentity(
      v7,
      lambda_7fbb9296e765c05af3e0f09740d20fa2_::_lambda_invoker_cdecl_,
      this);
  }
  if ( !*((_BYTE *)this + 544) && !*((_BYTE *)this + 200) && !*v5 )
  {
    if ( (int)D3DXPlat::GetExePath((char *)this + 600) < 0 )
      ThrowFailure(-2147418113);
    if ( *((_QWORD *)this + 78) > 7u )
      v6 = (_QWORD *)*v6;
    *v5 = v6;
    v8 = ShaderDiskCacheSQLite::StoreApplicationIdentity(v7, (HierarchicalCache *)((char *)this + 552));
    ThrowFailure(v8);
  }
  RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::~Accessor(&v10);
  return this;
}

```

## disassembly

```asm
0x180042f8c  mov     [rsp-28h+arg_10], rbx
0x180042f91  mov     [rsp-28h+arg_18], rsi
0x180042f96  mov     [rsp-28h+arg_0], rcx
0x180042f9b  push    rbp
0x180042f9c  push    rdi
0x180042f9d  push    r12
0x180042f9f  push    r14
0x180042fa1  push    r15
0x180042fa3  mov     rbp, rsp
0x180042fa6  sub     rsp, 60h
0x180042faa  mov     rdi, rdx
0x180042fad  mov     rsi, rcx
0x180042fb0  xor     edx, edx; Val
0x180042fb2  mov     r8d, 0A0h; Size
0x180042fb8  call    memset_0
0x180042fbd  lea     rcx, [rsi+0A0h]; lpCriticalSection
0x180042fc4  mov     edx, 0FA0h; dwSpinCount
0x180042fc9  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180042fcf  nop
0x180042fd0  mov     eax, [rdi]
0x180042fd2  mov     r12d, 1
0x180042fd8  and     al, r12b
0x180042fdb  mov     [rsi+0C8h], al
0x180042fe1  lea     rbx, [rsi+0D0h]
0x180042fe8  lea     rax, off_1800A9430
0x180042fef  mov     [rbp+var_40], rax
0x180042ff3  mov     [rbp+var_38], rsi
0x180042ff7  mov     [rbp+var_30], rdi
0x180042ffb  mov     [rbp+var_28], r12b
0x180042fff  mov     eax, dword ptr [rbp+var_30+1]
0x180043002  mov     [rbp+var_27], eax
0x180043005  movzx   eax, word ptr [rbp+var_30+5]
0x180043009  mov     [rbp+var_23], ax
0x18004300d  mov     al, byte ptr [rbp+var_30+7]
0x180043010  mov     [rbp+var_21], al
0x180043013  lea     rax, [rbp+var_40]
0x180043017  mov     [rbp+var_8], rax
0x18004301b  or      r8d, 0FFFFFFFFh
0x18004301f  cmp     [rdi+24h], r12d
0x180043023  cmovnz  r8d, r12d
0x180043027  lea     rdx, [rbp+var_40]
0x18004302b  mov     rcx, rbx
0x18004302e  call    ??0?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA@V?$function@$$A6A?AV?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@XZ@std@@I@Z; RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>(std::function<std::unique_ptr<ShaderDiskCacheSQLite> (void)>,uint)
0x180043033  nop
0x180043034  mov     qword ptr [rsi+1D0h], 2
0x18004303f  xorps   xmm0, xmm0
0x180043042  movups  xmmword ptr [rsi+1E8h], xmm0
0x180043049  movups  xmmword ptr [rsi+1F8h], xmm0
0x180043050  movups  xmmword ptr [rsi+208h], xmm0
0x180043057  mov     qword ptr [rsi+1D8h], 0
0x180043062  mov     qword ptr [rsi+1E0h], 0
0x18004306d  mov     dword ptr [rsi+218h], 0FFFFFFFFh
0x180043077  mov     dword ptr [rsi+21Ch], 0
0x180043081  mov     eax, [rdi]
0x180043083  shr     eax, 0Bh
0x180043086  and     al, r12b
0x180043089  mov     [rsi+220h], al
0x18004308f  mov     byte ptr [rsi+221h], 0
0x180043096  lea     r15, [rsi+228h]
0x18004309d  movups  xmmword ptr [r15], xmm0
0x1800430a1  movups  xmmword ptr [r15+10h], xmm0
0x1800430a6  movups  xmmword ptr [r15+20h], xmm0
0x1800430ab  lea     r14, [rsi+258h]
0x1800430b2  mov     rcx, r14
0x1800430b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800430ba  nop
0x1800430bb  lea     rcx, [rsi+278h]
0x1800430c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800430c7  nop
0x1800430c8  lea     rcx, [rsi+298h]
0x1800430cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800430d4  nop
0x1800430d5  mov     byte ptr [rsi+2B8h], 0
0x1800430dc  xorps   xmm0, xmm0
0x1800430df  xor     eax, eax
0x1800430e1  movups  xmmword ptr [rsi+2C0h], xmm0
0x1800430e8  mov     [rsi+2D0h], rax
0x1800430ef  lea     rcx, [rsi+2D8h]
0x1800430f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800430fb  nop
0x1800430fc  lea     rdx, [rbp+var_40]
0x180043100  mov     rcx, rbx
0x180043103  call    ?RetrieveForWrite@?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA?AVAccessor@1@XZ; RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::RetrieveForWrite(void)
0x180043108  nop
0x180043109  mov     rbx, [rbp+var_38]
0x18004310d  cmp     [rdi+24h], r12d
0x180043111  jnz     short loc_180043137
0x180043113  mov     r8, rsi; void *
0x180043116  lea     rdx, _lambda_4f1f0f58546a805377ccb5361a3d45a7____lambda_invoker_cdecl_; void (*)(const struct ShaderCacheApplicationIdentity *, void *)
0x18004311d  mov     rcx, rbx; this
0x180043120  call    ?LoadApplicationIdentity@ShaderDiskCacheSQLite@@QEAAJP6AXAEBUShaderCacheApplicationIdentity@@PEAX@Z1@Z; ShaderDiskCacheSQLite::LoadApplicationIdentity(void (*)(ShaderCacheApplicationIdentity const &,void *),void *)
0x180043125  mov     r8, rsi; void *
0x180043128  lea     rdx, _lambda_7fbb9296e765c05af3e0f09740d20fa2____lambda_invoker_cdecl_; void (*)(const struct ShaderCacheCompilerIdentity *, void *)
0x18004312f  mov     rcx, rbx; this
0x180043132  call    ?LoadCompilerIdentity@ShaderDiskCacheSQLite@@QEAAJP6AXAEBUShaderCacheCompilerIdentity@@PEAX@Z1@Z; ShaderDiskCacheSQLite::LoadCompilerIdentity(void (*)(ShaderCacheCompilerIdentity const &,void *),void *)
0x180043137  cmp     byte ptr [rsi+220h], 0
0x18004313e  jnz     short loc_180043185
0x180043140  cmp     byte ptr [rsi+0C8h], 0
0x180043147  jnz     short loc_180043185
0x180043149  cmp     qword ptr [r15], 0
0x18004314d  jnz     short loc_180043185
0x18004314f  mov     rcx, r14
0x180043152  call    ?GetExePath@D3DXPlat@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; D3DXPlat::GetExePath(std::wstring &)
0x180043157  test    eax, eax
0x180043159  jns     short loc_180043165
0x18004315b  mov     ecx, 8000FFFFh; int
0x180043160  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180043165  cmp     qword ptr [r14+18h], 7
0x18004316a  jbe     short loc_18004316F
0x18004316c  mov     r14, [r14]
0x18004316f  mov     [r15], r14
0x180043172  mov     rdx, r15; struct ShaderCacheApplicationIdentity *
0x180043175  mov     rcx, rbx; this
0x180043178  call    ?StoreApplicationIdentity@ShaderDiskCacheSQLite@@QEAAJAEBUShaderCacheApplicationIdentity@@@Z; ShaderDiskCacheSQLite::StoreApplicationIdentity(ShaderCacheApplicationIdentity const &)
0x18004317d  mov     ecx, eax; int
0x18004317f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180043184  nop
0x180043185  lea     rcx, [rbp+var_40]
0x180043189  call    ??1Accessor@?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA@XZ; RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::~Accessor(void)
0x18004318e  nop
0x18004318f  mov     rax, rsi
0x180043192  lea     r11, [rsp+60h+var_s0]
0x180043197  mov     rbx, [r11+40h]
0x18004319b  mov     rsi, [r11+48h]
0x18004319f  mov     rsp, r11
0x1800431a2  pop     r15
0x1800431a4  pop     r14
0x1800431a6  pop     r12
0x1800431a8  pop     rdi
0x1800431a9  pop     rbp
0x1800431aa  retn
```
