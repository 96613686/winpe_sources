# CallerIdentity::GetCallingProcessPackageInstallPath(ushort * *)

- ea: `0x1800274a4`
- end: `0x18002756c`
- name: `?GetCallingProcessPackageInstallPath@CallerIdentity@@YAJPEAPEAG@Z`
- size: `200`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001bad0`

## callees

- `0x180002dc0`
- `0x180003bd8`
- `0x1800272a8`
- `0x1800273b0`
- `0x1800274a4`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1800274fe`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1800274fe`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessPackageInstallPath(CallerIdentity *this, unsigned __int8 **a2)
{
  signed int CallingProcessPackageId; // ebx
  LONG PackagePath; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r9
  UINT32 pathLength; // [rsp+30h] [rbp-238h] BYREF
  PACKAGE_ID *packageId; // [rsp+38h] [rbp-230h] BYREF
  WCHAR path[264]; // [rsp+40h] [rbp-228h] BYREF

  *(_QWORD *)this = 0;
  packageId = 0;
  CallingProcessPackageId = CallerIdentity::GetCallingProcessPackageId((CallerIdentity *)&packageId, a2);
  if ( CallingProcessPackageId >= 0 )
  {
    pathLength = 260;
    PackagePath = GetPackagePath(packageId, 0, &pathLength, path);
    CallingProcessPackageId = PackagePath;
    if ( PackagePath > 0 )
      CallingProcessPackageId = (unsigned __int16)PackagePath | 0x80070000;
    if ( CallingProcessPackageId >= 0 )
    {
      v6 = -1;
      do
        ++v6;
      while ( path[v6] );
      CallingProcessPackageId = _AllocStringWorker<CTCoAllocPolicy>(v5, v4, path);
    }
  }
  CoTaskMemFree_0(packageId);
  return (unsigned int)CallingProcessPackageId;
}

```

## disassembly

```asm
0x1800274a4  mov     [rsp+arg_8], rbx
0x1800274a9  mov     [rsp+arg_10], rsi
0x1800274ae  push    rdi
0x1800274af  sub     rsp, 260h
0x1800274b6  mov     rax, cs:__security_cookie
0x1800274bd  xor     rax, rsp
0x1800274c0  mov     [rsp+268h+var_18], rax
0x1800274c8  xor     esi, esi
0x1800274ca  mov     rdi, rcx
0x1800274cd  mov     [rcx], rsi
0x1800274d0  lea     rcx, [rsp+268h+packageId]; this
0x1800274d5  mov     [rsp+268h+packageId], rsi
0x1800274da  call    ?GetCallingProcessPackageId@CallerIdentity@@YAJPEAPEAE@Z; CallerIdentity::GetCallingProcessPackageId(uchar * *)
0x1800274df  mov     ebx, eax
0x1800274e1  test    eax, eax
0x1800274e3  js      short loc_18002753B
0x1800274e5  mov     rcx, [rsp+268h+packageId]; packageId
0x1800274ea  lea     r9, [rsp+268h+path]; path
0x1800274ef  lea     r8, [rsp+268h+pathLength]; pathLength
0x1800274f4  mov     [rsp+268h+pathLength], 104h
0x1800274fc  xor     edx, edx; reserved
0x1800274fe  call    cs:__imp_GetPackagePath
0x180027504  mov     ebx, eax
0x180027506  test    eax, eax
0x180027508  jle     short loc_180027513
0x18002750a  movzx   ebx, ax
0x18002750d  or      ebx, 80070000h
0x180027513  test    ebx, ebx
0x180027515  js      short loc_18002753B
0x180027517  lea     rax, [rsp+268h+path]
0x18002751c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180027520  inc     r9
0x180027523  cmp     [rax+r9*2], si
0x180027528  jnz     short loc_180027520
0x18002752a  lea     r8, [rsp+268h+path]
0x18002752f  mov     [rsp+268h+var_240], rdi
0x180027534  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180027539  mov     ebx, eax
0x18002753b  mov     rcx, [rsp+268h+packageId]; pv
0x180027540  call    CoTaskMemFree_0
0x180027545  mov     eax, ebx
0x180027547  mov     rcx, [rsp+268h+var_18]
0x18002754f  xor     rcx, rsp; StackCookie
0x180027552  call    __security_check_cookie
0x180027557  lea     r11, [rsp+268h+var_8]
0x18002755f  mov     rbx, [r11+18h]
0x180027563  mov     rsi, [r11+20h]
0x180027567  mov     rsp, r11
0x18002756a  pop     rdi
0x18002756b  retn
```
