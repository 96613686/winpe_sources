# std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x18001b528`
- end: `0x18001b5c3`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEBA_K_K@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016b6c`
- `0x180016d30`
- `0x18001740c`
- `0x18002833c`
- `0x18002eee8`

## callees

- `0x1800047b4`
- `0x18001b528`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Desired_grow_bucket_count(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v2; // rbx
  float v3; // xmm0_4
  float v4; // xmm0_4
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx

  v2 = *(_QWORD *)(a1 + 56);
  if ( a2 < 0 )
    v3 = (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1))
       + (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1));
  else
    v3 = (float)(int)a2;
  v4 = o_ceilf_0(v3 / *(float *)a1);
  v5 = 0;
  if ( v4 >= 9.223372e18 )
  {
    v4 = v4 - 9.223372e18;
    if ( v4 < 9.223372e18 )
      v5 = 0x8000000000000000uLL;
  }
  v6 = 8;
  if ( v5 + (unsigned int)(int)v4 > 8 )
    v6 = v5 + (unsigned int)(int)v4;
  if ( v2 >= v6 )
    return v2;
  if ( v2 < 0x200 && 8 * v2 >= v6 )
    return 8 * v2;
  return v6;
}

```

## disassembly

```asm
0x18001b528  push    rbx
0x18001b52a  sub     rsp, 20h
0x18001b52e  mov     rbx, [rcx+38h]
0x18001b532  xorps   xmm0, xmm0
0x18001b535  test    rdx, rdx
0x18001b538  js      short loc_18001B541
0x18001b53a  cvtsi2ss xmm0, rdx
0x18001b53f  jmp     short loc_18001B556
0x18001b541  mov     rax, rdx
0x18001b544  and     edx, 1
0x18001b547  shr     rax, 1
0x18001b54a  or      rax, rdx
0x18001b54d  cvtsi2ss xmm0, rax
0x18001b552  addss   xmm0, xmm0
0x18001b556  divss   xmm0, dword ptr [rcx]; X
0x18001b55a  call    _o_ceilf_0
0x18001b55f  movss   xmm1, cs:__real@5f000000
0x18001b567  xor     eax, eax
0x18001b569  comiss  xmm0, xmm1
0x18001b56c  jb      short loc_18001B584
0x18001b56e  subss   xmm0, xmm1
0x18001b572  comiss  xmm0, xmm1
0x18001b575  jnb     short loc_18001B584
0x18001b577  mov     rcx, 8000000000000000h
0x18001b581  mov     rax, rcx
0x18001b584  mov     edx, 8
0x18001b589  cvttss2si rcx, xmm0
0x18001b58e  add     rcx, rax
0x18001b591  cmp     rcx, rdx
0x18001b594  cmova   rdx, rcx
0x18001b598  cmp     rbx, rdx
0x18001b59b  jb      short loc_18001B5A2
0x18001b59d  mov     rax, rbx
0x18001b5a0  jmp     short loc_18001B5BD
0x18001b5a2  cmp     rbx, 200h
0x18001b5a9  jnb     short loc_18001B5BA
0x18001b5ab  lea     rax, ds:0[rbx*8]
0x18001b5b3  cmp     rax, rdx
0x18001b5b6  cmovnb  rdx, rax
0x18001b5ba  mov     rax, rdx
0x18001b5bd  add     rsp, 20h
0x18001b5c1  pop     rbx
0x18001b5c2  retn
```
