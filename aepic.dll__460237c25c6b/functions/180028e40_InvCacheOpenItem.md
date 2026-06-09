# InvCacheOpenItem

- ea: `0x180028e40`
- end: `0x180028ff6`
- name: `InvCacheOpenItem`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180028e40`
- `0x1800295dc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180028fa9`
- `ntdll!RtlAllocateHeap` at `0x180028fa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028ee0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028ee0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028fc6`

## string_xrefs

- `0x180028ef9`: `RegCreateKeyEx failed [%#x]`
- `0x180028f0b`: `InvCacheOpenItem`
- `0x180028f2c`: `Item already exists and CREATE_NEW_CACHE_ITEM specified [%#x]`
- `0x180028f81`: `RegOpenKeyEx failed [%#x]`

## pseudocode

```c
__int64 __fastcall InvCacheOpenItem(_QWORD *a1, __int64 a2, const WCHAR *a3, int a4)
{
  __int64 v5; // rax
  HKEY v6; // rcx
  LSTATUS v7; // eax
  signed int v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  LSTATUS v12; // eax
  _QWORD *Heap; // rax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-38h]
  DWORD v16; // [rsp+60h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF

  phkResult = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( *(_DWORD *)a2 != 1 )
    return (unsigned int)-2147024809;
  if ( !a3 )
    return (unsigned int)-2147024809;
  if ( !*a3 )
    return (unsigned int)-2147024809;
  v5 = *(_QWORD *)(a2 + 8);
  if ( !v5 )
    return (unsigned int)-2147024809;
  v6 = *(HKEY *)(v5 + 8);
  if ( !v6 )
    return (unsigned int)-2147024809;
  if ( !a4 )
  {
    v16 = 0;
    v7 = RegCreateKeyExW(v6, a3, 0, 0, 0, 0xF003Fu, 0, &phkResult, &v16);
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = "RegCreateKeyEx failed [%#x]";
      v10 = 159;
LABEL_13:
      v11 = 1;
LABEL_14:
      dwOptions[0] = v8;
      AslLogCallPrintf(v11, "InvCacheOpenItem", v10, v9, *(_QWORD *)dwOptions);
      goto LABEL_25;
    }
    if ( v16 == 2 )
    {
      v8 = -2147024198;
      v9 = "Item already exists and CREATE_NEW_CACHE_ITEM specified [%#x]";
      v10 = 166;
      v11 = 3;
      goto LABEL_14;
    }
    goto LABEL_23;
  }
  if ( a4 != 1 )
    return (unsigned int)-2147024809;
  v12 = RegOpenKeyExW(v6, a3, 0, 0xF003Fu, &phkResult);
  v8 = v12;
  if ( v12 > 0 )
    v8 = (unsigned __int16)v12 | 0x80070000;
  if ( v8 >= 0 )
  {
LABEL_23:
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
    if ( Heap )
    {
      *(_DWORD *)Heap = 2;
      v8 = 0;
      Heap[1] = phkResult;
      *a1 = Heap;
      return (unsigned int)v8;
    }
    v8 = -2147024882;
    goto LABEL_25;
  }
  if ( v8 != -2147024894 )
  {
    v9 = "RegOpenKeyEx failed [%#x]";
    v10 = 177;
    goto LABEL_13;
  }
LABEL_25:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180028e40  mov     r11, rsp
0x180028e43  mov     [r11+18h], rbx
0x180028e47  push    rdi
0x180028e48  sub     rsp, 50h
0x180028e4c  mov     qword ptr [r11+10h], 0
0x180028e54  mov     r10, r8
0x180028e57  mov     rdi, rcx
0x180028e5a  test    rcx, rcx
0x180028e5d  jz      loc_180028FE4
0x180028e63  test    rdx, rdx
0x180028e66  jz      loc_180028FE4
0x180028e6c  cmp     dword ptr [rdx], 1
0x180028e6f  jnz     loc_180028FE4
0x180028e75  test    r8, r8
0x180028e78  jz      loc_180028FE4
0x180028e7e  xor     eax, eax
0x180028e80  cmp     ax, [r8]
0x180028e84  jz      loc_180028FE4
0x180028e8a  mov     rax, [rdx+8]
0x180028e8e  test    rax, rax
0x180028e91  jz      loc_180028FE4
0x180028e97  mov     rcx, [rax+8]; hKey
0x180028e9b  test    rcx, rcx
0x180028e9e  jz      loc_180028FE4
0x180028ea4  test    r9d, r9d
0x180028ea7  jnz     loc_180028F40
0x180028ead  lea     rax, [r11+8]
0x180028eb1  mov     [rsp+58h+arg_0], r9d
0x180028eb6  mov     [r11-18h], rax
0x180028eba  xor     r8d, r8d; Reserved
0x180028ebd  lea     rax, [r11+10h]
0x180028ec1  mov     rdx, r10; lpSubKey
0x180028ec4  mov     [r11-20h], rax
0x180028ec8  mov     qword ptr [r11-28h], 0
0x180028ed0  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180028ed8  mov     [rsp+58h+dwOptions], r9d; dwOptions
0x180028edd  xor     r9d, r9d; lpClass
0x180028ee0  call    cs:__imp_RegCreateKeyExW
0x180028ee6  mov     ebx, eax
0x180028ee8  test    eax, eax
0x180028eea  jle     short loc_180028EF5
0x180028eec  movzx   ebx, ax
0x180028eef  or      ebx, 80070000h
0x180028ef5  test    ebx, ebx
0x180028ef7  jns     short loc_180028F20
0x180028ef9  lea     r9, aRegcreatekeyex_0; "RegCreateKeyEx failed [%#x]"
0x180028f00  mov     r8d, 9Fh
0x180028f06  mov     ecx, 1
0x180028f0b  lea     rdx, aInvcacheopenit_0; "InvCacheOpenItem"
0x180028f12  mov     [rsp+58h+dwOptions], ebx
0x180028f16  call    AslLogCallPrintf
0x180028f1b  jmp     loc_180028FBC
0x180028f20  cmp     [rsp+58h+arg_0], 2
0x180028f25  jnz     short loc_180028F93
0x180028f27  mov     ebx, 800702BAh
0x180028f2c  lea     r9, aItemAlreadyExi; "Item already exists and CREATE_NEW_CACH"...
0x180028f33  mov     r8d, 0A6h
0x180028f39  mov     ecx, 3
0x180028f3e  jmp     short loc_180028F0B
0x180028f40  cmp     r9d, 1
0x180028f44  jnz     loc_180028FE4
0x180028f4a  lea     rax, [rsp+58h+phkResult]
0x180028f4f  mov     r9d, 0F003Fh; samDesired
0x180028f55  xor     r8d, r8d; ulOptions
0x180028f58  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x180028f5d  mov     rdx, r10; lpSubKey
0x180028f60  call    cs:__imp_RegOpenKeyExW
0x180028f66  mov     ebx, eax
0x180028f68  test    eax, eax
0x180028f6a  jle     short loc_180028F75
0x180028f6c  movzx   ebx, ax
0x180028f6f  or      ebx, 80070000h
0x180028f75  test    ebx, ebx
0x180028f77  jns     short loc_180028F93
0x180028f79  cmp     ebx, 80070002h
0x180028f7f  jz      short loc_180028FBC
0x180028f81  lea     r9, aRegopenkeyexFa_0; "RegOpenKeyEx failed [%#x]"
0x180028f88  mov     r8d, 0B1h
0x180028f8e  jmp     loc_180028F06
0x180028f93  mov     rcx, gs:60h
0x180028f9c  mov     edx, 8; Flags
0x180028fa1  mov     rcx, [rcx+30h]; HeapHandle
0x180028fa5  lea     r8d, [rdx+8]; Size
0x180028fa9  call    cs:__imp_RtlAllocateHeap
0x180028faf  mov     rcx, rax
0x180028fb2  test    rax, rax
0x180028fb5  jnz     short loc_180028FCE
0x180028fb7  mov     ebx, 8007000Eh
0x180028fbc  mov     rcx, [rsp+58h+phkResult]; hKey
0x180028fc1  test    rcx, rcx
0x180028fc4  jz      short loc_180028FE9
0x180028fc6  call    cs:__imp_RegCloseKey
0x180028fcc  jmp     short loc_180028FE9
0x180028fce  mov     dword ptr [rax], 2
0x180028fd4  xor     ebx, ebx
0x180028fd6  mov     rax, [rsp+58h+phkResult]
0x180028fdb  mov     [rcx+8], rax
0x180028fdf  mov     [rdi], rcx
0x180028fe2  jmp     short loc_180028FE9
0x180028fe4  mov     ebx, 80070057h
0x180028fe9  mov     eax, ebx
0x180028feb  mov     rbx, [rsp+58h+arg_10]
0x180028ff0  add     rsp, 50h
0x180028ff4  pop     rdi
0x180028ff5  retn
```
