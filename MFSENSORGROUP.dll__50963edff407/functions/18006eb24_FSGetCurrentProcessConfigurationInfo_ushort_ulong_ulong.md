# FSGetCurrentProcessConfigurationInfo(ushort *,ulong,ulong *)

- ea: `0x18006eb24`
- end: `0x18006ed59`
- name: `?FSGetCurrentProcessConfigurationInfo@@YAJPEAGKPEAK@Z`
- size: `565`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800049b0`

## callees

- `0x180005fa0`
- `0x18000f5a0`
- `0x180012120`
- `0x1800133fc`
- `0x180015e80`
- `0x180028eb4`
- `0x180044f30`
- `0x180045900`
- `0x18006eb24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006ec03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006ec8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006ec03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006ec8c`
- `ntdll!NtQueryInformationProcess` at `0x18006ec1f`
- `ntdll!NtQueryInformationProcess` at `0x18006ecaa`
- `ntdll!NtQueryInformationProcess` at `0x18006ec1f`
- `ntdll!NtQueryInformationProcess` at `0x18006ecaa`

## pseudocode

```c
__int64 __fastcall FSGetCurrentProcessConfigurationInfo(unsigned __int16 *a1, unsigned int a2, unsigned int *a3)
{
  unsigned __int64 v4; // rsi
  ULONG v6; // eax
  unsigned int v7; // edi
  int v8; // eax
  HANDLE CurrentProcess; // rax
  NTSTATUS v11; // eax
  void **unique; // rax
  const unsigned __int16 **v13; // r15
  __int64 v14; // rdx
  ULONG v15; // ebx
  HANDLE v16; // rax
  NTSTATUS v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  ULONG ProcessInformationLength; // [rsp+30h] [rbp-99h] BYREF
  PVOID ProcessInformation; // [rsp+38h] [rbp-91h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int16 v23[72]; // [rsp+50h] [rbp-79h] BYREF

  v4 = a2;
  ProcessInformationLength = 0;
  memset_0(v23, 0, 0x8Au);
  if ( FSCreatePackageFamilyNameTag(0, v23, 0x45u, &ProcessInformationLength) < 0 )
  {
    v7 = 0;
    ProcessInformation = 0;
    ProcessInformationLength = 0;
    CurrentProcess = GetCurrentProcess();
    v11 = NtQueryInformationProcess(CurrentProcess, ProcessImageFileName, 0, 0, &ProcessInformationLength);
    if ( !ProcessInformationLength )
    {
      v7 = v11 | 0x10000000;
      if ( v11 < 0 )
        goto LABEL_27;
    }
    unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(v22, ProcessInformationLength);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(
      &ProcessInformation,
      unique);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(v22);
    v13 = (const unsigned __int16 **)ProcessInformation;
    if ( ProcessInformation )
    {
      v15 = ProcessInformationLength;
      v16 = GetCurrentProcess();
      v17 = NtQueryInformationProcess(v16, ProcessImageFileName, v13, v15, &ProcessInformationLength);
      if ( !v17 || (v7 = v17 | 0x10000000, v17 >= 0) )
      {
        v18 = (*(unsigned __int16 *)v13 >> 1) + 1;
        *a3 = v18;
        if ( (_DWORD)v4 && a1 )
        {
          if ( (unsigned int)v4 >= v18 )
          {
            v19 = StringCchCopyW(a1, v4, v13[1]);
            v7 = v19;
            if ( v19 < 0 && g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                63,
                &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
                0,
                v19);
          }
          else
          {
            v7 = -1072860816;
          }
        }
        goto LABEL_27;
      }
      if ( g_wppLevels )
      {
        v14 = 62;
        goto LABEL_15;
      }
    }
    else
    {
      v7 = -2147024882;
      if ( g_wppLevels )
      {
        v14 = (unsigned int)((_DWORD)ProcessInformation + 61);
LABEL_15:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v7);
      }
    }
LABEL_27:
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&ProcessInformation);
    return v7;
  }
  v6 = ProcessInformationLength;
  *a3 = ProcessInformationLength;
  if ( !(_DWORD)v4 || !a1 )
    return 0;
  if ( (unsigned int)v4 >= v6 )
  {
    v8 = StringCchCopyW(a1, v4, v23);
    v7 = v8;
    if ( v8 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v8);
    }
  }
  else
  {
    return (unsigned int)-1072860816;
  }
  return v7;
}

