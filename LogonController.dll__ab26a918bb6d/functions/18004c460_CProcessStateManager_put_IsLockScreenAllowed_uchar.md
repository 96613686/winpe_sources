# CProcessStateManager::put_IsLockScreenAllowed(uchar)

- ea: `0x18004c460`
- end: `0x18004c583`
- name: `?put_IsLockScreenAllowed@CProcessStateManager@@UEAAJE@Z`
- size: `291`
- prototype: `__int64 __fastcall(CProcessStateManager *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18004c460`
- `0x18005d488`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004c550`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004c56b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004c550`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004c56b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004c479`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004c479`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c518`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c518`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004c502`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004c502`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c4d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c4d4`

## pseudocode

```c
__int64 __fastcall CProcessStateManager::put_IsLockScreenAllowed(RTL_SRWLOCK *this, char a2)
{
  RTL_SRWLOCK *v2; // rdi
  int v5; // ebx
  bool v6; // sf
  int dwOptions; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  BOOL Data; // [rsp+78h] [rbp+10h] BYREF

  v2 = this + 12;
  AcquireSRWLockExclusive(this + 12);
  hKey = 0;
  Data = a2 != 0;
  v5 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  if ( !v5 )
  {
    v5 = RegSetValueExW(hKey, L"AllowLockScreen", 0, 4u, (const BYTE *)&Data, 4u);
    if ( hKey != HKEY_LOCAL_MACHINE )
      RegCloseKey(hKey);
  }
  v6 = v5 < 0;
  if ( v5 > 0 )
  {
    v5 = (unsigned __int16)v5 | 0x80070000;
    v6 = v5 < 0;
  }
  if ( v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
      (const char *)(unsigned int)v5,
      dwOptions);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return (unsigned int)v5;
  }
  else
  {
    BYTE1(this[13].Ptr) = a2 != 0;
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return 0;
  }
}

```

## disassembly

```asm
0x18004c460  mov     [rsp+arg_10], rbx
0x18004c465  push    rbp
0x18004c466  push    rsi
0x18004c467  push    rdi
0x18004c468  sub     rsp, 50h
0x18004c46c  lea     rdi, [rcx+60h]
0x18004c470  mov     rbp, rcx
0x18004c473  mov     rcx, rdi; SRWLock
0x18004c476  mov     sil, dl
0x18004c479  call    cs:__imp_AcquireSRWLockExclusive
0x18004c47f  xor     eax, eax
0x18004c481  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18004c48a  test    sil, sil
0x18004c48d  mov     [rsp+68h+hKey], 0
0x18004c496  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004c49d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004c4a4  setnz   al
0x18004c4a7  xor     r9d, r9d; lpClass
0x18004c4aa  mov     [rsp+68h+Data], eax
0x18004c4ae  xor     r8d, r8d; Reserved
0x18004c4b1  lea     rax, [rsp+68h+hKey]
0x18004c4b6  mov     [rsp+68h+phkResult], rax; phkResult
0x18004c4bb  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004c4c4  mov     [rsp+68h+samDesired], 2; samDesired
0x18004c4cc  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18004c4d4  call    cs:__imp_RegCreateKeyExW
0x18004c4da  mov     ebx, eax
0x18004c4dc  test    eax, eax
0x18004c4de  jnz     short loc_18004C51E
0x18004c4e0  mov     rcx, [rsp+68h+hKey]; hKey
0x18004c4e5  lea     r9d, [rax+4]; dwType
0x18004c4e9  lea     rax, [rsp+68h+Data]
0x18004c4ee  mov     [rsp+68h+samDesired], r9d; cbData
0x18004c4f3  xor     r8d, r8d; Reserved
0x18004c4f6  mov     qword ptr [rsp+68h+dwOptions], rax; int
0x18004c4fb  lea     rdx, aAllowlockscree; "AllowLockScreen"
0x18004c502  call    cs:__imp_RegSetValueExW
0x18004c508  mov     rcx, [rsp+68h+hKey]; hKey
0x18004c50d  mov     ebx, eax
0x18004c50f  cmp     rcx, 0FFFFFFFF80000002h
0x18004c516  jz      short loc_18004C51E
0x18004c518  call    cs:__imp_RegCloseKey
0x18004c51e  test    ebx, ebx
0x18004c520  jle     short loc_18004C52D
0x18004c522  movzx   ebx, bx
0x18004c525  or      ebx, 80070000h
0x18004c52b  test    ebx, ebx
0x18004c52d  jns     short loc_18004C55A
0x18004c52f  mov     rcx, [rsp+68h]; this
0x18004c534  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x18004c53b  mov     r9d, ebx; char *
0x18004c53e  mov     edx, 1BEh; void *
0x18004c543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c548  test    rdi, rdi
0x18004c54b  jz      short loc_18004C556
0x18004c54d  mov     rcx, rdi; SRWLock
0x18004c550  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c556  mov     eax, ebx
0x18004c558  jmp     short loc_18004C573
0x18004c55a  test    sil, sil
0x18004c55d  setnz   al
0x18004c560  mov     [rbp+69h], al
0x18004c563  test    rdi, rdi
0x18004c566  jz      short loc_18004C571
0x18004c568  mov     rcx, rdi; SRWLock
0x18004c56b  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c571  xor     eax, eax
0x18004c573  mov     rbx, [rsp+68h+arg_10]
0x18004c57b  add     rsp, 50h
0x18004c57f  pop     rdi
0x18004c580  pop     rsi
0x18004c581  pop     rbp
0x18004c582  retn
```
