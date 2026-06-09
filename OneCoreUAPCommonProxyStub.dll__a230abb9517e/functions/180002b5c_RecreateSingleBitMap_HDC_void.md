# RecreateSingleBitMap(HDC__ *,void *)

- ea: `0x180002b5c`
- end: `0x180002c7b`
- name: `?RecreateSingleBitMap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAX@Z`
- size: `287`
- prototype: `HBITMAP __fastcall(HDC hdc, HANDLE hFileMappingObject)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002670`

## callees

- `0x180002b5c`
- `0x18000386c`
- `0x18000578c`
- `0x18000af04`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002c59`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002c59`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180002b98`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180002b98`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180002c27`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180002c27`

## pseudocode

```c
HBITMAP __fastcall RecreateSingleBitMap(HDC hdc, HANDLE hFileMappingObject)
{
  BITMAPINFO *v4; // rax
  int *v5; // rbx
  HBITMAP v6; // rdi
  rsize_t v7; // r9
  void *ppvBits; // [rsp+50h] [rbp+18h] BYREF
  BITMAPINFO *v10; // [rsp+58h] [rbp+20h] BYREF

  if ( (unsigned __int8)IsGetDIBitsPresent() )
  {
    v4 = (BITMAPINFO *)MapViewOfFileEx(hFileMappingObject, 6u, 0, 0, 0x100000u, 0);
    v10 = v4;
    v5 = (int *)v4;
    if ( v4 )
    {
      if ( v4->bmiHeader.biSize == 124
        && v4->bmiHeader.biBitCount == 32
        && !v4->bmiHeader.biCompression
        && !v4->bmiHeader.biSizeImage
        && !v4->bmiHeader.biClrUsed
        && *(_DWORD *)&v4[1].bmiHeader.biPlanes == 1466527264
        && 4 * v4->bmiHeader.biWidth * v4->bmiHeader.biHeight + 124 <= 0x100000 )
      {
        ppvBits = 0;
        v6 = CreateDIBSection(hdc, v4, 0, &ppvBits, 0, 0);
        if ( v6 )
        {
          v7 = 4 * v5[1] * (__int64)v5[2];
          memcpy_s(ppvBits, v7, v5 + 31, v7);
          UnmapViewOfFile(v5);
          return v6;
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180002b5c  mov     [rsp+arg_0], rbx
0x180002b61  push    rdi
0x180002b62  sub     rsp, 30h
0x180002b66  mov     rbx, rdx
0x180002b69  mov     rdi, rcx
0x180002b6c  call    IsGetDIBitsPresent
0x180002b71  test    al, al
0x180002b73  jz      loc_180002C6E
0x180002b79  xor     r9d, r9d; dwFileOffsetLow
0x180002b7c  mov     [rsp+38h+lpBaseAddress], 0; lpBaseAddress
0x180002b85  xor     r8d, r8d; dwFileOffsetHigh
0x180002b88  mov     [rsp+38h+dwNumberOfBytesToMap], 100000h; dwNumberOfBytesToMap
0x180002b91  mov     rcx, rbx; hFileMappingObject
0x180002b94  lea     edx, [r9+6]; dwDesiredAccess
0x180002b98  call    cs:__imp_MapViewOfFileEx
0x180002b9e  mov     [rsp+38h+arg_18], rax
0x180002ba3  mov     rbx, rax
0x180002ba6  test    rax, rax
0x180002ba9  jz      loc_180002C64
0x180002baf  cmp     dword ptr [rax], 7Ch ; '|'
0x180002bb2  jnz     loc_180002C64
0x180002bb8  cmp     word ptr [rax+0Eh], 20h ; ' '
0x180002bbd  jnz     loc_180002C64
0x180002bc3  cmp     dword ptr [rax+10h], 0
0x180002bc7  jnz     loc_180002C64
0x180002bcd  cmp     dword ptr [rax+14h], 0
0x180002bd1  jnz     loc_180002C64
0x180002bd7  cmp     dword ptr [rax+20h], 0
0x180002bdb  jnz     loc_180002C64
0x180002be1  cmp     dword ptr [rax+38h], 57696E20h
0x180002be8  jnz     short loc_180002C64
0x180002bea  mov     eax, [rax+8]
0x180002bed  imul    eax, [rbx+4]
0x180002bf1  lea     eax, ds:7Ch[rax*4]
0x180002bf8  cmp     eax, 100000h
0x180002bfd  jg      short loc_180002C64
0x180002bff  mov     dword ptr [rsp+38h+lpBaseAddress], 0; offset
0x180002c07  lea     r9, [rsp+38h+ppvBits]; ppvBits
0x180002c0c  xor     r8d, r8d; usage
0x180002c0f  mov     [rsp+38h+dwNumberOfBytesToMap], 0; hSection
0x180002c18  mov     rdx, rbx; pbmi
0x180002c1b  mov     [rsp+38h+ppvBits], 0
0x180002c24  mov     rcx, rdi; hdc
0x180002c27  call    cs:__imp_CreateDIBSection
0x180002c2d  mov     rdi, rax
0x180002c30  test    rax, rax
0x180002c33  jz      short loc_180002C64
0x180002c35  movsxd  rcx, dword ptr [rbx+4]
0x180002c39  lea     r8, [rbx+7Ch]; Source
0x180002c3d  movsxd  rdx, dword ptr [rbx+8]
0x180002c41  imul    rdx, rcx
0x180002c45  mov     rcx, [rsp+38h+ppvBits]; Destination
0x180002c4a  shl     rdx, 2; DestinationSize
0x180002c4e  mov     r9, rdx; SourceSize
0x180002c51  call    memcpy_s
0x180002c56  mov     rcx, rbx; lpBaseAddress
0x180002c59  call    cs:__imp_UnmapViewOfFile
0x180002c5f  mov     rax, rdi
0x180002c62  jmp     short loc_180002C70
0x180002c64  lea     rcx, [rsp+38h+arg_18]
0x180002c69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEBX@Z$1?UnmapViewOfFile@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void const *),&UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void const *),&UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180002c6e  xor     eax, eax
0x180002c70  mov     rbx, [rsp+38h+arg_0]
0x180002c75  add     rsp, 30h
0x180002c79  pop     rdi
0x180002c7a  retn
```
