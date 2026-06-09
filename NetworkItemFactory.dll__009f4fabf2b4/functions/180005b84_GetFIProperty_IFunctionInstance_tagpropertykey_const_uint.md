# GetFIProperty(IFunctionInstance *,_tagpropertykey const &,uint *)

- ea: `0x180005b84`
- end: `0x180005be6`
- name: `?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAI@Z`
- size: `98`
- prototype: `int(struct IFunctionInstance *, const struct _tagpropertykey *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ab8`
- `0x1800037f8`
- `0x1800059e8`

## callees

- `0x180005b84`
- `0x180005cc0`

## import_xrefs

- `ole32!PropVariantClear` at `0x180005bd3`
- `ole32!PropVariantClear` at `0x180005bd3`
- `PROPSYS!PropVariantToUInt32` at `0x180005bc6`
- `PROPSYS!PropVariantToUInt32` at `0x180005bc6`

## pseudocode

```c
__int64 __fastcall GetFIProperty(struct IFunctionInstance *a1, const struct _tagpropertykey *a2, unsigned int *a3)
{
  HRESULT FIProperty; // ebx
  struct tagPROPVARIANT propvarIn; // [rsp+20h] [rbp-28h] BYREF

  *a3 = 0;
  memset(&propvarIn, 0, sizeof(propvarIn));
  FIProperty = GetFIProperty(a1, &PKEY_WNET_DisplayType, &propvarIn);
  if ( FIProperty >= 0 )
  {
    FIProperty = PropVariantToUInt32((const PROPVARIANT *const)&propvarIn, a3);
    PropVariantClear((PROPVARIANT *)&propvarIn);
  }
  return (unsigned int)FIProperty;
}

```

## disassembly

```asm
0x180005b84  mov     [rsp+arg_0], rbx
0x180005b89  push    rdi
0x180005b8a  sub     rsp, 40h
0x180005b8e  mov     rdi, r8
0x180005b91  mov     dword ptr [r8], 0
0x180005b98  xorps   xmm0, xmm0
0x180005b9b  lea     r8, [rsp+48h+propvarIn]; struct tagPROPVARIANT *
0x180005ba0  xor     eax, eax
0x180005ba2  lea     rdx, PKEY_WNET_DisplayType; struct _tagpropertykey *
0x180005ba9  movups  xmmword ptr [rsp+48h+propvarIn], xmm0
0x180005bae  mov     [rsp+48h+var_18], rax
0x180005bb3  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,tagPROPVARIANT *)
0x180005bb8  mov     ebx, eax
0x180005bba  test    eax, eax
0x180005bbc  js      short loc_180005BD9
0x180005bbe  mov     rdx, rdi; pulRet
0x180005bc1  lea     rcx, [rsp+48h+propvarIn]; propvarIn
0x180005bc6  call    cs:__imp_PropVariantToUInt32
0x180005bcc  lea     rcx, [rsp+48h+propvarIn]; pvar
0x180005bd1  mov     ebx, eax
0x180005bd3  call    cs:__imp_PropVariantClear
0x180005bd9  mov     eax, ebx
0x180005bdb  mov     rbx, [rsp+48h+arg_0]
0x180005be0  add     rsp, 40h
0x180005be4  pop     rdi
0x180005be5  retn
```
