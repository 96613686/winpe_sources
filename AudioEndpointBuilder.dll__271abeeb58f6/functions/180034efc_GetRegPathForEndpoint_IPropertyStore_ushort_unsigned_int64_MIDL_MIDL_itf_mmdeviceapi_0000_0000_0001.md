# GetRegPathForEndpoint(IPropertyStore *,ushort *,unsigned __int64,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)

- ea: `0x180034efc`
- end: `0x180034f8f`
- name: `?GetRegPathForEndpoint@@YAJPEAUIPropertyStore@@PEAG_KW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@@Z`
- size: `147`
- prototype: `int(struct IPropertyStore *, unsigned __int16 *, unsigned __int64, enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180034c84`

## callees

- `0x180033864`
- `0x180034efc`
- `0x180068010`

## import_xrefs

- `MMDevAPI!__imp_GetCategoryPath` at `0x180034f57`
- `MMDevAPI!__imp_GetCategoryPath` at `0x180034f57`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034f77`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034f77`

## pseudocode

```c
__int64 __fastcall GetRegPathForEndpoint(struct IPropertyStore *a1, unsigned __int16 *a2, __int64 a3, unsigned int a4)
{
  int CategoryPath; // ebx
  unsigned __int64 v7; // rdx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-18h]

  *(_OWORD *)pvar = 0;
  v10 = 0;
  CategoryPath = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetValue)(
                   a1,
                   &PKEY_AudioEndpoint_GUID,
                   pvar);
  if ( CategoryPath >= 0 && LOWORD(pvar[0]) == 31 )
  {
    CategoryPath = GetCategoryPath(a2, 260, 0, a4);
    if ( CategoryPath >= 0 )
      CategoryPath = StringCchCatW(a2, v7, (const unsigned __int16 *)pvar[1]);
  }
  PropVariantClear(pvar);
  return (unsigned int)CategoryPath;
}

```

## disassembly

```asm
0x180034efc  mov     r11, rsp
0x180034eff  mov     [r11+8], rbx
0x180034f03  mov     [r11+10h], rsi
0x180034f07  push    rdi
0x180034f08  sub     rsp, 40h
0x180034f0c  xor     eax, eax
0x180034f0e  lea     r8, [r11-28h]
0x180034f12  xorps   xmm0, xmm0
0x180034f15  mov     rdi, rdx
0x180034f18  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180034f1d  mov     [r11-18h], rax
0x180034f21  lea     rdx, PKEY_AudioEndpoint_GUID
0x180034f28  mov     rax, [rcx]
0x180034f2b  mov     esi, r9d
0x180034f2e  mov     rax, [rax+28h]
0x180034f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f37  mov     ebx, eax
0x180034f39  test    eax, eax
0x180034f3b  js      short loc_180034F72
0x180034f3d  mov     eax, 1Fh
0x180034f42  cmp     ax, word ptr [rsp+48h+pvar]
0x180034f47  jnz     short loc_180034F72
0x180034f49  mov     r9d, esi
0x180034f4c  xor     r8d, r8d
0x180034f4f  mov     edx, 104h
0x180034f54  mov     rcx, rdi
0x180034f57  call    cs:__imp_GetCategoryPath
0x180034f5d  mov     ebx, eax
0x180034f5f  test    eax, eax
0x180034f61  js      short loc_180034F72
0x180034f63  mov     r8, [rsp+48h+pvar+8]; unsigned __int16 *
0x180034f68  mov     rcx, rdi; unsigned __int16 *
0x180034f6b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034f70  mov     ebx, eax
0x180034f72  lea     rcx, [rsp+48h+pvar]; pvar
0x180034f77  call    cs:__imp_PropVariantClear
0x180034f7d  mov     rsi, [rsp+48h+arg_8]
0x180034f82  mov     eax, ebx
0x180034f84  mov     rbx, [rsp+48h+arg_0]
0x180034f89  add     rsp, 40h
0x180034f8d  pop     rdi
0x180034f8e  retn
```
