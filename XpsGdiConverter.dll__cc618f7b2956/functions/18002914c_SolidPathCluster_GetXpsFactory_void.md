# SolidPathCluster::GetXpsFactory(void)

- ea: `0x18002914c`
- end: `0x180029193`
- name: `?GetXpsFactory@SolidPathCluster@@AEAAPEAUIXpsOMObjectFactory@@XZ`
- size: `71`
- prototype: `struct IXpsOMObjectFactory *__fastcall(SolidPathCluster *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180028acc`
- `0x180029538`
- `0x18002990c`

## callees

- `0x18002914c`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002917c`
- `ole32!CoCreateInstance` at `0x18002917c`

## pseudocode

```c
struct IXpsOMObjectFactory *__fastcall SolidPathCluster::GetXpsFactory(SolidPathCluster *this)
{
  char *v1; // rbx

  v1 = (char *)this + 48;
  if ( !*((_QWORD *)this + 6) )
    *((_DWORD *)this + 14) = CoCreateInstance(
                               &GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585,
                               0,
                               1u,
                               &GUID_f9b2a685_a50d_4fc2_b764_b56e093ea0ca,
                               (LPVOID *)this + 6);
  return *(struct IXpsOMObjectFactory **)v1;
}

```

## disassembly

```asm
0x18002914c  mov     [rsp+arg_0], rbx
0x180029151  push    rdi
0x180029152  sub     rsp, 30h
0x180029156  lea     rbx, [rcx+30h]
0x18002915a  mov     rdi, rcx
0x18002915d  cmp     qword ptr [rbx], 0
0x180029161  jnz     short loc_180029185
0x180029163  xor     edx, edx; pUnkOuter
0x180029165  mov     [rsp+38h+ppv], rbx; ppv
0x18002916a  lea     r9, _GUID_f9b2a685_a50d_4fc2_b764_b56e093ea0ca; riid
0x180029171  lea     rcx, _GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585; rclsid
0x180029178  lea     r8d, [rdx+1]; dwClsContext
0x18002917c  call    cs:__imp_CoCreateInstance
0x180029182  mov     [rdi+38h], eax
0x180029185  mov     rax, [rbx]
0x180029188  mov     rbx, [rsp+38h+arg_0]
0x18002918d  add     rsp, 30h
0x180029191  pop     rdi
0x180029192  retn
```
