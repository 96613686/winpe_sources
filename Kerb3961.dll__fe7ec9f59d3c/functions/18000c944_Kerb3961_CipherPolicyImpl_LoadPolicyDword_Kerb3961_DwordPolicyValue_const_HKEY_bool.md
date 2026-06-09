# Kerb3961::CipherPolicyImpl::LoadPolicyDword(Kerb3961::DwordPolicyValue const &,HKEY__ *,bool)

- ea: `0x18000c944`
- end: `0x18000ca73`
- name: `?LoadPolicyDword@CipherPolicyImpl@Kerb3961@@QEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUDwordPolicyValue@2@PEAUHKEY__@@_N@Z`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c4c8`
- `0x18000c944`

## callees

- `0x180002ec0`
- `0x18000c944`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c995`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c995`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c9e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c9e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca1d`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::CipherPolicyImpl::LoadPolicyDword(int a1, _DWORD *a2, __int64 a3, HKEY a4, char a5)
{
  Kerb3961::Telemetry *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // r8d
  const WCHAR *v11; // rdx
  int v12; // eax
  int v13; // r9d
  int v14; // eax
  _DWORD *v15; // rcx
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  BYTE Data[20]; // [rsp+34h] [rbp-14h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+40h] BYREF

  if ( a4 )
  {
    v8 = *(Kerb3961::Telemetry **)a3;
    LODWORD(hKey) = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    v9 = RegQueryValueExW(a4, (LPCWSTR)v8, 0, (LPDWORD)&hKey, Data, &cbData);
    if ( v9 != 2 )
    {
      if ( v9 || (_DWORD)hKey != 4 || cbData != 4 )
      {
        *a2 = -1073739509;
        return a2;
      }
      Kerb3961::Telemetry::PolicyConfiguration(
        *(Kerb3961::Telemetry **)a3,
        (const unsigned __int16 *)**(unsigned int **)(a3 + 8),
        v10);
      v14 = *(_DWORD *)Data;
      v15 = *(_DWORD **)(a3 + 8);
      if ( *(_DWORD *)Data )
      {
LABEL_20:
        *v15 = v14;
        *a2 = 0;
        return a2;
      }
LABEL_19:
      v14 = *(_DWORD *)(a3 + 16);
      goto LABEL_20;
    }
    **(_DWORD **)(a3 + 8) = *(_DWORD *)(a3 + 16);
  }
  v11 = *(const WCHAR **)(a3 + 24);
  if ( !v11 || a5 )
  {
    v15 = *(_DWORD **)(a3 + 8);
    goto LABEL_19;
  }
  hKey = 0;
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &hKey);
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  v13 = 0;
  if ( v12 >= 0 )
    v13 = (int)hKey;
  Kerb3961::CipherPolicyImpl::LoadPolicyDword(a1, (_DWORD)a2, a3, v13, 1);
  if ( hKey )
    RegCloseKey(hKey);
  return a2;
}

