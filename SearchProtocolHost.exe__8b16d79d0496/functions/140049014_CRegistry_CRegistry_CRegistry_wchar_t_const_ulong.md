# CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)

- ea: `0x140049014`
- end: `0x140049123`
- name: `??0CRegistry@@QEAA@PEAV0@PEB_WK@Z`
- size: `271`
- prototype: `CRegistry *(CRegistry *__hidden this, struct CRegistry *, const wchar_t *, unsigned int)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001cad4`
- `0x14001d314`
- `0x14001d6ac`
- `0x14003a8e8`
- `0x140043310`
- `0x1400493e0`
- `0x140049830`

## callees

- `0x140005240`
- `0x1400104c8`
- `0x140012394`
- `0x140049014`
- `0x140049228`
- `0x14004ee84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400490e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400490e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049088`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400490fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049088`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400490fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this, struct CRegistry *a2, wchar_t *a3, REGSAM a4)
{
  struct CLMString *v8; // rbx
  _WORD *v9; // rcx
  HKEY v10; // rbx
  const wchar_t *v11; // rcx
  bool v12; // al
  wchar_t *v13; // rdx
  LSTATUS v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-268h]
  wchar_t v17[264]; // [rsp+40h] [rbp-248h] BYREF

  v8 = (CRegistry *)((char *)this + 8);
  v9 = (_WORD *)((char *)this + 32);
  *((_QWORD *)v8 + 1) = v9;
  *((_QWORD *)v8 + 2) = 65;
  *v9 = 0;
  *(_QWORD *)v8 = &CCICommonPathString::`vftable';
  *(_QWORD *)this = &CRegistry::`vftable';
  *((_DWORD *)this + 42) = 1;
  SetLastError(0);
  CLMString::operator=(v8, *((_QWORD *)a2 + 2));
  AppendSlashIf(v8);
  CLMString::Append(v8, a3, 0xFFFFFFFF);
  v10 = (HKEY)*((_QWORD *)a2 + 22);
  v12 = MapRegistryKeyPath(v11, v10, a3, v17, phkResult);
  v13 = v17;
  if ( !v12 )
    v13 = a3;
  v14 = RegOpenKeyExW(v10, v13, 0, a4, (PHKEY)this + 22);
  if ( v14 )
  {
    *((_QWORD *)this + 22) = 0;
    SetLastError(v14);
  }
  return this;
}

```

## disassembly

```asm
0x140049014  push    rbx
0x140049016  push    rbp
0x140049017  push    rsi
0x140049018  push    rdi
0x140049019  push    r14
0x14004901b  sub     rsp, 260h
0x140049022  mov     [rsp+288h+var_258], 0FFFFFFFFFFFFFFFEh
0x14004902b  mov     rax, cs:__security_cookie
0x140049032  xor     rax, rsp
0x140049035  mov     [rsp+288h+var_38], rax
0x14004903d  mov     ebp, r9d
0x140049040  mov     rsi, r8
0x140049043  mov     rdi, rdx
0x140049046  mov     r14, rcx
0x140049049  mov     [rsp+288h+var_250], rcx
0x14004904e  lea     rbx, [rcx+8]
0x140049052  lea     rcx, [rbx+18h]
0x140049056  mov     [rbx+8], rcx
0x14004905a  mov     qword ptr [rbx+10h], 41h ; 'A'
0x140049062  xor     eax, eax
0x140049064  mov     [rcx], ax
0x140049067  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x14004906e  mov     [rbx], rax
0x140049071  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x140049078  mov     [r14], rax
0x14004907b  mov     dword ptr [r14+0A8h], 1
0x140049086  xor     ecx, ecx; dwErrCode
0x140049088  call    cs:__imp_SetLastError
0x14004908e  mov     rdx, [rdi+10h]
0x140049092  mov     rcx, rbx
0x140049095  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x14004909a  mov     rcx, rbx; this
0x14004909d  call    ?AppendSlashIf@@YAXAEAVCLMString@@@Z; AppendSlashIf(CLMString &)
0x1400490a2  or      r8d, 0FFFFFFFFh; unsigned int
0x1400490a6  mov     rdx, rsi; wchar_t *
0x1400490a9  mov     rcx, rbx; this
0x1400490ac  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1400490b1  mov     rbx, [rdi+0B0h]
0x1400490b8  lea     rdi, [r14+0B0h]
0x1400490bf  lea     r9, [rsp+288h+var_248]; wchar_t *
0x1400490c4  mov     r8, rsi; wchar_t *
0x1400490c7  mov     rdx, rbx; HKEY
0x1400490ca  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x1400490cf  lea     rdx, [rsp+288h+var_248]
0x1400490d4  test    al, al
0x1400490d6  cmovz   rdx, rsi; lpSubKey
0x1400490da  mov     qword ptr [rsp+288h+phkResult], rdi; phkResult
0x1400490df  mov     r9d, ebp; samDesired
0x1400490e2  xor     r8d, r8d; ulOptions
0x1400490e5  mov     rcx, rbx; hKey
0x1400490e8  call    cs:__imp_RegOpenKeyExW
0x1400490ee  test    eax, eax
0x1400490f0  jz      short loc_140049102
0x1400490f2  mov     qword ptr [rdi], 0
0x1400490f9  mov     ecx, eax; dwErrCode
0x1400490fb  call    cs:__imp_SetLastError
0x140049101  nop
0x140049102  mov     rax, r14
0x140049105  mov     rcx, [rsp+288h+var_38]
0x14004910d  xor     rcx, rsp; StackCookie
0x140049110  call    __security_check_cookie
0x140049115  add     rsp, 260h
0x14004911c  pop     r14
0x14004911e  pop     rdi
0x14004911f  pop     rsi
0x140049120  pop     rbp
0x140049121  pop     rbx
0x140049122  retn
```
