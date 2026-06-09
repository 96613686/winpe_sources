# CNetworkExplorerFolderViewCB::_StopProgressBar(void)

- ea: `0x18000693c`
- end: `0x18000696c`
- name: `?_StopProgressBar@CNetworkExplorerFolderViewCB@@AEAAJXZ`
- size: `48`
- prototype: `__int64 __fastcall(CNetworkExplorerFolderViewCB *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800066f4`
- `0x1800069c0`
- `0x18000cc44`

## callees

- `0x18000693c`
- `0x18000df84`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolderViewCB::_StopProgressBar(
        CNetworkExplorerFolderViewCB *this,
        const struct _GUID *a2)
{
  __int64 result; // rax
  unsigned int v4; // ecx
  unsigned int v5; // r8d

  result = 2147500037LL;
  v4 = *((_DWORD *)this + 8);
  if ( v4 )
  {
    v5 = *((_DWORD *)this + 9);
    if ( v5 )
    {
      result = GIT_UnregisterProgress(v4, a2, v5);
      *((_DWORD *)this + 9) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000693c  push    rbx
0x18000693e  sub     rsp, 20h
0x180006942  mov     rbx, rcx
0x180006945  mov     eax, 80004005h
0x18000694a  mov     ecx, [rcx+20h]; unsigned int
0x18000694d  test    ecx, ecx
0x18000694f  jz      short loc_180006966
0x180006951  mov     r8d, [rbx+24h]; unsigned int
0x180006955  test    r8d, r8d
0x180006958  jz      short loc_180006966
0x18000695a  call    ?GIT_UnregisterProgress@@YAJKAEBU_GUID@@K@Z; GIT_UnregisterProgress(ulong,_GUID const &,ulong)
0x18000695f  mov     dword ptr [rbx+24h], 0
0x180006966  add     rsp, 20h
0x18000696a  pop     rbx
0x18000696b  retn
```
