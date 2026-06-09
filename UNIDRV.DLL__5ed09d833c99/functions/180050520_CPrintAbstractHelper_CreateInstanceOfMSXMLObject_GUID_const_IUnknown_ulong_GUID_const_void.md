# CPrintAbstractHelper::CreateInstanceOfMSXMLObject(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x180050520`
- end: `0x1800505c7`
- name: `?CreateInstanceOfMSXMLObject@CPrintAbstractHelper@@UEAAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z`
- size: `167`
- prototype: `int __fastcall(CPrintAbstractHelper *this, const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *riid, void **ppv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180075740`

## callees

- `0x180050520`
- `0x180077010`

## import_xrefs

- `ole32!CoInitializeEx` at `0x180050557`
- `ole32!CoInitializeEx` at `0x180050557`
- `ole32!CoCreateInstance` at `0x1800505aa`
- `ole32!CoCreateInstance` at `0x1800505aa`

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
0x180050520  mov     [rsp+arg_0], rbx
0x180050525  mov     [rsp+arg_8], rsi
0x18005052a  push    rdi
0x18005052b  sub     rsp, 30h
0x18005052f  mov     rdi, r8
0x180050532  mov     rsi, rdx
0x180050535  mov     rbx, rcx
0x180050538  test    r8, r8
0x18005053b  jnz     short loc_180050545
0x18005053d  xor     eax, eax
0x18005053f  cmp     r9d, 2
0x180050543  jb      short loc_18005054A
0x180050545  mov     eax, 80070057h
0x18005054a  cmp     dword ptr [rcx+43Ch], 0
0x180050551  jnz     short loc_180050584
0x180050553  xor     edx, edx; dwCoInit
0x180050555  xor     ecx, ecx; pvReserved
0x180050557  call    cs:__imp_CoInitializeEx
0x18005055e  nop     dword ptr [rax+rax+00h]
0x180050563  mov     dword ptr [rbx+43Ch], 1
0x18005056d  test    eax, eax
0x18005056f  js      short loc_180050588
0x180050571  mov     rax, [rbx+10h]
0x180050575  mov     rcx, [rbx+8]
0x180050579  mov     rax, [rax+50h]
0x18005057d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050582  jmp     short loc_18005058F
0x180050584  test    eax, eax
0x180050586  jns     short loc_18005058F
0x180050588  cmp     eax, 80010106h
0x18005058d  jnz     short loc_1800505B6
0x18005058f  mov     rax, [rsp+38h+arg_28]
0x180050594  mov     r8d, 1; dwClsContext
0x18005059a  mov     r9, [rsp+38h+riid]; riid
0x18005059f  mov     rdx, rdi; pUnkOuter
0x1800505a2  mov     rcx, rsi; rclsid
0x1800505a5  mov     [rsp+38h+ppv], rax; ppv
0x1800505aa  call    cs:__imp_CoCreateInstance
0x1800505b1  nop     dword ptr [rax+rax+00h]
0x1800505b6  mov     rbx, [rsp+38h+arg_0]
0x1800505bb  mov     rsi, [rsp+38h+arg_8]
0x1800505c0  add     rsp, 30h
0x1800505c4  pop     rdi
0x1800505c5  retn
```
