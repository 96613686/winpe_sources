# RegSetDword

- ea: `0x140028d5c`
- end: `0x140028e62`
- name: `RegSetDword`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14005aa68`

## callees

- `0x140028d5c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140028df3`
- `ADVAPI32!RegSetValueExW` at `0x140028e33`
- `ADVAPI32!RegSetValueExW` at `0x140028df3`
- `ADVAPI32!RegSetValueExW` at `0x140028e33`
- `ADVAPI32!RegCreateKeyExW` at `0x140028dbc`
- `ADVAPI32!RegCreateKeyExW` at `0x140028dbc`
- `ADVAPI32!RegCloseKey` at `0x140028e09`
- `ADVAPI32!RegCloseKey` at `0x140028e09`
- `KERNEL32!SetLastError` at `0x140028e43`
- `KERNEL32!SetLastError` at `0x140028e43`

## pseudocode

```c
__int64 __fastcall RegSetDword(__int64 a1, const WCHAR *a2, HKEY a3, DWORD a4)
{
  unsigned int v4; // ebx
  LSTATUS v5; // edi
  BYTE Data[24]; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF
  DWORD v9; // [rsp+88h] [rbp+20h] BYREF

  v9 = a4;
  hKey = a3;
  v4 = 0;
  *(_DWORD *)Data = 1;
  if ( a2 )
  {
    hKey = 0;
    v9 = 0;
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &v9);
    if ( !v5 )
    {
      v5 = RegSetValueExW(hKey, L"ErrorControl", 0, 4u, Data, 4u);
      RegCloseKey(hKey);
    }
  }
  else
  {
    v5 = RegSetValueExW(HKEY_LOCAL_MACHINE, L"ErrorControl", 0, 4u, Data, 4u);
  }
  SetLastError(v5);
  LOBYTE(v4) = v5 == 0;
  return v4;
}

```

## disassembly

```asm
0x140028d5c  mov     r11, rsp
0x140028d5f  mov     [r11+8], rbx
0x140028d63  mov     [r11+20h], r9d
0x140028d67  mov     [r11+18h], r8
0x140028d6b  push    rdi
0x140028d6c  sub     rsp, 60h
0x140028d70  xor     ebx, ebx
0x140028d72  mov     dword ptr [rsp+68h+Data], 1
0x140028d7a  xor     r8d, r8d; Reserved
0x140028d7d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140028d84  test    rdx, rdx
0x140028d87  jz      loc_140028E17
0x140028d8d  lea     rax, [r11+20h]
0x140028d91  mov     [r11+18h], rbx
0x140028d95  mov     [r11-28h], rax
0x140028d99  lea     r9, Class; lpClass
0x140028da0  lea     rax, [r11+18h]
0x140028da4  mov     [r11+20h], ebx
0x140028da8  mov     [r11-30h], rax
0x140028dac  mov     [r11-38h], rbx
0x140028db0  mov     [rsp+68h+samDesired], 20006h; samDesired
0x140028db8  mov     [rsp+68h+dwOptions], ebx; dwOptions
0x140028dbc  call    cs:__imp_RegCreateKeyExW
0x140028dc3  nop     dword ptr [rax+rax+00h]
0x140028dc8  mov     edi, eax
0x140028dca  test    eax, eax
0x140028dcc  jnz     short loc_140028E41
0x140028dce  mov     rcx, [rsp+68h+hKey]; hKey
0x140028dd6  lea     r9d, [rbx+4]; dwType
0x140028dda  lea     rax, [rsp+68h+Data]
0x140028ddf  mov     [rsp+68h+samDesired], r9d; cbData
0x140028de4  xor     r8d, r8d; Reserved
0x140028de7  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140028dec  lea     rdx, aErrorcontrol; "ErrorControl"
0x140028df3  call    cs:__imp_RegSetValueExW
0x140028dfa  nop     dword ptr [rax+rax+00h]
0x140028dff  mov     rcx, [rsp+68h+hKey]; hKey
0x140028e07  mov     edi, eax
0x140028e09  call    cs:__imp_RegCloseKey
0x140028e10  nop     dword ptr [rax+rax+00h]
0x140028e15  jmp     short loc_140028E41
0x140028e17  mov     r9d, 4; dwType
0x140028e1d  lea     rax, [rsp+68h+Data]
0x140028e22  mov     [rsp+68h+samDesired], r9d; cbData
0x140028e27  lea     rdx, aErrorcontrol; "ErrorControl"
0x140028e2e  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140028e33  call    cs:__imp_RegSetValueExW
0x140028e3a  nop     dword ptr [rax+rax+00h]
0x140028e3f  mov     edi, eax
0x140028e41  mov     ecx, edi; dwErrCode
0x140028e43  call    cs:__imp_SetLastError
0x140028e4a  nop     dword ptr [rax+rax+00h]
0x140028e4f  test    edi, edi
0x140028e51  setz    bl
0x140028e54  mov     eax, ebx
0x140028e56  mov     rbx, [rsp+68h+arg_0]
0x140028e5b  add     rsp, 60h
0x140028e5f  pop     rdi
0x140028e60  retn
```
