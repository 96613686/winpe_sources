# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x18000d6d0`
- end: `0x18000d772`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ac1c`

## callees

- `0x180001f94`
- `0x18000d6d0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Desired_grow_bucket_count(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v2; // rbx
  float v3; // xmm0_4
  float v4; // xmm0_4
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx

  v2 = qword_1800165A8;
  if ( a2 < 0 )
    v3 = (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1))
       + (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1));
  else
    v3 = (float)(int)a2;
  v4 = o_ceilf_0(v3 / *(float *)&AppMon::PortManager::m_openedHandleTable);
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
0x18000d6d0  push    rbx
0x18000d6d2  sub     rsp, 20h
0x18000d6d6  mov     rbx, cs:qword_1800165A8
0x18000d6dd  xorps   xmm0, xmm0
0x18000d6e0  test    rdx, rdx
0x18000d6e3  js      short loc_18000D6EC
0x18000d6e5  cvtsi2ss xmm0, rdx
0x18000d6ea  jmp     short loc_18000D701
0x18000d6ec  mov     rax, rdx
0x18000d6ef  and     edx, 1
0x18000d6f2  shr     rax, 1
0x18000d6f5  or      rax, rdx
0x18000d6f8  cvtsi2ss xmm0, rax
0x18000d6fd  addss   xmm0, xmm0
0x18000d701  divss   xmm0, cs:?m_openedHandleTable@PortManager@AppMon@@0V?$unordered_map@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@U?$hash@PEAX@2@U?$equal_to@PEAX@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@@std@@A; X
0x18000d709  call    _o_ceilf_0
0x18000d70e  movss   xmm1, cs:__real@5f000000
0x18000d716  xor     eax, eax
0x18000d718  comiss  xmm0, xmm1
0x18000d71b  jb      short loc_18000D733
0x18000d71d  subss   xmm0, xmm1
0x18000d721  comiss  xmm0, xmm1
0x18000d724  jnb     short loc_18000D733
0x18000d726  mov     rcx, 8000000000000000h
0x18000d730  mov     rax, rcx
0x18000d733  mov     edx, 8
0x18000d738  cvttss2si rcx, xmm0
0x18000d73d  add     rcx, rax
0x18000d740  cmp     rcx, rdx
0x18000d743  cmova   rdx, rcx
0x18000d747  cmp     rbx, rdx
0x18000d74a  jb      short loc_18000D751
0x18000d74c  mov     rax, rbx
0x18000d74f  jmp     short loc_18000D76C
0x18000d751  cmp     rbx, 200h
0x18000d758  jnb     short loc_18000D769
0x18000d75a  lea     rax, ds:0[rbx*8]
0x18000d762  cmp     rax, rdx
0x18000d765  cmovnb  rdx, rax
0x18000d769  mov     rax, rdx
0x18000d76c  add     rsp, 20h
0x18000d770  pop     rbx
0x18000d771  retn
```
