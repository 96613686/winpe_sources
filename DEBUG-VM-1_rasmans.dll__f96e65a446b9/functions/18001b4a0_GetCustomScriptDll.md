# GetCustomScriptDll

- ea: `0x18001b4a0`
- end: `0x18001b724`
- name: `GetCustomScriptDll`
- size: `644`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bfb0`
- `0x18001b4a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b637`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001b58d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001b606`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001b58d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001b606`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001b559`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001b559`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b6d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b6d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b5c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b5c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6bf`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001b62a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001b64b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001b62a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001b64b`

## string_xrefs

- `0x18001b54b`: `System\CurrentControlSet\Services\Rasman\Parameters`
- `0x18001b586`: `CustomScriptDllPath`
- `0x18001b5e9`: `CustomScriptDllPath`

## pseudocode

```c
double __fastcall GetCustomScriptDll(__int64 a1, __int64 a2, __int64 a3)
{
  struct _LIST_ENTRY *v4; // rcx
  double result; // xmm0_8
  DWORD LastError; // ebx
  BYTE *v7; // rax
  CHAR *v8; // rsi
  DWORD v9; // eax
  DWORD v10; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1175, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 4u )
  {
    result = WPP_SF_(v4[1].Flink, 1176, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  LastError = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 1u, &hKey);
  if ( !LastError )
  {
    LastError = RegQueryValueExA(hKey, "CustomScriptDllPath", 0, &Type, 0, &cbData);
    if ( !LastError )
    {
      if ( Type == 2 && cbData - 1 <= 0x103 )
      {
        v7 = (BYTE *)LocalAlloc(0x40u, cbData + 1);
        v8 = (CHAR *)v7;
        if ( !v7 )
        {
          LastError = GetLastError();
          *(_DWORD *)a3 = LastError;
          goto LABEL_33;
        }
        v7[cbData] = 0;
        LastError = RegQueryValueExA(hKey, "CustomScriptDllPath", 0, &Type, v7, &cbData);
        if ( LastError || Type != 2 || cbData - 1 > 0x103 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            result = WPP_SF_d(
                       WPP_GLOBAL_Control[1].Flink,
                       1177,
                       WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                       LastError);
          }
        }
        else
        {
          v9 = ExpandEnvironmentStringsA(v8, 0, 0);
          cbData = v9;
          if ( !v9 || !ExpandEnvironmentStringsA(v8, (LPSTR)(a3 + 4), v9) )
          {
            v10 = GetLastError();
            LastError = v10;
LABEL_30:
            *(_DWORD *)a3 = v10;
            LocalFree(v8);
            goto LABEL_33;
          }
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
          {
            WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 1178, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a3 + 4);
          }
        }
        v10 = LastError;
        goto LABEL_30;
      }
      LastError = -2147467259;
    }
  }
  *(_DWORD *)a3 = LastError;
LABEL_33:
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    return WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1179, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, LastError);
  }
  return result;
}

