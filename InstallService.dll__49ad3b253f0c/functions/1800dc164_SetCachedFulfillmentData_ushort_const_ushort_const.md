# SetCachedFulfillmentData(ushort const *,ushort const *)

- ea: `0x1800dc164`
- end: `0x1800dc2c6`
- name: `?SetCachedFulfillmentData@@YAJPEBG0@Z`
- size: `354`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, PCWSTR lpData)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006c230`
- `0x1800803e4`
- `0x1800da3ec`
- `0x1800db024`
- `0x1800dc4b4`

## callees

- `0x180024fe0`
- `0x180043320`
- `0x1800d9d64`
- `0x1800da1d4`
- `0x1800dae90`
- `0x1800dc164`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dc286`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dc286`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc18a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc1e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc1fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc23c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc29e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc2ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc18a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc1e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc1fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc23c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc29e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc2ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc1c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc220`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc1c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc220`

## string_xrefs

- `0x1800dc250`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State\CategoryCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall SetCachedFulfillmentData(LPCWSTR lpValueName, PCWSTR lpData)
{
  char v4; // bp
  PCWSTR StringRawBuffer; // r8
  Microsoft::WRL::Wrappers::Details **v6; // rdi
  Microsoft::WRL::Wrappers::Details *v7; // rbx
  HSTRING v8; // r8
  HSTRING v9; // rdi
  __int64 v10; // rdi
  const WCHAR *RegistryLocation; // rax
  LSTATUS v12; // eax
  unsigned int v13; // edi
  HSTRING string; // [rsp+80h] [rbp+18h] BYREF
  HSTRING v16; // [rsp+88h] [rbp+20h] BYREF

  v4 = 0;
  LODWORD(string) = 0;
  WindowsDeleteString(0);
  string = 0;
  if ( (int)GetCachedLastScanTime(lpValueName, &string) < 0 )
  {
    StringRawBuffer = 0;
  }
  else
  {
    DeleteFulfillmentCachePlaceholder(lpValueName);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  }
  v6 = (Microsoft::WRL::Wrappers::Details **)FormatFulfillmentDataJson(&v16, lpData, StringRawBuffer);
  WindowsDeleteString(0);
  v7 = *v6;
  *v6 = 0;
  WindowsDeleteString(v16);
  if ( v7 )
  {
    v9 = 0;
    v4 = 1;
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(v7, 0, v8) )
      lpData = WindowsGetStringRawBuffer((HSTRING)v7, 0);
  }
  else
  {
    v9 = string;
  }
  if ( (v4 & 1) != 0 )
    WindowsDeleteString(v9);
  v10 = -1;
  do
    ++v10;
  while ( lpData[v10] );
  RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                                      (__int64)&qword_1802CAE68,
                                      (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State\\CategoryCache");
  v12 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, RegistryLocation, lpValueName, 1u, lpData, 2 * v10 + 2);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  WindowsDeleteString((HSTRING)v7);
  WindowsDeleteString(string);
  return v13;
}

```

## disassembly