```

## disassembly

```asm
0x18000c944  push    rbp
0x18000c946  push    rbx
0x18000c947  push    rsi
0x18000c948  push    rdi
0x18000c949  mov     rbp, rsp
0x18000c94c  sub     rsp, 48h
0x18000c950  mov     rax, r9
0x18000c953  mov     rdi, r8
0x18000c956  mov     rbx, rdx
0x18000c959  mov     rsi, rcx
0x18000c95c  test    r9, r9
0x18000c95f  jz      short loc_18000C9AD
0x18000c961  mov     rdx, [rdi]; lpValueName
0x18000c964  lea     rcx, [rbp+cbData]
0x18000c968  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x18000c96d  lea     r9, [rbp+hKey]; lpType
0x18000c971  lea     rcx, [rbp+Data]
0x18000c975  mov     dword ptr [rbp+hKey], 0
0x18000c97c  mov     [rsp+48h+lpData], rcx; lpData
0x18000c981  xor     r8d, r8d; lpReserved
0x18000c984  mov     rcx, rax; hKey
0x18000c987  mov     dword ptr [rbp+Data], 0
0x18000c98e  mov     [rbp+cbData], 4
0x18000c995  call    cs:__imp_RegQueryValueExW
0x18000c99b  cmp     eax, 2
0x18000c99e  jnz     loc_18000CA25
0x18000c9a4  mov     rcx, [rdi+8]
0x18000c9a8  mov     eax, [rdi+10h]
0x18000c9ab  mov     [rcx], eax
0x18000c9ad  mov     rdx, [rdi+18h]; lpSubKey
0x18000c9b1  test    rdx, rdx
0x18000c9b4  jz      loc_18000CA58
0x18000c9ba  cmp     [rbp+arg_20], 0
0x18000c9be  jnz     loc_18000CA58
0x18000c9c4  lea     rax, [rbp+hKey]
0x18000c9c8  mov     [rbp+hKey], 0
0x18000c9d0  mov     r9d, 20019h; samDesired
0x18000c9d6  mov     [rsp+48h+lpData], rax; phkResult
0x18000c9db  xor     r8d, r8d; ulOptions
0x18000c9de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c9e5  call    cs:__imp_RegOpenKeyExW
0x18000c9eb  test    eax, eax
0x18000c9ed  jle     short loc_18000C9F7
0x18000c9ef  movzx   eax, ax
0x18000c9f2  or      eax, 80070000h
0x18000c9f7  xor     r9d, r9d
0x18000c9fa  mov     byte ptr [rsp+48h+lpData], 1
0x18000c9ff  test    eax, eax
0x18000ca01  mov     r8, rdi
0x18000ca04  mov     rdx, rbx
0x18000ca07  mov     rcx, rsi
0x18000ca0a  cmovns  r9, [rbp+hKey]
0x18000ca0f  call    ?LoadPolicyDword@CipherPolicyImpl@Kerb3961@@QEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUDwordPolicyValue@2@PEAUHKEY__@@_N@Z; Kerb3961::CipherPolicyImpl::LoadPolicyDword(Kerb3961::DwordPolicyValue const &,HKEY__ *,bool)
0x18000ca14  mov     rcx, [rbp+hKey]; hKey
0x18000ca18  test    rcx, rcx
0x18000ca1b  jz      short loc_18000CA67
0x18000ca1d  call    cs:__imp_RegCloseKey
0x18000ca23  jmp     short loc_18000CA67
0x18000ca25  test    eax, eax
0x18000ca27  jnz     short loc_18000CA50
0x18000ca29  cmp     dword ptr [rbp+hKey], 4
0x18000ca2d  jnz     short loc_18000CA50
0x18000ca2f  cmp     [rbp+cbData], 4
0x18000ca33  jnz     short loc_18000CA50
0x18000ca35  mov     rdx, [rdi+8]
0x18000ca39  mov     rcx, [rdi]; this
0x18000ca3c  mov     edx, [rdx]; unsigned __int16 *
0x18000ca3e  call    ?PolicyConfiguration@Telemetry@Kerb3961@@YAXPEBGI@Z; Kerb3961::Telemetry::PolicyConfiguration(ushort const *,uint)
0x18000ca43  mov     eax, dword ptr [rbp+Data]
0x18000ca46  mov     rcx, [rdi+8]
0x18000ca4a  test    eax, eax
0x18000ca4c  jnz     short loc_18000CA5F
0x18000ca4e  jmp     short loc_18000CA5C
0x18000ca50  mov     dword ptr [rbx], 0C000090Bh
0x18000ca56  jmp     short loc_18000CA67
0x18000ca58  mov     rcx, [rdi+8]
0x18000ca5c  mov     eax, [rdi+10h]
0x18000ca5f  mov     [rcx], eax
0x18000ca61  mov     dword ptr [rbx], 0
0x18000ca67  mov     rax, rbx
0x18000ca6a  add     rsp, 48h
0x18000ca6e  pop     rdi
0x18000ca6f  pop     rsi
0x18000ca70  pop     rbx
0x18000ca71  pop     rbp
0x18000ca72  retn
```
