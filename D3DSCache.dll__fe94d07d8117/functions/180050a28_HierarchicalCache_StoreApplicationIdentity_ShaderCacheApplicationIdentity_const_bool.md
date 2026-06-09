# HierarchicalCache::StoreApplicationIdentity(ShaderCacheApplicationIdentity const &,bool)

- ea: `0x180050a28`
- end: `0x180050c90`
- name: `?StoreApplicationIdentity@HierarchicalCache@@QEAAJAEBUShaderCacheApplicationIdentity@@_N@Z`
- size: `616`
- prototype: `__int64 __fastcall(HierarchicalCache *this, const struct ShaderCacheApplicationIdentity *, char)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180047900`
- `0x18004fbc0`

## callees

- `0x180001ce0`
- `0x18001a700`
- `0x18002a1e0`
- `0x18003b170`
- `0x18003e9f0`
- `0x18003ed98`
- `0x1800449f0`
- `0x18004d23c`
- `0x1800509a0`
- `0x180050a28`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180050c30`
- `msvcp_win!_Mtx_unlock` at `0x180050c30`

## pseudocode

```c
__int64 __fastcall HierarchicalCache::StoreApplicationIdentity(
        HierarchicalCache *this,
        const struct ShaderCacheApplicationIdentity *a2,
        char a3)
{
  char v6; // bl
  struct _Mtx_internal_imp_t *v8; // r13
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  char v12; // bl
  _QWORD *v13; // r14
  __int64 v14; // rdx
  __int64 v15; // rax
  char v16; // si
  char v17; // si
  _QWORD *v18; // rbx
  _QWORD *v19; // rax
  __int64 v20; // rax
  unsigned int v21; // ebx
  _BYTE v22[32]; // [rsp+28h] [rbp-58h] BYREF
  ShaderDiskCacheSQLite *v23[6]; // [rsp+48h] [rbp-38h] BYREF

  v6 = 0;
  if ( *((_BYTE *)this + 200) && a3 )
    return 2147942487LL;
  v8 = (HierarchicalCache *)((char *)this + 464);
  std::_Mutex_base::lock((HierarchicalCache *)((char *)this + 464));
  *(_OWORD *)((char *)this + 552) = *(_OWORD *)a2;
  *(_OWORD *)((char *)this + 568) = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 584) = *((_OWORD *)a2 + 2);
  if ( *((_BYTE *)this + 544) || !a3 )
  {
    if ( *(_QWORD *)a2 )
    {
      v9 = std::wstring::wstring(v23, *(_QWORD *)a2);
      v6 = 1;
    }
    else
    {
      v9 = std::wstring::wstring(v22);
      v6 = 2;
    }
    std::wstring::operator=((char *)this + 600, v9);
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      std::wstring::~wstring(v22);
    }
    if ( (v6 & 1) != 0 )
    {
      v6 &= ~1u;
      std::wstring::~wstring(v23);
    }
  }
  v10 = *((_QWORD *)a2 + 1);
  if ( v10 )
  {
    v11 = std::wstring::wstring(v22, v10);
    v12 = v6 | 4;
  }
  else
  {
    v11 = std::wstring::wstring(v23);
    v12 = v6 | 8;
  }
  v13 = (_QWORD *)((char *)this + 632);
  std::wstring::operator=((char *)this + 632, v11);
  if ( (v12 & 8) != 0 )
  {
    v12 &= ~8u;
    std::wstring::~wstring(v23);
  }
  if ( (v12 & 4) != 0 )
  {
    v12 &= ~4u;
    std::wstring::~wstring(v22);
  }
  v14 = *((_QWORD *)a2 + 2);
  if ( v14 )
  {
    v15 = std::wstring::wstring(v22, v14);
    v16 = 16;
  }
  else
  {
    v15 = std::wstring::wstring(v23);
    v16 = 32;
  }
  v17 = v12 | v16;
  v18 = (_QWORD *)((char *)this + 664);
  std::wstring::operator=((char *)this + 664, v15);
  if ( (v17 & 0x20) != 0 )
  {
    v17 &= ~0x20u;
    std::wstring::~wstring(v23);
  }
  if ( (v17 & 0x10) != 0 )
    std::wstring::~wstring(v22);
  if ( *((_QWORD *)this + 77) )
  {
    v19 = (_QWORD *)((char *)this + 600);
    if ( *((_QWORD *)this + 78) > 7u )
      v19 = (_QWORD *)*v19;
  }
  else
  {
    v19 = 0;
  }
  *((_QWORD *)this + 69) = v19;
  if ( *((_QWORD *)this + 81) )
  {
    if ( *((_QWORD *)this + 82) > 7u )
      v13 = (_QWORD *)*v13;
  }
  else
  {
    v13 = 0;
  }
  *((_QWORD *)this + 70) = v13;
  if ( *((_QWORD *)this + 85) )
  {
    if ( *((_QWORD *)this + 86) > 7u )
      v18 = (_QWORD *)*v18;
  }
  else
  {
    v18 = 0;
  }
  *((_QWORD *)this + 71) = v18;
  *((_BYTE *)this + 545) = 1;
  _Mtx_unlock(v8);
  if ( !a3 )
    return 0;
  v20 = RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::RetrieveForWrite((__int64)this + 208, (__int64)v23);
  v21 = ShaderDiskCacheSQLite::StoreApplicationIdentity(
          *(ShaderDiskCacheSQLite **)(v20 + 8),
          (HierarchicalCache *)((char *)this + 552));
  RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::~Accessor(v23);
  return v21;
}

