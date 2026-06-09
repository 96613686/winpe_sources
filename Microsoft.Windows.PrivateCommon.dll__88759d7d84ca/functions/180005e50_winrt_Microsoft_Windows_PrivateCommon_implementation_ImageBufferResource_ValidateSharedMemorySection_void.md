# winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::ValidateSharedMemorySection(void)

- ea: `0x180005e50`
- end: `0x180005f51`
- name: `?ValidateSharedMemorySection@ImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@AEAAXXZ`
- size: `257`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800060b0`
- `0x180006190`

## callees

- `0x1800012e0`
- `0x180001450`
- `0x180001500`
- `0x180001d90`
- `0x180005d90`
- `0x180005e50`
- `0x180007280`
- `0x180008e5c`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180005e95`
- `KERNEL32!MapViewOfFile` at `0x180005e95`
- `KERNEL32!VirtualQuery` at `0x180005ec4`
- `KERNEL32!VirtualQuery` at `0x180005ec4`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::ValidateSharedMemorySection(
        HANDLE *this)
{
  void *v2; // rax
  void *v3; // rdi
  winrt *v4; // rcx
  unsigned int v5; // eax
  winrt::hresult *v6; // rax
  char v7[8]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-80h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-68h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+70h] [rbp-48h] BYREF

  if ( !this[7] )
  {
    v2 = MapViewOfFile(this[5], 0xF001Fu, 0, 0, 0);
    memset(&Buffer, 0, sizeof(Buffer));
    v3 = v2;
    if ( !VirtualQuery(v2, &Buffer, 0x30u) )
      winrt::throw_last_error(v4);
    v5 = winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::Capacity((winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource *)this);
    if ( v5 > Buffer.RegionSize )
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)v9, L"Image dimension parameters too large for buffer.");
      v6 = winrt::hresult::hresult((winrt::hresult *)v7, -2147024809);
      winrt::hresult_error::hresult_error(pExceptionObject, *(unsigned int *)v6, v9);
      throw (winrt::hresult_error *)pExceptionObject;
    }
    this[7] = v3;
  }
}

```

## disassembly

```asm
0x180005e50  push    rbx
0x180005e52  sub     rsp, 0B0h
0x180005e59  mov     rax, cs:__security_cookie
0x180005e60  xor     rax, rsp
0x180005e63  mov     [rsp+0B8h+var_18], rax
0x180005e6b  cmp     qword ptr [rcx+38h], 0
0x180005e70  mov     rbx, rcx
0x180005e73  jnz     short loc_180005EEF
0x180005e75  mov     rcx, [rcx+28h]; hFileMappingObject
0x180005e79  xor     r9d, r9d; dwFileOffsetLow
0x180005e7c  xor     r8d, r8d; dwFileOffsetHigh
0x180005e7f  mov     [rsp+0B8h+arg_8], rdi
0x180005e87  mov     edx, 0F001Fh; dwDesiredAccess
0x180005e8c  mov     [rsp+0B8h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x180005e95  call    cs:__imp_MapViewOfFile
0x180005e9b  xorps   xmm0, xmm0
0x180005e9e  lea     rdx, [rsp+0B8h+Buffer]; lpBuffer
0x180005ea3  mov     rcx, rax; lpAddress
0x180005ea6  mov     r8d, 30h ; '0'; dwLength
0x180005eac  movups  xmmword ptr [rsp+0B8h+Buffer.BaseAddress], xmm0
0x180005eb1  mov     rdi, rax
0x180005eb4  movups  xmmword ptr [rsp+0B8h+Buffer.AllocationProtect], xmm0
0x180005ebc  movups  xmmword ptr [rsp+0B8h+Buffer.State], xmm0
0x180005ec4  call    cs:__imp_VirtualQuery
0x180005eca  test    rax, rax
0x180005ecd  jz      short loc_180005F08
0x180005ecf  mov     rcx, rbx; this
0x180005ed2  call    ?Capacity@ImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@QEAAIXZ; winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::Capacity(void)
0x180005ed7  mov     eax, eax
0x180005ed9  cmp     rax, [rsp+0B8h+Buffer.RegionSize]
0x180005ee1  ja      short loc_180005F0E
0x180005ee3  mov     [rbx+38h], rdi
0x180005ee7  mov     rdi, [rsp+0B8h+arg_8]
0x180005eef  mov     rcx, [rsp+0B8h+var_18]
0x180005ef7  xor     rcx, rsp; StackCookie
0x180005efa  call    __security_check_cookie
0x180005eff  add     rsp, 0B0h
0x180005f06  pop     rbx
0x180005f07  retn
0x180005f08  call    ?throw_last_error@winrt@@YAXXZ; winrt::throw_last_error(void)
0x180005f0e  lea     rdx, aImageDimension; "Image dimension parameters too large fo"...
0x180005f15  lea     rcx, [rsp+0B8h+var_68]; this
0x180005f1a  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180005f1f  mov     edx, 80070057h; int
0x180005f24  lea     rcx, [rsp+0B8h+var_88]; this
0x180005f29  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180005f2e  lea     r8, [rsp+0B8h+var_68]
0x180005f33  lea     rcx, [rsp+0B8h+pExceptionObject]
0x180005f38  mov     edx, [rax]
0x180005f3a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &)
0x180005f3f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180005f46  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180005f4b  call    _CxxThrowException
```
