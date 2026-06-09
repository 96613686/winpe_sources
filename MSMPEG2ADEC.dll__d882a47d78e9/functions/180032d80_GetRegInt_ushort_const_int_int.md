# GetRegInt(ushort const *,int,int)

- ea: `0x180032d80`
- end: `0x180032ea4`
- name: `?GetRegInt@@YAHPEBGHH@Z`
- size: `292`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800108f0`

## callees

- `0x180032d80`
- `0x180032f00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032e55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032e55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032e21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032e21`

## pseudocode

```c
__int64 __fastcall GetRegInt(LPCWSTR lpValueName, unsigned int a2)
{
  int v2; // edi
  __int64 v5; // rax
  const WCHAR *v6; // rdx
  LSTATUS v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !lpSubKey )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(&xmmword_1800ADB00 + v5) );
    if ( v5 || (int)UTIL_REGGetModuleBase() >= 0 )
      lpSubKey = &xmmword_1800ADB00;
  }
  cbData = 8;
  while ( 1 )
  {
    v6 = (const WCHAR *)qword_1800ADAF0;
    if ( v2 < 2 )
      v6 = lpSubKey;
    if ( v6 )
    {
      if ( !RegOpenKeyExW((HKEY)qword_180095458[v2], v6, 0, 0x20019u, &hKey) )
      {
        v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, Data, &cbData);
        RegCloseKey(hKey);
        if ( !v7 )
          break;
      }
    }
    if ( !qword_180095458[++v2] )
      return a2;
  }
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x180032d80  mov     [rsp+arg_0], rbx
0x180032d85  mov     [rsp+arg_8], rbp
0x180032d8a  mov     [rsp+cbData], r8d
0x180032d8f  push    rsi
0x180032d90  push    rdi
0x180032d91  push    r14
0x180032d93  sub     rsp, 40h
0x180032d97  xor     edi, edi
0x180032d99  mov     ebp, edx
0x180032d9b  cmp     cs:lpSubKey, rdi
0x180032da2  mov     rsi, rcx
0x180032da5  mov     [rsp+58h+hKey], rdi
0x180032daa  mov     [rsp+58h+Type], edi
0x180032dae  mov     [rsp+58h+cbData], edi
0x180032db2  jnz     short loc_180032DE0
0x180032db4  lea     rbx, xmmword_1800ADB00
0x180032dbb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180032dc2  inc     rax
0x180032dc5  cmp     [rbx+rax*2], di
0x180032dc9  jnz     short loc_180032DC2
0x180032dcb  test    rax, rax
0x180032dce  jnz     short loc_180032DD9
0x180032dd0  call    ?UTIL_REGGetModuleBase@@YAHW4ERegModule@@PEAG_K_N@Z; UTIL_REGGetModuleBase(ERegModule,ushort *,unsigned __int64,bool)
0x180032dd5  test    eax, eax
0x180032dd7  js      short loc_180032DE0
0x180032dd9  mov     cs:lpSubKey, rbx
0x180032de0  mov     [rsp+58h+cbData], 8
0x180032de8  lea     r14, qword_180095458
0x180032def  nop
0x180032df0  mov     rdx, cs:qword_1800ADAF0
0x180032df7  cmp     edi, 2
0x180032dfa  cmovl   rdx, cs:lpSubKey; lpSubKey
0x180032e02  test    rdx, rdx
0x180032e05  jz      short loc_180032E78
0x180032e07  lea     rax, [rsp+58h+hKey]
0x180032e0c  movsxd  rcx, edi
0x180032e0f  mov     r9d, 20019h; samDesired
0x180032e15  mov     [rsp+58h+phkResult], rax; phkResult
0x180032e1a  xor     r8d, r8d; ulOptions
0x180032e1d  mov     rcx, [r14+rcx*8]; hKey
0x180032e21  call    cs:__imp_RegOpenKeyExW
0x180032e28  nop     dword ptr [rax+rax+00h]
0x180032e2d  test    eax, eax
0x180032e2f  jnz     short loc_180032E78
0x180032e31  mov     rcx, [rsp+58h+hKey]; hKey
0x180032e36  lea     rax, [rsp+58h+cbData]
0x180032e3b  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180032e40  lea     r9, [rsp+58h+Type]; lpType
0x180032e45  lea     rax, [rsp+58h+Data]
0x180032e4a  xor     r8d, r8d; lpReserved
0x180032e4d  mov     rdx, rsi; lpValueName
0x180032e50  mov     [rsp+58h+phkResult], rax; lpData
0x180032e55  call    cs:__imp_RegQueryValueExW
0x180032e5c  nop     dword ptr [rax+rax+00h]
0x180032e61  mov     rcx, [rsp+58h+hKey]; hKey
0x180032e66  mov     ebx, eax
0x180032e68  call    cs:__imp_RegCloseKey
0x180032e6f  nop     dword ptr [rax+rax+00h]
0x180032e74  test    ebx, ebx
0x180032e76  jz      short loc_180032E9E
0x180032e78  inc     edi
0x180032e7a  movsxd  rax, edi
0x180032e7d  cmp     qword ptr [r14+rax*8], 0
0x180032e82  jnz     loc_180032DF0
0x180032e88  mov     eax, ebp
0x180032e8a  mov     rbx, [rsp+58h+arg_0]
0x180032e8f  mov     rbp, [rsp+58h+arg_8]
0x180032e94  add     rsp, 40h
0x180032e98  pop     r14
0x180032e9a  pop     rdi
0x180032e9b  pop     rsi
0x180032e9c  retn
0x180032e9e  mov     eax, dword ptr [rsp+58h+Data]
0x180032ea2  jmp     short loc_180032E8A
```
