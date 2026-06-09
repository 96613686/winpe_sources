# SetProcessACGPolicy(void)

- ea: `0x140004e5c`
- end: `0x140004f42`
- name: `?SetProcessACGPolicy@@YAXXZ`
- size: `230`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400054fc`

## callees

- `0x140004e5c`
- `0x1400050e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140004e77`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140004e77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004eaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004eaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004f22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004f22`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140004eef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140004eef`

## pseudocode

```c
void SetProcessACGPolicy(void)
{
  bool v0; // bl
  __int64 v1; // r8
  const char *v2; // r9
  BYTE Data[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v5; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  v0 = 1;
  v5 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(2, &v5, 4) )
  {
    hKey = 0;
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Session Manager\\kernel",
           0,
           0x20019u,
           &hKey) )
    {
      goto LABEL_6;
    }
    cbData = 16;
    *(_OWORD *)Data = 0;
    if ( !RegQueryValueExW(hKey, L"MitigationOptions", 0, 0, Data, &cbData) )
      v0 = (*(_QWORD *)Data & 0x3000000000LL) != 0x2000000000LL;
    RegCloseKey(hKey);
    if ( v0 )
LABEL_6:
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, 480, v1, v2);
  }
}

```

## disassembly

```asm
0x140004e5c  push    rbx
0x140004e5e  sub     rsp, 40h
0x140004e62  mov     ebx, 1
0x140004e67  lea     rdx, [rsp+48h+arg_0]
0x140004e6c  mov     [rsp+48h+arg_0], ebx
0x140004e70  lea     r8d, [rbx+3]
0x140004e74  lea     ecx, [rbx+1]
0x140004e77  call    cs:__imp_SetProcessMitigationPolicy
0x140004e7d  test    eax, eax
0x140004e7f  jnz     loc_140004F3C
0x140004e85  lea     rax, [rsp+48h+hKey]
0x140004e8a  mov     [rsp+48h+hKey], 0
0x140004e93  mov     r9d, 20019h; samDesired
0x140004e99  mov     [rsp+48h+phkResult], rax; phkResult
0x140004e9e  xor     r8d, r8d; ulOptions
0x140004ea1  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ses"...
0x140004ea8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004eaf  call    cs:__imp_RegOpenKeyExW
0x140004eb5  test    eax, eax
0x140004eb7  jnz     short loc_140004F2C
0x140004eb9  mov     rcx, [rsp+48h+hKey]; hKey
0x140004ebe  lea     rax, [rsp+48h+cbData]
0x140004ec3  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140004ec8  lea     rdx, ValueName; "MitigationOptions"
0x140004ecf  lea     rax, [rsp+48h+Data]
0x140004ed4  mov     [rsp+48h+cbData], 10h
0x140004edc  xorps   xmm0, xmm0
0x140004edf  mov     [rsp+48h+phkResult], rax; lpData
0x140004ee4  xor     r9d, r9d; lpType
0x140004ee7  xor     r8d, r8d; lpReserved
0x140004eea  movups  xmmword ptr [rsp+48h+Data], xmm0
0x140004eef  call    cs:__imp_RegQueryValueExW
0x140004ef5  test    eax, eax
0x140004ef7  jnz     short loc_140004F1D
0x140004ef9  mov     rcx, qword ptr [rsp+48h+Data]
0x140004efe  mov     rax, 3000000000h
0x140004f08  and     rcx, rax
0x140004f0b  mov     r8, 2000000000h
0x140004f15  xor     eax, eax
0x140004f17  cmp     rcx, r8
0x140004f1a  cmovz   ebx, eax
0x140004f1d  mov     rcx, [rsp+48h+hKey]; hKey
0x140004f22  call    cs:__imp_RegCloseKey
0x140004f28  test    bl, bl
0x140004f2a  jz      short loc_140004F3C
0x140004f2c  mov     rcx, [rsp+48h]; this
0x140004f31  mov     edx, 1E0h; void *
0x140004f36  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140004f3c  add     rsp, 40h
0x140004f40  pop     rbx
0x140004f41  retn
```
