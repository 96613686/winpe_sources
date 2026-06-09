# IsCustomDLLTrusted

- ea: `0x18000d590`
- end: `0x18000d90f`
- name: `IsCustomDLLTrusted`
- size: `895`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001f340`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000d590`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d822`
- `msvcrt!_wcsicmp` at `0x18000d822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d73f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d73f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d790`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d790`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d626`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d626`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d887`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d887`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d6d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d6d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d731`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d731`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d87d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d87d`

## string_xrefs

- `0x18000d5ff`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18000d789`: `CustomDLL`

## pseudocode

```c
__int64 __fastcall IsCustomDLLTrusted(wchar_t *String2)
{
  unsigned int v2; // eax
  struct _LIST_ENTRY *v3; // rcx
  __int64 v4; // rdx
  DWORD LastError; // eax
  int v6; // ebx
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  BYTE *v9; // rsi
  unsigned int v10; // eax
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  const wchar_t *v14; // rdi
  __int64 v15; // rax
  DWORD cValues; // [rsp+60h] [rbp-20h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-1Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+C8h] [rbp+48h] BYREF
  DWORD cbMaxValueLen; // [rsp+D0h] [rbp+50h] BYREF
  DWORD Type; // [rsp+D8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 45, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
  }
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  Type = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters",
         0,
         0x2000000u,
         &hKey);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return 0;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 46, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v2);
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v3[1].Blink) & 0x2000) == 0
      || BYTE1(v3[1].Blink) < 6u )
    {
      return 0;
    }
    v4 = 47;
    goto LABEL_52;
  }
  LastError = RegQueryInfoKeyW(
                hKey,
                0,
                0,
                0,
                &cSubKeys,
                &cbMaxSubKeyLen,
                0,
                &cValues,
                &cbMaxValueNameLen,
                &cbMaxValueLen,
                0,
                0);
  v6 = LastError;
  if ( LastError )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 48;
LABEL_19:
      WPP_SF_d(v7[1].Flink, v8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, LastError);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  ++cbMaxValueNameLen;
  v9 = (BYTE *)LocalAlloc(0x40u, cbMaxValueLen);
  if ( v9 )
  {
    v10 = RegQueryValueExW(hKey, L"CustomDLL", 0, &Type, v9, &cbMaxValueLen);
    v6 = v10;
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_46;
      }
      v12 = 50;
      v13 = v10;
    }
    else
    {
      if ( Type == 7 )
      {
        v6 = 126;
        v14 = (const wchar_t *)v9;
        if ( *(_WORD *)v9 )
        {
          while ( _wcsicmp(v14, String2) )
          {
            v15 = -1;
            do
              ++v15;
            while ( v14[v15] );
            v14 += v15 + 1;
            if ( !*v14 )
              goto LABEL_46;
          }
          v6 = 0;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 52, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
          }
        }
        goto LABEL_46;
      }
      v6 = 1015;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
LABEL_46:
        LocalFree(v9);
        goto LABEL_47;
      }
      v12 = 51;
      v13 = 1015;
    }
    WPP_SF_d(v11[1].Flink, v12, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v13);
    goto LABEL_46;
  }
  LastError = GetLastError();
  v6 = LastError;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v8 = 49;
    goto LABEL_19;
  }
LABEL_47:
  RegCloseKey(hKey);
  if ( v6 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
    {
      return 0;
    }
    v4 = 53;
LABEL_52:
    WPP_SF_(v3[1].Flink, v4, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 54, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x18000d590  mov     [rsp-38h+arg_0], rbx
0x18000d595  push    rbp
0x18000d596  push    rsi
0x18000d597  push    rdi
0x18000d598  push    r12
0x18000d59a  push    r13
0x18000d59c  push    r14
0x18000d59e  push    r15
0x18000d5a0  mov     rbp, rsp
0x18000d5a3  sub     rsp, 80h
0x18000d5aa  mov     r14, rcx
0x18000d5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5b4  lea     r13, WPP_GLOBAL_Control
0x18000d5bb  mov     r12d, 2000h
0x18000d5c1  cmp     rcx, r13
0x18000d5c4  jz      short loc_18000D5E7
0x18000d5c6  test    [rcx+1Ch], r12d
0x18000d5ca  jz      short loc_18000D5E7
0x18000d5cc  cmp     byte ptr [rcx+19h], 6
0x18000d5d0  jb      short loc_18000D5E7
0x18000d5d2  mov     rcx, [rcx+10h]
0x18000d5d6  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000d5dd  mov     edx, 2Dh ; '-'
0x18000d5e2  call    WPP_SF_
0x18000d5e7  xor     r15d, r15d
0x18000d5ea  lea     rax, [rbp+hKey]
0x18000d5ee  mov     r9d, 2000000h; samDesired
0x18000d5f4  mov     [rbp+hKey], r15
0x18000d5f8  xor     r8d, r8d; ulOptions
0x18000d5fb  mov     [rbp+cSubKeys], r15d
0x18000d5ff  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18000d606  mov     [rbp+cbMaxSubKeyLen], r15d
0x18000d60a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d611  mov     [rbp+cbMaxValueNameLen], r15d
0x18000d615  mov     [rbp+cValues], r15d
0x18000d619  mov     [rbp+cbMaxValueLen], r15d
0x18000d61d  mov     [rbp+Type], r15d
0x18000d621  mov     [rsp+80h+phkResult], rax; phkResult
0x18000d626  call    cs:__imp_RegOpenKeyExW
0x18000d62c  test    eax, eax
0x18000d62e  jz      short loc_18000D691
0x18000d630  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d637  cmp     rcx, r13
0x18000d63a  jz      loc_18000D8BE
0x18000d640  test    [rcx+1Ch], r12d
0x18000d644  jz      short loc_18000D66A
0x18000d646  cmp     byte ptr [rcx+19h], 2
0x18000d64a  jb      short loc_18000D66A
0x18000d64c  mov     rcx, [rcx+10h]
0x18000d650  lea     edx, [r15+2Eh]
0x18000d654  mov     r9d, eax
0x18000d657  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000d65e  call    WPP_SF_d
0x18000d663  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d66a  cmp     rcx, r13
0x18000d66d  jz      loc_18000D8BE
0x18000d673  test    [rcx+1Ch], r12d
0x18000d677  jz      loc_18000D8BE
0x18000d67d  cmp     byte ptr [rcx+19h], 6
0x18000d681  jb      loc_18000D8BE
0x18000d687  mov     edx, 2Fh ; '/'
0x18000d68c  jmp     loc_18000D8AE
0x18000d691  mov     rcx, [rbp+hKey]; hKey
0x18000d695  lea     rax, [rbp+cbMaxValueLen]
0x18000d699  mov     [rsp+80h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000d69e  xor     r9d, r9d; lpReserved
0x18000d6a1  mov     [rsp+80h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000d6a6  xor     r8d, r8d; lpcchClass
0x18000d6a9  mov     [rsp+80h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000d6ae  xor     edx, edx; lpClass
0x18000d6b0  lea     rax, [rbp+cbMaxValueNameLen]
0x18000d6b4  mov     [rsp+80h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000d6b9  lea     rax, [rbp+cValues]
0x18000d6bd  mov     [rsp+80h+lpcValues], rax; lpcValues
0x18000d6c2  lea     rax, [rbp+cbMaxSubKeyLen]
0x18000d6c6  mov     [rsp+80h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000d6cb  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000d6d0  lea     rax, [rbp+cSubKeys]
0x18000d6d4  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x18000d6d9  call    cs:__imp_RegQueryInfoKeyW
0x18000d6df  mov     ebx, eax
0x18000d6e1  test    eax, eax
0x18000d6e3  jz      short loc_18000D726
0x18000d6e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6ec  cmp     rcx, r13
0x18000d6ef  jz      loc_18000D883
0x18000d6f5  test    [rcx+1Ch], r12d
0x18000d6f9  jz      loc_18000D883
0x18000d6ff  cmp     byte ptr [rcx+19h], 2
0x18000d703  jb      loc_18000D883
0x18000d709  mov     edx, 30h ; '0'
0x18000d70e  mov     rcx, [rcx+10h]
0x18000d712  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000d719  mov     r9d, eax
0x18000d71c  call    WPP_SF_d
0x18000d721  jmp     loc_18000D883
0x18000d726  mov     edx, [rbp+cbMaxValueLen]; uBytes
0x18000d729  mov     ecx, 40h ; '@'; uFlags
0x18000d72e  inc     [rbp+cbMaxValueNameLen]
0x18000d731  call    cs:__imp_LocalAlloc
0x18000d737  mov     rsi, rax
0x18000d73a  test    rax, rax
0x18000d73d  jnz     short loc_18000D770
0x18000d73f  call    cs:__imp_GetLastError
0x18000d745  mov     ebx, eax
0x18000d747  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d74e  cmp     rcx, r13
0x18000d751  jz      loc_18000D883
0x18000d757  test    [rcx+1Ch], r12d
0x18000d75b  jz      loc_18000D883
0x18000d761  cmp     byte ptr [rcx+19h], 2
0x18000d765  jb      loc_18000D883
0x18000d76b  lea     edx, [rsi+31h]
0x18000d76e  jmp     short loc_18000D70E
0x18000d770  mov     rcx, [rbp+hKey]; hKey
0x18000d774  lea     rax, [rbp+cbMaxValueLen]
0x18000d778  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000d77d  lea     r9, [rbp+Type]; lpType
0x18000d781  xor     r8d, r8d; lpReserved
0x18000d784  mov     [rsp+80h+phkResult], rsi; lpData
0x18000d789  lea     rdx, aCustomdll; "CustomDLL"
0x18000d790  call    cs:__imp_RegQueryValueExW
0x18000d796  mov     ebx, eax
0x18000d798  test    eax, eax
0x18000d79a  jz      short loc_18000D7DD
0x18000d79c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7a3  cmp     rcx, r13
0x18000d7a6  jz      loc_18000D87A
0x18000d7ac  test    [rcx+1Ch], r12d
0x18000d7b0  jz      loc_18000D87A
0x18000d7b6  cmp     byte ptr [rcx+19h], 2
0x18000d7ba  jb      loc_18000D87A
0x18000d7c0  mov     edx, 32h ; '2'
0x18000d7c5  mov     r9d, eax
0x18000d7c8  mov     rcx, [rcx+10h]
0x18000d7cc  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000d7d3  call    WPP_SF_d
0x18000d7d8  jmp     loc_18000D87A
0x18000d7dd  cmp     [rbp+Type], 7
0x18000d7e1  jz      short loc_18000D80E
0x18000d7e3  mov     ebx, 3F7h
0x18000d7e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7ef  cmp     rcx, r13
0x18000d7f2  jz      loc_18000D87A
0x18000d7f8  test    [rcx+1Ch], r12d
0x18000d7fc  jz      short loc_18000D87A
0x18000d7fe  cmp     byte ptr [rcx+19h], 2
0x18000d802  jb      short loc_18000D87A
0x18000d804  mov     edx, 33h ; '3'
0x18000d809  mov     r9d, ebx
0x18000d80c  jmp     short loc_18000D7C8
0x18000d80e  mov     ebx, 7Eh ; '~'
0x18000d813  mov     rdi, rsi
0x18000d816  cmp     [rsi], r15w
0x18000d81a  jz      short loc_18000D87A
0x18000d81c  mov     rdx, r14; String2
0x18000d81f  mov     rcx, rdi; String1
0x18000d822  call    cs:__imp__wcsicmp
0x18000d828  test    eax, eax
0x18000d82a  jz      short loc_18000D84A
0x18000d82c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d830  inc     rax
0x18000d833  cmp     [rdi+rax*2], r15w
0x18000d838  jnz     short loc_18000D830
0x18000d83a  lea     rdi, [rdi+rax*2]
0x18000d83e  add     rdi, 2
0x18000d842  cmp     [rdi], r15w
0x18000d846  jnz     short loc_18000D81C
0x18000d848  jmp     short loc_18000D87A
0x18000d84a  mov     ebx, r15d
0x18000d84d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d854  cmp     rcx, r13
0x18000d857  jz      short loc_18000D87A
0x18000d859  test    [rcx+1Ch], r12d
0x18000d85d  jz      short loc_18000D87A
0x18000d85f  cmp     byte ptr [rcx+19h], 4
0x18000d863  jb      short loc_18000D87A
0x18000d865  mov     rcx, [rcx+10h]
0x18000d869  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000d870  mov     edx, 34h ; '4'
0x18000d875  call    WPP_SF_
0x18000d87a  mov     rcx, rsi; hMem
0x18000d87d  call    cs:__imp_LocalFree
0x18000d883  mov     rcx, [rbp+hKey]; hKey
0x18000d887  call    cs:__imp_RegCloseKey
0x18000d88d  test    ebx, ebx
0x18000d88f  jz      short loc_18000D8C2
0x18000d891  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d898  cmp     rcx, r13
0x18000d89b  jz      short loc_18000D8BE
0x18000d89d  test    [rcx+1Ch], r12d
0x18000d8a1  jz      short loc_18000D8BE
0x18000d8a3  cmp     byte ptr [rcx+19h], 6
0x18000d8a7  jb      short loc_18000D8BE
0x18000d8a9  mov     edx, 35h ; '5'
0x18000d8ae  mov     rcx, [rcx+10h]
0x18000d8b2  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000d8b9  call    WPP_SF_
0x18000d8be  xor     eax, eax
0x18000d8c0  jmp     short loc_18000D8F4
0x18000d8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8c9  cmp     rcx, r13
0x18000d8cc  jz      short loc_18000D8EF
0x18000d8ce  test    [rcx+1Ch], r12d
0x18000d8d2  jz      short loc_18000D8EF
0x18000d8d4  cmp     byte ptr [rcx+19h], 6
0x18000d8d8  jb      short loc_18000D8EF
0x18000d8da  mov     rcx, [rcx+10h]
0x18000d8de  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000d8e5  mov     edx, 36h ; '6'
0x18000d8ea  call    WPP_SF_
0x18000d8ef  mov     eax, 1
0x18000d8f4  mov     rbx, [rsp+80h+arg_0]
0x18000d8fc  add     rsp, 80h
0x18000d903  pop     r15
0x18000d905  pop     r14
0x18000d907  pop     r13
0x18000d909  pop     r12
0x18000d90b  pop     rdi
0x18000d90c  pop     rsi
0x18000d90d  pop     rbp
0x18000d90e  retn
```
