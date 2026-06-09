# CFineReaderShim::SaveKey(ushort const *,HKEY__ *,ushort *)

- ea: `0x180035b3c`
- end: `0x180035c34`
- name: `?SaveKey@CFineReaderShim@@AEAAKPEBGPEAUHKEY__@@PEAG@Z`
- size: `248`
- prototype: `unsigned int(CFineReaderShim *__hidden this, const unsigned __int16 *, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180035214`

## callees

- `0x180001cf0`
- `0x1800028e0`
- `0x180035b3c`
- `0x1800543c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180035c12`
- `ADVAPI32!RegCloseKey` at `0x180035c12`
- `ADVAPI32!RegSaveKeyW` at `0x180035bda`
- `ADVAPI32!RegSaveKeyW` at `0x180035bda`
- `ADVAPI32!RegOpenKeyExW` at `0x180035bc1`
- `ADVAPI32!RegOpenKeyExW` at `0x180035bc1`

## string_xrefs

- `0x180035be6`: `Failed to save key fine reader migration shim [%d]`
- `0x180035bf7`: `CFineReaderShim::SaveKey`

## pseudocode

```c
__int64 __fastcall CFineReaderShim::SaveKey(
        CFineReaderShim *this,
        const unsigned __int16 *a2,
        HKEY a3,
        unsigned __int16 *a4)
{
  __int64 v5; // r9
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-248h] BYREF
  wchar_t Buffer[264]; // [rsp+40h] [rbp-238h] BYREF

  hKey = 0;
  v5 = *((_QWORD *)this + 1);
  if ( a2 )
    swprintf_s(Buffer, 0x103u, L"%s\\%s.%s.reg", v5, a2, a4);
  else
    swprintf_s(Buffer, 0x103u, L"%s\\%s.reg", v5, a4);
  v7 = RegOpenKeyExW(a3, a4, 0, 0x20019u, &hKey);
  if ( !v7 )
  {
    v8 = RegSaveKeyW(hKey, Buffer, 0);
    v7 = v8;
    if ( v8 )
      AslLogCallPrintf(1, "CFineReaderShim::SaveKey", 691, "Failed to save key fine reader migration shim [%d]", v8);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180035b3c  push    rbx
0x180035b3e  push    rdi
0x180035b3f  sub     rsp, 268h
0x180035b46  mov     rax, cs:__security_cookie
0x180035b4d  xor     rax, rsp
0x180035b50  mov     [rsp+278h+var_28], rax
0x180035b58  mov     [rsp+278h+hKey], 0
0x180035b61  mov     rbx, r9
0x180035b64  mov     r9, [rcx+8]
0x180035b68  lea     rcx, [rsp+278h+Buffer]; Buffer
0x180035b6d  mov     rdi, r8
0x180035b70  test    rdx, rdx
0x180035b73  jnz     short loc_180035B8D
0x180035b75  lea     r8, aSSReg; "%s\\%s.reg"
0x180035b7c  mov     [rsp+278h+phkResult], rbx
0x180035b81  mov     edx, 103h; BufferCount
0x180035b86  call    swprintf_s
0x180035b8b  jmp     short loc_180035BA8
0x180035b8d  mov     [rsp+278h+var_250], rbx
0x180035b92  lea     r8, aSSSReg; "%s\\%s.%s.reg"
0x180035b99  mov     [rsp+278h+phkResult], rdx
0x180035b9e  mov     edx, 103h; BufferCount
0x180035ba3  call    swprintf_s
0x180035ba8  lea     rax, [rsp+278h+hKey]
0x180035bad  mov     r9d, 20019h; samDesired
0x180035bb3  xor     r8d, r8d; ulOptions
0x180035bb6  mov     [rsp+278h+phkResult], rax; phkResult
0x180035bbb  mov     rdx, rbx; lpSubKey
0x180035bbe  mov     rcx, rdi; hKey
0x180035bc1  call    cs:__imp_RegOpenKeyExW
0x180035bc7  mov     ebx, eax
0x180035bc9  test    eax, eax
0x180035bcb  jnz     short loc_180035C08
0x180035bcd  mov     rcx, [rsp+278h+hKey]; hKey
0x180035bd2  lea     rdx, [rsp+278h+Buffer]; lpFile
0x180035bd7  xor     r8d, r8d; lpSecurityAttributes
0x180035bda  call    cs:__imp_RegSaveKeyW
0x180035be0  mov     ebx, eax
0x180035be2  test    eax, eax
0x180035be4  jz      short loc_180035C08
0x180035be6  lea     r9, aFailedToSaveKe; "Failed to save key fine reader migratio"...
0x180035bed  mov     dword ptr [rsp+278h+phkResult], eax
0x180035bf1  mov     r8d, 2B3h
0x180035bf7  lea     rdx, aCfinereadershi_2; "CFineReaderShim::SaveKey"
0x180035bfe  mov     ecx, 1
0x180035c03  call    AslLogCallPrintf
0x180035c08  mov     rcx, [rsp+278h+hKey]; hKey
0x180035c0d  test    rcx, rcx
0x180035c10  jz      short loc_180035C18
0x180035c12  call    cs:__imp_RegCloseKey
0x180035c18  mov     eax, ebx
0x180035c1a  mov     rcx, [rsp+278h+var_28]
0x180035c22  xor     rcx, rsp; StackCookie
0x180035c25  call    __security_check_cookie
0x180035c2a  add     rsp, 268h
0x180035c31  pop     rdi
0x180035c32  pop     rbx
0x180035c33  retn
```
