# Microsoft::Resources::WindowsClientProfileBaseHelpers::OpenRegKeyForPackageName(ushort const *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180065f84`
- end: `0x18006605f`
- name: `?OpenRegKeyForPackageName@WindowsClientProfileBaseHelpers@Resources@Microsoft@@AEAAJPEBG0KPEAPEAUHKEY__@@@Z`
- size: `219`
- prototype: `int(Microsoft::Resources::WindowsClientProfileBaseHelpers *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a5c80`

## callees

- `0x18002c8d0`
- `0x180065f84`
- `0x180083978`
- `0x1800862f0`

## import_xrefs

- `KERNELBASE!PackageFamilyNameFromFullName` at `0x180065fcb`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x180065fcb`
- `profapi!__imp_GetAppContainerRegistryHandleFromName` at `0x180065fe7`
- `profapi!__imp_GetAppContainerRegistryHandleFromName` at `0x180065fe7`

## pseudocode

```c
unsigned int __fastcall Microsoft::Resources::WindowsClientProfileBaseHelpers::OpenRegKeyForPackageName(
        Microsoft::Resources::WindowsClientProfileBaseHelpers *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        HKEY *a5)
{
  unsigned int v7; // eax
  unsigned int result; // eax
  unsigned int v9; // ebx
  unsigned int v10; // [rsp+20h] [rbp-D8h]
  int v11; // [rsp+20h] [rbp-D8h]
  UINT32 packageFamilyNameLength[4]; // [rsp+30h] [rbp-C8h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+40h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  packageFamilyNameLength[0] = 65;
  *a5 = 0;
  v7 = PackageFamilyNameFromFullName(a2, packageFamilyNameLength, packageFamilyName);
  if ( v7 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x96B,
             (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
             (const char *)v7,
             v10);
  result = GetAppContainerRegistryHandleFromName(packageFamilyName, 0, a3, a4, a5);
  v9 = result;
  if ( (result & 0x80000000) == 0 )
    return 0;
  if ( result != -2147024894 && result != -2147024891 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x970,
      (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
      (const char *)result,
      v11);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180065f84  push    rbx
0x180065f86  push    rsi
0x180065f87  push    rdi
0x180065f88  sub     rsp, 0E0h
0x180065f8f  mov     rax, cs:__security_cookie
0x180065f96  xor     rax, rsp
0x180065f99  mov     [rsp+0F8h+var_28], rax
0x180065fa1  mov     rbx, [rsp+0F8h+arg_20]
0x180065fa9  mov     rdi, r8
0x180065fac  mov     rcx, rdx; packageFullName
0x180065faf  mov     [rsp+0F8h+packageFamilyNameLength], 41h ; 'A'
0x180065fb7  lea     r8, [rsp+0F8h+packageFamilyName]; packageFamilyName
0x180065fbc  mov     esi, r9d
0x180065fbf  lea     rdx, [rsp+0F8h+packageFamilyNameLength]; packageFamilyNameLength
0x180065fc4  mov     qword ptr [rbx], 0
0x180065fcb  call    cs:__imp_PackageFamilyNameFromFullName
0x180065fd1  test    eax, eax
0x180065fd3  jnz     short loc_180066015
0x180065fd5  mov     r9d, esi
0x180065fd8  mov     qword ptr [rsp+0F8h+var_D8], rbx; int
0x180065fdd  mov     r8, rdi
0x180065fe0  lea     rcx, [rsp+0F8h+packageFamilyName]
0x180065fe5  xor     edx, edx
0x180065fe7  call    cs:__imp_GetAppContainerRegistryHandleFromName
0x180065fed  mov     ebx, eax
0x180065fef  test    eax, eax
0x180065ff1  jns     short loc_180066033
0x180065ff3  cmp     eax, 80070002h
0x180065ff8  jnz     short loc_180066037
0x180065ffa  mov     rcx, [rsp+0F8h+var_28]
0x180066002  xor     rcx, rsp; StackCookie
0x180066005  call    __security_check_cookie
0x18006600a  add     rsp, 0E0h
0x180066011  pop     rdi
0x180066012  pop     rsi
0x180066013  pop     rbx
0x180066014  retn
0x180066015  mov     rcx, [rsp+0F8h]; this
0x18006601d  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x180066024  mov     r9d, eax; char *
0x180066027  mov     edx, 96Bh; void *
0x18006602c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180066031  jmp     short loc_180065FFA
0x180066033  xor     eax, eax
0x180066035  jmp     short loc_180065FFA
0x180066037  cmp     ebx, 80070005h
0x18006603d  jz      short loc_180065FFA
0x18006603f  mov     rcx, [rsp+0F8h]; this
0x180066047  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18006604e  mov     r9d, ebx; char *
0x180066051  mov     edx, 970h; void *
0x180066056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006605b  mov     eax, ebx
0x18006605d  jmp     short loc_180065FFA
```
