# ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x140017fbc`
- end: `0x1400180ae`
- name: `?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z`
- size: `242`
- prototype: `__int64 __fastcall(LPBYTE lpData, int, HKEY, const unsigned __int16 *, const unsigned __int16 *lpValueName)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400161f4`
- `0x140018b40`
- `0x140019054`

## callees

- `0x1400074d4`
- `0x140017fbc`
- `0x14001a8aa`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001800c`
- `ADVAPI32!RegOpenKeyExW` at `0x14001800c`
- `ADVAPI32!RegCloseKey` at `0x14001808e`
- `ADVAPI32!RegCloseKey` at `0x14001808e`
- `ADVAPI32!RegQueryValueExW` at `0x140018052`
- `ADVAPI32!RegQueryValueExW` at `0x140018052`
- `KERNEL32!SetLastError` at `0x140018096`
- `KERNEL32!SetLastError` at `0x140018096`

## string_xrefs

- `0x140018028`: `RegOpenKeyExW for %1 failed with Status = %2!d!.`

## pseudocode

```c
__int64 __fastcall ReadRegSZValue(
        LPBYTE lpData,
        int a2,
        HKEY a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpValueName)
{
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  int v13; // [rsp+54h] [rbp+1Ch]

  v13 = HIDWORD(a3);
  hKey = 0;
  cbData = 2 * a2;
  memset_0(lpData, 0, (unsigned int)(2 * a2));
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a4, 0, 0x101u, &hKey);
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    else
      v8 = v7;
    LogInfo(L"RegOpenKeyExW for %1 failed with Status = %2!d!.", a4, (unsigned int)v7);
    goto LABEL_11;
  }
  v8 = 0;
  v9 = RegQueryValueExW(hKey, lpValueName, 0, 0, lpData, &cbData);
  if ( v9 )
  {
    if ( v9 > 0 )
    {
      v8 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 == 2 )
        goto LABEL_11;
    }
    else
    {
      v8 = v9;
    }
    LogInfo(L"RegQueryValueExW for %1 failed with Status = %2!d!.", lpValueName, (unsigned int)v9);
  }
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(0);
  return v8;
}

```

## disassembly

```asm
0x140017fbc  mov     rax, rsp
0x140017fbf  mov     [rax+8], rbx
0x140017fc3  mov     [rax+20h], rsi
0x140017fc7  mov     [rax+18h], r8
0x140017fcb  push    rdi
0x140017fcc  sub     rsp, 30h
0x140017fd0  mov     qword ptr [rax+10h], 0
0x140017fd8  mov     rdi, r9
0x140017fdb  lea     eax, [rdx+rdx]
0x140017fde  mov     rsi, rcx
0x140017fe1  mov     r8d, eax; Size
0x140017fe4  xor     edx, edx; Val
0x140017fe6  mov     [rsp+38h+cbData], eax
0x140017fea  call    memset_0
0x140017fef  lea     rax, [rsp+38h+hKey]
0x140017ff4  mov     r9d, 101h; samDesired
0x140017ffa  xor     r8d, r8d; ulOptions
0x140017ffd  mov     [rsp+38h+phkResult], rax; phkResult
0x140018002  mov     rdx, rdi; lpSubKey
0x140018005  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001800c  call    cs:__imp_RegOpenKeyExW
0x140018012  test    eax, eax
0x140018014  jz      short loc_140018031
0x140018016  jg      short loc_14001801C
0x140018018  mov     ebx, eax
0x14001801a  jmp     short loc_140018025
0x14001801c  movzx   ebx, ax
0x14001801f  or      ebx, 80070000h
0x140018025  mov     rdx, rdi
0x140018028  lea     rcx, aRegopenkeyexwF_1; "RegOpenKeyExW for %1 failed with Status"...
0x14001802f  jmp     short loc_14001807C
0x140018031  mov     rdx, [rsp+38h+lpValueName]; lpValueName
0x140018036  lea     rax, [rsp+38h+cbData]
0x14001803b  mov     rcx, [rsp+38h+hKey]; hKey
0x140018040  xor     r9d, r9d; lpType
0x140018043  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140018048  xor     r8d, r8d; lpReserved
0x14001804b  mov     [rsp+38h+phkResult], rsi; lpData
0x140018050  xor     ebx, ebx
0x140018052  call    cs:__imp_RegQueryValueExW
0x140018058  test    eax, eax
0x14001805a  jz      short loc_140018084
0x14001805c  jg      short loc_140018062
0x14001805e  mov     ebx, eax
0x140018060  jmp     short loc_140018070
0x140018062  movzx   ebx, ax
0x140018065  or      ebx, 80070000h
0x14001806b  cmp     eax, 2
0x14001806e  jz      short loc_140018084
0x140018070  mov     rdx, [rsp+38h+lpValueName]
0x140018075  lea     rcx, aRegqueryvaluee; "RegQueryValueExW for %1 failed with Sta"...
0x14001807c  mov     r8d, eax
0x14001807f  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140018084  mov     rcx, [rsp+38h+hKey]; hKey
0x140018089  test    rcx, rcx
0x14001808c  jz      short loc_140018094
0x14001808e  call    cs:__imp_RegCloseKey
0x140018094  xor     ecx, ecx; dwErrCode
0x140018096  call    cs:__imp_SetLastError
0x14001809c  mov     rsi, [rsp+38h+arg_18]
0x1400180a1  mov     eax, ebx
0x1400180a3  mov     rbx, [rsp+38h+arg_0]
0x1400180a8  add     rsp, 30h
0x1400180ac  pop     rdi
0x1400180ad  retn
```
