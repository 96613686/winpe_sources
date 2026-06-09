# CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)

- ea: `0x140028588`
- end: `0x1400286a5`
- name: `??0CRegistry@@QEAA@PEAV0@PEB_WK@Z`
- size: `285`
- prototype: `CRegistry *__fastcall(CRegistry *this, struct CRegistry *, wchar_t *, REGSAM)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002290c`
- `0x140028890`
- `0x140028d20`

## callees

- `0x1400030a0`
- `0x140028218`
- `0x140028588`
- `0x140028720`
- `0x14002aac4`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400285fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002867d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400285fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002867d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002866a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002866a`

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
  (*(void (__fastcall **)(struct CLMString *, _QWORD, _QWORD, __int64))(*(_QWORD *)v8 + 32LL))(
    v8,
    *((_QWORD *)a2 + 2),
    0,
    0xFFFFFFFFLL);
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
0x140028588  push    rbx
0x14002858a  push    rbp
0x14002858b  push    rsi
0x14002858c  push    rdi
0x14002858d  push    r14
0x14002858f  sub     rsp, 260h
0x140028596  mov     [rsp+288h+var_258], 0FFFFFFFFFFFFFFFEh
0x14002859f  mov     rax, cs:__security_cookie
0x1400285a6  xor     rax, rsp
0x1400285a9  mov     [rsp+288h+var_38], rax
0x1400285b1  mov     ebp, r9d
0x1400285b4  mov     rsi, r8
0x1400285b7  mov     rdi, rdx
0x1400285ba  mov     r14, rcx
0x1400285bd  mov     [rsp+288h+var_250], rcx
0x1400285c2  lea     rbx, [rcx+8]
0x1400285c6  lea     rcx, [rbx+18h]
0x1400285ca  mov     [rbx+8], rcx
0x1400285ce  mov     qword ptr [rbx+10h], 41h ; 'A'
0x1400285d6  xor     eax, eax
0x1400285d8  mov     [rcx], ax
0x1400285db  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1400285e2  mov     [rbx], rax
0x1400285e5  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1400285ec  mov     [r14], rax
0x1400285ef  mov     dword ptr [r14+0A8h], 1
0x1400285fa  xor     ecx, ecx; dwErrCode
0x1400285fc  call    cs:__imp_SetLastError
0x140028602  mov     rax, [rbx]
0x140028605  or      r9d, 0FFFFFFFFh
0x140028609  xor     r8d, r8d
0x14002860c  mov     rdx, [rdi+10h]
0x140028610  mov     rcx, rbx
0x140028613  mov     rax, [rax+20h]
0x140028617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002861c  mov     rcx, rbx; struct CLMString *
0x14002861f  call    ?AppendSlashIf@@YAXAEAVCLMString@@@Z; AppendSlashIf(CLMString &)
0x140028624  or      r8d, 0FFFFFFFFh; unsigned int
0x140028628  mov     rdx, rsi; wchar_t *
0x14002862b  mov     rcx, rbx; this
0x14002862e  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x140028633  mov     rbx, [rdi+0B0h]
0x14002863a  lea     rdi, [r14+0B0h]
0x140028641  lea     r9, [rsp+288h+var_248]; wchar_t *
0x140028646  mov     r8, rsi; wchar_t *
0x140028649  mov     rdx, rbx; HKEY
0x14002864c  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x140028651  lea     rdx, [rsp+288h+var_248]
0x140028656  test    al, al
0x140028658  cmovz   rdx, rsi; lpSubKey
0x14002865c  mov     qword ptr [rsp+288h+phkResult], rdi; phkResult
0x140028661  mov     r9d, ebp; samDesired
0x140028664  xor     r8d, r8d; ulOptions
0x140028667  mov     rcx, rbx; hKey
0x14002866a  call    cs:__imp_RegOpenKeyExW
0x140028670  test    eax, eax
0x140028672  jz      short loc_140028684
0x140028674  mov     qword ptr [rdi], 0
0x14002867b  mov     ecx, eax; dwErrCode
0x14002867d  call    cs:__imp_SetLastError
0x140028683  nop
0x140028684  mov     rax, r14
0x140028687  mov     rcx, [rsp+288h+var_38]
0x14002868f  xor     rcx, rsp; StackCookie
0x140028692  call    __security_check_cookie
0x140028697  add     rsp, 260h
0x14002869e  pop     r14
0x1400286a0  pop     rdi
0x1400286a1  pop     rsi
0x1400286a2  pop     rbp
0x1400286a3  pop     rbx
0x1400286a4  retn
```
