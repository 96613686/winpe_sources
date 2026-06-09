# CLSIDToMultibyteString

- ea: `0x1800375c8`
- end: `0x180037674`
- name: `CLSIDToMultibyteString`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003776c`

## callees

- `0x180023dd0`
- `0x1800375c8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180037651`
- `ole32!CoTaskMemFree` at `0x180037651`
- `ole32!StringFromCLSID` at `0x1800375ff`
- `ole32!StringFromCLSID` at `0x1800375ff`
- `KERNEL32!WideCharToMultiByte` at `0x180037637`
- `KERNEL32!WideCharToMultiByte` at `0x180037637`

## pseudocode

```c
HRESULT __fastcall CLSIDToMultibyteString(IID *a1, CHAR *a2)
{
  IID v2; // xmm0
  HRESULT result; // eax
  int v5; // ebx
  LPCWCH lpWideCharStr; // [rsp+40h] [rbp-38h] BYREF
  IID v7; // [rsp+50h] [rbp-28h] BYREF

  v2 = *a1;
  lpWideCharStr = 0;
  v7 = v2;
  result = StringFromCLSID(&v7, (LPOLESTR *)&lpWideCharStr);
  v5 = result;
  if ( result >= 0 )
  {
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, a2, 50, 0, 0) )
      v5 = -2147467259;
    if ( lpWideCharStr )
      CoTaskMemFree((LPVOID)lpWideCharStr);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800375c8  mov     r11, rsp
0x1800375cb  mov     [r11+18h], rbx
0x1800375cf  push    rdi
0x1800375d0  sub     rsp, 70h
0x1800375d4  mov     rax, cs:__security_cookie
0x1800375db  xor     rax, rsp
0x1800375de  mov     [rsp+78h+var_18], rax
0x1800375e3  movups  xmm0, xmmword ptr [rcx]
0x1800375e6  mov     rdi, rdx
0x1800375e9  mov     qword ptr [r11-38h], 0
0x1800375f1  lea     rdx, [r11-38h]; lplpsz
0x1800375f5  lea     rcx, [r11-28h]; rclsid
0x1800375f9  movdqu  [rsp+78h+var_28], xmm0
0x1800375ff  call    cs:__imp_StringFromCLSID
0x180037605  mov     ebx, eax
0x180037607  test    eax, eax
0x180037609  js      short loc_180037659
0x18003760b  mov     r8, [rsp+78h+lpWideCharStr]; lpWideCharStr
0x180037610  or      r9d, 0FFFFFFFFh; cchWideChar
0x180037614  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18003761d  xor     edx, edx; dwFlags
0x18003761f  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180037628  xor     ecx, ecx; CodePage
0x18003762a  mov     [rsp+78h+cbMultiByte], 32h ; '2'; cbMultiByte
0x180037632  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x180037637  call    cs:__imp_WideCharToMultiByte
0x18003763d  test    eax, eax
0x18003763f  mov     ecx, 80004005h
0x180037644  cmovz   ebx, ecx
0x180037647  mov     rcx, [rsp+78h+lpWideCharStr]; pv
0x18003764c  test    rcx, rcx
0x18003764f  jz      short loc_180037657
0x180037651  call    cs:__imp_CoTaskMemFree
0x180037657  mov     eax, ebx
0x180037659  mov     rcx, [rsp+78h+var_18]
0x18003765e  xor     rcx, rsp; StackCookie
0x180037661  call    __security_check_cookie
0x180037666  mov     rbx, [rsp+78h+arg_10]
0x18003766e  add     rsp, 70h
0x180037672  pop     rdi
0x180037673  retn
```
