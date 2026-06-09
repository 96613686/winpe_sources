# WinMain(x,x,x,x)

- ea: `0x40aca2`
- end: `0x40ad8d`
- name: `_WinMain@16`
- size: `235`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40b702`

## callees

- `0x407eb0`
- `0x4092c3`
- `0x40935c`
- `0x4097aa`
- `0x409865`
- `0x4098ae`
- `0x409ef3`
- `0x40a034`
- `0x40ac17`
- `0x40aca2`
- `0x40b3e3`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x40accd`
- `KERNEL32!GetProcAddress` at `0x40accd`
- `KERNEL32!GetCommandLineW` at `0x40ace8`
- `KERNEL32!GetCommandLineW` at `0x40ace8`
- `KERNEL32!GetModuleHandleW` at `0x40acc6`
- `KERNEL32!GetModuleHandleW` at `0x40acc6`

## string_xrefs

- `0x40acbc`: `SetDefaultDllDirectories`
- `0x40acc1`: `kernel32.dll`

## pseudocode

```c
int __stdcall WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
  HMODULE ModuleHandleW; // eax
  BOOL (__stdcall *SetDefaultDllDirectories)(DWORD); // eax
  LPWSTR CommandLineW; // eax
  signed int v7; // esi
  _DWORD *v8; // eax
  _DWORD Src[6]; // [esp+10h] [ebp-38h] BYREF
  HMODULE v11[7]; // [esp+28h] [ebp-20h] BYREF

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  SetDefaultDllDirectories = (BOOL (__stdcall *)(DWORD))GetProcAddress(ModuleHandleW, "SetDefaultDllDirectories");
  if ( SetDefaultDllDirectories )
    ((void (__thiscall *)(BOOL (__stdcall *)(DWORD), int))SetDefaultDllDirectories)(SetDefaultDllDirectories, 2048);
  CommandLineW = GetCommandLineW();
  sub_409EF3(Src, CommandLineW);
  memset(v11, 0, sizeof(v11));
  sub_4092C3(hInstance);
  v7 = sub_4097AA(v11);
  if ( v7 >= 0 )
  {
    v8 = Src;
    if ( Src[5] >= 8u )
      v8 = (_DWORD *)Src[0];
    v7 = sub_409865(v8, nShowCmd);
  }
  else if ( (unsigned __int8)sub_40AC17(Src) )
  {
    if ( v7 == -2147218688 )
    {
      v7 = sub_4098AE(v11);
      if ( v7 >= 0 )
        v7 = -2147218686;
    }
  }
  sub_40935C(v11);
  sub_40A034(Src);
  return v7;
}

```

## disassembly

```asm
0x40aca2  push    ebp
0x40aca3  mov     ebp, esp
0x40aca5  and     esp, 0FFFFFFF8h
0x40aca8  sub     esp, 3Ch
0x40acab  mov     eax, ___security_cookie
0x40acb0  xor     eax, esp
0x40acb2  mov     [esp+3Ch+var_4], eax
0x40acb6  push    ebx
0x40acb7  mov     ebx, [ebp+hInstance]
0x40acba  push    esi
0x40acbb  push    edi
0x40acbc  push    offset aSetdefaultdlld; "SetDefaultDllDirectories"
0x40acc1  push    offset ModuleName; "kernel32.dll"
0x40acc6  call    ds:GetModuleHandleW
0x40accc  push    eax; hModule
0x40accd  call    ds:GetProcAddress
0x40acd3  mov     esi, eax
0x40acd5  test    esi, esi
0x40acd7  jz      short loc_40ACE8
0x40acd9  push    800h
0x40acde  mov     ecx, esi
0x40ace0  call    ds:___guard_check_icall_fptr
0x40ace6  call    esi
0x40ace8  call    ds:GetCommandLineW
0x40acee  push    eax; Src
0x40acef  lea     ecx, [esp+4Ch+Src]; void *
0x40acf3  call    sub_409EF3
0x40acf8  push    7
0x40acfa  pop     ecx
0x40acfb  xor     eax, eax
0x40acfd  lea     edi, [esp+48h+var_20]
0x40ad01  rep stosd
0x40ad03  push    ebx; hModule
0x40ad04  lea     ecx, [esp+4Ch+var_20]
0x40ad08  call    sub_4092C3
0x40ad0d  lea     ecx, [esp+48h+var_20]
0x40ad11  call    sub_4097AA
0x40ad16  mov     esi, eax
0x40ad18  test    esi, esi
0x40ad1a  jns     short loc_40AD47
0x40ad1c  lea     ecx, [esp+48h+Src]; Src
0x40ad20  call    sub_40AC17
0x40ad25  test    al, al
0x40ad27  jz      short loc_40AD65
0x40ad29  cmp     esi, 80040B00h
0x40ad2f  jnz     short loc_40AD65
0x40ad31  lea     ecx, [esp+48h+var_20]
0x40ad35  call    sub_4098AE
0x40ad3a  mov     esi, eax
0x40ad3c  test    esi, esi
0x40ad3e  js      short loc_40AD65
0x40ad40  mov     esi, 80040B02h
0x40ad45  jmp     short loc_40AD65
0x40ad47  cmp     dword ptr [esp+48h+var_24], 8
0x40ad4c  lea     eax, [esp+48h+Src]
0x40ad50  jb      short loc_40AD56
0x40ad52  mov     eax, [esp+48h+Src]
0x40ad56  push    [ebp+nShowCmd]
0x40ad59  lea     ecx, [esp+4Ch+var_20]
0x40ad5d  push    eax
0x40ad5e  call    sub_409865
0x40ad63  mov     esi, eax
0x40ad65  lea     ecx, [esp+48h+var_20]
0x40ad69  call    sub_40935C
0x40ad6e  lea     ecx, [esp+48h+Src]
0x40ad72  call    sub_40A034
0x40ad77  mov     ecx, [esp+48h+var_4]
0x40ad7b  mov     eax, esi
0x40ad7d  pop     edi
0x40ad7e  pop     esi
0x40ad7f  pop     ebx
0x40ad80  xor     ecx, esp; StackCookie
0x40ad82  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40ad87  mov     esp, ebp
0x40ad89  pop     ebp
0x40ad8a  retn    10h
```
