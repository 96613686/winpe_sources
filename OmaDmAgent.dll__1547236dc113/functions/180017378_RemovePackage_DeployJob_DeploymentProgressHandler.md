# RemovePackage(_DeployJob,DeploymentProgressHandler *)

- ea: `0x180017378`
- end: `0x180017688`
- name: `?RemovePackage@@YAJU_DeployJob@@PEAVDeploymentProgressHandler@@@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017b58`

## callees

- `0x18000a290`
- `0x18000a2c0`
- `0x18000a440`
- `0x18000bbf8`
- `0x180014fc4`
- `0x18001507c`
- `0x1800150f8`
- `0x180016734`
- `0x180017378`
- `0x180017918`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800175d7`
- `KERNEL32!WaitForSingleObject` at `0x1800175d7`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180017650`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180017650`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800173b7`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800173b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017644`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017644`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RemovePackage(__int64 *a1, __int64 a2)
{
  int v4; // edi
  int v5; // eax
  _QWORD *v6; // r14
  _QWORD *v7; // rax
  int PackageManager; // eax
  __int64 v9; // rcx
  __int64 v10; // r9
  int v11; // eax
  __int64 v12; // rcx
  int v13; // r8d
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  struct Windows::Management::Deployment::IPackageManager *v19; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v20[2]; // [rsp+48h] [rbp-18h] BYREF

  v20[1] = a1;
  if ( a2 )
  {
    v5 = RoInitialize(1);
    v4 = v5;
    if ( v5 >= 0 )
    {
      string = 0;
      v6 = a1 + 4;
      if ( (unsigned __int64)a1[7] < 8 )
        v7 = a1 + 4;
      else
        v7 = (_QWORD *)*v6;
      v20[0] = v7;
      Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, v20);
      v19 = 0;
      v17 = 0;
      PackageManager = GetPackageManager(&v19);
      v4 = PackageManager;
      if ( PackageManager >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *, HSTRING, __int64 *))(*(_QWORD *)v19 + 64LL))(
               v19,
               string,
               &v17);
        if ( v4 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            if ( (unsigned __int64)a1[7] >= 8 )
              v6 = (_QWORD *)*v6;
            if ( (unsigned __int64)a1[3] < 8 )
              LODWORD(v10) = (_DWORD)a1;
            else
              v10 = *a1;
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              76,
              (unsigned int)&WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
              v10,
              (__int64)v6);
          }
          _DeployJob::operator=(a2 + 80, a1);
          v11 = AddDeploymentCallbacks(v17, a2, a2 + 8);
          v4 = v11;
          if ( v11 >= 0 )
          {
            if ( WaitForSingleObject(*(HANDLE *)(a2 + 72), *((_DWORD *)a1 + 30)) == 258
              && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[14] & 2) != 0 )
            {
              v14 = a1 + 8;
              if ( (unsigned __int64)a1[11] >= 8 )
                v14 = (_QWORD *)*v14;
              WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, v13, *((_DWORD *)a1 + 30), (__int64)v14);
            }
            v15 = v17;
            if ( v17 )
            {
              v17 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                77,
                &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
                (unsigned int)v11);
            v12 = v17;
            if ( v17 )
            {
              v17 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_17887b334fcf349edf3df6ab34803119_Traceguids);
          v9 = v17;
          if ( v17 )
          {
            v17 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
          (unsigned int)PackageManager);
      }
      WindowsDeleteString(string);
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
        (unsigned int)v5);
    }
  }
  else
  {
    v4 = -2147024809;
  }
  RoUninitialize();
  _DeployJob::~_DeployJob((_DeployJob *)a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017378  mov     [rsp-28h+arg_10], rbx
0x18001737d  push    rbp
0x18001737e  push    rsi
0x18001737f  push    rdi
0x180017380  push    r14
0x180017382  push    r15
0x180017384  mov     rbp, rsp
0x180017387  sub     rsp, 60h
0x18001738b  mov     rax, cs:__security_cookie
0x180017392  xor     rax, rsp
0x180017395  mov     [rbp+var_8], rax
0x180017399  mov     r15, rdx
0x18001739c  mov     rsi, rcx
0x18001739f  mov     [rbp+var_10], rcx
0x1800173a3  test    rdx, rdx
0x1800173a6  jnz     short loc_1800173B2
0x1800173a8  mov     edi, 80070057h
0x1800173ad  jmp     loc_180017650
0x1800173b2  mov     ecx, 1
0x1800173b7  call    cs:__imp_RoInitialize
0x1800173be  nop     dword ptr [rax+rax+00h]
0x1800173c3  mov     edi, eax
0x1800173c5  test    eax, eax
0x1800173c7  jns     short loc_180017407
0x1800173c9  lea     rbx, WPP_GLOBAL_Control
0x1800173d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173d7  cmp     rcx, rbx
0x1800173da  jz      loc_180017650
0x1800173e0  test    byte ptr [rcx+1Ch], 4
0x1800173e4  jz      loc_180017650
0x1800173ea  mov     edx, 49h ; 'I'
0x1800173ef  mov     r9d, eax
0x1800173f2  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x1800173f9  mov     rcx, [rcx+10h]
0x1800173fd  call    WPP_SF_d
0x180017402  jmp     loc_180017650
0x180017407  mov     [rbp+string], 0
0x18001740f  lea     r14, [rsi+20h]
0x180017413  cmp     qword ptr [r14+18h], 8
0x180017418  jb      short loc_18001741F
0x18001741a  mov     rax, [r14]
0x18001741d  jmp     short loc_180017422
0x18001741f  mov     rax, r14
0x180017422  mov     [rbp+var_18], rax
0x180017426  lea     rdx, [rbp+var_18]
0x18001742a  lea     rcx, [rbp+string]
0x18001742e  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180017433  mov     [rbp+var_20], 0
0x18001743b  mov     [rbp+var_30], 0
0x180017443  lea     rcx, [rbp+var_20]; struct Windows::Management::Deployment::IPackageManager **
0x180017447  call    ?GetPackageManager@@YAJPEAPEAUIPackageManager@Deployment@Management@Windows@@@Z; GetPackageManager(Windows::Management::Deployment::IPackageManager * *)
0x18001744c  mov     edi, eax
0x18001744e  test    eax, eax
0x180017450  jns     short loc_1800174A7
0x180017452  lea     rbx, WPP_GLOBAL_Control
0x180017459  mov     rcx, cs:WPP_GLOBAL_Control
0x180017460  cmp     rcx, rbx
0x180017463  jz      short loc_180017484
0x180017465  test    byte ptr [rcx+1Ch], 4
0x180017469  jz      short loc_180017484
0x18001746b  mov     edx, 4Ah ; 'J'
0x180017470  mov     r9d, eax
0x180017473  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x18001747a  mov     rcx, [rcx+10h]
0x18001747e  call    WPP_SF_d
0x180017483  nop
0x180017484  mov     rcx, [rbp+var_30]
0x180017488  test    rcx, rcx
0x18001748b  jz      short loc_1800174A2
0x18001748d  mov     [rbp+var_30], 0
0x180017495  mov     rax, [rcx]
0x180017498  mov     rax, [rax+10h]
0x18001749c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174a1  nop
0x1800174a2  jmp     loc_180017640
0x1800174a7  mov     rcx, [rbp+var_20]
0x1800174ab  mov     rax, [rcx]
0x1800174ae  lea     r8, [rbp+var_30]
0x1800174b2  mov     rdx, [rbp+string]
0x1800174b6  mov     rax, [rax+40h]
0x1800174ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174bf  mov     edi, eax
0x1800174c1  test    eax, eax
0x1800174c3  jns     short loc_180017517
0x1800174c5  lea     rbx, WPP_GLOBAL_Control
0x1800174cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174d3  cmp     rcx, rbx
0x1800174d6  jz      short loc_1800174F4
0x1800174d8  test    byte ptr [rcx+1Ch], 4
0x1800174dc  jz      short loc_1800174F4
0x1800174de  mov     edx, 4Bh ; 'K'
0x1800174e3  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x1800174ea  mov     rcx, [rcx+10h]
0x1800174ee  call    WPP_SF_
0x1800174f3  nop
0x1800174f4  mov     rcx, [rbp+var_30]
0x1800174f8  test    rcx, rcx
0x1800174fb  jz      short loc_180017512
0x1800174fd  mov     [rbp+var_30], 0
0x180017505  mov     rax, [rcx]
0x180017508  mov     rax, [rax+10h]
0x18001750c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017511  nop
0x180017512  jmp     loc_180017640
0x180017517  lea     rbx, WPP_GLOBAL_Control
0x18001751e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017525  cmp     rcx, rbx
0x180017528  jz      short loc_180017563
0x18001752a  test    byte ptr [rcx+1Ch], 1
0x18001752e  jz      short loc_180017563
0x180017530  cmp     qword ptr [r14+18h], 8
0x180017535  jb      short loc_18001753A
0x180017537  mov     r14, [r14]
0x18001753a  cmp     qword ptr [rsi+18h], 8
0x18001753f  jb      short loc_180017546
0x180017541  mov     r9, [rsi]
0x180017544  jmp     short loc_180017549
0x180017546  mov     r9, rsi
0x180017549  mov     edx, 4Ch ; 'L'
0x18001754e  mov     [rsp+60h+var_40], r14
0x180017553  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x18001755a  mov     rcx, [rcx+10h]
0x18001755e  call    WPP_SF_SS
0x180017563  lea     rcx, [r15+50h]
0x180017567  mov     rdx, rsi
0x18001756a  call    ??4_DeployJob@@QEAAAEAU0@AEBU0@@Z; _DeployJob::operator=(_DeployJob const &)
0x18001756f  lea     r8, [r15+8]
0x180017573  mov     rdx, r15
0x180017576  mov     rcx, [rbp+var_30]
0x18001757a  call    ?AddDeploymentCallbacks@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@@Z; AddDeploymentCallbacks(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *)
0x18001757f  mov     edi, eax
0x180017581  test    eax, eax
0x180017583  jns     short loc_1800175D0
0x180017585  mov     rcx, cs:WPP_GLOBAL_Control
0x18001758c  cmp     rcx, rbx
0x18001758f  jz      short loc_1800175B0
0x180017591  test    byte ptr [rcx+1Ch], 4
0x180017595  jz      short loc_1800175B0
0x180017597  mov     edx, 4Dh ; 'M'
0x18001759c  mov     r9d, eax
0x18001759f  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x1800175a6  mov     rcx, [rcx+10h]
0x1800175aa  call    WPP_SF_d
0x1800175af  nop
0x1800175b0  mov     rcx, [rbp+var_30]
0x1800175b4  test    rcx, rcx
0x1800175b7  jz      short loc_1800175CE
0x1800175b9  mov     [rbp+var_30], 0
0x1800175c1  mov     rax, [rcx]
0x1800175c4  mov     rax, [rax+10h]
0x1800175c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175cd  nop
0x1800175ce  jmp     short loc_180017640
0x1800175d0  mov     edx, [rsi+78h]; dwMilliseconds
0x1800175d3  mov     rcx, [r15+48h]; hHandle
0x1800175d7  call    cs:__imp_WaitForSingleObject
0x1800175de  nop     dword ptr [rax+rax+00h]
0x1800175e3  cmp     eax, 102h
0x1800175e8  jnz     short loc_180017622
0x1800175ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175f1  cmp     rcx, rbx
0x1800175f4  jz      short loc_180017622
0x1800175f6  test    byte ptr [rcx+1Ch], 2
0x1800175fa  jz      short loc_180017622
0x1800175fc  lea     rax, [rsi+40h]
0x180017600  cmp     qword ptr [rax+18h], 8
0x180017605  jb      short loc_18001760A
0x180017607  mov     rax, [rax]
0x18001760a  mov     edx, 4Eh ; 'N'
0x18001760f  mov     [rsp+60h+var_40], rax
0x180017614  mov     r9d, [rsi+78h]
0x180017618  mov     rcx, [rcx+10h]
0x18001761c  call    WPP_SF_DS
0x180017621  nop
0x180017622  mov     rcx, [rbp+var_30]
0x180017626  test    rcx, rcx
0x180017629  jz      short loc_180017640
0x18001762b  mov     [rbp+var_30], 0
0x180017633  mov     rax, [rcx]
0x180017636  mov     rax, [rax+10h]
0x18001763a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001763f  nop
0x180017640  mov     rcx, [rbp+string]; string
0x180017644  call    cs:__imp_WindowsDeleteString
0x18001764b  nop     dword ptr [rax+rax+00h]
0x180017650  call    cs:__imp_RoUninitialize
0x180017657  nop     dword ptr [rax+rax+00h]
0x18001765c  nop
0x18001765d  mov     rcx, rsi; this
0x180017660  call    ??1_DeployJob@@QEAA@XZ; _DeployJob::~_DeployJob(void)
0x180017665  mov     eax, edi
0x180017667  mov     rcx, [rbp+var_8]
0x18001766b  xor     rcx, rsp; StackCookie
0x18001766e  call    __security_check_cookie
0x180017673  mov     rbx, [rsp+60h+arg_10]
0x18001767b  add     rsp, 60h
0x18001767f  pop     r15
0x180017681  pop     r14
0x180017683  pop     rdi
0x180017684  pop     rsi
0x180017685  pop     rbp
0x180017686  retn
```
