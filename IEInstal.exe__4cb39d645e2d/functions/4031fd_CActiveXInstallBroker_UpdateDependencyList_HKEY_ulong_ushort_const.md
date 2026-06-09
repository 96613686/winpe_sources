# CActiveXInstallBroker::UpdateDependencyList(HKEY__ *,ulong,ushort const * *)

- ea: `0x4031fd`
- end: `0x40328b`
- name: `?UpdateDependencyList@CActiveXInstallBroker@@AAEJPAUHKEY__@@KPAPBG@Z`
- size: `142`
- prototype: `unsigned int __thiscall(CActiveXInstallBroker *this, HKEY hKey, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x404c02`

## callees

- `0x4031fd`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x403251`
- `ADVAPI32!RegSetValueExW` at `0x403251`
- `ADVAPI32!RegCloseKey` at `0x40327c`
- `ADVAPI32!RegCloseKey` at `0x40327c`
- `ADVAPI32!RegCreateKeyW` at `0x403227`
- `ADVAPI32!RegCreateKeyW` at `0x403227`

## pseudocode

```c
unsigned int __thiscall CActiveXInstallBroker::UpdateDependencyList(
        CActiveXInstallBroker *this,
        HKEY hKey,
        unsigned int a3,
        const unsigned __int16 **a4)
{
  HKEY v4; // eax
  unsigned int v5; // esi
  int v6; // ebx
  int v7; // edi
  LSTATUS v8; // eax
  HKEY phkResult; // [esp+Ch] [ebp-4h] BYREF

  v4 = 0;
  v5 = 0;
  phkResult = 0;
  v6 = 1;
  v7 = 0;
  if ( !a3 )
    return v5;
  while ( 1 )
  {
    if ( v6 )
    {
      v8 = RegCreateKeyW(hKey, L"Distribution Units", &phkResult);
      if ( v8 )
        goto LABEL_11;
      v4 = phkResult;
      v6 = 0;
    }
    if ( a4 && a4[v7] )
      break;
LABEL_9:
    if ( ++v7 >= a3 )
      goto LABEL_14;
  }
  v8 = RegSetValueExW(v4, a4[v7], 0, 1u, (const BYTE *)&Data, 1u);
  if ( !v8 )
  {
    v4 = phkResult;
    goto LABEL_9;
  }
LABEL_11:
  v5 = (unsigned __int16)v8 | 0x80070000;
  if ( v8 <= 0 )
    v5 = v8;
  v4 = phkResult;
LABEL_14:
  if ( v4 )
    RegCloseKey(v4);
  return v5;
}

```

## disassembly

```asm
0x4031fd  mov     edi, edi
0x4031ff  push    ebp
0x403200  mov     ebp, esp
0x403202  push    ecx
0x403203  push    ebx
0x403204  push    esi
0x403205  xor     ebx, ebx
0x403207  xor     eax, eax
0x403209  push    edi
0x40320a  xor     esi, esi
0x40320c  mov     [ebp+phkResult], eax
0x40320f  inc     ebx
0x403210  xor     edi, edi
0x403212  cmp     [ebp+arg_4], eax
0x403215  jbe     short loc_403282
0x403217  test    ebx, ebx
0x403219  jz      short loc_403236
0x40321b  lea     eax, [ebp+phkResult]
0x40321e  push    eax; phkResult
0x40321f  push    offset aDistributionUn; "Distribution Units"
0x403224  push    [ebp+hKey]; hKey
0x403227  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x40322d  test    eax, eax
0x40322f  jnz     short loc_403266
0x403231  mov     eax, [ebp+phkResult]
0x403234  xor     ebx, ebx
0x403236  mov     ecx, [ebp+arg_8]
0x403239  test    ecx, ecx
0x40323b  jz      short loc_40325E
0x40323d  cmp     [ecx+edi*4], esi
0x403240  jz      short loc_40325E
0x403242  push    1; cbData
0x403244  push    offset Data; lpData
0x403249  push    1; dwType
0x40324b  push    0; Reserved
0x40324d  push    dword ptr [ecx+edi*4]; lpValueName
0x403250  push    eax; hKey
0x403251  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x403257  test    eax, eax
0x403259  jnz     short loc_403266
0x40325b  mov     eax, [ebp+phkResult]
0x40325e  inc     edi
0x40325f  cmp     edi, [ebp+arg_4]
0x403262  jb      short loc_403217
0x403264  jmp     short loc_403277
0x403266  movzx   esi, ax
0x403269  or      esi, 80070000h
0x40326f  test    eax, eax
0x403271  cmovle  esi, eax
0x403274  mov     eax, [ebp+phkResult]
0x403277  test    eax, eax
0x403279  jz      short loc_403282
0x40327b  push    eax; hKey
0x40327c  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x403282  pop     edi
0x403283  mov     eax, esi
0x403285  pop     esi
0x403286  pop     ebx
0x403287  leave
0x403288  retn    0Ch
```
