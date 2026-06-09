# CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)

- ea: `0x18002add0`
- end: `0x18002aec1`
- name: `?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z`
- size: `241`
- prototype: `int(CRegistry *__hidden this, HKEY, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030634`
- `0x180038164`

## callees

- `0x180002300`
- `0x180014448`
- `0x18002add0`
- `0x18002b944`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ae23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ae23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae10`

## pseudocode

```c
__int64 __fastcall CRegistry::Init(CRegistry *this, HKEY a2, wchar_t *a3, __int64 a4, const wchar_t *a5)
{
  HKEY v8; // rcx
  const wchar_t *v9; // rcx
  bool v10; // al
  wchar_t *v11; // rdx
  LSTATUS v12; // eax
  signed int v13; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-258h]
  ATL::CAtlException *v16; // [rsp+38h] [rbp-240h] BYREF
  wchar_t v17[264]; // [rsp+40h] [rbp-238h] BYREF
  void *retaddr; // [rsp+278h] [rbp+0h]

  if ( *((_DWORD *)this + 42) )
  {
    v8 = (HKEY)*((_QWORD *)this + 22);
    if ( v8 )
    {
      RegCloseKey(v8);
      *((_QWORD *)this + 22) = 0;
    }
  }
  SetLastError(0);
  *((_DWORD *)this + 42) = 1;
  v10 = MapRegistryKeyPath(v9, a2, a3, v17, phkResult);
  v11 = v17;
  if ( !v10 )
    v11 = a3;
  v12 = RegOpenKeyExW(a2, v11, 0, 0x20019u, (PHKEY)this + 22);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 < 0 )
    *((_QWORD *)this + 22) = 0;
  try
  {
    CLMString::operator=((__int64)this + 8, (__int64)a3);
  }
  catch ( ATL::CAtlException *v16 )
  {
    return *(unsigned int *)v16;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      152,
      "onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx");
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002add0  mov     [rsp+arg_18], rbx
0x18002add5  push    rsi
0x18002add6  push    rdi
0x18002add7  push    r14
0x18002add9  sub     rsp, 260h
0x18002ade0  mov     rax, cs:__security_cookie
0x18002ade7  xor     rax, rsp
0x18002adea  mov     [rsp+278h+var_28], rax
0x18002adf2  mov     rsi, r8
0x18002adf5  mov     rbx, rdx
0x18002adf8  mov     rdi, rcx
0x18002adfb  cmp     dword ptr [rcx+0A8h], 0
0x18002ae02  jz      short loc_18002AE21
0x18002ae04  mov     rcx, [rcx+0B0h]; hKey
0x18002ae0b  test    rcx, rcx
0x18002ae0e  jz      short loc_18002AE21
0x18002ae10  call    cs:__imp_RegCloseKey
0x18002ae16  mov     qword ptr [rdi+0B0h], 0
0x18002ae21  xor     ecx, ecx; dwErrCode
0x18002ae23  call    cs:__imp_SetLastError
0x18002ae29  mov     dword ptr [rdi+0A8h], 1
0x18002ae33  lea     r14, [rdi+0B0h]
0x18002ae3a  lea     r9, [rsp+278h+var_238]; wchar_t *
0x18002ae3f  mov     r8, rsi; wchar_t *
0x18002ae42  mov     rdx, rbx; HKEY
0x18002ae45  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x18002ae4a  lea     rdx, [rsp+278h+var_238]
0x18002ae4f  test    al, al
0x18002ae51  cmovz   rdx, rsi; lpSubKey
0x18002ae55  mov     qword ptr [rsp+278h+phkResult], r14; phkResult
0x18002ae5a  mov     r9d, 20019h; samDesired
0x18002ae60  xor     r8d, r8d; ulOptions
0x18002ae63  mov     rcx, rbx; hKey
0x18002ae66  call    cs:__imp_RegOpenKeyExW
0x18002ae6c  mov     ebx, eax
0x18002ae6e  test    eax, eax
0x18002ae70  jle     short loc_18002AE7B
0x18002ae72  movzx   ebx, ax
0x18002ae75  or      ebx, 80070000h
0x18002ae7b  test    ebx, ebx
0x18002ae7d  jns     short loc_18002AE86
0x18002ae7f  mov     qword ptr [r14], 0
0x18002ae86  lea     rcx, [rdi+8]
0x18002ae8a  mov     rdx, rsi
0x18002ae8d  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18002ae92  nop
0x18002ae93  jmp     short loc_18002AE9B
0x18002ae95  jmp     short $+2
0x18002ae97  mov     ebx, [rsp+278h+var_248]
0x18002ae9b  mov     eax, ebx
0x18002ae9d  mov     rcx, [rsp+278h+var_28]
0x18002aea5  xor     rcx, rsp; StackCookie
0x18002aea8  call    __security_check_cookie
0x18002aead  mov     rbx, [rsp+278h+arg_18]
0x18002aeb5  add     rsp, 260h
0x18002aebc  pop     r14
0x18002aebe  pop     rdi
0x18002aebf  pop     rsi
0x18002aec0  retn
```
