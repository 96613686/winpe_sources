# CActiveXInstallSecurityManager::ProcessUrlAction(ulong,uchar *,ulong,uchar *,ulong,ulong,ulong)

- ea: `0x408de0`
- end: `0x408e2d`
- name: `?ProcessUrlAction@CActiveXInstallSecurityManager@@UAGJKPAEK0KKK@Z`
- size: `77`
- prototype: `int __stdcall(CActiveXInstallSecurityManager *__hidden this, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x408de0`
- `0x40d1d0`

## pseudocode

```c
int __stdcall CActiveXInstallSecurityManager::ProcessUrlAction(
        CActiveXInstallSecurityManager *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  int v8; // edx
  int v9; // edi
  int v10; // ecx

  v8 = -2147467259;
  v9 = *((_DWORD *)this + 2);
  if ( v9 )
  {
    v10 = *((_DWORD *)this + 3);
    if ( v10 )
      return (*(int (__thiscall **)(_DWORD, int, int, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int))(*(_DWORD *)v10 + 28))(
               *(_DWORD *)(*(_DWORD *)v10 + 28),
               v10,
               v9,
               a2,
               a3,
               a4,
               a5,
               a6,
               a7,
               a8);
  }
  return v8;
}

```

## disassembly

```asm
0x408de0  mov     edi, edi
0x408de2  push    ebp
0x408de3  mov     ebp, esp
0x408de5  mov     eax, [ebp+this]
0x408de8  mov     edx, 80004005h
0x408ded  push    edi
0x408dee  mov     edi, [eax+8]
0x408df1  test    edi, edi
0x408df3  jz      short loc_408E26
0x408df5  mov     ecx, [eax+0Ch]
0x408df8  test    ecx, ecx
0x408dfa  jz      short loc_408E26
0x408dfc  mov     eax, [ecx]
0x408dfe  push    esi
0x408dff  push    [ebp+arg_1C]
0x408e02  push    [ebp+arg_18]
0x408e05  mov     esi, [eax+1Ch]
0x408e08  push    [ebp+arg_14]
0x408e0b  push    [ebp+arg_10]
0x408e0e  push    [ebp+arg_C]
0x408e11  push    [ebp+arg_8]
0x408e14  push    [ebp+arg_4]
0x408e17  push    edi
0x408e18  push    ecx
0x408e19  mov     ecx, esi
0x408e1b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x408e21  call    esi
0x408e23  mov     edx, eax
0x408e25  pop     esi
0x408e26  mov     eax, edx
0x408e28  pop     edi
0x408e29  pop     ebp
0x408e2a  retn    20h ; ' '
```
