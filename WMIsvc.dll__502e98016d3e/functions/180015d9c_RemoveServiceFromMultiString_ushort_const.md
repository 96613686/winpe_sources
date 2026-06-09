# RemoveServiceFromMultiString(ushort const *)

- ea: `0x180015d9c`
- end: `0x180015f6f`
- name: `?RemoveServiceFromMultiString@@YAJPEBG@Z`
- size: `467`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015560`
- `0x180015a00`

## callees

- `0x1800039f4`
- `0x18000ca20`
- `0x1800103e0`
- `0x180015d9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015dda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015dda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015e16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015e84`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015e16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015e84`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015f1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015f1f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015e27`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015e40`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015e27`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015e40`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RemoveServiceFromMultiString(LPCWSTR lpValueName)
{
  int v2; // r12d
  unsigned int v3; // esi
  HKEY v4; // rbx
  BYTE *v5; // rdi
  const BYTE *v6; // r15
  __int64 v7; // rdx
  BYTE *v8; // r14
  int v9; // eax
  __int16 v10; // cx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+34h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v15[8]; // [rsp+40h] [rbp-18h] BYREF
  _BYTE v16[16]; // [rsp+48h] [rbp-10h] BYREF

  v2 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SvcHost",
         0,
         0xF003Fu,
         &hKey);
  if ( !v3 )
  {
    v4 = hKey;
    cbData = 0;
    Type = 0;
    if ( RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData) )
    {
      v3 = 0;
      goto LABEL_24;
    }
    v5 = (BYTE *)CWin32DefaultArena::WbemMemAlloc(cbData);
    std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(v16, v5);
    v6 = (const BYTE *)CWin32DefaultArena::WbemMemAlloc(cbData);
    std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(v15, v6);
    if ( !v5 || !v7 )
    {
      v3 = 14;
      goto LABEL_22;
    }
    v3 = RegQueryValueExW(hKey, lpValueName, 0, &Type, v5, &cbData);
    if ( v3 )
    {
      if ( Type == 7 )
      {
LABEL_22:
        CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>(v15);
        CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>(v16);
LABEL_24:
        RegCloseKey(v4);
        return v3;
      }
    }
    else if ( Type == 7 )
    {
      v8 = (BYTE *)v6;
      while ( *(_WORD *)v5 )
      {
        v9 = wbem_wcsicmp((const unsigned __int16 *)v5, L"winmgmt");
        v10 = *(_WORD *)v5;
        if ( v9 )
        {
          while ( v10 )
          {
            v5 += 2;
            *(_WORD *)v8 = v10;
            v8 += 2;
            v10 = *(_WORD *)v5;
          }
          *(_WORD *)v8 = 0;
          v8 += 2;
        }
        else
        {
          v2 = 1;
          if ( v10 )
          {
            do
              v5 += 2;
            while ( *(_WORD *)v5 );
          }
          cbData -= 16;
        }
        v5 += 2;
      }
      *(_WORD *)v8 = 0;
      if ( v2 )
        v3 = RegSetValueExW(hKey, lpValueName, 0, 7u, v6, cbData);
      goto LABEL_22;
    }
    v3 = 13;
    goto LABEL_22;
  }
  return v3;
}

