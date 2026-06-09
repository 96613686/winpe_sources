# GetLatestCompatibleMinorVersion(_GUID,ushort)

- ea: `0x18014f1e8`
- end: `0x18014f450`
- name: `?GetLatestCompatibleMinorVersion@@YAGU_GUID@@G@Z`
- size: `616`
- prototype: `unsigned __int16 __fastcall(struct _GUID *__struct_ptr, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18014f458`

## callees

- `0x18014f1e8`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!wcsncmp` at `0x18014f391`
- `MSVCR100!wcsncmp` at `0x18014f391`
- `MSVCR100!swscanf_s` at `0x18014f3c4`
- `MSVCR100!swscanf_s` at `0x18014f3c4`
- `MSVCR100!swprintf_s` at `0x18014f24e`
- `MSVCR100!swprintf_s` at `0x18014f24e`
- `ADVAPI32!RegOpenKeyExW` at `0x18014f275`
- `ADVAPI32!RegOpenKeyExW` at `0x18014f2c1`
- `ADVAPI32!RegOpenKeyExW` at `0x18014f275`
- `ADVAPI32!RegOpenKeyExW` at `0x18014f2c1`
- `ADVAPI32!RegEnumKeyExW` at `0x18014f35a`
- `ADVAPI32!RegEnumKeyExW` at `0x18014f35a`
- `ADVAPI32!RegCloseKey` at `0x18014f41d`
- `ADVAPI32!RegCloseKey` at `0x18014f430`
- `ADVAPI32!RegCloseKey` at `0x18014f41d`
- `ADVAPI32!RegCloseKey` at `0x18014f430`
- `ole32!StringFromGUID2` at `0x18014f29b`
- `ole32!StringFromGUID2` at `0x18014f29b`

## pseudocode

```c
__int64 __fastcall GetLatestCompatibleMinorVersion(struct _GUID *a1, unsigned __int16 a2)
{
  unsigned __int16 v3; // [rsp+40h] [rbp-10C0h]
  unsigned __int16 v4; // [rsp+44h] [rbp-10BCh] BYREF
  unsigned __int16 v5; // [rsp+48h] [rbp-10B8h]
  DWORD dwIndex; // [rsp+4Ch] [rbp-10B4h]
  unsigned int MaxCount; // [rsp+50h] [rbp-10B0h]
  DWORD MaxCount_4; // [rsp+54h] [rbp-10ACh] BYREF
  int v9; // [rsp+58h] [rbp-10A8h]
  __int64 v10; // [rsp+60h] [rbp-10A0h]
  HKEY hKey; // [rsp+68h] [rbp-1098h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-1090h] BYREF
  wchar_t *v13; // [rsp+78h] [rbp-1088h]
  wchar_t *v14; // [rsp+80h] [rbp-1080h]
  wchar_t Buffer[12]; // [rsp+88h] [rbp-1078h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-1060h] BYREF
  wchar_t Name[2048]; // [rsp+F0h] [rbp-1010h] BYREF

  hKey = 0;
  phkResult = 0;
  v13 = 0;
  v3 = 0;
  swprintf_s(Buffer, 0xCu, L"%x.", a2);
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Typelib", 0, 0x20019u, &hKey) )
  {
    StringFromGUID2(a1, sz, 39);
    if ( !RegOpenKeyExW(hKey, sz, 0, 0x20019u, &phkResult) )
    {
      v14 = Buffer;
      v10 = -1;
      do
        ++v10;
      while ( v14[v10] );
      MaxCount = v10;
      dwIndex = 0;
      MaxCount_4 = 2048;
      while ( !RegEnumKeyExW(phkResult, dwIndex, Name, &MaxCount_4, 0, 0, 0, 0) )
      {
        ++dwIndex;
        MaxCount_4 = 2048;
        if ( !wcsncmp(Name, Buffer, MaxCount) )
        {
          v13 = &Name[MaxCount];
          v4 = 0;
          swscanf_s(v13, L"%x", &v4);
          if ( *v13 )
            v9 = v4;
          else
            v9 = 0;
          v5 = v9;
          if ( (unsigned __int16)v9 > (int)v3 )
            v3 = v5;
        }
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18014f1e8  mov     [rsp-8+arg_8], dx
0x18014f1ed  mov     [rsp-8+rguid], rcx
0x18014f1f2  push    rbp
0x18014f1f3  mov     rbp, rsp
0x18014f1f6  mov     eax, 1100h
0x18014f1fb  call    _alloca_probe
0x18014f200  sub     rsp, rax
0x18014f203  mov     rax, cs:__security_cookie
0x18014f20a  xor     rax, rsp
0x18014f20d  mov     [rbp+var_10], rax
0x18014f211  mov     [rsp+1100h+hKey], 0
0x18014f21a  mov     [rsp+1100h+var_1090], 0
0x18014f223  mov     [rsp+1100h+var_1088], 0
0x18014f22c  xor     eax, eax
0x18014f22e  mov     [rsp+1100h+var_10C0], ax
0x18014f233  movzx   eax, [rbp+arg_8]
0x18014f237  mov     r9d, eax
0x18014f23a  lea     r8, asc_1803B84F8; "%x."
0x18014f241  mov     edx, 0Ch; BufferCount
0x18014f246  lea     rcx, [rsp+1100h+Buffer]; Buffer
0x18014f24e  call    cs:__imp_swprintf_s
0x18014f254  lea     rax, [rsp+1100h+hKey]
0x18014f259  mov     [rsp+1100h+phkResult], rax; phkResult
0x18014f25e  mov     r9d, 20019h; samDesired
0x18014f264  xor     r8d, r8d; ulOptions
0x18014f267  lea     rdx, aTypelib_2; "Typelib"
0x18014f26e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18014f275  call    cs:__imp_RegOpenKeyExW
0x18014f27b  test    eax, eax
0x18014f27d  jz      short loc_18014F289
0x18014f27f  jmp     loc_18014F410
0x18014f284  jmp     loc_18014F410
0x18014f289  mov     r8d, 27h ; '''; cchMax
0x18014f28f  lea     rdx, [rsp+1100h+sz]; lpsz
0x18014f297  mov     rcx, [rbp+rguid]; rguid
0x18014f29b  call    cs:__imp_StringFromGUID2
0x18014f2a1  lea     rax, [rsp+1100h+var_1090]
0x18014f2a6  mov     [rsp+1100h+phkResult], rax; phkResult
0x18014f2ab  mov     r9d, 20019h; samDesired
0x18014f2b1  xor     r8d, r8d; ulOptions
0x18014f2b4  lea     rdx, [rsp+1100h+sz]; lpSubKey
0x18014f2bc  mov     rcx, [rsp+1100h+hKey]; hKey
0x18014f2c1  call    cs:__imp_RegOpenKeyExW
0x18014f2c7  test    eax, eax
0x18014f2c9  jz      short loc_18014F2D5
0x18014f2cb  jmp     loc_18014F410
0x18014f2d0  jmp     loc_18014F410
0x18014f2d5  lea     rax, [rsp+1100h+Buffer]
0x18014f2dd  mov     [rsp+1100h+var_1080], rax
0x18014f2e5  mov     [rsp+1100h+var_10A0], 0FFFFFFFFFFFFFFFFh
0x18014f2ee  inc     [rsp+1100h+var_10A0]
0x18014f2f3  mov     rax, [rsp+1100h+var_1080]
0x18014f2fb  mov     rcx, [rsp+1100h+var_10A0]
0x18014f300  cmp     word ptr [rax+rcx*2], 0
0x18014f305  jnz     short loc_18014F2EE
0x18014f307  mov     rax, [rsp+1100h+var_10A0]
0x18014f30c  mov     dword ptr [rsp+1100h+MaxCount], eax
0x18014f310  mov     [rsp+1100h+dwIndex], 0
0x18014f318  mov     dword ptr [rsp+1100h+MaxCount+4], 800h
0x18014f320  mov     [rsp+1100h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18014f329  mov     [rsp+1100h+lpcchClass], 0; lpcchClass
0x18014f332  mov     [rsp+1100h+lpClass], 0; lpClass
0x18014f33b  mov     [rsp+1100h+phkResult], 0; lpReserved
0x18014f344  lea     r9, [rsp+1100h+MaxCount+4]; lpcchName
0x18014f349  lea     r8, [rsp+1100h+Name]; lpName
0x18014f351  mov     edx, [rsp+1100h+dwIndex]; dwIndex
0x18014f355  mov     rcx, [rsp+1100h+var_1090]; hKey
0x18014f35a  call    cs:__imp_RegEnumKeyExW
0x18014f360  test    eax, eax
0x18014f362  jnz     loc_18014F410
0x18014f368  mov     eax, [rsp+1100h+dwIndex]
0x18014f36c  inc     eax
0x18014f36e  mov     [rsp+1100h+dwIndex], eax
0x18014f372  mov     dword ptr [rsp+1100h+MaxCount+4], 800h
0x18014f37a  mov     eax, dword ptr [rsp+1100h+MaxCount]
0x18014f37e  mov     r8d, eax; MaxCount
0x18014f381  lea     rdx, [rsp+1100h+Buffer]; String2
0x18014f389  lea     rcx, [rsp+1100h+Name]; String1
0x18014f391  call    cs:__imp_wcsncmp
0x18014f397  test    eax, eax
0x18014f399  jnz     short loc_18014F40B
0x18014f39b  mov     eax, dword ptr [rsp+1100h+MaxCount]
0x18014f39f  lea     rax, [rsp+rax*2+1100h+Name]
0x18014f3a7  mov     [rsp+1100h+var_1088], rax
0x18014f3ac  xor     eax, eax
0x18014f3ae  mov     [rsp+1100h+var_10BC], ax
0x18014f3b3  lea     r8, [rsp+1100h+var_10BC]
0x18014f3b8  lea     rdx, asc_1803B8510; "%x"
0x18014f3bf  mov     rcx, [rsp+1100h+var_1088]; Buffer
0x18014f3c4  call    cs:__imp_swscanf_s
0x18014f3ca  mov     rax, [rsp+1100h+var_1088]
0x18014f3cf  movzx   eax, word ptr [rax]
0x18014f3d2  test    eax, eax
0x18014f3d4  jz      short loc_18014F3E1
0x18014f3d6  movzx   eax, [rsp+1100h+var_10BC]
0x18014f3db  mov     [rsp+1100h+var_10A8], eax
0x18014f3df  jmp     short loc_18014F3E9
0x18014f3e1  mov     [rsp+1100h+var_10A8], 0
0x18014f3e9  movzx   eax, word ptr [rsp+1100h+var_10A8]
0x18014f3ee  mov     [rsp+1100h+var_10B8], ax
0x18014f3f3  movzx   eax, [rsp+1100h+var_10B8]
0x18014f3f8  movzx   ecx, [rsp+1100h+var_10C0]
0x18014f3fd  cmp     eax, ecx
0x18014f3ff  jle     short loc_18014F40B
0x18014f401  movzx   eax, [rsp+1100h+var_10B8]
0x18014f406  mov     [rsp+1100h+var_10C0], ax
0x18014f40b  jmp     loc_18014F320
0x18014f410  cmp     [rsp+1100h+var_1090], 0
0x18014f416  jz      short loc_18014F423
0x18014f418  mov     rcx, [rsp+1100h+var_1090]; hKey
0x18014f41d  call    cs:__imp_RegCloseKey
0x18014f423  cmp     [rsp+1100h+hKey], 0
0x18014f429  jz      short loc_18014F436
0x18014f42b  mov     rcx, [rsp+1100h+hKey]; hKey
0x18014f430  call    cs:__imp_RegCloseKey
0x18014f436  movzx   eax, [rsp+1100h+var_10C0]
0x18014f43b  mov     rcx, [rbp+var_10]
0x18014f43f  xor     rcx, rsp; StackCookie
0x18014f442  call    __security_check_cookie
0x18014f447  add     rsp, 1100h
0x18014f44e  pop     rbp
0x18014f44f  retn
```
