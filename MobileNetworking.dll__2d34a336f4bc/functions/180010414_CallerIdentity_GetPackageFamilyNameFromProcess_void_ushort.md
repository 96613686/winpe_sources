# CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)

- ea: `0x180010414`
- end: `0x1800104d5`
- name: `?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `193`
- prototype: `__int64 __fastcall(HANDLE hProcess, PWSTR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e1e8`

## callees

- `0x18000fa4c`
- `0x180010414`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001046c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001046c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104c0`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001043d`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001049c`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001043d`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001049c`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageFamilyNameFromProcess(HANDLE hProcess, PWSTR *a2, unsigned __int16 **a3)
{
  LONG v5; // eax
  signed int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  PWSTR v11; // rbx
  LONG v12; // eax
  PWSTR v13; // rax
  UINT32 packageFamilyNameLength; // [rsp+58h] [rbp+10h] BYREF
  PWSTR packageFamilyName; // [rsp+60h] [rbp+18h]

  *a2 = 0;
  packageFamilyNameLength = 0;
  v5 = GetPackageFamilyName(hProcess, &packageFamilyNameLength, 0);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 == -2147024774 && packageFamilyNameLength )
  {
    packageFamilyName = 0;
    CoTaskMemFree(0);
    v10 = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, v9, packageFamilyNameLength);
    v11 = packageFamilyName;
    v6 = v10;
    if ( v10 >= 0 )
    {
      v12 = GetPackageFamilyName(hProcess, &packageFamilyNameLength, packageFamilyName);
      v6 = v12;
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
      if ( v6 >= 0 )
      {
        v13 = v11;
        v11 = 0;
        *a2 = v13;
      }
    }
    CoTaskMemFree(v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010414  mov     [rsp+arg_0], rbx
0x180010419  push    rbp
0x18001041a  push    rsi
0x18001041b  push    rdi
0x18001041c  sub     rsp, 30h
0x180010420  mov     rsi, rdx
0x180010423  mov     qword ptr [rdx], 0
0x18001042a  lea     rdx, [rsp+48h+packageFamilyNameLength]; packageFamilyNameLength
0x18001042f  mov     [rsp+48h+packageFamilyNameLength], 0
0x180010437  xor     r8d, r8d; packageFamilyName
0x18001043a  mov     rbp, rcx
0x18001043d  call    cs:__imp_GetPackageFamilyName
0x180010443  mov     edi, eax
0x180010445  test    eax, eax
0x180010447  jle     short loc_180010452
0x180010449  movzx   edi, ax
0x18001044c  or      edi, 80070000h
0x180010452  cmp     edi, 8007007Ah
0x180010458  jnz     short loc_1800104C6
0x18001045a  cmp     [rsp+48h+packageFamilyNameLength], 0
0x18001045f  jbe     short loc_1800104C6
0x180010461  xor     ecx, ecx; pv
0x180010463  mov     [rsp+48h+packageFamilyName], 0
0x18001046c  call    cs:__imp_CoTaskMemFree
0x180010472  mov     r9d, [rsp+48h+packageFamilyNameLength]
0x180010477  lea     rax, [rsp+48h+packageFamilyName]
0x18001047c  mov     [rsp+48h+var_20], rax
0x180010481  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180010486  mov     rbx, [rsp+48h+packageFamilyName]
0x18001048b  mov     edi, eax
0x18001048d  test    eax, eax
0x18001048f  js      short loc_1800104BD
0x180010491  mov     r8, rbx; packageFamilyName
0x180010494  lea     rdx, [rsp+48h+packageFamilyNameLength]; packageFamilyNameLength
0x180010499  mov     rcx, rbp; hProcess
0x18001049c  call    cs:__imp_GetPackageFamilyName
0x1800104a2  mov     edi, eax
0x1800104a4  test    eax, eax
0x1800104a6  jle     short loc_1800104B1
0x1800104a8  movzx   edi, ax
0x1800104ab  or      edi, 80070000h
0x1800104b1  test    edi, edi
0x1800104b3  js      short loc_1800104BD
0x1800104b5  mov     rax, rbx
0x1800104b8  xor     ebx, ebx
0x1800104ba  mov     [rsi], rax
0x1800104bd  mov     rcx, rbx; pv
0x1800104c0  call    cs:__imp_CoTaskMemFree
0x1800104c6  mov     rbx, [rsp+48h+arg_0]
0x1800104cb  mov     eax, edi
0x1800104cd  add     rsp, 30h
0x1800104d1  pop     rdi
0x1800104d2  pop     rsi
0x1800104d3  pop     rbp
0x1800104d4  retn
```
