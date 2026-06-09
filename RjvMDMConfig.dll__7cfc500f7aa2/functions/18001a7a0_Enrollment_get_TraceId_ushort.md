# Enrollment::get_TraceId(ushort * *)

- ea: `0x18001a7a0`
- end: `0x18001a954`
- name: `?get_TraceId@Enrollment@@UEAAJPEAPEAG@Z`
- size: `436`
- prototype: `__int64 __fastcall(Enrollment *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180001c60`
- `0x1800026d8`
- `0x180005a38`
- `0x1800075e8`
- `0x18000ff18`
- `0x18000ff80`
- `0x180011828`
- `0x18001a35c`
- `0x18001a7a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a915`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a915`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a8ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a8ff`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a8f0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a8f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a8b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a8b6`

## pseudocode

```c
__int64 __fastcall Enrollment::get_TraceId(Enrollment *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v4; // rax
  int String; // ebx
  unsigned __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  bool v9; // sf
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-C8h]
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(SubKey, 0, 0x208u);
  hKey = 0;
  psz = 0;
  v4 = (const unsigned __int16 *)DMGetKnownRegPath(2);
  String = StringCchCopyW(SubKey, 0x104u, v4);
  if ( String >= 0 )
  {
    String = StringCchCatW(SubKey, 0x104u, L"Status");
    if ( String >= 0 )
    {
      String = StringCchCatW(SubKey, 0x104u, L"\\");
      if ( String >= 0 )
      {
        v6 = (unsigned __int64)this + 150;
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)(v6 + 2 * v7) );
        String = StringCchCatW(SubKey, 0x104u, (const unsigned __int16 *)(v6 & -(__int64)(v7 != 0)));
        if ( String >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hKey,
            0);
          v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
          v9 = v8 < 0;
          if ( v8 > 0 )
          {
            v8 = (unsigned __int16)v8 | 0x80070000;
            v9 = v8 < 0;
          }
          if ( v9 )
          {
            String = v8;
          }
          else
          {
            String = RegistryAllocAndGetString(hKey);
            if ( String >= 0 )
            {
              *a2 = SysAllocString(psz);
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, psz);
            }
          }
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18001a7a0  mov     [rsp-8+arg_10], rbx
0x18001a7a5  push    rbp
0x18001a7a6  push    rsi
0x18001a7a7  push    rdi
0x18001a7a8  push    r14
0x18001a7aa  push    r15
0x18001a7ac  lea     rbp, [rsp-160h]
0x18001a7b4  sub     rsp, 260h
0x18001a7bb  mov     rax, cs:__security_cookie
0x18001a7c2  xor     rax, rsp
0x18001a7c5  mov     [rbp+180h+var_30], rax
0x18001a7cc  mov     rsi, rdx
0x18001a7cf  mov     rdi, rcx
0x18001a7d2  xor     edx, edx; Val
0x18001a7d4  lea     rcx, [rsp+280h+SubKey]; void *
0x18001a7d9  mov     r8d, 208h; Size
0x18001a7df  call    memset_0
0x18001a7e4  xor     r14d, r14d
0x18001a7e7  mov     [rsp+280h+hKey], r14
0x18001a7ec  mov     [rsp+280h+psz], r14
0x18001a7f1  lea     ecx, [r14+2]
0x18001a7f5  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18001a7fa  mov     r15d, 104h
0x18001a800  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18001a805  mov     edx, r15d; unsigned __int64
0x18001a808  mov     r8, rax; unsigned __int16 *
0x18001a80b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a810  mov     ebx, eax
0x18001a812  test    eax, eax
0x18001a814  js      loc_18001A921
0x18001a81a  lea     r8, aStatus; "Status"
0x18001a821  mov     edx, r15d; unsigned __int64
0x18001a824  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18001a829  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a82e  mov     ebx, eax
0x18001a830  test    eax, eax
0x18001a832  js      loc_18001A921
0x18001a838  lea     r8, asc_180020DAC; "\\"
0x18001a83f  mov     edx, r15d; unsigned __int64
0x18001a842  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18001a847  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a84c  mov     ebx, eax
0x18001a84e  test    eax, eax
0x18001a850  js      loc_18001A921
0x18001a856  lea     rcx, [rdi+96h]
0x18001a85d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a861  inc     rax
0x18001a864  cmp     [rcx+rax*2], r14w
0x18001a869  jnz     short loc_18001A861
0x18001a86b  neg     rax
0x18001a86e  mov     rdx, r15; unsigned __int64
0x18001a871  sbb     r8, r8
0x18001a874  and     r8, rcx; unsigned __int16 *
0x18001a877  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18001a87c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a881  mov     ebx, eax
0x18001a883  test    eax, eax
0x18001a885  js      loc_18001A921
0x18001a88b  xor     edx, edx
0x18001a88d  lea     rcx, [rsp+280h+hKey]
0x18001a892  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001a897  lea     rax, [rsp+280h+hKey]
0x18001a89c  mov     r9d, 1; samDesired
0x18001a8a2  xor     r8d, r8d; ulOptions
0x18001a8a5  mov     [rsp+280h+phkResult], rax; phkResult
0x18001a8aa  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18001a8af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a8b6  call    cs:__imp_RegOpenKeyExW
0x18001a8bd  nop     dword ptr [rax+rax+00h]
0x18001a8c2  test    eax, eax
0x18001a8c4  jle     short loc_18001A8D0
0x18001a8c6  movzx   eax, ax
0x18001a8c9  or      eax, 80070000h
0x18001a8ce  test    eax, eax
0x18001a8d0  jns     short loc_18001A8D6
0x18001a8d2  mov     ebx, eax
0x18001a8d4  jmp     short loc_18001A921
0x18001a8d6  mov     rcx, [rsp+280h+hKey]; hKey
0x18001a8db  lea     r8, [rsp+280h+psz]
0x18001a8e0  call    RegistryAllocAndGetString
0x18001a8e5  mov     ebx, eax
0x18001a8e7  test    eax, eax
0x18001a8e9  js      short loc_18001A921
0x18001a8eb  mov     rcx, [rsp+280h+psz]; psz
0x18001a8f0  call    cs:__imp_SysAllocString
0x18001a8f7  nop     dword ptr [rax+rax+00h]
0x18001a8fc  mov     [rsi], rax
0x18001a8ff  call    cs:__imp_GetProcessHeap
0x18001a906  nop     dword ptr [rax+rax+00h]
0x18001a90b  mov     r8, [rsp+280h+psz]; lpMem
0x18001a910  xor     edx, edx; dwFlags
0x18001a912  mov     rcx, rax; hHeap
0x18001a915  call    cs:__imp_HeapFree
0x18001a91c  nop     dword ptr [rax+rax+00h]
0x18001a921  lea     rcx, [rsp+280h+hKey]
0x18001a926  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001a92b  mov     eax, ebx
0x18001a92d  mov     rcx, [rbp+180h+var_30]
0x18001a934  xor     rcx, rsp; StackCookie
0x18001a937  call    __security_check_cookie
0x18001a93c  mov     rbx, [rsp+280h+arg_10]
0x18001a944  add     rsp, 260h
0x18001a94b  pop     r15
0x18001a94d  pop     r14
0x18001a94f  pop     rdi
0x18001a950  pop     rsi
0x18001a951  pop     rbp
0x18001a952  retn
```
