# CActiveXInstallBroker::RegisterDllFile2ThreadProc(void *)

- ea: `0x404460`
- end: `0x4044a8`
- name: `?RegisterDllFile2ThreadProc@CActiveXInstallBroker@@CGKPAX@Z`
- size: `72`
- prototype: `HRESULT __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x404460`
- `0x4044ae`

## import_xrefs

- `ole32!CoInitialize` at `0x404468`
- `ole32!CoInitialize` at `0x404468`
- `ole32!CoUninitialize` at `0x40449b`
- `ole32!CoUninitialize` at `0x40449b`

## pseudocode

```c
HRESULT __stdcall CActiveXInstallBroker::RegisterDllFile2ThreadProc(LPVOID lpThreadParameter)
{
  HRESULT v1; // esi

  v1 = CoInitialize(0);
  if ( v1 >= 0 )
  {
    if ( lpThreadParameter && *(_DWORD *)lpThreadParameter )
      v1 = CActiveXInstallBroker::RegisterDllFile2Helper(
             *(const unsigned __int16 ***)lpThreadParameter,
             *((unsigned __int16 **)lpThreadParameter + 1),
             *((_DWORD *)lpThreadParameter + 2),
             *((_DWORD *)lpThreadParameter + 3),
             *((_DWORD *)lpThreadParameter + 4));
    else
      v1 = -2147024809;
    CoUninitialize();
  }
  return v1;
}

```

## disassembly

```asm
0x404460  mov     edi, edi
0x404462  push    ebp
0x404463  mov     ebp, esp
0x404465  push    esi
0x404466  push    0; pvReserved
0x404468  call    ds:__imp__CoInitialize@4; CoInitialize(x)
0x40446e  mov     esi, eax
0x404470  test    esi, esi
0x404472  js      short loc_4044A1
0x404474  mov     eax, [ebp+lpThreadParameter]
0x404477  test    eax, eax
0x404479  jz      short loc_404496
0x40447b  mov     ecx, [eax]; this
0x40447d  test    ecx, ecx
0x40447f  jz      short loc_404496
0x404481  push    dword ptr [eax+10h]; int
0x404484  push    dword ptr [eax+0Ch]; int
0x404487  push    dword ptr [eax+8]; cchDest
0x40448a  push    dword ptr [eax+4]; unsigned __int16 *
0x40448d  call    ?RegisterDllFile2Helper@CActiveXInstallBroker@@AAEJPAG0HH@Z; CActiveXInstallBroker::RegisterDllFile2Helper(ushort *,ushort *,int,int)
0x404492  mov     esi, eax
0x404494  jmp     short loc_40449B
0x404496  mov     esi, 80070057h
0x40449b  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x4044a1  mov     eax, esi
0x4044a3  pop     esi
0x4044a4  pop     ebp
0x4044a5  retn    4
```
