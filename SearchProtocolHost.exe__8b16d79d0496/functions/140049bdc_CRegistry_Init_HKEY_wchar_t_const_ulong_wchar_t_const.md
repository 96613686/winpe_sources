# CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)

- ea: `0x140049bdc`
- end: `0x140049d17`
- name: `?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z`
- size: `315`
- prototype: `int(CRegistry *__hidden this, HKEY, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004d158`

## callees

- `0x140005240`
- `0x1400104c8`
- `0x140012394`
- `0x140049228`
- `0x140049bdc`
- `0x14004ee84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049c31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049c31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140049c8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140049c8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049c44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049c44`

## pseudocode

```c
__int64 __fastcall CRegistry::Init(CRegistry *this, HKEY a2, const wchar_t *a3, __int64 a4, const wchar_t *a5)
{
  HKEY v7; // rcx
  const wchar_t *v8; // rcx
  bool v9; // al
  wchar_t *v10; // rdx
  LSTATUS v11; // eax
  signed int v12; // ebx
  struct CLMString *v13; // rdi
  unsigned int phkResult; // [rsp+20h] [rbp-268h]
  ATL::CAtlException *v16; // [rsp+40h] [rbp-248h] BYREF
  wchar_t v17[264]; // [rsp+50h] [rbp-238h] BYREF
  void *retaddr; // [rsp+288h] [rbp+0h]

  if ( *((_DWORD *)this + 42) )
  {
    v7 = (HKEY)*((_QWORD *)this + 22);
    if ( v7 )
    {
      RegCloseKey(v7);
      *((_QWORD *)this + 22) = 0;
    }
  }
  SetLastError(0);
  *((_DWORD *)this + 42) = 1;
  v9 = MapRegistryKeyPath(v8, a2, L"Software\\Microsoft\\Windows Search", v17, phkResult);
  v10 = v17;
  if ( !v9 )
    v10 = (wchar_t *)L"Software\\Microsoft\\Windows Search";
  v11 = RegOpenKeyExW(a2, v10, 0, 0x20019u, (PHKEY)this + 22);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 < 0 )
    *((_QWORD *)this + 22) = 0;
  try
  {
    v13 = (CRegistry *)((char *)this + 8);
    if ( a5 )
    {
      CLMString::operator=(v13, a5);
      AppendSlashIf(v13);
      CLMString::Append(v13, L"Software\\Microsoft\\Windows Search", 0xFFFFFFFF);
    }
    else
    {
      CLMString::operator=(v13, L"Software\\Microsoft\\Windows Search");
    }
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
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140049bdc  mov     rax, rsp
0x140049bdf  push    rdi
0x140049be0  push    r12
0x140049be2  push    r14
0x140049be4  sub     rsp, 270h
0x140049beb  mov     [rsp+288h+var_250], 0FFFFFFFFFFFFFFFEh
0x140049bf4  mov     [rax+18h], rbx
0x140049bf8  mov     [rax+20h], rsi
0x140049bfc  mov     rax, cs:__security_cookie
0x140049c03  xor     rax, rsp
0x140049c06  mov     [rsp+288h+var_28], rax
0x140049c0e  mov     rbx, rdx
0x140049c11  mov     rdi, rcx
0x140049c14  mov     rsi, [rsp+288h+arg_20]
0x140049c1c  cmp     dword ptr [rcx+0A8h], 0
0x140049c23  jz      short loc_140049C42
0x140049c25  mov     rcx, [rcx+0B0h]; hKey
0x140049c2c  test    rcx, rcx
0x140049c2f  jz      short loc_140049C42
0x140049c31  call    cs:__imp_RegCloseKey
0x140049c37  mov     qword ptr [rdi+0B0h], 0
0x140049c42  xor     ecx, ecx; dwErrCode
0x140049c44  call    cs:__imp_SetLastError
0x140049c4a  mov     dword ptr [rdi+0A8h], 1
0x140049c54  lea     r14, [rdi+0B0h]
0x140049c5b  lea     r9, [rsp+288h+var_238]; wchar_t *
0x140049c60  lea     r12, aSoftwareMicros_1; "Software\\Microsoft\\Windows Search"
0x140049c67  mov     r8, r12; wchar_t *
0x140049c6a  mov     rdx, rbx; HKEY
0x140049c6d  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x140049c72  lea     rdx, [rsp+288h+var_238]
0x140049c77  test    al, al
0x140049c79  cmovz   rdx, r12; lpSubKey
0x140049c7d  mov     qword ptr [rsp+288h+phkResult], r14; phkResult
0x140049c82  mov     r9d, 20019h; samDesired
0x140049c88  xor     r8d, r8d; ulOptions
0x140049c8b  mov     rcx, rbx; hKey
0x140049c8e  call    cs:__imp_RegOpenKeyExW
0x140049c94  mov     ebx, eax
0x140049c96  test    eax, eax
0x140049c98  jle     short loc_140049CA3
0x140049c9a  movzx   ebx, ax
0x140049c9d  or      ebx, 80070000h
0x140049ca3  test    ebx, ebx
0x140049ca5  jns     short loc_140049CAE
0x140049ca7  mov     qword ptr [r14], 0
0x140049cae  add     rdi, 8
0x140049cb2  mov     rcx, rdi
0x140049cb5  test    rsi, rsi
0x140049cb8  jz      short loc_140049CDB
0x140049cba  mov     rdx, rsi
0x140049cbd  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x140049cc2  mov     rcx, rdi; this
0x140049cc5  call    ?AppendSlashIf@@YAXAEAVCLMString@@@Z; AppendSlashIf(CLMString &)
0x140049cca  or      r8d, 0FFFFFFFFh; unsigned int
0x140049cce  mov     rdx, r12; wchar_t *
0x140049cd1  mov     rcx, rdi; this
0x140049cd4  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x140049cd9  jmp     short loc_140049CE4
0x140049cdb  mov     rdx, r12
0x140049cde  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x140049ce3  nop
0x140049ce4  jmp     short loc_140049CEC
0x140049ce6  jmp     short $+2
0x140049ce8  mov     ebx, [rsp+288h+var_258]
0x140049cec  mov     eax, ebx
0x140049cee  mov     rcx, [rsp+288h+var_28]
0x140049cf6  xor     rcx, rsp; StackCookie
0x140049cf9  call    __security_check_cookie
0x140049cfe  lea     r11, [rsp+288h+var_18]
0x140049d06  mov     rbx, [r11+30h]
0x140049d0a  mov     rsi, [r11+38h]
0x140049d0e  mov     rsp, r11
0x140049d11  pop     r14
0x140049d13  pop     r12
0x140049d15  pop     rdi
0x140049d16  retn
```
