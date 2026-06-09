# CActiveXInstallSecurityManager::~CActiveXInstallSecurityManager(void)

- ea: `0x408c35`
- end: `0x408c68`
- name: `??1CActiveXInstallSecurityManager@@QAE@XZ`
- size: `51`
- prototype: `void __thiscall(CActiveXInstallSecurityManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x408d50`

## callees

- `0x408c35`
- `0x40d1d0`

## import_xrefs

- `OLEAUT32!__imp__SysFreeString@4` at `0x408c49`
- `OLEAUT32!__imp__SysFreeString@4` at `0x408c49`

## pseudocode

```c
void __thiscall CActiveXInstallSecurityManager::~CActiveXInstallSecurityManager(CActiveXInstallSecurityManager *this)
{
  bool v2; // zf
  int v3; // ecx

  v2 = *((_DWORD *)this + 2) == 0;
  *(_DWORD *)this = &CActiveXInstallSecurityManager::`vftable';
  if ( !v2 )
    SysFreeString(*((BSTR *)this + 2));
  v3 = *((_DWORD *)this + 3);
  if ( v3 )
    (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)v3 + 8))(*(_DWORD *)(*(_DWORD *)v3 + 8), *((_DWORD *)this + 3));
}

```

## disassembly

```asm
0x408c35  mov     edi, edi
0x408c37  push    esi
0x408c38  mov     esi, ecx
0x408c3a  cmp     dword ptr [esi+8], 0
0x408c3e  mov     dword ptr [esi], offset ??_7CActiveXInstallSecurityManager@@6B@; const CActiveXInstallSecurityManager::`vftable'
0x408c44  jz      short loc_408C4F
0x408c46  push    dword ptr [esi+8]; bstrString
0x408c49  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x408c4f  mov     ecx, [esi+0Ch]
0x408c52  test    ecx, ecx
0x408c54  jz      short loc_408C66
0x408c56  mov     eax, [ecx]
0x408c58  push    ecx
0x408c59  mov     esi, [eax+8]
0x408c5c  mov     ecx, esi
0x408c5e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x408c64  call    esi
0x408c66  pop     esi
0x408c67  retn
```
