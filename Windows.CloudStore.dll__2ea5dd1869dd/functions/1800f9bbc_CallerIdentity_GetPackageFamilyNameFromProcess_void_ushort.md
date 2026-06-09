# CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)

- ea: `0x1800f9bbc`
- end: `0x1800f9c80`
- name: `?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f814`
- `0x180054d4c`
- `0x18005facc`

## callees

- `0x1800620a0`
- `0x1800f9bbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9c6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9c6b`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800f9be5`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800f9c47`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800f9be5`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800f9c47`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageFamilyNameFromProcess(HANDLE hProcess, PWSTR *a2, unsigned __int16 **a3)
{
  LONG v5; // eax
  signed int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  PWSTR v10; // rbx
  LONG v11; // eax
  PWSTR v12; // rax
  __int64 v14; // [rsp+20h] [rbp-28h]
  UINT32 packageFamilyNameLength; // [rsp+58h] [rbp+10h] BYREF
  PWSTR packageFamilyName; // [rsp+60h] [rbp+18h] BYREF

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
    v9 = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, 0, packageFamilyNameLength, v14, &packageFamilyName);
    v10 = packageFamilyName;
    v6 = v9;
    if ( v9 >= 0 )
    {
      v11 = GetPackageFamilyName(hProcess, &packageFamilyNameLength, packageFamilyName);
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      if ( v6 >= 0 )
      {
        v12 = v10;
        v10 = 0;
        *a2 = v12;
      }
    }
    CoTaskMemFree(v10);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800f9bbc  mov     [rsp+arg_0], rbx
0x1800f9bc1  push    rbp
0x1800f9bc2  push    rsi
0x1800f9bc3  push    rdi
0x1800f9bc4  sub     rsp, 30h
0x1800f9bc8  mov     rsi, rdx
0x1800f9bcb  mov     qword ptr [rdx], 0
0x1800f9bd2  lea     rdx, [rsp+48h+packageFamilyNameLength]; packageFamilyNameLength
0x1800f9bd7  mov     [rsp+48h+packageFamilyNameLength], 0
0x1800f9bdf  xor     r8d, r8d; packageFamilyName
0x1800f9be2  mov     rbp, rcx
0x1800f9be5  call    cs:__imp_GetPackageFamilyName
0x1800f9beb  mov     edi, eax
0x1800f9bed  test    eax, eax
0x1800f9bef  jle     short loc_1800F9BFA
0x1800f9bf1  movzx   edi, ax
0x1800f9bf4  or      edi, 80070000h
0x1800f9bfa  cmp     edi, 8007007Ah
0x1800f9c00  jnz     short loc_1800F9C71
0x1800f9c02  cmp     [rsp+48h+packageFamilyNameLength], 0
0x1800f9c07  jbe     short loc_1800F9C71
0x1800f9c09  xor     ecx, ecx; pv
0x1800f9c0b  mov     [rsp+48h+packageFamilyName], 0
0x1800f9c14  call    cs:__imp_CoTaskMemFree
0x1800f9c1a  mov     r9d, [rsp+48h+packageFamilyNameLength]
0x1800f9c1f  lea     rax, [rsp+48h+packageFamilyName]
0x1800f9c24  xor     r8d, r8d
0x1800f9c27  mov     [rsp+48h+var_20], rax
0x1800f9c2c  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800f9c31  mov     rbx, [rsp+48h+packageFamilyName]
0x1800f9c36  mov     edi, eax
0x1800f9c38  test    eax, eax
0x1800f9c3a  js      short loc_1800F9C68
0x1800f9c3c  mov     r8, rbx; packageFamilyName
0x1800f9c3f  lea     rdx, [rsp+48h+packageFamilyNameLength]; packageFamilyNameLength
0x1800f9c44  mov     rcx, rbp; hProcess
0x1800f9c47  call    cs:__imp_GetPackageFamilyName
0x1800f9c4d  mov     edi, eax
0x1800f9c4f  test    eax, eax
0x1800f9c51  jle     short loc_1800F9C5C
0x1800f9c53  movzx   edi, ax
0x1800f9c56  or      edi, 80070000h
0x1800f9c5c  test    edi, edi
0x1800f9c5e  js      short loc_1800F9C68
0x1800f9c60  mov     rax, rbx
0x1800f9c63  xor     ebx, ebx
0x1800f9c65  mov     [rsi], rax
0x1800f9c68  mov     rcx, rbx; pv
0x1800f9c6b  call    cs:__imp_CoTaskMemFree
0x1800f9c71  mov     rbx, [rsp+48h+arg_0]
0x1800f9c76  mov     eax, edi
0x1800f9c78  add     rsp, 30h
0x1800f9c7c  pop     rdi
0x1800f9c7d  pop     rsi
0x1800f9c7e  pop     rbp
0x1800f9c7f  retn
```
