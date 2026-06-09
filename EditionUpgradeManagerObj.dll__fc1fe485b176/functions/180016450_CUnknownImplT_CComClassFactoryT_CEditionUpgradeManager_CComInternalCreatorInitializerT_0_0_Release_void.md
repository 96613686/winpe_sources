# CUnknownImplT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::Release(void)

- ea: `0x180016450`
- end: `0x18001647a`
- name: `?Release@?$CUnknownImplT@V?$CComClassFactoryT@VCEditionUpgradeManager@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@UEAAKXZ`
- size: `42`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e90`
- `0x180016450`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::Release(
        volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 )
  {
    operator delete((void *)a1);
    _InterlockedDecrement(&CComProcessCounter<0>::g_lServerLockCount);
  }
  return v1;
}

```

## disassembly

```asm
0x180016450  push    rbx
0x180016452  sub     rsp, 20h
0x180016456  or      ebx, 0FFFFFFFFh
0x180016459  lock xadd [rcx+8], ebx
0x18001645e  sub     ebx, 1
0x180016461  jnz     short loc_180016472
0x180016463  lea     edx, [rbx+10h]; unsigned __int64
0x180016466  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001646b  lock dec cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x180016472  mov     eax, ebx
0x180016474  add     rsp, 20h
0x180016478  pop     rbx
0x180016479  retn
```
