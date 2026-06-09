# std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x180010f00`
- end: `0x180010f9b`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fe60`

## callees

- `0x1800056a4`
- `0x180010f00`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Desired_grow_bucket_count(
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
0x180010f00  push    rbx
0x180010f02  sub     rsp, 20h
0x180010f06  mov     rbx, [rcx+38h]
0x180010f0a  xorps   xmm0, xmm0
0x180010f0d  test    rdx, rdx
0x180010f10  js      short loc_180010F19
0x180010f12  cvtsi2ss xmm0, rdx
0x180010f17  jmp     short loc_180010F2E
0x180010f19  mov     rax, rdx
0x180010f1c  and     edx, 1
0x180010f1f  shr     rax, 1
0x180010f22  or      rax, rdx
0x180010f25  cvtsi2ss xmm0, rax
0x180010f2a  addss   xmm0, xmm0
0x180010f2e  divss   xmm0, dword ptr [rcx]; X
0x180010f32  call    _o_ceilf_0
0x180010f37  movss   xmm1, cs:__real@5f000000
0x180010f3f  xor     eax, eax
0x180010f41  comiss  xmm0, xmm1
0x180010f44  jb      short loc_180010F5C
0x180010f46  subss   xmm0, xmm1
0x180010f4a  comiss  xmm0, xmm1
0x180010f4d  jnb     short loc_180010F5C
0x180010f4f  mov     rcx, 8000000000000000h
0x180010f59  mov     rax, rcx
0x180010f5c  mov     edx, 8
0x180010f61  cvttss2si rcx, xmm0
0x180010f66  add     rcx, rax
0x180010f69  cmp     rcx, rdx
0x180010f6c  cmova   rdx, rcx
0x180010f70  cmp     rbx, rdx
0x180010f73  jb      short loc_180010F7A
0x180010f75  mov     rax, rbx
0x180010f78  jmp     short loc_180010F95
0x180010f7a  cmp     rbx, 200h
0x180010f81  jnb     short loc_180010F92
0x180010f83  lea     rax, ds:0[rbx*8]
0x180010f8b  cmp     rax, rdx
0x180010f8e  cmovnb  rdx, rax
0x180010f92  mov     rax, rdx
0x180010f95  add     rsp, 20h
0x180010f99  pop     rbx
0x180010f9a  retn
```
