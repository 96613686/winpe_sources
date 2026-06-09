# CActiveXInstallSecurityManager::GetSecurityId(uchar *,ulong *,ulong)

- ea: `0x408d90`
- end: `0x408dd3`
- name: `?GetSecurityId@CActiveXInstallSecurityManager@@UAGJPAEPAKK@Z`
- size: `67`
- prototype: `int __stdcall(CActiveXInstallSecurityManager *__hidden this, unsigned __int8 *, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x408d90`

## import_xrefs

- `urlmon!__imp__GetZoneAgnosticSecurityIdFromUrl@20` at `0x408dc4`
- `urlmon!__imp__GetZoneAgnosticSecurityIdFromUrl@20` at `0x408dc4`

## pseudocode

```c
int __stdcall CActiveXInstallSecurityManager::GetSecurityId(
        CActiveXInstallSecurityManager *this,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned int a4)
{
  int v4; // ecx
  int v5; // edx
  int v6; // esi

  v4 = -2147467259;
  v5 = *((_DWORD *)this + 2);
  if ( v5 )
  {
    v6 = *((_DWORD *)this + 3);
    if ( v6 )
    {
      if ( a3 && *a3 >= 0x200 )
        return GetZoneAgnosticSecurityIdFromUrl(v6, v5, a2, a3, a4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x408d90  mov     edi, edi
0x408d92  push    ebp
0x408d93  mov     ebp, esp
0x408d95  mov     eax, [ebp+this]
0x408d98  mov     ecx, 80004005h
0x408d9d  mov     edx, [eax+8]
0x408da0  test    edx, edx
0x408da2  jz      short loc_408DCD
0x408da4  push    esi
0x408da5  mov     esi, [eax+0Ch]
0x408da8  test    esi, esi
0x408daa  jz      short loc_408DCC
0x408dac  mov     eax, [ebp+arg_8]
0x408daf  test    eax, eax
0x408db1  jz      short loc_408DCC
0x408db3  cmp     dword ptr [eax], 200h
0x408db9  jb      short loc_408DCC
0x408dbb  push    [ebp+arg_C]
0x408dbe  push    eax
0x408dbf  push    [ebp+arg_4]
0x408dc2  push    edx
0x408dc3  push    esi
0x408dc4  call    ds:__imp__GetZoneAgnosticSecurityIdFromUrl@20; GetZoneAgnosticSecurityIdFromUrl(x,x,x,x,x)
0x408dca  mov     ecx, eax
0x408dcc  pop     esi
0x408dcd  mov     eax, ecx
0x408dcf  pop     ebp
0x408dd0  retn    10h
```
