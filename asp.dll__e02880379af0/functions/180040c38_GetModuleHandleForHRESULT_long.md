# GetModuleHandleForHRESULT(long)

- ea: `0x180040c38`
- end: `0x180040cdc`
- name: `?GetModuleHandleForHRESULT@@YAPEAUHINSTANCE__@@J@Z`
- size: `164`
- prototype: `HINSTANCE __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180040d6c`

## callees

- `0x180023dd0`
- `0x180040c38`

## import_xrefs

- `msvcrt!strcat_s` at `0x180040c7a`
- `msvcrt!strcat_s` at `0x180040ca4`
- `msvcrt!strcat_s` at `0x180040c7a`
- `msvcrt!strcat_s` at `0x180040ca4`
- `KERNEL32!LoadLibraryExA` at `0x180040cb5`
- `KERNEL32!LoadLibraryExA` at `0x180040cb5`

## string_xrefs

- `0x180040c8b`: `METADATA.DLL`
- `0x180040c9d`: `ASP.DLL`

## pseudocode

```c
HINSTANCE __fastcall GetModuleHandleForHRESULT(int a1)
{
  const char *v2; // r8
  char Destination[272]; // [rsp+20h] [rbp-128h] BYREF

  Destination[0] = 0;
  if ( g_fOOP )
    strcat_s(Destination, 0x104u, "INETSRV\\");
  v2 = "METADATA.DLL";
  if ( (a1 & 0x1FFF0000) != 0xC0000 )
    v2 = "ASP.DLL";
  strcat_s(Destination, 0x104u, v2);
  return LoadLibraryExA(Destination, 0, 2u);
}

```

## disassembly

```asm
0x180040c38  mov     [rsp+arg_0], rbx
0x180040c3d  push    rdi
0x180040c3e  sub     rsp, 140h
0x180040c45  mov     rax, cs:__security_cookie
0x180040c4c  xor     rax, rsp
0x180040c4f  mov     [rsp+148h+var_18], rax
0x180040c57  cmp     cs:?g_fOOP@@3HA, 0; int g_fOOP
0x180040c5e  mov     ebx, ecx
0x180040c60  mov     [rsp+148h+Destination], 0
0x180040c65  mov     edi, 104h
0x180040c6a  jz      short loc_180040C80
0x180040c6c  lea     r8, aInetsrv; "INETSRV\\"
0x180040c73  mov     edx, edi; SizeInBytes
0x180040c75  lea     rcx, [rsp+148h+Destination]; Destination
0x180040c7a  call    cs:__imp_strcat_s
0x180040c80  and     ebx, 1FFF0000h
0x180040c86  lea     rcx, [rsp+148h+Destination]; Destination
0x180040c8b  lea     r8, aMetadataDll; "METADATA.DLL"
0x180040c92  mov     rdx, rdi; SizeInBytes
0x180040c95  cmp     ebx, 0C0000h
0x180040c9b  jz      short loc_180040CA4
0x180040c9d  lea     r8, aAspDll_0; "ASP.DLL"
0x180040ca4  call    cs:__imp_strcat_s
0x180040caa  xor     edx, edx; hFile
0x180040cac  lea     rcx, [rsp+148h+Destination]; lpLibFileName
0x180040cb1  lea     r8d, [rdx+2]; dwFlags
0x180040cb5  call    cs:__imp_LoadLibraryExA
0x180040cbb  mov     rcx, [rsp+148h+var_18]
0x180040cc3  xor     rcx, rsp; StackCookie
0x180040cc6  call    __security_check_cookie
0x180040ccb  mov     rbx, [rsp+148h+arg_0]
0x180040cd3  add     rsp, 140h
0x180040cda  pop     rdi
0x180040cdb  retn
```
