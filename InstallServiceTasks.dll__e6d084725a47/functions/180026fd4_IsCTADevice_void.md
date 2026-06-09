# IsCTADevice(void)

- ea: `0x180026fd4`
- end: `0x180027018`
- name: `?IsCTADevice@@YAHXZ`
- size: `68`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028b44`

## callees

- `0x180029190`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027003`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027003`

## pseudocode

```c
_BOOL8 IsCTADevice(void)
{
  const WCHAR *RegistryLocation; // rax

  RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(&qword_18006A488, &word_18004C64C);
  return CompareStringOrdinal(RegistryLocation, -1, L"zh", -1, 1) == 2;
}

```

## disassembly

```asm
0x180026fd4  sub     rsp, 38h
0x180026fd8  lea     rdx, word_18004C64C
0x180026fdf  lea     rcx, qword_18006A488
0x180026fe6  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x180026feb  or      edx, 0FFFFFFFFh; cchCount1
0x180026fee  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180026ff6  mov     r9d, edx; cchCount2
0x180026ff9  lea     r8, String2; "zh"
0x180027000  mov     rcx, rax; lpString1
0x180027003  call    cs:__imp_CompareStringOrdinal
0x180027009  xor     ecx, ecx
0x18002700b  cmp     eax, 2
0x18002700e  setz    cl
0x180027011  mov     eax, ecx
0x180027013  add     rsp, 38h
0x180027017  retn
```
