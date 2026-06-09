# CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)

- ea: `0x1400290b8`
- end: `0x1400291ff`
- name: `?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z`
- size: `327`
- prototype: `int(CRegistry *__hidden this, HKEY, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028044`

## callees

- `0x1400030a0`
- `0x140028218`
- `0x140028720`
- `0x1400290b8`
- `0x14002aac4`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029122`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002910f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002910f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140029169`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140029169`

## pseudocode

```c
__int64 __fastcall CRegistry::Init(CRegistry *this, HKEY a2, const wchar_t *a3, REGSAM a4, const wchar_t *a5)
{
  HKEY v8; // rcx
  const wchar_t *v9; // rcx
  bool v10; // al
  wchar_t *v11; // rdx
  LSTATUS v12; // eax
  signed int v13; // ebx
  struct CLMString *v14; // rdi
  void (__fastcall *v15)(struct CLMString *, const wchar_t *, _QWORD, __int64); // rax
  unsigned int phkResult; // [rsp+20h] [rbp-278h]
  ATL::CAtlException *v18; // [rsp+40h] [rbp-258h] BYREF
  wchar_t v19[264]; // [rsp+50h] [rbp-248h] BYREF

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
  v10 = MapRegistryKeyPath(v9, a2, L"Software\\Microsoft\\Windows Search", v19, phkResult);
  v11 = v19;
  if ( !v10 )
    v11 = (wchar_t *)L"Software\\Microsoft\\Windows Search";
  v12 = RegOpenKeyExW(a2, v11, 0, a4, (PHKEY)this + 22);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 < 0 )
    *((_QWORD *)this + 22) = 0;
  try
  {
    v14 = (CRegistry *)((char *)this + 8);
    v15 = *(void (__fastcall **)(struct CLMString *, const wchar_t *, _QWORD, __int64))(*(_QWORD *)v14 + 32LL);
    if ( a5 )
    {
      v15(v14, a5, 0, 0xFFFFFFFFLL);
      AppendSlashIf(v14);
      CLMString::Append(v14, L"Software\\Microsoft\\Windows Search", 0xFFFFFFFF);
    }
    else
    {
      v15(v14, L"Software\\Microsoft\\Windows Search", 0, 0xFFFFFFFFLL);
    }
  }
  catch ( ATL::CAtlException *v18 )
  {
    return *(unsigned int *)v18;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>();
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400290b8  mov     rax, rsp
0x1400290bb  push    rsi
0x1400290bc  push    rdi
0x1400290bd  push    r13
0x1400290bf  push    r14
0x1400290c1  push    r15
0x1400290c3  sub     rsp, 270h
0x1400290ca  mov     [rsp+298h+var_260], 0FFFFFFFFFFFFFFFEh
0x1400290d3  mov     [rax+18h], rbx
0x1400290d7  mov     rax, cs:__security_cookie
0x1400290de  xor     rax, rsp
0x1400290e1  mov     [rsp+298h+var_38], rax
0x1400290e9  mov     r15d, r9d
0x1400290ec  mov     rbx, rdx
0x1400290ef  mov     rdi, rcx
0x1400290f2  mov     rsi, [rsp+298h+arg_20]
0x1400290fa  cmp     dword ptr [rcx+0A8h], 0
0x140029101  jz      short loc_140029120
0x140029103  mov     rcx, [rcx+0B0h]; hKey
0x14002910a  test    rcx, rcx
0x14002910d  jz      short loc_140029120
0x14002910f  call    cs:__imp_RegCloseKey
0x140029115  mov     qword ptr [rdi+0B0h], 0
0x140029120  xor     ecx, ecx; dwErrCode
0x140029122  call    cs:__imp_SetLastError
0x140029128  mov     dword ptr [rdi+0A8h], 1
0x140029132  lea     r14, [rdi+0B0h]
0x140029139  lea     r9, [rsp+298h+var_248]; wchar_t *
0x14002913e  lea     r13, aSoftwareMicros_2; "Software\\Microsoft\\Windows Search"
0x140029145  mov     r8, r13; wchar_t *
0x140029148  mov     rdx, rbx; HKEY
0x14002914b  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x140029150  lea     rdx, [rsp+298h+var_248]
0x140029155  test    al, al
0x140029157  cmovz   rdx, r13; lpSubKey
0x14002915b  mov     qword ptr [rsp+298h+phkResult], r14; phkResult
0x140029160  mov     r9d, r15d; samDesired
0x140029163  xor     r8d, r8d; ulOptions
0x140029166  mov     rcx, rbx; hKey
0x140029169  call    cs:__imp_RegOpenKeyExW
0x14002916f  mov     ebx, eax
0x140029171  test    eax, eax
0x140029173  jle     short loc_14002917E
0x140029175  movzx   ebx, ax
0x140029178  or      ebx, 80070000h
0x14002917e  test    ebx, ebx
0x140029180  jns     short loc_140029189
0x140029182  mov     qword ptr [r14], 0
0x140029189  add     rdi, 8
0x14002918d  mov     rax, [rdi]
0x140029190  mov     rax, [rax+20h]
0x140029194  or      r9d, 0FFFFFFFFh
0x140029198  xor     r8d, r8d
0x14002919b  mov     rcx, rdi
0x14002919e  test    rsi, rsi
0x1400291a1  jz      short loc_1400291C4
0x1400291a3  mov     rdx, rsi
0x1400291a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400291ab  mov     rcx, rdi; struct CLMString *
0x1400291ae  call    ?AppendSlashIf@@YAXAEAVCLMString@@@Z; AppendSlashIf(CLMString &)
0x1400291b3  or      r8d, 0FFFFFFFFh; unsigned int
0x1400291b7  mov     rdx, r13; wchar_t *
0x1400291ba  mov     rcx, rdi; this
0x1400291bd  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1400291c2  jmp     short loc_1400291CD
0x1400291c4  mov     rdx, r13
0x1400291c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400291cc  nop
0x1400291cd  jmp     short loc_1400291D5
0x1400291cf  jmp     short $+2
0x1400291d1  mov     ebx, [rsp+298h+var_268]
0x1400291d5  mov     eax, ebx
0x1400291d7  mov     rcx, [rsp+298h+var_38]
0x1400291df  xor     rcx, rsp; StackCookie
0x1400291e2  call    __security_check_cookie
0x1400291e7  mov     rbx, [rsp+298h+arg_10]
0x1400291ef  add     rsp, 270h
0x1400291f6  pop     r15
0x1400291f8  pop     r14
0x1400291fa  pop     r13
0x1400291fc  pop     rdi
0x1400291fd  pop     rsi
0x1400291fe  retn
```
