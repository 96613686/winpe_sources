# mlib::MRegistryRWBase::write(void)

- ea: `0x18002e380`
- end: `0x18002e3f0`
- name: `?write@MRegistryRWBase@mlib@@UEAAHXZ`
- size: `112`
- prototype: `__int64 __fastcall(mlib::MRegistryRWBase *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004538`
- `0x18001168c`
- `0x18002e19c`

## callees

- `0x180011a94`
- `0x18002e1f8`
- `0x18002e380`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e3d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e3d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3b1`

## pseudocode

```c
__int64 __fastcall mlib::MRegistryRWBase::write(mlib::MRegistryRWBase *this)
{
  unsigned int v2; // esi
  DWORD LastError; // ebx

  v2 = 1;
  if ( !(unsigned int)mlib::RegistryKey::OpenKeyWR(this) )
  {
    v2 = (*(__int64 (__fastcall **)(mlib::MRegistryRWBase *))(*(_QWORD *)this + 32LL))(this);
    LastError = GetLastError();
    *((_BYTE *)this + 65) = v2 == 0;
    mlib::RegistryKey::CloseKey(this);
    SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x18002e380  mov     [rsp+arg_0], rbx
0x18002e385  mov     [rsp+arg_8], rsi
0x18002e38a  push    rdi
0x18002e38b  sub     rsp, 20h
0x18002e38f  mov     rdi, rcx
0x18002e392  mov     esi, 1
0x18002e397  call    ?OpenKeyWR@RegistryKey@mlib@@QEAAHXZ; mlib::RegistryKey::OpenKeyWR(void)
0x18002e39c  test    eax, eax
0x18002e39e  jnz     short loc_18002E3DD
0x18002e3a0  mov     rax, [rdi]
0x18002e3a3  mov     rcx, rdi
0x18002e3a6  mov     rax, [rax+20h]
0x18002e3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3af  mov     esi, eax
0x18002e3b1  call    cs:__imp_GetLastError
0x18002e3b8  nop     dword ptr [rax+rax+00h]
0x18002e3bd  test    esi, esi
0x18002e3bf  mov     ebx, eax
0x18002e3c1  setz    cl
0x18002e3c4  mov     [rdi+41h], cl
0x18002e3c7  mov     rcx, rdi; this
0x18002e3ca  call    ?CloseKey@RegistryKey@mlib@@QEAAXXZ; mlib::RegistryKey::CloseKey(void)
0x18002e3cf  mov     ecx, ebx; dwErrCode
0x18002e3d1  call    cs:__imp_SetLastError
0x18002e3d8  nop     dword ptr [rax+rax+00h]
0x18002e3dd  mov     rbx, [rsp+28h+arg_0]
0x18002e3e2  mov     eax, esi
0x18002e3e4  mov     rsi, [rsp+28h+arg_8]
0x18002e3e9  add     rsp, 20h
0x18002e3ed  pop     rdi
0x18002e3ee  retn
```
