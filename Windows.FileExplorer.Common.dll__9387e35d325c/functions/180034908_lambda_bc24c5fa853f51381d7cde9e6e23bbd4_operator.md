# _lambda_bc24c5fa853f51381d7cde9e6e23bbd4_::operator()

- ea: `0x180034908`
- end: `0x180034afb`
- name: `_lambda_bc24c5fa853f51381d7cde9e6e23bbd4_::operator()`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003dd40`

## callees

- `0x1800037dc`
- `0x180005214`
- `0x1800077c8`
- `0x18001d320`
- `0x18001e3b0`
- `0x18003169c`
- `0x180034908`
- `0x180034b04`
- `0x18003d4a4`
- `0x1800434c0`
- `0x180043c98`
- `0x180044040`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034940`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034940`
- `cldapi!CfHydratePlaceholder` at `0x180034a23`
- `cldapi!CfHydratePlaceholder` at `0x180034a23`

## string_xrefs

- `0x180034981`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x1800349c1`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x180034a47`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x180034ab6`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x180034acf`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_bc24c5fa853f51381d7cde9e6e23bbd4_::operator()(CFilePlaceholder **a1)
{
  CFilePlaceholder *v2; // rbx
  HANDLE FileW; // rdi
  const char *v4; // r9
  char *v5; // rcx
  const char *v7; // r9
  unsigned int LastError; // ebx
  CFilePlaceholder *v9; // rax
  int v10; // eax
  unsigned int v11; // ebp
  CFilePlaceholder *v12; // rdi
  unsigned __int16 **v13; // rbx
  int LastSyncStatus; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v17; // [rsp+70h] [rbp+8h] BYREF

  v2 = *a1;
  FileW = CreateFileW(*(LPCWSTR *)a1[1], 0, 7u, 0, 3u, 0x40000000u, 0);
  v5 = (char *)*((_QWORD *)v2 + 102);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v5);
  *((_QWORD *)v2 + 102) = FileW;
  if ( ((*((_QWORD *)*a1 + 102) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2AA,
             (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
             v4);
  CloudFilesTelemetry::CloudDownloadAndGo::ShellInitiatedHydration(a1[2]);
  v17 = 0;
  if ( (unsigned __int8)_try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                          &v17,
                          1) )
  {
    v9 = *a1;
    *(_OWORD *)((char *)v9 + 824) = 0;
    *(_OWORD *)((char *)v9 + 840) = 0;
    *((_QWORD *)*a1 + 106) = v17;
    *(_QWORD *)dwCreationDisposition = (char *)*a1 + 824;
    LastError = CfHydratePlaceholder(*((_QWORD *)*a1 + 102), *(_QWORD *)a1[3], *(_QWORD *)a1[4], 0);
    if ( (int)(LastError + 0x80000000) < 0 || LastError == -2147023899 )
    {
      Microsoft::WRL::ComPtr<IFilePlaceholderCallback>::operator=((char *)*a1 + 792, *(_QWORD *)a1[5]);
      v10 = CFilePlaceholder::ListenForHydrationProgress(*a1);
      v11 = v10;
      LastError = -2147023901;
      if ( v10 != -2147023901 )
      {
        if ( v10 >= 0 )
        {
          LastError = 0;
        }
        else
        {
          v12 = *a1;
          v13 = (unsigned __int16 **)a1[7];
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            v13,
            0);
          LastSyncStatus = CFilePlaceholder::GetLastSyncStatus(v12, (unsigned int *)a1[6], v13);
          if ( LastSyncStatus < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2C1,
              (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
              (const char *)(unsigned int)LastSyncStatus,
              dwCreationDisposition[0]);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C3,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
            (const char *)v11,
            dwCreationDisposition[0]);
          LastError = v11;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B6,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
        (const char *)LastError,
        dwCreationDisposition[0]);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2B0,
                  (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
                  v7);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastError;
}

```

## disassembly

