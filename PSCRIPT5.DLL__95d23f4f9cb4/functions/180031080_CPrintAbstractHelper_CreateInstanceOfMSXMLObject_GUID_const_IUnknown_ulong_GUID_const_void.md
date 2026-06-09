# CPrintAbstractHelper::CreateInstanceOfMSXMLObject(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x180031080`
- end: `0x18003111a`
- name: `?CreateInstanceOfMSXMLObject@CPrintAbstractHelper@@UEAAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z`
- size: `154`
- prototype: `int(CPrintAbstractHelper *__hidden this, const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002c500`

## callees

- `0x180031080`
- `0x18005d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180031104`
- `ole32!CoCreateInstance` at `0x180031104`
- `ole32!CoInitializeEx` at `0x1800310b7`
- `ole32!CoInitializeEx` at `0x1800310b7`

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
0x180031080  mov     [rsp+arg_0], rbx
0x180031085  mov     [rsp+arg_8], rsi
0x18003108a  push    rdi
0x18003108b  sub     rsp, 30h
0x18003108f  mov     rdi, r8
0x180031092  mov     rsi, rdx
0x180031095  mov     rbx, rcx
0x180031098  test    r8, r8
0x18003109b  jnz     short loc_1800310A5
0x18003109d  xor     eax, eax
0x18003109f  cmp     r9d, 2
0x1800310a3  jb      short loc_1800310AA
0x1800310a5  mov     eax, 80070057h
0x1800310aa  cmp     dword ptr [rcx+43Ch], 0
0x1800310b1  jnz     short loc_1800310DE
0x1800310b3  xor     edx, edx; dwCoInit
0x1800310b5  xor     ecx, ecx; pvReserved
0x1800310b7  call    cs:__imp_CoInitializeEx
0x1800310bd  mov     dword ptr [rbx+43Ch], 1
0x1800310c7  test    eax, eax
0x1800310c9  js      short loc_1800310E2
0x1800310cb  mov     rax, [rbx+10h]
0x1800310cf  mov     rcx, [rbx+8]
0x1800310d3  mov     rax, [rax+50h]
0x1800310d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310dc  jmp     short loc_1800310E9
0x1800310de  test    eax, eax
0x1800310e0  jns     short loc_1800310E9
0x1800310e2  cmp     eax, 80010106h
0x1800310e7  jnz     short loc_18003110A
0x1800310e9  mov     rax, [rsp+38h+arg_28]
0x1800310ee  mov     r8d, 1; dwClsContext
0x1800310f4  mov     r9, [rsp+38h+riid]; riid
0x1800310f9  mov     rdx, rdi; pUnkOuter
0x1800310fc  mov     rcx, rsi; rclsid
0x1800310ff  mov     [rsp+38h+ppv], rax; ppv
0x180031104  call    cs:__imp_CoCreateInstance
0x18003110a  mov     rbx, [rsp+38h+arg_0]
0x18003110f  mov     rsi, [rsp+38h+arg_8]
0x180031114  add     rsp, 30h
0x180031118  pop     rdi
0x180031119  retn
```
