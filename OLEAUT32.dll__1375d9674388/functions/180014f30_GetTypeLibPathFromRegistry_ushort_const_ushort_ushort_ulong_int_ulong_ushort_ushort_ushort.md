# GetTypeLibPathFromRegistry(ushort const *,ushort,ushort,ulong,int,ulong,ushort *,ushort *,ushort *)

- ea: `0x180014f30`
- end: `0x1800150fb`
- name: `?GetTypeLibPathFromRegistry@@YAJPEBGGGKHKPEAG11@Z`
- size: `459`
- prototype: `int(const unsigned __int16 *, unsigned __int16, unsigned __int16, unsigned int, int, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014840`

## callees

- `0x180014f30`
- `0x180015104`
- `0x1800153bc`
- `0x180015414`
- `0x1800161b8`
- `0x18004d900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180014ff3`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180014ff3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015058`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015058`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015083`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800150bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800150e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015083`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800150bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800150e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001501b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001501b`

## string_xrefs

- `0x1800150d1`: `mincore\com\oleaut32\typelib\tlibapi.cpp`

## pseudocode

```c
__int64 __fastcall GetTypeLibPathFromRegistry(
        const unsigned __int16 *a1,
        int a2,
        unsigned __int16 a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        unsigned __int16 *pvData,
        unsigned __int16 *a8,
        unsigned __int16 *a9)
{
  int BestLcidMatch; // eax
  unsigned int v11; // ebx
  __int64 v13; // rdx
  int phkResult; // [rsp+20h] [rbp-81h]
  unsigned __int16 v15[2]; // [rsp+40h] [rbp-61h] BYREF
  unsigned __int16 v16; // [rsp+44h] [rbp-5Dh] BYREF
  unsigned int v17; // [rsp+48h] [rbp-59h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-51h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-49h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-41h] BYREF
  int v21[4]; // [rsp+68h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-29h]
  WCHAR SubKey[8]; // [rsp+80h] [rbp-21h] BYREF
  __int16 v24; // [rsp+90h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+37h]

  v15[0] = 0;
  v16 = 0;
  *(_OWORD *)v21 = 0;
  hKey = 0;
  BestLcidMatch = OpenTypeLibKey(a1, a2, a3, a5, (HKEY *)v21, v15, &v16);
  v11 = BestLcidMatch;
  if ( BestLcidMatch < 0 )
  {
    v13 = 2426;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"mincore\\com\\oleaut32\\typelib\\tlibapi.cpp",
      (const char *)(unsigned int)BestLcidMatch,
      phkResult);
    goto LABEL_12;
  }
  v17 = 0;
  lpSubKey = 0;
  BestLcidMatch = GetBestLcidMatch(hKey, a4, &v17, &lpSubKey);
  v11 = BestLcidMatch;
  if ( BestLcidMatch < 0 )
  {
    v13 = 2431;
    goto LABEL_17;
  }
  *(_OWORD *)SubKey = 0;
  v24 = 0;
  _o__ultow_s(v17, SubKey, 9, 16);
  hkey = 0;
  if ( RegOpenKeyExW(hKey, SubKey, 0, 0x2000000u, &hkey) )
  {
    if ( hkey )
      RegCloseKey(hkey);
    v11 = -2147319779;
  }
  else
  {
    pcbData = 520;
    if ( RegGetValueW(hkey, lpSubKey, 0, 6u, 0, pvData, &pcbData) )
    {
      if ( hkey )
        RegCloseKey(hkey);
      v11 = -2147319780;
    }
    else
    {
      if ( a8 )
        *a8 = v15[0];
      if ( a9 )
        *a9 = v16;
      if ( hkey )
        RegCloseKey(hkey);
      v11 = 0;
    }
  }
LABEL_12:
  TLIBKEY::~TLIBKEY((TLIBKEY *)v21);
  return v11;
}

