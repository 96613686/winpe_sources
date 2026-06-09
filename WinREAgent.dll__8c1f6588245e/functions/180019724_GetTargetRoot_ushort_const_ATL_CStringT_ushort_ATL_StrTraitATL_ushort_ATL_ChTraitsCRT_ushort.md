# GetTargetRoot(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180019724`
- end: `0x1800198fb`
- name: `?GetTargetRoot@@YAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800173a0`
- `0x18001b268`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x1800074b8`
- `0x1800089d0`
- `0x18000d92c`
- `0x180011ef4`
- `0x180019724`
- `0x180037344`
- `0x18004d8d0`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800197fd`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800197fd`
- `KERNEL32!GetLastError` at `0x180019807`
- `KERNEL32!GetLastError` at `0x180019849`
- `KERNEL32!GetLastError` at `0x180019807`
- `KERNEL32!GetLastError` at `0x180019849`

## string_xrefs

- `0x18001981b`: `Failed to get system Windows directory`
- `0x1800197b7`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001982f`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetTargetRoot(__int64 a1, _QWORD *a2)
{
  int Drive; // edi
  __int64 v5; // r8
  signed int LastError; // eax
  signed int v7; // eax
  ATL::CStringData *v8; // rcx
  ATL::CStringData *v9; // rsi
  int *v10; // r14
  __int64 v11; // rbx
  unsigned __int16 v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v14);
  if ( a1 )
  {
    v13 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)v15,
      a1);
    Drive = PushButtonReset::Path::GetDrive(v15, &v13);
    ATL::CStringData::Release((ATL::CStringData *)(v15[0] - 24LL));
    if ( Drive < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Drive,
        "GetTargetRoot",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1320,
        L"Failed to get Drive of [%s]",
        a1);
LABEL_11:
      v8 = (ATL::CStringData *)(v14 - 24);
      goto LABEL_19;
    }
    v5 = v13;
  }
  else
  {
    memset_0(Buffer, 0, 0x20Au);
    if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "GetTargetRoot",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1330,
        L"Failed to get system Windows directory");
      v7 = GetLastError();
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      Drive = v7;
      goto LABEL_11;
    }
    Drive = 0;
    v5 = Buffer[0];
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v14,
    L"%c:\\",
    v5);
  v9 = (ATL::CStringData *)(v14 - 24);
  v10 = (int *)(*a2 - 24LL);
  if ( (int *)(v14 - 24) != v10 )
  {
    if ( v10[4] >= 0 && *(_QWORD *)v9 == *(_QWORD *)v10 )
    {
      v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v14 - 24);
      ATL::CStringData::Release((ATL::CStringData *)v10);
      *a2 = v11 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v14, *(unsigned int *)(v14 - 16));
    }
  }
  v8 = v9;
LABEL_19:
  ATL::CStringData::Release(v8);
  return (unsigned int)Drive;
}

