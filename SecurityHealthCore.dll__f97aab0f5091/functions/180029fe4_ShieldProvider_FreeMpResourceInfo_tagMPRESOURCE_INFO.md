# ShieldProvider::FreeMpResourceInfo(tagMPRESOURCE_INFO *)

- ea: `0x180029fe4`
- end: `0x18002a02c`
- name: `?FreeMpResourceInfo@ShieldProvider@@YAXPEAUtagMPRESOURCE_INFO@@@Z`
- size: `72`
- prototype: `void __fastcall(ShieldProvider *__hidden this, struct tagMPRESOURCE_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002a034`
- `0x180034f1c`

## callees

- `0x180029fe4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180029ff9`
- `ole32!CoTaskMemFree` at `0x18002a008`
- `ole32!CoTaskMemFree` at `0x18002a017`
- `ole32!CoTaskMemFree` at `0x18002a020`
- `ole32!CoTaskMemFree` at `0x180029ff9`
- `ole32!CoTaskMemFree` at `0x18002a008`
- `ole32!CoTaskMemFree` at `0x18002a017`
- `ole32!CoTaskMemFree` at `0x18002a020`

## pseudocode

```c
void __fastcall ShieldProvider::FreeMpResourceInfo(ShieldProvider *this, struct tagMPRESOURCE_INFO *a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  if ( this )
  {
    v3 = *(void **)this;
    if ( v3 )
      CoTaskMemFree(v3);
    v4 = (void *)*((_QWORD *)this + 1);
    if ( v4 )
      CoTaskMemFree(v4);
    v5 = (void *)*((_QWORD *)this + 3);
    if ( v5 )
      CoTaskMemFree(v5);
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x180029fe4  test    rcx, rcx
0x180029fe7  jz      short locret_18002A02B
0x180029fe9  push    rbx
0x180029fea  sub     rsp, 20h
0x180029fee  mov     rbx, rcx
0x180029ff1  mov     rcx, [rcx]; pv
0x180029ff4  test    rcx, rcx
0x180029ff7  jz      short loc_180029FFF
0x180029ff9  call    cs:__imp_CoTaskMemFree
0x180029fff  mov     rcx, [rbx+8]; pv
0x18002a003  test    rcx, rcx
0x18002a006  jz      short loc_18002A00E
0x18002a008  call    cs:__imp_CoTaskMemFree
0x18002a00e  mov     rcx, [rbx+18h]; pv
0x18002a012  test    rcx, rcx
0x18002a015  jz      short loc_18002A01D
0x18002a017  call    cs:__imp_CoTaskMemFree
0x18002a01d  mov     rcx, rbx; pv
0x18002a020  call    cs:__imp_CoTaskMemFree
0x18002a026  add     rsp, 20h
0x18002a02a  pop     rbx
0x18002a02b  retn
```
