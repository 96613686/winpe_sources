# AccProvpInitProviders

- ea: `0x18002a088`
- end: `0x18002a2ec`
- name: `AccProvpInitProviders`
- size: `612`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `20`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029d20`
- `0x1800498c4`
- `0x180049a90`
- `0x180049b9c`
- `0x180049d50`
- `0x180049df0`
- `0x180049e60`
- `0x180049fc0`
- `0x18004a3b0`
- `0x18004a4f0`
- `0x18004a750`
- `0x18004aa30`
- `0x18004ab40`
- `0x18004ad70`
- `0x18004b170`
- `0x18004b600`
- `0x18004b930`
- `0x18004bd60`
- `0x18004c0b0`
- `0x18004c300`

## callees

- `0x180029b98`
- `0x18002a088`
- `0x18002a2f4`
- `0x18002a420`

## import_xrefs

- `msvcrt!wcschr` at `0x18002a1d1`
- `msvcrt!wcschr` at `0x18002a2a5`
- `msvcrt!wcschr` at `0x18002a1d1`
- `msvcrt!wcschr` at `0x18002a2a5`
- `KERNELBASE!LocalAlloc` at `0x18002a1a5`
- `KERNELBASE!LocalAlloc` at `0x18002a1a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a256`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a256`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a0fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a0fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a159`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a159`
- `KERNEL32!LocalFree` at `0x18002a14a`
- `KERNEL32!LocalFree` at `0x18002a14a`
- `KERNEL32!EnterCriticalSection` at `0x18002a0ac`
- `KERNEL32!EnterCriticalSection` at `0x18002a0ac`
- `KERNEL32!LeaveCriticalSection` at `0x18002a0c5`
- `KERNEL32!LeaveCriticalSection` at `0x18002a0c5`

## string_xrefs

- `0x18002a0ee`: `System\CurrentControlSet\Control\LSA\AccessProviders`
- `0x18002a244`: `RequireUniqueAccessibility`

## pseudocode

```c
__int64 __fastcall AccProvpInitProviders(__int64 a1)
{
  unsigned int StringFromRegistry; // ebx
  __int64 v3; // rax
  __int64 Data; // [rsp+80h] [rbp+40h]
  HKEY hKey; // [rsp+98h] [rbp+58h] BYREF

  Data = a1;
  hKey = 0;
  EnterCriticalSection(&gAccProviders);
  if ( (qword_1800A34E8 & 2) != 0 )
  {
    StringFromRegistry = 0;
  }
  else
  {
    StringFromRegistry = RegOpenKeyExW(
                           HKEY_LOCAL_MACHINE,
                           L"System\\CurrentControlSet\\Control\\LSA\\AccessProviders",
                           0,
                           0x20019u,
                           &hKey);
    if ( !StringFromRegistry )
    {
      StringFromRegistry = AccProvpGetStringFromRegistry(hKey, L"ProviderOrder");
      if ( !StringFromRegistry )
      {
        v3 = -1;
        do
          ++v3;
        while ( *(_WORD *)(2 * v3) );
        StringFromRegistry = 13;
        LocalFree(0);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  LeaveCriticalSection(&gAccProviders);
  return StringFromRegistry;
}

```

## disassembly

