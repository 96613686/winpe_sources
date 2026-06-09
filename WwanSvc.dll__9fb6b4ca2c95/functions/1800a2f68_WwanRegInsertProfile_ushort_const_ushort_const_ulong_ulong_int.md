# WwanRegInsertProfile(ushort const *,ushort const *,ulong,ulong,int)

- ea: `0x1800a2f68`
- end: `0x1800a31b6`
- name: `?WwanRegInsertProfile@@YAKPEBG0KKH@Z`
- size: `590`
- prototype: `unsigned int __usercall@<eax>(LPCWSTR lpSubKey@<rcx>, const unsigned __int16 *Src@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18009f9f0`
- `0x1800a3e84`

## callees

- `0x180012300`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x1800a2f68`
- `0x1800a38c4`
- `0x1800a39b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a3002`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a305f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a3002`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a305f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3083`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a30ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3181`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3083`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a30ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3181`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2fc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2fc9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a30b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a30e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a30b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a30e2`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a3113`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a3177`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a3113`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a3177`

## string_xrefs

- `0x1800a306e`: `RegCreateKeyEx failed, errCode (0x%8x)`
- `0x1800a3011`: `RegOpenKeyEx failed, errCode (0x%8x)`
- `0x1800a30f8`: `RegSetValueEx failed, errCode (0x%8x)`

## pseudocode

```c
__int64 __fastcall WwanRegInsertProfile(LPCWSTR lpSubKey, WCHAR *Src, int a3, int a4, int a5)
{
  unsigned int v7; // eax
  unsigned int inited; // ebx
  unsigned int v9; // eax
  unsigned int v10; // eax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v13; // [rsp+58h] [rbp-8h] BYREF
  int Data; // [rsp+90h] [rbp+30h] BYREF
  int v15; // [rsp+98h] [rbp+38h] BYREF

  v15 = a4;
  Data = a3;
  WwanLog::Enter("WwanRegInsertProfile");
  hKey = 0;
  v13 = 0;
  if ( a5 )
    v7 = RegCreateKeyExW(::hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  else
    v7 = RegOpenKeyExW(qword_180152870, lpSubKey, 0, 0x2001Fu, &hKey);
  inited = v7;
  if ( v7 )
  {
    WwanLog::Error("WwanRegInsertProfile", 0, L"RegOpenKeyEx failed, errCode (0x%8x)", v7);
    goto LABEL_20;
  }
  v9 = RegCreateKeyExW(hKey, Src, 0, 0, 0, 0x20006u, 0, &v13, 0);
  inited = v9;
  if ( v9 )
  {
    WwanLog::Error("WwanRegInsertProfile", 0, L"RegCreateKeyEx failed, errCode (0x%8x)", v9);
LABEL_8:
    RegCloseKey(hKey);
    goto LABEL_20;
  }
  inited = RegSetValueExW(v13, L"dwFlags", 0, 4u, (const BYTE *)&Data, 4u);
  if ( !inited )
    inited = RegSetValueExW(v13, L"ProfileIndex", 0, 4u, (const BYTE *)&v15, 4u);
  RegCloseKey(v13);
  if ( inited )
  {
    WwanLog::Error("WwanRegInsertProfile", 0, L"RegSetValueEx failed, errCode (0x%8x)", inited);
LABEL_13:
    RegDeleteKeyW(hKey, Src);
    goto LABEL_8;
  }
  if ( a5 )
  {
    inited = initMultiSzVal(hKey, L"ProfileList");
    if ( inited )
    {
      WwanLog::Error("WwanRegInsertProfile", 0, L"_initMultiSzVal failed, errCode (0x%8x)", inited);
      goto LABEL_13;
    }
  }
  v10 = insMultiSzVal(hKey, L"ProfileList", Src);
  inited = v10;
  if ( v10 )
  {
    WwanLog::Error("WwanRegInsertProfile", 0, L"_insMultiSzVal failed, errCode (0x%8x)", v10);
    RegDeleteKeyW(hKey, Src);
  }
  RegCloseKey(hKey);
  WwanLog::Verbose("WwanRegInsertProfile", 0, L"errCode (0x%8x)", inited);
LABEL_20:
  WwanLog::Exit("WwanRegInsertProfile");
  return inited;
}

```

## disassembly

```asm
0x1800a2f68  mov     [rsp-18h+arg_0], rbx
0x1800a2f6d  mov     [rsp-18h+arg_18], r9d
0x1800a2f72  mov     [rsp-18h+Data], r8d
0x1800a2f77  push    rbp
0x1800a2f78  push    rdi
0x1800a2f79  push    r15
0x1800a2f7b  mov     rbp, rsp
0x1800a2f7e  sub     rsp, 60h
0x1800a2f82  mov     rbx, rcx
0x1800a2f85  lea     r15, aWwanreginsertp_0; "WwanRegInsertProfile"
0x1800a2f8c  mov     rcx, r15; char *
0x1800a2f8f  mov     rdi, rdx
0x1800a2f92  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a2f97  xor     r8d, r8d; Reserved
0x1800a2f9a  mov     [rbp+hKey], 0
0x1800a2fa2  lea     rax, [rbp+hKey]
0x1800a2fa6  mov     [rbp+var_8], 0
0x1800a2fae  mov     rdx, rbx; lpSubKey
0x1800a2fb1  cmp     [rbp+arg_20], r8d
0x1800a2fb5  jnz     short loc_1800A2FD1
0x1800a2fb7  mov     rcx, cs:qword_180152870; hKey
0x1800a2fbe  mov     r9d, 2001Fh; samDesired
0x1800a2fc4  mov     [rsp+60h+phkResult], rax; phkResult
0x1800a2fc9  call    cs:__imp_RegOpenKeyExW
0x1800a2fcf  jmp     short loc_1800A3008
0x1800a2fd1  mov     rcx, cs:hKey; hKey
0x1800a2fd8  xor     r9d, r9d; lpClass
0x1800a2fdb  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800a2fe4  mov     [rsp+60h+var_28], rax; phkResult
0x1800a2fe9  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a2ff2  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x1800a2ffa  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x1800a3002  call    cs:__imp_RegCreateKeyExW
0x1800a3008  mov     ebx, eax
0x1800a300a  test    eax, eax
0x1800a300c  jz      short loc_1800A3027
0x1800a300e  mov     r9d, eax
0x1800a3011  lea     r8, aRegopenkeyexFa_1; "RegOpenKeyEx failed, errCode (0x%8x)"
0x1800a3018  xor     edx, edx; struct _GUID *
0x1800a301a  mov     rcx, r15; char *
0x1800a301d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a3022  jmp     loc_1800A319B
0x1800a3027  mov     rcx, [rbp+hKey]; hKey
0x1800a302b  lea     rax, [rbp+var_8]
0x1800a302f  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800a3038  xor     r9d, r9d; lpClass
0x1800a303b  mov     [rsp+60h+var_28], rax; phkResult
0x1800a3040  xor     r8d, r8d; Reserved
0x1800a3043  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a304c  mov     rdx, rdi; lpSubKey
0x1800a304f  mov     [rsp+60h+samDesired], 20006h; samDesired
0x1800a3057  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x1800a305f  call    cs:__imp_RegCreateKeyExW
0x1800a3065  mov     ebx, eax
0x1800a3067  test    eax, eax
0x1800a3069  jz      short loc_1800A308E
0x1800a306b  mov     r9d, eax
0x1800a306e  lea     r8, aRegcreatekeyex_0; "RegCreateKeyEx failed, errCode (0x%8x)"
0x1800a3075  xor     edx, edx; struct _GUID *
0x1800a3077  mov     rcx, r15; char *
0x1800a307a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a307f  mov     rcx, [rbp+hKey]; hKey
0x1800a3083  call    cs:__imp_RegCloseKey
0x1800a3089  jmp     loc_1800A319B
0x1800a308e  mov     rcx, [rbp+var_8]; hKey
0x1800a3092  lea     rax, [rbp+Data]
0x1800a3096  mov     [rsp+60h+samDesired], 4; cbData
0x1800a309e  lea     rdx, aDwflags; "dwFlags"
0x1800a30a5  mov     r9d, 4; dwType
0x1800a30ab  mov     [rsp+60h+phkResult], rax; lpData
0x1800a30b0  xor     r8d, r8d; Reserved
0x1800a30b3  call    cs:__imp_RegSetValueExW
0x1800a30b9  mov     ebx, eax
0x1800a30bb  test    eax, eax
0x1800a30bd  jnz     short loc_1800A30EA
0x1800a30bf  mov     rcx, [rbp+var_8]; hKey
0x1800a30c3  lea     rax, [rbp+arg_18]
0x1800a30c7  mov     [rsp+60h+samDesired], 4; cbData
0x1800a30cf  lea     r9d, [rbx+4]; dwType
0x1800a30d3  xor     r8d, r8d; Reserved
0x1800a30d6  mov     [rsp+60h+phkResult], rax; lpData
0x1800a30db  lea     rdx, aProfileindex; "ProfileIndex"
0x1800a30e2  call    cs:__imp_RegSetValueExW
0x1800a30e8  mov     ebx, eax
0x1800a30ea  mov     rcx, [rbp+var_8]; hKey
0x1800a30ee  call    cs:__imp_RegCloseKey
0x1800a30f4  test    ebx, ebx
0x1800a30f6  jz      short loc_1800A311E
0x1800a30f8  lea     r8, aRegsetvalueexF_0; "RegSetValueEx failed, errCode (0x%8x)"
0x1800a30ff  mov     r9d, ebx
0x1800a3102  xor     edx, edx; struct _GUID *
0x1800a3104  mov     rcx, r15; char *
0x1800a3107  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a310c  mov     rcx, [rbp+hKey]; hKey
0x1800a3110  mov     rdx, rdi; lpSubKey
0x1800a3113  call    cs:__imp_RegDeleteKeyW
0x1800a3119  jmp     loc_1800A307F
0x1800a311e  cmp     [rbp+arg_20], 0
0x1800a3122  jz      short loc_1800A3143
0x1800a3124  mov     rcx, [rbp+hKey]; hKey
0x1800a3128  lea     rdx, aProfilelist; "ProfileList"
0x1800a312f  call    _initMultiSzVal
0x1800a3134  mov     ebx, eax
0x1800a3136  test    eax, eax
0x1800a3138  jz      short loc_1800A3143
0x1800a313a  lea     r8, aInitmultiszval_0; "_initMultiSzVal failed, errCode (0x%8x)"
0x1800a3141  jmp     short loc_1800A30FF
0x1800a3143  mov     rcx, [rbp+hKey]; hKey
0x1800a3147  lea     rdx, aProfilelist; "ProfileList"
0x1800a314e  mov     r8, rdi; Src
0x1800a3151  call    _insMultiSzVal
0x1800a3156  mov     ebx, eax
0x1800a3158  test    eax, eax
0x1800a315a  jz      short loc_1800A317D
0x1800a315c  mov     r9d, eax
0x1800a315f  lea     r8, aInsmultiszvalF; "_insMultiSzVal failed, errCode (0x%8x)"
0x1800a3166  xor     edx, edx; struct _GUID *
0x1800a3168  mov     rcx, r15; char *
0x1800a316b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a3170  mov     rcx, [rbp+hKey]; hKey
0x1800a3174  mov     rdx, rdi; lpSubKey
0x1800a3177  call    cs:__imp_RegDeleteKeyW
0x1800a317d  mov     rcx, [rbp+hKey]; hKey
0x1800a3181  call    cs:__imp_RegCloseKey
0x1800a3187  mov     r9d, ebx
0x1800a318a  lea     r8, aErrcode0x8x; "errCode (0x%8x)"
0x1800a3191  xor     edx, edx; struct _GUID *
0x1800a3193  mov     rcx, r15; char *
0x1800a3196  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800a319b  mov     rcx, r15; char *
0x1800a319e  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a31a3  mov     eax, ebx
0x1800a31a5  mov     rbx, [rsp+60h+arg_0]
0x1800a31ad  add     rsp, 60h
0x1800a31b1  pop     r15
0x1800a31b3  pop     rdi
0x1800a31b4  pop     rbp
0x1800a31b5  retn
```
