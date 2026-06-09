# SRAppExtensionIteratorContext::PackageVersionFromPackageFullName(ushort const *,unsigned __int64 &)

- ea: `0x180014a40`
- end: `0x180014ae5`
- name: `?PackageVersionFromPackageFullName@SRAppExtensionIteratorContext@@CAJPEBGAEA_K@Z`
- size: `165`
- prototype: `__int64 __fastcall(PCWSTR packageFullName, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001384c`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x180014a40`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180014a8e`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180014a8e`

## string_xrefs

- `0x180014aa2`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_appextension.cpp`

## pseudocode

```c
__int64 __fastcall SRAppExtensionIteratorContext::PackageVersionFromPackageFullName(
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
      (void *)0xC5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_appextension.cpp",
      (const char *)(unsigned int)v4,
      bufferLength[0]);
    return v5;
  }
}

```

## disassembly

```asm
0x180014a40  mov     [rsp+arg_10], rbx
0x180014a45  push    rdi
0x180014a46  sub     rsp, 130h
0x180014a4d  mov     rax, cs:__security_cookie
0x180014a54  xor     rax, rsp
0x180014a57  mov     [rsp+138h+var_18], rax
0x180014a5f  mov     rdi, rdx
0x180014a62  mov     rbx, rcx
0x180014a65  xor     edx, edx; Val
0x180014a67  lea     rcx, [rsp+138h+buffer]; void *
0x180014a6c  mov     r8d, 0F0h; Size
0x180014a72  call    memset_0
0x180014a77  lea     r9, [rsp+138h+buffer]; buffer
0x180014a7c  mov     [rsp+138h+bufferLength], 0F0h; int
0x180014a84  lea     r8, [rsp+138h+bufferLength]; bufferLength
0x180014a89  xor     edx, edx; flags
0x180014a8b  mov     rcx, rbx; packageFullName
0x180014a8e  call    cs:__imp_PackageIdFromFullName
0x180014a94  mov     ebx, eax
0x180014a96  test    eax, eax
0x180014a98  jns     short loc_180014ABA
0x180014a9a  mov     rcx, [rsp+138h]; this
0x180014aa2  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180014aa9  mov     r9d, eax; char *
0x180014aac  mov     edx, 0C5h; void *
0x180014ab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014ab6  mov     eax, ebx
0x180014ab8  jmp     short loc_180014AC4
0x180014aba  mov     rax, [rsp+138h+var_100]
0x180014abf  mov     [rdi], rax
0x180014ac2  xor     eax, eax
0x180014ac4  mov     rcx, [rsp+138h+var_18]
0x180014acc  xor     rcx, rsp; StackCookie
0x180014acf  call    __security_check_cookie
0x180014ad4  mov     rbx, [rsp+138h+arg_10]
0x180014adc  add     rsp, 130h
0x180014ae3  pop     rdi
0x180014ae4  retn
```
