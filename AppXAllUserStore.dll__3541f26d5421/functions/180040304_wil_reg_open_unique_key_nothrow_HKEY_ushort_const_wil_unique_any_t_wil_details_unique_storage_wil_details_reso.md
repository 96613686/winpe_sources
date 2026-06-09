# wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)

- ea: `0x180040304`
- end: `0x180040383`
- name: `?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z`
- size: `127`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000bf10`
- `0x18003e684`

## callees

- `0x18001ed4c`
- `0x18001ff94`
- `0x180040304`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040332`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040332`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040361`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040361`

## pseudocode

```c
LSTATUS __fastcall wil::reg::open_unique_key_nothrow(__int64 a1, const WCHAR *a2, HKEY *a3)
{
  HKEY v3; // rdi
  LSTATUS result; // eax
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v7 = a1;
  v3 = *a3;
  if ( *a3 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
    RegCloseKey(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
  }
  *a3 = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, a3);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180040304  mov     rax, rsp
0x180040307  mov     [rax+10h], rbx
0x18004030b  mov     [rax+18h], rsi
0x18004030f  mov     [rax+8], rcx
0x180040313  push    rdi
0x180040314  sub     rsp, 30h
0x180040318  mov     rdi, [r8]
0x18004031b  mov     rbx, r8
0x18004031e  mov     rsi, rdx
0x180040321  test    rdi, rdi
0x180040324  jz      short loc_180040342
0x180040326  lea     rcx, [rax+8]; this
0x18004032a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004032f  mov     rcx, rdi; hKey
0x180040332  call    cs:__imp_RegCloseKey
0x180040338  lea     rcx, [rsp+38h+arg_0]; this
0x18004033d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180040342  mov     r9d, 20019h; samDesired
0x180040348  mov     qword ptr [rbx], 0
0x18004034f  xor     r8d, r8d; ulOptions
0x180040352  mov     [rsp+38h+phkResult], rbx; phkResult
0x180040357  mov     rdx, rsi; lpSubKey
0x18004035a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040361  call    cs:__imp_RegOpenKeyExW
0x180040367  test    eax, eax
0x180040369  jle     short loc_180040373
0x18004036b  movzx   eax, ax
0x18004036e  or      eax, 80070000h
0x180040373  mov     rbx, [rsp+38h+arg_8]
0x180040378  mov     rsi, [rsp+38h+arg_10]
0x18004037d  add     rsp, 30h
0x180040381  pop     rdi
0x180040382  retn
```