```asm
0x18002a088  mov     [rsp-38h+Data], rcx
0x18002a08d  push    rbp
0x18002a08e  push    rbx
0x18002a08f  push    rsi
0x18002a090  push    rdi
0x18002a091  push    r12
0x18002a093  push    r13
0x18002a095  push    r14
0x18002a097  mov     rbp, rsp
0x18002a09a  sub     rsp, 40h
0x18002a09e  xor     r12d, r12d
0x18002a0a1  lea     rcx, gAccProviders; lpCriticalSection
0x18002a0a8  mov     [rbp+hKey], r12
0x18002a0ac  call    cs:__imp_EnterCriticalSection
0x18002a0b2  test    byte ptr cs:qword_1800A34E8, 2
0x18002a0b9  jz      short loc_18002A0DC
0x18002a0bb  mov     ebx, r12d
0x18002a0be  lea     rcx, gAccProviders; lpCriticalSection
0x18002a0c5  call    cs:__imp_LeaveCriticalSection
0x18002a0cb  mov     eax, ebx
0x18002a0cd  add     rsp, 40h
0x18002a0d1  pop     r14
0x18002a0d3  pop     r13
0x18002a0d5  pop     r12
0x18002a0d7  pop     rdi
0x18002a0d8  pop     rsi
0x18002a0d9  pop     rbx
0x18002a0da  pop     rbp
0x18002a0db  retn
0x18002a0dc  lea     rax, [rbp+hKey]
0x18002a0e0  mov     r9d, 20019h; samDesired
0x18002a0e6  xor     r8d, r8d; ulOptions
0x18002a0e9  mov     [rsp+40h+phkResult], rax; phkResult
0x18002a0ee  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\LSA"...
0x18002a0f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a0fc  call    cs:__imp_RegOpenKeyExW
0x18002a102  mov     ebx, eax
0x18002a104  test    eax, eax
0x18002a106  jnz     short loc_18002A150
0x18002a108  mov     rcx, [rbp+hKey]; hKey
0x18002a10c  lea     r8, [rbp+hMem]
0x18002a110  lea     rdx, aProviderorder; "ProviderOrder"
0x18002a117  mov     [rbp+hMem], r12
0x18002a11b  call    AccProvpGetStringFromRegistry
0x18002a120  mov     ebx, eax
0x18002a122  test    eax, eax
0x18002a124  jnz     short loc_18002A150
0x18002a126  mov     rcx, [rbp+hMem]; Str
0x18002a12a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a12e  inc     rax
0x18002a131  cmp     [rcx+rax*2], r12w
0x18002a136  jnz     short loc_18002A12E
0x18002a138  test    rax, rax
0x18002a13b  jnz     loc_18002A28E
0x18002a141  mov     ebx, 0Dh
0x18002a146  mov     rcx, [rbp+hMem]; hMem
0x18002a14a  call    cs:__imp_LocalFree
0x18002a150  mov     rcx, [rbp+hKey]; hKey
0x18002a154  test    rcx, rcx
0x18002a157  jz      short loc_18002A15F
0x18002a159  call    cs:__imp_RegCloseKey
0x18002a15f  test    ebx, ebx
0x18002a161  jnz     loc_18002A0BE
0x18002a167  call    AccProvpLoadMartaFunctions
0x18002a16c  mov     ebx, eax
0x18002a16e  test    eax, eax
0x18002a170  jnz     loc_18002A0BE
0x18002a176  or      dword ptr cs:qword_1800A34E8, 2
0x18002a17d  jmp     loc_18002A0BE
0x18002a182  test    ebx, ebx
0x18002a184  jz      short loc_18002A141
0x18002a186  mov     dword ptr cs:qword_1800A34E8+4, ebx
0x18002a18c  cmp     ebx, 1555555h
0x18002a192  ja      loc_18002A273
0x18002a198  lea     rdx, [rbx+rbx*2]
0x18002a19c  mov     ecx, 40h ; '@'; uFlags
0x18002a1a1  shl     rdx, 6; uBytes
0x18002a1a5  call    cs:__imp_LocalAlloc
0x18002a1ab  mov     cs:qword_1800A34F0, rax
0x18002a1b2  test    rax, rax
0x18002a1b5  jz      loc_18002A27A
0x18002a1bb  mov     rsi, [rbp+hMem]
0x18002a1bf  mov     r14d, r12d
0x18002a1c2  test    rsi, rsi
0x18002a1c5  jz      loc_18002A284
0x18002a1cb  mov     edx, r13d; Ch
0x18002a1ce  mov     rcx, rsi; Str
0x18002a1d1  call    cs:__imp_wcschr
0x18002a1d7  mov     rdi, rax
0x18002a1da  test    rax, rax
0x18002a1dd  jnz     loc_18002A2C0
0x18002a1e3  mov     ecx, r14d
0x18002a1e6  mov     rdx, rsi
0x18002a1e9  lea     r8, [rcx+rcx*2]
0x18002a1ed  mov     rcx, [rbp+hKey]
0x18002a1f1  shl     r8, 6
0x18002a1f5  add     r8, cs:qword_1800A34F0
0x18002a1fc  call    AccProvpLoadProviderDef
0x18002a201  test    rdi, rdi
0x18002a204  jnz     loc_18002A2C9
0x18002a20a  test    eax, eax
0x18002a20c  lea     ecx, [r14+1]
0x18002a210  mov     rsi, rdi
0x18002a213  cmovnz  ecx, r14d
0x18002a217  mov     r14d, ecx
0x18002a21a  test    rdi, rdi
0x18002a21d  jnz     short loc_18002A1CB
0x18002a21f  test    ecx, ecx
0x18002a221  jz      short loc_18002A284
0x18002a223  mov     rcx, [rbp+hKey]; hKey
0x18002a227  lea     rax, [rbp+cbData]
0x18002a22b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002a230  lea     r9, [rbp+Type]; lpType
0x18002a234  lea     rax, [rbp+Data]
0x18002a238  mov     [rbp+Type], r12d
0x18002a23c  xor     r8d, r8d; lpReserved
0x18002a23f  mov     [rsp+40h+phkResult], rax; lpData
0x18002a244  lea     rdx, aRequireuniquea; "RequireUniqueAccessibility"
0x18002a24b  mov     dword ptr [rbp+Data], r12d
0x18002a24f  mov     [rbp+cbData], 4
0x18002a256  call    cs:__imp_RegQueryValueExW
0x18002a25c  mov     ebx, eax
0x18002a25e  test    eax, eax
0x18002a260  jz      short loc_18002A2D6
0x18002a262  cmp     eax, 2
0x18002a265  jnz     loc_18002A146
0x18002a26b  mov     ebx, r12d
0x18002a26e  jmp     loc_18002A146
0x18002a273  mov     cs:qword_1800A34F0, r12
0x18002a27a  mov     ebx, 8
0x18002a27f  jmp     loc_18002A146
0x18002a284  mov     ebx, 4B4h
0x18002a289  jmp     loc_18002A146
0x18002a28e  mov     ebx, r12d
0x18002a291  test    rcx, rcx
0x18002a294  jz      loc_18002A141
0x18002a29a  mov     r13d, 2Ch ; ','
0x18002a2a0  mov     edx, r13d; Ch
0x18002a2a3  inc     ebx
0x18002a2a5  call    cs:__imp_wcschr
0x18002a2ab  test    rax, rax
0x18002a2ae  lea     rcx, [rax+2]
0x18002a2b2  cmovz   rcx, rax
0x18002a2b6  test    rcx, rcx
0x18002a2b9  jnz     short loc_18002A2A0
0x18002a2bb  jmp     loc_18002A182
0x18002a2c0  mov     [rax], r12w
0x18002a2c4  jmp     loc_18002A1E3
0x18002a2c9  mov     [rdi], r13w
0x18002a2cd  add     rdi, 2
0x18002a2d1  jmp     loc_18002A20A
0x18002a2d6  cmp     dword ptr [rbp+Data], 1
0x18002a2da  jnz     loc_18002A146
0x18002a2e0  or      dword ptr cs:qword_1800A34E8, 1
0x18002a2e7  jmp     loc_18002A146
```
