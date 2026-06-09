# CDfsShell::AddPages(int (*)(_PSP *,__int64),__int64)

- ea: `0x180007be0`
- end: `0x180007d85`
- name: `?AddPages@CDfsShell@@UEAAJP6AHPEAU_PSP@@_J@Z1@Z`
- size: `421`
- prototype: `__int64 __fastcall(CDfsShell *__hidden this, int (*)(struct _PSP *, __int64), __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004328`
- `0x180007be0`
- `0x180008120`
- `0x180009b54`
- `0x18000c010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180007c23`
- `ADVAPI32!RegOpenKeyExW` at `0x180007c23`
- `ADVAPI32!RegQueryValueExW` at `0x180007c51`
- `ADVAPI32!RegQueryValueExW` at `0x180007c51`
- `ADVAPI32!RegCloseKey` at `0x180007c5e`
- `ADVAPI32!RegCloseKey` at `0x180007c5e`
- `OLEAUT32!__imp_SysAllocString` at `0x180007d28`
- `OLEAUT32!__imp_SysAllocString` at `0x180007d3d`
- `OLEAUT32!__imp_SysAllocString` at `0x180007d28`
- `OLEAUT32!__imp_SysAllocString` at `0x180007d3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d16`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d20`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d16`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d20`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDfsShell::AddPages(
        unsigned __int64 this,
        unsigned int (__fastcall *a2)(__int64, __int64),
        __int64 a3)
{
  LSTATUS Value; // ebx
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned __int64 v10; // rbx
  __int64 v11; // rcx
  const OLECHAR *v12; // rcx
  unsigned __int16 *v13; // rdi
  const OLECHAR *v14; // rcx
  unsigned __int16 *v15; // rbx
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\explorer",
         0,
         1u,
         &hKey)
    || (Value = RegQueryValueExW(hKey, L"NoDFSTab", 0, 0, 0, 0), RegCloseKey(hKey), Value) )
  {
    v7 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)(this + 32) + 32LL))(this + 32);
    v8 = v7;
    if ( !v7 )
      return 2147942414LL;
    if ( a2(v7, a3) )
    {
      v10 = this & -(__int64)(this != 8);
      if ( v10 )
      {
        v11 = *(_QWORD *)(this + 240);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        *(_QWORD *)(this + 240) = v10;
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v10 + 8LL))(this & -(__int64)(this != 8));
      }
      v12 = *(const OLECHAR **)(this + 16);
      if ( v12 )
      {
        v13 = SysAllocString(v12);
        if ( !v13 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        v13 = 0;
      }
      v14 = *(const OLECHAR **)(this + 24);
      if ( v14 )
      {
        v15 = SysAllocString(v14);
        if ( !v15 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        v15 = 0;
      }
      CDfsShellExtProp::put_DirPaths((CDfsShellExtProp *)(this + 32), v13, v15);
      SysFreeString(v15);
      SysFreeString(v13);
    }
    else
    {
      IsolationAwareDestroyPropertySheetPage(v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007be0  mov     r11, rsp
0x180007be3  mov     [r11+8], rbx
0x180007be7  mov     [r11+10h], rbp
0x180007beb  push    rsi
0x180007bec  push    rdi
0x180007bed  push    r14
0x180007bef  sub     rsp, 40h
0x180007bf3  mov     rdi, r8
0x180007bf6  mov     rbp, rdx
0x180007bf9  mov     rsi, rcx
0x180007bfc  mov     qword ptr [r11+20h], 0
0x180007c04  lea     rax, [r11+20h]
0x180007c08  mov     [r11-38h], rax
0x180007c0c  mov     r9d, 1; samDesired
0x180007c12  xor     r8d, r8d; ulOptions
0x180007c15  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007c1c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180007c23  call    cs:__imp_RegOpenKeyExW
0x180007c29  test    eax, eax
0x180007c2b  jnz     short loc_180007C6C
0x180007c2d  mov     [rsp+58h+lpcbData], 0; lpcbData
0x180007c36  mov     [rsp+58h+lpData], 0; lpData
0x180007c3f  xor     r9d, r9d; lpType
0x180007c42  xor     r8d, r8d; lpReserved
0x180007c45  lea     rdx, aNodfstab; "NoDFSTab"
0x180007c4c  mov     rcx, [rsp+58h+hKey]; hKey
0x180007c51  call    cs:__imp_RegQueryValueExW
0x180007c57  mov     ebx, eax
0x180007c59  mov     rcx, [rsp+58h+hKey]; hKey
0x180007c5e  call    cs:__imp_RegCloseKey
0x180007c64  test    ebx, ebx
0x180007c66  jz      loc_180007D5A
0x180007c6c  lea     r14, [rsi+20h]
0x180007c70  mov     rax, [r14]
0x180007c73  mov     rcx, r14
0x180007c76  mov     rax, [rax+20h]
0x180007c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c7f  mov     rbx, rax
0x180007c82  test    rax, rax
0x180007c85  jnz     short loc_180007C91
0x180007c87  mov     eax, 8007000Eh
0x180007c8c  jmp     loc_180007D5C
0x180007c91  mov     rdx, rdi
0x180007c94  mov     rcx, rbx
0x180007c97  mov     rax, rbp
0x180007c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c9f  test    eax, eax
0x180007ca1  jz      loc_180007D52
0x180007ca7  lea     rax, [rsi-8]
0x180007cab  neg     rax
0x180007cae  sbb     rbx, rbx
0x180007cb1  and     rbx, rsi
0x180007cb4  jz      short loc_180007CE4
0x180007cb6  mov     rcx, [rsi+0F0h]
0x180007cbd  test    rcx, rcx
0x180007cc0  jz      short loc_180007CCE
0x180007cc2  mov     rax, [rcx]
0x180007cc5  mov     rax, [rax+10h]
0x180007cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cce  mov     [rsi+0F0h], rbx
0x180007cd5  mov     rax, [rbx]
0x180007cd8  mov     rcx, rbx
0x180007cdb  mov     rax, [rax+8]
0x180007cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce4  mov     rcx, [rsi+10h]; psz
0x180007ce8  test    rcx, rcx
0x180007ceb  jnz     short loc_180007D28
0x180007ced  xor     edi, edi
0x180007cef  mov     [rsp+58h+var_28], rdi
0x180007cf4  mov     rcx, [rsi+18h]; psz
0x180007cf8  test    rcx, rcx
0x180007cfb  jnz     short loc_180007D3D
0x180007cfd  xor     ebx, ebx
0x180007cff  mov     [rsp+58h+var_20], rbx
0x180007d04  mov     r8, rbx; unsigned __int16 *
0x180007d07  mov     rdx, rdi; unsigned __int16 *
0x180007d0a  mov     rcx, r14; this
0x180007d0d  call    ?put_DirPaths@CDfsShellExtProp@@QEAAJPEAG0@Z; CDfsShellExtProp::put_DirPaths(ushort *,ushort *)
0x180007d12  nop
0x180007d13  mov     rcx, rbx; bstrString
0x180007d16  call    cs:__imp_SysFreeString
0x180007d1c  nop
0x180007d1d  mov     rcx, rdi; bstrString
0x180007d20  call    cs:__imp_SysFreeString
0x180007d26  jmp     short loc_180007D5A
0x180007d28  call    cs:__imp_SysAllocString
0x180007d2e  mov     rdi, rax
0x180007d31  mov     [rsp+58h+var_28], rax
0x180007d36  test    rax, rax
0x180007d39  jz      short loc_180007D6F
0x180007d3b  jmp     short loc_180007CF4
0x180007d3d  call    cs:__imp_SysAllocString
0x180007d43  mov     rbx, rax
0x180007d46  mov     [rsp+58h+var_20], rax
0x180007d4b  test    rax, rax
0x180007d4e  jz      short loc_180007D7A
0x180007d50  jmp     short loc_180007D04
0x180007d52  mov     rcx, rbx
0x180007d55  call    IsolationAwareDestroyPropertySheetPage
0x180007d5a  xor     eax, eax
0x180007d5c  mov     rbx, [rsp+58h+arg_0]
0x180007d61  mov     rbp, [rsp+58h+arg_8]
0x180007d66  add     rsp, 40h
0x180007d6a  pop     r14
0x180007d6c  pop     rdi
0x180007d6d  pop     rsi
0x180007d6e  retn
0x180007d6f  mov     ecx, 8007000Eh; int
0x180007d74  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007d7a  mov     ecx, 8007000Eh; int
0x180007d7f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
