# CActiveXInstallBroker::Reset(int)

- ea: `0x402f70`
- end: `0x403014`
- name: `?Reset@CActiveXInstallBroker@@AAEXH@Z`
- size: `164`
- prototype: `void __thiscall(CActiveXInstallBroker *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x402f16`
- `0x4035e8`

## callees

- `0x402f46`
- `0x402f70`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x402fa5`
- `KERNEL32!FreeLibrary` at `0x402fb4`
- `KERNEL32!FreeLibrary` at `0x402fa5`
- `KERNEL32!FreeLibrary` at `0x402fb4`
- `ole32!CoTaskMemFree` at `0x402fc7`
- `ole32!CoTaskMemFree` at `0x402fd9`
- `ole32!CoTaskMemFree` at `0x402fc7`
- `ole32!CoTaskMemFree` at `0x402fd9`
- `OLEAUT32!__imp__SysFreeString@4` at `0x402f7b`
- `OLEAUT32!__imp__SysFreeString@4` at `0x402f84`
- `OLEAUT32!__imp__SysFreeString@4` at `0x402f8d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x402f96`
- `OLEAUT32!__imp__SysFreeString@4` at `0x402f7b`
- `OLEAUT32!__imp__SysFreeString@4` at `0x402f84`
- `OLEAUT32!__imp__SysFreeString@4` at `0x402f8d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x402f96`

## pseudocode

```c
void __thiscall CActiveXInstallBroker::Reset(CActiveXInstallBroker *this, int a2)
{
  int v3; // esi
  int v4; // eax
  int v5; // ecx
  void *v6; // [esp-8h] [ebp-Ch]

  SysFreeString(*((BSTR *)this + 8));
  SysFreeString(*((BSTR *)this + 9));
  SysFreeString(*((BSTR *)this + 10));
  SysFreeString(*((BSTR *)this + 11));
  if ( *((_DWORD *)this + 16) )
    FreeLibrary(*((HMODULE *)this + 16));
  if ( *((_DWORD *)this + 17) )
    FreeLibrary(*((HMODULE *)this + 17));
  v3 = *((_DWORD *)this + 19);
  while ( v3 )
  {
    if ( *(_DWORD *)v3 )
      CoTaskMemFree(*(LPVOID *)v3);
    v4 = 0;
    v6 = (void *)v3;
    if ( v3 != *(_DWORD *)(v3 + 4) )
      v4 = *(_DWORD *)(v3 + 4);
    v3 = v4;
    CoTaskMemFree(v6);
  }
  v5 = *((_DWORD *)this + 23);
  if ( v5 )
  {
    (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)v5 + 8))(*(_DWORD *)(*(_DWORD *)v5 + 8), *((_DWORD *)this + 23));
    *((_DWORD *)this + 23) = 0;
  }
  if ( a2 )
    CActiveXInstallBroker::Init(this);
}

```

## disassembly

```asm
0x402f70  mov     edi, edi
0x402f72  push    ebp
0x402f73  mov     ebp, esp
0x402f75  push    edi
0x402f76  mov     edi, ecx
0x402f78  push    dword ptr [edi+20h]; bstrString
0x402f7b  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x402f81  push    dword ptr [edi+24h]; bstrString
0x402f84  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x402f8a  push    dword ptr [edi+28h]; bstrString
0x402f8d  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x402f93  push    dword ptr [edi+2Ch]; bstrString
0x402f96  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x402f9c  cmp     dword ptr [edi+40h], 0
0x402fa0  jz      short loc_402FAB
0x402fa2  push    dword ptr [edi+40h]; hLibModule
0x402fa5  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x402fab  cmp     dword ptr [edi+44h], 0
0x402faf  jz      short loc_402FBA
0x402fb1  push    dword ptr [edi+44h]; hLibModule
0x402fb4  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x402fba  push    esi
0x402fbb  mov     esi, [edi+4Ch]
0x402fbe  jmp     short loc_402FDF
0x402fc0  cmp     dword ptr [esi], 0
0x402fc3  jz      short loc_402FCD
0x402fc5  push    dword ptr [esi]; pv
0x402fc7  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x402fcd  xor     eax, eax
0x402fcf  cmp     esi, [esi+4]
0x402fd2  push    esi; pv
0x402fd3  cmovnz  eax, [esi+4]
0x402fd7  mov     esi, eax
0x402fd9  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x402fdf  test    esi, esi
0x402fe1  jnz     short loc_402FC0
0x402fe3  mov     ecx, [edi+5Ch]
0x402fe6  test    ecx, ecx
0x402fe8  jz      short loc_403001
0x402fea  mov     eax, [ecx]
0x402fec  push    ecx
0x402fed  mov     esi, [eax+8]
0x402ff0  mov     ecx, esi
0x402ff2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x402ff8  call    esi
0x402ffa  mov     dword ptr [edi+5Ch], 0
0x403001  cmp     [ebp+arg_0], 0
0x403005  pop     esi
0x403006  jz      short loc_40300F
0x403008  mov     ecx, edi; this
0x40300a  call    ?Init@CActiveXInstallBroker@@AAEXXZ; CActiveXInstallBroker::Init(void)
0x40300f  pop     edi
0x403010  pop     ebp
0x403011  retn    4
```
