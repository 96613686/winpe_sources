# AcmEngineSetBaseWorkingDirectory(void *,ushort const *)

- ea: `0x18004e7f0`
- end: `0x18004ea90`
- name: `?AcmEngineSetBaseWorkingDirectory@@YAJPEAXPEBG@Z`
- size: `672`
- prototype: `__int64 __fastcall(BYTE *lpData, PCWSTR FileName)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000a51c`
- `0x18004e6e4`
- `0x18004e7f0`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x18004e855`
- `ntdll!RtlDoesFileExists_U` at `0x18004e855`
- `ADVAPI32!RegCloseKey` at `0x18004ea59`
- `ADVAPI32!RegCloseKey` at `0x18004ea59`
- `ADVAPI32!RegSetValueExW` at `0x18004ea1a`
- `ADVAPI32!RegSetValueExW` at `0x18004ea1a`
- `ADVAPI32!RegCreateKeyExW` at `0x18004e9ad`
- `ADVAPI32!RegCreateKeyExW` at `0x18004e9ad`

## string_xrefs

- `0x18004e869`: `Base working directory does not exist [%S]`
- `0x18004e876`: `AcmEngineSetBaseWorkingDirectory`
- `0x18004e9d8`: `AcmEngineSetBaseWorkingDirectory`
- `0x18004e8e9`: `Failed to construct shim directory path [%x]`
- `0x18004e930`: `Failed to construct shim directory path [%x]`
- `0x18004e95e`: `Failed to construct shim directory path [%x]`
- `0x18004e9c6`: `Failed to create key [%S] [%x]`
- `0x18004ea05`: `BaseWorkingDirectory`

## pseudocode

```c
__int64 __fastcall AcmEngineSetBaseWorkingDirectory(wchar_t *lpData, PCWSTR FileName)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rdx
  PCWSTR v7; // rcx
  wchar_t *v8; // r8
  wchar_t *v9; // rcx
  __int64 v10; // rbp
  __int64 v11; // rax
  HRESULT v12; // eax
  HRESULT v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-288h]
  HKEY hKey; // [rsp+50h] [rbp-258h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-248h] BYREF

  memset_0(SubKey, 0, 0x208u);
  hKey = 0;
  if ( !lpData || !FileName || !*FileName )
    return 2147942487LL;
  if ( RtlDoesFileExists_U(FileName) )
  {
    v5 = 2147483646;
    v6 = 260;
    v7 = FileName;
    v8 = lpData;
    do
    {
      if ( !v5 )
        break;
      if ( !*v7 )
        break;
      *v8++ = *v7++;
      --v5;
      --v6;
    }
    while ( v6 );
    v9 = v8 - 1;
    v4 = v6 == 0 ? 0x8007007A : 0;
    if ( v6 )
      v9 = v8;
    *v9 = 0;
    if ( v6 )
    {
      v10 = -1;
      v11 = -1;
      do
        ++v11;
      while ( FileName[v11] );
      if ( FileName[v11 - 1] == 92 || (v12 = StringCchCatW(lpData, 0x104u, L"\\"), v4 = v12, v12 >= 0) )
      {
        v13 = StringCchCatW(lpData, 0x104u, L"MigrationShims");
        v4 = v13;
        if ( v13 >= 0 )
        {
          AcmEngineGetShimKey(SubKey);
          v14 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
          if ( v14 )
          {
            v4 = v14 | 0x10000000;
            AslLogCallPrintf(
              1,
              "AcmEngineSetBaseWorkingDirectory",
              458,
              "Failed to create key [%S] [%x]",
              SubKey,
              v14 | 0x10000000);
          }
          else
          {
            do
              ++v10;
            while ( lpData[v10] );
            v15 = RegSetValueExW(hKey, L"BaseWorkingDirectory", 0, 1u, (const BYTE *)lpData, 2 * v10 + 2);
            v4 = v15;
            if ( v15 )
            {
              if ( v15 > 0 )
                v4 = (unsigned __int16)v15 | 0x80070000;
              dwOptions[0] = v4;
              AslLogCallPrintf(
                1,
                "AcmEngineSetBaseWorkingDirectory",
                470,
                "Failed to set value [%x]",
                *(_QWORD *)dwOptions);
            }
            else
            {
              v4 = 0;
            }
          }
        }
        else
        {
          AslLogCallPrintf(
            1,
            "AcmEngineSetBaseWorkingDirectory",
            437,
            "Failed to construct shim directory path [%x]",
            v13);
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          "AcmEngineSetBaseWorkingDirectory",
          424,
          "Failed to construct shim directory path [%x]",
          v12);
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        "AcmEngineSetBaseWorkingDirectory",
        409,
        "Failed to construct shim directory path [%x]",
        -2147024774);
    }
  }
  else
  {
    v4 = -2147024893;
    AslLogCallPrintf(1, "AcmEngineSetBaseWorkingDirectory", 397, "Base working directory does not exist [%S]", FileName);
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18004e7f0  mov     [rsp+arg_10], rbx
0x18004e7f5  push    rbp
0x18004e7f6  push    rdi
0x18004e7f7  push    r12
0x18004e7f9  push    r14
0x18004e7fb  push    r15
0x18004e7fd  sub     rsp, 280h
0x18004e804  mov     rax, cs:__security_cookie
0x18004e80b  xor     rax, rsp
0x18004e80e  mov     [rsp+2A8h+var_38], rax
0x18004e816  mov     rdi, rdx
0x18004e819  mov     r14, rcx
0x18004e81c  xor     edx, edx; Val
0x18004e81e  lea     rcx, [rsp+2A8h+SubKey]; void *
0x18004e823  mov     r8d, 208h; Size
0x18004e829  call    memset_0
0x18004e82e  xor     r15d, r15d
0x18004e831  mov     [rsp+2A8h+hKey], r15
0x18004e836  test    r14, r14
0x18004e839  jz      loc_18004EA63
0x18004e83f  test    rdi, rdi
0x18004e842  jz      loc_18004EA63
0x18004e848  cmp     [rdi], r15w
0x18004e84c  jz      loc_18004EA63
0x18004e852  mov     rcx, rdi; FileName
0x18004e855  call    cs:__imp_RtlDoesFileExists_U
0x18004e85b  test    al, al
0x18004e85d  jnz     short loc_18004E88C
0x18004e85f  mov     ebx, 80070003h
0x18004e864  mov     qword ptr [rsp+2A8h+dwOptions], rdi
0x18004e869  lea     r9, aBaseWorkingDir; "Base working directory does not exist ["...
0x18004e870  mov     r8d, 18Dh
0x18004e876  lea     rdx, aAcmenginesetba_0; "AcmEngineSetBaseWorkingDirectory"
0x18004e87d  mov     ecx, 1
0x18004e882  call    AslLogCallPrintf
0x18004e887  jmp     loc_18004EA4A
0x18004e88c  mov     r12d, 104h
0x18004e892  mov     eax, 7FFFFFFEh
0x18004e897  mov     edx, r12d
0x18004e89a  mov     rcx, rdi
0x18004e89d  mov     r8, r14
0x18004e8a0  test    rax, rax
0x18004e8a3  jz      short loc_18004E8C4
0x18004e8a5  movzx   r9d, word ptr [rcx]
0x18004e8a9  test    r9w, r9w
0x18004e8ad  jz      short loc_18004E8C4
0x18004e8af  mov     [r8], r9w
0x18004e8b3  add     rcx, 2
0x18004e8b7  add     r8, 2
0x18004e8bb  dec     rax
0x18004e8be  sub     rdx, 1
0x18004e8c2  jnz     short loc_18004E8A0
0x18004e8c4  mov     rax, rdx
0x18004e8c7  lea     rcx, [r8-2]
0x18004e8cb  neg     rax
0x18004e8ce  sbb     ebx, ebx
0x18004e8d0  not     ebx
0x18004e8d2  and     ebx, 8007007Ah
0x18004e8d8  test    rdx, rdx
0x18004e8db  cmovnz  rcx, r8
0x18004e8df  mov     [rcx], r15w
0x18004e8e3  jnz     short loc_18004E8FB
0x18004e8e5  mov     [rsp+2A8h+dwOptions], ebx
0x18004e8e9  lea     r9, aFailedToConstr; "Failed to construct shim directory path"...
0x18004e8f0  mov     r8d, 199h
0x18004e8f6  jmp     loc_18004E876
0x18004e8fb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18004e8ff  mov     rax, rbp
0x18004e902  inc     rax
0x18004e905  cmp     [rdi+rax*2], r15w
0x18004e90a  jnz     short loc_18004E902
0x18004e90c  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18004e912  jz      short loc_18004E942
0x18004e914  lea     r8, asc_18006E074; "\\"
0x18004e91b  mov     rdx, r12; cchDest
0x18004e91e  mov     rcx, r14; pszDest
0x18004e921  call    StringCchCatW
0x18004e926  mov     ebx, eax
0x18004e928  test    eax, eax
0x18004e92a  jns     short loc_18004E942
0x18004e92c  mov     [rsp+2A8h+dwOptions], eax
0x18004e930  lea     r9, aFailedToConstr; "Failed to construct shim directory path"...
0x18004e937  mov     r8d, 1A8h
0x18004e93d  jmp     loc_18004E876
0x18004e942  lea     r8, aMigrationshims_0; "MigrationShims"
0x18004e949  mov     rdx, r12; cchDest
0x18004e94c  mov     rcx, r14; pszDest
0x18004e94f  call    StringCchCatW
0x18004e954  mov     ebx, eax
0x18004e956  test    eax, eax
0x18004e958  jns     short loc_18004E970
0x18004e95a  mov     [rsp+2A8h+dwOptions], eax
0x18004e95e  lea     r9, aFailedToConstr; "Failed to construct shim directory path"...
0x18004e965  mov     r8d, 1B5h
0x18004e96b  jmp     loc_18004E876
0x18004e970  lea     rcx, [rsp+2A8h+SubKey]; pszDest
0x18004e975  call    ?AcmEngineGetShimKey@@YAJPEAG@Z; AcmEngineGetShimKey(ushort *)
0x18004e97a  mov     [rsp+2A8h+lpdwDisposition], r15; lpdwDisposition
0x18004e97f  lea     rax, [rsp+2A8h+hKey]
0x18004e984  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18004e989  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x18004e98e  mov     [rsp+2A8h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18004e993  xor     r9d, r9d; lpClass
0x18004e996  mov     [rsp+2A8h+samDesired], 20006h; samDesired
0x18004e99e  xor     r8d, r8d; Reserved
0x18004e9a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004e9a8  mov     [rsp+2A8h+dwOptions], r15d; dwOptions
0x18004e9ad  call    cs:__imp_RegCreateKeyExW
0x18004e9b3  mov     ebx, eax
0x18004e9b5  test    eax, eax
0x18004e9b7  jz      short loc_18004E9EB
0x18004e9b9  bts     ebx, 1Ch
0x18004e9bd  lea     rax, [rsp+2A8h+SubKey]
0x18004e9c2  mov     [rsp+2A8h+samDesired], ebx
0x18004e9c6  lea     r9, aFailedToCreate_6; "Failed to create key [%S] [%x]"
0x18004e9cd  mov     r8d, 1CAh
0x18004e9d3  mov     qword ptr [rsp+2A8h+dwOptions], rax
0x18004e9d8  lea     rdx, aAcmenginesetba_0; "AcmEngineSetBaseWorkingDirectory"
0x18004e9df  mov     ecx, 1
0x18004e9e4  call    AslLogCallPrintf
0x18004e9e9  jmp     short loc_18004EA4A
0x18004e9eb  inc     rbp
0x18004e9ee  cmp     [r14+rbp*2], r15w
0x18004e9f3  jnz     short loc_18004E9EB
0x18004e9f5  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18004e9fa  lea     eax, ds:2[rbp*2]
0x18004ea01  mov     [rsp+2A8h+samDesired], eax; cbData
0x18004ea05  lea     rdx, aBaseworkingdir; "BaseWorkingDirectory"
0x18004ea0c  mov     r9d, 1; dwType
0x18004ea12  mov     qword ptr [rsp+2A8h+dwOptions], r14; lpData
0x18004ea17  xor     r8d, r8d; Reserved
0x18004ea1a  call    cs:__imp_RegSetValueExW
0x18004ea20  mov     ebx, eax
0x18004ea22  test    eax, eax
0x18004ea24  jz      short loc_18004EA47
0x18004ea26  jle     short loc_18004EA31
0x18004ea28  movzx   ebx, ax
0x18004ea2b  or      ebx, 80070000h
0x18004ea31  mov     [rsp+2A8h+dwOptions], ebx
0x18004ea35  lea     r9, aFailedToSetVal_3; "Failed to set value [%x]"
0x18004ea3c  mov     r8d, 1D6h
0x18004ea42  jmp     loc_18004E876
0x18004ea47  mov     ebx, r15d
0x18004ea4a  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18004ea4f  lea     rax, [rcx-1]
0x18004ea53  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004ea57  ja      short loc_18004EA5F
0x18004ea59  call    cs:__imp_RegCloseKey
0x18004ea5f  mov     eax, ebx
0x18004ea61  jmp     short loc_18004EA68
0x18004ea63  mov     eax, 80070057h
0x18004ea68  mov     rcx, [rsp+2A8h+var_38]
0x18004ea70  xor     rcx, rsp; StackCookie
0x18004ea73  call    __security_check_cookie
0x18004ea78  mov     rbx, [rsp+2A8h+arg_10]
0x18004ea80  add     rsp, 280h
0x18004ea87  pop     r15
0x18004ea89  pop     r14
0x18004ea8b  pop     r12
0x18004ea8d  pop     rdi
0x18004ea8e  pop     rbp
0x18004ea8f  retn
```
