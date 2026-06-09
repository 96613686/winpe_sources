# CWiaExtensionHost64::GetExtension(long,ushort *,_GUID const &,_GUID const &,void * *)

- ea: `0x180001d60`
- end: `0x180001db0`
- name: `?GetExtension@CWiaExtensionHost64@@UEAAJJPEAGAEBU_GUID@@1PEAPEAX@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWiaExtensionHost64 *this, __int64, unsigned __int16 *, const struct _GUID *, const struct _GUID *riid, void **ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d60`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180001d95`
- `ole32!CoCreateInstance` at `0x180001d95`
- `ole32!CoInitializeEx` at `0x180001d71`
- `ole32!CoInitializeEx` at `0x180001d71`
- `ole32!CoUninitialize` at `0x180001d9d`
- `ole32!CoUninitialize` at `0x180001d9d`

## pseudocode

```c
__int64 __fastcall CWiaExtensionHost64::GetExtension(
        CWiaExtensionHost64 *this,
        __int64 a2,
        unsigned __int16 *a3,
        const struct _GUID *a4,
        const struct _GUID *riid,
        void **ppv)
{
  HRESULT Instance; // ebx

  Instance = CoInitializeEx(0, 0);
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(a4, 0, 0x17u, riid, ppv);
    CoUninitialize();
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180001d60  mov     [rsp+arg_0], rbx
0x180001d65  push    rdi
0x180001d66  sub     rsp, 30h
0x180001d6a  xor     edx, edx; dwCoInit
0x180001d6c  xor     ecx, ecx; pvReserved
0x180001d6e  mov     rdi, r9
0x180001d71  call    cs:__imp_CoInitializeEx
0x180001d77  mov     ebx, eax
0x180001d79  test    eax, eax
0x180001d7b  js      short loc_180001DA3
0x180001d7d  mov     rax, [rsp+38h+arg_28]
0x180001d82  xor     edx, edx; pUnkOuter
0x180001d84  mov     r9, [rsp+38h+riid]; riid
0x180001d89  mov     rcx, rdi; rclsid
0x180001d8c  mov     [rsp+38h+ppv], rax; ppv
0x180001d91  lea     r8d, [rdx+17h]; dwClsContext
0x180001d95  call    cs:__imp_CoCreateInstance
0x180001d9b  mov     ebx, eax
0x180001d9d  call    cs:__imp_CoUninitialize
0x180001da3  mov     eax, ebx
0x180001da5  mov     rbx, [rsp+38h+arg_0]
0x180001daa  add     rsp, 30h
0x180001dae  pop     rdi
0x180001daf  retn
```
