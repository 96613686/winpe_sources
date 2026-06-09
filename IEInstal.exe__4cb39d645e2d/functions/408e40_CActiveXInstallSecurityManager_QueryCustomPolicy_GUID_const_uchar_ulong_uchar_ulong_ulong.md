# CActiveXInstallSecurityManager::QueryCustomPolicy(_GUID const &,uchar * *,ulong *,uchar *,ulong,ulong)

- ea: `0x408e40`
- end: `0x408e8a`
- name: `?QueryCustomPolicy@CActiveXInstallSecurityManager@@UAGJABU_GUID@@PAPAEPAKPAEKK@Z`
- size: `74`
- prototype: `int __stdcall(CActiveXInstallSecurityManager *__hidden this, const struct _GUID *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x408e40`
- `0x40d1d0`

## pseudocode

```c
int __stdcall CActiveXInstallSecurityManager::QueryCustomPolicy(
        CActiveXInstallSecurityManager *this,
        const struct _GUID *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7)
{
  int v7; // edx
  int v8; // edi
  int v9; // ecx

  v7 = -2147467259;
  v8 = *((_DWORD *)this + 2);
  if ( v8 )
  {
    v9 = *((_DWORD *)this + 3);
    if ( v9 )
      return (*(int (__thiscall **)(_DWORD, int, int, const struct _GUID *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned int))(*(_DWORD *)v9 + 32))(
               *(_DWORD *)(*(_DWORD *)v9 + 32),
               v9,
               v8,
               a2,
               a3,
               a4,
               a5,
               a6,
               a7);
  }
  return v7;
}

```

## disassembly

```asm
0x408e40  mov     edi, edi
0x408e42  push    ebp
0x408e43  mov     ebp, esp
0x408e45  mov     eax, [ebp+this]
0x408e48  mov     edx, 80004005h
0x408e4d  push    edi
0x408e4e  mov     edi, [eax+8]
0x408e51  test    edi, edi
0x408e53  jz      short loc_408E83
0x408e55  mov     ecx, [eax+0Ch]
0x408e58  test    ecx, ecx
0x408e5a  jz      short loc_408E83
0x408e5c  mov     eax, [ecx]
0x408e5e  push    esi
0x408e5f  push    [ebp+arg_18]
0x408e62  push    [ebp+arg_14]
0x408e65  mov     esi, [eax+20h]
0x408e68  push    [ebp+arg_10]
0x408e6b  push    [ebp+arg_C]
0x408e6e  push    [ebp+arg_8]
0x408e71  push    [ebp+arg_4]
0x408e74  push    edi
0x408e75  push    ecx
0x408e76  mov     ecx, esi
0x408e78  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x408e7e  call    esi
0x408e80  mov     edx, eax
0x408e82  pop     esi
0x408e83  mov     eax, edx
0x408e85  pop     edi
0x408e86  pop     ebp
0x408e87  retn    1Ch
```
