# CMILResourceCache::GetResource(ulong,IMILCacheableResource * *)

- ea: `0x18002ec80`
- end: `0x18002ed91`
- name: `?GetResource@CMILResourceCache@@UEAAJKPEAPEAUIMILCacheableResource@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(CMILResourceCache *__hidden this, unsigned int, struct IMILCacheableResource **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002ec80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002ecd4`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002ed0f`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002ecd4`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002ed0f`

## pseudocode

```c
__int64 __fastcall CMILResourceCache::GetResource(CMILResourceCache *this, unsigned int a2, void ****a3)
{
  __int64 v4; // rbx
  int v7; // eax
  int i; // eax
  __int64 v9; // r14
  __int64 v10; // rsi
  void ***v11; // rbx
  char v12; // al
  void **v13; // rdx

  v4 = a2;
  if ( g_tagNoCaching )
    return 2147500037LL;
  v7 = _InterlockedIncrement((volatile signed __int32 *)this + 14);
  if ( v7 < 0 )
  {
    if ( (v7 & 0x40000000) != 0 )
      return 2147942405LL;
    for ( i = *((_DWORD *)this + 14); i < 0; i = *((_DWORD *)this + 14) )
      SleepEx(0, 1);
  }
  *a3 = 0;
  if ( (unsigned int)v4 < *((_DWORD *)this + 8) )
  {
    v9 = *((_QWORD *)this + 1);
    v10 = v4;
    do
    {
      v11 = *(void ****)(v9 + 8 * v10);
      if ( v11 == &g_MILCacheableResourceDummy )
      {
        SleepEx(0, 1);
        v11 = 0;
      }
    }
    while ( v11 != (void ***)_InterlockedCompareExchange64(
                               (volatile signed __int64 *)(v9 + 8 * v10),
                               (signed __int64)&g_MILCacheableResourceDummy,
                               (signed __int64)v11) );
    if ( v11 )
    {
      v12 = ((__int64 (__fastcall *)(void ***))(*v11)[4])(v11);
      v13 = *v11;
      if ( v12 )
      {
        ((void (__fastcall *)(void ***))*v13)(v11);
        *a3 = v11;
      }
      else
      {
        ((void (__fastcall *)(void ***))v13[3])(v11);
        v11 = 0;
      }
    }
    if ( &g_MILCacheableResourceDummy != (void ***)_InterlockedCompareExchange64(
                                                     (volatile signed __int64 *)(v9 + 8 * v10),
                                                     (signed __int64)v11,
                                                     (signed __int64)&g_MILCacheableResourceDummy) )
    {
      if ( v11 )
        ((void (__fastcall *)(void ***))(*v11)[3])(v11);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 14);
  return 0;
}

```

## disassembly

```asm
0x18002ec80  push    rbx
0x18002ec82  push    rsi
0x18002ec83  push    rdi
0x18002ec84  push    r12
0x18002ec86  push    r14
0x18002ec88  push    r15
0x18002ec8a  sub     rsp, 28h
0x18002ec8e  cmp     cs:?g_tagNoCaching@@3_NA, 0; bool g_tagNoCaching
0x18002ec95  mov     r15, r8
0x18002ec98  mov     ebx, edx
0x18002ec9a  mov     rdi, rcx
0x18002ec9d  jz      short loc_18002ECA9
0x18002ec9f  mov     eax, 80004005h
0x18002eca4  jmp     loc_18002ED83
0x18002eca9  mov     eax, 1
0x18002ecae  lock xadd [rcx+38h], eax
0x18002ecb3  add     eax, 1
0x18002ecb6  jns     short loc_18002ECE1
0x18002ecb8  bt      eax, 1Eh
0x18002ecbc  jnb     short loc_18002ECC8
0x18002ecbe  mov     eax, 80070005h
0x18002ecc3  jmp     loc_18002ED83
0x18002ecc8  mov     eax, [rcx+38h]
0x18002eccb  jmp     short loc_18002ECDD
0x18002eccd  mov     edx, 1; bAlertable
0x18002ecd2  xor     ecx, ecx; dwMilliseconds
0x18002ecd4  call    cs:__imp_SleepEx
0x18002ecda  mov     eax, [rdi+38h]
0x18002ecdd  test    eax, eax
0x18002ecdf  js      short loc_18002ECCD
0x18002ece1  mov     qword ptr [r15], 0
0x18002ece8  cmp     ebx, [rdi+20h]
0x18002eceb  jnb     loc_18002ED7D
0x18002ecf1  mov     r14, [rdi+8]
0x18002ecf5  lea     r12, ?g_MILCacheableResourceDummy@@3VCMILCacheableResourceDummy@@A; CMILCacheableResourceDummy g_MILCacheableResourceDummy
0x18002ecfc  mov     rsi, rbx
0x18002ecff  mov     rbx, [r14+rsi*8]
0x18002ed03  cmp     rbx, r12
0x18002ed06  jnz     short loc_18002ED17
0x18002ed08  mov     edx, 1; bAlertable
0x18002ed0d  xor     ecx, ecx; dwMilliseconds
0x18002ed0f  call    cs:__imp_SleepEx
0x18002ed15  xor     ebx, ebx
0x18002ed17  mov     rax, rbx
0x18002ed1a  lock cmpxchg [r14+rsi*8], r12
0x18002ed20  cmp     rbx, rax
0x18002ed23  jnz     short loc_18002ECFF
0x18002ed25  test    rbx, rbx
0x18002ed28  jz      short loc_18002ED5B
0x18002ed2a  mov     rax, [rbx]
0x18002ed2d  mov     rcx, rbx
0x18002ed30  mov     rax, [rax+20h]
0x18002ed34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed39  mov     rdx, [rbx]
0x18002ed3c  mov     rcx, rbx
0x18002ed3f  test    al, al
0x18002ed41  jz      short loc_18002ED50
0x18002ed43  mov     rax, [rdx]
0x18002ed46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed4b  mov     [r15], rbx
0x18002ed4e  jmp     short loc_18002ED5B
0x18002ed50  mov     rax, [rdx+18h]
0x18002ed54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed59  xor     ebx, ebx
0x18002ed5b  mov     rax, r12
0x18002ed5e  lock cmpxchg [r14+rsi*8], rbx
0x18002ed64  cmp     r12, rax
0x18002ed67  jz      short loc_18002ED7D
0x18002ed69  test    rbx, rbx
0x18002ed6c  jz      short loc_18002ED7D
0x18002ed6e  mov     rax, [rbx]
0x18002ed71  mov     rcx, rbx
0x18002ed74  mov     rax, [rax+18h]
0x18002ed78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed7d  lock dec dword ptr [rdi+38h]
0x18002ed81  xor     eax, eax
0x18002ed83  add     rsp, 28h
0x18002ed87  pop     r15
0x18002ed89  pop     r14
0x18002ed8b  pop     r12
0x18002ed8d  pop     rdi
0x18002ed8e  pop     rsi
0x18002ed8f  pop     rbx
0x18002ed90  retn
```
