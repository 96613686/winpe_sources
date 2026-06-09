# CreateKnownFolderPath(_GUID const &,ushort const *,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180004b80`
- end: `0x180004cb2`
- name: `?CreateKnownFolderPath@@YAJAEBU_GUID@@PEBGHAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(const KNOWNFOLDERID *, __int64, int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002cb0`
- `0x180004b80`
- `0x18000504c`

## import_xrefs

- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x180004c5e`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x180004c5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c9f`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180004bad`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180004bad`

## string_xrefs

- `0x180004c13`: `\Comms`

## pseudocode

```c
__int64 __fastcall CreateKnownFolderPath(const KNOWNFOLDERID *a1, __int64 a2, int a3, LPCWSTR *a4)
{
  HRESULT v8; // esi
  int v10; // eax
  unsigned int v11; // ebx
  PWSTR ppszPath; // [rsp+20h] [rbp-38h] BYREF

  ppszPath = 0;
  v8 = SHGetKnownFolderPath(a1, 0x4000u, 0, &ppszPath);
  if ( v8 >= 0 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             a4,
                             ppszPath)
      || (*(_QWORD *)&a1->Data1 == 0x4C9D71852856B913LL && *(_QWORD *)a1->Data4 == 0x143CA8691298CC9ALL
       || *(_QWORD *)&FOLDERID_LocalAppData.Data1 == *(_QWORD *)&a1->Data1
       && *(_QWORD *)FOLDERID_LocalAppData.Data4 == *(_QWORD *)a1->Data4)
      && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             a4,
                             L"\\Comms")
      || a2
      && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             a4,
                             a2) )
    {
      if ( ppszPath )
        CoTaskMemFree(ppszPath);
      return 2147942414LL;
    }
    else if ( !a3 || (v10 = SHCreateDirectoryExW(0, *a4, 0), v11 = v10, v10 == 183) || v10 == 80 || !v10 )
    {
      if ( ppszPath )
        CoTaskMemFree(ppszPath);
      return 0;
    }
    else
    {
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      if ( ppszPath )
        CoTaskMemFree(ppszPath);
      return v11;
    }
  }
  else
  {
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x180004b80  push    rbx
0x180004b82  push    rbp
0x180004b83  push    rsi
0x180004b84  push    rdi
0x180004b85  push    r14
0x180004b87  sub     rsp, 30h
0x180004b8b  mov     rdi, r9
0x180004b8e  mov     [rsp+58h+ppszPath], 0
0x180004b97  mov     r14d, r8d
0x180004b9a  lea     r9, [rsp+58h+ppszPath]; ppszPath
0x180004b9f  mov     rbp, rdx
0x180004ba2  xor     r8d, r8d; hToken
0x180004ba5  mov     edx, 4000h; dwFlags
0x180004baa  mov     rbx, rcx
0x180004bad  call    cs:__imp_SHGetKnownFolderPath
0x180004bb3  mov     esi, eax
0x180004bb5  test    eax, eax
0x180004bb7  jns     short loc_180004BD0
0x180004bb9  mov     rcx, [rsp+58h+ppszPath]; pv
0x180004bbe  test    rcx, rcx
0x180004bc1  jz      short loc_180004BC9
0x180004bc3  call    cs:__imp_CoTaskMemFree
0x180004bc9  mov     eax, esi
0x180004bcb  jmp     loc_180004CA7
0x180004bd0  mov     rdx, [rsp+58h+ppszPath]
0x180004bd5  mov     rcx, rdi
0x180004bd8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180004bdd  test    al, al
0x180004bdf  jz      short loc_180004C3A
0x180004be1  mov     rax, cs:qword_18000D238
0x180004be8  cmp     rax, [rbx]
0x180004beb  jnz     short loc_180004BFA
0x180004bed  mov     rax, cs:qword_18000D240
0x180004bf4  cmp     rax, [rbx+8]
0x180004bf8  jz      short loc_180004C13
0x180004bfa  mov     rax, qword ptr cs:FOLDERID_LocalAppData.Data1
0x180004c01  cmp     rax, [rbx]
0x180004c04  jnz     short loc_180004C26
0x180004c06  mov     rax, qword ptr cs:FOLDERID_LocalAppData.Data4
0x180004c0d  cmp     rax, [rbx+8]
0x180004c11  jnz     short loc_180004C26
0x180004c13  lea     rdx, aComms; "\\Comms"
0x180004c1a  mov     rcx, rdi
0x180004c1d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180004c22  test    al, al
0x180004c24  jz      short loc_180004C3A
0x180004c26  test    rbp, rbp
0x180004c29  jz      short loc_180004C51
0x180004c2b  mov     rdx, rbp
0x180004c2e  mov     rcx, rdi
0x180004c31  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180004c36  test    al, al
0x180004c38  jnz     short loc_180004C51
0x180004c3a  mov     rcx, [rsp+58h+ppszPath]; pv
0x180004c3f  test    rcx, rcx
0x180004c42  jz      short loc_180004C4A
0x180004c44  call    cs:__imp_CoTaskMemFree
0x180004c4a  mov     eax, 8007000Eh
0x180004c4f  jmp     short loc_180004CA7
0x180004c51  test    r14d, r14d
0x180004c54  jz      short loc_180004C95
0x180004c56  mov     rdx, [rdi]; pszPath
0x180004c59  xor     r8d, r8d; psa
0x180004c5c  xor     ecx, ecx; hwnd
0x180004c5e  call    cs:__imp_SHCreateDirectoryExW
0x180004c64  mov     ebx, eax
0x180004c66  cmp     eax, 0B7h
0x180004c6b  jz      short loc_180004C95
0x180004c6d  cmp     eax, 50h ; 'P'
0x180004c70  jz      short loc_180004C95
0x180004c72  test    eax, eax
0x180004c74  jz      short loc_180004C95
0x180004c76  jle     short loc_180004C81
0x180004c78  movzx   ebx, ax
0x180004c7b  or      ebx, 80070000h
0x180004c81  mov     rcx, [rsp+58h+ppszPath]; pv
0x180004c86  test    rcx, rcx
0x180004c89  jz      short loc_180004C91
0x180004c8b  call    cs:__imp_CoTaskMemFree
0x180004c91  mov     eax, ebx
0x180004c93  jmp     short loc_180004CA7
0x180004c95  mov     rcx, [rsp+58h+ppszPath]; pv
0x180004c9a  test    rcx, rcx
0x180004c9d  jz      short loc_180004CA5
0x180004c9f  call    cs:__imp_CoTaskMemFree
0x180004ca5  xor     eax, eax
0x180004ca7  add     rsp, 30h
0x180004cab  pop     r14
0x180004cad  pop     rdi
0x180004cae  pop     rsi
0x180004caf  pop     rbp
0x180004cb0  pop     rbx
0x180004cb1  retn
```
