# SmartPtr<IBackgroundCopyJob>::operator&(void)

- ea: `0x18001cab8`
- end: `0x18001cad4`
- name: `??I?$SmartPtr@UIBackgroundCopyJob@@@@QEAAPEAPEAUIBackgroundCopyJob@@XZ`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001cb10`
- `0x18001d000`
- `0x18001ed00`

## callees

- `0x18001c328`

## pseudocode

```c
__int64 __fastcall SmartPtr<IBackgroundCopyJob>::operator&(__int64 a1)
{
  __int64 v1; // rbx

  v1 = a1 + 8;
  ATL::CComPtr<IBackgroundCopyJob>::Release(a1 + 8);
  return v1;
}

```

## disassembly

```asm
0x18001cab8  push    rbx
0x18001caba  sub     rsp, 20h
0x18001cabe  lea     rbx, [rcx+8]
0x18001cac2  mov     rcx, rbx
0x18001cac5  call    ?Release@?$CComPtr@UIBackgroundCopyJob@@@ATL@@QEAAXXZ; ATL::CComPtr<IBackgroundCopyJob>::Release(void)
0x18001caca  mov     rax, rbx
0x18001cacd  add     rsp, 20h
0x18001cad1  pop     rbx
0x18001cad2  retn
```
