# CompModelFromCLSID(_GUID const &,ulong *,int *)

- ea: `0x18003776c`
- end: `0x18003796c`
- name: `?CompModelFromCLSID@@YAJAEBU_GUID@@PEAKPEAH@Z`
- size: `512`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int *, int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180037528`
- `0x18003929c`
- `0x180057330`
- `0x18005eec8`

## callees

- `0x180023dd0`
- `0x1800375c8`
- `0x18003776c`
- `0x180038a64`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180037908`
- `ADVAPI32!RegCloseKey` at `0x180037917`
- `ADVAPI32!RegCloseKey` at `0x180037926`
- `ADVAPI32!RegCloseKey` at `0x180037908`
- `ADVAPI32!RegCloseKey` at `0x180037917`
- `ADVAPI32!RegCloseKey` at `0x180037926`
- `ADVAPI32!RegQueryValueExA` at `0x1800378a1`
- `ADVAPI32!RegQueryValueExA` at `0x1800378ec`
- `ADVAPI32!RegQueryValueExA` at `0x1800378a1`
- `ADVAPI32!RegQueryValueExA` at `0x1800378ec`
- `ADVAPI32!RegOpenKeyExA` at `0x180037814`
- `ADVAPI32!RegOpenKeyExA` at `0x180037838`
- `ADVAPI32!RegOpenKeyExA` at `0x180037869`
- `ADVAPI32!RegOpenKeyExA` at `0x180037814`
- `ADVAPI32!RegOpenKeyExA` at `0x180037838`
- `ADVAPI32!RegOpenKeyExA` at `0x180037869`

## string_xrefs

- `0x180037803`: `CLSID`
- `0x180037884`: `ThreadingModel`
- `0x1800378cf`: `ASPComponentNonAgile`

## pseudocode