```

## disassembly

```asm
0x18006eb24  push    rbp
0x18006eb26  push    rbx
0x18006eb27  push    rsi
0x18006eb28  push    rdi
0x18006eb29  push    r12
0x18006eb2b  push    r14
0x18006eb2d  push    r15
0x18006eb2f  lea     rbp, [rsp-27h]
0x18006eb34  sub     rsp, 0F0h
0x18006eb3b  mov     rax, cs:__security_cookie
0x18006eb42  xor     rax, rsp
0x18006eb45  mov     [rbp+57h+var_40], rax
0x18006eb49  mov     r12, r8
0x18006eb4c  mov     esi, edx
0x18006eb4e  mov     r14, rcx
0x18006eb51  mov     [rsp+120h+ProcessInformationLength], 0
0x18006eb59  xor     edx, edx; Val
0x18006eb5b  lea     rcx, [rbp+57h+var_D0]; void *
0x18006eb5f  mov     r8d, 8Ah; Size
0x18006eb65  call    memset_0
0x18006eb6a  lea     r9, [rsp+120h+ProcessInformationLength]; unsigned int *
0x18006eb6f  mov     r8d, 45h ; 'E'; unsigned int
0x18006eb75  lea     rdx, [rbp+57h+var_D0]; unsigned __int16 *
0x18006eb79  xor     ecx, ecx; hProcess
0x18006eb7b  call    ?FSCreatePackageFamilyNameTag@@YAJPEAXPEAGKPEAK@Z; FSCreatePackageFamilyNameTag(void *,ushort *,ulong,ulong *)
0x18006eb80  test    eax, eax
0x18006eb82  js      short loc_18006EBF8
0x18006eb84  mov     eax, [rsp+120h+ProcessInformationLength]
0x18006eb88  mov     [r12], eax
0x18006eb8c  test    esi, esi
0x18006eb8e  jz      short loc_18006EBF1
0x18006eb90  test    r14, r14
0x18006eb93  jz      short loc_18006EBF1
0x18006eb95  cmp     esi, eax
0x18006eb97  jnb     short loc_18006EBA3
0x18006eb99  mov     edi, 0C00D7170h
0x18006eb9e  jmp     loc_18006ED39
0x18006eba3  mov     rdx, rsi; unsigned __int64
0x18006eba6  lea     r8, [rbp+57h+var_D0]; unsigned __int16 *
0x18006ebaa  mov     rcx, r14; unsigned __int16 *
0x18006ebad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006ebb2  mov     edi, eax
0x18006ebb4  test    eax, eax
0x18006ebb6  jns     loc_18006ED39
0x18006ebbc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ebc3  jb      loc_18006ED39
0x18006ebc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ebd0  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18006ebd7  mov     edx, 3Ch ; '<'
0x18006ebdc  mov     dword ptr [rsp+120h+ReturnLength], eax
0x18006ebe0  xor     r9d, r9d
0x18006ebe3  mov     rcx, [rcx+10h]
0x18006ebe7  call    WPP_SF_qD
0x18006ebec  jmp     loc_18006ED39
0x18006ebf1  xor     eax, eax
0x18006ebf3  jmp     loc_18006ED3B
0x18006ebf8  xor     edi, edi
0x18006ebfa  mov     [rsp+120h+ProcessInformation], rdi
0x18006ebff  mov     [rsp+120h+ProcessInformationLength], edi
0x18006ec03  call    cs:__imp_GetCurrentProcess
0x18006ec09  xor     r9d, r9d; ProcessInformationLength
0x18006ec0c  lea     edx, [rdi+1Bh]; ProcessInformationClass
0x18006ec0f  mov     rcx, rax; ProcessHandle
0x18006ec12  xor     r8d, r8d; ProcessInformation
0x18006ec15  lea     rax, [rsp+120h+ProcessInformationLength]
0x18006ec1a  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18006ec1f  call    cs:__imp_NtQueryInformationProcess
0x18006ec25  mov     ecx, [rsp+120h+ProcessInformationLength]
0x18006ec29  test    ecx, ecx
0x18006ec2b  jnz     short loc_18006EC3B
0x18006ec2d  mov     edi, eax
0x18006ec2f  or      edi, 10000000h
0x18006ec35  jl      loc_18006ED2F
0x18006ec3b  mov     rdx, rcx
0x18006ec3e  lea     rcx, [rsp+120h+var_E0]
0x18006ec43  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18006ec48  mov     rdx, rax
0x18006ec4b  lea     rcx, [rsp+120h+ProcessInformation]
0x18006ec50  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18006ec55  lea     rcx, [rsp+120h+var_E0]
0x18006ec5a  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18006ec5f  mov     r15, [rsp+120h+ProcessInformation]
0x18006ec64  test    r15, r15
0x18006ec67  jnz     short loc_18006EC88
0x18006ec69  mov     edi, 8007000Eh
0x18006ec6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ec75  jb      loc_18006ED2F
0x18006ec7b  lea     edx, [r15+3Dh]
0x18006ec7f  mov     dword ptr [rsp+120h+ReturnLength], edi
0x18006ec83  jmp     loc_18006ED15
0x18006ec88  mov     ebx, [rsp+120h+ProcessInformationLength]
0x18006ec8c  call    cs:__imp_GetCurrentProcess
0x18006ec92  lea     rcx, [rsp+120h+ProcessInformationLength]
0x18006ec97  mov     r9d, ebx; ProcessInformationLength
0x18006ec9a  mov     [rsp+120h+ReturnLength], rcx; ReturnLength
0x18006ec9f  mov     r8, r15; ProcessInformation
0x18006eca2  mov     rcx, rax; ProcessHandle
0x18006eca5  mov     edx, 1Bh; ProcessInformationClass
0x18006ecaa  call    cs:__imp_NtQueryInformationProcess
0x18006ecb0  test    eax, eax
0x18006ecb2  jz      short loc_18006ECCE
0x18006ecb4  mov     edi, eax
0x18006ecb6  or      edi, 10000000h
0x18006ecbc  jge     short loc_18006ECCE
0x18006ecbe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ecc5  jb      short loc_18006ED2F
0x18006ecc7  mov     edx, 3Eh ; '>'
0x18006eccc  jmp     short loc_18006EC7F
0x18006ecce  movzx   eax, word ptr [r15]
0x18006ecd2  shr     eax, 1
0x18006ecd4  inc     eax
0x18006ecd6  mov     [r12], eax
0x18006ecda  test    esi, esi
0x18006ecdc  jz      short loc_18006ED2F
0x18006ecde  test    r14, r14
0x18006ece1  jz      short loc_18006ED2F
0x18006ece3  cmp     esi, eax
0x18006ece5  jnb     short loc_18006ECEE
0x18006ece7  mov     edi, 0C00D7170h
0x18006ecec  jmp     short loc_18006ED2F
0x18006ecee  mov     r8, [r15+8]; unsigned __int16 *
0x18006ecf2  mov     rdx, rsi; unsigned __int64
0x18006ecf5  mov     rcx, r14; unsigned __int16 *
0x18006ecf8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006ecfd  mov     edi, eax
0x18006ecff  test    eax, eax
0x18006ed01  jns     short loc_18006ED2F
0x18006ed03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ed0a  jb      short loc_18006ED2F
0x18006ed0c  mov     edx, 3Fh ; '?'
0x18006ed11  mov     dword ptr [rsp+120h+ReturnLength], eax
0x18006ed15  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ed1c  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18006ed23  xor     r9d, r9d
0x18006ed26  mov     rcx, [rcx+10h]
0x18006ed2a  call    WPP_SF_qD
0x18006ed2f  lea     rcx, [rsp+120h+ProcessInformation]
0x18006ed34  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18006ed39  mov     eax, edi
0x18006ed3b  mov     rcx, [rbp+57h+var_40]
0x18006ed3f  xor     rcx, rsp; StackCookie
0x18006ed42  call    __security_check_cookie
0x18006ed47  add     rsp, 0F0h
0x18006ed4e  pop     r15
0x18006ed50  pop     r14
0x18006ed52  pop     r12
0x18006ed54  pop     rdi
0x18006ed55  pop     rsi
0x18006ed56  pop     rbx
0x18006ed57  pop     rbp
0x18006ed58  retn
```