```

## disassembly

```asm
0x180014f30  push    rbp
0x180014f32  push    rbx
0x180014f33  push    rsi
0x180014f34  push    rdi
0x180014f35  push    r14
0x180014f37  push    r15
0x180014f39  lea     rbp, [rsp-7]
0x180014f3e  sub     rsp, 0A8h
0x180014f45  mov     rax, cs:__security_cookie
0x180014f4c  xor     rax, rsp
0x180014f4f  mov     [rbp+2Fh+var_38], rax
0x180014f53  mov     r15, [rbp+2Fh+arg_30]
0x180014f57  xor     eax, eax
0x180014f59  mov     rsi, [rbp+2Fh+arg_38]
0x180014f5d  mov     r14d, r9d
0x180014f60  mov     r9d, [rbp+2Fh+arg_20]; int
0x180014f64  xorps   xmm0, xmm0
0x180014f67  mov     rdi, [rbp+2Fh+arg_40]
0x180014f6b  mov     [rbp+2Fh+var_90], ax
0x180014f6f  mov     [rbp+2Fh+var_8C], ax
0x180014f73  lea     rax, [rbp+2Fh+var_8C]
0x180014f77  mov     [rsp+0D0h+pcbData], rax; unsigned __int16 *
0x180014f7c  lea     rax, [rbp+2Fh+var_90]
0x180014f80  mov     [rsp+0D0h+pvData], rax; unsigned __int16 *
0x180014f85  lea     rax, [rbp+2Fh+var_68]
0x180014f89  mov     [rsp+0D0h+phkResult], rax; int
0x180014f8e  movdqu  xmmword ptr [rbp+2Fh+var_68], xmm0
0x180014f93  mov     [rbp+2Fh+hKey], 0
0x180014f9b  call    ?OpenTypeLibKey@@YAJPEBGGGHPEAUTLIBKEY@@PEAG2@Z; OpenTypeLibKey(ushort const *,ushort,ushort,int,TLIBKEY *,ushort *,ushort *)
0x180014fa0  mov     ebx, eax
0x180014fa2  test    eax, eax
0x180014fa4  js      loc_1800150C8
0x180014faa  mov     rcx, [rbp+2Fh+hKey]; HKEY
0x180014fae  lea     r9, [rbp+2Fh+lpSubKey]; unsigned __int16 **
0x180014fb2  lea     r8, [rbp+2Fh+var_88]; unsigned int *
0x180014fb6  mov     [rbp+2Fh+var_88], 0
0x180014fbd  mov     edx, r14d; unsigned int
0x180014fc0  mov     [rbp+2Fh+lpSubKey], 0
0x180014fc8  call    ?GetBestLcidMatch@@YAJPEAUHKEY__@@KPEAKPEAPEBG@Z; GetBestLcidMatch(HKEY__ *,ulong,ulong *,ushort const * *)
0x180014fcd  mov     ebx, eax
0x180014fcf  test    eax, eax
0x180014fd1  js      loc_1800150F4
0x180014fd7  mov     ecx, [rbp+2Fh+var_88]
0x180014fda  lea     rdx, [rbp+2Fh+SubKey]
0x180014fde  xor     eax, eax
0x180014fe0  xorps   xmm0, xmm0
0x180014fe3  movups  xmmword ptr [rbp+2Fh+SubKey], xmm0
0x180014fe7  mov     [rbp+2Fh+var_40], ax
0x180014feb  lea     r9d, [rax+10h]
0x180014fef  lea     r8d, [rax+9]
0x180014ff3  call    cs:__imp__o__ultow_s
0x180014ff9  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180014ffd  lea     rax, [rbp+2Fh+hkey]
0x180015001  mov     r9d, 2000000h; samDesired
0x180015007  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18001500c  xor     r8d, r8d; ulOptions
0x18001500f  mov     [rbp+2Fh+hkey], 0
0x180015017  lea     rdx, [rbp+2Fh+SubKey]; lpSubKey
0x18001501b  call    cs:__imp_RegOpenKeyExW
0x180015021  mov     rcx, [rbp+2Fh+hkey]; hKey
0x180015025  test    eax, eax
0x180015027  jnz     loc_1800150E2
0x18001502d  mov     rdx, [rbp+2Fh+lpSubKey]; lpSubKey
0x180015031  lea     rax, [rbp+2Fh+var_78]
0x180015035  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18001503a  mov     r9d, 6; dwFlags
0x180015040  mov     [rsp+0D0h+pvData], r15; pvData
0x180015045  xor     r8d, r8d; lpValue
0x180015048  mov     [rsp+0D0h+phkResult], 0; pdwType
0x180015051  mov     [rbp+2Fh+var_78], 208h
0x180015058  call    cs:__imp_RegGetValueW
0x18001505e  test    eax, eax
0x180015060  jnz     short loc_1800150B2
0x180015062  test    rsi, rsi
0x180015065  jz      short loc_18001506E
0x180015067  movzx   eax, [rbp+2Fh+var_90]
0x18001506b  mov     [rsi], ax
0x18001506e  test    rdi, rdi
0x180015071  jz      short loc_18001507A
0x180015073  movzx   eax, [rbp+2Fh+var_8C]
0x180015077  mov     [rdi], ax
0x18001507a  mov     rcx, [rbp+2Fh+hkey]; hKey
0x18001507e  test    rcx, rcx
0x180015081  jz      short loc_180015089
0x180015083  call    cs:__imp_RegCloseKey
0x180015089  xor     ebx, ebx
0x18001508b  lea     rcx, [rbp+2Fh+var_68]; this
0x18001508f  call    ??1TLIBKEY@@QEAA@XZ; TLIBKEY::~TLIBKEY(void)
0x180015094  mov     eax, ebx
0x180015096  mov     rcx, [rbp+2Fh+var_38]
0x18001509a  xor     rcx, rsp; StackCookie
0x18001509d  call    __security_check_cookie
0x1800150a2  add     rsp, 0A8h
0x1800150a9  pop     r15
0x1800150ab  pop     r14
0x1800150ad  pop     rdi
0x1800150ae  pop     rsi
0x1800150af  pop     rbx
0x1800150b0  pop     rbp
0x1800150b1  retn
0x1800150b2  mov     rcx, [rbp+2Fh+hkey]; hKey
0x1800150b6  test    rcx, rcx
0x1800150b9  jz      short loc_1800150C1
0x1800150bb  call    cs:__imp_RegCloseKey
0x1800150c1  mov     ebx, 8002801Ch
0x1800150c6  jmp     short loc_18001508B
0x1800150c8  mov     edx, 97Ah; void *
0x1800150cd  mov     rcx, [rbp+37h]; this
0x1800150d1  lea     r8, aMincoreComOlea_3; "mincore\\com\\oleaut32\\typelib\\tlibap"...
0x1800150d8  mov     r9d, eax; char *
0x1800150db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800150e0  jmp     short loc_18001508B
0x1800150e2  test    rcx, rcx
0x1800150e5  jz      short loc_1800150ED
0x1800150e7  call    cs:__imp_RegCloseKey
0x1800150ed  mov     ebx, 8002801Dh
0x1800150f2  jmp     short loc_18001508B
0x1800150f4  mov     edx, 97Fh
0x1800150f9  jmp     short loc_1800150CD
```
