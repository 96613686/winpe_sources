# CRegistry::CRegistry(HKEY__ *,wchar_t const *,ulong,wchar_t const *)

- ea: `0x18002a18c`
- end: `0x18002a278`
- name: `??0CRegistry@@QEAA@PEAUHKEY__@@PEB_WK1@Z`
- size: `236`
- prototype: `CRegistry *__fastcall(CRegistry *this, HKEY, wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016044`
- `0x180038164`

## callees

- `0x180002300`
- `0x180014448`
- `0x18002a18c`
- `0x18002b944`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a1fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a24a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a1fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a24a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a237`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a237`

## pseudocode

```c
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this, HKEY a2, wchar_t *a3)
{
  _WORD *v6; // rcx
  const wchar_t *v7; // rcx
  bool v8; // al
  wchar_t *v9; // rdx
  LSTATUS v10; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-258h]
  wchar_t v13[264]; // [rsp+40h] [rbp-238h] BYREF

  v6 = (_WORD *)((char *)this + 32);
  *((_QWORD *)this + 2) = v6;
  *((_QWORD *)this + 3) = 65;
  *v6 = 0;
  *((_QWORD *)this + 1) = &TLMString<64,64,32767>::`vftable';
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
0x18002a18c  mov     [rsp+arg_18], rbx
0x18002a191  push    rsi
0x18002a192  push    rdi
0x18002a193  push    r14
0x18002a195  sub     rsp, 260h
0x18002a19c  mov     rax, cs:__security_cookie
0x18002a1a3  xor     rax, rsp
0x18002a1a6  mov     [rsp+278h+var_28], rax
0x18002a1ae  mov     rbx, r8
0x18002a1b1  mov     rdi, rdx
0x18002a1b4  mov     rsi, rcx
0x18002a1b7  mov     [rsp+278h+var_248], rcx
0x18002a1bc  add     rcx, 20h ; ' '
0x18002a1c0  mov     [rsi+10h], rcx
0x18002a1c4  mov     qword ptr [rsi+18h], 41h ; 'A'
0x18002a1cc  xor     eax, eax
0x18002a1ce  mov     [rcx], ax
0x18002a1d1  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x18002a1d8  mov     [rsi+8], rax
0x18002a1dc  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18002a1e3  mov     [rsi], rax
0x18002a1e6  mov     dword ptr [rsi+0A8h], 1
0x18002a1f0  mov     rdx, r8
0x18002a1f3  lea     rcx, [rsi+8]
0x18002a1f7  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18002a1fc  xor     ecx, ecx; dwErrCode
0x18002a1fe  call    cs:__imp_SetLastError
0x18002a204  lea     r14, [rsi+0B0h]
0x18002a20b  lea     r9, [rsp+278h+var_238]; wchar_t *
0x18002a210  mov     r8, rbx; wchar_t *
0x18002a213  mov     rdx, rdi; HKEY
0x18002a216  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x18002a21b  lea     rdx, [rsp+278h+var_238]
0x18002a220  test    al, al
0x18002a222  cmovz   rdx, rbx; lpSubKey
0x18002a226  mov     qword ptr [rsp+278h+phkResult], r14; phkResult
0x18002a22b  mov     r9d, 20019h; samDesired
0x18002a231  xor     r8d, r8d; ulOptions
0x18002a234  mov     rcx, rdi; hKey
0x18002a237  call    cs:__imp_RegOpenKeyExW
0x18002a23d  test    eax, eax
0x18002a23f  jz      short loc_18002A251
0x18002a241  mov     qword ptr [r14], 0
0x18002a248  mov     ecx, eax; dwErrCode
0x18002a24a  call    cs:__imp_SetLastError
0x18002a250  nop
0x18002a251  mov     rax, rsi
0x18002a254  mov     rcx, [rsp+278h+var_28]
0x18002a25c  xor     rcx, rsp; StackCookie
0x18002a25f  call    __security_check_cookie
0x18002a264  mov     rbx, [rsp+278h+arg_18]
0x18002a26c  add     rsp, 260h
0x18002a273  pop     r14
0x18002a275  pop     rdi
0x18002a276  pop     rsi
0x18002a277  retn
```
