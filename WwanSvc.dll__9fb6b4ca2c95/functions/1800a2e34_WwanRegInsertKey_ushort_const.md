# WwanRegInsertKey(ushort const *)

- ea: `0x1800a2e34`
- end: `0x1800a2f5f`
- name: `?WwanRegInsertKey@@YAKPEBG@Z`
- size: `299`
- prototype: `unsigned int __fastcall(const unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18009b6c8`

## callees

- `0x180012300`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x1800a2e34`
- `0x1800a38c4`
- `0x1800a39b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2e9a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2e9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2ed7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2ed7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a2f2c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a2f2c`

## string_xrefs

- `0x1800a2ea9`: `RegCreateKeyEx failed, errCode (0x%8x)`

## pseudocode

```c
__int64 __fastcall WwanRegInsertKey(WCHAR *Src)
{
  unsigned int v2; // eax
  unsigned int inited; // ebx
  unsigned int v4; // eax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  WwanLog::Enter("WwanRegInsertKey");
  hKey = 0;
  v2 = RegCreateKeyExW(qword_180152870, Src, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  inited = v2;
  if ( v2 )
  {
    WwanLog::Error("WwanRegInsertKey", 0, L"RegCreateKeyEx failed, errCode (0x%8x)", v2);
  }
  else
  {
    inited = initMultiSzVal(hKey, L"ProfileList");
    RegCloseKey(hKey);
    if ( inited )
    {
      WwanLog::Error("WwanRegInsertKey", 0, L"_initMultiSzVal failed, errCode (0x%8x)", inited);
    }
    else
    {
      v4 = insMultiSzVal(qword_180152870, L"KeyList", Src);
      inited = v4;
      if ( !v4 )
      {
        WwanLog::Verbose("WwanRegInsertKey", 0, L"errCode (0x%8x)", 0);
        inited = 0;
        goto LABEL_9;
      }
      WwanLog::Error("WwanRegInsertKey", 0, L"_insMultiSzVal failed, errCode (0x%8x)", v4);
    }
    RegDeleteKeyW(qword_180152870, Src);
  }
LABEL_9:
  WwanLog::Exit("WwanRegInsertKey");
  return inited;
}

```

## disassembly

```asm
0x1800a2e34  mov     [rsp+arg_0], rbx
0x1800a2e39  mov     [rsp+arg_10], rsi
0x1800a2e3e  push    rdi
0x1800a2e3f  sub     rsp, 50h
0x1800a2e43  mov     rdi, rcx
0x1800a2e46  lea     rsi, aWwanreginsertk_0; "WwanRegInsertKey"
0x1800a2e4d  mov     rcx, rsi; char *
0x1800a2e50  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a2e55  mov     rcx, cs:qword_180152870; hKey
0x1800a2e5c  lea     rax, [rsp+58h+hKey]
0x1800a2e61  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800a2e6a  xor     r9d, r9d; lpClass
0x1800a2e6d  mov     [rsp+58h+phkResult], rax; phkResult
0x1800a2e72  xor     r8d, r8d; Reserved
0x1800a2e75  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a2e7e  mov     rdx, rdi; lpSubKey
0x1800a2e81  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800a2e89  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800a2e91  mov     [rsp+58h+hKey], 0
0x1800a2e9a  call    cs:__imp_RegCreateKeyExW
0x1800a2ea0  mov     ebx, eax
0x1800a2ea2  test    eax, eax
0x1800a2ea4  jz      short loc_1800A2EBF
0x1800a2ea6  mov     r9d, eax
0x1800a2ea9  lea     r8, aRegcreatekeyex_0; "RegCreateKeyEx failed, errCode (0x%8x)"
0x1800a2eb0  xor     edx, edx; struct _GUID *
0x1800a2eb2  mov     rcx, rsi; char *
0x1800a2eb5  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a2eba  jmp     loc_1800A2F45
0x1800a2ebf  mov     rcx, [rsp+58h+hKey]; hKey
0x1800a2ec4  lea     rdx, aProfilelist; "ProfileList"
0x1800a2ecb  call    _initMultiSzVal
0x1800a2ed0  mov     rcx, [rsp+58h+hKey]; hKey
0x1800a2ed5  mov     ebx, eax
0x1800a2ed7  call    cs:__imp_RegCloseKey
0x1800a2edd  test    ebx, ebx
0x1800a2edf  jz      short loc_1800A2EF2
0x1800a2ee1  mov     r9d, ebx
0x1800a2ee4  lea     r8, aInitmultiszval_0; "_initMultiSzVal failed, errCode (0x%8x)"
0x1800a2eeb  xor     edx, edx
0x1800a2eed  mov     rcx, rsi
0x1800a2ef0  jmp     short loc_1800A2F1D
0x1800a2ef2  mov     rcx, cs:qword_180152870; hKey
0x1800a2ef9  lea     rdx, aKeylist; "KeyList"
0x1800a2f00  mov     r8, rdi; Src
0x1800a2f03  call    _insMultiSzVal
0x1800a2f08  xor     edx, edx; struct _GUID *
0x1800a2f0a  mov     ebx, eax
0x1800a2f0c  mov     rcx, rsi; char *
0x1800a2f0f  test    eax, eax
0x1800a2f11  jz      short loc_1800A2F34
0x1800a2f13  mov     r9d, eax
0x1800a2f16  lea     r8, aInsmultiszvalF; "_insMultiSzVal failed, errCode (0x%8x)"
0x1800a2f1d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a2f22  mov     rcx, cs:qword_180152870; hKey
0x1800a2f29  mov     rdx, rdi; lpSubKey
0x1800a2f2c  call    cs:__imp_RegDeleteKeyW
0x1800a2f32  jmp     short loc_1800A2F45
0x1800a2f34  xor     r9d, r9d
0x1800a2f37  lea     r8, aErrcode0x8x; "errCode (0x%8x)"
0x1800a2f3e  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800a2f43  xor     ebx, ebx
0x1800a2f45  mov     rcx, rsi; char *
0x1800a2f48  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a2f4d  mov     rsi, [rsp+58h+arg_10]
0x1800a2f52  mov     eax, ebx
0x1800a2f54  mov     rbx, [rsp+58h+arg_0]
0x1800a2f59  add     rsp, 50h
0x1800a2f5d  pop     rdi
0x1800a2f5e  retn
```
