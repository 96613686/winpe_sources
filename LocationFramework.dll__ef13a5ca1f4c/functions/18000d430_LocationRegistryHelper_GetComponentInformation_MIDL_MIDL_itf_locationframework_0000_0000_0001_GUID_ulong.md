# LocationRegistryHelper::GetComponentInformation(__MIDL___MIDL_itf_locationframework_0000_0000_0001,_GUID *,ulong *)

- ea: `0x18000d430`
- end: `0x18000d63c`
- name: `?GetComponentInformation@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEAU_GUID@@PEAK@Z`
- size: `524`
- prototype: `__int64 __fastcall(unsigned int, GUID *, BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d340`

## callees

- `0x18000d430`
- `0x18000d650`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d5d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d5d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d4c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d4c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d518`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d5b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d518`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d5b5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d564`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d564`

## string_xrefs

- `0x18000d504`: `ClassID`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall LocationRegistryHelper::GetComponentInformation(unsigned int a1, GUID *a2, BYTE *a3)
{
  __int64 v6; // r8
  unsigned int ComponentRegKeyPath; // ebx
  LSTATUS v8; // eax
  HKEY v9; // rcx
  LSTATUS v10; // eax
  unsigned __int16 v11; // di
  bool v12; // cc
  __int16 v13; // ax
  int v14; // ebx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[256]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(SubKey, 0, 0x1FEu);
  if ( !a2 || !a3 )
    return (unsigned int)-2147467261;
  *(_DWORD *)a3 = 0;
  ComponentRegKeyPath = LocationRegistryHelper::GetComponentRegKeyPath(a1, SubKey, v6, 0);
  if ( (ComponentRegKeyPath & 0x80000000) == 0 )
  {
    hKey = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
    if ( v8 )
    {
      if ( v8 <= 0 )
        return (unsigned int)v8;
      else
        return (unsigned __int16)v8 | 0x80070000;
    }
    v9 = hKey;
    Type = 0;
    cbData = 128;
    *a2 = GUID_NULL;
    v10 = RegQueryValueExW(v9, L"ClassID", 0, &Type, Data, &cbData);
    v11 = 13;
    v12 = v10 <= 0;
    if ( !v10 )
    {
      if ( Type - 1 <= 1 )
      {
        if ( !cbData )
        {
          v13 = 0;
          *(_WORD *)Data = 0;
LABEL_11:
          if ( v13 != 123 || CLSIDFromString((LPCOLESTR)Data, a2) < 0 )
          {
            LOWORD(v10) = 13;
LABEL_14:
            v14 = (unsigned __int16)v10;
LABEL_15:
            ComponentRegKeyPath = v14 | 0x80070000;
            goto LABEL_19;
          }
          cbData = 0;
          Type = 4;
          v10 = RegQueryValueExW(hKey, L"ClsCtx", 0, &cbData, a3, &Type);
          if ( !v10 )
          {
            if ( cbData == 4 )
              goto LABEL_19;
LABEL_30:
            v14 = v11;
            goto LABEL_15;
          }
          if ( v10 > 0 )
          {
            v11 = v10;
            goto LABEL_30;
          }
LABEL_27:
          ComponentRegKeyPath = v10;
LABEL_19:
          if ( hKey )
            RegCloseKey(hKey);
          return ComponentRegKeyPath;
        }
        if ( (cbData & 1) == 0 && !*(_WORD *)&Data[2 * ((unsigned __int64)cbData >> 1) - 2] )
        {
          v13 = *(_WORD *)Data;
          goto LABEL_11;
        }
      }
      v10 = 13;
      v12 = 0;
    }
    if ( !v12 )
      goto LABEL_14;
    goto LABEL_27;
  }
  return ComponentRegKeyPath;
}

