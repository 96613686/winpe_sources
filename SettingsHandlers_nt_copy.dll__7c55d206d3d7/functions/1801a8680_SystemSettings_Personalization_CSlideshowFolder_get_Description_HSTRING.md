# SystemSettings::Personalization::CSlideshowFolder::get_Description(HSTRING__ * *)

- ea: `0x1801a8680`
- end: `0x1801a8790`
- name: `?get_Description@CSlideshowFolder@Personalization@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `272`
- prototype: `int(SystemSettings::Personalization::CSlideshowFolder *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1801a8680`
- `0x180221f9c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801a86de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801a86de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a872d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a872d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8776`
- `SHELL32!SHGetNameFromIDList` at `0x1801a86ac`
- `SHELL32!SHGetNameFromIDList` at `0x1801a8719`
- `SHELL32!SHGetNameFromIDList` at `0x1801a86ac`
- `SHELL32!SHGetNameFromIDList` at `0x1801a8719`
- `SHELL32!__imp_ILFree` at `0x1801a8745`
- `SHELL32!__imp_ILFree` at `0x1801a8745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a8764`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a8764`

## pseudocode

```c
__int64 __fastcall SystemSettings::Personalization::CSlideshowFolder::get_Description(
        SystemSettings::Personalization::CSlideshowFolder *this,
        HSTRING *a2)
{
  __int64 v3; // rcx
  HRESULT String; // ebx
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  PWSTR ppszName; // [rsp+60h] [rbp+30h] BYREF
  LPCITEMIDLIST pidl; // [rsp+70h] [rbp+40h] BYREF
  PWSTR v13; // [rsp+78h] [rbp+48h] BYREF

  v3 = *((_QWORD *)this + 28);
  ppszName = 0;
  String = SHGetNameFromIDList(*(LPCITEMIDLIST *)(v3 + 8), SIGDN_NORMALDISPLAY, &ppszName);
  if ( String >= 0 )
  {
    v6 = -1;
    if ( CompareStringOrdinal(ppszName, -1, L"SkyDrive", -1, 1) == 2 )
    {
      v9 = *((_QWORD *)this + 28);
      pidl = 0;
      if ( (int)SimpleToRealIDListWithContext(v8, v7, *(_QWORD *)(v9 + 8), &pidl) >= 0 )
      {
        v13 = 0;
        if ( SHGetNameFromIDList(pidl, SIGDN_NORMALDISPLAY, &v13) >= 0 )
        {
          CoTaskMemFree(ppszName);
          ppszName = v13;
        }
        ILFree((LPITEMIDLIST)pidl);
      }
    }
    do
      ++v6;
    while ( ppszName[v6] );
    String = WindowsCreateString(ppszName, v6, a2);
    CoTaskMemFree(ppszName);
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1801a8680  push    rbp
0x1801a8682  push    rbx
0x1801a8683  push    rsi
0x1801a8684  push    rdi
0x1801a8685  push    r14
0x1801a8687  mov     rbp, rsp
0x1801a868a  sub     rsp, 30h
0x1801a868e  mov     rdi, rcx
0x1801a8691  lea     r8, [rbp+ppszName]; ppszName
0x1801a8695  mov     rcx, [rcx+0E0h]
0x1801a869c  mov     rsi, rdx
0x1801a869f  xor     r14d, r14d
0x1801a86a2  xor     edx, edx; sigdnName
0x1801a86a4  mov     [rbp+ppszName], r14
0x1801a86a8  mov     rcx, [rcx+8]; pidl
0x1801a86ac  call    cs:__imp_SHGetNameFromIDList
0x1801a86b3  nop     dword ptr [rax+rax+00h]
0x1801a86b8  mov     ebx, eax
0x1801a86ba  test    eax, eax
0x1801a86bc  js      loc_1801A8782
0x1801a86c2  mov     rcx, [rbp+ppszName]; lpString1
0x1801a86c6  lea     r8, aSkydrive; "SkyDrive"
0x1801a86cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801a86d1  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x1801a86d9  mov     r9d, ebx; cchCount2
0x1801a86dc  mov     edx, ebx; cchCount1
0x1801a86de  call    cs:__imp_CompareStringOrdinal
0x1801a86e5  nop     dword ptr [rax+rax+00h]
0x1801a86ea  cmp     eax, 2
0x1801a86ed  jnz     short loc_1801A8751
0x1801a86ef  mov     r8, [rdi+0E0h]
0x1801a86f6  lea     r9, [rbp+pidl]
0x1801a86fa  mov     [rbp+pidl], r14
0x1801a86fe  mov     r8, [r8+8]
0x1801a8702  call    SimpleToRealIDListWithContext
0x1801a8707  test    eax, eax
0x1801a8709  js      short loc_1801A8751
0x1801a870b  mov     rcx, [rbp+pidl]; pidl
0x1801a870f  lea     r8, [rbp+arg_18]; ppszName
0x1801a8713  xor     edx, edx; sigdnName
0x1801a8715  mov     [rbp+arg_18], r14
0x1801a8719  call    cs:__imp_SHGetNameFromIDList
0x1801a8720  nop     dword ptr [rax+rax+00h]
0x1801a8725  test    eax, eax
0x1801a8727  js      short loc_1801A8741
0x1801a8729  mov     rcx, [rbp+ppszName]; pv
0x1801a872d  call    cs:__imp_CoTaskMemFree
0x1801a8734  nop     dword ptr [rax+rax+00h]
0x1801a8739  mov     rax, [rbp+arg_18]
0x1801a873d  mov     [rbp+ppszName], rax
0x1801a8741  mov     rcx, [rbp+pidl]; pidl
0x1801a8745  call    cs:__imp_ILFree
0x1801a874c  nop     dword ptr [rax+rax+00h]
0x1801a8751  mov     rcx, [rbp+ppszName]; sourceString
0x1801a8755  inc     rbx
0x1801a8758  cmp     [rcx+rbx*2], r14w
0x1801a875d  jnz     short loc_1801A8755
0x1801a875f  mov     r8, rsi; string
0x1801a8762  mov     edx, ebx; length
0x1801a8764  call    cs:__imp_WindowsCreateString
0x1801a876b  nop     dword ptr [rax+rax+00h]
0x1801a8770  mov     rcx, [rbp+ppszName]; pv
0x1801a8774  mov     ebx, eax
0x1801a8776  call    cs:__imp_CoTaskMemFree
0x1801a877d  nop     dword ptr [rax+rax+00h]
0x1801a8782  mov     eax, ebx
0x1801a8784  add     rsp, 30h
0x1801a8788  pop     r14
0x1801a878a  pop     rdi
0x1801a878b  pop     rsi
0x1801a878c  pop     rbx
0x1801a878d  pop     rbp
0x1801a878e  retn
```
