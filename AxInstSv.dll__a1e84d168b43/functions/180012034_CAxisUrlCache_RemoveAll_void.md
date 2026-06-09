# CAxisUrlCache::RemoveAll(void)

- ea: `0x180012034`
- end: `0x1800120e6`
- name: `?RemoveAll@CAxisUrlCache@@QEAAJXZ`
- size: `178`
- prototype: `__int64 __fastcall(CAxisUrlCache *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011c74`

## callees

- `0x180004afc`
- `0x180011ab0`
- `0x180011b8c`
- `0x180011cb0`
- `0x180012034`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180012055`
- `ntdll!RtlAcquireResourceExclusive` at `0x180012055`
- `ntdll!RtlReleaseResource` at `0x18001209d`
- `ntdll!RtlReleaseResource` at `0x18001209d`

## pseudocode

```c
__int64 __fastcall CAxisUrlCache::RemoveAll(CAxisUrlCache *this)
{
  __int64 ***v2; // rdi
  __int64 *v3; // rdx
  CAxISUrlEntry *v4; // rsi
  __int64 *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // edx
  __int64 **v8; // rbx

  if ( *((_DWORD *)this + 6) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 32), 1u);
    v2 = (__int64 ***)((char *)this + 8);
    do
    {
      v3 = **v2;
      if ( v3 == (__int64 *)*v2 )
        break;
      v4 = (CAxISUrlEntry *)v3[5];
      v5 = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Extract(
             (__int64 **)this + 1,
             v3);
      std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(
        v6,
        v5);
      if ( v4 )
        CAxISUrlEntry::`scalar deleting destructor'(v4, v7);
    }
    while ( *((_QWORD *)this + 2) );
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 32));
    v8 = *v2;
    std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(
      (char *)this + 8,
      (char *)this + 8,
      (*v2)[1]);
    v8[1] = (__int64 *)v8;
    *v8 = (__int64 *)v8;
    v8[2] = (__int64 *)v8;
    *((_QWORD *)this + 2) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180012034  mov     [rsp+arg_10], rbx
0x180012039  push    rsi
0x18001203a  push    rdi
0x18001203b  push    r14
0x18001203d  sub     rsp, 30h
0x180012041  mov     r14, rcx
0x180012044  xor     esi, esi
0x180012046  cmp     [rcx+18h], esi
0x180012049  jz      loc_1800120D6
0x18001204f  mov     dl, 1; Wait
0x180012051  add     rcx, 20h ; ' '; Resource
0x180012055  call    cs:__imp_RtlAcquireResourceExclusive
0x18001205b  lea     rdi, [r14+8]
0x18001205f  mov     [rsp+48h+arg_8], rdi
0x180012064  mov     rax, [rdi]
0x180012067  mov     rdx, [rax]
0x18001206a  cmp     rdx, rax
0x18001206d  jz      short loc_180012097
0x18001206f  mov     rsi, [rdx+28h]
0x180012073  mov     rcx, rdi
0x180012076  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>)
0x18001207b  mov     rdx, rax
0x18001207e  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>> &,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x180012083  test    rsi, rsi
0x180012086  jz      short loc_180012090
0x180012088  mov     rcx, rsi; this
0x18001208b  call    ??_GCAxISUrlEntry@@QEAAPEAXI@Z; CAxISUrlEntry::`scalar deleting destructor'(uint)
0x180012090  cmp     qword ptr [r14+10h], 0
0x180012095  jnz     short loc_180012064
0x180012097  xor     esi, esi
0x180012099  lea     rcx, [r14+20h]; Resource
0x18001209d  call    cs:__imp_RtlReleaseResource
0x1800120a3  nop
0x1800120a4  jmp     short loc_1800120B1
0x1800120a6  jmp     short $+2
0x1800120a8  mov     rdi, [rsp+48h+arg_8]
0x1800120ad  mov     esi, [rsp+48h+arg_0]
0x1800120b1  mov     rbx, [rdi]
0x1800120b4  mov     r8, [rbx+8]
0x1800120b8  mov     rdx, rdi
0x1800120bb  mov     rcx, rdi
0x1800120be  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>> &,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x1800120c3  mov     [rbx+8], rbx
0x1800120c7  mov     [rbx], rbx
0x1800120ca  mov     [rbx+10h], rbx
0x1800120ce  mov     qword ptr [rdi+8], 0
0x1800120d6  mov     eax, esi
0x1800120d8  mov     rbx, [rsp+48h+arg_10]
0x1800120dd  add     rsp, 30h
0x1800120e1  pop     r14
0x1800120e3  pop     rdi
0x1800120e4  pop     rsi
0x1800120e5  retn
```
