# CMILResourceCache::SetResource(ulong,IMILCacheableResource *)

- ea: `0x18001ec70`
- end: `0x18001ed4e`
- name: `?SetResource@CMILResourceCache@@UEAAJKPEAUIMILCacheableResource@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(CMILResourceCache *__hidden this, unsigned int, struct IMILCacheableResource *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800171c4`
- `0x18001ec70`
- `0x18001ed54`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18001ecbf`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18001ecbf`

## pseudocode

```c
__int64 __fastcall CMILResourceCache::SetResource(
        CMILResourceCache *this,
        unsigned int a2,
        struct IMILCacheableResource *a3)
{
  __int64 v4; // rbp
  int v7; // eax
  int i; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // r14
  __int64 v12; // rsi

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
  v9 = 0;
  if ( (unsigned int)v4 >= *((_DWORD *)this + 8) )
  {
    v10 = CMILResourceCache::EnsureCount(this, (int)v4 + 1);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_20;
      goto LABEL_16;
    }
  }
  v11 = *((_QWORD *)this + 1);
  if ( !a3
    || (v10 = (*(__int64 (__fastcall **)(struct IMILCacheableResource *))(*(_QWORD *)a3 + 16LL))(a3), v9 = v10, v10 >= 0) )
  {
    v12 = _InterlockedExchange64((volatile __int64 *)(v11 + 8 * v4), (__int64)a3);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
    goto LABEL_20;
  }
  if ( g_doStackCaptures )
LABEL_16:
    DoStackCapture(v10);
LABEL_20:
  _InterlockedDecrement((volatile signed __int32 *)this + 14);
  return v9;
}

```

## disassembly

```asm
0x18001ec70  push    rbx
0x18001ec72  push    rbp
0x18001ec73  push    rsi
0x18001ec74  push    rdi
0x18001ec75  push    r14
0x18001ec77  sub     rsp, 20h
0x18001ec7b  cmp     cs:?g_tagNoCaching@@3_NA, 0; bool g_tagNoCaching
0x18001ec82  mov     rsi, r8
0x18001ec85  mov     ebp, edx
0x18001ec87  mov     rdi, rcx
0x18001ec8a  jz      short loc_18001EC96
0x18001ec8c  mov     eax, 80004005h
0x18001ec91  jmp     loc_18001ED43
0x18001ec96  mov     ebx, 1
0x18001ec9b  mov     eax, ebx
0x18001ec9d  lock xadd [rcx+38h], eax
0x18001eca2  add     eax, ebx
0x18001eca4  jns     short loc_18001ECCC
0x18001eca6  bt      eax, 1Eh
0x18001ecaa  jnb     short loc_18001ECB6
0x18001ecac  mov     eax, 80070005h
0x18001ecb1  jmp     loc_18001ED43
0x18001ecb6  mov     eax, [rcx+38h]
0x18001ecb9  jmp     short loc_18001ECC8
0x18001ecbb  mov     edx, ebx; bAlertable
0x18001ecbd  xor     ecx, ecx; dwMilliseconds
0x18001ecbf  call    cs:__imp_SleepEx
0x18001ecc5  mov     eax, [rdi+38h]
0x18001ecc8  test    eax, eax
0x18001ecca  js      short loc_18001ECBB
0x18001eccc  xor     ebx, ebx
0x18001ecce  cmp     ebp, [rdi+20h]
0x18001ecd1  jb      short loc_18001ECF1
0x18001ecd3  lea     edx, [rbp+1]; unsigned int
0x18001ecd6  mov     rcx, rdi; this
0x18001ecd9  call    ?EnsureCount@CMILResourceCache@@IEAAJI@Z; CMILResourceCache::EnsureCount(uint)
0x18001ecde  mov     ebx, eax
0x18001ece0  test    eax, eax
0x18001ece2  jns     short loc_18001ECF1
0x18001ece4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001eceb  jnz     short loc_18001ED18
0x18001eced  test    eax, eax
0x18001ecef  js      short loc_18001ED3D
0x18001ecf1  mov     r14, [rdi+8]
0x18001ecf5  test    rsi, rsi
0x18001ecf8  jz      short loc_18001ED25
0x18001ecfa  mov     rax, [rsi]
0x18001ecfd  mov     rcx, rsi
0x18001ed00  mov     rax, [rax+10h]
0x18001ed04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed09  mov     ebx, eax
0x18001ed0b  test    eax, eax
0x18001ed0d  jns     short loc_18001ED25
0x18001ed0f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001ed16  jz      short loc_18001ED21
0x18001ed18  mov     ecx, eax; int
0x18001ed1a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001ed1f  jmp     short loc_18001ED3D
0x18001ed21  test    eax, eax
0x18001ed23  js      short loc_18001ED3D
0x18001ed25  xchg    rsi, [r14+rbp*8]
0x18001ed29  test    rsi, rsi
0x18001ed2c  jz      short loc_18001ED3D
0x18001ed2e  mov     rdx, [rsi]
0x18001ed31  mov     rcx, rsi
0x18001ed34  mov     rax, [rdx+18h]
0x18001ed38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed3d  lock dec dword ptr [rdi+38h]
0x18001ed41  mov     eax, ebx
0x18001ed43  add     rsp, 20h
0x18001ed47  pop     r14
0x18001ed49  pop     rdi
0x18001ed4a  pop     rsi
0x18001ed4b  pop     rbp
0x18001ed4c  pop     rbx
0x18001ed4d  retn
```
