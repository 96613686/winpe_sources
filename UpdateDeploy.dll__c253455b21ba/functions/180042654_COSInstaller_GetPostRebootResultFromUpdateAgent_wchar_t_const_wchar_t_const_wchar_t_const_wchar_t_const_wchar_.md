# COSInstaller::GetPostRebootResultFromUpdateAgent(wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,bool *,tagPostRebootResultData *)

- ea: `0x180042654`
- end: `0x180042a1b`
- name: `?GetPostRebootResultFromUpdateAgent@COSInstaller@@AEAAJQEA_W0000000PEA_NPEAUtagPostRebootResultData@@@Z`
- size: `967`
- prototype: `__int64 __fastcall(COSInstaller *__hidden this, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, bool *, struct tagPostRebootResultData *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003f760`

## callees

- `0x180003180`
- `0x18000dce4`
- `0x1800110fc`
- `0x180042654`
- `0x180042e50`
- `0x1800430ec`
- `0x180043a60`
- `0x180044b90`
- `0x18004c04c`
- `0x1800523d0`
- `0x180052774`
- `0x180061960`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800427d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800429c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800427d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800429c5`

## string_xrefs

- `0x1800426d6`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180042740`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18004299b`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180042907`: `Update is not committed yet`
- `0x1800428d8`: `Update status code is 0x%08lX`
- `0x180042941`: `Failed to install the update`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall COSInstaller::GetPostRebootResultFromUpdateAgent(
        COSInstaller *this,
        wchar_t *const a2,
        wchar_t *const a3,
        wchar_t *const a4,
        wchar_t *const a5,
        wchar_t *const a6,
        wchar_t *const a7,
        wchar_t *const a8,
        wchar_t *const lpWideCharStr,
        bool *a10,
        struct tagPostRebootResultData *a11)
{
  __int64 v12; // rdx
  OSDeploymentHelper::CDeploymentSessionWrapper *v14; // rbx
  int v15; // eax
  int v16; // esi
  void *v17; // rdi
  wchar_t *v18; // rax
  unsigned int v19; // r8d
  unsigned int v20; // r9d
  int v21; // eax
  int v22; // ecx
  BOOL v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+20h] [rbp-E0h]
  __int64 v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+38h] [rbp-C8h]
  unsigned int v30; // [rsp+50h] [rbp-B0h] BYREF
  void *lpMem; // [rsp+58h] [rbp-A8h] BYREF
  OSDeploymentHelper::CDeploymentSessionWrapper *v32; // [rsp+60h] [rbp-A0h] BYREF
  char *v33; // [rsp+68h] [rbp-98h] BYREF
  struct tagDSFile **v34; // [rsp+70h] [rbp-90h] BYREF
  bool *v35; // [rsp+78h] [rbp-88h]
  _QWORD v36[2]; // [rsp+80h] [rbp-80h] BYREF
  char v37; // [rsp+90h] [rbp-70h]
  GUID v38; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v39; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *v40; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v41; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v42; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v43[14]; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+140h] [rbp+40h] BYREF
  __int64 v45; // [rsp+148h] [rbp+48h] BYREF
  wchar_t v46[8]; // [rsp+150h] [rbp+50h]
  __int64 v47; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v39 = a2;
  v42 = a3;
  v41 = a5;
  v40 = a6;
  v35 = a10;
  if ( !a10 )
  {
    v12 = 2297;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)0x80004003LL,
      v26);
    return 2147500035LL;
  }
  if ( !a11 )
  {
    v12 = 2298;
    goto LABEL_3;
  }
  v14 = 0;
  v32 = 0;
  memset(v43, 0, 0x68u);
  lpMem = 0;
  hObject = 0;
  v15 = ConvertWideToAnsi_Alloc(lpWideCharStr, (char **)&lpMem);
  v16 = v15;
  v17 = lpMem;
  if ( v15 >= 0 )
  {
    v43[0] = a7;
    v43[1] = v39;
    v43[2] = a8;
    v43[4] = lpMem;
    LODWORD(v43[8]) = 2;
    if ( a4 )
    {
      v18 = (wchar_t *)v43[6];
      if ( *a4 )
        v18 = a4;
      v43[6] = v18;
    }
    v45 = 0;
    *(GUID *)v46 = GUID_NULL;
    v47 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl) )
    {
      v21 = OSDeploymentHelper::SandboxAccessMutexGuard::Acquire((wchar_t *)&v45, v39, v19);
    }
    else
    {
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      v21 = OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(
              v39,
              (const wchar_t *)&hObject,
              (void **)0x493E0,
              v20);
    }
    v22 = v21;
    if ( v21 < 0 )
    {
      v23 = v21 == -2147024638;
      *((_DWORD *)a11 + 2) = v23;
      *((_DWORD *)a11 + 9) = v23;
      v24 = -2145116138;
      if ( v22 == -2147024638 )
        v24 = -2145116140;
      *(_DWORD *)a11 = v24;
      v16 = 0;
      goto LABEL_32;
    }
    v36[0] = &hObject;
    v36[1] = &v39;
    v37 = 1;
    v33 = (char *)v43;
    v38 = Buf1;
    v34 = 0;
    v30 = 0;
    v16 = Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,OSDeploymentHelper::CDeploymentSessionWrapper,wchar_t * const &,wchar_t * const &,wchar_t * const &,int,std::nullptr_t,_GUID,unsigned long const &,tagOptionalSessionInfo5 *>(
            &v32,
            &v42,
            &v41,
            &v40,
            &v30,
            &v34,
            (__int64)&v38,
            v29,
            &v33);
    v14 = v32;
    if ( v16 >= 0 )
    {
      *v35 = 1;
      v16 = (*(__int64 (__fastcall **)(__int64, struct tagPostRebootResultData *))(*((_QWORD *)v14 + 2) + 80LL))(
              (__int64)v14 + 16,
              a11);
      if ( v16 >= 0 )
      {
        LODWORD(v28) = *(_DWORD *)a11;
        WUTrace(0, 0, 4096, 4, 0, L"Update status code is 0x%08lX", v28);
        if ( *(_DWORD *)a11 == -805306323 )
        {
          WUTrace(0, 0, 4096, 4, 0, L"Update is not committed yet");
          *((_DWORD *)a11 + 2) = 1;
          *((_DWORD *)a11 + 9) = 1;
          *(_DWORD *)a11 = -2145116140;
        }
        else if ( *(int *)a11 < 0 )
        {
          WUTrace(0, 0, 4096, 4, 0, L"Failed to install the update");
        }
        v16 = 0;
        goto LABEL_31;
      }
      WUTrace(0, 0, 4096, 4, 0, L"GetPostRebootResult call failed. Status code is 0x%08lX");
      v25 = 2401;
    }
    else
    {
      v25 = 2366;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)v16,
      v27);
