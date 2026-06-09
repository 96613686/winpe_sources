# WindowsMidiServicesInternal::ResourceGetHString(uint)

- ea: `0x180017fd4`
- end: `0x180018089`
- name: `?ResourceGetHString@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@I@Z`
- size: `181`
- prototype: `struct winrt::hstring __high(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180018710`

## callees

- `0x180004f86`
- `0x180004ff4`
- `0x18000500c`
- `0x180014250`
- `0x180017fd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001805e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001805e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180018007`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180018007`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001801c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001801c`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall WindowsMidiServicesInternal::ResourceGetHString(
        struct winrt::impl::shared_hstring_header **a1,
        UINT a2)
{
  int StringW; // eax
  const char *v5; // rdx
  unsigned int v6; // ebp
  const void *v7; // rsi
  struct winrt::impl::shared_hstring_header *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  struct winrt::impl::shared_hstring_header *v11; // rbx
  size_t v12; // r8
  void *v13; // rcx
  HINSTANCE hInstance; // [rsp+60h] [rbp+18h] BYREF
  const void *Buffer; // [rsp+68h] [rbp+20h] BYREF

  Buffer = 0;
  hInstance = 0;
  GetModuleHandleExW(4u, (LPCWSTR)WindowsMidiServicesInternal::GetCurrentModule, &hInstance);
  StringW = LoadStringW(hInstance, a2, (LPWSTR)&Buffer, 0);
  v6 = StringW;
  if ( StringW <= 0 )
  {
    *a1 = 0;
    return a1;
  }
  v7 = Buffer;
  v8 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)StringW, v5);
  v11 = v8;
  v12 = 2LL * v6;
  if ( v12 )
  {
    v13 = (char *)v8 + 28;
    if ( v8 != (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      if ( v7 )
      {
        memcpy_0(v13, v7, v12);
        goto LABEL_8;
      }
      memset_0(v13, 0, v12);
    }
    *(_DWORD *)_o__errno(v13, v9, v12, v10) = 22;
    invalid_parameter_noinfo();
  }
LABEL_8:
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x180017fd4  mov     rax, rsp
0x180017fd7  mov     [rax+8], rbx
0x180017fdb  push    rbp
0x180017fdc  push    rsi
0x180017fdd  push    rdi
0x180017fde  sub     rsp, 30h
0x180017fe2  mov     ebx, edx
0x180017fe4  mov     qword ptr [rax+20h], 0
0x180017fec  mov     rdi, rcx
0x180017fef  mov     qword ptr [rax+18h], 0
0x180017ff7  lea     rdx, ?GetCurrentModule@WindowsMidiServicesInternal@@YAPEAUHINSTANCE__@@XZ; lpModuleName
0x180017ffe  mov     ecx, 4; dwFlags
0x180018003  lea     r8, [rax+18h]; phModule
0x180018007  call    cs:__imp_GetModuleHandleExW
0x18001800d  mov     rcx, [rsp+48h+hInstance]; hInstance
0x180018012  lea     r8, [rsp+48h+Buffer]; lpBuffer
0x180018017  xor     r9d, r9d; cchBufferMax
0x18001801a  mov     edx, ebx; uID
0x18001801c  call    cs:__imp_LoadStringW
0x180018022  mov     ebp, eax
0x180018024  test    eax, eax
0x180018026  jle     short loc_180018074
0x180018028  mov     rsi, [rsp+48h+Buffer]
0x18001802d  mov     ecx, ebp; this
0x18001802f  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180018034  mov     r8d, ebp
0x180018037  mov     rbx, rax
0x18001803a  add     r8, r8; Size
0x18001803d  jz      short loc_18001806F
0x18001803f  lea     rcx, [rax+1Ch]; void *
0x180018043  test    rcx, rcx
0x180018046  jz      short loc_18001805E
0x180018048  test    rsi, rsi
0x18001804b  jz      short loc_180018057
0x18001804d  mov     rdx, rsi; Src
0x180018050  call    memcpy_0
0x180018055  jmp     short loc_18001806F
0x180018057  xor     edx, edx; Val
0x180018059  call    memset_0
0x18001805e  call    cs:__imp__o__errno
0x180018064  mov     dword ptr [rax], 16h
0x18001806a  call    _invalid_parameter_noinfo
0x18001806f  mov     [rdi], rbx
0x180018072  jmp     short loc_180018079
0x180018074  xor     eax, eax
0x180018076  mov     [rdi], rax
0x180018079  mov     rbx, [rsp+48h+arg_0]
0x18001807e  mov     rax, rdi
0x180018081  add     rsp, 30h
0x180018085  pop     rdi
0x180018086  pop     rsi
0x180018087  pop     rbp
0x180018088  retn
```
