# CRegistryChangeListener::_RestoreChangeCallback(void)

- ea: `0x180009618`
- end: `0x180009709`
- name: `?_RestoreChangeCallback@CRegistryChangeListener@@AEAAJXZ`
- size: `241`
- prototype: `int __fastcall(CRegistryChangeListener *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009280`
- `0x180009468`

## callees

- `0x180009618`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009666`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009666`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800096ab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800096ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009676`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009676`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800096e7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800096e7`

## pseudocode

```c
int __fastcall CRegistryChangeListener::_RestoreChangeCallback(CRegistryChangeListener *this)
{
  HKEY *phkResult; // rbx
  const WCHAR *v3; // rdx
  int result; // eax
  bool v5; // sf

  phkResult = (HKEY *)((char *)this + 32);
  if ( (*((_BYTE *)this + 88) & 1) == 0 || RegQueryInfoKeyW(*phkResult, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0) != 1018 )
    goto LABEL_6;
  RegCloseKey(*phkResult);
  v3 = (const WCHAR *)*((_QWORD *)this + 10);
  *phkResult = 0;
  result = RegCreateKeyExW(HKEY_CURRENT_USER, v3, 0, 0, 0, 0x20019u, 0, phkResult, 0);
  v5 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result < 0;
  }
  if ( !v5 )
  {
LABEL_6:
    result = RegNotifyChangeKeyValue(
               *phkResult,
               (*((_DWORD *)this + 22) >> 1) & 1,
               (*((_DWORD *)this + 22) & 4 | 0x10u) >> 2,
               *((HANDLE *)this + 3),
               1);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180009618  mov     rax, rsp
0x18000961b  mov     [rax+8], rbx
0x18000961f  mov     [rax+10h], rsi
0x180009623  push    rdi
0x180009624  sub     rsp, 60h
0x180009628  xor     esi, esi
0x18000962a  lea     rbx, [rcx+20h]
0x18000962e  test    byte ptr [rcx+58h], 1
0x180009632  mov     rdi, rcx
0x180009635  jz      loc_1800096C1
0x18000963b  mov     rcx, [rbx]; hKey
0x18000963e  xor     r9d, r9d; lpReserved
0x180009641  mov     [rax-10h], rsi
0x180009645  xor     r8d, r8d; lpcchClass
0x180009648  mov     [rax-18h], rsi
0x18000964c  xor     edx, edx; lpClass
0x18000964e  mov     [rax-20h], rsi
0x180009652  mov     [rax-28h], rsi
0x180009656  mov     [rax-30h], rsi
0x18000965a  mov     [rax-38h], rsi
0x18000965e  mov     [rax-40h], rsi
0x180009662  mov     [rax-48h], rsi
0x180009666  call    cs:__imp_RegQueryInfoKeyW
0x18000966c  cmp     eax, 3FAh
0x180009671  jnz     short loc_1800096C1
0x180009673  mov     rcx, [rbx]; hKey
0x180009676  call    cs:__imp_RegCloseKey
0x18000967c  mov     rdx, [rdi+50h]; lpSubKey
0x180009680  xor     r9d, r9d; lpClass
0x180009683  mov     [rsp+68h+lpdwDisposition], rsi; lpdwDisposition
0x180009688  xor     r8d, r8d; Reserved
0x18000968b  mov     [rsp+68h+phkResult], rbx; phkResult
0x180009690  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009697  mov     [rsp+68h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000969c  mov     [rsp+68h+samDesired], 20019h; samDesired
0x1800096a4  mov     [rsp+68h+dwOptions], esi; dwOptions
0x1800096a8  mov     [rbx], rsi
0x1800096ab  call    cs:__imp_RegCreateKeyExW
0x1800096b1  test    eax, eax
0x1800096b3  jle     short loc_1800096BF
0x1800096b5  movzx   eax, ax
0x1800096b8  or      eax, 80070000h
0x1800096bd  test    eax, eax
0x1800096bf  js      short loc_1800096F9
0x1800096c1  mov     edx, [rdi+58h]
0x1800096c4  mov     r8d, edx
0x1800096c7  mov     r9, [rdi+18h]; hEvent
0x1800096cb  and     r8d, 4
0x1800096cf  mov     rcx, [rbx]; hKey
0x1800096d2  or      r8d, 10h
0x1800096d6  shr     edx, 1
0x1800096d8  shr     r8d, 2; dwNotifyFilter
0x1800096dc  and     edx, 1; bWatchSubtree
0x1800096df  mov     [rsp+68h+dwOptions], 1; fAsynchronous
0x1800096e7  call    cs:__imp_RegNotifyChangeKeyValue
0x1800096ed  test    eax, eax
0x1800096ef  jle     short loc_1800096F9
0x1800096f1  movzx   eax, ax
0x1800096f4  or      eax, 80070000h
0x1800096f9  mov     rbx, [rsp+68h+arg_0]
0x1800096fe  mov     rsi, [rsp+68h+arg_8]
0x180009703  add     rsp, 60h
0x180009707  pop     rdi
0x180009708  retn
```