```

## disassembly

```asm
0x18001b4a0  mov     [rsp-28h+arg_0], rbx
0x18001b4a5  mov     [rsp-28h+arg_8], rsi
0x18001b4aa  push    rbp
0x18001b4ab  push    rdi
0x18001b4ac  push    r12
0x18001b4ae  push    r13
0x18001b4b0  push    r14
0x18001b4b2  mov     rbp, rsp
0x18001b4b5  sub     rsp, 40h
0x18001b4b9  mov     rdi, r8
0x18001b4bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4c3  lea     r13, WPP_GLOBAL_Control
0x18001b4ca  mov     r12d, 2000h
0x18001b4d0  cmp     rcx, r13
0x18001b4d3  jz      short loc_18001B4FD
0x18001b4d5  test    [rcx+1Ch], r12d
0x18001b4d9  jz      short loc_18001B4FD
0x18001b4db  cmp     byte ptr [rcx+19h], 6
0x18001b4df  jb      short loc_18001B4FD
0x18001b4e1  mov     rcx, [rcx+10h]
0x18001b4e5  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001b4ec  mov     edx, 497h
0x18001b4f1  call    WPP_SF_
0x18001b4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4fd  mov     [rbp+hKey], 0
0x18001b505  mov     [rbp+cbData], 0
0x18001b50c  mov     [rbp+Type], 0
0x18001b513  cmp     rcx, r13
0x18001b516  jz      short loc_18001B539
0x18001b518  test    [rcx+1Ch], r12d
0x18001b51c  jz      short loc_18001B539
0x18001b51e  cmp     byte ptr [rcx+19h], 4
0x18001b522  jb      short loc_18001B539
0x18001b524  mov     rcx, [rcx+10h]
0x18001b528  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001b52f  mov     edx, 498h
0x18001b534  call    WPP_SF_
0x18001b539  lea     rax, [rbp+hKey]
0x18001b53d  mov     r9d, 1; samDesired
0x18001b543  xor     r8d, r8d; ulOptions
0x18001b546  mov     [rsp+40h+phkResult], rax; phkResult
0x18001b54b  lea     rdx, aSystemCurrentc_20; "System\\CurrentControlSet\\Services\\Ra"...
0x18001b552  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b559  call    cs:__imp_RegOpenKeyExA
0x18001b55f  mov     ebx, eax
0x18001b561  test    eax, eax
0x18001b563  jnz     loc_18001B6CC
0x18001b569  mov     rcx, [rbp+hKey]; hKey
0x18001b56d  lea     rax, [rbp+cbData]
0x18001b571  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001b576  lea     r9, [rbp+Type]; lpType
0x18001b57a  xor     r8d, r8d; lpReserved
0x18001b57d  mov     [rsp+40h+phkResult], 0; lpData
0x18001b586  lea     rdx, aCustomscriptdl; "CustomScriptDllPath"
0x18001b58d  call    cs:__imp_RegQueryValueExA
0x18001b593  mov     ebx, eax
0x18001b595  test    eax, eax
0x18001b597  jnz     loc_18001B6CC
0x18001b59d  cmp     [rbp+Type], 2
0x18001b5a1  jnz     loc_18001B6C7
0x18001b5a7  mov     ecx, [rbp+cbData]
0x18001b5aa  mov     r14d, 103h
0x18001b5b0  lea     eax, [rcx-1]
0x18001b5b3  cmp     eax, r14d
0x18001b5b6  ja      loc_18001B6C7
0x18001b5bc  lea     edx, [rcx+1]; uBytes
0x18001b5bf  lea     ecx, [rbx+40h]; uFlags
0x18001b5c2  call    cs:__imp_LocalAlloc
0x18001b5c8  mov     rsi, rax
0x18001b5cb  test    rax, rax
0x18001b5ce  jnz     short loc_18001B5DF
0x18001b5d0  call    cs:__imp_GetLastError
0x18001b5d6  mov     ebx, eax
0x18001b5d8  mov     [rdi], eax
0x18001b5da  jmp     loc_18001B6CE
0x18001b5df  mov     eax, [rbp+cbData]
0x18001b5e2  lea     r9, [rbp+Type]; lpType
0x18001b5e6  xor     r8d, r8d; lpReserved
0x18001b5e9  lea     rdx, aCustomscriptdl; "CustomScriptDllPath"
0x18001b5f0  mov     byte ptr [rax+rsi], 0
0x18001b5f4  lea     rax, [rbp+cbData]
0x18001b5f8  mov     rcx, [rbp+hKey]; hKey
0x18001b5fc  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001b601  mov     [rsp+40h+phkResult], rsi; lpData
0x18001b606  call    cs:__imp_RegQueryValueExA
0x18001b60c  mov     ebx, eax
0x18001b60e  test    eax, eax
0x18001b610  jnz     short loc_18001B688
0x18001b612  cmp     [rbp+Type], 2
0x18001b616  jnz     short loc_18001B688
0x18001b618  mov     eax, [rbp+cbData]
0x18001b61b  dec     eax
0x18001b61d  cmp     eax, r14d
0x18001b620  ja      short loc_18001B688
0x18001b622  xor     r8d, r8d; nSize
0x18001b625  xor     edx, edx; lpDst
0x18001b627  mov     rcx, rsi; lpSrc
0x18001b62a  call    cs:__imp_ExpandEnvironmentStringsA
0x18001b630  mov     [rbp+cbData], eax
0x18001b633  test    eax, eax
0x18001b635  jnz     short loc_18001B641
0x18001b637  call    cs:__imp_GetLastError
0x18001b63d  mov     ebx, eax
0x18001b63f  jmp     short loc_18001B6BA
0x18001b641  mov     r8d, eax; nSize
0x18001b644  lea     rdx, [rdi+4]; lpDst
0x18001b648  mov     rcx, rsi; lpSrc
0x18001b64b  call    cs:__imp_ExpandEnvironmentStringsA
0x18001b651  test    eax, eax
0x18001b653  jz      short loc_18001B637
0x18001b655  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b65c  cmp     rcx, r13
0x18001b65f  jz      short loc_18001B6B8
0x18001b661  test    [rcx+1Ch], r12d
0x18001b665  jz      short loc_18001B6B8
0x18001b667  cmp     byte ptr [rcx+19h], 4
0x18001b66b  jb      short loc_18001B6B8
0x18001b66d  mov     rcx, [rcx+10h]
0x18001b671  lea     r9, [rdi+4]
0x18001b675  mov     edx, 49Ah
0x18001b67a  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001b681  call    WPP_SF_s
0x18001b686  jmp     short loc_18001B6B8
0x18001b688  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b68f  cmp     rcx, r13
0x18001b692  jz      short loc_18001B6B8
0x18001b694  test    [rcx+1Ch], r12d
0x18001b698  jz      short loc_18001B6B8
0x18001b69a  cmp     byte ptr [rcx+19h], 2
0x18001b69e  jb      short loc_18001B6B8
0x18001b6a0  mov     rcx, [rcx+10h]
0x18001b6a4  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001b6ab  mov     edx, 499h
0x18001b6b0  mov     r9d, ebx
0x18001b6b3  call    WPP_SF_d
0x18001b6b8  mov     eax, ebx
0x18001b6ba  mov     rcx, rsi; hMem
0x18001b6bd  mov     [rdi], eax
0x18001b6bf  call    cs:__imp_LocalFree
0x18001b6c5  jmp     short loc_18001B6CE
0x18001b6c7  mov     ebx, 80004005h
0x18001b6cc  mov     [rdi], ebx
0x18001b6ce  mov     rcx, [rbp+hKey]; hKey
0x18001b6d2  test    rcx, rcx
0x18001b6d5  jz      short loc_18001B6DD
0x18001b6d7  call    cs:__imp_RegCloseKey
0x18001b6dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6e4  cmp     rcx, r13
0x18001b6e7  jz      short loc_18001B70D
0x18001b6e9  test    [rcx+1Ch], r12d
0x18001b6ed  jz      short loc_18001B70D
0x18001b6ef  cmp     byte ptr [rcx+19h], 6
0x18001b6f3  jb      short loc_18001B70D
0x18001b6f5  mov     rcx, [rcx+10h]
0x18001b6f9  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001b700  mov     edx, 49Bh
0x18001b705  mov     r9d, ebx
0x18001b708  call    WPP_SF_d
0x18001b70d  mov     rbx, [rsp+40h+arg_0]
0x18001b712  mov     rsi, [rsp+40h+arg_8]
0x18001b717  add     rsp, 40h
0x18001b71b  pop     r14
0x18001b71d  pop     r13
0x18001b71f  pop     r12
0x18001b721  pop     rdi
0x18001b722  pop     rbp
0x18001b723  retn
```