```

## disassembly

```asm
0x180015d9c  push    rbp
0x180015d9e  push    rbx
0x180015d9f  push    rsi
0x180015da0  push    rdi
0x180015da1  push    r12
0x180015da3  push    r13
0x180015da5  push    r14
0x180015da7  push    r15
0x180015da9  mov     rbp, rsp
0x180015dac  sub     rsp, 58h
0x180015db0  mov     r13, rcx
0x180015db3  xor     r12d, r12d
0x180015db6  mov     [rbp+hKey], r12
0x180015dba  lea     rax, [rbp+hKey]
0x180015dbe  mov     [rsp+58h+phkResult], rax; phkResult
0x180015dc3  mov     r9d, 0F003Fh; samDesired
0x180015dc9  xor     r8d, r8d; ulOptions
0x180015dcc  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180015dd3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015dda  call    cs:__imp_RegOpenKeyExW
0x180015de0  mov     esi, eax
0x180015de2  test    eax, eax
0x180015de4  jnz     loc_180015F5C
0x180015dea  mov     rbx, [rbp+hKey]
0x180015dee  mov     [rbp+arg_8], rbx
0x180015df2  mov     [rbp+cbData], r12d
0x180015df6  mov     [rbp+Type], r12d
0x180015dfa  lea     rax, [rbp+cbData]
0x180015dfe  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180015e03  mov     [rsp+58h+phkResult], r12; lpData
0x180015e08  lea     r9, [rbp+Type]; lpType
0x180015e0c  xor     r8d, r8d; lpReserved
0x180015e0f  mov     rdx, r13; lpValueName
0x180015e12  mov     rcx, [rbp+hKey]; hKey
0x180015e16  call    cs:__imp_RegQueryValueExW
0x180015e1c  test    eax, eax
0x180015e1e  jnz     loc_180015F50
0x180015e24  mov     ecx, [rbp+cbData]
0x180015e27  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180015e2d  mov     rdi, rax
0x180015e30  mov     rdx, rax
0x180015e33  lea     rcx, [rbp+var_10]
0x180015e37  call    ??0?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@PEAVCTraceSessionControl@@@Z; std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(CTraceSessionControl *)
0x180015e3c  nop
0x180015e3d  mov     ecx, [rbp+cbData]
0x180015e40  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180015e46  mov     r15, rax
0x180015e49  mov     rdx, rax
0x180015e4c  lea     rcx, [rbp+var_18]
0x180015e50  call    ??0?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@PEAVCTraceSessionControl@@@Z; std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(CTraceSessionControl *)
0x180015e55  nop
0x180015e56  test    rdi, rdi
0x180015e59  jz      loc_180015F36
0x180015e5f  test    rdx, rdx
0x180015e62  jz      loc_180015F36
0x180015e68  lea     rax, [rbp+cbData]
0x180015e6c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180015e71  mov     [rsp+58h+phkResult], rdi; lpData
0x180015e76  lea     r9, [rbp+Type]; lpType
0x180015e7a  xor     r8d, r8d; lpReserved
0x180015e7d  mov     rdx, r13; lpValueName
0x180015e80  mov     rcx, [rbp+hKey]; hKey
0x180015e84  call    cs:__imp_RegQueryValueExW
0x180015e8a  mov     esi, eax
0x180015e8c  test    eax, eax
0x180015e8e  jnz     loc_180015F29
0x180015e94  cmp     [rbp+Type], 7
0x180015e98  jnz     loc_180015F2F
0x180015e9e  mov     r14, r15
0x180015ea1  xor     edx, edx
0x180015ea3  jmp     short loc_180015EF5
0x180015ea5  lea     rdx, ServiceName; "winmgmt"
0x180015eac  mov     rcx, rdi; unsigned __int16 *
0x180015eaf  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180015eb4  movzx   ecx, word ptr [rdi]
0x180015eb7  xor     edx, edx
0x180015eb9  test    eax, eax
0x180015ebb  jnz     short loc_180015EE4
0x180015ebd  lea     r12d, [rdx+1]
0x180015ec1  test    cx, cx
0x180015ec4  jz      short loc_180015ECF
0x180015ec6  add     rdi, 2
0x180015eca  cmp     [rdi], dx
0x180015ecd  jnz     short loc_180015EC6
0x180015ecf  add     [rbp+cbData], 0FFFFFFF0h
0x180015ed3  jmp     short loc_180015EF1
0x180015ed5  add     rdi, 2
0x180015ed9  mov     [r14], cx
0x180015edd  add     r14, 2
0x180015ee1  movzx   ecx, word ptr [rdi]
0x180015ee4  test    cx, cx
0x180015ee7  jnz     short loc_180015ED5
0x180015ee9  mov     [r14], dx
0x180015eed  add     r14, 2
0x180015ef1  add     rdi, 2
0x180015ef5  cmp     [rdi], dx
0x180015ef8  jnz     short loc_180015EA5
0x180015efa  mov     [r14], dx
0x180015efe  test    r12d, r12d
0x180015f01  jz      short loc_180015F3B
0x180015f03  mov     eax, [rbp+cbData]
0x180015f06  mov     dword ptr [rsp+58h+lpcbData], eax; cbData
0x180015f0a  mov     [rsp+58h+phkResult], r15; lpData
0x180015f0f  mov     r9d, 7; dwType
0x180015f15  xor     r8d, r8d; Reserved
0x180015f18  mov     rdx, r13; lpValueName
0x180015f1b  mov     rcx, [rbp+hKey]; hKey
0x180015f1f  call    cs:__imp_RegSetValueExW
0x180015f25  mov     esi, eax
0x180015f27  jmp     short loc_180015F3B
0x180015f29  cmp     [rbp+Type], 7
0x180015f2d  jz      short loc_180015F3B
0x180015f2f  mov     esi, 0Dh
0x180015f34  jmp     short loc_180015F3B
0x180015f36  mov     esi, 0Eh
0x180015f3b  lea     rcx, [rbp+var_18]
0x180015f3f  call    ??1?$CDeleteMe@G@@QEAA@XZ; CDeleteMe<ushort>::~CDeleteMe<ushort>(void)
0x180015f44  nop
0x180015f45  lea     rcx, [rbp+var_10]
0x180015f49  call    ??1?$CDeleteMe@G@@QEAA@XZ; CDeleteMe<ushort>::~CDeleteMe<ushort>(void)
0x180015f4e  jmp     short loc_180015F53
0x180015f50  mov     esi, r12d
0x180015f53  mov     rcx, rbx; hKey
0x180015f56  call    cs:__imp_RegCloseKey
0x180015f5c  mov     eax, esi
0x180015f5e  add     rsp, 58h
0x180015f62  pop     r15
0x180015f64  pop     r14
0x180015f66  pop     r13
0x180015f68  pop     r12
0x180015f6a  pop     rdi
0x180015f6b  pop     rsi
0x180015f6c  pop     rbx
0x180015f6d  pop     rbp
0x180015f6e  retn
```
