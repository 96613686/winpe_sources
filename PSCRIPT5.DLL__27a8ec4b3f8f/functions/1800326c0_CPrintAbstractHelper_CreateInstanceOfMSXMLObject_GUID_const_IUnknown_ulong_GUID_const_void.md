# CPrintAbstractHelper::CreateInstanceOfMSXMLObject(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x1800326c0`
- end: `0x180032767`
- name: `?CreateInstanceOfMSXMLObject@CPrintAbstractHelper@@UEAAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z`
- size: `167`
- prototype: `int __fastcall(CPrintAbstractHelper *this, const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *riid, void **ppv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d920`

## callees

- `0x1800326c0`
- `0x18005f010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003274a`
- `ole32!CoCreateInstance` at `0x18003274a`
- `ole32!CoInitializeEx` at `0x1800326f7`
- `ole32!CoInitializeEx` at `0x1800326f7`

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
0x1800326c0  mov     [rsp+arg_0], rbx
0x1800326c5  mov     [rsp+arg_8], rsi
0x1800326ca  push    rdi
0x1800326cb  sub     rsp, 30h
0x1800326cf  mov     rdi, r8
0x1800326d2  mov     rsi, rdx
0x1800326d5  mov     rbx, rcx
0x1800326d8  test    r8, r8
0x1800326db  jnz     short loc_1800326E5
0x1800326dd  xor     eax, eax
0x1800326df  cmp     r9d, 2
0x1800326e3  jb      short loc_1800326EA
0x1800326e5  mov     eax, 80070057h
0x1800326ea  cmp     dword ptr [rcx+43Ch], 0
0x1800326f1  jnz     short loc_180032724
0x1800326f3  xor     edx, edx; dwCoInit
0x1800326f5  xor     ecx, ecx; pvReserved
0x1800326f7  call    cs:__imp_CoInitializeEx
0x1800326fe  nop     dword ptr [rax+rax+00h]
0x180032703  mov     dword ptr [rbx+43Ch], 1
0x18003270d  test    eax, eax
0x18003270f  js      short loc_180032728
0x180032711  mov     rax, [rbx+10h]
0x180032715  mov     rcx, [rbx+8]
0x180032719  mov     rax, [rax+50h]
0x18003271d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032722  jmp     short loc_18003272F
0x180032724  test    eax, eax
0x180032726  jns     short loc_18003272F
0x180032728  cmp     eax, 80010106h
0x18003272d  jnz     short loc_180032756
0x18003272f  mov     rax, [rsp+38h+arg_28]
0x180032734  mov     r8d, 1; dwClsContext
0x18003273a  mov     r9, [rsp+38h+riid]; riid
0x18003273f  mov     rdx, rdi; pUnkOuter
0x180032742  mov     rcx, rsi; rclsid
0x180032745  mov     [rsp+38h+ppv], rax; ppv
0x18003274a  call    cs:__imp_CoCreateInstance
0x180032751  nop     dword ptr [rax+rax+00h]
0x180032756  mov     rbx, [rsp+38h+arg_0]
0x18003275b  mov     rsi, [rsp+38h+arg_8]
0x180032760  add     rsp, 30h
0x180032764  pop     rdi
0x180032765  retn
```
