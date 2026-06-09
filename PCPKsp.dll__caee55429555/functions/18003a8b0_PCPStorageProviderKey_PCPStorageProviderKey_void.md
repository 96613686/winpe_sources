# PCPStorageProviderKey::PCPStorageProviderKey(void)

- ea: `0x18003a8b0`
- end: `0x18003aad9`
- name: `??0PCPStorageProviderKey@@QEAA@XZ`
- size: `553`
- prototype: `PCPStorageProviderKey *__fastcall(PCPStorageProviderKey *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800204a0`
- `0x180038aa0`
- `0x18003a340`
- `0x18003a868`
- `0x18005aebc`
- `0x1800604d0`

## callees

- `0x18003a8b0`
- `0x1800764d0`
- `0x18007704c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18003a9d9`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18003a9d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003aaa1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003aaa1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003aa86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003aa86`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003aa41`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003aa41`
- `RPCRT4!UuidCreate` at `0x18003a9ec`
- `RPCRT4!UuidCreate` at `0x18003a9ec`

## string_xrefs

- `0x18003aa1c`: `System\CurrentControlSet\services\TPM`

## pseudocode

```c
PCPStorageProviderKey *__fastcall PCPStorageProviderKey::PCPStorageProviderKey(PCPStorageProviderKey *this)
{
  _DWORD *pvData; // rsi
  DWORD pcbData[3]; // [rsp+44h] [rbp-244h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-238h] BYREF

  *(_DWORD *)this = 1263551312;
  pvData = (_DWORD *)((char *)this + 4);
  *((_DWORD *)this + 1) = 0;
  *(_OWORD *)((char *)this + 8) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 10) = 0;
  *(GUID *)((char *)this + 56) = GUID_NULL;
  memset_0((char *)this + 88, 0, 0x208u);
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_DWORD *)this + 158) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_DWORD *)this + 162) = 0;
  *((_BYTE *)this + 652) = 0;
  *((_DWORD *)this + 164) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_DWORD *)this + 170) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_DWORD *)this + 174) = 0;
  *((_BYTE *)this + 700) = 0;
  *((_DWORD *)this + 176) = 0;
  *((_BYTE *)this + 708) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_DWORD *)this + 180) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_BYTE *)this + 736) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_DWORD *)this + 188) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 98) = 0;
  *((_DWORD *)this + 18) = rand();
  UuidCreate((UUID *)((char *)this + 56));
  memset_0(SubKey, 0, 0x208u);
  if ( (int)RtlGetPersistedStateLocation(L"TpmRegDriverTpm", 0, L"System\\CurrentControlSet\\services\\TPM", 0) >= 0 )
  {
    pcbData[0] = 4;
    RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ProviderOperationFlags", 0x18u, 0, pvData, pcbData);
    if ( (*pvData & 1) == 0 )
      InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 8), 0x400u);
  }
  return this;
}

