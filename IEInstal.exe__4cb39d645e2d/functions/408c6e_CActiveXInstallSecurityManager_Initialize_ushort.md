# CActiveXInstallSecurityManager::Initialize(ushort *)

- ea: `0x408c6e`
- end: `0x408ccd`
- name: `?Initialize@CActiveXInstallSecurityManager@@QAEJPAG@Z`
- size: `95`
- prototype: `HRESULT __thiscall(CActiveXInstallSecurityManager *this, unsigned __int16 *psz)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x40373b`

## callees

- `0x408c6e`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x408c86`
- `OLEAUT32!__imp__SysAllocString@4` at `0x408c86`
- `OLEAUT32!__imp__SysFreeString@4` at `0x408cb0`
- `OLEAUT32!__imp__SysFreeString@4` at `0x408cb0`
- `urlmon!CoInternetCreateSecurityManager` at `0x408c98`
- `urlmon!CoInternetCreateSecurityManager` at `0x408c98`

## pseudocode

```c
HRESULT __thiscall CActiveXInstallSecurityManager::Initialize(
        CActiveXInstallSecurityManager *this,
        unsigned __int16 *psz)
{
  OLECHAR *v3; // edi
  HRESULT v4; // esi
  IInternetSecurityManager *ppSM; // [esp+Ch] [ebp-4h] BYREF

  ppSM = 0;
  if ( !psz )
    return -2147024809;
  v3 = SysAllocString(psz);
  if ( !v3 )
    return -2147024882;
  v4 = CoInternetCreateSecurityManager(0, &ppSM, 0);
  if ( v4 < 0 )
  {
    SysFreeString(v3);
  }
  else
  {
    *((_DWORD *)this + 3) = ppSM;
    *((_DWORD *)this + 2) = v3;
  }
  return v4;
}

```

## disassembly

```asm
0x408c6e  mov     edi, edi
0x408c70  push    ebp
0x408c71  mov     ebp, esp
0x408c73  push    ecx
0x408c74  push    ebx
0x408c75  push    esi
0x408c76  xor     esi, esi
0x408c78  mov     ebx, ecx
0x408c7a  push    edi
0x408c7b  mov     [ebp+ppSM], esi
0x408c7e  cmp     [ebp+psz], esi
0x408c81  jz      short loc_408CBF
0x408c83  push    [ebp+psz]; psz
0x408c86  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x408c8c  mov     edi, eax
0x408c8e  test    edi, edi
0x408c90  jz      short loc_408CB8
0x408c92  push    esi; dwReserved
0x408c93  lea     eax, [ebp+ppSM]
0x408c96  push    eax; ppSM
0x408c97  push    esi; pSP
0x408c98  call    ds:__imp__CoInternetCreateSecurityManager@12; CoInternetCreateSecurityManager(x,x,x)
0x408c9e  mov     esi, eax
0x408ca0  test    esi, esi
0x408ca2  js      short loc_408CAF
0x408ca4  mov     ecx, [ebp+ppSM]
0x408ca7  mov     [ebx+0Ch], ecx
0x408caa  mov     [ebx+8], edi
0x408cad  jmp     short loc_408CC4
0x408caf  push    edi; bstrString
0x408cb0  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x408cb6  jmp     short loc_408CC4
0x408cb8  mov     esi, 8007000Eh
0x408cbd  jmp     short loc_408CC4
0x408cbf  mov     esi, 80070057h
0x408cc4  pop     edi
0x408cc5  mov     eax, esi
0x408cc7  pop     esi
0x408cc8  pop     ebx
0x408cc9  leave
0x408cca  retn    4
```