```

## disassembly

```asm
0x180019724  mov     [rsp-8+arg_10], rbx
0x180019729  push    rbp
0x18001972a  push    rsi
0x18001972b  push    rdi
0x18001972c  push    r14
0x18001972e  push    r15
0x180019730  lea     rbp, [rsp-180h]
0x180019738  sub     rsp, 280h
0x18001973f  mov     rax, cs:__security_cookie
0x180019746  xor     rax, rsp
0x180019749  mov     [rbp+1A0h+var_30], rax
0x180019750  mov     r15, rdx
0x180019753  mov     rbx, rcx
0x180019756  lea     rcx, [rsp+2A0h+var_258]
0x18001975b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180019760  nop
0x180019761  test    rbx, rbx
0x180019764  jz      short loc_1800197E1
0x180019766  xor     eax, eax
0x180019768  mov     [rsp+2A0h+var_260], ax
0x18001976d  mov     rdx, rbx
0x180019770  lea     rcx, [rsp+2A0h+var_250]
0x180019775  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001977a  nop
0x18001977b  lea     rdx, [rsp+2A0h+var_260]
0x180019780  lea     rcx, [rsp+2A0h+var_250]
0x180019785  call    ?GetDrive@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAG@Z; PushButtonReset::Path::GetDrive(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort *)
0x18001978a  mov     edi, eax
0x18001978c  mov     rcx, [rsp+2A0h+var_250]
0x180019791  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019795  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001979a  test    edi, edi
0x18001979c  jns     short loc_1800197D6
0x18001979e  mov     [rsp+2A0h+var_270], rbx
0x1800197a3  lea     rax, aFailedToGetDri; "Failed to get Drive of [%s]"
0x1800197aa  mov     [rsp+2A0h+var_278], rax
0x1800197af  mov     [rsp+2A0h+var_280], 528h
0x1800197b7  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800197be  lea     r8, aGettargetroot; "GetTargetRoot"
0x1800197c5  mov     edx, edi
0x1800197c7  mov     ecx, 2
0x1800197cc  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800197d1  jmp     loc_18001985A
0x1800197d6  movzx   r8d, [rsp+2A0h+var_260]
0x1800197dc  jmp     loc_18001986D
0x1800197e1  xor     edx, edx; Val
0x1800197e3  mov     r8d, 20Ah; Size
0x1800197e9  lea     rcx, [rsp+2A0h+Buffer]; void *
0x1800197ee  call    memset_0
0x1800197f3  mov     edx, 104h; uSize
0x1800197f8  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x1800197fd  call    cs:__imp_GetSystemWindowsDirectoryW
0x180019803  test    eax, eax
0x180019805  jnz     short loc_180019865
0x180019807  call    cs:__imp_GetLastError
0x18001980d  mov     ebx, 80070000h
0x180019812  test    eax, eax
0x180019814  jle     short loc_18001981B
0x180019816  movzx   eax, ax
0x180019819  or      eax, ebx
0x18001981b  lea     rcx, aFailedToGetSys_0; "Failed to get system Windows directory"
0x180019822  mov     [rsp+2A0h+var_278], rcx
0x180019827  mov     [rsp+2A0h+var_280], 532h
0x18001982f  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019836  lea     r8, aGettargetroot; "GetTargetRoot"
0x18001983d  mov     edx, eax
0x18001983f  mov     ecx, 2
0x180019844  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019849  call    cs:__imp_GetLastError
0x18001984f  test    eax, eax
0x180019851  jle     short loc_180019858
0x180019853  movzx   eax, ax
0x180019856  or      eax, ebx
0x180019858  mov     edi, eax
0x18001985a  mov     rcx, [rsp+2A0h+var_258]
0x18001985f  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180019863  jmp     short loc_1800198CE
0x180019865  xor     edi, edi
0x180019867  movzx   r8d, [rsp+2A0h+Buffer]
0x18001986d  lea     rdx, aC; "%c:\\"
0x180019874  lea     rcx, [rsp+2A0h+var_258]
0x180019879  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001987e  mov     rdx, [rsp+2A0h+var_258]
0x180019883  lea     rsi, [rdx-18h]
0x180019887  mov     r14, [r15]
0x18001988a  add     r14, 0FFFFFFFFFFFFFFE8h
0x18001988e  cmp     rsi, r14
0x180019891  jz      short loc_1800198CB
0x180019893  cmp     dword ptr [r14+10h], 0
0x180019898  jl      short loc_1800198BE
0x18001989a  mov     rax, [r14]
0x18001989d  cmp     [rsi], rax
0x1800198a0  jnz     short loc_1800198BE
0x1800198a2  mov     rcx, rsi
0x1800198a5  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800198aa  mov     rbx, rax
0x1800198ad  mov     rcx, r14; this
0x1800198b0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800198b5  lea     rax, [rbx+18h]
0x1800198b9  mov     [r15], rax
0x1800198bc  jmp     short loc_1800198CB
0x1800198be  mov     r8d, [rdx-10h]
0x1800198c2  mov     rcx, r15
0x1800198c5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800198ca  nop
0x1800198cb  mov     rcx, rsi; this
0x1800198ce  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800198d3  mov     eax, edi
0x1800198d5  mov     rcx, [rbp+1A0h+var_30]
0x1800198dc  xor     rcx, rsp; StackCookie
0x1800198df  call    __security_check_cookie
0x1800198e4  mov     rbx, [rsp+2A0h+arg_10]
0x1800198ec  add     rsp, 280h
0x1800198f3  pop     r15
0x1800198f5  pop     r14
0x1800198f7  pop     rdi
0x1800198f8  pop     rsi
0x1800198f9  pop     rbp
0x1800198fa  retn
```
