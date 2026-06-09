# RecursiveUtil::RemoveReadOnly(void *,ulong)

- ea: `0x18003be84`
- end: `0x18003bf2b`
- name: `?RemoveReadOnly@RecursiveUtil@@YAJPEAXK@Z`
- size: `167`
- prototype: `__int64 __fastcall(HANDLE hFile, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18003af94`

## callees

- `0x18000d030`
- `0x180012714`
- `0x18003be84`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003beea`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003beea`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003bec1`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003bec1`

## string_xrefs

- `0x18003befe`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`

## pseudocode

```c
__int64 __fastcall RecursiveUtil::RemoveReadOnly(HANDLE hFile, void *a2)
{
  char v2; // bl
  const char *v4; // r9
  _OWORD FileInformation[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v7 = 0;
  v2 = (char)a2;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandleEx(hFile, FileBasicInfo, FileInformation, 0x28u) )
    return 0;
  if ( (v7 & 1) == 0 )
    return 0;
  LODWORD(v7) = v7 & 0xFFFFFFFE;
  if ( SetFileInformationByHandle(hFile, FileBasicInfo, FileInformation, 0x28u) || (v2 & 4) != 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xD7,
             (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
             v4);
}

```

## disassembly

```asm
0x18003be84  mov     [rsp+arg_8], rbx
0x18003be89  push    rdi
0x18003be8a  sub     rsp, 50h
0x18003be8e  mov     rax, cs:__security_cookie
0x18003be95  xor     rax, rsp
0x18003be98  mov     [rsp+58h+var_10], rax
0x18003be9d  xor     eax, eax
0x18003be9f  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x18003bea4  xorps   xmm0, xmm0
0x18003bea7  mov     [rsp+58h+var_18], rax
0x18003beac  mov     ebx, edx
0x18003beae  mov     rdi, rcx
0x18003beb1  xor     edx, edx; FileInformationClass
0x18003beb3  lea     r9d, [rax+28h]; dwBufferSize
0x18003beb7  movups  [rsp+58h+FileInformation], xmm0
0x18003bebc  movups  [rsp+58h+var_28], xmm0
0x18003bec1  call    cs:__imp_GetFileInformationByHandleEx
0x18003bec7  test    eax, eax
0x18003bec9  jz      short loc_18003BF11
0x18003becb  mov     eax, dword ptr [rsp+58h+var_18]
0x18003becf  test    al, 1
0x18003bed1  jz      short loc_18003BF11
0x18003bed3  and     eax, 0FFFFFFFEh
0x18003bed6  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x18003bedb  mov     r9d, 28h ; '('; dwBufferSize
0x18003bee1  mov     dword ptr [rsp+58h+var_18], eax
0x18003bee5  xor     edx, edx; FileInformationClass
0x18003bee7  mov     rcx, rdi; hFile
0x18003beea  call    cs:__imp_SetFileInformationByHandle
0x18003bef0  test    eax, eax
0x18003bef2  jnz     short loc_18003BF11
0x18003bef4  test    bl, 4
0x18003bef7  jnz     short loc_18003BF11
0x18003bef9  mov     rcx, [rsp+58h]; this
0x18003befe  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003bf05  mov     edx, 0D7h; void *
0x18003bf0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003bf0f  jmp     short loc_18003BF13
0x18003bf11  xor     eax, eax
0x18003bf13  mov     rcx, [rsp+58h+var_10]
0x18003bf18  xor     rcx, rsp; StackCookie
0x18003bf1b  call    __security_check_cookie
0x18003bf20  mov     rbx, [rsp+58h+arg_8]
0x18003bf25  add     rsp, 50h
0x18003bf29  pop     rdi
0x18003bf2a  retn
```
