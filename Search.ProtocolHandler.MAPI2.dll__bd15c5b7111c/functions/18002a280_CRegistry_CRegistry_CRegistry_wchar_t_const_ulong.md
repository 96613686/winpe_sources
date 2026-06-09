# CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)

- ea: `0x18002a280`
- end: `0x18002a391`
- name: `??0CRegistry@@QEAA@PEAV0@PEB_WK@Z`
- size: `273`
- prototype: `CRegistry *__fastcall(CRegistry *this, struct CRegistry *, wchar_t *, REGSAM)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002a560`
- `0x18002a9b0`

## callees

- `0x180002300`
- `0x180014448`
- `0x18002a280`
- `0x18002a3e4`
- `0x18002b944`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a2eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a369`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a2eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a369`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a356`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a356`

## pseudocode

```c
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this, struct CRegistry *a2, wchar_t *a3, REGSAM a4)
{
  char *v8; // rbx
  _WORD *v9; // rcx
  HKEY v10; // rbx
  const wchar_t *v11; // rcx
  bool v12; // al
  wchar_t *v13; // rdx
  LSTATUS v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-268h]
  wchar_t v17[264]; // [rsp+40h] [rbp-248h] BYREF

  v8 = (char *)this + 8;
  v9 = (_WORD *)((char *)this + 32);
  *((_QWORD *)v8 + 1) = v9;
  *((_QWORD *)v8 + 2) = 65;
  *v9 = 0;
  *(_QWORD *)v8 = &TLMString<64,64,32767>::`vftable';
  *(_QWORD *)this = &CRegistry::`vftable';
  *((_DWORD *)this + 42) = 1;
  SetLastError(0);
  CLMString::operator=(v8, *((_QWORD *)a2 + 2));
  AppendSlashIf((struct CLMString *)v8);
  (*(void (__fastcall **)(char *, wchar_t *, _QWORD, __int64))(*(_QWORD *)v8 + 32LL))(
    v8,
    a3,
    *((unsigned int *)v8 + 5),
    0xFFFFFFFFLL);
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
0x18002a280  push    rbx
0x18002a282  push    rbp
0x18002a283  push    rsi
0x18002a284  push    rdi
0x18002a285  push    r14
0x18002a287  sub     rsp, 260h
0x18002a28e  mov     rax, cs:__security_cookie
0x18002a295  xor     rax, rsp
0x18002a298  mov     [rsp+288h+var_38], rax
0x18002a2a0  mov     ebp, r9d
0x18002a2a3  mov     rsi, r8
0x18002a2a6  mov     rdi, rdx
0x18002a2a9  mov     r14, rcx
0x18002a2ac  mov     [rsp+288h+var_258], rcx
0x18002a2b1  lea     rbx, [rcx+8]
0x18002a2b5  lea     rcx, [rbx+18h]
0x18002a2b9  mov     [rbx+8], rcx
0x18002a2bd  mov     qword ptr [rbx+10h], 41h ; 'A'
0x18002a2c5  xor     eax, eax
0x18002a2c7  mov     [rcx], ax
0x18002a2ca  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x18002a2d1  mov     [rbx], rax
0x18002a2d4  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18002a2db  mov     [r14], rax
0x18002a2de  mov     dword ptr [r14+0A8h], 1
0x18002a2e9  xor     ecx, ecx; dwErrCode
0x18002a2eb  call    cs:__imp_SetLastError
0x18002a2f1  mov     rdx, [rdi+10h]
0x18002a2f5  mov     rcx, rbx
0x18002a2f8  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18002a2fd  mov     rcx, rbx; struct CLMString *
0x18002a300  call    ?AppendSlashIf@@YAXAEAVCLMString@@@Z; AppendSlashIf(CLMString &)
0x18002a305  mov     rax, [rbx]
0x18002a308  or      r9d, 0FFFFFFFFh
0x18002a30c  mov     r8d, [rbx+14h]
0x18002a310  mov     rdx, rsi
0x18002a313  mov     rcx, rbx
0x18002a316  mov     rax, [rax+20h]
0x18002a31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a31f  mov     rbx, [rdi+0B0h]
0x18002a326  lea     rdi, [r14+0B0h]
0x18002a32d  lea     r9, [rsp+288h+var_248]; wchar_t *
0x18002a332  mov     r8, rsi; wchar_t *
0x18002a335  mov     rdx, rbx; HKEY
0x18002a338  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x18002a33d  lea     rdx, [rsp+288h+var_248]
0x18002a342  test    al, al
0x18002a344  cmovz   rdx, rsi; lpSubKey
0x18002a348  mov     qword ptr [rsp+288h+phkResult], rdi; phkResult
0x18002a34d  mov     r9d, ebp; samDesired
0x18002a350  xor     r8d, r8d; ulOptions
0x18002a353  mov     rcx, rbx; hKey
0x18002a356  call    cs:__imp_RegOpenKeyExW
0x18002a35c  test    eax, eax
0x18002a35e  jz      short loc_18002A370
0x18002a360  mov     qword ptr [rdi], 0
0x18002a367  mov     ecx, eax; dwErrCode
0x18002a369  call    cs:__imp_SetLastError
0x18002a36f  nop
0x18002a370  mov     rax, r14
0x18002a373  mov     rcx, [rsp+288h+var_38]
0x18002a37b  xor     rcx, rsp; StackCookie
0x18002a37e  call    __security_check_cookie
0x18002a383  add     rsp, 260h
0x18002a38a  pop     r14
0x18002a38c  pop     rdi
0x18002a38d  pop     rsi
0x18002a38e  pop     rbp
0x18002a38f  pop     rbx
0x18002a390  retn
```