```

## disassembly

```asm
0x18000d430  mov     [rsp-8+arg_18], rbx
0x18000d435  push    rbp
0x18000d436  push    rdi
0x18000d437  push    r12
0x18000d439  push    r14
0x18000d43b  push    r15
0x18000d43d  lea     rbp, [rsp-1D0h]
0x18000d445  sub     rsp, 2D0h
0x18000d44c  mov     rax, cs:__security_cookie
0x18000d453  xor     rax, rsp
0x18000d456  mov     [rbp+1F0h+var_30], rax
0x18000d45d  mov     r14, r8
0x18000d460  mov     r15, rdx
0x18000d463  mov     ebx, ecx
0x18000d465  xor     edx, edx; Val
0x18000d467  mov     r8d, 1FEh; Size
0x18000d46d  lea     rcx, [rbp+1F0h+SubKey]; void *
0x18000d471  call    memset_0
0x18000d476  xor     r12d, r12d
0x18000d479  test    r15, r15
0x18000d47c  jz      loc_18000D601
0x18000d482  test    r14, r14
0x18000d485  jz      loc_18000D601
0x18000d48b  xor     r9d, r9d
0x18000d48e  mov     [r14], r12d
0x18000d491  lea     rdx, [rbp+1F0h+SubKey]
0x18000d495  mov     ecx, ebx
0x18000d497  call    ?GetComponentRegKeyPath@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEAGKH@Z; LocationRegistryHelper::GetComponentRegKeyPath(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ushort *,ulong,int)
0x18000d49c  mov     ebx, eax
0x18000d49e  test    eax, eax
0x18000d4a0  js      loc_18000D5D8
0x18000d4a6  lea     rax, [rsp+2F0h+hKey]
0x18000d4ab  mov     [rsp+2F0h+hKey], r12
0x18000d4b0  mov     r9d, 20019h; samDesired
0x18000d4b6  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18000d4bb  xor     r8d, r8d; ulOptions
0x18000d4be  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18000d4c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d4c9  call    cs:__imp_RegOpenKeyExW
0x18000d4cf  test    eax, eax
0x18000d4d1  jnz     loc_18000D608
0x18000d4d7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000d4de  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000d4e3  lea     rax, [rsp+2F0h+cbData]
0x18000d4e8  mov     [rsp+2F0h+lpcbData], rax; lpcbData
0x18000d4ed  lea     r9, [rsp+2F0h+Type]; lpType
0x18000d4f2  lea     rax, [rsp+2F0h+Data]
0x18000d4f7  mov     [rsp+2F0h+Type], r12d
0x18000d4fc  xor     r8d, r8d; lpReserved
0x18000d4ff  mov     [rsp+2F0h+phkResult], rax; lpData
0x18000d504  lea     rdx, ValueName; "ClassID"
0x18000d50b  mov     [rsp+2F0h+cbData], 80h
0x18000d513  movdqu  xmmword ptr [r15], xmm0
0x18000d518  call    cs:__imp_RegQueryValueExW
0x18000d51e  lea     edi, [r12+0Dh]
0x18000d523  test    eax, eax
0x18000d525  jnz     loc_18000D619
0x18000d52b  mov     eax, [rsp+2F0h+Type]
0x18000d52f  dec     eax
0x18000d531  cmp     eax, 1
0x18000d534  ja      short loc_18000D57B
0x18000d536  mov     eax, [rsp+2F0h+cbData]
0x18000d53a  test    eax, eax
0x18000d53c  jz      loc_18000D62F
0x18000d542  test    al, 1
0x18000d544  jnz     short loc_18000D57B
0x18000d546  shr     rax, 1
0x18000d549  cmp     word ptr [rsp+rax*2+2F0h+Type+2], r12w
0x18000d54f  jnz     short loc_18000D57B
0x18000d551  movzx   eax, word ptr [rsp+2F0h+Data]
0x18000d556  cmp     ax, 7Bh ; '{'
0x18000d55a  jnz     short loc_18000D56E
0x18000d55c  mov     rdx, r15; pclsid
0x18000d55f  lea     rcx, [rsp+2F0h+Data]; lpsz
0x18000d564  call    cs:__imp_CLSIDFromString
0x18000d56a  test    eax, eax
0x18000d56c  jns     short loc_18000D585
0x18000d56e  mov     eax, edi
0x18000d570  movzx   ebx, ax
0x18000d573  or      ebx, 80070000h
0x18000d579  jmp     short loc_18000D5C6
0x18000d57b  mov     eax, edi
0x18000d57d  test    eax, eax
0x18000d57f  jnz     loc_18000D619
0x18000d585  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000d58a  lea     rax, [rsp+2F0h+Type]
0x18000d58f  mov     [rsp+2F0h+lpcbData], rax; lpcbData
0x18000d594  lea     r9, [rsp+2F0h+cbData]; lpType
0x18000d599  xor     r8d, r8d; lpReserved
0x18000d59c  mov     [rsp+2F0h+phkResult], r14; lpData
0x18000d5a1  lea     rdx, aClsctx; "ClsCtx"
0x18000d5a8  mov     [rsp+2F0h+cbData], r12d
0x18000d5ad  mov     [rsp+2F0h+Type], 4
0x18000d5b5  call    cs:__imp_RegQueryValueExW
0x18000d5bb  test    eax, eax
0x18000d5bd  jnz     short loc_18000D623
0x18000d5bf  cmp     [rsp+2F0h+cbData], 4
0x18000d5c4  jnz     short loc_18000D627
0x18000d5c6  cmp     [rsp+2F0h+hKey], r12
0x18000d5cb  jz      short loc_18000D5D8
0x18000d5cd  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000d5d2  call    cs:__imp_RegCloseKey
0x18000d5d8  mov     eax, ebx
0x18000d5da  mov     rcx, [rbp+1F0h+var_30]
0x18000d5e1  xor     rcx, rsp; StackCookie
0x18000d5e4  call    __security_check_cookie
0x18000d5e9  mov     rbx, [rsp+2F0h+arg_18]
0x18000d5f1  add     rsp, 2D0h
0x18000d5f8  pop     r15
0x18000d5fa  pop     r14
0x18000d5fc  pop     r12
0x18000d5fe  pop     rdi
0x18000d5ff  pop     rbp
0x18000d600  retn
0x18000d601  mov     ebx, 80004003h
0x18000d606  jmp     short loc_18000D5D8
0x18000d608  jle     short loc_18000D615
0x18000d60a  movzx   ebx, ax
0x18000d60d  or      ebx, 80070000h
0x18000d613  jmp     short loc_18000D5D8
0x18000d615  mov     ebx, eax
0x18000d617  jmp     short loc_18000D5D8
0x18000d619  jg      loc_18000D570
0x18000d61f  mov     ebx, eax
0x18000d621  jmp     short loc_18000D5C6
0x18000d623  jle     short loc_18000D61F
0x18000d625  mov     edi, eax
0x18000d627  movzx   ebx, di
0x18000d62a  jmp     loc_18000D573
0x18000d62f  mov     eax, r12d
0x18000d632  mov     word ptr [rsp+2F0h+Data], ax
0x18000d637  jmp     loc_18000D556
```
