# SupportedFileTypes::IsDirectoryOrParentHiddenOrSystem(ushort const *,bool *)

- ea: `0x18007231c`
- end: `0x1800723f3`
- name: `?IsDirectoryOrParentHiddenOrSystem@SupportedFileTypes@@SAJPEBGPEA_N@Z`
- size: `215`
- prototype: `__int64 __fastcall(LPCWSTR psz, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18002ed38`

## callees

- `0x18002fc0c`
- `0x18003f800`
- `0x18007231c`
- `0x180072604`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x180072396`
- `KERNEL32!GetFileAttributesExW` at `0x180072396`
- `ole32!CoTaskMemFree` at `0x1800723cd`
- `ole32!CoTaskMemFree` at `0x1800723cd`
- `SHLWAPI!PathIsRelativeW` at `0x180072345`
- `SHLWAPI!PathIsRelativeW` at `0x180072345`
- `SHLWAPI!PathIsRootW` at `0x1800723bf`
- `SHLWAPI!PathIsRootW` at `0x1800723bf`
- `SHLWAPI!SHStrDupW` at `0x180072365`
- `SHLWAPI!SHStrDupW` at `0x180072365`

## pseudocode

```c
__int64 __fastcall SupportedFileTypes::IsDirectoryOrParentHiddenOrSystem(LPCWSTR psz, bool *a2)
{
  HRESULT v5; // ebx
  const WCHAR *v6; // rcx
  HRESULT ResultFromKnownLastError; // eax
  LPWSTR ppwsz; // [rsp+20h] [rbp-40h] BYREF
  _OWORD FileInformation[2]; // [rsp+28h] [rbp-38h] BYREF
  int v10; // [rsp+48h] [rbp-18h]

  *a2 = 0;
  if ( PathIsRelativeW(psz) )
    return 2147942487LL;
  ppwsz = 0;
  v5 = SHStrDupW(psz, &ppwsz);
  if ( v5 >= 0 )
  {
    while ( !PathIsRootW(ppwsz) && !*a2 && v5 >= 0 )
    {
      v10 = 0;
      memset(FileInformation, 0, sizeof(FileInformation));
      if ( GetFileAttributesExW(ppwsz, GetFileExInfoStandard, FileInformation) )
      {
        v6 = ppwsz;
        *a2 = (FileInformation[0] & 6) != 0;
        ResultFromKnownLastError = SafePathRemoveFileSpec(v6);
      }
      else
      {
        ResultFromKnownLastError = GetResultFromKnownLastError();
      }
      v5 = ResultFromKnownLastError;
    }
    CoTaskMemFree(ppwsz);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007231c  mov     [rsp-8+arg_10], rbx
0x180072321  mov     [rsp-8+arg_18], rdi
0x180072326  push    rbp
0x180072327  mov     rbp, rsp
0x18007232a  sub     rsp, 60h
0x18007232e  mov     rax, cs:__security_cookie
0x180072335  xor     rax, rsp
0x180072338  mov     [rbp+var_10], rax
0x18007233c  mov     rdi, rdx
0x18007233f  mov     byte ptr [rdx], 0
0x180072342  mov     rbx, rcx
0x180072345  call    cs:__imp_PathIsRelativeW
0x18007234b  test    eax, eax
0x18007234d  jz      short loc_180072356
0x18007234f  mov     eax, 80070057h
0x180072354  jmp     short loc_1800723D5
0x180072356  lea     rdx, [rbp+ppwsz]; ppwsz
0x18007235a  mov     [rbp+ppwsz], 0
0x180072362  mov     rcx, rbx; psz
0x180072365  call    cs:__imp_SHStrDupW
0x18007236b  mov     ebx, eax
0x18007236d  test    eax, eax
0x18007236f  js      short loc_1800723D3
0x180072371  jmp     short loc_1800723BB
0x180072373  cmp     byte ptr [rdi], 0
0x180072376  jnz     short loc_1800723C9
0x180072378  test    ebx, ebx
0x18007237a  js      short loc_1800723C9
0x18007237c  mov     rcx, [rbp+ppwsz]; lpFileName
0x180072380  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180072384  xorps   xmm0, xmm0
0x180072387  xor     eax, eax
0x180072389  xor     edx, edx; fInfoLevelId
0x18007238b  mov     [rbp+var_18], eax
0x18007238e  movups  [rbp+FileInformation], xmm0
0x180072392  movups  [rbp+var_28], xmm0
0x180072396  call    cs:__imp_GetFileAttributesExW
0x18007239c  test    eax, eax
0x18007239e  jz      short loc_1800723B4
0x1800723a0  test    byte ptr [rbp+FileInformation], 6
0x1800723a4  mov     rcx, [rbp+ppwsz]; lpString
0x1800723a8  setnz   al
0x1800723ab  mov     [rdi], al
0x1800723ad  call    SafePathRemoveFileSpec
0x1800723b2  jmp     short loc_1800723B9
0x1800723b4  call    GetResultFromKnownLastError
0x1800723b9  mov     ebx, eax
0x1800723bb  mov     rcx, [rbp+ppwsz]; pszPath
0x1800723bf  call    cs:__imp_PathIsRootW
0x1800723c5  test    eax, eax
0x1800723c7  jz      short loc_180072373
0x1800723c9  mov     rcx, [rbp+ppwsz]; pv
0x1800723cd  call    cs:__imp_CoTaskMemFree
0x1800723d3  mov     eax, ebx
0x1800723d5  mov     rcx, [rbp+var_10]
0x1800723d9  xor     rcx, rsp; StackCookie
0x1800723dc  call    __security_check_cookie
0x1800723e1  lea     r11, [rsp+60h+var_s0]
0x1800723e6  mov     rbx, [r11+20h]
0x1800723ea  mov     rdi, [r11+28h]
0x1800723ee  mov     rsp, r11
0x1800723f1  pop     rbp
0x1800723f2  retn
```
