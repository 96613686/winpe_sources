# CProcessStateManager::ResetIsBoot(void)

- ea: `0x18004b4ec`
- end: `0x18004b581`
- name: `?ResetIsBoot@CProcessStateManager@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059510`

## callees

- `0x18004b4ec`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004b570`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004b570`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004b500`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004b500`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b530`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b530`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b562`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004b549`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004b549`

## pseudocode

```c
void __fastcall CProcessStateManager::ResetIsBoot(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rbx
  HKEY v3; // rcx
  HKEY v4; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = this + 14;
  AcquireSRWLockExclusive(this + 14);
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
          0,
          0x2001Fu,
          &hKey) )
  {
    v3 = hKey;
    LOBYTE(this[15].Ptr) = 0;
    RegDeleteValueW(v3, L"BootLogon");
  }
  v4 = hKey;
  hKey = 0;
  if ( v4 )
    RegCloseKey(v4);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x18004b4ec  mov     [rsp+arg_8], rbx
0x18004b4f1  push    rdi
0x18004b4f2  sub     rsp, 30h
0x18004b4f6  lea     rbx, [rcx+70h]
0x18004b4fa  mov     rdi, rcx
0x18004b4fd  mov     rcx, rbx; SRWLock
0x18004b500  call    cs:__imp_AcquireSRWLockExclusive
0x18004b506  lea     rax, [rsp+38h+hKey]
0x18004b50b  mov     [rsp+38h+hKey], 0
0x18004b514  mov     r9d, 2001Fh; samDesired
0x18004b51a  mov     [rsp+38h+phkResult], rax; phkResult
0x18004b51f  xor     r8d, r8d; ulOptions
0x18004b522  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004b529  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b530  call    cs:__imp_RegOpenKeyExW
0x18004b536  test    eax, eax
0x18004b538  jnz     short loc_18004B54F
0x18004b53a  mov     rcx, [rsp+38h+hKey]; hKey
0x18004b53f  lea     rdx, aBootlogon; "BootLogon"
0x18004b546  mov     [rdi+78h], al
0x18004b549  call    cs:__imp_RegDeleteValueW
0x18004b54f  mov     rcx, [rsp+38h+hKey]; hKey
0x18004b554  mov     [rsp+38h+hKey], 0
0x18004b55d  test    rcx, rcx
0x18004b560  jz      short loc_18004B568
0x18004b562  call    cs:__imp_RegCloseKey
0x18004b568  test    rbx, rbx
0x18004b56b  jz      short loc_18004B576
0x18004b56d  mov     rcx, rbx; SRWLock
0x18004b570  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b576  mov     rbx, [rsp+38h+arg_8]
0x18004b57b  add     rsp, 30h
0x18004b57f  pop     rdi
0x18004b580  retn
```