```c
__int64 __fastcall CompModelFromCLSID(const struct _GUID *a1, unsigned int *a2, int *a3)
{
  __int64 result; // rax
  unsigned int v6; // ebx
  int v7; // esi
  int v8; // r15d
  LSTATUS v9; // eax
  DWORD cbData; // [rsp+30h] [rbp-49h] BYREF
  HKEY v11; // [rsp+38h] [rbp-41h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-31h] BYREF
  BYTE Data[16]; // [rsp+50h] [rbp-29h] BYREF
  char v15; // [rsp+64h] [rbp-15h]
  CHAR SubKey[56]; // [rsp+70h] [rbp-9h] BYREF

  if ( (_BYTE)xmmword_180079F90 || a3 )
  {
    *(struct _GUID *)Data = *a1;
    result = CLSIDToMultibyteString(Data, SubKey);
    v6 = result;
    if ( (int)result >= 0 )
    {
      hKey = 0;
      v7 = 1;
      phkResult = 0;
      v11 = 0;
      v8 = 1;
      if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20019u, &hKey)
        || RegOpenKeyExA(hKey, SubKey, 0, 0x20019u, &phkResult) )
      {
        v6 = -2147467259;
      }
      else if ( RegOpenKeyExA(phkResult, "InprocServer32", 0, 0x20019u, &v11) )
      {
        v8 = 0;
      }
      else
      {
        cbData = 21;
        v9 = RegQueryValueExA(v11, "ThreadingModel", 0, 0, Data, &cbData);
        v15 = 0;
        if ( !v9 )
        {
          v7 = RegStrToCompModel((char *)Data, cbData);
          if ( v7 == 8 )
          {
            cbData = 21;
            if ( !RegQueryValueExA(v11, "ASPComponentNonAgile", 0, 0, Data, &cbData) )
              v7 = 2;
          }
        }
      }
      if ( v11 )
        RegCloseKey(v11);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( hKey )
        RegCloseKey(hKey);
      if ( a2 )
        *a2 = (_BYTE)xmmword_180079F90 != 0 ? v7 : 0;
      if ( a3 )
        *a3 = v8;
      return v6;
    }
  }
  else
  {
    if ( a2 )
      *a2 = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003776c  mov     [rsp-8+arg_18], rbx
0x180037771  push    rbp
0x180037772  push    rsi
0x180037773  push    rdi
0x180037774  push    r14
0x180037776  push    r15
0x180037778  lea     rbp, [rsp-37h]
0x18003777d  sub     rsp, 0B0h
0x180037784  mov     rax, cs:__security_cookie
0x18003778b  xor     rax, rsp
0x18003778e  mov     [rbp+57h+var_28], rax
0x180037792  cmp     byte ptr cs:xmmword_180079F90, 0
0x180037799  mov     r14, r8
0x18003779c  mov     rdi, rdx
0x18003779f  jnz     short loc_1800377B5
0x1800377a1  test    r8, r8
0x1800377a4  jnz     short loc_1800377B5
0x1800377a6  test    rdx, rdx
0x1800377a9  jz      short loc_1800377AE
0x1800377ab  mov     [rdx], r8d
0x1800377ae  xor     eax, eax
0x1800377b0  jmp     loc_180037949
0x1800377b5  movups  xmm0, xmmword ptr [rcx]
0x1800377b8  lea     rdx, [rbp+57h+SubKey]
0x1800377bc  lea     rcx, [rbp+57h+Data]
0x1800377c0  movdqu  xmmword ptr [rbp+57h+Data], xmm0
0x1800377c5  call    CLSIDToMultibyteString
0x1800377ca  mov     ebx, eax
0x1800377cc  test    eax, eax
0x1800377ce  js      loc_180037949
0x1800377d4  lea     rax, [rbp+57h+hKey]
0x1800377d8  mov     [rbp+57h+hKey], 0
0x1800377e0  mov     esi, 1
0x1800377e5  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800377ea  mov     r9d, 20019h; samDesired
0x1800377f0  mov     [rbp+57h+var_90], 0
0x1800377f8  xor     r8d, r8d; ulOptions
0x1800377fb  mov     [rbp+57h+var_98], 0
0x180037803  lea     rdx, aClsid_0; "CLSID"
0x18003780a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180037811  mov     r15d, esi
0x180037814  call    cs:__imp_RegOpenKeyExA
0x18003781a  test    eax, eax
0x18003781c  jnz     short loc_180037842
0x18003781e  mov     rcx, [rbp+57h+hKey]; hKey
0x180037822  lea     rax, [rbp+57h+var_90]
0x180037826  mov     r9d, 20019h; samDesired
0x18003782c  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180037831  xor     r8d, r8d; ulOptions
0x180037834  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180037838  call    cs:__imp_RegOpenKeyExA
0x18003783e  test    eax, eax
0x180037840  jz      short loc_18003784C
0x180037842  mov     ebx, 80004005h
0x180037847  jmp     loc_1800378FF
0x18003784c  mov     rcx, [rbp+57h+var_90]; hKey
0x180037850  lea     rax, [rbp+57h+var_98]
0x180037854  mov     r9d, 20019h; samDesired
0x18003785a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18003785f  xor     r8d, r8d; ulOptions
0x180037862  lea     rdx, aInprocserver32; "InprocServer32"
0x180037869  call    cs:__imp_RegOpenKeyExA
0x18003786f  test    eax, eax
0x180037871  jnz     loc_1800378FC
0x180037877  mov     rcx, [rbp+57h+var_98]; hKey
0x18003787b  lea     rax, [rbp+57h+cbData]
0x18003787f  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180037884  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18003788b  lea     rax, [rbp+57h+Data]
0x18003788f  mov     [rbp+57h+cbData], 15h
0x180037896  xor     r9d, r9d; lpType
0x180037899  mov     [rsp+0D0h+phkResult], rax; lpData
0x18003789e  xor     r8d, r8d; lpReserved
0x1800378a1  call    cs:__imp_RegQueryValueExA
0x1800378a7  mov     [rbp+57h+var_6C], 0
0x1800378ab  test    eax, eax
0x1800378ad  jnz     short loc_1800378FF
0x1800378af  mov     edx, [rbp+57h+cbData]; MaxCount
0x1800378b2  lea     rcx, [rbp+57h+Data]; String1
0x1800378b6  call    RegStrToCompModel
0x1800378bb  mov     esi, eax
0x1800378bd  cmp     eax, 8
0x1800378c0  jnz     short loc_1800378FF
0x1800378c2  mov     rcx, [rbp+57h+var_98]; hKey
0x1800378c6  lea     rax, [rbp+57h+cbData]
0x1800378ca  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800378cf  lea     rdx, aAspcomponentno; "ASPComponentNonAgile"
0x1800378d6  lea     rax, [rbp+57h+Data]
0x1800378da  mov     [rbp+57h+cbData], 15h
0x1800378e1  xor     r9d, r9d; lpType
0x1800378e4  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800378e9  xor     r8d, r8d; lpReserved
0x1800378ec  call    cs:__imp_RegQueryValueExA
0x1800378f2  test    eax, eax
0x1800378f4  lea     ecx, [rsi-6]
0x1800378f7  cmovz   esi, ecx
0x1800378fa  jmp     short loc_1800378FF
0x1800378fc  xor     r15d, r15d
0x1800378ff  mov     rcx, [rbp+57h+var_98]; hKey
0x180037903  test    rcx, rcx
0x180037906  jz      short loc_18003790E
0x180037908  call    cs:__imp_RegCloseKey
0x18003790e  mov     rcx, [rbp+57h+var_90]; hKey
0x180037912  test    rcx, rcx
0x180037915  jz      short loc_18003791D
0x180037917  call    cs:__imp_RegCloseKey
0x18003791d  mov     rcx, [rbp+57h+hKey]; hKey
0x180037921  test    rcx, rcx
0x180037924  jz      short loc_18003792C
0x180037926  call    cs:__imp_RegCloseKey
0x18003792c  test    rdi, rdi
0x18003792f  jz      short loc_18003793F
0x180037931  mov     cl, byte ptr cs:xmmword_180079F90
0x180037937  neg     cl
0x180037939  sbb     edx, edx
0x18003793b  and     edx, esi
0x18003793d  mov     [rdi], edx
0x18003793f  test    r14, r14
0x180037942  jz      short loc_180037947
0x180037944  mov     [r14], r15d
0x180037947  mov     eax, ebx
0x180037949  mov     rcx, [rbp+57h+var_28]
0x18003794d  xor     rcx, rsp; StackCookie
0x180037950  call    __security_check_cookie
0x180037955  mov     rbx, [rsp+0D0h+arg_18]
0x18003795d  add     rsp, 0B0h
0x180037964  pop     r15
0x180037966  pop     r14
0x180037968  pop     rdi
0x180037969  pop     rsi
0x18003796a  pop     rbp
0x18003796b  retn
```
