# CMidi2DiagnosticsPluginMetadataProvider::`scalar deleting destructor'(uint)

- ea: `0x18000b990`
- end: `0x18000b9b8`
- name: `??_GCMidi2DiagnosticsPluginMetadataProvider@@UEAAPEAXI@Z`
- size: `40`
- prototype: `void *__fastcall(CMidi2DiagnosticsPluginMetadataProvider *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x1800033f4`
- `0x18000b990`

## pseudocode

```c
CMidi2DiagnosticsPluginMetadataProvider *__fastcall CMidi2DiagnosticsPluginMetadataProvider::`scalar deleting destructor'(
        CMidi2DiagnosticsPluginMetadataProvider *this,
        char a2)
{
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b990  push    rbx
0x18000b992  sub     rsp, 20h
0x18000b996  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000b99d  mov     rbx, rcx
0x18000b9a0  test    dl, 1
0x18000b9a3  jz      short loc_18000B9AF
0x18000b9a5  mov     edx, 20h ; ' '
0x18000b9aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b9af  mov     rax, rbx
0x18000b9b2  add     rsp, 20h
0x18000b9b6  pop     rbx
0x18000b9b7  retn
```