```asm
0x1800dc164  mov     [rsp+arg_0], rbx
0x1800dc169  push    rbp
0x1800dc16a  push    rsi
0x1800dc16b  push    rdi
0x1800dc16c  push    r14
0x1800dc16e  push    r15
0x1800dc170  sub     rsp, 40h
0x1800dc174  mov     rsi, rdx
0x1800dc177  mov     r14, rcx
0x1800dc17a  xor     r15d, r15d
0x1800dc17d  mov     ebp, r15d
0x1800dc180  mov     dword ptr [rsp+68h+string], r15d
0x1800dc188  xor     ecx, ecx; string
0x1800dc18a  call    cs:__imp_WindowsDeleteString
0x1800dc190  mov     [rsp+68h+string], r15
0x1800dc198  lea     rdx, [rsp+68h+string]; HSTRING *
0x1800dc1a0  mov     rcx, r14; lpValue
0x1800dc1a3  call    ?GetCachedLastScanTime@@YAJPEBGPEAPEAUHSTRING__@@@Z; GetCachedLastScanTime(ushort const *,HSTRING__ * *)
0x1800dc1a8  mov     [rsp+68h+var_38], r15
0x1800dc1ad  test    eax, eax
0x1800dc1af  js      short loc_1800DC1CE
0x1800dc1b1  mov     rcx, r14; lpValueName
0x1800dc1b4  call    ?DeleteFulfillmentCachePlaceholder@@YAJPEBG@Z; DeleteFulfillmentCachePlaceholder(ushort const *)
0x1800dc1b9  xor     edx, edx; length
0x1800dc1bb  mov     rcx, [rsp+68h+string]; string
0x1800dc1c3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc1c9  mov     r8, rax
0x1800dc1cc  jmp     short loc_1800DC1D1
0x1800dc1ce  xor     r8d, r8d
0x1800dc1d1  mov     rdx, rsi
0x1800dc1d4  lea     rcx, [rsp+68h+arg_18]
0x1800dc1dc  call    ?FormatFulfillmentDataJson@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG0@Z; FormatFulfillmentDataJson(ushort const *,ushort const *)
0x1800dc1e1  mov     rdi, rax
0x1800dc1e4  xor     ecx, ecx; string
0x1800dc1e6  call    cs:__imp_WindowsDeleteString
0x1800dc1ec  mov     rbx, [rdi]
0x1800dc1ef  mov     [rdi], r15
0x1800dc1f2  mov     rcx, [rsp+68h+arg_18]; string
0x1800dc1fa  call    cs:__imp_WindowsDeleteString
0x1800dc200  test    rbx, rbx
0x1800dc203  jz      short loc_1800DC22B
0x1800dc205  mov     rdi, r15
0x1800dc208  mov     ebp, 1
0x1800dc20d  xor     edx, edx; HSTRING
0x1800dc20f  mov     rcx, rbx; this
0x1800dc212  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800dc217  test    eax, eax
0x1800dc219  jz      short loc_1800DC233
0x1800dc21b  xor     edx, edx; length
0x1800dc21d  mov     rcx, rbx; string
0x1800dc220  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc226  mov     rsi, rax
0x1800dc229  jmp     short loc_1800DC233
0x1800dc22b  mov     rdi, [rsp+68h+string]
0x1800dc233  test    bpl, 1
0x1800dc237  jz      short loc_1800DC242
0x1800dc239  mov     rcx, rdi; string
0x1800dc23c  call    cs:__imp_WindowsDeleteString
0x1800dc242  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800dc246  inc     rdi
0x1800dc249  cmp     [rsi+rdi*2], r15w
0x1800dc24e  jnz     short loc_1800DC246
0x1800dc250  lea     rdx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800dc257  lea     rcx, qword_1802CAE68
0x1800dc25e  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x1800dc263  lea     ecx, ds:2[rdi*2]
0x1800dc26a  mov     [rsp+68h+cbData], ecx; cbData
0x1800dc26e  mov     [rsp+68h+lpData], rsi; lpData
0x1800dc273  mov     r9d, 1; dwType
0x1800dc279  mov     r8, r14; lpValueName
0x1800dc27c  mov     rdx, rax; lpSubKey
0x1800dc27f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dc286  call    cs:__imp_RegSetKeyValueW
0x1800dc28c  mov     edi, eax
0x1800dc28e  test    eax, eax
0x1800dc290  jle     short loc_1800DC29B
0x1800dc292  movzx   edi, ax
0x1800dc295  or      edi, 80070000h
0x1800dc29b  mov     rcx, rbx; string
0x1800dc29e  call    cs:__imp_WindowsDeleteString
0x1800dc2a4  nop
0x1800dc2a5  mov     rcx, [rsp+68h+string]; string
0x1800dc2ad  call    cs:__imp_WindowsDeleteString
0x1800dc2b3  mov     eax, edi
0x1800dc2b5  mov     rbx, [rsp+68h+arg_0]
0x1800dc2ba  add     rsp, 40h
0x1800dc2be  pop     r15
0x1800dc2c0  pop     r14
0x1800dc2c2  pop     rdi
0x1800dc2c3  pop     rsi
0x1800dc2c4  pop     rbp
0x1800dc2c5  retn
```
