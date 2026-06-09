# SetSecRegValues(HKEY__ *,_PERUSERSECTIONW *,int)

- ea: `0x18000ed4c`
- end: `0x18000ef89`
- name: `?SetSecRegValues@@YAXPEAUHKEY__@@PEAU_PERUSERSECTIONW@@H@Z`
- size: `573`
- prototype: `void __fastcall(HKEY hKey, struct _PERUSERSECTIONW *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010d50`

## callees

- `0x18000279c`
- `0x18000ed4c`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000ee23`
- `ADVAPI32!RegSetValueExW` at `0x18000ee63`
- `ADVAPI32!RegSetValueExW` at `0x18000eeb3`
- `ADVAPI32!RegSetValueExW` at `0x18000eef3`
- `ADVAPI32!RegSetValueExW` at `0x18000ef2d`
- `ADVAPI32!RegSetValueExW` at `0x18000ef57`
- `ADVAPI32!RegSetValueExW` at `0x18000ee23`
- `ADVAPI32!RegSetValueExW` at `0x18000ee63`
- `ADVAPI32!RegSetValueExW` at `0x18000eeb3`
- `ADVAPI32!RegSetValueExW` at `0x18000eef3`
- `ADVAPI32!RegSetValueExW` at `0x18000ef2d`
- `ADVAPI32!RegSetValueExW` at `0x18000ef57`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee73`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee73`

## string_xrefs

- `0x18000ef45`: `IsInstalled`
- `0x18000ee1c`: `StubPath`
- `0x18000eee1`: `ComponentID`
- `0x18000edf1`: `RealStubPath`

## pseudocode

```c
void __fastcall SetSecRegValues(HKEY hKey, struct _PERUSERSECTIONW *a2, int a3)
{
  __int64 v4; // rbx
  unsigned __int16 *szStub; // rcx
  __int64 v8; // rax
  DWORD v9; // r9d
  const WCHAR *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  BYTE *lpData; // [rsp+20h] [rbp-848h]
  DWORD cbData; // [rsp+28h] [rbp-840h]
  unsigned __int16 Data[1024]; // [rsp+30h] [rbp-838h] BYREF

  v4 = -1;
  szStub = a2->szStub;
  if ( a2->szStub[0] )
  {
    if ( ctx < 2u )
    {
      v11 = -1;
      do
        ++v11;
      while ( szStub[v11] );
      v9 = 1;
      cbData = 2 * v11 + 2;
      lpData = (BYTE *)a2->szStub;
    }
    else
    {
      AddEnvInPath(szStub, Data, 0x400u);
      v8 = -1;
      do
        ++v8;
      while ( Data[v8] );
      v9 = 2;
      cbData = 2 * v8 + 2;
      lpData = (BYTE *)Data;
    }
    if ( a3 )
      v10 = L"RealStubPath";
    else
      v10 = L"StubPath";
    RegSetValueExW(hKey, v10, 0, v9, lpData, cbData);
  }
  if ( a2->szVersion[0] )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2->szVersion[v12] );
    RegSetValueExW(hKey, L"Version", 0, 1u, (const BYTE *)a2->szVersion, 2 * v12 + 2);
    RegDeleteValueW(hKey, L"QFEVersion");
  }
  if ( a2->szLocale[0] )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2->szLocale[v13] );
    RegSetValueExW(hKey, L"Locale", 0, 1u, (const BYTE *)a2->szLocale, 2 * v13 + 2);
  }
  if ( a2->szCompID[0] )
  {
    v14 = -1;
    do
      ++v14;
    while ( a2->szCompID[v14] );
    RegSetValueExW(hKey, L"ComponentID", 0, 1u, (const BYTE *)a2->szCompID, 2 * v14 + 2);
  }
  if ( a2->szDispName[0] )
  {
    do
      ++v4;
    while ( a2->szDispName[v4] );
    RegSetValueExW(hKey, &word_18001DE6C, 0, 1u, (const BYTE *)a2->szDispName, 2 * v4 + 2);
  }
  RegSetValueExW(hKey, L"IsInstalled", 0, 4u, (const BYTE *)&a2->dwIsInstalled, 4u);
}

