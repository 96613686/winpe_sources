# WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *,WaasMedic::RegistryHiveType)

- ea: `0x1800268f4`
- end: `0x1800269ef`
- name: `?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAKW4RegistryHiveType@1@@Z`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180023df0`
- `0x180023f40`
- `0x180024460`
- `0x180024610`
- `0x180024a10`
- `0x1800254f4`
- `0x180029494`
- `0x18002a7ec`
- `0x18002d108`
- `0x18002d468`
- `0x18002f414`
- `0x1800384a0`
- `0x180061790`

## callees

- `0x1800268f4`
- `0x1800269f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026959`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026959`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800269ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800269ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800269de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800269de`

## pseudocode

```c
LSTATUS __fastcall WaasMedic::RegQueryDwordValue(__int64 a1, const WCHAR *a2, HKEY a3, const unsigned __int16 *a4)
{
  LSTATUS result; // eax
  bool v8; // zf
  REGSAM v9; // ebx
  unsigned int *v10; // r9
  int DwordValue; // ebx
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+8h] BYREF

  hKey = 0;
  if ( !a4 )
    return -2147467261;
  v8 = dword_1800A55AC == 0;
  v9 = 1;
  *(_DWORD *)a4 = 0;
  if ( v8 )
  {
    dword_1800A55B0 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  if ( dword_1800A55B0 )
    v9 = 257;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v9, &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    DwordValue = WaasMedic::RegQueryDwordValue((WaasMedic *)hKey, a3, a4, v10);
    RegCloseKey(hKey);
    return DwordValue;
  }
  return result;
}

```

## disassembly

```asm
0x1800268f4  mov     rax, rsp
0x1800268f7  mov     [rax+8], rcx
0x1800268fb  push    rbx
0x1800268fc  push    rbp
0x1800268fd  push    rsi
0x1800268fe  push    rdi
0x1800268ff  sub     rsp, 68h
0x180026903  mov     qword ptr [rax+8], 0
0x18002690b  mov     rdi, r9
0x18002690e  mov     rsi, r8
0x180026911  mov     rbp, rdx
0x180026914  test    r9, r9
0x180026917  jnz     short loc_180026923
0x180026919  mov     eax, 80004003h
0x18002691e  jmp     loc_1800269E6
0x180026923  cmp     cs:dword_1800A55AC, 0
0x18002692a  mov     ebx, 1
0x18002692f  mov     dword ptr [r9], 0
0x180026936  jnz     short loc_18002697F
0x180026938  xorps   xmm0, xmm0
0x18002693b  mov     cs:dword_1800A55B0, 0
0x180026945  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18002694a  movups  xmmword ptr [rsp+88h+SystemInfo], xmm0
0x18002694f  movups  xmmword ptr [rsp+88h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180026954  movups  xmmword ptr [rsp+88h+SystemInfo.dwNumberOfProcessors], xmm0
0x180026959  call    cs:__imp_GetNativeSystemInfo
0x18002695f  lea     eax, [rbx+5]
0x180026962  cmp     ax, word ptr [rsp+88h+SystemInfo]
0x180026967  jz      short loc_180026973
0x180026969  lea     eax, [rbx+8]
0x18002696c  cmp     ax, word ptr [rsp+88h+SystemInfo]
0x180026971  jnz     short loc_180026979
0x180026973  mov     cs:dword_1800A55B0, ebx
0x180026979  mov     cs:dword_1800A55AC, ebx
0x18002697f  cmp     cs:dword_1800A55B0, 0
0x180026986  mov     eax, 101h
0x18002698b  cmovnz  ebx, eax
0x18002698e  lea     rax, [rsp+88h+hKey]
0x180026996  mov     r9d, ebx; samDesired
0x180026999  xor     r8d, r8d; ulOptions
0x18002699c  mov     [rsp+88h+phkResult], rax; phkResult
0x1800269a1  mov     rdx, rbp; lpSubKey
0x1800269a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800269ab  call    cs:__imp_RegOpenKeyExW
0x1800269b1  test    eax, eax
0x1800269b3  jz      short loc_1800269C1
0x1800269b5  jle     short loc_1800269E6
0x1800269b7  movzx   eax, ax
0x1800269ba  or      eax, 80070000h
0x1800269bf  jmp     short loc_1800269E6
0x1800269c1  mov     rcx, [rsp+88h+hKey]; this
0x1800269c9  mov     r8, rdi; unsigned __int16 *
0x1800269cc  mov     rdx, rsi; HKEY
0x1800269cf  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x1800269d4  mov     rcx, [rsp+88h+hKey]; hKey
0x1800269dc  mov     ebx, eax
0x1800269de  call    cs:__imp_RegCloseKey
0x1800269e4  mov     eax, ebx
0x1800269e6  add     rsp, 68h
0x1800269ea  pop     rdi
0x1800269eb  pop     rsi
0x1800269ec  pop     rbp
0x1800269ed  pop     rbx
0x1800269ee  retn
```
