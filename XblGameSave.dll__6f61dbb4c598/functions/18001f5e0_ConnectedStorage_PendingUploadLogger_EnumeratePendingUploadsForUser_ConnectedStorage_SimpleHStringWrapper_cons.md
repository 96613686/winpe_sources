# ConnectedStorage::PendingUploadLogger::EnumeratePendingUploadsForUser(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)>)

- ea: `0x18001f5e0`
- end: `0x18001f7e3`
- name: `?EnumeratePendingUploadsForUser@PendingUploadLogger@ConnectedStorage@@SAXAEBVSimpleHStringWrapper@2@0V?$function@$$A6AXAEBVSimpleHStringWrapper@ConnectedStorage@@0@Z@std@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180034734`

## callees

- `0x180003c70`
- `0x180011c0c`
- `0x180015f7c`
- `0x18001f5e0`
- `0x18001f8dc`
- `0x18001f984`
- `0x18001f9d8`
- `0x18008e010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f7dc`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f7dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f716`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001f768`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001f768`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ConnectedStorage::PendingUploadLogger::EnumeratePendingUploadsForUser(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  HKEY v6; // rcx
  int v7; // edi
  DWORD v8; // edx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v16; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v19[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Data[259]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v21; // [rsp+286h] [rbp+186h]
  WCHAR ValueName[264]; // [rsp+290h] [rbp+190h] BYREF

  v19[1] = a3;
  ConnectedStorage::GetRootKey((ConnectedStorage *)v19);
  if ( v19[0] )
  {
    ConnectedStorage::GetUserKeyFromRoot(&v18, v19[0], a1, 0);
    if ( v18 )
    {
      ConnectedStorage::GetXuidKeyFromUser(&hKey, v18, a2, 0);
      v6 = hKey;
      if ( hKey )
      {
        v7 = 0;
        Type = 0;
        v8 = 0;
        while ( 1 )
        {
          cchValueName = 260;
          cbData = 260;
          if ( RegEnumValueW(v6, v8, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData) )
            break;
          if ( Type == 1 )
          {
            ValueName[259] = 0;
            v21 = 0;
            ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v16, ValueName);
            ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, Data);
            v9 = *(_QWORD *)(a3 + 56);
            if ( !v9 )
            {
              std::_Xbad_function_call();
              JUMPOUT(0x18001F7E3LL);
            }
            (*(void (__fastcall **)(__int64, HSTRING *, HSTRING *))(*(_QWORD *)v9 + 16LL))(v9, &v16, &string);
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v16);
            v16 = 0;
          }
          v8 = ++v7;
          v6 = hKey;
        }
      }
      ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&hKey);
    }
    ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&v18);
  }
  ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)v19);
  v11 = *(_QWORD *)(a3 + 56);
  if ( v11 )
  {
    LOBYTE(v10) = v11 != a3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 32LL))(v11, v10);
    *(_QWORD *)(a3 + 56) = 0;
  }
}

```

## disassembly

