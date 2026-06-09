# BypassServiceResponse(ushort const *)

- ea: `0x180006f7c`
- end: `0x18000700f`
- name: `?BypassServiceResponse@@YA_NPEBG@Z`
- size: `147`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f060`
- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`

## callees

- `0x180006f7c`
- `0x18000eaec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006fca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006fca`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x180006ff6`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x180006ff6`

## pseudocode

```c
bool __fastcall BypassServiceResponse(const unsigned __int16 *a1)
{
  LONG StagedPackageOrigin; // eax
  int v4; // [rsp+58h] [rbp+10h] BYREF
  PackageOrigin origin; // [rsp+60h] [rbp+18h] BYREF
  DWORD v6; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  v6 = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Store",
          L"ApiBypass",
          0x18u,
          0,
          &v4,
          &v6)
    && v4
    || ShouldSkipPackage(a1)
    || (origin = PackageOrigin_Unknown, (StagedPackageOrigin = GetStagedPackageOrigin(a1, &origin)) != 0)
    || origin != PackageOrigin_Store )
  {
    LOBYTE(StagedPackageOrigin) = 1;
  }
  return StagedPackageOrigin;
}

```

## disassembly

```asm
0x180006f7c  mov     r11, rsp
0x180006f7f  push    rbx
0x180006f80  sub     rsp, 40h
0x180006f84  lea     rax, [r11+20h]
0x180006f88  mov     [rsp+48h+arg_8], 0
0x180006f90  mov     [r11-18h], rax
0x180006f94  lea     r8, Value; "ApiBypass"
0x180006f9b  lea     rax, [r11+10h]
0x180006f9f  mov     [rsp+48h+arg_18], 4
0x180006fa7  mov     rbx, rcx
0x180006faa  mov     [r11-20h], rax
0x180006fae  mov     r9d, 18h; dwFlags
0x180006fb4  mov     qword ptr [r11-28h], 0
0x180006fbc  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180006fc3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180006fca  call    cs:__imp_RegGetValueW
0x180006fd0  test    eax, eax
0x180006fd2  jnz     short loc_180006FDA
0x180006fd4  cmp     [rsp+48h+arg_8], eax
0x180006fd8  jnz     short loc_180007007
0x180006fda  mov     rcx, rbx; unsigned __int16 *
0x180006fdd  call    ?ShouldSkipPackage@@YA_NPEBG@Z; ShouldSkipPackage(ushort const *)
0x180006fe2  test    al, al
0x180006fe4  jnz     short loc_180007007
0x180006fe6  lea     rdx, [rsp+48h+origin]; origin
0x180006feb  mov     [rsp+48h+origin], 0
0x180006ff3  mov     rcx, rbx; packageFullName
0x180006ff6  call    cs:__imp_GetStagedPackageOrigin
0x180006ffc  test    eax, eax
0x180006ffe  jnz     short loc_180007007
0x180007000  cmp     [rsp+48h+origin], 3
0x180007005  jz      short loc_180007009
0x180007007  mov     al, 1
0x180007009  add     rsp, 40h
0x18000700d  pop     rbx
0x18000700e  retn
```