```asm
0x180034908  push    rbx
0x18003490a  push    rbp
0x18003490b  push    rsi
0x18003490c  push    rdi
0x18003490d  sub     rsp, 48h
0x180034911  mov     rsi, rcx
0x180034914  mov     rbx, [rcx]
0x180034917  mov     rcx, [rcx+8]
0x18003491b  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180034924  mov     [rsp+68h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18003492c  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180034934  xor     r9d, r9d; lpSecurityAttributes
0x180034937  xor     edx, edx; dwDesiredAccess
0x180034939  lea     r8d, [r9+7]; dwShareMode
0x18003493d  mov     rcx, [rcx]; lpFileName
0x180034940  call    cs:__imp_CreateFileW
0x180034946  mov     rdi, rax
0x180034949  mov     rcx, [rbx+330h]; hObject
0x180034950  lea     rdx, [rcx-1]
0x180034954  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180034958  ja      short loc_18003495F
0x18003495a  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003495f  mov     [rbx+330h], rdi
0x180034966  mov     rax, [rsi]
0x180034969  mov     rcx, [rax+330h]
0x180034970  inc     rcx
0x180034973  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18003497a  jnz     short loc_180034997
0x18003497c  mov     rcx, [rsp+68h]; this
0x180034981  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x180034988  mov     edx, 2AAh; void *
0x18003498d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034992  jmp     loc_180034AF2
0x180034997  mov     rcx, [rsi+10h]; this
0x18003499b  call    ?ShellInitiatedHydration@CloudDownloadAndGo@CloudFilesTelemetry@@QEAAXXZ; CloudFilesTelemetry::CloudDownloadAndGo::ShellInitiatedHydration(void)
0x1800349a0  mov     [rsp+68h+arg_0], 0
0x1800349a9  mov     edx, 1
0x1800349ae  lea     rcx, [rsp+68h+arg_0]
0x1800349b3  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800349b8  test    al, al
0x1800349ba  jnz     short loc_1800349D9
0x1800349bc  mov     rcx, [rsp+68h]; this
0x1800349c1  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800349c8  mov     edx, 2B0h; void *
0x1800349cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800349d2  mov     ebx, eax
0x1800349d4  jmp     loc_180034AE6
0x1800349d9  mov     rax, [rsi]
0x1800349dc  xorps   xmm0, xmm0
0x1800349df  movups  xmmword ptr [rax+338h], xmm0
0x1800349e6  movups  xmmword ptr [rax+348h], xmm0
0x1800349ed  mov     rcx, [rsi]
0x1800349f0  mov     rax, [rsp+68h+arg_0]
0x1800349f5  mov     [rcx+350h], rax
0x1800349fc  mov     rcx, [rsi]
0x1800349ff  mov     r8, [rsi+20h]
0x180034a03  mov     rdx, [rsi+18h]
0x180034a07  lea     rax, [rcx+338h]
0x180034a0e  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; int
0x180034a13  xor     r9d, r9d
0x180034a16  mov     r8, [r8]
0x180034a19  mov     rdx, [rdx]
0x180034a1c  mov     rcx, [rcx+330h]
0x180034a23  call    cs:__imp_CfHydratePlaceholder
0x180034a29  mov     ebx, eax
0x180034a2b  mov     eax, 80000000h
0x180034a30  lea     ecx, [rbx+rax]
0x180034a33  test    eax, ecx
0x180034a35  jnz     short loc_180034A5D
0x180034a37  cmp     ebx, 800703E5h
0x180034a3d  jz      short loc_180034A5D
0x180034a3f  mov     rcx, [rsp+68h]; this
0x180034a44  mov     r9d, ebx; char *
0x180034a47  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x180034a4e  mov     edx, 2B6h; void *
0x180034a53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034a58  jmp     loc_180034AE6
0x180034a5d  mov     rdx, [rsi+28h]
0x180034a61  mov     rcx, [rsi]
0x180034a64  add     rcx, 318h
0x180034a6b  mov     rdx, [rdx]
0x180034a6e  call    ??4?$ComPtr@UIFilePlaceholderCallback@@@WRL@Microsoft@@QEAAAEAV012@PEAUIFilePlaceholderCallback@@@Z; Microsoft::WRL::ComPtr<IFilePlaceholderCallback>::operator=(IFilePlaceholderCallback *)
0x180034a73  mov     rcx, [rsi]; this
0x180034a76  call    ?ListenForHydrationProgress@CFilePlaceholder@@AEAAJXZ; CFilePlaceholder::ListenForHydrationProgress(void)
0x180034a7b  mov     ebp, eax
0x180034a7d  mov     ebx, 800703E3h
0x180034a82  cmp     eax, ebx
0x180034a84  jz      short loc_180034AE6
0x180034a86  test    eax, eax
0x180034a88  jns     short loc_180034AE4
0x180034a8a  mov     rdi, [rsi]
0x180034a8d  mov     rbx, [rsi+38h]
0x180034a91  xor     edx, edx
0x180034a93  mov     rcx, rbx
0x180034a96  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034a9b  mov     r8, rbx; unsigned __int16 **
0x180034a9e  mov     rdx, [rsi+30h]; unsigned int *
0x180034aa2  mov     rcx, rdi; this
0x180034aa5  call    ?GetLastSyncStatus@CFilePlaceholder@@AEAAJPEAKPEAPEAG@Z; CFilePlaceholder::GetLastSyncStatus(ulong *,ushort * *)
0x180034aaa  mov     rcx, [rsp+68h]; this
0x180034aaf  test    eax, eax
0x180034ab1  jns     short loc_180034AC7
0x180034ab3  mov     r9d, eax; char *
0x180034ab6  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x180034abd  mov     edx, 2C1h; void *
0x180034ac2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034ac7  mov     rcx, [rsp+68h]; this
0x180034acc  mov     r9d, ebp; char *
0x180034acf  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x180034ad6  mov     edx, 2C3h; void *
0x180034adb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034ae0  mov     ebx, ebp
0x180034ae2  jmp     short loc_180034AE6
0x180034ae4  xor     ebx, ebx
0x180034ae6  lea     rcx, [rsp+68h+arg_0]
0x180034aeb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180034af0  mov     eax, ebx
0x180034af2  add     rsp, 48h
0x180034af6  pop     rdi
0x180034af7  pop     rsi
0x180034af8  pop     rbp
0x180034af9  pop     rbx
0x180034afa  retn
```