```asm
0x18001f5e0  mov     [rsp-8+arg_18], rbx
0x18001f5e5  push    rbp
0x18001f5e6  push    rsi
0x18001f5e7  push    rdi
0x18001f5e8  lea     rbp, [rsp-3B0h]
0x18001f5f0  sub     rsp, 4B0h
0x18001f5f7  mov     rax, cs:__security_cookie
0x18001f5fe  xor     rax, rsp
0x18001f601  mov     [rbp+3C0h+var_20], rax
0x18001f608  mov     rbx, r8
0x18001f60b  mov     rsi, rdx
0x18001f60e  mov     rdi, rcx
0x18001f611  mov     [rsp+4C0h+var_448], rbx
0x18001f616  lea     rcx, [rsp+4C0h+var_450]
0x18001f61b  call    ?GetRootKey@ConnectedStorage@@YA?AVHKey@1@XZ; ConnectedStorage::GetRootKey(void)
0x18001f620  nop
0x18001f621  mov     rdx, [rsp+4C0h+var_450]
0x18001f626  test    rdx, rdx
0x18001f629  jz      loc_18001F78C
0x18001f62f  xor     r9d, r9d
0x18001f632  mov     r8, rdi
0x18001f635  lea     rcx, [rsp+4C0h+var_458]
0x18001f63a  call    ?GetUserKeyFromRoot@ConnectedStorage@@YA?AVHKey@1@PEAUHKEY__@@AEBVSimpleHStringWrapper@1@_N@Z; ConnectedStorage::GetUserKeyFromRoot(HKEY__ *,ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18001f63f  nop
0x18001f640  mov     rdx, [rsp+4C0h+var_458]
0x18001f645  test    rdx, rdx
0x18001f648  jz      loc_18001F781
0x18001f64e  xor     r9d, r9d
0x18001f651  mov     r8, rsi
0x18001f654  lea     rcx, [rsp+4C0h+hKey]
0x18001f659  call    ?GetXuidKeyFromUser@ConnectedStorage@@YA?AVHKey@1@PEAUHKEY__@@AEBVSimpleHStringWrapper@1@_N@Z; ConnectedStorage::GetXuidKeyFromUser(HKEY__ *,ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18001f65e  nop
0x18001f65f  mov     rcx, [rsp+4C0h+hKey]
0x18001f664  test    rcx, rcx
0x18001f667  jz      loc_18001F776
0x18001f66d  xor     edi, edi
0x18001f66f  mov     esi, 104h
0x18001f674  mov     [rsp+4C0h+Type], edi
0x18001f678  lea     rax, [rsp+4C0h+cbData]
0x18001f67d  mov     [rsp+4C0h+lpcbData], rax
0x18001f682  lea     rax, [rbp+3C0h+Data]
0x18001f686  mov     [rsp+4C0h+lpData], rax
0x18001f68b  lea     rax, [rsp+4C0h+Type]
0x18001f690  mov     [rsp+4C0h+lpType], rax
0x18001f695  mov     [rsp+4C0h+lpReserved], rdi
0x18001f69a  xor     edx, edx
0x18001f69c  jmp     loc_18001F754
0x18001f6a1  cmp     [rsp+4C0h+Type], 1
0x18001f6a6  jnz     short loc_18001F725
0x18001f6a8  xor     eax, eax
0x18001f6aa  mov     [rbp+3C0h+var_2A], ax
0x18001f6b1  mov     [rbp+3C0h+var_23A], ax
0x18001f6b8  lea     rdx, [rbp+3C0h+ValueName]; sourceString
0x18001f6bf  lea     rcx, [rsp+4C0h+var_468]; string
0x18001f6c4  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18001f6c9  nop
0x18001f6ca  lea     rdx, [rbp+3C0h+Data]; sourceString
0x18001f6ce  lea     rcx, [rsp+4C0h+string]; string
0x18001f6d3  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18001f6d8  nop
0x18001f6d9  mov     rcx, [rbx+38h]
0x18001f6dd  test    rcx, rcx
0x18001f6e0  jz      loc_18001F7DC
0x18001f6e6  mov     rax, [rcx]
0x18001f6e9  lea     r8, [rsp+4C0h+string]
0x18001f6ee  lea     rdx, [rsp+4C0h+var_468]
0x18001f6f3  mov     rax, [rax+10h]
0x18001f6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6fc  nop
0x18001f6fd  mov     rcx, [rsp+4C0h+string]; string
0x18001f702  call    cs:__imp_WindowsDeleteString
0x18001f708  mov     [rsp+4C0h+string], 0
0x18001f711  mov     rcx, [rsp+4C0h+var_468]; string
0x18001f716  call    cs:__imp_WindowsDeleteString
0x18001f71c  mov     [rsp+4C0h+var_468], 0
0x18001f725  inc     edi
0x18001f727  lea     rax, [rsp+4C0h+cbData]
0x18001f72c  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x18001f731  lea     rax, [rbp+3C0h+Data]
0x18001f735  mov     [rsp+4C0h+lpData], rax; lpData
0x18001f73a  lea     rax, [rsp+4C0h+Type]
0x18001f73f  mov     [rsp+4C0h+lpType], rax; lpType
0x18001f744  mov     [rsp+4C0h+lpReserved], 0; lpReserved
0x18001f74d  mov     edx, edi; dwIndex
0x18001f74f  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18001f754  mov     [rsp+4C0h+cchValueName], esi
0x18001f758  mov     [rsp+4C0h+cbData], esi
0x18001f75c  lea     r9, [rsp+4C0h+cchValueName]; lpcchValueName
0x18001f761  lea     r8, [rbp+3C0h+ValueName]; lpValueName
0x18001f768  call    cs:__imp_RegEnumValueW
0x18001f76e  test    eax, eax
0x18001f770  jz      loc_18001F6A1
0x18001f776  lea     rcx, [rsp+4C0h+hKey]; this
0x18001f77b  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001f780  nop
0x18001f781  lea     rcx, [rsp+4C0h+var_458]; this
0x18001f786  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001f78b  nop
0x18001f78c  lea     rcx, [rsp+4C0h+var_450]; this
0x18001f791  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001f796  nop
0x18001f797  mov     rcx, [rbx+38h]
0x18001f79b  test    rcx, rcx
0x18001f79e  jz      short loc_18001F7BA
0x18001f7a0  mov     rax, [rcx]
0x18001f7a3  cmp     rcx, rbx
0x18001f7a6  setnz   dl
0x18001f7a9  mov     rax, [rax+20h]
0x18001f7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7b2  mov     qword ptr [rbx+38h], 0
0x18001f7ba  mov     rcx, [rbp+3C0h+var_20]
0x18001f7c1  xor     rcx, rsp; StackCookie
0x18001f7c4  call    __security_check_cookie
0x18001f7c9  mov     rbx, [rsp+4C0h+arg_18]
0x18001f7d1  add     rsp, 4B0h
0x18001f7d8  pop     rdi
0x18001f7d9  pop     rsi
0x18001f7da  pop     rbp
0x18001f7db  retn
0x18001f7dc  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001f7e2  nop
```
