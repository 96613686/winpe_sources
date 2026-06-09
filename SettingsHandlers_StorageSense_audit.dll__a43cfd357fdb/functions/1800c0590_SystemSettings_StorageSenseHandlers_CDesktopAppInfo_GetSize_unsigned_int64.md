# SystemSettings::StorageSenseHandlers::CDesktopAppInfo::GetSize(unsigned __int64 *)

- ea: `0x1800c0590`
- end: `0x1800c067b`
- name: `?GetSize@CDesktopAppInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEA_K@Z`
- size: `235`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CDesktopAppInfo *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800c0590`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c05e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c05e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c05cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c0601`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c05cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c0601`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c063e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c063e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0659`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0663`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0659`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0663`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CDesktopAppInfo::GetSize(
        SystemSettings::StorageSenseHandlers::CDesktopAppInfo *this,
        unsigned __int64 *a2)
{
  unsigned int v4; // edi
  const WCHAR *StringRawBuffer; // rax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  unsigned int Data; // [rsp+70h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+40h] BYREF

  hKey = 0;
  phkResult = 0;
  v4 = RegOpenKeyExW(*((HKEY *)this + 13), (LPCWSTR)this + 56, 0, 0x20019u, &hKey);
  if ( !v4 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 5), 0);
    v4 = RegOpenKeyExW(hKey, StringRawBuffer, 0, 0x20019u, &phkResult);
    if ( !v4 )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      v4 = RegQueryValueExW(phkResult, L"EstimatedSize", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( !v4 )
        *((_QWORD *)this + 12) = (unsigned __int64)Data << 10;
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  *a2 = *((_QWORD *)this + 12);
  return v4;
}

```

## disassembly

```asm
0x1800c0590  push    rbp
0x1800c0592  push    rbx
0x1800c0593  push    rsi
0x1800c0594  push    rdi
0x1800c0595  mov     rbp, rsp
0x1800c0598  sub     rsp, 48h
0x1800c059c  mov     rsi, rdx
0x1800c059f  mov     [rbp+hKey], 0
0x1800c05a7  lea     rdx, [rcx+70h]; lpSubKey
0x1800c05ab  mov     [rbp+arg_18], 0
0x1800c05b3  mov     rbx, rcx
0x1800c05b6  lea     rax, [rbp+hKey]
0x1800c05ba  mov     rcx, [rcx+68h]; hKey
0x1800c05be  mov     r9d, 20019h; samDesired
0x1800c05c4  xor     r8d, r8d; ulOptions
0x1800c05c7  mov     [rsp+48h+phkResult], rax; phkResult
0x1800c05cc  call    cs:__imp_RegOpenKeyExW
0x1800c05d2  mov     edi, eax
0x1800c05d4  test    eax, eax
0x1800c05d6  jnz     loc_1800C0669
0x1800c05dc  mov     rcx, [rbx+28h]; string
0x1800c05e0  xor     edx, edx; length
0x1800c05e2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c05e8  lea     rcx, [rbp+arg_18]
0x1800c05ec  mov     r9d, 20019h; samDesired
0x1800c05f2  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800c05f7  xor     r8d, r8d; ulOptions
0x1800c05fa  mov     rcx, [rbp+hKey]; hKey
0x1800c05fe  mov     rdx, rax; lpSubKey
0x1800c0601  call    cs:__imp_RegOpenKeyExW
0x1800c0607  mov     edi, eax
0x1800c0609  test    eax, eax
0x1800c060b  jnz     short loc_1800C065F
0x1800c060d  mov     rcx, [rbp+arg_18]; hKey
0x1800c0611  lea     r9, [rbp+Type]; lpType
0x1800c0615  mov     [rbp+Type], eax
0x1800c0618  lea     rdx, aEstimatedsize; "EstimatedSize"
0x1800c061f  mov     [rbp+Data], eax
0x1800c0622  xor     r8d, r8d; lpReserved
0x1800c0625  lea     rax, [rbp+cbData]
0x1800c0629  mov     [rbp+cbData], 4
0x1800c0630  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800c0635  lea     rax, [rbp+Data]
0x1800c0639  mov     [rsp+48h+phkResult], rax; lpData
0x1800c063e  call    cs:__imp_RegQueryValueExW
0x1800c0644  mov     edi, eax
0x1800c0646  test    eax, eax
0x1800c0648  jnz     short loc_1800C0655
0x1800c064a  mov     eax, [rbp+Data]
0x1800c064d  shl     rax, 0Ah
0x1800c0651  mov     [rbx+60h], rax
0x1800c0655  mov     rcx, [rbp+arg_18]; hKey
0x1800c0659  call    cs:__imp_RegCloseKey
0x1800c065f  mov     rcx, [rbp+hKey]; hKey
0x1800c0663  call    cs:__imp_RegCloseKey
0x1800c0669  mov     rax, [rbx+60h]
0x1800c066d  mov     [rsi], rax
0x1800c0670  mov     eax, edi
0x1800c0672  add     rsp, 48h
0x1800c0676  pop     rdi
0x1800c0677  pop     rsi
0x1800c0678  pop     rbx
0x1800c0679  pop     rbp
0x1800c067a  retn
```
