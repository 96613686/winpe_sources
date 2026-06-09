# CreateContainer(void *,ushort const *,ushort const *)

- ea: `0x18002366c`
- end: `0x180023716`
- name: `?CreateContainer@@YAJPEAXPEBG1@Z`
- size: `170`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002371c`

## callees

- `0x18002435c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800236f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800236fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800236f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800236fe`
- `adsldpc!ADSICreateDSObject` at `0x1800236e6`
- `adsldpc!ADSICreateDSObject` at `0x1800236e6`

## pseudocode

```c
__int64 __fastcall CreateContainer(void *a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  struct _ads_attr_info v7; // [rsp+20h] [rbp-48h] BYREF
  struct _ads_attr_info v8; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v9; // [rsp+80h] [rbp+18h] BYREF

  v9 = L"classStore";
  PackStrArrToAttr(&v7, L"objectclass", &v9, 1u);
  v9 = a3;
  PackStrArrToAttr(&v8, L"description", &v9, a3 != 0);
  LODWORD(a3) = ADSICreateDSObject(a1, a2, &v7, 2);
  LocalFree(v7.pADsValues);
  LocalFree(v8.pADsValues);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x18002366c  mov     r11, rsp
0x18002366f  mov     [r11+8], rbx
0x180023673  mov     [r11+10h], rsi
0x180023677  push    rdi
0x180023678  sub     rsp, 60h
0x18002367c  mov     rbx, r8
0x18002367f  lea     rax, aClassstore; "classStore"
0x180023686  mov     rdi, rdx
0x180023689  mov     [r11+18h], rax
0x18002368d  mov     rsi, rcx
0x180023690  lea     r8, [r11+18h]; unsigned __int16 **
0x180023694  lea     rdx, aObjectclass; "objectclass"
0x18002369b  mov     r9d, 1; unsigned int
0x1800236a1  lea     rcx, [r11-48h]; struct _ads_attr_info *
0x1800236a5  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x1800236aa  xor     r9d, r9d
0x1800236ad  mov     [rsp+68h+arg_10], rbx
0x1800236b5  test    rbx, rbx
0x1800236b8  lea     r8, [rsp+68h+arg_10]; unsigned __int16 **
0x1800236c0  lea     rdx, aDescription; "description"
0x1800236c7  setnz   r9b; unsigned int
0x1800236cb  lea     rcx, [rsp+68h+var_28]; struct _ads_attr_info *
0x1800236d0  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x1800236d5  mov     r9d, 2
0x1800236db  lea     r8, [rsp+68h+var_48]
0x1800236e0  mov     rdx, rdi
0x1800236e3  mov     rcx, rsi
0x1800236e6  call    cs:__imp_ADSICreateDSObject
0x1800236ec  mov     rcx, [rsp+68h+hMem]; hMem
0x1800236f1  mov     ebx, eax
0x1800236f3  call    cs:__imp_LocalFree
0x1800236f9  mov     rcx, [rsp+68h+var_28.pADsValues]; hMem
0x1800236fe  call    cs:__imp_LocalFree
0x180023704  mov     rsi, [rsp+68h+arg_8]
0x180023709  mov     eax, ebx
0x18002370b  mov     rbx, [rsp+68h+arg_0]
0x180023710  add     rsp, 60h
0x180023714  pop     rdi
0x180023715  retn
```
