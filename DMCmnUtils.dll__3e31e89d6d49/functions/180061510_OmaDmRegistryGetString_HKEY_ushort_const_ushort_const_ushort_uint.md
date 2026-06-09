# OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)

- ea: `0x180061510`
- end: `0x1800615fd`
- name: `?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z`
- size: `237`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, BYTE *, DWORD cbData)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18005e8e0`
- `0x18005fdd0`
- `0x180060a80`

## callees

- `0x180061510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006156c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006156c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800615b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800615b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800615e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800615e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OmaDmRegistryGetString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        DWORD cbData)
{
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  Type = 1;
  hKey = 0;
  cbData *= 2;
  if ( !a1 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_14;
  }
  if ( !a2 )
  {
    hKey = a1;
LABEL_10:
    v8 = 0;
    v10 = RegQueryValueExW(a1, a3, 0, &Type, a4, &cbData);
    if ( v10 )
    {
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      else
        v8 = v10;
    }
LABEL_14:
    if ( !a2 )
      return v8;
    goto LABEL_15;
  }
  v9 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
  v8 = v9;
  if ( !v9 )
  {
    a1 = hKey;
    goto LABEL_10;
  }
  if ( v9 > 0 )
    v8 = (unsigned __int16)v9 | 0x80070000;
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180061510  mov     [rsp+arg_10], rbx
0x180061515  push    rbp
0x180061516  push    rsi
0x180061517  push    rdi
0x180061518  sub     rsp, 30h
0x18006151c  mov     eax, [rsp+48h+cbData]
0x180061520  mov     rsi, r9
0x180061523  add     eax, eax
0x180061525  mov     [rsp+48h+Type], 1
0x18006152d  mov     [rsp+48h+hKey], 0
0x180061536  mov     rbp, r8
0x180061539  mov     [rsp+48h+cbData], eax
0x18006153d  mov     rdi, rdx
0x180061540  test    rcx, rcx
0x180061543  jnz     short loc_18006154F
0x180061545  mov     ebx, 80070057h
0x18006154a  jmp     loc_1800615D2
0x18006154f  test    rsi, rsi
0x180061552  jz      short loc_180061545
0x180061554  test    rdi, rdi
0x180061557  jz      short loc_180061592
0x180061559  lea     rax, [rsp+48h+hKey]
0x18006155e  mov     r9d, 20119h; samDesired
0x180061564  xor     r8d, r8d; ulOptions
0x180061567  mov     [rsp+48h+phkResult], rax; phkResult
0x18006156c  call    cs:__imp_RegOpenKeyExW
0x180061573  nop     dword ptr [rax+rax+00h]
0x180061578  mov     ebx, eax
0x18006157a  test    eax, eax
0x18006157c  jz      short loc_18006158B
0x18006157e  jle     short loc_1800615D7
0x180061580  movzx   ebx, ax
0x180061583  or      ebx, 80070000h
0x180061589  jmp     short loc_1800615D7
0x18006158b  mov     rcx, [rsp+48h+hKey]; hKey
0x180061590  jmp     short loc_180061597
0x180061592  mov     [rsp+48h+hKey], rcx
0x180061597  lea     rax, [rsp+48h+cbData]
0x18006159c  xor     r8d, r8d; lpReserved
0x18006159f  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800615a4  lea     r9, [rsp+48h+Type]; lpType
0x1800615a9  mov     rdx, rbp; lpValueName
0x1800615ac  mov     [rsp+48h+phkResult], rsi; lpData
0x1800615b1  xor     ebx, ebx
0x1800615b3  call    cs:__imp_RegQueryValueExW
0x1800615ba  nop     dword ptr [rax+rax+00h]
0x1800615bf  test    eax, eax
0x1800615c1  jz      short loc_1800615D2
0x1800615c3  jg      short loc_1800615C9
0x1800615c5  mov     ebx, eax
0x1800615c7  jmp     short loc_1800615D2
0x1800615c9  movzx   ebx, ax
0x1800615cc  or      ebx, 80070000h
0x1800615d2  test    rdi, rdi
0x1800615d5  jz      short loc_1800615ED
0x1800615d7  mov     rcx, [rsp+48h+hKey]; hKey
0x1800615dc  test    rcx, rcx
0x1800615df  jz      short loc_1800615ED
0x1800615e1  call    cs:__imp_RegCloseKey
0x1800615e8  nop     dword ptr [rax+rax+00h]
0x1800615ed  mov     eax, ebx
0x1800615ef  mov     rbx, [rsp+48h+arg_10]
0x1800615f4  add     rsp, 30h
0x1800615f8  pop     rdi
0x1800615f9  pop     rsi
0x1800615fa  pop     rbp
0x1800615fb  retn
```
