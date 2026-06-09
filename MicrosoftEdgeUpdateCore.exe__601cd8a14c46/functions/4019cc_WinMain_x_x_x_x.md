# WinMain(x,x,x,x)

- ea: `0x4019cc`
- end: `0x401a91`
- name: `_WinMain@16`
- size: `197`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x40d5c2`

## callees

- `0x4015d2`
- `0x4018e5`
- `0x4019cc`
- `0x401a91`
- `0x401cac`
- `0x402330`
- `0x404733`
- `0x404ad0`
- `0x40629e`
- `0x40d08d`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x4019eb`
- `KERNEL32!GetModuleHandleW` at `0x4019eb`
- `KERNEL32!GetProcAddress` at `0x4019f2`
- `KERNEL32!GetProcAddress` at `0x4019f2`
- `ole32!CoInitializeEx` at `0x401a11`
- `ole32!CoInitializeEx` at `0x401a11`

## string_xrefs

- `0x4019e6`: `kernel32.dll`
- `0x4019e1`: `SetDefaultDllDirectories`

## pseudocode

```c
int __stdcall WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
  HMODULE ModuleHandleW; // eax
  BOOL (__stdcall *SetDefaultDllDirectories)(DWORD); // eax
  HRESULT v6; // esi
  int v7; // ecx
  int v8; // eax
  _DWORD v10[2]; // [esp+8h] [ebp-10h] BYREF
  HRESULT v11; // [esp+10h] [ebp-8h] BYREF

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  SetDefaultDllDirectories = (BOOL (__stdcall *)(DWORD))GetProcAddress(ModuleHandleW, "SetDefaultDllDirectories");
  if ( SetDefaultDllDirectories )
    ((void (__thiscall *)(BOOL (__stdcall *)(DWORD), int))SetDefaultDllDirectories)(SetDefaultDllDirectories, 2048);
  v6 = CoInitializeEx(0, 4u);
  v11 = v6;
  if ( v6 >= 0 )
  {
    HIBYTE(v10[0]) = 0;
    qword_43EEB0 = sub_40629E();
    v8 = sub_404733(v7, v7);
    sub_401CAC(v8);
    sub_4015D2(v10[1] - 16);
    v6 = sub_404AD0((char *)v10 + 3);
    if ( v6 >= 0 )
      v6 = sub_4018E5(SHIBYTE(v10[0]));
  }
  sub_401A91(&v11);
  return v6;
}

```

## disassembly

```asm
0x4019cc  push    ebp
0x4019cd  mov     ebp, esp
0x4019cf  and     esp, 0FFFFFFF8h
0x4019d2  sub     esp, 14h
0x4019d5  mov     eax, ___security_cookie
0x4019da  xor     eax, esp
0x4019dc  mov     [esp+14h+var_4], eax
0x4019e0  push    esi
0x4019e1  push    offset aSetdefaultdlld; "SetDefaultDllDirectories"
0x4019e6  push    offset aKernel32Dll_0; "kernel32.dll"
0x4019eb  call    ds:GetModuleHandleW
0x4019f1  push    eax; hModule
0x4019f2  call    ds:GetProcAddress
0x4019f8  mov     esi, eax
0x4019fa  test    esi, esi
0x4019fc  jz      short loc_401A0D
0x4019fe  push    800h
0x401a03  mov     ecx, esi
0x401a05  call    ds:___guard_check_icall_fptr
0x401a0b  call    esi
0x401a0d  push    4; dwCoInit
0x401a0f  push    0; pvReserved
0x401a11  call    ds:CoInitializeEx
0x401a17  mov     esi, eax
0x401a19  mov     [esp+18h+var_8], esi
0x401a1d  test    esi, esi
0x401a1f  js      short loc_401A74
0x401a21  mov     byte ptr [esp+18h+var_10+3], 0
0x401a26  call    sub_40629E
0x401a2b  push    ecx
0x401a2c  push    ecx
0x401a2d  lea     ecx, [esp+20h+var_C]
0x401a31  mov     dword ptr qword_43EEB0, eax
0x401a36  mov     dword ptr qword_43EEB0+4, edx
0x401a3c  call    sub_404733
0x401a41  pop     ecx
0x401a42  pop     ecx
0x401a43  push    eax
0x401a44  mov     ecx, offset dword_43ED7C
0x401a49  call    sub_401CAC
0x401a4e  mov     ecx, [esp+18h+var_C]
0x401a52  lea     ecx, [ecx-10h]
0x401a55  call    sub_4015D2
0x401a5a  lea     ecx, [esp+18h+var_10+3]
0x401a5e  call    sub_404AD0
0x401a63  mov     esi, eax
0x401a65  test    esi, esi
0x401a67  js      short loc_401A74
0x401a69  mov     cl, byte ptr [esp+18h+var_10+3]
0x401a6d  call    sub_4018E5
0x401a72  mov     esi, eax
0x401a74  lea     ecx, [esp+18h+var_8]
0x401a78  call    sub_401A91
0x401a7d  mov     ecx, [esp+18h+var_4]
0x401a81  mov     eax, esi
0x401a83  pop     esi
0x401a84  xor     ecx, esp; StackCookie
0x401a86  call    @__security_check_cookie@4; __security_check_cookie(x)
0x401a8b  mov     esp, ebp
0x401a8d  pop     ebp
0x401a8e  retn    10h
```
