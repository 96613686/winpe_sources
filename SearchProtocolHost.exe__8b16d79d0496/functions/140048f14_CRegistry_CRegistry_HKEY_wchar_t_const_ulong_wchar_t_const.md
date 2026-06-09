# CRegistry::CRegistry(HKEY__ *,wchar_t const *,ulong,wchar_t const *)

- ea: `0x140048f14`
- end: `0x14004900b`
- name: `??0CRegistry@@QEAA@PEAUHKEY__@@PEB_WK1@Z`
- size: `247`
- prototype: `CRegistry *(CRegistry *__hidden this, HKEY, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001cad4`
- `0x14001d314`
- `0x14001d6ac`
- `0x14003a8e8`
- `0x140043310`

## callees

- `0x140005240`
- `0x1400104c8`
- `0x140048f14`
- `0x14004ee84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140048fca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140048fca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140048f91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140048fdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140048f91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140048fdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this, HKEY a2, wchar_t *a3)
{
  _WORD *v6; // rcx
  const wchar_t *v7; // rcx
  bool v8; // al
  wchar_t *v9; // rdx
  LSTATUS v10; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-268h]
  wchar_t v13[264]; // [rsp+50h] [rbp-238h] BYREF

  v6 = (_WORD *)((char *)this + 32);
  *((_QWORD *)this + 2) = v6;
  *((_QWORD *)this + 3) = 65;
  *v6 = 0;
  *((_QWORD *)this + 1) = &CCICommonPathString::`vftable';
  *(_QWORD *)this = &CRegistry::`vftable';
  *((_DWORD *)this + 42) = 1;
  CLMString::operator=((char *)this + 8, a3);
  SetLastError(0);
  v8 = MapRegistryKeyPath(v7, a2, a3, v13, phkResult);
  v9 = v13;
  if ( !v8 )
    v9 = a3;
  v10 = RegOpenKeyExW(a2, v9, 0, 0x20019u, (PHKEY)this + 22);
  if ( v10 )
  {
    *((_QWORD *)this + 22) = 0;
    SetLastError(v10);
  }
  return this;
}

```

## disassembly

```asm
0x140048f14  mov     rax, rsp
0x140048f17  push    rsi
0x140048f18  push    rdi
0x140048f19  push    r14
0x140048f1b  sub     rsp, 270h
0x140048f22  mov     [rsp+288h+var_258], 0FFFFFFFFFFFFFFFEh
0x140048f2b  mov     [rax+20h], rbx
0x140048f2f  mov     rax, cs:__security_cookie
0x140048f36  xor     rax, rsp
0x140048f39  mov     [rsp+288h+var_28], rax
0x140048f41  mov     rbx, r8
0x140048f44  mov     rdi, rdx
0x140048f47  mov     rsi, rcx
0x140048f4a  mov     [rsp+288h+var_248], rcx
0x140048f4f  add     rcx, 20h ; ' '
0x140048f53  mov     [rsi+10h], rcx
0x140048f57  mov     qword ptr [rsi+18h], 41h ; 'A'
0x140048f5f  xor     eax, eax
0x140048f61  mov     [rcx], ax
0x140048f64  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x140048f6b  mov     [rsi+8], rax
0x140048f6f  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x140048f76  mov     [rsi], rax
0x140048f79  mov     dword ptr [rsi+0A8h], 1
0x140048f83  mov     rdx, r8
0x140048f86  lea     rcx, [rsi+8]
0x140048f8a  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x140048f8f  xor     ecx, ecx; dwErrCode
0x140048f91  call    cs:__imp_SetLastError
0x140048f97  lea     r14, [rsi+0B0h]
0x140048f9e  lea     r9, [rsp+288h+var_238]; wchar_t *
0x140048fa3  mov     r8, rbx; wchar_t *
0x140048fa6  mov     rdx, rdi; HKEY
0x140048fa9  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x140048fae  lea     rdx, [rsp+288h+var_238]
0x140048fb3  test    al, al
0x140048fb5  cmovz   rdx, rbx; lpSubKey
0x140048fb9  mov     qword ptr [rsp+288h+phkResult], r14; phkResult
0x140048fbe  mov     r9d, 20019h; samDesired
0x140048fc4  xor     r8d, r8d; ulOptions
0x140048fc7  mov     rcx, rdi; hKey
0x140048fca  call    cs:__imp_RegOpenKeyExW
0x140048fd0  test    eax, eax
0x140048fd2  jz      short loc_140048FE4
0x140048fd4  mov     qword ptr [r14], 0
0x140048fdb  mov     ecx, eax; dwErrCode
0x140048fdd  call    cs:__imp_SetLastError
0x140048fe3  nop
0x140048fe4  mov     rax, rsi
0x140048fe7  mov     rcx, [rsp+288h+var_28]
0x140048fef  xor     rcx, rsp; StackCookie
0x140048ff2  call    __security_check_cookie
0x140048ff7  mov     rbx, [rsp+288h+arg_18]
0x140048fff  add     rsp, 270h
0x140049006  pop     r14
0x140049008  pop     rdi
0x140049009  pop     rsi
0x14004900a  retn
```
