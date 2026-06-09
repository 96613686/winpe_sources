# SRPkgExtensionIteratorContext::PackageVersionFromPackageFullName(ushort const *,unsigned __int64 &)

- ea: `0x180017f58`
- end: `0x180017ffd`
- name: `?PackageVersionFromPackageFullName@SRPkgExtensionIteratorContext@@CAJPEBGAEA_K@Z`
- size: `165`
- prototype: `__int64 __fastcall(PCWSTR packageFullName, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001757c`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x180017f58`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180017fa6`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180017fa6`

## string_xrefs

- `0x180017fba`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_pkgextension.cpp`

## pseudocode

```c
__int64 __fastcall SRPkgExtensionIteratorContext::PackageVersionFromPackageFullName(
        PCWSTR packageFullName,
        unsigned __int64 *a2)
{
  LONG v4; // eax
  unsigned int v5; // ebx
  UINT32 bufferLength[4]; // [rsp+20h] [rbp-118h] BYREF
  BYTE buffer[8]; // [rsp+30h] [rbp-108h] BYREF
  unsigned __int64 v9; // [rsp+38h] [rbp-100h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  memset_0(buffer, 0, 0xF0u);
  bufferLength[0] = 240;
  v4 = PackageIdFromFullName(packageFullName, 0, bufferLength, buffer);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *a2 = v9;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_pkgextension.cpp",
      (const char *)(unsigned int)v4,
      bufferLength[0]);
    return v5;
  }
}

```

## disassembly

```asm
0x180017f58  mov     [rsp+arg_10], rbx
0x180017f5d  push    rdi
0x180017f5e  sub     rsp, 130h
0x180017f65  mov     rax, cs:__security_cookie
0x180017f6c  xor     rax, rsp
0x180017f6f  mov     [rsp+138h+var_18], rax
0x180017f77  mov     rdi, rdx
0x180017f7a  mov     rbx, rcx
0x180017f7d  xor     edx, edx; Val
0x180017f7f  lea     rcx, [rsp+138h+buffer]; void *
0x180017f84  mov     r8d, 0F0h; Size
0x180017f8a  call    memset_0
0x180017f8f  lea     r9, [rsp+138h+buffer]; buffer
0x180017f94  mov     [rsp+138h+bufferLength], 0F0h; int
0x180017f9c  lea     r8, [rsp+138h+bufferLength]; bufferLength
0x180017fa1  xor     edx, edx; flags
0x180017fa3  mov     rcx, rbx; packageFullName
0x180017fa6  call    cs:__imp_PackageIdFromFullName
0x180017fac  mov     ebx, eax
0x180017fae  test    eax, eax
0x180017fb0  jns     short loc_180017FD2
0x180017fb2  mov     rcx, [rsp+138h]; this
0x180017fba  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x180017fc1  mov     r9d, eax; char *
0x180017fc4  mov     edx, 0BCh; void *
0x180017fc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fce  mov     eax, ebx
0x180017fd0  jmp     short loc_180017FDC
0x180017fd2  mov     rax, [rsp+138h+var_100]
0x180017fd7  mov     [rdi], rax
0x180017fda  xor     eax, eax
0x180017fdc  mov     rcx, [rsp+138h+var_18]
0x180017fe4  xor     rcx, rsp; StackCookie
0x180017fe7  call    __security_check_cookie
0x180017fec  mov     rbx, [rsp+138h+arg_10]
0x180017ff4  add     rsp, 130h
0x180017ffb  pop     rdi
0x180017ffc  retn
```
