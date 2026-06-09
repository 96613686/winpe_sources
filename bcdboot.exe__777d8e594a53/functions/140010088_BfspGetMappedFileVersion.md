# BfspGetMappedFileVersion

- ea: `0x140010088`
- end: `0x14001018b`
- name: `BfspGetMappedFileVersion`
- size: `259`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000ff2c`
- `0x14000ffe8`

## callees

- `0x140010088`
- `0x140026650`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140010154`
- `msvcrt!_wcsicmp` at `0x140010154`
- `ntdll!LdrAccessResource` at `0x140010124`
- `ntdll!LdrAccessResource` at `0x140010124`
- `ntdll!LdrFindResource_U` at `0x1400100f4`
- `ntdll!LdrFindResource_U` at `0x1400100f4`

## pseudocode

```c
__int64 __fastcall BfspGetMappedFileVersion(__int64 a1)
{
  void *v1; // rbx
  ULONG Size; // [rsp+24h] [rbp-54h] BYREF
  PVOID Resource; // [rsp+28h] [rbp-50h] BYREF
  __int64 v5; // [rsp+30h] [rbp-48h]
  PIMAGE_RESOURCE_DATA_ENTRY ResourceDataEntry[2]; // [rsp+38h] [rbp-40h] BYREF
  struct _LDR_RESOURCE_INFO v7; // [rsp+48h] [rbp-30h] BYREF

  v5 = 0;
  ResourceDataEntry[0] = 0;
  Size = 0;
  Resource = 0;
  v1 = (void *)(a1 | 1);
  ResourceDataEntry[1] = (PIMAGE_RESOURCE_DATA_ENTRY)(a1 | 1);
  v7.Type = 16;
  v7.Name = 1;
  v7.Language = 0;
  if ( LdrFindResource_U((PVOID)(a1 | 1), &v7, 3u, ResourceDataEntry) >= 0
    && LdrAccessResource(v1, ResourceDataEntry[0], &Resource, &Size) >= 0
    && Size >= 0x5C
    && !_wcsicmp((const wchar_t *)Resource + 3, L"VS_VERSION_INFO") )
  {
    HIDWORD(v5) = *((_DWORD *)Resource + 12);
    LODWORD(v5) = *((_DWORD *)Resource + 13);
  }
  return v5;
}

```

## disassembly

```asm
0x140010088  mov     r11, rsp
0x14001008b  push    rbx
0x14001008c  sub     rsp, 70h
0x140010090  mov     rax, cs:__security_cookie
0x140010097  xor     rax, rsp
0x14001009a  mov     [rsp+78h+var_18], rax
0x14001009f  mov     rbx, rcx
0x1400100a2  mov     qword ptr [r11-48h], 0
0x1400100aa  mov     qword ptr [r11-40h], 0
0x1400100b2  mov     [rsp+78h+Size], 0
0x1400100ba  mov     qword ptr [r11-50h], 0
0x1400100c2  or      rbx, 1
0x1400100c6  mov     [rsp+78h+var_38], rbx
0x1400100cb  mov     qword ptr [r11-30h], 10h
0x1400100d3  mov     qword ptr [r11-28h], 1
0x1400100db  mov     qword ptr [r11-20h], 0
0x1400100e3  lea     r9, [r11-40h]; ResourceDataEntry
0x1400100e7  mov     r8d, 3; Level
0x1400100ed  lea     rdx, [r11-30h]; ResourceInfo
0x1400100f1  mov     rcx, rbx; BaseAddress
0x1400100f4  call    cs:__imp_LdrFindResource_U
0x1400100fa  mov     [rsp+78h+var_58], eax
0x1400100fe  jmp     short loc_14001010E
0x140010100  mov     eax, 0C0000001h
0x140010105  mov     [rsp+78h+var_58], eax
0x140010109  mov     rbx, [rsp+78h+var_38]
0x14001010e  test    eax, eax
0x140010110  js      short loc_140010173
0x140010112  lea     r9, [rsp+78h+Size]; Size
0x140010117  lea     r8, [rsp+78h+Resource]; Resource
0x14001011c  mov     rdx, [rsp+78h+ResourceDataEntry]; ResourceDataEntry
0x140010121  mov     rcx, rbx; BaseAddress
0x140010124  call    cs:__imp_LdrAccessResource
0x14001012a  mov     [rsp+78h+var_58], eax
0x14001012e  jmp     short loc_140010139
0x140010130  mov     eax, 0C0000001h
0x140010135  mov     [rsp+78h+var_58], eax
0x140010139  test    eax, eax
0x14001013b  js      short loc_140010173
0x14001013d  cmp     [rsp+78h+Size], 5Ch ; '\'
0x140010142  jb      short loc_140010171
0x140010144  mov     rcx, [rsp+78h+Resource]
0x140010149  add     rcx, 6; String1
0x14001014d  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x140010154  call    cs:__imp__wcsicmp
0x14001015a  test    eax, eax
0x14001015c  jnz     short loc_140010171
0x14001015e  mov     rcx, [rsp+78h+Resource]
0x140010163  mov     eax, [rcx+30h]
0x140010166  mov     dword ptr [rsp+78h+var_48+4], eax
0x14001016a  mov     eax, [rcx+34h]
0x14001016d  mov     dword ptr [rsp+78h+var_48], eax
0x140010171  jmp     short $+2
0x140010173  mov     rax, [rsp+78h+var_48]
0x140010178  mov     rcx, [rsp+78h+var_18]
0x14001017d  xor     rcx, rsp; StackCookie
0x140010180  call    __security_check_cookie
0x140010185  add     rsp, 70h
0x140010189  pop     rbx
0x14001018a  retn
```
