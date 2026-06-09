# QualcommRadioDriverMigrationShimCollect(int *,ushort const *,ushort const *,void *)

- ea: `0x18003a720`
- end: `0x18003a858`
- name: `?QualcommRadioDriverMigrationShimCollect@@YAJPEAHPEBG1PEAX@Z`
- size: `312`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a6f0`

## callees

- `0x18003a654`
- `0x18003a720`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18003a7d4`
- `ADVAPI32!RegQueryValueExW` at `0x18003a7d4`
- `ADVAPI32!RegCloseKey` at `0x18003a83f`
- `ADVAPI32!RegCloseKey` at `0x18003a83f`
- `ADVAPI32!RegSetValueExW` at `0x18003a81f`
- `ADVAPI32!RegSetValueExW` at `0x18003a81f`
- `ADVAPI32!RegCreateKeyExW` at `0x18003a798`
- `ADVAPI32!RegCreateKeyExW` at `0x18003a798`

## pseudocode

```c
__int64 __fastcall QualcommRadioDriverMigrationShimCollect(
        int *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4)
{
  unsigned int v5; // ecx
  char *v6; // rdx
  DWORD cbData; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+54h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  int Data; // [rsp+70h] [rbp+10h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Type = 0;
  cbData = 0;
  Data = 0;
  QualcommLogMsg((unsigned int)a1, "*Collect*");
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, QualcommRegData, 0, 0, 0, 0x20006u, 0, &hKey, 0) )
  {
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && Data == *(_DWORD *)&dword_180096970 )
    {
      v6 = "*Nothing is changed*";
    }
    else
    {
      RegSetValueExW(hKey, lpValueName, 0, 4u, &dword_180096970, cbData);
      v6 = "*Vaule is set to 0*";
    }
    QualcommLogMsg(v5, v6);
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  *a1 = 0;
  return 0;
}

```

## disassembly

```asm
0x18003a720  mov     [rsp-8+arg_8], rbx
0x18003a725  push    rbp
0x18003a726  mov     rbp, rsp
0x18003a729  sub     rsp, 60h
0x18003a72d  lea     rdx, aCollect_1; "*Collect*"
0x18003a734  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x18003a73c  mov     rbx, rcx
0x18003a73f  mov     [rbp+Type], 0
0x18003a746  mov     [rbp+cbData], 0
0x18003a74d  mov     [rbp+Data], 0
0x18003a754  call    ?QualcommLogMsg@@YAXKPEAD@Z; QualcommLogMsg(ulong,char *)
0x18003a759  mov     rdx, cs:?QualcommRegData@@3PAU_QUALCOMMREG@@A; lpSubKey
0x18003a760  lea     rax, [rbp+hKey]
0x18003a764  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18003a76d  xor     r9d, r9d; lpClass
0x18003a770  mov     [rsp+60h+phkResult], rax; phkResult
0x18003a775  xor     r8d, r8d; Reserved
0x18003a778  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003a781  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a788  mov     [rsp+60h+samDesired], 20006h; samDesired
0x18003a790  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18003a798  call    cs:__imp_RegCreateKeyExW
0x18003a79e  test    eax, eax
0x18003a7a0  jnz     loc_18003A831
0x18003a7a6  mov     rdx, cs:lpValueName; lpValueName
0x18003a7ad  lea     r9, [rbp+Type]; lpType
0x18003a7b1  mov     rcx, [rbp+hKey]; hKey
0x18003a7b5  xor     r8d, r8d; lpReserved
0x18003a7b8  mov     [rbp+Data], eax
0x18003a7bb  lea     rax, [rbp+cbData]
0x18003a7bf  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x18003a7c4  lea     rax, [rbp+Data]
0x18003a7c8  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18003a7cd  mov     [rbp+cbData], 4
0x18003a7d4  call    cs:__imp_RegQueryValueExW
0x18003a7da  test    eax, eax
0x18003a7dc  jnz     short loc_18003A7F8
0x18003a7de  cmp     [rbp+Type], 4
0x18003a7e2  jnz     short loc_18003A7F8
0x18003a7e4  mov     eax, cs:dword_180096970
0x18003a7ea  cmp     [rbp+Data], eax
0x18003a7ed  jnz     short loc_18003A7F8
0x18003a7ef  lea     rdx, aNothingIsChang; "*Nothing is changed*"
0x18003a7f6  jmp     short loc_18003A82C
0x18003a7f8  mov     eax, [rbp+cbData]
0x18003a7fb  mov     r9d, 4; dwType
0x18003a801  mov     rdx, cs:lpValueName; lpValueName
0x18003a808  xor     r8d, r8d; Reserved
0x18003a80b  mov     rcx, [rbp+hKey]; hKey
0x18003a80f  mov     [rsp+60h+samDesired], eax; cbData
0x18003a813  lea     rax, dword_180096970
0x18003a81a  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18003a81f  call    cs:__imp_RegSetValueExW
0x18003a825  lea     rdx, aVauleIsSetTo0; "*Vaule is set to 0*"
0x18003a82c  call    ?QualcommLogMsg@@YAXKPEAD@Z; QualcommLogMsg(ulong,char *)
0x18003a831  mov     rcx, [rbp+hKey]; hKey
0x18003a835  lea     rax, [rcx-1]
0x18003a839  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003a83d  ja      short loc_18003A845
0x18003a83f  call    cs:__imp_RegCloseKey
0x18003a845  mov     dword ptr [rbx], 0
0x18003a84b  xor     eax, eax
0x18003a84d  mov     rbx, [rsp+60h+arg_8]
0x18003a852  add     rsp, 60h
0x18003a856  pop     rbp
0x18003a857  retn
```
