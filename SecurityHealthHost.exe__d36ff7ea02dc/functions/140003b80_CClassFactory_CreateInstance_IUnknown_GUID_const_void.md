# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140003b80`
- end: `0x140003be1`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `97`
- prototype: `__int64 __fastcall(CClassFactory *this, struct IUnknown *, const struct _GUID *, void **ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003040`
- `0x140003b80`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140003b98`
- `ole32!CoCreateInstance` at `0x140003b98`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **ppv)
{
  HRESULT Instance; // ebx

  Instance = CoCreateInstance((const IID *const)((char *)this + 24), a2, 1u, a3, ppv);
  if ( Instance >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_f2a66fa2f7dd318b6912da7823821443_Traceguids,
      (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140003b80  push    rbx
0x140003b82  sub     rsp, 30h
0x140003b86  mov     [rsp+38h+ppv], r9; ppv
0x140003b8b  add     rcx, 18h; rclsid
0x140003b8f  mov     r9, r8; riid
0x140003b92  mov     r8d, 1; dwClsContext
0x140003b98  call    cs:__imp_CoCreateInstance
0x140003b9e  mov     ebx, eax
0x140003ba0  test    eax, eax
0x140003ba2  jns     short loc_140003BD9
0x140003ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bab  lea     rax, WPP_GLOBAL_Control
0x140003bb2  cmp     rcx, rax
0x140003bb5  jz      short loc_140003BD5
0x140003bb7  test    byte ptr [rcx+1Ch], 1
0x140003bbb  jz      short loc_140003BD5
0x140003bbd  mov     rcx, [rcx+10h]
0x140003bc1  lea     r8, WPP_f2a66fa2f7dd318b6912da7823821443_Traceguids
0x140003bc8  mov     edx, 0Ah
0x140003bcd  mov     r9d, ebx
0x140003bd0  call    WPP_SF_d
0x140003bd5  mov     eax, ebx
0x140003bd7  jmp     short loc_140003BDB
0x140003bd9  xor     eax, eax
0x140003bdb  add     rsp, 30h
0x140003bdf  pop     rbx
0x140003be0  retn
```
