# Streaming::MDLCache::FreeMDL(kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)

- ea: `0x14000d054`
- end: `0x14000d0c0`
- name: `?FreeMDL@MDLCache@Streaming@@QEAAXAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x14000c4ac`
- `0x1400115cc`

## callees

- `0x14000d054`
- `0x14000d0c8`
- `0x14000d4bc`

## pseudocode

```c
void __fastcall Streaming::MDLCache::FreeMDL(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  char *v3; // rcx
  unsigned int v4; // r8d

  if ( *a2 )
  {
    v2 = a2[1];
    if ( v2 )
    {
      v3 = (char *)Streaming::staging_operations::gMDLCache;
      if ( *(_DWORD *)(v2 + 8) )
      {
        v4 = *(_DWORD *)(*a2 + 48);
        if ( v4 <= 0x1000 )
        {
LABEL_9:
          Streaming::MDLListCache::FreeMDL((__int64)v3, a2);
          return;
        }
        if ( v4 <= 0x20000 )
        {
          v3 = (char *)Streaming::staging_operations::gMDLCache + 256;
          goto LABEL_9;
        }
        if ( v4 <= 0x100000 )
        {
          v3 = (char *)Streaming::staging_operations::gMDLCache + 512;
          goto LABEL_9;
        }
        Streaming::MDLList::Remove((char *)Streaming::staging_operations::gMDLCache + 768, a2);
      }
    }
  }
}

```

## disassembly

```asm
0x14000d054  sub     rsp, 28h
0x14000d058  cmp     qword ptr [rdx], 0
0x14000d05c  jz      short loc_14000D0BA
0x14000d05e  mov     rax, [rdx+8]
0x14000d062  test    rax, rax
0x14000d065  jz      short loc_14000D0BA
0x14000d067  mov     eax, [rax+8]
0x14000d06a  mov     rcx, cs:?gMDLCache@staging_operations@Streaming@@3PEAVMDLCache@2@EA; Streaming::MDLCache * Streaming::staging_operations::gMDLCache
0x14000d071  test    eax, eax
0x14000d073  jz      short loc_14000D0BA
0x14000d075  mov     rax, [rdx]
0x14000d078  mov     r8d, [rax+30h]
0x14000d07c  cmp     r8d, 1000h
0x14000d083  jbe     short loc_14000D0A7
0x14000d085  cmp     r8d, 20000h
0x14000d08c  ja      short loc_14000D097
0x14000d08e  add     rcx, 100h
0x14000d095  jmp     short loc_14000D0A7
0x14000d097  cmp     r8d, 100000h
0x14000d09e  ja      short loc_14000D0AE
0x14000d0a0  add     rcx, 200h
0x14000d0a7  call    ?FreeMDL@MDLListCache@Streaming@@QEAAJAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z; Streaming::MDLListCache::FreeMDL(kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)
0x14000d0ac  jmp     short loc_14000D0BA
0x14000d0ae  add     rcx, 300h
0x14000d0b5  call    ?Remove@MDLList@Streaming@@QEAAJAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z; Streaming::MDLList::Remove(kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)
0x14000d0ba  add     rsp, 28h
0x14000d0be  retn
```
