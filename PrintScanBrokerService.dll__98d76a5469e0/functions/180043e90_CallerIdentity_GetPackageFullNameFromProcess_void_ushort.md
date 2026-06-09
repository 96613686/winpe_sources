# CallerIdentity::GetPackageFullNameFromProcess(void *,ushort * *)

- ea: `0x180043e90`
- end: `0x180043f54`
- name: `?GetPackageFullNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043e20`

## callees

- `0x1800432dc`
- `0x180043e90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043f3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043f3f`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x180043eb9`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x180043f1b`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x180043eb9`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x180043f1b`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageFullNameFromProcess(HANDLE hProcess, PWSTR *a2, unsigned __int16 **a3)
{
  LONG v5; // eax
  signed int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  PWSTR v10; // rbx
  LONG v11; // eax
  PWSTR v12; // rax
  UINT32 packageFullNameLength; // [rsp+58h] [rbp+10h] BYREF
  PWSTR packageFullName; // [rsp+60h] [rbp+18h]

  *a2 = 0;
  packageFullNameLength = 0;
  v5 = GetPackageFullName(hProcess, &packageFullNameLength, 0);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 == -2147024774 && packageFullNameLength )
  {
    packageFullName = 0;
    CoTaskMemFree(0);
    v9 = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, 0, packageFullNameLength);
    v10 = packageFullName;
    v6 = v9;
    if ( v9 >= 0 )
    {
      v11 = GetPackageFullName(hProcess, &packageFullNameLength, packageFullName);
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
0x180043e90  mov     [rsp+arg_0], rbx
0x180043e95  push    rbp
0x180043e96  push    rsi
0x180043e97  push    rdi
0x180043e98  sub     rsp, 30h
0x180043e9c  mov     rsi, rdx
0x180043e9f  mov     qword ptr [rdx], 0
0x180043ea6  lea     rdx, [rsp+48h+packageFullNameLength]; packageFullNameLength
0x180043eab  mov     [rsp+48h+packageFullNameLength], 0
0x180043eb3  xor     r8d, r8d; packageFullName
0x180043eb6  mov     rbp, rcx
0x180043eb9  call    cs:__imp_GetPackageFullName
0x180043ebf  mov     edi, eax
0x180043ec1  test    eax, eax
0x180043ec3  jle     short loc_180043ECE
0x180043ec5  movzx   edi, ax
0x180043ec8  or      edi, 80070000h
0x180043ece  cmp     edi, 8007007Ah
0x180043ed4  jnz     short loc_180043F45
0x180043ed6  cmp     [rsp+48h+packageFullNameLength], 0
0x180043edb  jbe     short loc_180043F45
0x180043edd  xor     ecx, ecx; pv
0x180043edf  mov     [rsp+48h+packageFullName], 0
0x180043ee8  call    cs:__imp_CoTaskMemFree
0x180043eee  mov     r9d, [rsp+48h+packageFullNameLength]
0x180043ef3  lea     rax, [rsp+48h+packageFullName]
0x180043ef8  xor     r8d, r8d
0x180043efb  mov     [rsp+48h+var_20], rax
0x180043f00  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180043f05  mov     rbx, [rsp+48h+packageFullName]
0x180043f0a  mov     edi, eax
0x180043f0c  test    eax, eax
0x180043f0e  js      short loc_180043F3C
0x180043f10  mov     r8, rbx; packageFullName
0x180043f13  lea     rdx, [rsp+48h+packageFullNameLength]; packageFullNameLength
0x180043f18  mov     rcx, rbp; hProcess
0x180043f1b  call    cs:__imp_GetPackageFullName
0x180043f21  mov     edi, eax
0x180043f23  test    eax, eax
0x180043f25  jle     short loc_180043F30
0x180043f27  movzx   edi, ax
0x180043f2a  or      edi, 80070000h
0x180043f30  test    edi, edi
0x180043f32  js      short loc_180043F3C
0x180043f34  mov     rax, rbx
0x180043f37  xor     ebx, ebx
0x180043f39  mov     [rsi], rax
0x180043f3c  mov     rcx, rbx; pv
0x180043f3f  call    cs:__imp_CoTaskMemFree
0x180043f45  mov     rbx, [rsp+48h+arg_0]
0x180043f4a  mov     eax, edi
0x180043f4c  add     rsp, 30h
0x180043f50  pop     rdi
0x180043f51  pop     rsi
0x180043f52  pop     rbp
0x180043f53  retn
```
