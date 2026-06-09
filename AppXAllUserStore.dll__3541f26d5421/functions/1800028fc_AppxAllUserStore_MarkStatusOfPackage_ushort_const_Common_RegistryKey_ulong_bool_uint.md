# AppxAllUserStore::MarkStatusOfPackage(ushort const *,Common::RegistryKey *,ulong,bool,uint *)

- ea: `0x1800028fc`
- end: `0x180002b15`
- name: `?MarkStatusOfPackage@AppxAllUserStore@@YAJPEBGPEAVRegistryKey@Common@@K_NPEAI@Z`
- size: `537`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, const unsigned __int16 *, struct Common::RegistryKey *, unsigned int, bool, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180002c94`

## callees

- `0x1800028fc`
- `0x1800035f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002948`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800029ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002948`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800029ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002a71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002ad2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002a71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002ad2`

## string_xrefs

- `0x1800029aa`: `NumberOfAttempts`
- `0x180002a27`: `NumberOfAttempts`
- `0x180002ab2`: `NumberOfAttempts`
- `0x180002af4`: `NumberOfAttempts`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::MarkStatusOfPackage(
        AppxAllUserStore *this,
        HKEY *a2,
        struct Common::RegistryKey *a3,
        char a4,
        _DWORD *a5)
{
  DWORD v7; // esi
  int v8; // edi
  int Value; // eax
  int v10; // ecx
  bool v11; // sf
  char v13; // bl
  HKEY v14; // rcx
  int v15; // eax
  int v16; // ecx
  bool v17; // sf
  HKEY v18; // rcx
  LSTATUS v19; // eax
  int v20; // ecx
  signed int v21; // ebx
  const WCHAR *v22; // r9
  HKEY v23; // rcx
  LSTATUS v24; // eax
  BYTE lpData[4]; // [rsp+30h] [rbp-18h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-14h] BYREF
  DWORD cbData[4]; // [rsp+38h] [rbp-10h] BYREF

  *(_DWORD *)Data = 0;
  cbData[0] = 4;
  v7 = (unsigned int)a3;
  v8 = (int)this;
  Value = RegQueryValueExW(*a2, L"LastReturnValue", 0, 0, Data, cbData);
  v11 = Value < 0;
  if ( Value > 0 )
  {
    Value = (unsigned __int16)Value | 0x80070000;
    v11 = Value < 0;
  }
  if ( v11 )
  {
    v13 = 0;
    if ( Value != -2147024894 && Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v10,
        (unsigned int)AppxAllUserStoreReadKeyValueError,
        v8,
        (unsigned int)L"LastReturnValue",
        Value);
  }
  else
  {
    if ( !*(_DWORD *)Data && !v7 )
      return 0;
    v13 = 1;
  }
  v14 = *a2;
  *(_DWORD *)lpData = 1;
  cbData[0] = 4;
  v15 = RegQueryValueExW(v14, L"NumberOfAttempts", 0, 0, lpData, cbData);
  v17 = v15 < 0;
  if ( v15 > 0 )
  {
    v15 = (unsigned __int16)v15 | 0x80070000;
    v17 = v15 < 0;
  }
  if ( v17 )
  {
    if ( v15 != -2147024894 && Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v16,
        (unsigned int)AppxAllUserStoreReadKeyValueError,
        v8,
        (unsigned int)L"NumberOfAttempts",
        0);
    *(_DWORD *)lpData = 1;
  }
  else
  {
    if ( *(_DWORD *)lpData >= 0xAu )
      return 2147942413LL;
    if ( !a4 )
      ++*(_DWORD *)lpData;
    if ( v13 && !*(_DWORD *)Data && v7 )
      *(_DWORD *)lpData = 0;
  }
  v18 = *a2;
  cbData[0] = v7;
  v19 = RegSetValueExW(v18, L"LastReturnValue", 0, 4u, (const BYTE *)cbData, 4u);
  v21 = v19;
  if ( v19 > 0 )
    v21 = (unsigned __int16)v19 | 0x80070000;
  if ( v21 >= 0 )
  {
    v23 = *a2;
    cbData[0] = *(_DWORD *)lpData;
    v24 = RegSetValueExW(v23, L"NumberOfAttempts", 0, 4u, (const BYTE *)cbData, 4u);
    v21 = v24;
    if ( v24 > 0 )
      v21 = (unsigned __int16)v24 | 0x80070000;
    if ( v21 >= 0 )
    {
      *a5 = *(_DWORD *)lpData;
      return (unsigned int)v21;
    }
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
    {
      v22 = L"NumberOfAttempts";
      goto LABEL_31;
    }
  }
  else if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
  {
    v22 = L"LastReturnValue";
LABEL_31:
    McTemplateU0zzd_EventWriteTransfer(v20, (unsigned int)AppxAllUserStoreWriteKeyValueError, v8, (_DWORD)v22, v21);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800028fc  push    rbp
0x1800028fe  push    rbx
0x1800028ff  push    rsi
0x180002900  push    rdi
0x180002901  push    r14
0x180002903  push    r15
0x180002905  mov     rbp, rsp
0x180002908  sub     rsp, 48h
0x18000290c  mov     r14, rdx
0x18000290f  mov     dword ptr [rbp+Data], 0
0x180002916  lea     rax, [rbp+cbData]
0x18000291a  mov     [rbp+cbData], 4
0x180002921  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180002926  lea     rdx, ValueName; "LastReturnValue"
0x18000292d  mov     r15b, r9b
0x180002930  lea     rax, [rbp+Data]
0x180002934  mov     esi, r8d
0x180002937  mov     [rsp+48h+lpData], rax; lpData
0x18000293c  mov     rdi, rcx
0x18000293f  xor     r9d, r9d; lpType
0x180002942  mov     rcx, [r14]; hKey
0x180002945  xor     r8d, r8d; lpReserved
0x180002948  call    cs:__imp_RegQueryValueExW
0x18000294e  test    eax, eax
0x180002950  jle     short loc_18000295C
0x180002952  movzx   eax, ax
0x180002955  or      eax, 80070000h
0x18000295a  test    eax, eax
0x18000295c  js      short loc_180002973
0x18000295e  cmp     dword ptr [rbp+Data], 0
0x180002962  jnz     short loc_18000296F
0x180002964  test    esi, esi
0x180002966  jnz     short loc_18000296F
0x180002968  xor     eax, eax
0x18000296a  jmp     loc_180002B08
0x18000296f  mov     bl, 1
0x180002971  jmp     short loc_18000299E
0x180002973  xor     bl, bl
0x180002975  cmp     eax, 80070002h
0x18000297a  jz      short loc_18000299E
0x18000297c  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, bl
0x180002982  jge     short loc_18000299E
0x180002984  lea     r9, ValueName; "LastReturnValue"
0x18000298b  mov     dword ptr [rsp+48h+lpData], eax
0x18000298f  mov     r8, rdi
0x180002992  lea     rdx, AppxAllUserStoreReadKeyValueError
0x180002999  call    McTemplateU0zzd_EventWriteTransfer
0x18000299e  mov     rcx, [r14]; hKey
0x1800029a1  lea     rax, [rbp+cbData]
0x1800029a5  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800029aa  lea     rdx, aNumberofattemp; "NumberOfAttempts"
0x1800029b1  lea     rax, [rbp+var_18]
0x1800029b5  mov     dword ptr [rbp+var_18], 1
0x1800029bc  xor     r9d, r9d; lpType
0x1800029bf  mov     [rsp+48h+lpData], rax; lpData
0x1800029c4  xor     r8d, r8d; lpReserved
0x1800029c7  mov     [rbp+cbData], 4
0x1800029ce  call    cs:__imp_RegQueryValueExW
0x1800029d4  test    eax, eax
0x1800029d6  jle     short loc_1800029E2
0x1800029d8  movzx   eax, ax
0x1800029db  or      eax, 80070000h
0x1800029e0  test    eax, eax
0x1800029e2  js      short loc_180002A17
0x1800029e4  mov     eax, dword ptr [rbp+var_18]
0x1800029e7  cmp     eax, 0Ah
0x1800029ea  jb      short loc_1800029F6
0x1800029ec  mov     eax, 8007000Dh
0x1800029f1  jmp     loc_180002B08
0x1800029f6  test    r15b, r15b
0x1800029f9  jnz     short loc_180002A00
0x1800029fb  inc     eax
0x1800029fd  mov     dword ptr [rbp+var_18], eax
0x180002a00  test    bl, bl
0x180002a02  jz      short loc_180002A4C
0x180002a04  cmp     dword ptr [rbp+Data], 0
0x180002a08  jnz     short loc_180002A4C
0x180002a0a  test    esi, esi
0x180002a0c  jz      short loc_180002A4C
0x180002a0e  mov     dword ptr [rbp+var_18], 0
0x180002a15  jmp     short loc_180002A4C
0x180002a17  cmp     eax, 80070002h
0x180002a1c  jz      short loc_180002A45
0x180002a1e  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180002a25  jge     short loc_180002A45
0x180002a27  lea     r9, aNumberofattemp; "NumberOfAttempts"
0x180002a2e  mov     dword ptr [rsp+48h+lpData], 0
0x180002a36  mov     r8, rdi
0x180002a39  lea     rdx, AppxAllUserStoreReadKeyValueError
0x180002a40  call    McTemplateU0zzd_EventWriteTransfer
0x180002a45  mov     dword ptr [rbp+var_18], 1
0x180002a4c  mov     rcx, [r14]; hKey
0x180002a4f  lea     rax, [rbp+cbData]
0x180002a53  mov     [rbp+cbData], esi
0x180002a56  lea     rdx, ValueName; "LastReturnValue"
0x180002a5d  mov     esi, 4
0x180002a62  xor     r8d, r8d; Reserved
0x180002a65  mov     dword ptr [rsp+48h+lpcbData], esi; cbData
0x180002a69  mov     r9d, esi; dwType
0x180002a6c  mov     [rsp+48h+lpData], rax; lpData
0x180002a71  call    cs:__imp_RegSetValueExW
0x180002a77  mov     ebx, eax
0x180002a79  test    eax, eax
0x180002a7b  jle     short loc_180002A86
0x180002a7d  movzx   ebx, ax
0x180002a80  or      ebx, 80070000h
0x180002a86  test    ebx, ebx
0x180002a88  jns     short loc_180002AAF
0x180002a8a  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180002a91  jge     short loc_180002B06
0x180002a93  lea     r9, ValueName; "LastReturnValue"
0x180002a9a  mov     r8, rdi
0x180002a9d  mov     dword ptr [rsp+48h+lpData], ebx
0x180002aa1  lea     rdx, AppxAllUserStoreWriteKeyValueError
0x180002aa8  call    McTemplateU0zzd_EventWriteTransfer
0x180002aad  jmp     short loc_180002B06
0x180002aaf  mov     eax, dword ptr [rbp+var_18]
0x180002ab2  lea     rdx, aNumberofattemp; "NumberOfAttempts"
0x180002ab9  mov     rcx, [r14]; hKey
0x180002abc  mov     r9d, esi; dwType
0x180002abf  mov     [rbp+cbData], eax
0x180002ac2  xor     r8d, r8d; Reserved
0x180002ac5  lea     rax, [rbp+cbData]
0x180002ac9  mov     dword ptr [rsp+48h+lpcbData], esi; cbData
0x180002acd  mov     [rsp+48h+lpData], rax; lpData
0x180002ad2  call    cs:__imp_RegSetValueExW
0x180002ad8  mov     ebx, eax
0x180002ada  test    eax, eax
0x180002adc  jle     short loc_180002AE7
0x180002ade  movzx   ebx, ax
0x180002ae1  or      ebx, 80070000h
0x180002ae7  test    ebx, ebx
0x180002ae9  jns     short loc_180002AFD
0x180002aeb  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180002af2  jge     short loc_180002B06
0x180002af4  lea     r9, aNumberofattemp; "NumberOfAttempts"
0x180002afb  jmp     short loc_180002A9A
0x180002afd  mov     rcx, qword ptr [rbp+arg_20]
0x180002b01  mov     eax, dword ptr [rbp+var_18]
0x180002b04  mov     [rcx], eax
0x180002b06  mov     eax, ebx
0x180002b08  add     rsp, 48h
0x180002b0c  pop     r15
0x180002b0e  pop     r14
0x180002b10  pop     rdi
0x180002b11  pop     rsi
0x180002b12  pop     rbx
0x180002b13  pop     rbp
0x180002b14  retn
```