```

## disassembly

```asm
0x18000ed4c  mov     [rsp+arg_10], rbx
0x18000ed51  mov     [rsp+arg_18], rbp
0x18000ed56  push    rsi
0x18000ed57  push    rdi
0x18000ed58  push    r12
0x18000ed5a  push    r14
0x18000ed5c  push    r15
0x18000ed5e  sub     rsp, 840h
0x18000ed65  mov     rax, cs:__security_cookie
0x18000ed6c  xor     rax, rsp
0x18000ed6f  mov     [rsp+868h+var_38], rax
0x18000ed77  mov     rdi, rcx
0x18000ed7a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ed7e  lea     rcx, [rdx+18Ah]; unsigned __int16 *
0x18000ed85  xor     r14d, r14d
0x18000ed88  mov     ebp, r8d
0x18000ed8b  mov     rsi, rdx
0x18000ed8e  mov     r12d, 1
0x18000ed94  cmp     [rcx], r14w
0x18000ed98  jz      loc_18000EE29
0x18000ed9e  lea     r15d, [r12+1]
0x18000eda3  cmp     cs:?ctx@@3UADVCONTEXTW@@A, r15w; ADVCONTEXTW ctx
0x18000edab  jb      short loc_18000EDFA
0x18000edad  mov     r8d, 400h; unsigned int
0x18000edb3  lea     rdx, [rsp+868h+Data]; unsigned __int16 *
0x18000edb8  call    ?AddEnvInPath@@YAHPEBGPEAGK@Z; AddEnvInPath(ushort const *,ushort *,ulong)
0x18000edbd  lea     rcx, [rsp+868h+Data]
0x18000edc2  mov     rax, rbx
0x18000edc5  inc     rax
0x18000edc8  cmp     [rcx+rax*2], r14w
0x18000edcd  jnz     short loc_18000EDC5
0x18000edcf  lea     eax, ds:2[rax*2]
0x18000edd6  mov     r9d, r15d; dwType
0x18000edd9  mov     [rsp+868h+cbData], eax; cbData
0x18000eddd  lea     rax, [rsp+868h+Data]
0x18000ede2  mov     [rsp+868h+lpData], rax; lpData
0x18000ede7  xor     r8d, r8d; Reserved
0x18000edea  mov     rcx, rdi; hKey
0x18000eded  test    ebp, ebp
0x18000edef  jz      short loc_18000EE1C
0x18000edf1  lea     rdx, aRealstubpath; "RealStubPath"
0x18000edf8  jmp     short loc_18000EE23
0x18000edfa  mov     rax, rbx
0x18000edfd  inc     rax
0x18000ee00  cmp     [rcx+rax*2], r14w
0x18000ee05  jnz     short loc_18000EDFD
0x18000ee07  lea     eax, ds:2[rax*2]
0x18000ee0e  mov     r9d, r12d
0x18000ee11  mov     [rsp+868h+cbData], eax
0x18000ee15  mov     [rsp+868h+lpData], rcx
0x18000ee1a  jmp     short loc_18000EDE7
0x18000ee1c  lea     rdx, aStubpath; "StubPath"
0x18000ee23  call    cs:__imp_RegSetValueExW
0x18000ee29  lea     rcx, [rsi+9AAh]
0x18000ee30  cmp     [rcx], r14w
0x18000ee34  jz      short loc_18000EE79
0x18000ee36  mov     rax, rbx
0x18000ee39  inc     rax
0x18000ee3c  cmp     [rcx+rax*2], r14w
0x18000ee41  jnz     short loc_18000EE39
0x18000ee43  lea     eax, ds:2[rax*2]
0x18000ee4a  mov     r9d, r12d; dwType
0x18000ee4d  mov     [rsp+868h+cbData], eax; cbData
0x18000ee51  lea     rdx, aVersion; "Version"
0x18000ee58  mov     [rsp+868h+lpData], rcx; lpData
0x18000ee5d  xor     r8d, r8d; Reserved
0x18000ee60  mov     rcx, rdi; hKey
0x18000ee63  call    cs:__imp_RegSetValueExW
0x18000ee69  lea     rdx, aQfeversion; "QFEVersion"
0x18000ee70  mov     rcx, rdi; hKey
0x18000ee73  call    cs:__imp_RegDeleteValueW
0x18000ee79  lea     rcx, [rsi+176h]
0x18000ee80  cmp     [rcx], r14w
0x18000ee84  jz      short loc_18000EEB9
0x18000ee86  mov     rax, rbx
0x18000ee89  inc     rax
0x18000ee8c  cmp     [rcx+rax*2], r14w
0x18000ee91  jnz     short loc_18000EE89
0x18000ee93  lea     eax, ds:2[rax*2]
0x18000ee9a  mov     r9d, r12d; dwType
0x18000ee9d  mov     [rsp+868h+cbData], eax; cbData
0x18000eea1  lea     rdx, aLocale; "Locale"
0x18000eea8  mov     [rsp+868h+lpData], rcx; lpData
0x18000eead  xor     r8d, r8d; Reserved
0x18000eeb0  mov     rcx, rdi; hKey
0x18000eeb3  call    cs:__imp_RegSetValueExW
0x18000eeb9  lea     rcx, [rsi+9EAh]
0x18000eec0  cmp     [rcx], r14w
0x18000eec4  jz      short loc_18000EEF9
0x18000eec6  mov     rax, rbx
0x18000eec9  inc     rax
0x18000eecc  cmp     [rcx+rax*2], r14w
0x18000eed1  jnz     short loc_18000EEC9
0x18000eed3  lea     eax, ds:2[rax*2]
0x18000eeda  mov     r9d, r12d; dwType
0x18000eedd  mov     [rsp+868h+cbData], eax; cbData
0x18000eee1  lea     rdx, aComponentid; "ComponentID"
0x18000eee8  mov     [rsp+868h+lpData], rcx; lpData
0x18000eeed  xor     r8d, r8d; Reserved
0x18000eef0  mov     rcx, rdi; hKey
0x18000eef3  call    cs:__imp_RegSetValueExW
0x18000eef9  lea     rcx, [rsi+76h]
0x18000eefd  cmp     [rcx], r14w
0x18000ef01  jz      short loc_18000EF33
0x18000ef03  inc     rbx
0x18000ef06  cmp     [rcx+rbx*2], r14w
0x18000ef0b  jnz     short loc_18000EF03
0x18000ef0d  lea     eax, ds:2[rbx*2]
0x18000ef14  mov     r9d, r12d; dwType
0x18000ef17  mov     [rsp+868h+cbData], eax; cbData
0x18000ef1b  lea     rdx, word_18001DE6C; lpValueName
0x18000ef22  mov     [rsp+868h+lpData], rcx; lpData
0x18000ef27  xor     r8d, r8d; Reserved
0x18000ef2a  mov     rcx, rdi; hKey
0x18000ef2d  call    cs:__imp_RegSetValueExW
0x18000ef33  mov     r9d, 4; dwType
0x18000ef39  lea     rax, [rsi+0AECh]
0x18000ef40  mov     [rsp+868h+cbData], r9d; cbData
0x18000ef45  lea     rdx, aIsinstalled; "IsInstalled"
0x18000ef4c  xor     r8d, r8d; Reserved
0x18000ef4f  mov     [rsp+868h+lpData], rax; lpData
0x18000ef54  mov     rcx, rdi; hKey
0x18000ef57  call    cs:__imp_RegSetValueExW
0x18000ef5d  mov     rcx, [rsp+868h+var_38]
0x18000ef65  xor     rcx, rsp; StackCookie
0x18000ef68  call    __security_check_cookie
0x18000ef6d  lea     r11, [rsp+868h+var_28]
0x18000ef75  mov     rbx, [r11+40h]
0x18000ef79  mov     rbp, [r11+48h]
0x18000ef7d  mov     rsp, r11
0x18000ef80  pop     r15
0x18000ef82  pop     r14
0x18000ef84  pop     r12
0x18000ef86  pop     rdi
0x18000ef87  pop     rsi
0x18000ef88  retn
```
