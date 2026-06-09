# CProcess::RuntimeClassInitialize(void *,ulong,ulong,ushort const *,ushort const *,unsigned __int64,ushort const *,int,ushort const *,int,int,int,int,int,int,int,int,bool,int,int)

- ea: `0x180006990`
- end: `0x180006dfc`
- name: `?RuntimeClassInitialize@CProcess@@QEAAJPEAXKKPEBG1_K1H1HHHHHHHH_NHH@Z`
- size: `1132`
- prototype: `__int64 __usercall@<rax>(CProcess *__hidden this@<rcx>, HANDLE hSourceHandle@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, const unsigned __int16 *, const unsigned __int16 *, HANDLE TargetHandle, const unsigned __int16 *, int, const unsigned __int16 *, int, int, int, int, int, int, int, int, bool, int, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180003c70`

## callees

- `0x180006990`
- `0x180006e6c`
- `0x18000a384`
- `0x18000c8b8`
- `0x18000f040`
- `0x180019ff0`
- `0x18001a3fc`
- `0x18001d0b0`
- `0x18001d8a0`
- `0x180020a60`
- `0x180023040`
- `0x180026b90`
- `0x180027f10`
- `0x18002acfc`
- `0x18002cb40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006a6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006a78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006c5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006c6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006a6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006a78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006c5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006c6f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180006aa2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180006c98`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180006aa2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180006c98`
- `ntdll!NtQueryInformationProcess` at `0x180006cf6`
- `ntdll!NtQueryInformationProcess` at `0x180006cf6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006d45`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006d45`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProcess::RuntimeClassInitialize(
        CProcess *this,
        HANDLE hSourceHandle,
        int a3,
        int a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        HANDLE TargetHandle,
        const unsigned __int16 *a8,
        DWORD a9,
        const unsigned __int16 *a10,
        int a11,
        int a12,
        int a13,
        int a14,
        int a15,
        int a16,
        int a17,
        int a18,
        DWORD a19,
        int a20,
        int a21)
{
  HANDLE *v23; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v25; // rax
  const char *v26; // r9
  __int64 result; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // eax
  unsigned int v31; // ebx
  const char *v32; // r9
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // eax
  unsigned int v36; // ebx
  const unsigned __int16 *v37; // rdi
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // eax
  unsigned int v41; // ebx
  const unsigned __int16 *v42; // rdi
  __int64 v43; // rdx
  __int64 v44; // rcx
  int v45; // eax
  unsigned int v46; // ebx
  int v47; // eax
  unsigned int v48; // ebx
  int v49; // r14d
  HANDLE v50; // rbx
  void *v51; // rdi
  HANDLE v52; // rax
  DWORD v53; // ebx
  HANDLE v54; // rax
  const struct _tlgProvider_t *v55; // rax
  __int64 v56; // r8
  __int64 v57; // r9
  CProcess *v58; // rcx
  int dwDesiredAccess; // [rsp+20h] [rbp-78h]
  _OWORD ProcessInformation[2]; // [rsp+40h] [rbp-58h] BYREF
  DWORD dwProcessId[4]; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  char v63; // [rsp+A0h] [rbp+8h] BYREF

  *((_DWORD *)this + 40) = a3;
  *((_DWORD *)this + 41) = a4;
  *((_DWORD *)this + 48) = a9;
  *((_DWORD *)this + 105) = a11;
  *((_DWORD *)this + 106) = a12;
  *((_DWORD *)this + 107) = a13;
  *((_DWORD *)this + 108) = a14;
  *((_DWORD *)this + 110) = a16;
  *((_DWORD *)this + 111) = a17;
  *((_DWORD *)this + 116) = a18;
  *((_DWORD *)this + 109) = a15;
  *((_QWORD *)this + 26) = TargetHandle;
  *((_BYTE *)this + 786) = a19;
  *((_DWORD *)this + 117) = a20;
  *((_DWORD *)this + 118) = a21;
  if ( hSourceHandle )
  {
    v23 = (HANDLE *)((char *)this + 152);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 152,
      0);
    CurrentProcess = GetCurrentProcess();
    v25 = GetCurrentProcess();
    if ( !DuplicateHandle(v25, hSourceHandle, CurrentProcess, v23, 0x101000u, 0, 0) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xA0F,
               (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
               v26);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (void **)this + 21,
    0);
  try
  {
    v30 = _AllocString<CTCoAllocPolicy>(v29, v28, a5, (char *)this + 168);
    v31 = v30;
    if ( v30 >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        (void **)this + 23,
        0);
      v35 = _AllocString<CTCoAllocPolicy>(v34, v33, a8, (char *)this + 184);
      v36 = v35;
      if ( v35 >= 0 )
      {
        v37 = a6;
        if ( a6
          && (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                (void **)this + 22,
                0),
              v40 = _AllocString<CTCoAllocPolicy>(v39, v38, v37, (char *)this + 176),
              v41 = v40,
              v40 < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA1E,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
            (const char *)(unsigned int)v40,
            dwDesiredAccess);
          result = v41;
        }
        else
        {
          v42 = a10;
          if ( a10
            && (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  (void **)this + 25,
                  0),
                v45 = _AllocString<CTCoAllocPolicy>(v44, v43, v42, (char *)this + 200),
                v46 = v45,
                v45 < 0) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA22,
              (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
              (const char *)(unsigned int)v45,
              dwDesiredAccess);
            result = v46;
          }
          else if ( hSourceHandle && (v47 = CProcess::SetupProcessTerminationWatcher(this), v48 = v47, v47 < 0) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA2B,
              (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
              (const char *)(unsigned int)v47,
              dwDesiredAccess);
            result = v48;
          }
          else
          {
            a19 = *((_DWORD *)this + 40);
            v49 = 0;
            TargetHandle = 0;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &TargetHandle,
              0);
            v50 = GetCurrentProcess();
            v51 = (void *)*((_QWORD *)this + 19);
            v52 = GetCurrentProcess();
            if ( DuplicateHandle(v52, v51, v50, &TargetHandle, 0x1000u, 0, 0) )
            {
              while ( 1 )
              {
                std::vector<unsigned long>::_Emplace_one_at_back<unsigned long const &>((char *)this + 128, &a19);
                if ( !TargetHandle )
                  break;
                memset(ProcessInformation, 0, sizeof(ProcessInformation));
                *(_OWORD *)dwProcessId = 0;
                if ( NtQueryInformationProcess(TargetHandle, ProcessBasicInformation, ProcessInformation, 0x30u, 0) < 0 )
                  break;
                v53 = dwProcessId[2];
                a19 = dwProcessId[2];
                if ( *(_QWORD *)std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned long>>>,unsigned long>(
                                  &v63,
                                  *((_QWORD *)this + 16),
                                  *((_QWORD *)this + 17),
                                  &a19) != *((_QWORD *)this + 17) )
                {
                  v55 = AudioSrvPolicyManagerTelemetryProvider::Provider();
                  if ( *(_DWORD *)v55 > 4u && (unsigned __int8)tlgKeywordOn(v55, 0x10000, v55) )
                  {
                    a19 = *((_DWORD *)this + 40);
                    a9 = v53;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                      v56,
                      (unsigned __int8 *)byte_18005739D,
                      v56,
                      v57,
                      (__int64)&a9,
                      (__int64)&a19);
                  }
                  break;
                }
                v54 = OpenProcess(0x1000u, 0, v53);
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                  &TargetHandle,
                  v54);
                if ( v53 )
                {
                  if ( (unsigned int)++v49 < 0xA )
                    continue;
                }
                break;
              }
            }
            CProcess::ResetDataFlowAccessCheckResults(this);
            CProcess::ClearSmtcSubscriptions(v58);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
            result = 0;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA17,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
          (const char *)(unsigned int)v35,
          dwDesiredAccess);
        result = v36;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA15,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
        (const char *)(unsigned int)v30,
        dwDesiredAccess);
      result = v31;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA5B,
                           (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
                           v32);
  }
  return result;
}

