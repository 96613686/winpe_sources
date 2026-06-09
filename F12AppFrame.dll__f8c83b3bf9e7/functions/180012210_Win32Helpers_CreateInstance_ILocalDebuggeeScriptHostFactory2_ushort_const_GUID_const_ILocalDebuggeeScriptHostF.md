# Win32Helpers::CreateInstance<ILocalDebuggeeScriptHostFactory2>(ushort const *,_GUID const &,ILocalDebuggeeScriptHostFactory2 * *)

- ea: `0x180012210`
- end: `0x180012373`
- name: `??$CreateInstance@UILocalDebuggeeScriptHostFactory2@@@Win32Helpers@@YAJPEBGAEBU_GUID@@PEAPEAUILocalDebuggeeScriptHostFactory2@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016710`

## callees

- `0x180005e44`
- `0x180012210`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001226d`
- `KERNEL32!GetProcAddress` at `0x18001226d`
- `KERNEL32!LoadLibraryExW` at `0x18001224c`
- `KERNEL32!LoadLibraryExW` at `0x18001224c`

## string_xrefs

- `0x180012245`: `F12\DiagnosticsTap.dll`
- `0x180012263`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall Win32Helpers::CreateInstance<ILocalDebuggeeScriptHostFactory2>(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v4; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v7; // rax
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = a2;
  v9 = a1;
  if ( a3 )
  {
    *a3 = 0;
    Library = LoadLibraryExW(L"F12\\DiagnosticsTap.dll", 0, 0x800u);
    if ( Library && (ProcAddress = GetProcAddress(Library, "DllGetClassObject")) != 0 )
    {
      v10 = 0;
      v4 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
             &GUID_ca7c1262_ea3b_4508_b120_df9bcdef3e60,
             &IID_IClassFactory,
             &v10);
      if ( v4 )
      {
        if ( v4 >= 0 )
          v4 = -2147467259;
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      else if ( v10 )
      {
        v9 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v10 + 24LL))(
               v10,
               0,
               &GUID_7075051c_8d62_4342_af05_7afd5f1c2c73,
               &v9);
        if ( v4 )
        {
          if ( v4 >= 0 )
            v4 = -2147467259;
          if ( v9 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
        else
        {
          v7 = v9;
          v9 = 0;
          *a3 = v7;
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          return 0;
        }
      }
      else
      {
        return (unsigned int)-2147467262;
      }
    }
    else
    {
      return (unsigned int)ATL::AtlHresultFromLastError();
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012210  mov     [rsp+arg_10], rbx
0x180012215  mov     [rsp+arg_8], rdx
0x18001221a  mov     [rsp+arg_0], rcx
0x18001221f  push    rdi
0x180012220  sub     rsp, 30h
0x180012224  mov     rdi, r8
0x180012227  test    r8, r8
0x18001222a  jnz     short loc_180012236
0x18001222c  mov     ebx, 80070057h
0x180012231  jmp     loc_180012366
0x180012236  mov     qword ptr [r8], 0
0x18001223d  xor     edx, edx; hFile
0x18001223f  mov     r8d, 800h; dwFlags
0x180012245  lea     rcx, aF12Diagnostics; "F12\\DiagnosticsTap.dll"
0x18001224c  call    cs:__imp_LoadLibraryExW
0x180012252  test    rax, rax
0x180012255  jnz     short loc_180012263
0x180012257  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001225c  mov     ebx, eax
0x18001225e  jmp     loc_180012366
0x180012263  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18001226a  mov     rcx, rax; hModule
0x18001226d  call    cs:__imp_GetProcAddress
0x180012273  test    rax, rax
0x180012276  jz      short loc_180012257
0x180012278  mov     [rsp+38h+arg_8], 0
0x180012281  lea     r8, [rsp+38h+arg_8]
0x180012286  lea     rdx, IID_IClassFactory
0x18001228d  lea     rcx, _GUID_ca7c1262_ea3b_4508_b120_df9bcdef3e60
0x180012294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012299  mov     ebx, eax
0x18001229b  test    eax, eax
0x18001229d  jz      short loc_1800122C5
0x18001229f  mov     eax, 80004005h
0x1800122a4  test    ebx, ebx
0x1800122a6  cmovns  ebx, eax
0x1800122a9  mov     rcx, [rsp+38h+arg_8]
0x1800122ae  test    rcx, rcx
0x1800122b1  jz      short loc_1800122C0
0x1800122b3  mov     rax, [rcx]
0x1800122b6  mov     rax, [rax+10h]
0x1800122ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122bf  nop
0x1800122c0  jmp     loc_180012366
0x1800122c5  mov     rcx, [rsp+38h+arg_8]
0x1800122ca  test    rcx, rcx
0x1800122cd  jnz     short loc_1800122D9
0x1800122cf  mov     ebx, 80004002h
0x1800122d4  jmp     loc_180012366
0x1800122d9  mov     [rsp+38h+arg_0], 0
0x1800122e2  mov     rax, [rcx]
0x1800122e5  lea     r9, [rsp+38h+arg_0]
0x1800122ea  lea     r8, _GUID_7075051c_8d62_4342_af05_7afd5f1c2c73
0x1800122f1  xor     edx, edx
0x1800122f3  mov     rax, [rax+18h]
0x1800122f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122fc  mov     ebx, eax
0x1800122fe  test    eax, eax
0x180012300  jz      short loc_18001233C
0x180012302  mov     eax, 80004005h
0x180012307  test    ebx, ebx
0x180012309  cmovns  ebx, eax
0x18001230c  mov     rcx, [rsp+38h+arg_0]
0x180012311  test    rcx, rcx
0x180012314  jz      short loc_180012323
0x180012316  mov     rax, [rcx]
0x180012319  mov     rax, [rax+10h]
0x18001231d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012322  nop
0x180012323  mov     rcx, [rsp+38h+arg_8]
0x180012328  test    rcx, rcx
0x18001232b  jz      short loc_18001233A
0x18001232d  mov     rax, [rcx]
0x180012330  mov     rax, [rax+10h]
0x180012334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012339  nop
0x18001233a  jmp     short loc_180012366
0x18001233c  mov     rax, [rsp+38h+arg_0]
0x180012341  mov     [rsp+38h+arg_0], 0
0x18001234a  mov     [rdi], rax
0x18001234d  mov     rcx, [rsp+38h+arg_8]
0x180012352  test    rcx, rcx
0x180012355  jz      short loc_180012364
0x180012357  mov     rax, [rcx]
0x18001235a  mov     rax, [rax+10h]
0x18001235e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012363  nop
0x180012364  xor     ebx, ebx
0x180012366  mov     eax, ebx
0x180012368  mov     rbx, [rsp+38h+arg_10]
0x18001236d  add     rsp, 30h
0x180012371  pop     rdi
0x180012372  retn
```