```

## disassembly

```asm
0x18003a8b0  mov     [rsp+arg_8], rbx
0x18003a8b5  mov     [rsp+arg_10], rbp
0x18003a8ba  push    rsi
0x18003a8bb  push    rdi
0x18003a8bc  push    r14
0x18003a8be  sub     rsp, 270h
0x18003a8c5  mov     rax, cs:__security_cookie
0x18003a8cc  xor     rax, rsp
0x18003a8cf  mov     [rsp+288h+var_28], rax
0x18003a8d7  mov     dword ptr [rcx], 4B504350h
0x18003a8dd  lea     rsi, [rcx+4]
0x18003a8e1  xor     r14d, r14d
0x18003a8e4  xorps   xmm0, xmm0
0x18003a8e7  mov     [rsi], r14d
0x18003a8ea  xor     eax, eax
0x18003a8ec  movups  xmmword ptr [rcx+8], xmm0
0x18003a8f0  mov     rbx, rcx
0x18003a8f3  xor     edx, edx; Val
0x18003a8f5  movups  xmmword ptr [rcx+18h], xmm0
0x18003a8f9  mov     [rcx+28h], rax
0x18003a8fd  mov     r8d, 208h; Size
0x18003a903  mov     [rcx+30h], r14
0x18003a907  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003a90e  mov     [rcx+48h], r14d
0x18003a912  mov     [rcx+50h], r14
0x18003a916  movups  xmmword ptr [rcx+38h], xmm0
0x18003a91a  add     rcx, 58h ; 'X'; void *
0x18003a91e  call    memset_0
0x18003a923  mov     [rbx+260h], r14
0x18003a92a  mov     [rbx+268h], r14
0x18003a931  mov     [rbx+270h], r14
0x18003a938  mov     [rbx+278h], r14d
0x18003a93f  mov     [rbx+280h], r14
0x18003a946  mov     [rbx+288h], r14d
0x18003a94d  mov     [rbx+28Ch], r14b
0x18003a954  mov     [rbx+290h], r14d
0x18003a95b  mov     [rbx+298h], r14
0x18003a962  mov     [rbx+2A0h], r14
0x18003a969  mov     [rbx+2A8h], r14d
0x18003a970  mov     [rbx+2B0h], r14
0x18003a977  mov     [rbx+2B8h], r14d
0x18003a97e  mov     [rbx+2BCh], r14b
0x18003a985  mov     [rbx+2C0h], r14d
0x18003a98c  mov     [rbx+2C4h], r14b
0x18003a993  mov     [rbx+2C8h], r14
0x18003a99a  mov     [rbx+2D0h], r14d
0x18003a9a1  mov     [rbx+2D8h], r14
0x18003a9a8  mov     [rbx+2E0h], r14b
0x18003a9af  mov     [rbx+2E8h], r14
0x18003a9b6  mov     [rbx+2F0h], r14d
0x18003a9bd  mov     [rbx+2F8h], r14
0x18003a9c4  mov     [rbx+300h], r14
0x18003a9cb  mov     [rbx+308h], r14
0x18003a9d2  mov     [rbx+310h], r14
0x18003a9d9  call    cs:__imp_rand
0x18003a9e0  nop     dword ptr [rax+rax+00h]
0x18003a9e5  lea     rcx, [rbx+38h]; Uuid
0x18003a9e9  mov     [rbx+48h], eax
0x18003a9ec  call    cs:__imp_UuidCreate
0x18003a9f3  nop     dword ptr [rax+rax+00h]
0x18003a9f8  xor     edx, edx; Val
0x18003a9fa  lea     rcx, [rsp+288h+SubKey]; void *
0x18003a9ff  mov     r8d, 208h; Size
0x18003aa05  call    memset_0
0x18003aa0a  lea     rax, [rsp+288h+var_248]
0x18003aa0f  mov     [rsp+288h+var_248], 208h
0x18003aa17  mov     [rsp+288h+pcbData], rax
0x18003aa1c  lea     r8, aSystemCurrentc_2; "System\\CurrentControlSet\\services\\TP"...
0x18003aa23  lea     rax, [rsp+288h+SubKey]
0x18003aa28  mov     dword ptr [rsp+288h+pvData], 208h
0x18003aa30  xor     r9d, r9d
0x18003aa33  mov     [rsp+288h+pdwType], rax
0x18003aa38  xor     edx, edx
0x18003aa3a  lea     rcx, aTpmregdrivertp; "TpmRegDriverTpm"
0x18003aa41  call    cs:__imp_RtlGetPersistedStateLocation
0x18003aa48  nop     dword ptr [rax+rax+00h]
0x18003aa4d  test    eax, eax
0x18003aa4f  js      short loc_18003AAAD
0x18003aa51  lea     rax, [rsp+288h+var_244]
0x18003aa56  mov     [rsp+288h+var_244], 4
0x18003aa5e  mov     [rsp+288h+pcbData], rax; pcbData
0x18003aa63  lea     r8, Value; "ProviderOperationFlags"
0x18003aa6a  mov     [rsp+288h+pvData], rsi; pvData
0x18003aa6f  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18003aa74  mov     r9d, 18h; dwFlags
0x18003aa7a  mov     [rsp+288h+pdwType], r14; pdwType
0x18003aa7f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003aa86  call    cs:__imp_RegGetValueW
0x18003aa8d  nop     dword ptr [rax+rax+00h]
0x18003aa92  mov     eax, [rsi]
0x18003aa94  test    al, 1
0x18003aa96  jnz     short loc_18003AAAD
0x18003aa98  mov     edx, 400h; dwSpinCount
0x18003aa9d  lea     rcx, [rbx+8]; lpCriticalSection
0x18003aaa1  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003aaa8  nop     dword ptr [rax+rax+00h]
0x18003aaad  mov     rax, rbx
0x18003aab0  mov     rcx, [rsp+288h+var_28]
0x18003aab8  xor     rcx, rsp; StackCookie
0x18003aabb  call    __security_check_cookie
0x18003aac0  lea     r11, [rsp+288h+var_18]
0x18003aac8  mov     rbx, [r11+28h]
0x18003aacc  mov     rbp, [r11+30h]
0x18003aad0  mov     rsp, r11
0x18003aad3  pop     r14
0x18003aad5  pop     rdi
0x18003aad6  pop     rsi
0x18003aad7  retn
```
