# CActiveXInstallBroker::RegisterDllFile2(ushort *,ushort *,int,int)

- ea: `0x404806`
- end: `0x40485e`
- name: `?RegisterDllFile2@CActiveXInstallBroker@@QAGJPAG0HH@Z`
- size: `88`
- prototype: `HRESULT __userpurge@<eax>(OLECHAR *@<edx>, CLSID *@<ecx>, OLECHAR *cchDest, unsigned __int16 *, unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x405e30`
- `0x405e70`

## callees

- `0x4044ae`
- `0x404806`
- `0x404864`

## import_xrefs

- `urlmon!CompatFlagsFromClsid` at `0x40482d`
- `urlmon!CompatFlagsFromClsid` at `0x40482d`

## pseudocode

```c
HRESULT __userpurge CActiveXInstallBroker::RegisterDllFile2@<eax>(
        OLECHAR *a1@<edx>,
        CLSID *a2@<ecx>,
        OLECHAR *cchDest,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6,
        int a7)
{
  HRESULT result; // eax
  DWORD pdwMiscStatusFlags; // [esp+8h] [ebp-8h] BYREF
  DWORD pdwCompatFlags; // [esp+Ch] [ebp-4h] BYREF

  pdwCompatFlags = 0;
  pdwMiscStatusFlags = 0;
  result = CompatFlagsFromClsid(a2 + 3, &pdwCompatFlags, &pdwMiscStatusFlags);
  if ( result >= 0 )
  {
    if ( (pdwCompatFlags & 0x1000000) != 0 )
      return CActiveXInstallBroker::STARegisterDllFile2((CActiveXInstallBroker *)a2, a1, cchDest, (int)a4, (int)a5);
    else
      return CActiveXInstallBroker::RegisterDllFile2Helper(
               (CActiveXInstallBroker *)a2,
               a1,
               (size_t)cchDest,
               (int)a4,
               (int)a5);
  }
  return result;
}

```

## disassembly

```asm
0x404806  mov     edi, edi
0x404808  push    ebp
0x404809  mov     ebp, esp
0x40480b  push    ecx
0x40480c  push    ecx
0x40480d  push    esi
0x40480e  push    edi
0x40480f  lea     eax, [ebp+pdwMiscStatusFlags]
0x404812  mov     [ebp+pdwCompatFlags], 0
0x404819  push    eax; pdwMiscStatusFlags
0x40481a  mov     esi, ecx
0x40481c  mov     [ebp+pdwMiscStatusFlags], 0
0x404823  lea     eax, [ebp+pdwCompatFlags]
0x404826  mov     edi, edx
0x404828  push    eax; pdwCompatFlags
0x404829  lea     eax, [esi+30h]
0x40482c  push    eax; pclsid
0x40482d  call    ds:__imp__CompatFlagsFromClsid@12; CompatFlagsFromClsid(x,x,x)
0x404833  test    eax, eax
0x404835  js      short loc_404858
0x404837  test    [ebp+pdwCompatFlags], 1000000h
0x40483e  mov     ecx, esi; this
0x404840  push    [ebp+arg_8]; int
0x404843  push    [ebp+arg_4]; int
0x404846  push    [ebp+cchDest]; cchDest
0x404849  push    edi; unsigned __int16 *
0x40484a  jz      short loc_404853
0x40484c  call    ?STARegisterDllFile2@CActiveXInstallBroker@@AAEJPAG0HH@Z; CActiveXInstallBroker::STARegisterDllFile2(ushort *,ushort *,int,int)
0x404851  jmp     short loc_404858
0x404853  call    ?RegisterDllFile2Helper@CActiveXInstallBroker@@AAEJPAG0HH@Z; CActiveXInstallBroker::RegisterDllFile2Helper(ushort *,ushort *,int,int)
0x404858  pop     edi
0x404859  pop     esi
0x40485a  leave
0x40485b  retn    0Ch
```