```

## disassembly

```asm
0x180050a28  mov     [rsp-38h+arg_10], rbx
0x180050a2d  push    rbp
0x180050a2e  push    rsi
0x180050a2f  push    rdi
0x180050a30  push    r12
0x180050a32  push    r13
0x180050a34  push    r14
0x180050a36  push    r15
0x180050a38  mov     rbp, rsp
0x180050a3b  sub     rsp, 80h
0x180050a42  mov     rax, cs:__security_cookie
0x180050a49  xor     rax, rsp
0x180050a4c  mov     [rbp+var_8], rax
0x180050a50  mov     r15b, r8b
0x180050a53  mov     rsi, rdx
0x180050a56  mov     rdi, rcx
0x180050a59  xor     ebx, ebx
0x180050a5b  mov     dword ptr [rbp+var_60], ebx
0x180050a5e  cmp     [rcx+0C8h], bl
0x180050a64  jz      short loc_180050A75
0x180050a66  test    r8b, r8b
0x180050a69  jz      short loc_180050A75
0x180050a6b  mov     eax, 80070057h
0x180050a70  jmp     loc_180050C69
0x180050a75  lea     r13, [rcx+1D0h]
0x180050a7c  mov     [rbp+var_60], r13
0x180050a80  mov     rcx, r13; this
0x180050a83  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180050a88  nop
0x180050a89  lea     r12, [rdi+228h]
0x180050a90  movups  xmm0, xmmword ptr [rsi]
0x180050a93  movups  xmmword ptr [r12], xmm0
0x180050a98  movups  xmm1, xmmword ptr [rsi+10h]
0x180050a9c  movups  xmmword ptr [r12+10h], xmm1
0x180050aa2  movups  xmm0, xmmword ptr [rsi+20h]
0x180050aa6  movups  xmmword ptr [r12+20h], xmm0
0x180050aac  cmp     byte ptr [rdi+220h], 0
0x180050ab3  jnz     short loc_180050ABA
0x180050ab5  test    r15b, r15b
0x180050ab8  jnz     short loc_180050B11
0x180050aba  mov     rdx, [rsi]
0x180050abd  test    rdx, rdx
0x180050ac0  jz      short loc_180050AD2
0x180050ac2  lea     rcx, [rbp+var_38]
0x180050ac6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050acb  mov     ebx, 1
0x180050ad0  jmp     short loc_180050AE0
0x180050ad2  lea     rcx, [rbp+var_58]
0x180050ad6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180050adb  mov     ebx, 2
0x180050ae0  lea     rcx, [rdi+258h]
0x180050ae7  mov     rdx, rax
0x180050aea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180050aef  test    bl, 2
0x180050af2  jz      short loc_180050B00
0x180050af4  and     ebx, 0FFFFFFFDh
0x180050af7  lea     rcx, [rbp+var_58]
0x180050afb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050b00  test    bl, 1
0x180050b03  jz      short loc_180050B11
0x180050b05  and     ebx, 0FFFFFFFEh
0x180050b08  lea     rcx, [rbp+var_38]
0x180050b0c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050b11  mov     rdx, [rsi+8]
0x180050b15  test    rdx, rdx
0x180050b18  jz      short loc_180050B28
0x180050b1a  lea     rcx, [rbp+var_58]
0x180050b1e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050b23  or      ebx, 4
0x180050b26  jmp     short loc_180050B34
0x180050b28  lea     rcx, [rbp+var_38]
0x180050b2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180050b31  or      ebx, 8
0x180050b34  lea     r14, [rdi+278h]
0x180050b3b  mov     rdx, rax
0x180050b3e  mov     rcx, r14
0x180050b41  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180050b46  test    bl, 8
0x180050b49  jz      short loc_180050B57
0x180050b4b  and     ebx, 0FFFFFFF7h
0x180050b4e  lea     rcx, [rbp+var_38]
0x180050b52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050b57  test    bl, 4
0x180050b5a  jz      short loc_180050B68
0x180050b5c  and     ebx, 0FFFFFFFBh
0x180050b5f  lea     rcx, [rbp+var_58]
0x180050b63  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050b68  mov     rdx, [rsi+10h]
0x180050b6c  test    rdx, rdx
0x180050b6f  jz      short loc_180050B81
0x180050b71  lea     rcx, [rbp+var_58]
0x180050b75  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050b7a  mov     esi, 10h
0x180050b7f  jmp     short loc_180050B8F
0x180050b81  lea     rcx, [rbp+var_38]
0x180050b85  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180050b8a  mov     esi, 20h ; ' '
0x180050b8f  or      esi, ebx
0x180050b91  lea     rbx, [rdi+298h]
0x180050b98  mov     rdx, rax
0x180050b9b  mov     rcx, rbx
0x180050b9e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180050ba3  test    sil, 20h
0x180050ba7  jz      short loc_180050BB5
0x180050ba9  and     esi, 0FFFFFFDFh
0x180050bac  lea     rcx, [rbp+var_38]
0x180050bb0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050bb5  test    sil, 10h
0x180050bb9  jz      short loc_180050BC4
0x180050bbb  lea     rcx, [rbp+var_58]
0x180050bbf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050bc4  xor     esi, esi
0x180050bc6  cmp     [rdi+268h], rsi
0x180050bcd  jnz     short loc_180050BD3
0x180050bcf  mov     eax, esi
0x180050bd1  jmp     short loc_180050BE4
0x180050bd3  lea     rax, [rdi+258h]
0x180050bda  cmp     qword ptr [rax+18h], 7
0x180050bdf  jbe     short loc_180050BE4
0x180050be1  mov     rax, [rax]
0x180050be4  mov     [r12], rax
0x180050be8  cmp     [rdi+288h], rsi
0x180050bef  jnz     short loc_180050BF6
0x180050bf1  mov     r14, rsi
0x180050bf4  jmp     short loc_180050C00
0x180050bf6  cmp     qword ptr [r14+18h], 7
0x180050bfb  jbe     short loc_180050C00
0x180050bfd  mov     r14, [r14]
0x180050c00  mov     [rdi+230h], r14
0x180050c07  cmp     [rdi+2A8h], rsi
0x180050c0e  jnz     short loc_180050C15
0x180050c10  mov     rbx, rsi
0x180050c13  jmp     short loc_180050C1F
0x180050c15  cmp     qword ptr [rbx+18h], 7
0x180050c1a  jbe     short loc_180050C1F
0x180050c1c  mov     rbx, [rbx]
0x180050c1f  mov     [rdi+238h], rbx
0x180050c26  mov     byte ptr [rdi+221h], 1
0x180050c2d  mov     rcx, r13; _Mtx_t
0x180050c30  call    cs:__imp__Mtx_unlock
0x180050c36  test    r15b, r15b
0x180050c39  jz      short loc_180050C67
0x180050c3b  lea     rcx, [rdi+0D0h]
0x180050c42  lea     rdx, [rbp+var_38]
0x180050c46  call    ?RetrieveForWrite@?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA?AVAccessor@1@XZ; RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::RetrieveForWrite(void)
0x180050c4b  nop
0x180050c4c  mov     rdx, r12; struct ShaderCacheApplicationIdentity *
0x180050c4f  mov     rcx, [rax+8]; this
0x180050c53  call    ?StoreApplicationIdentity@ShaderDiskCacheSQLite@@QEAAJAEBUShaderCacheApplicationIdentity@@@Z; ShaderDiskCacheSQLite::StoreApplicationIdentity(ShaderCacheApplicationIdentity const &)
0x180050c58  mov     ebx, eax
0x180050c5a  lea     rcx, [rbp+var_38]
0x180050c5e  call    ??1Accessor@?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA@XZ; RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::~Accessor(void)
0x180050c63  mov     eax, ebx
0x180050c65  jmp     short loc_180050C69
0x180050c67  xor     eax, eax
0x180050c69  mov     rcx, [rbp+var_8]
0x180050c6d  xor     rcx, rsp; StackCookie
0x180050c70  call    __security_check_cookie
0x180050c75  mov     rbx, [rsp+80h+arg_10]
0x180050c7d  add     rsp, 80h
0x180050c84  pop     r15
0x180050c86  pop     r14
0x180050c88  pop     r13
0x180050c8a  pop     r12
0x180050c8c  pop     rdi
0x180050c8d  pop     rsi
0x180050c8e  pop     rbp
0x180050c8f  retn
```
