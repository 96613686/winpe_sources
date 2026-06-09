# CProfileCache::_ClearMapping(void)

- ea: `0x180006bd4`
- end: `0x180006c22`
- name: `?_ClearMapping@CProfileCache@@AEAAXXZ`
- size: `78`
- prototype: `void __fastcall(CProfileCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180006ef4`

## callees

- `0x18000599c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006be1`
- `ole32!CoTaskMemFree` at `0x180006bf3`
- `ole32!CoTaskMemFree` at `0x180006be1`
- `ole32!CoTaskMemFree` at `0x180006bf3`

## pseudocode

```c
void __fastcall CProfileCache::_ClearMapping(LPVOID *this)
{
  void *v2; // rcx
  unsigned int v3; // edx
  unsigned __int16 **v4; // rcx

  CoTaskMemFree(this[4]);
  v2 = this[5];
  this[4] = 0;
  CoTaskMemFree(v2);
  v3 = *((_DWORD *)this + 4);
  v4 = (unsigned __int16 **)this[3];
  this[5] = 0;
  FreeStringArray(v4, v3);
  this[3] = 0;
  *((_DWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180006bd4  push    rbx
0x180006bd6  sub     rsp, 20h
0x180006bda  mov     rbx, rcx
0x180006bdd  mov     rcx, [rcx+20h]; pv
0x180006be1  call    cs:__imp_CoTaskMemFree
0x180006be7  mov     rcx, [rbx+28h]; pv
0x180006beb  mov     qword ptr [rbx+20h], 0
0x180006bf3  call    cs:__imp_CoTaskMemFree
0x180006bf9  mov     edx, [rbx+10h]; unsigned int
0x180006bfc  mov     rcx, [rbx+18h]; unsigned __int16 **
0x180006c00  mov     qword ptr [rbx+28h], 0
0x180006c08  call    ?FreeStringArray@@YAXPEAPEAGI@Z; FreeStringArray(ushort * *,uint)
0x180006c0d  mov     qword ptr [rbx+18h], 0
0x180006c15  mov     dword ptr [rbx+10h], 0
0x180006c1c  add     rsp, 20h
0x180006c20  pop     rbx
0x180006c21  retn
```