LABEL_31:
    wil::details::lambda_call__lambda_aaac948832a0183d23684ee84e848ef9___::_lambda_call__lambda_aaac948832a0183d23684ee84e848ef9___(v36);
LABEL_32:
    OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v45);
    goto LABEL_33;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x902,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)(unsigned int)v15,
    v26);
LABEL_33:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v17 )
    SusFree(v17);
  if ( v14 )
    (*(void (__fastcall **)(OSDeploymentHelper::CDeploymentSessionWrapper *))(*(_QWORD *)v14 + 16LL))(v14);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180042654  mov     [rsp-8+arg_0], rbx
0x180042659  push    rbp
0x18004265a  push    rsi
0x18004265b  push    rdi
0x18004265c  push    r12
0x18004265e  push    r13
0x180042660  push    r14
0x180042662  push    r15
0x180042664  lea     rbp, [rsp-70h]
0x180042669  sub     rsp, 170h
0x180042670  mov     rax, cs:__security_cookie
0x180042677  xor     rax, rsp
0x18004267a  mov     [rbp+0A0h+var_38], rax
0x18004267e  mov     r15, r9
0x180042681  mov     r14, [rbp+0A0h+arg_50]
0x180042688  mov     [rbp+0A0h+var_F8], rdx
0x18004268c  mov     [rbp+0A0h+var_E0], r8
0x180042690  mov     rax, [rbp+0A0h+arg_20]
0x180042697  mov     [rbp+0A0h+var_E8], rax
0x18004269b  mov     rax, [rbp+0A0h+arg_28]
0x1800426a2  mov     [rbp+0A0h+var_F0], rax
0x1800426a6  mov     r12, [rbp+0A0h+arg_30]
0x1800426ad  mov     r13, [rbp+0A0h+arg_38]
0x1800426b4  mov     rdi, [rbp+0A0h+lpWideCharStr]
0x1800426bb  mov     rax, [rbp+0A0h+arg_48]
0x1800426c2  mov     [rsp+1A0h+var_128], rax
0x1800426c7  test    rax, rax
0x1800426ca  jnz     short loc_1800426F3
0x1800426cc  mov     edx, 8F9h; void *
0x1800426d1  mov     ebx, 80004003h
0x1800426d6  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800426dd  mov     r9d, ebx; char *
0x1800426e0  mov     rcx, [rbp+0A8h]; this
0x1800426e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800426ec  mov     eax, ebx
0x1800426ee  jmp     loc_1800429F4
0x1800426f3  test    r14, r14
0x1800426f6  jnz     short loc_1800426FF
0x1800426f8  mov     edx, 8FAh
0x1800426fd  jmp     short loc_1800426D1
0x1800426ff  xor     ebx, ebx
0x180042701  mov     [rsp+1A0h+var_140], rbx
0x180042706  xor     edx, edx; Val
0x180042708  lea     r8d, [rbx+68h]; Size
0x18004270c  lea     rcx, [rbp+0A0h+var_D0]; void *
0x180042710  call    memset
0x180042715  mov     [rsp+1A0h+lpMem], rbx
0x18004271a  mov     [rbp+0A0h+hObject], rbx
0x18004271e  lea     rdx, [rsp+1A0h+lpMem]; char **
0x180042723  mov     rcx, rdi; lpWideCharStr
0x180042726  call    ?ConvertWideToAnsi_Alloc@@YAJPEB_WPEAPEAD@Z; ConvertWideToAnsi_Alloc(wchar_t const *,char * *)
0x18004272b  mov     esi, eax
0x18004272d  mov     rdi, [rsp+1A0h+lpMem]
0x180042732  test    eax, eax
0x180042734  jns     short loc_180042759
0x180042736  mov     rcx, [rbp+0A8h]; this
0x18004273d  mov     r9d, eax; char *
0x180042740  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180042747  mov     edx, 902h; void *
0x18004274c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042751  xor     r13d, r13d
0x180042754  jmp     loc_1800429BC
0x180042759  mov     [rbp+0A0h+var_D0], r12
0x18004275d  mov     rax, [rbp+0A0h+var_F8]
0x180042761  mov     [rbp+0A0h+var_C8], rax
0x180042765  mov     [rbp+0A0h+var_C0], r13
0x180042769  mov     [rbp+0A0h+var_B0], rdi
0x18004276d  mov     [rbp+0A0h+var_90], 2
0x180042774  xor     r13d, r13d
0x180042777  test    r15, r15
0x18004277a  jz      short loc_18004278C
0x18004277c  mov     rax, [rbp+0A0h+var_A0]
0x180042780  cmp     [r15], r13w
0x180042784  cmovnz  rax, r15
0x180042788  mov     [rbp+0A0h+var_A0], rax
0x18004278c  xorps   xmm0, xmm0
0x18004278f  movups  xmmword ptr [rbp+0A0h+var_58], xmm0
0x180042793  movups  [rbp+0A0h+var_48], xmm0
0x180042797  mov     qword ptr [rbp+0A0h+var_58], r13
0x18004279b  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800427a2  movdqu  xmmword ptr [rbp+0A0h+var_58+8], xmm1
0x1800427a7  mov     qword ptr [rbp+0A0h+var_48+8], r13
0x1800427ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl(void)'::`2'::impl
0x1800427b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(void)
0x1800427b7  test    al, al
0x1800427b9  jz      short loc_1800427CA
0x1800427bb  mov     rdx, [rbp+0A0h+var_F8]; wchar_t *
0x1800427bf  lea     rcx, [rbp+0A0h+var_58]; this
0x1800427c3  call    ?Acquire@SandboxAccessMutexGuard@OSDeploymentHelper@@QEAAJPEB_WK@Z; OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(wchar_t const *,ulong)
0x1800427c8  jmp     short loc_1800427F0
0x1800427ca  mov     rcx, [rbp+0A0h+hObject]; hObject
0x1800427ce  test    rcx, rcx
0x1800427d1  jz      short loc_1800427DD
0x1800427d3  call    cs:__imp_CloseHandle
0x1800427d9  mov     [rbp+0A0h+hObject], r13
0x1800427dd  mov     r8d, 493E0h; void **
0x1800427e3  lea     rdx, [rbp+0A0h+hObject]; wchar_t *
0x1800427e7  mov     rcx, [rbp+0A0h+var_F8]; this
0x1800427eb  call    ?CreateAndAcquireSandboxAccessMutex@OSDeploymentHelper@@YAJPEB_WPEAPEAXK@Z; OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(wchar_t const *,void * *,ulong)
0x1800427f0  mov     ecx, eax
0x1800427f2  test    eax, eax
0x1800427f4  jns     short loc_180042823
0x1800427f6  mov     eax, r13d
0x1800427f9  mov     r8d, 80070102h
0x1800427ff  cmp     ecx, r8d
0x180042802  setz    al
0x180042805  mov     [r14+8], eax
0x180042809  mov     [r14+24h], eax
0x18004280d  mov     eax, 80242016h
0x180042812  lea     edx, [rax-2]
0x180042815  cmovz   eax, edx
0x180042818  mov     [r14], eax
0x18004281b  mov     esi, r13d
0x18004281e  jmp     loc_1800429B2
0x180042823  lea     rax, [rbp+0A0h+hObject]
0x180042827  mov     [rbp+0A0h+var_120], rax
0x18004282b  lea     rax, [rbp+0A0h+var_F8]
0x18004282f  mov     [rbp+0A0h+var_118], rax
0x180042833  mov     [rbp+0A0h+var_110], 1
0x180042837  lea     rax, [rbp+0A0h+var_D0]
0x18004283b  mov     [rsp+1A0h+var_138], rax
0x180042840  movups  xmm0, xmmword ptr cs:Buf1.Data1
0x180042847  movdqu  [rbp+0A0h+var_108], xmm0
0x18004284c  mov     [rsp+1A0h+var_130], r13
0x180042851  mov     [rsp+1A0h+var_150], r13d
0x180042856  lea     rax, [rsp+1A0h+var_138]
0x18004285b  mov     [rsp+1A0h+var_160], rax
0x180042860  lea     rax, [rbp+0A0h+var_108]
0x180042864  mov     [rsp+1A0h+var_170], rax
0x180042869  lea     rax, [rsp+1A0h+var_130]
0x18004286e  mov     [rsp+1A0h+var_178], rax
0x180042873  lea     rax, [rsp+1A0h+var_150]
0x180042878  mov     qword ptr [rsp+1A0h+var_180], rax
0x18004287d  lea     r9, [rbp+0A0h+var_F0]
0x180042881  lea     r8, [rbp+0A0h+var_E8]
0x180042885  lea     rdx, [rbp+0A0h+var_E0]
0x180042889  lea     rcx, [rsp+1A0h+var_140]
0x18004288e  call    ??$MakeAndInitialize@VCDeploymentSessionWrapper@OSDeploymentHelper@@V12@AEBQEA_WAEBQEA_WAEBQEA_WH$$TU_GUID@@AEBKPEAUtagOptionalSessionInfo5@@@Details@WRL@Microsoft@@YAJPEAPEAVCDeploymentSessionWrapper@OSDeploymentHelper@@AEBQEA_W11$$QEAH$$QEA$$T$$QEAU_GUID@@AEBK$$QEAPEAUtagOptionalSessionInfo5@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,OSDeploymentHelper::CDeploymentSessionWrapper,wchar_t * const &,wchar_t * const &,wchar_t * const &,int,std::nullptr_t,_GUID,ulong const &,tagOptionalSessionInfo5 *>(OSDeploymentHelper::CDeploymentSessionWrapper * *,wchar_t * const &,wchar_t * const &,wchar_t * const &,int &&,$$T$$QEAU_GUID &&,ulong const &,tagOptionalSessionInfo5 * &&)
0x180042893  mov     esi, eax
0x180042895  mov     rbx, [rsp+1A0h+var_140]
0x18004289a  test    eax, eax
0x18004289c  jns     short loc_1800428A8
0x18004289e  mov     edx, 93Eh
0x1800428a3  jmp     loc_180042991
0x1800428a8  mov     rax, [rsp+1A0h+var_128]
0x1800428ad  mov     byte ptr [rax], 1
0x1800428b0  lea     rcx, [rbx+10h]
0x1800428b4  mov     rax, [rcx]
0x1800428b7  mov     rdx, r14
0x1800428ba  mov     rax, [rax+50h]
0x1800428be  call    _guard_dispatch_icall
0x1800428c3  mov     esi, eax
0x1800428c5  xor     edx, edx
0x1800428c7  xor     ecx, ecx
0x1800428c9  test    eax, eax
0x1800428cb  js      loc_180042966
0x1800428d1  mov     eax, [r14]
0x1800428d4  mov     dword ptr [rsp+1A0h+var_170], eax
0x1800428d8  lea     rax, aUpdateStatusCo; "Update status code is 0x%08lX"
0x1800428df  mov     [rsp+1A0h+var_178], rax
0x1800428e4  mov     qword ptr [rsp+1A0h+var_180], r13
0x1800428e9  lea     r15d, [rdx+4]
0x1800428ed  mov     r9d, r15d
0x1800428f0  mov     r12d, 1000h
0x1800428f6  mov     r8d, r12d
0x1800428f9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800428fe  cmp     dword ptr [r14], 0D000002Dh
0x180042905  jnz     short loc_18004293C
0x180042907  lea     rax, aUpdateIsNotCom; "Update is not committed yet"
0x18004290e  mov     [rsp+1A0h+var_178], rax
0x180042913  mov     qword ptr [rsp+1A0h+var_180], r13
0x180042918  mov     r9d, r15d
0x18004291b  mov     r8d, r12d
0x18004291e  xor     edx, edx
0x180042920  xor     ecx, ecx
0x180042922  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180042927  lea     eax, [r15-3]
0x18004292b  mov     [r14+8], eax
0x18004292f  mov     [r14+24h], eax
0x180042933  mov     dword ptr [r14], 80242014h
0x18004293a  jmp     short loc_180042961
0x18004293c  cmp     [r14], r13d
0x18004293f  jge     short loc_180042961
0x180042941  lea     rax, aFailedToInstal; "Failed to install the update"
0x180042948  mov     [rsp+1A0h+var_178], rax
0x18004294d  mov     qword ptr [rsp+1A0h+var_180], r13
0x180042952  mov     r9d, r15d
0x180042955  mov     r8d, r12d
0x180042958  xor     edx, edx
0x18004295a  xor     ecx, ecx
0x18004295c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180042961  mov     esi, r13d
0x180042964  jmp     short loc_1800429A8
0x180042966  mov     dword ptr [rsp+1A0h+var_170], eax
0x18004296a  lea     rax, aGetpostrebootr_0; "GetPostRebootResult call failed. Status"...
0x180042971  mov     [rsp+1A0h+var_178], rax
0x180042976  mov     qword ptr [rsp+1A0h+var_180], r13; int
0x18004297b  mov     r9d, 4
0x180042981  mov     r8d, 1000h
0x180042987  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004298c  mov     edx, 961h; void *
0x180042991  mov     rcx, [rbp+0A8h]; this
0x180042998  mov     r9d, esi; char *
0x18004299b  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800429a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800429a7  nop
0x1800429a8  lea     rcx, [rbp+0A0h+var_120]
0x1800429ac  call    wil__details__lambda_call__lambda_aaac948832a0183d23684ee84e848ef9______lambda_call__lambda_aaac948832a0183d23684ee84e848ef9___
0x1800429b1  nop
0x1800429b2  lea     rcx, [rbp+0A0h+var_58]; this
0x1800429b6  call    ??1SandboxAccessMutexGuard@OSDeploymentHelper@@QEAA@XZ; OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard(void)
0x1800429bb  nop
0x1800429bc  mov     rcx, [rbp+0A0h+hObject]; hObject
0x1800429c0  test    rcx, rcx
0x1800429c3  jz      short loc_1800429CF
0x1800429c5  call    cs:__imp_CloseHandle
0x1800429cb  mov     [rbp+0A0h+hObject], r13
0x1800429cf  test    rdi, rdi
0x1800429d2  jz      short loc_1800429DD
0x1800429d4  mov     rcx, rdi; lpMem
0x1800429d7  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800429dc  nop
0x1800429dd  test    rbx, rbx
0x1800429e0  jz      short loc_1800429F2
0x1800429e2  mov     rcx, [rbx]
0x1800429e5  mov     rax, [rcx+10h]
0x1800429e9  mov     rcx, rbx
0x1800429ec  call    _guard_dispatch_icall
0x1800429f1  nop
0x1800429f2  mov     eax, esi
0x1800429f4  mov     rcx, [rbp+0A0h+var_38]
0x1800429f8  xor     rcx, rsp; StackCookie
0x1800429fb  call    __security_check_cookie
0x180042a00  mov     rbx, [rsp+1A0h+arg_0]
0x180042a08  add     rsp, 170h
0x180042a0f  pop     r15
0x180042a11  pop     r14
0x180042a13  pop     r13
0x180042a15  pop     r12
0x180042a17  pop     rdi
0x180042a18  pop     rsi
0x180042a19  pop     rbp
0x180042a1a  retn
```
