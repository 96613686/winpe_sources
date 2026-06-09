# WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1400182dc`
- end: `0x1400183e9`
- name: `?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019d68`
- `0x14001a0c4`
- `0x14001a244`
- `0x14001a418`

## callees

- `0x1400074d4`
- `0x1400182dc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400183c9`
- `ADVAPI32!RegCloseKey` at `0x1400183c9`
- `ADVAPI32!RegCreateKeyExW` at `0x14001834f`
- `ADVAPI32!RegCreateKeyExW` at `0x14001834f`
- `ADVAPI32!RegSetValueExW` at `0x140018394`
- `ADVAPI32!RegSetValueExW` at `0x140018394`
- `KERNEL32!SetLastError` at `0x1400183d1`
- `KERNEL32!SetLastError` at `0x1400183d1`

## string_xrefs

- `0x14001836b`: `RegCreateKeyEx for subkey %1 failed with Status = %2!d!.`
- `0x1400183b0`: `RegSetValueEx for value %1 failed with Status = %2!d!.`

## pseudocode

```c
__int64 __fastcall WriteRegDWORDValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  if ( a2 && a3 )
  {
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x20106u, 0, &hKey, 0);
    if ( v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      else
        v6 = v7;
      LogInfo(L"RegCreateKeyEx for subkey %1 failed with Status = %2!d!.", a2, (unsigned int)v7);
    }
    else
    {
      v6 = 0;
      v8 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
      if ( v8 )
      {
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
        else
          v6 = v8;
        LogInfo(L"RegSetValueEx for value %1 failed with Status = %2!d!.", a3, (unsigned int)v8);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    v6 = -2147024809;
  }
  SetLastError(0);
  return v6;
}

```

## disassembly

```asm
0x1400182dc  mov     rax, rsp
0x1400182df  mov     [rax+10h], rbx
0x1400182e3  mov     [rax+18h], rsi
0x1400182e7  mov     [rax+20h], r9d
0x1400182eb  mov     [rax+8], rcx
0x1400182ef  push    rdi
0x1400182f0  sub     rsp, 50h
0x1400182f4  mov     qword ptr [rax+8], 0
0x1400182fc  mov     rdi, r8
0x1400182ff  mov     rsi, rdx
0x140018302  test    rdx, rdx
0x140018305  jnz     short loc_140018311
0x140018307  mov     ebx, 80070057h
0x14001830c  jmp     loc_1400183CF
0x140018311  test    rdi, rdi
0x140018314  jz      short loc_140018307
0x140018316  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x14001831f  lea     rax, [rsp+58h+hKey]
0x140018324  mov     [rsp+58h+phkResult], rax; phkResult
0x140018329  xor     r9d, r9d; lpClass
0x14001832c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140018335  xor     r8d, r8d; Reserved
0x140018338  mov     [rsp+58h+samDesired], 20106h; samDesired
0x140018340  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018347  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14001834f  call    cs:__imp_RegCreateKeyExW
0x140018355  test    eax, eax
0x140018357  jz      short loc_140018374
0x140018359  jg      short loc_14001835F
0x14001835b  mov     ebx, eax
0x14001835d  jmp     short loc_140018368
0x14001835f  movzx   ebx, ax
0x140018362  or      ebx, 80070000h
0x140018368  mov     rdx, rsi
0x14001836b  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx for subkey %1 failed wit"...
0x140018372  jmp     short loc_1400183B7
0x140018374  mov     rcx, [rsp+58h+hKey]; hKey
0x140018379  lea     rax, [rsp+58h+Data]
0x14001837e  xor     ebx, ebx
0x140018380  xor     r8d, r8d; Reserved
0x140018383  mov     rdx, rdi; lpValueName
0x140018386  lea     r9d, [rbx+4]; dwType
0x14001838a  mov     [rsp+58h+samDesired], r9d; cbData
0x14001838f  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x140018394  call    cs:__imp_RegSetValueExW
0x14001839a  test    eax, eax
0x14001839c  jz      short loc_1400183BF
0x14001839e  jg      short loc_1400183A4
0x1400183a0  mov     ebx, eax
0x1400183a2  jmp     short loc_1400183AD
0x1400183a4  movzx   ebx, ax
0x1400183a7  or      ebx, 80070000h
0x1400183ad  mov     rdx, rdi
0x1400183b0  lea     rcx, aRegsetvalueexF_0; "RegSetValueEx for value %1 failed with "...
0x1400183b7  mov     r8d, eax
0x1400183ba  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x1400183bf  mov     rcx, [rsp+58h+hKey]; hKey
0x1400183c4  test    rcx, rcx
0x1400183c7  jz      short loc_1400183CF
0x1400183c9  call    cs:__imp_RegCloseKey
0x1400183cf  xor     ecx, ecx; dwErrCode
0x1400183d1  call    cs:__imp_SetLastError
0x1400183d7  mov     rsi, [rsp+58h+arg_10]
0x1400183dc  mov     eax, ebx
0x1400183de  mov     rbx, [rsp+58h+arg_8]
0x1400183e3  add     rsp, 50h
0x1400183e7  pop     rdi
0x1400183e8  retn
```
