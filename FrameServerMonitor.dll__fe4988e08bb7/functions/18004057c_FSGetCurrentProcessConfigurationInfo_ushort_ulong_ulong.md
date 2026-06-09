# FSGetCurrentProcessConfigurationInfo(ushort *,ulong,ulong *)

- ea: `0x18004057c`
- end: `0x1800407a7`
- name: `?FSGetCurrentProcessConfigurationInfo@@YAJPEAGKPEAK@Z`
- size: `555`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180036cb8`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180004f34`
- `0x1800060f8`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x18003ff38`
- `0x18004057c`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180040671`
- `ntdll!NtQueryInformationProcess` at `0x1800406f8`
- `ntdll!NtQueryInformationProcess` at `0x180040671`
- `ntdll!NtQueryInformationProcess` at `0x1800406f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800406da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800406da`

## pseudocode

```c
__int64 __fastcall FSGetCurrentProcessConfigurationInfo(unsigned __int16 *a1, unsigned int a2, unsigned int *a3)
{
  unsigned __int64 v4; // rsi
  __int64 v6; // r8
  ULONG v7; // eax
  int v8; // edi
  HANDLE CurrentProcess; // rax
  NTSTATUS v11; // eax
  const struct std::nothrow_t *unique; // rax
  const unsigned __int16 **v13; // r15
  __int64 v14; // rdx
  ULONG v15; // ebx
  HANDLE v16; // rax
  NTSTATUS v17; // eax
  unsigned int v18; // eax
  ULONG ProcessInformationLength; // [rsp+30h] [rbp-99h] BYREF
  PVOID ProcessInformation; // [rsp+38h] [rbp-91h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int16 v22[72]; // [rsp+50h] [rbp-79h] BYREF

  v4 = a2;
  ProcessInformationLength = 0;
  memset_0(v22, 0, 0x8Au);
  if ( FSCreatePackageFamilyNameTag(0, v22, v6, &ProcessInformationLength) < 0 )
  {
    v8 = 0;
    ProcessInformation = 0;
    ProcessInformationLength = 0;
    CurrentProcess = GetCurrentProcess();
    v11 = NtQueryInformationProcess(CurrentProcess, ProcessImageFileName, 0, 0, &ProcessInformationLength);
    if ( !ProcessInformationLength )
    {
      v8 = v11 | 0x10000000;
      if ( v11 < 0 )
        goto LABEL_27;
    }
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(v21, ProcessInformationLength);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
      &ProcessInformation,
      unique);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(v21);
    v13 = (const unsigned __int16 **)ProcessInformation;
    if ( ProcessInformation )
    {
      v15 = ProcessInformationLength;
      v16 = GetCurrentProcess();
      v17 = NtQueryInformationProcess(v16, ProcessImageFileName, v13, v15, &ProcessInformationLength);
      if ( v17 && (v8 = v17 | 0x10000000, v17 < 0) )
      {
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 62;
          goto LABEL_26;
        }
      }
      else
      {
        v18 = (*(unsigned __int16 *)v13 >> 1) + 1;
        *a3 = v18;
        if ( !(_DWORD)v4 || !a1 )
          goto LABEL_27;
        if ( (unsigned int)v4 >= v18 )
        {
          v8 = StringCchCopyW(a1, v4, v13[1]);
          if ( v8 >= 0 || !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_27;
          v14 = 63;
          goto LABEL_26;
        }
        v8 = -1072860816;
      }
    }
    else
    {
      v8 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 61;
LABEL_26:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v8);
      }
    }
LABEL_27:
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&ProcessInformation);
    return (unsigned int)v8;
  }
  v7 = ProcessInformationLength;
  *a3 = ProcessInformationLength;
  if ( !(_DWORD)v4 || !a1 )
    return 0;
  if ( (unsigned int)v4 >= v7 )
  {
    v8 = StringCchCopyW(a1, v4, v22);
    if ( v8 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v8);
    }
  }
  else
  {
    return (unsigned int)-1072860816;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004057c  push    rbp
0x18004057e  push    rbx
0x18004057f  push    rsi
0x180040580  push    rdi
0x180040581  push    r12
0x180040583  push    r14
0x180040585  push    r15
0x180040587  lea     rbp, [rsp-27h]
0x18004058c  sub     rsp, 0F0h
0x180040593  mov     rax, cs:__security_cookie
0x18004059a  xor     rax, rsp
0x18004059d  mov     [rbp+57h+var_40], rax
0x1800405a1  mov     r12, r8
0x1800405a4  mov     esi, edx
0x1800405a6  mov     r14, rcx
0x1800405a9  mov     [rsp+120h+ProcessInformationLength], 0
0x1800405b1  xor     edx, edx; Val
0x1800405b3  lea     rcx, [rbp+57h+var_D0]; void *
0x1800405b7  mov     r8d, 8Ah; Size
0x1800405bd  call    memset_0
0x1800405c2  lea     r9, [rsp+120h+ProcessInformationLength]; unsigned int *
0x1800405c7  xor     ecx, ecx; hProcess
0x1800405c9  lea     rdx, [rbp+57h+var_D0]; unsigned __int16 *
0x1800405cd  call    ?FSCreatePackageFamilyNameTag@@YAJPEAXPEAGKPEAK@Z; FSCreatePackageFamilyNameTag(void *,ushort *,ulong,ulong *)
0x1800405d2  test    eax, eax
0x1800405d4  js      short loc_18004064A
0x1800405d6  mov     eax, [rsp+120h+ProcessInformationLength]
0x1800405da  mov     [r12], eax
0x1800405de  test    esi, esi
0x1800405e0  jz      short loc_180040643
0x1800405e2  test    r14, r14
0x1800405e5  jz      short loc_180040643
0x1800405e7  cmp     esi, eax
0x1800405e9  jnb     short loc_1800405F5
0x1800405eb  mov     edi, 0C00D7170h
0x1800405f0  jmp     loc_180040787
0x1800405f5  mov     rdx, rsi; unsigned __int64
0x1800405f8  lea     r8, [rbp+57h+var_D0]; unsigned __int16 *
0x1800405fc  mov     rcx, r14; unsigned __int16 *
0x1800405ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180040604  mov     edi, eax
0x180040606  test    eax, eax
0x180040608  jns     loc_180040787
0x18004060e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040613  cmp     al, 1
0x180040615  jb      loc_180040787
0x18004061b  mov     rcx, cs:WPP_GLOBAL_Control
0x180040622  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180040629  mov     edx, 3Ch ; '<'
0x18004062e  mov     dword ptr [rsp+120h+ReturnLength], edi
0x180040632  xor     r9d, r9d
0x180040635  mov     rcx, [rcx+10h]
0x180040639  call    WPP_SF_qD
0x18004063e  jmp     loc_180040787
0x180040643  xor     eax, eax
0x180040645  jmp     loc_180040789
0x18004064a  xor     edi, edi
0x18004064c  mov     [rsp+120h+ProcessInformation], rdi
0x180040651  mov     [rsp+120h+ProcessInformationLength], edi
0x180040655  call    cs:__imp_GetCurrentProcess
0x18004065b  xor     r9d, r9d; ProcessInformationLength
0x18004065e  lea     edx, [rdi+1Bh]; ProcessInformationClass
0x180040661  mov     rcx, rax; ProcessHandle
0x180040664  xor     r8d, r8d; ProcessInformation
0x180040667  lea     rax, [rsp+120h+ProcessInformationLength]
0x18004066c  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x180040671  call    cs:__imp_NtQueryInformationProcess
0x180040677  mov     ecx, [rsp+120h+ProcessInformationLength]
0x18004067b  test    ecx, ecx
0x18004067d  jnz     short loc_18004068D
0x18004067f  mov     edi, eax
0x180040681  or      edi, 10000000h
0x180040687  jl      loc_18004077D
0x18004068d  mov     rdx, rcx
0x180040690  lea     rcx, [rsp+120h+var_E0]
0x180040695  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18004069a  mov     rdx, rax
0x18004069d  lea     rcx, [rsp+120h+ProcessInformation]
0x1800406a2  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800406a7  lea     rcx, [rsp+120h+var_E0]
0x1800406ac  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x1800406b1  mov     r15, [rsp+120h+ProcessInformation]
0x1800406b6  test    r15, r15
0x1800406b9  jnz     short loc_1800406D6
0x1800406bb  mov     edi, 8007000Eh
0x1800406c0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800406c5  cmp     al, 1
0x1800406c7  jb      loc_18004077D
0x1800406cd  lea     edx, [r15+3Dh]
0x1800406d1  jmp     loc_18004075F
0x1800406d6  mov     ebx, [rsp+120h+ProcessInformationLength]
0x1800406da  call    cs:__imp_GetCurrentProcess
0x1800406e0  lea     rcx, [rsp+120h+ProcessInformationLength]
0x1800406e5  mov     r9d, ebx; ProcessInformationLength
0x1800406e8  mov     [rsp+120h+ReturnLength], rcx; ReturnLength
0x1800406ed  mov     r8, r15; ProcessInformation
0x1800406f0  mov     rcx, rax; ProcessHandle
0x1800406f3  mov     edx, 1Bh; ProcessInformationClass
0x1800406f8  call    cs:__imp_NtQueryInformationProcess
0x1800406fe  test    eax, eax
0x180040700  jz      short loc_18004071C
0x180040702  mov     edi, eax
0x180040704  or      edi, 10000000h
0x18004070a  jge     short loc_18004071C
0x18004070c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040711  cmp     al, 1
0x180040713  jb      short loc_18004077D
0x180040715  mov     edx, 3Eh ; '>'
0x18004071a  jmp     short loc_18004075F
0x18004071c  movzx   eax, word ptr [r15]
0x180040720  shr     eax, 1
0x180040722  inc     eax
0x180040724  mov     [r12], eax
0x180040728  test    esi, esi
0x18004072a  jz      short loc_18004077D
0x18004072c  test    r14, r14
0x18004072f  jz      short loc_18004077D
0x180040731  cmp     esi, eax
0x180040733  jnb     short loc_18004073C
0x180040735  mov     edi, 0C00D7170h
0x18004073a  jmp     short loc_18004077D
0x18004073c  mov     r8, [r15+8]; unsigned __int16 *
0x180040740  mov     rdx, rsi; unsigned __int64
0x180040743  mov     rcx, r14; unsigned __int16 *
0x180040746  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004074b  mov     edi, eax
0x18004074d  test    eax, eax
0x18004074f  jns     short loc_18004077D
0x180040751  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040756  cmp     al, 1
0x180040758  jb      short loc_18004077D
0x18004075a  mov     edx, 3Fh ; '?'
0x18004075f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040766  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18004076d  xor     r9d, r9d
0x180040770  mov     dword ptr [rsp+120h+ReturnLength], edi
0x180040774  mov     rcx, [rcx+10h]
0x180040778  call    WPP_SF_qD
0x18004077d  lea     rcx, [rsp+120h+ProcessInformation]
0x180040782  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180040787  mov     eax, edi
0x180040789  mov     rcx, [rbp+57h+var_40]
0x18004078d  xor     rcx, rsp; StackCookie
0x180040790  call    __security_check_cookie
0x180040795  add     rsp, 0F0h
0x18004079c  pop     r15
0x18004079e  pop     r14
0x1800407a0  pop     r12
0x1800407a2  pop     rdi
0x1800407a3  pop     rsi
0x1800407a4  pop     rbx
0x1800407a5  pop     rbp
0x1800407a6  retn
```
