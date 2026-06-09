# Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)

- ea: `0x18002f690`
- end: `0x18002f7f9`
- name: `?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z`
- size: `361`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002a020`
- `0x18002a438`
- `0x18002bc70`
- `0x180035308`

## callees

- `0x180003c80`
- `0x18000f9e4`
- `0x180013b8c`
- `0x18001b444`
- `0x1800212c8`
- `0x180021348`
- `0x1800236ac`
- `0x180023bc0`
- `0x18002f690`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f700`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f77b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f700`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f77b`

## string_xrefs

- `0x18002f723`: `onecore\base\devices\cam\core\registryhelpers.cpp`
- `0x18002f78c`: `onecore\base\devices\cam\core\registryhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::RegGetStringValue(
        __int64 a1,
        HKEY a2,
        const WCHAR *a3,
        const WCHAR *a4,
        _BYTE *a5)
{
  unsigned int ValueW; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  void *pvData; // rax
  unsigned int v14; // eax
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned int pdwType; // [rsp+20h] [rbp-41h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-41h]
  DWORD pcbData; // [rsp+40h] [rbp-21h] BYREF
  DWORD v21[4]; // [rsp+48h] [rbp-19h] BYREF
  _BYTE v22[32]; // [rsp+58h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  *(_QWORD *)v21 = a1;
  pcbData = 0;
  if ( a5 )
    *a5 = 0;
  ValueW = RegGetValueW(a2, a3, a4, 0x10022u, 0, 0, &pcbData);
  if ( ValueW == 2 )
  {
    std::wstring::wstring(a1);
  }
  else
  {
    if ( ValueW )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\registryhelpers.cpp",
        (const char *)ValueW,
        pdwType);
    std::wstring::wstring(v22, (unsigned __int64)pcbData >> 1);
    v21[0] = 0;
    pvData = (void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22, v10, v11, v12);
    v14 = RegGetValueW(a2, a3, a4, 0x10022u, v21, pvData, &pcbData);
    if ( v14 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\registryhelpers.cpp",
        (const char *)v14,
        pdwTypea);
    v15 = (unsigned __int64)pcbData >> 1;
    if ( v21[0] == 1 )
      v16 = v15 - 1;
    else
      v16 = v15 - 2;
    std::wstring::resize(v22, v16);
    if ( a5 )
      *a5 = 1;
    std::wstring::wstring(a1, v22);
    std::wstring::_Tidy_deallocate(v22);
  }
  return a1;
}

```

## disassembly

```asm
0x18002f690  push    rbp
0x18002f692  push    rbx
0x18002f693  push    rsi
0x18002f694  push    rdi
0x18002f695  push    r14
0x18002f697  push    r15
0x18002f699  lea     rbp, [rsp-27h]
0x18002f69e  sub     rsp, 88h
0x18002f6a5  mov     rax, cs:__security_cookie
0x18002f6ac  xor     rax, rsp
0x18002f6af  mov     [rbp+4Fh+var_38], rax
0x18002f6b3  mov     r15, r9
0x18002f6b6  mov     r14, r8
0x18002f6b9  mov     rsi, rdx
0x18002f6bc  mov     rbx, rcx
0x18002f6bf  mov     qword ptr [rbp+4Fh+var_68], rcx
0x18002f6c3  mov     rdi, [rbp+4Fh+arg_20]
0x18002f6c7  mov     [rbp+4Fh+var_70], 0
0x18002f6ce  test    rdi, rdi
0x18002f6d1  jz      short loc_18002F6D6
0x18002f6d3  mov     byte ptr [rdi], 0
0x18002f6d6  lea     rax, [rbp+4Fh+var_70]
0x18002f6da  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18002f6df  mov     [rsp+0B0h+pvData], 0; pvData
0x18002f6e8  mov     [rsp+0B0h+pdwType], 0; unsigned int
0x18002f6f1  mov     r9d, 10022h; dwFlags
0x18002f6f7  mov     r8, r15; lpValue
0x18002f6fa  mov     rdx, r14; lpSubKey
0x18002f6fd  mov     rcx, rsi; hkey
0x18002f700  call    cs:__imp_RegGetValueW
0x18002f706  cmp     eax, 2
0x18002f709  jnz     short loc_18002F718
0x18002f70b  mov     rcx, rbx
0x18002f70e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002f713  jmp     loc_18002F7DA
0x18002f718  test    eax, eax
0x18002f71a  jz      short loc_18002F735
0x18002f71c  mov     rcx, [rbp+57h]; this
0x18002f720  mov     r9d, eax; char *
0x18002f723  lea     r8, aOnecoreBaseDev_7; "onecore\\base\\devices\\cam\\core\\regi"...
0x18002f72a  mov     edx, 0DAh; void *
0x18002f72f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002f735  mov     edx, [rbp+4Fh+var_70]
0x18002f738  shr     rdx, 1
0x18002f73b  lea     rcx, [rbp+4Fh+var_58]
0x18002f73f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18002f744  nop
0x18002f745  mov     [rbp+4Fh+var_68], 0
0x18002f74c  lea     rcx, [rbp+4Fh+var_58]
0x18002f750  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f755  lea     rcx, [rbp+4Fh+var_70]
0x18002f759  mov     [rsp+0B0h+pcbData], rcx; pcbData
0x18002f75e  mov     [rsp+0B0h+pvData], rax; pvData
0x18002f763  lea     rax, [rbp+4Fh+var_68]
0x18002f767  mov     [rsp+0B0h+pdwType], rax; unsigned int
0x18002f76c  mov     r9d, 10022h; dwFlags
0x18002f772  mov     r8, r15; lpValue
0x18002f775  mov     rdx, r14; lpSubKey
0x18002f778  mov     rcx, rsi; hkey
0x18002f77b  call    cs:__imp_RegGetValueW
0x18002f781  mov     rcx, [rbp+57h]; this
0x18002f785  test    eax, eax
0x18002f787  jz      short loc_18002F79E
0x18002f789  mov     r9d, eax; char *
0x18002f78c  lea     r8, aOnecoreBaseDev_7; "onecore\\base\\devices\\cam\\core\\regi"...
0x18002f793  mov     edx, 0EBh; void *
0x18002f798  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002f79e  mov     edx, [rbp+4Fh+var_70]
0x18002f7a1  lea     rcx, [rbp+4Fh+var_58]
0x18002f7a5  shr     rdx, 1
0x18002f7a8  cmp     [rbp+4Fh+var_68], 1
0x18002f7ac  jnz     short loc_18002F7B3
0x18002f7ae  dec     rdx
0x18002f7b1  jmp     short loc_18002F7B7
0x18002f7b3  sub     rdx, 2
0x18002f7b7  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002f7bc  test    rdi, rdi
0x18002f7bf  jz      short loc_18002F7C4
0x18002f7c1  mov     byte ptr [rdi], 1
0x18002f7c4  lea     rdx, [rbp+4Fh+var_58]
0x18002f7c8  mov     rcx, rbx
0x18002f7cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18002f7d0  nop
0x18002f7d1  lea     rcx, [rbp+4Fh+var_58]
0x18002f7d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f7da  mov     rax, rbx
0x18002f7dd  mov     rcx, [rbp+4Fh+var_38]
0x18002f7e1  xor     rcx, rsp; StackCookie
0x18002f7e4  call    __security_check_cookie
0x18002f7e9  add     rsp, 88h
0x18002f7f0  pop     r15
0x18002f7f2  pop     r14
0x18002f7f4  pop     rdi
0x18002f7f5  pop     rsi
0x18002f7f6  pop     rbx
0x18002f7f7  pop     rbp
0x18002f7f8  retn
```
