# CPrintAbstractHelper::CreateInstanceOfMSXMLObject(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x18004ede0`
- end: `0x18004ee7a`
- name: `?CreateInstanceOfMSXMLObject@CPrintAbstractHelper@@UEAAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z`
- size: `154`
- prototype: `int(CPrintAbstractHelper *__hidden this, const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180073670`

## callees

- `0x18004ede0`
- `0x180075010`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18004ee17`
- `ole32!CoInitializeEx` at `0x18004ee17`
- `ole32!CoCreateInstance` at `0x18004ee64`
- `ole32!CoCreateInstance` at `0x18004ee64`

## pseudocode

```c
int __fastcall CPrintAbstractHelper::CreateInstanceOfMSXMLObject(
        CPrintAbstractHelper *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        unsigned int a4,
        const struct _GUID *riid,
        void **ppv)
{
  int result; // eax

  if ( a3 || (result = 0, a4 >= 2) )
    result = -2147024809;
  if ( *((_DWORD *)this + 271) )
  {
    if ( result >= 0 )
      return CoCreateInstance(a2, a3, 1u, riid, ppv);
LABEL_8:
    if ( result != -2147417850 )
      return result;
    return CoCreateInstance(a2, a3, 1u, riid, ppv);
  }
  result = CoInitializeEx(0, 0);
  *((_DWORD *)this + 271) = 1;
  if ( result < 0 )
    goto LABEL_8;
  (*(void (__fastcall **)(_QWORD))(*((_QWORD *)this + 2) + 80LL))(*((_QWORD *)this + 1));
  return CoCreateInstance(a2, a3, 1u, riid, ppv);
}

```

## disassembly

```asm
0x18004ede0  mov     [rsp+arg_0], rbx
0x18004ede5  mov     [rsp+arg_8], rsi
0x18004edea  push    rdi
0x18004edeb  sub     rsp, 30h
0x18004edef  mov     rdi, r8
0x18004edf2  mov     rsi, rdx
0x18004edf5  mov     rbx, rcx
0x18004edf8  test    r8, r8
0x18004edfb  jnz     short loc_18004EE05
0x18004edfd  xor     eax, eax
0x18004edff  cmp     r9d, 2
0x18004ee03  jb      short loc_18004EE0A
0x18004ee05  mov     eax, 80070057h
0x18004ee0a  cmp     dword ptr [rcx+43Ch], 0
0x18004ee11  jnz     short loc_18004EE3E
0x18004ee13  xor     edx, edx; dwCoInit
0x18004ee15  xor     ecx, ecx; pvReserved
0x18004ee17  call    cs:__imp_CoInitializeEx
0x18004ee1d  mov     dword ptr [rbx+43Ch], 1
0x18004ee27  test    eax, eax
0x18004ee29  js      short loc_18004EE42
0x18004ee2b  mov     rax, [rbx+10h]
0x18004ee2f  mov     rcx, [rbx+8]
0x18004ee33  mov     rax, [rax+50h]
0x18004ee37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee3c  jmp     short loc_18004EE49
0x18004ee3e  test    eax, eax
0x18004ee40  jns     short loc_18004EE49
0x18004ee42  cmp     eax, 80010106h
0x18004ee47  jnz     short loc_18004EE6A
0x18004ee49  mov     rax, [rsp+38h+arg_28]
0x18004ee4e  mov     r8d, 1; dwClsContext
0x18004ee54  mov     r9, [rsp+38h+riid]; riid
0x18004ee59  mov     rdx, rdi; pUnkOuter
0x18004ee5c  mov     rcx, rsi; rclsid
0x18004ee5f  mov     [rsp+38h+ppv], rax; ppv
0x18004ee64  call    cs:__imp_CoCreateInstance
0x18004ee6a  mov     rbx, [rsp+38h+arg_0]
0x18004ee6f  mov     rsi, [rsp+38h+arg_8]
0x18004ee74  add     rsp, 30h
0x18004ee78  pop     rdi
0x18004ee79  retn
```
