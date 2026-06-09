# Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *)

- ea: `0x14000d2a4`
- end: `0x14000d2e8`
- name: `?Free_SR_VOLUME_PROP@@YAXPEAU_SR_VOLUME_PROP@@@Z`
- size: `68`
- prototype: `void __fastcall(struct _SR_VOLUME_PROP *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000d1a4`
- `0x14000d414`
- `0x14000d688`

## callees

- `0x14000d2a4`
- `0x14000d2f0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000d2b5`
- `ole32!CoTaskMemFree` at `0x14000d2c7`
- `ole32!CoTaskMemFree` at `0x14000d2b5`
- `ole32!CoTaskMemFree` at `0x14000d2c7`

## pseudocode

```c
void __fastcall Free_SR_VOLUME_PROP(struct _SR_VOLUME_PROP *a1)
{
  void *v2; // rcx

  if ( a1 )
  {
    CoTaskMemFree(*((LPVOID *)a1 + 2));
    v2 = (void *)*((_QWORD *)a1 + 3);
    *((_QWORD *)a1 + 2) = 0;
    CoTaskMemFree(v2);
    *((_QWORD *)a1 + 3) = 0;
    Free_StringArray((unsigned int *)a1 + 8, (unsigned __int16 ***)a1 + 5);
  }
}

```

## disassembly

```asm
0x14000d2a4  test    rcx, rcx
0x14000d2a7  jz      short locret_14000D2E7
0x14000d2a9  push    rbx
0x14000d2aa  sub     rsp, 20h
0x14000d2ae  mov     rbx, rcx
0x14000d2b1  mov     rcx, [rcx+10h]; pv
0x14000d2b5  call    cs:__imp_CoTaskMemFree
0x14000d2bb  mov     rcx, [rbx+18h]; pv
0x14000d2bf  mov     qword ptr [rbx+10h], 0
0x14000d2c7  call    cs:__imp_CoTaskMemFree
0x14000d2cd  lea     rdx, [rbx+28h]; unsigned __int16 ***
0x14000d2d1  mov     qword ptr [rbx+18h], 0
0x14000d2d9  lea     rcx, [rbx+20h]; unsigned int *
0x14000d2dd  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x14000d2e2  add     rsp, 20h
0x14000d2e6  pop     rbx
0x14000d2e7  retn
```
