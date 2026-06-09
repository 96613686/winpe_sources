# _SetSecurityOnFileOrFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS)

- ea: `0x180006210`
- end: `0x1800064cb`
- name: `?_SetSecurityOnFileOrFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@@Z`
- size: `699`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004ae8`
- `0x180005270`

## callees

- `0x180006210`
- `0x1800064d4`
- `0x18000d2b8`
- `0x18003aa84`
- `0x180050ba0`
- `0x180051524`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000644c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000644c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000638a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000645e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000638a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000645e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800062d5`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800063cf`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800062d5`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800063cf`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180006337`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180006337`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006375`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800062ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800062ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000640b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000640b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000631c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000631c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800063fe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800063fe`

## pseudocode

```c
__int64 __fastcall _SetSecurityOnFileOrFolder(const WCHAR *a1, const wchar_t *a2, int a3, char a4)
{
  const wchar_t *v5; // rdx
  WCHAR *v6; // r8
  __int64 v7; // rax
  __int64 v8; // r10
  WCHAR *v9; // rcx
  unsigned int Error; // ebx
  __int64 result; // rax
  void *v12; // rax
  void *v13; // rdi
  bool v14; // si
  size_t v15; // rax
  bool v16; // zf
  const wchar_t *v17; // r9
  DWORD nLengthNeeded[2]; // [rsp+30h] [rbp-268h] BYREF
  LPWSTR v19; // [rsp+38h] [rbp-260h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-258h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+60h] [rbp-238h] BYREF

  if ( a3 )
  {
    v16 = (a4 & 1) == 0;
    v17 = L"BU";
    if ( v16 )
      v17 = a2;
    Error = StringCchPrintfW(StringSecurityDescriptor, 0x104u, (&off_1800E6010)[3 * a3], v17);
  }
  else
  {
    v5 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
    v6 = StringSecurityDescriptor;
    v7 = 2147483646;
    v8 = 260;
    do
    {
      if ( !v7 )
        break;
      if ( !*v5 )
        break;
      *v6++ = *v5++;
      --v7;
      --v8;
    }
    while ( v8 );
    v9 = v6 - 1;
    Error = -2147024774;
    if ( v8 )
    {
      v9 = v6;
      Error = 0;
    }
    *v9 = 0;
  }
  if ( (Error & 0x80000000) != 0 )
    return Error;
  nLengthNeeded[0] = 0;
  if ( !GetFileSecurityW(a1, 7u, 0, 0, nLengthNeeded) && (unsigned int)ResultFromKnownLastError() == -2147024774 )
  {
    v12 = CoTaskMemAlloc(nLengthNeeded[0]);
    v13 = v12;
    if ( v12 )
    {
      v14 = 0;
      v15 = CTCoAllocPolicy::_CoTaskMemSize(v12);
      memset_0(v13, 0, v15);
      if ( GetFileSecurityW(a1, 7u, v13, nLengthNeeded[0], nLengthNeeded) )
      {
        v19 = 0;
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v13, 1u, 7u, &v19, 0) )
        {
          v14 = CompareStringOrdinal(v19, -1, StringSecurityDescriptor, -1, 1) == 2;
          LocalFree(v19);
        }
      }
      CoTaskMemFree(v13);
      if ( v14 )
        return Error;
    }
  }
  *(_QWORD *)nLengthNeeded = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         StringSecurityDescriptor,
         1u,
         (PSECURITY_DESCRIPTOR *)nLengthNeeded,
         0)
    || (result = ResultFromKnownLastError(), (int)result >= 0) )
  {
    if ( SetFileSecurityW(a1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
      goto LABEL_18;
    Error = ResultFromKnownLastError();
    if ( Error != -2147024894 )
    {
      if ( Error == -2147024891 )
        Error = 0;
      goto LABEL_19;
    }
    SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    if ( CreateDirectoryW(a1, &SecurityAttributes) )
LABEL_18:
      Error = 0;
    else
      Error = ResultFromKnownLastError();
LABEL_19:
    LocalFree(*(HLOCAL *)nLengthNeeded);
    return Error;
  }
  return result;
}

```

## disassembly

```asm
0x180006210  push    rbx
0x180006212  push    rbp
0x180006213  sub     rsp, 288h
0x18000621a  mov     rax, cs:__security_cookie
0x180006221  xor     rax, rsp
0x180006224  mov     [rsp+298h+var_28], rax
0x18000622c  mov     rbp, rcx
0x18000622f  test    r8d, r8d
0x180006232  jnz     loc_180006466
0x180006238  mov     rdx, cs:off_1800E6010; "O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-"...
0x18000623f  lea     r8, [rsp+298h+StringSecurityDescriptor]
0x180006244  mov     eax, 7FFFFFFEh
0x180006249  mov     r10d, 104h
0x18000624f  nop
0x180006250  test    rax, rax
0x180006253  jz      short loc_180006272
0x180006255  movzx   ecx, word ptr [rdx]
0x180006258  test    cx, cx
0x18000625b  jz      short loc_180006272
0x18000625d  mov     [r8], cx
0x180006261  add     rdx, 2
0x180006265  add     r8, 2
0x180006269  dec     rax
0x18000626c  sub     r10, 1
0x180006270  jnz     short loc_180006250
0x180006272  test    r10, r10
0x180006275  lea     rcx, [r8-2]
0x180006279  mov     ebx, 8007007Ah
0x18000627e  cmovnz  rcx, r8
0x180006282  xor     eax, eax
0x180006284  test    r10, r10
0x180006287  cmovnz  ebx, eax
0x18000628a  mov     [rcx], ax
0x18000628d  test    ebx, ebx
0x18000628f  jns     short loc_1800062AD
0x180006291  mov     eax, ebx
0x180006293  mov     rcx, [rsp+298h+var_28]
0x18000629b  xor     rcx, rsp; StackCookie
0x18000629e  call    __security_check_cookie
0x1800062a3  add     rsp, 288h
0x1800062aa  pop     rbp
0x1800062ab  pop     rbx
0x1800062ac  retn
0x1800062ad  lea     rax, [rsp+298h+nLengthNeeded]
0x1800062b2  mov     [rsp+298h+var_18], rdi
0x1800062ba  xor     r9d, r9d; nLength
0x1800062bd  mov     [rsp+298h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800062c2  xor     r8d, r8d; pSecurityDescriptor
0x1800062c5  mov     [rsp+298h+nLengthNeeded], 0
0x1800062cd  mov     edx, 7; RequestedInformation
0x1800062d2  mov     rcx, rbp; lpFileName
0x1800062d5  call    cs:__imp_GetFileSecurityW
0x1800062db  test    eax, eax
0x1800062dd  jnz     short loc_180006301
0x1800062df  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800062e4  cmp     eax, 8007007Ah
0x1800062e9  jnz     short loc_180006301
0x1800062eb  mov     ecx, [rsp+298h+nLengthNeeded]; cb
0x1800062ef  call    cs:__imp_CoTaskMemAlloc
0x1800062f5  mov     rdi, rax
0x1800062f8  test    rax, rax
0x1800062fb  jnz     loc_180006395
0x180006301  xor     r9d, r9d; SecurityDescriptorSize
0x180006304  mov     qword ptr [rsp+298h+nLengthNeeded], 0
0x18000630d  lea     r8, [rsp+298h+nLengthNeeded]; SecurityDescriptor
0x180006312  mov     edx, 1; StringSDRevision
0x180006317  lea     rcx, [rsp+298h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000631c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180006322  test    eax, eax
0x180006324  jz      loc_18000649D
0x18000632a  mov     r8, qword ptr [rsp+298h+nLengthNeeded]; pSecurityDescriptor
0x18000632f  mov     edx, 7; SecurityInformation
0x180006334  mov     rcx, rbp; lpFileName
0x180006337  call    cs:__imp_SetFileSecurityW
0x18000633d  test    eax, eax
0x18000633f  jnz     short loc_180006383
0x180006341  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006346  mov     ebx, eax
0x180006348  cmp     eax, 80070002h
0x18000634d  jnz     loc_1800064BB
0x180006353  mov     rax, qword ptr [rsp+298h+nLengthNeeded]
0x180006358  lea     rdx, [rsp+298h+SecurityAttributes]; lpSecurityAttributes
0x18000635d  mov     [rsp+298h+SecurityAttributes.lpSecurityDescriptor], rax
0x180006362  mov     rcx, rbp; lpPathName
0x180006365  xor     eax, eax
0x180006367  mov     qword ptr [rsp+298h+SecurityAttributes.nLength], 18h
0x180006370  mov     qword ptr [rsp+298h+SecurityAttributes.bInheritHandle], rax
0x180006375  call    cs:__imp_CreateDirectoryW
0x18000637b  test    eax, eax
0x18000637d  jz      loc_1800064AF
0x180006383  xor     ebx, ebx
0x180006385  mov     rcx, qword ptr [rsp+298h+nLengthNeeded]; hMem
0x18000638a  call    cs:__imp_LocalFree
0x180006390  jmp     loc_180006422
0x180006395  mov     [rsp+298h+arg_10], rsi
0x18000639d  mov     rcx, rdi; void *
0x1800063a0  xor     sil, sil
0x1800063a3  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x1800063a8  mov     r8, rax; Size
0x1800063ab  xor     edx, edx; Val
0x1800063ad  mov     rcx, rdi; void *
0x1800063b0  call    memset_0
0x1800063b5  mov     r9d, [rsp+298h+nLengthNeeded]; nLength
0x1800063ba  lea     rax, [rsp+298h+nLengthNeeded]
0x1800063bf  mov     r8, rdi; pSecurityDescriptor
0x1800063c2  mov     [rsp+298h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800063c7  mov     edx, 7; RequestedInformation
0x1800063cc  mov     rcx, rbp; lpFileName
0x1800063cf  call    cs:__imp_GetFileSecurityW
0x1800063d5  test    eax, eax
0x1800063d7  jz      short loc_180006408
0x1800063d9  lea     r9, [rsp+298h+var_260]; StringSecurityDescriptor
0x1800063de  mov     [rsp+298h+var_260], 0
0x1800063e7  mov     edx, 1; RequestedStringSDRevision
0x1800063ec  mov     [rsp+298h+lpnLengthNeeded], 0; StringSecurityDescriptorLen
0x1800063f5  mov     r8d, 7; SecurityInformation
0x1800063fb  mov     rcx, rdi; SecurityDescriptor
0x1800063fe  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180006404  test    eax, eax
0x180006406  jnz     short loc_180006431
0x180006408  mov     rcx, rdi; pv
0x18000640b  call    cs:__imp_CoTaskMemFree
0x180006411  test    sil, sil
0x180006414  mov     rsi, [rsp+298h+arg_10]
0x18000641c  jz      loc_180006301
0x180006422  mov     eax, ebx
0x180006424  mov     rdi, [rsp+298h+var_18]
0x18000642c  jmp     loc_180006293
0x180006431  mov     rcx, [rsp+298h+var_260]; lpString1
0x180006436  lea     r8, [rsp+298h+StringSecurityDescriptor]; lpString2
0x18000643b  mov     r9d, 0FFFFFFFFh; cchCount2
0x180006441  mov     dword ptr [rsp+298h+lpnLengthNeeded], 1; bIgnoreCase
0x180006449  mov     edx, r9d; cchCount1
0x18000644c  call    cs:__imp_CompareStringOrdinal
0x180006452  mov     rcx, [rsp+298h+var_260]; hMem
0x180006457  cmp     eax, 2
0x18000645a  setz    sil
0x18000645e  call    cs:__imp_LocalFree
0x180006464  jmp     short loc_180006408
0x180006466  movsxd  rax, r8d
0x180006469  lea     rcx, [rsp+298h+StringSecurityDescriptor]; unsigned __int16 *
0x18000646e  test    r9b, 1
0x180006472  lea     r9, aBu; "BU"
0x180006479  cmovz   r9, rdx
0x18000647d  mov     edx, 104h; unsigned __int64
0x180006482  lea     r8, [rax+rax*2]
0x180006486  lea     rax, off_1800E6010; "O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-"...
0x18000648d  mov     r8, [rax+r8*8]; unsigned __int16 *
0x180006491  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006496  mov     ebx, eax
0x180006498  jmp     loc_18000628D
0x18000649d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800064a2  test    eax, eax
0x1800064a4  js      loc_180006424
0x1800064aa  jmp     loc_18000632A
0x1800064af  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800064b4  mov     ebx, eax
0x1800064b6  jmp     loc_180006385
0x1800064bb  xor     ecx, ecx
0x1800064bd  cmp     ebx, 80070005h
0x1800064c3  cmovz   ebx, ecx
0x1800064c6  jmp     loc_180006385
```