```

## disassembly

```asm
0x180006990  push    rbx
0x180006992  push    rsi
0x180006993  push    rdi
0x180006994  push    r14
0x180006996  sub     rsp, 78h
0x18000699a  mov     r14, rdx
0x18000699d  mov     rsi, rcx
0x1800069a0  mov     [rcx+0A0h], r8d
0x1800069a7  mov     [rcx+0A4h], r9d
0x1800069ae  mov     eax, [rsp+98h+arg_40]
0x1800069b5  mov     [rcx+0C0h], eax
0x1800069bb  mov     eax, [rsp+98h+arg_50]
0x1800069c2  mov     [rcx+1A4h], eax
0x1800069c8  mov     eax, [rsp+98h+arg_58]
0x1800069cf  mov     [rcx+1A8h], eax
0x1800069d5  mov     eax, [rsp+98h+arg_60]
0x1800069dc  mov     [rcx+1ACh], eax
0x1800069e2  mov     eax, [rsp+98h+arg_68]
0x1800069e9  mov     [rcx+1B0h], eax
0x1800069ef  mov     eax, [rsp+98h+arg_78]
0x1800069f6  mov     [rcx+1B8h], eax
0x1800069fc  mov     eax, [rsp+98h+arg_80]
0x180006a03  mov     [rcx+1BCh], eax
0x180006a09  mov     eax, [rsp+98h+arg_88]
0x180006a10  mov     [rcx+1D0h], eax
0x180006a16  mov     eax, [rsp+98h+arg_70]
0x180006a1d  mov     [rcx+1B4h], eax
0x180006a23  mov     rax, [rsp+98h+TargetHandle]
0x180006a2b  mov     [rcx+0D0h], rax
0x180006a32  mov     al, byte ptr [rsp+98h+arg_90]
0x180006a39  mov     [rcx+312h], al
0x180006a3f  mov     eax, [rsp+98h+arg_98]
0x180006a46  mov     [rcx+1D4h], eax
0x180006a4c  mov     eax, [rsp+98h+arg_A0]
0x180006a53  mov     [rcx+1D8h], eax
0x180006a59  test    rdx, rdx
0x180006a5c  jz      short loc_180006ACA
0x180006a5e  lea     rdi, [rcx+98h]
0x180006a65  xor     edx, edx
0x180006a67  mov     rcx, rdi
0x180006a6a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180006a6f  call    cs:__imp_GetCurrentProcess
0x180006a75  mov     rbx, rax
0x180006a78  call    cs:__imp_GetCurrentProcess
0x180006a7e  mov     [rsp+98h+dwOptions], 0; dwOptions
0x180006a86  mov     [rsp+98h+bInheritHandle], 0; bInheritHandle
0x180006a8e  mov     [rsp+98h+dwDesiredAccess], 101000h; dwDesiredAccess
0x180006a96  mov     r9, rdi; lpTargetHandle
0x180006a99  mov     r8, rbx; hTargetProcessHandle
0x180006a9c  mov     rdx, r14; hSourceHandle
0x180006a9f  mov     rcx, rax; hSourceProcessHandle
0x180006aa2  call    cs:__imp_DuplicateHandle
0x180006aa8  test    eax, eax
0x180006aaa  jnz     short loc_180006ACA
0x180006aac  mov     rcx, [rsp+98h]; this
0x180006ab4  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x180006abb  mov     edx, 0A0Fh; void *
0x180006ac0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006ac5  jmp     loc_180006DF1
0x180006aca  lea     rbx, [rsi+0A8h]
0x180006ad1  xor     edx, edx
0x180006ad3  mov     rcx, rbx
0x180006ad6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006adb  mov     r9, rbx
0x180006ade  mov     r8, [rsp+98h+arg_20]
0x180006ae6  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180006aeb  mov     ebx, eax
0x180006aed  test    eax, eax
0x180006aef  jns     short loc_180006B14
0x180006af1  mov     rcx, [rsp+98h]; this
0x180006af9  mov     r9d, eax; char *
0x180006afc  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x180006b03  mov     edx, 0A15h; void *
0x180006b08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b0d  mov     eax, ebx
0x180006b0f  jmp     loc_180006DF1
0x180006b14  lea     rbx, [rsi+0B8h]
0x180006b1b  xor     edx, edx
0x180006b1d  mov     rcx, rbx
0x180006b20  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006b25  mov     r9, rbx
0x180006b28  mov     r8, [rsp+98h+arg_38]
0x180006b30  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180006b35  mov     ebx, eax
0x180006b37  test    eax, eax
0x180006b39  jns     short loc_180006B5E
0x180006b3b  mov     rcx, [rsp+98h]; this
0x180006b43  mov     r9d, eax; char *
0x180006b46  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x180006b4d  mov     edx, 0A17h; void *
0x180006b52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b57  mov     eax, ebx
0x180006b59  jmp     loc_180006DF1
0x180006b5e  mov     rdi, [rsp+98h+arg_28]
0x180006b66  test    rdi, rdi
0x180006b69  jz      short loc_180006BB0
0x180006b6b  lea     rbx, [rsi+0B0h]
0x180006b72  xor     edx, edx
0x180006b74  mov     rcx, rbx
0x180006b77  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006b7c  mov     r9, rbx
0x180006b7f  mov     r8, rdi
0x180006b82  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180006b87  mov     ebx, eax
0x180006b89  test    eax, eax
0x180006b8b  jns     short loc_180006BB0
0x180006b8d  mov     rcx, [rsp+98h]; this
0x180006b95  mov     r9d, eax; char *
0x180006b98  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x180006b9f  mov     edx, 0A1Eh; void *
0x180006ba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ba9  mov     eax, ebx
0x180006bab  jmp     loc_180006DF1
0x180006bb0  mov     rdi, [rsp+98h+arg_48]
0x180006bb8  test    rdi, rdi
0x180006bbb  jz      short loc_180006C02
0x180006bbd  lea     rbx, [rsi+0C8h]
0x180006bc4  xor     edx, edx
0x180006bc6  mov     rcx, rbx
0x180006bc9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006bce  mov     r9, rbx
0x180006bd1  mov     r8, rdi
0x180006bd4  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180006bd9  mov     ebx, eax
0x180006bdb  test    eax, eax
0x180006bdd  jns     short loc_180006C02
0x180006bdf  mov     rcx, [rsp+98h]; this
0x180006be7  mov     r9d, eax; char *
0x180006bea  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x180006bf1  mov     edx, 0A22h; void *
0x180006bf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006bfb  mov     eax, ebx
0x180006bfd  jmp     loc_180006DF1
0x180006c02  test    r14, r14
0x180006c05  jz      short loc_180006C38
0x180006c07  mov     rcx, rsi; this
0x180006c0a  call    ?SetupProcessTerminationWatcher@CProcess@@IEAAJXZ; CProcess::SetupProcessTerminationWatcher(void)
0x180006c0f  mov     ebx, eax
0x180006c11  test    eax, eax
0x180006c13  jns     short loc_180006C38
0x180006c15  mov     rcx, [rsp+98h]; this
0x180006c1d  mov     r9d, eax; char *
0x180006c20  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x180006c27  mov     edx, 0A2Bh; void *
0x180006c2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c31  mov     eax, ebx
0x180006c33  jmp     loc_180006DF1
0x180006c38  mov     eax, [rsi+0A0h]
0x180006c3e  mov     [rsp+98h+arg_90], eax
0x180006c45  xor     r14d, r14d
0x180006c48  mov     [rsp+98h+TargetHandle], r14
0x180006c50  xor     edx, edx
0x180006c52  lea     rcx, [rsp+98h+TargetHandle]
0x180006c5a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180006c5f  call    cs:__imp_GetCurrentProcess
0x180006c65  mov     rbx, rax
0x180006c68  mov     rdi, [rsi+98h]
0x180006c6f  call    cs:__imp_GetCurrentProcess
0x180006c75  mov     [rsp+98h+dwOptions], r14d; dwOptions
0x180006c7a  mov     [rsp+98h+bInheritHandle], r14d; bInheritHandle
0x180006c7f  mov     [rsp+98h+dwDesiredAccess], 1000h; dwDesiredAccess
0x180006c87  lea     r9, [rsp+98h+TargetHandle]; lpTargetHandle
0x180006c8f  mov     r8, rbx; hTargetProcessHandle
0x180006c92  mov     rdx, rdi; hSourceHandle
0x180006c95  mov     rcx, rax; hSourceProcessHandle
0x180006c98  call    cs:__imp_DuplicateHandle
0x180006c9e  test    eax, eax
0x180006ca0  jz      loc_180006DCB
0x180006ca6  lea     rdi, [rsi+80h]
0x180006cad  lea     rdx, [rsp+98h+arg_90]
0x180006cb5  mov     rcx, rdi
0x180006cb8  call    ??$_Emplace_one_at_back@AEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAAEAKAEBK@Z; std::vector<ulong>::_Emplace_one_at_back<ulong const &>(ulong const &)
0x180006cbd  mov     rcx, [rsp+98h+TargetHandle]; ProcessHandle
0x180006cc5  test    rcx, rcx
0x180006cc8  jz      loc_180006DCB
0x180006cce  xorps   xmm0, xmm0
0x180006cd1  movups  [rsp+98h+ProcessInformation], xmm0
0x180006cd6  movups  [rsp+98h+var_48], xmm0
0x180006cdb  movups  xmmword ptr [rsp+98h+dwProcessId], xmm0
0x180006ce0  mov     qword ptr [rsp+98h+dwDesiredAccess], 0; ReturnLength
0x180006ce9  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180006cef  lea     r8, [rsp+98h+ProcessInformation]; ProcessInformation
0x180006cf4  xor     edx, edx; ProcessInformationClass
0x180006cf6  call    cs:__imp_NtQueryInformationProcess
0x180006cfc  test    eax, eax
0x180006cfe  js      loc_180006DCB
0x180006d04  mov     rbx, qword ptr [rsp+98h+dwProcessId+8]
0x180006d09  mov     [rsp+98h+arg_90], ebx
0x180006d10  lea     r9, [rsp+98h+arg_90]
0x180006d18  mov     r8, [rsi+88h]
0x180006d1f  mov     rdx, [rdi]
0x180006d22  lea     rcx, [rsp+98h+arg_0]
0x180006d2a  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@std@@K@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@0@V10@V10@AEBK@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ulong>>>,ulong>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ulong>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ulong>>>,ulong const &)
0x180006d2f  mov     rcx, [rsi+88h]
0x180006d36  cmp     [rax], rcx
0x180006d39  jnz     short loc_180006D6E
0x180006d3b  mov     r8d, ebx; dwProcessId
0x180006d3e  xor     edx, edx; bInheritHandle
0x180006d40  mov     ecx, 1000h; dwDesiredAccess
0x180006d45  call    cs:__imp_OpenProcess
0x180006d4b  mov     rdx, rax
0x180006d4e  lea     rcx, [rsp+98h+TargetHandle]
0x180006d56  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180006d5b  test    ebx, ebx
0x180006d5d  jz      short loc_180006DCB
0x180006d5f  inc     r14d
0x180006d62  cmp     r14d, 0Ah
0x180006d66  jb      loc_180006CA6
0x180006d6c  jmp     short loc_180006DCB
0x180006d6e  call    ?Provider@AudioSrvPolicyManagerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioSrvPolicyManagerTelemetryProvider::Provider(void)
0x180006d73  mov     r8, rax
0x180006d76  mov     ecx, [rax]
0x180006d78  cmp     ecx, 4
0x180006d7b  jbe     short loc_180006DCB
0x180006d7d  mov     edx, 10000h
0x180006d82  mov     rcx, rax
0x180006d85  call    _tlgKeywordOn
0x180006d8a  test    al, al
0x180006d8c  jz      short loc_180006DCB
0x180006d8e  mov     ecx, [rsi+0A0h]
0x180006d94  mov     [rsp+98h+arg_90], ecx
0x180006d9b  mov     [rsp+98h+arg_40], ebx
0x180006da2  lea     rax, [rsp+98h+arg_90]
0x180006daa  mov     qword ptr [rsp+98h+bInheritHandle], rax
0x180006daf  lea     rax, [rsp+98h+arg_40]
0x180006db7  mov     qword ptr [rsp+98h+dwDesiredAccess], rax
0x180006dbc  lea     rdx, byte_18005739D
0x180006dc3  mov     rcx, r8
0x180006dc6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180006dcb  mov     rcx, rsi; this
0x180006dce  call    ?ResetDataFlowAccessCheckResults@CProcess@@QEAAXXZ; CProcess::ResetDataFlowAccessCheckResults(void)
0x180006dd3  call    ?ClearSmtcSubscriptions@CProcess@@QEAAXXZ; CProcess::ClearSmtcSubscriptions(void)
0x180006dd8  nop
0x180006dd9  lea     rcx, [rsp+98h+TargetHandle]
0x180006de1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180006de6  xor     eax, eax
0x180006de8  jmp     short loc_180006DF1
0x180006dea  mov     eax, [rsp+98h+arg_90]
0x180006df1  add     rsp, 78h
0x180006df5  pop     r14
0x180006df7  pop     rdi
0x180006df8  pop     rsi
0x180006df9  pop     rbx
0x180006dfa  retn
```
