# WSManProvHost::HostInitialize(_WSMAN_PROVHOST_INITDETAILS *,IWSManHostEntrySink *,ushort *,ulong,int,int,int)

- ea: `0x1801b3860`
- end: `0x1801b40d7`
- name: `?HostInitialize@WSManProvHost@@UEAAJPEAU_WSMAN_PROVHOST_INITDETAILS@@PEAUIWSManHostEntrySink@@PEAGKHHH@Z`
- size: `2167`
- prototype: `int __fastcall(WSManProvHost *this, struct _WSMAN_PROVHOST_INITDETAILS *, struct IWSManHostEntrySink *, unsigned __int16 *, unsigned int, int, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180013760`
- `0x180026e80`
- `0x18002dd80`
- `0x18003a3a0`
- `0x18005a5b0`
- `0x180071400`
- `0x180077490`
- `0x1800973c0`
- `0x1800ba2bc`
- `0x1800db738`
- `0x180112380`
- `0x1801123a8`
- `0x1801b314c`
- `0x1801b3860`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b391b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b397f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b391b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b397f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3fb3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1801b3c5a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1801b3c5a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1801b38fe`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1801b38fe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1801b3ce6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1801b3ce6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801b3beb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801b3beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b3ea9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b3ea9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b3ec2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b3ec2`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1801b3f26`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1801b3f26`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1801b3e72`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1801b3e72`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801b3fd8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801b3fd8`

## string_xrefs

- `0x1801b3f1f`: `__WINRM_RUNAS_CLIENT_TOKEN__`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall WSManProvHost::HostInitialize(
        WSManProvHost *this,
        struct _WSMAN_PROVHOST_INITDETAILS *a2,
        struct IWSManHostEntrySink *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8)
{
  PVOID *v12; // rcx
  HANDLE v13; // rax
  DWORD LastError; // eax
  int v15; // ebx
  int result; // eax
  unsigned int v17; // eax
  unsigned __int16 *v18; // rax
  unsigned int ErrorCode; // eax
  const struct Catalog::Provider *Provider; // rax
  int v21; // ebx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  HANDLE EventW; // rax
  DWORD v25; // eax
  __int64 v26; // r9
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  HANDLE CurrentThread; // rax
  DWORD v30; // eax
  DWORD v31; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-A1h] BYREF
  void **v33; // [rsp+40h] [rbp-91h] BYREF
  signed __int32 v34[4]; // [rsp+48h] [rbp-89h] BYREF
  char v35; // [rsp+58h] [rbp-79h]
  const wchar_t *v36; // [rsp+60h] [rbp-71h]
  const wchar_t *v37; // [rsp+68h] [rbp-69h]
  const wchar_t *v38; // [rsp+70h] [rbp-61h]
  const wchar_t *v39; // [rsp+78h] [rbp-59h]
  WCHAR Value[4]; // [rsp+80h] [rbp-51h] BYREF
  signed __int32 v41[4]; // [rsp+88h] [rbp-49h] BYREF
  char v42; // [rsp+98h] [rbp-39h]
  const wchar_t *v43; // [rsp+A0h] [rbp-31h]
  const wchar_t *v44; // [rsp+A8h] [rbp-29h]
  const wchar_t *v45; // [rsp+B0h] [rbp-21h]
  const wchar_t *v46; // [rsp+B8h] [rbp-19h]

  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_769441059adc374bf6ea72702644ec2e_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 || !*(_QWORD *)a2 || !a3 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x100) != 0 )
      WPP_SF_(v12[2], 28, WPP_769441059adc374bf6ea72702644ec2e_Traceguids);
    return -2147024809;
  }
  v13 = OpenEventW(0x100000u, 0, (LPCWSTR)a2 + 52);
  AutoHandle::operator=((char *)this + 392, v13);
  if ( !*((_QWORD *)this + 49) )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, LastError);
    if ( v15 > 0 )
      return (unsigned __int16)v15 | 0x80070000;
    return v15;
  }
  if ( !WSManProvHost::EnforceQuota(this, *((_DWORD *)a2 + 2), *((_DWORD *)a2 + 3), (const unsigned __int16 *)a2 + 8) )
  {
    if ( (int)GetLastError() > 0 )
      return (unsigned __int16)GetLastError() | 0x80070000;
    else
      return GetLastError();
  }
  v17 = IPCListener::Initialize((WSManProvHost *)((char *)this + 16), *(const unsigned __int16 **)a2);
  if ( v17 )
  {
    if ( v17 == 14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, 14);
      return -2147024882;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, v17);
      return -2147418113;
    }
  }
  v34[0] = 0;
  v33 = &CErrorContext::`vftable';
  v34[2] = 0;
  v34[3] = -1;
  v36 = &Class;
  v37 = &Class;
  v38 = &Class;
  v39 = &Class;
  v35 = 1;
  _InterlockedIncrement(v34);
  LODWORD(Handles[0]) = 0;
  v18 = CopyString(a4, (const int *)Handles, (struct IRequestContext *)&v33);
  AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=((char *)this + 216, v18);
  if ( !*((_QWORD *)this + 27) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      ErrorCode = CErrorContext::GetErrorCode((CErrorContext *)&v33);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, ErrorCode);
    }
    if ( (int)CErrorContext::GetErrorCode((CErrorContext *)&v33) <= 0 )
      return CErrorContext::GetErrorCode((CErrorContext *)&v33);
    LOWORD(result) = CErrorContext::GetErrorCode((CErrorContext *)&v33);
    return (unsigned __int16)result | 0x80070000;
  }
  Provider = Catalog::GetProvider((Catalog *)(*((_QWORD *)this + 4) + 32LL), a4);
  *((_QWORD *)this + 29) = Provider;
  *((_DWORD *)this + 60) = *((_DWORD *)Provider + 59);
  *((_DWORD *)Provider + 58) = a5;
  if ( !(unsigned int)CWSManCriticalSection::IsValid((WSManProvHost *)((char *)this + 120)) )
  {
    v21 = GetLastError();
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v23 = 33;
LABEL_39:
      WPP_SF_d(v22[2], v23, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, (unsigned int)v21);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  if ( !(unsigned int)CWSManCriticalSection::IsValid((WSManProvHost *)((char *)this + 168)) )
  {
    v21 = GetLastError();
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v23 = 34;
      goto LABEL_39;
    }
LABEL_40:
    if ( v21 > 0 )
      return (unsigned __int16)v21 | 0x80070000;
    return v21;
  }
  *((_QWORD *)this + 46) = this;
  if ( a5 - 1 > 1 )
  {
LABEL_80:
    if ( a6 && a7 && !a8 )
    {
      Handles[0] = 0;
      v21 = CoImpersonateClient();
      if ( v21 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          goto LABEL_107;
        v28 = 41;
LABEL_106:
        WPP_SF_d(v27[2], v28, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, (unsigned int)v21);
LABEL_107:
        AutoCleanup<AutoHandle,void *>::ReleasePtr(Handles);
        return v21;
      }
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x20008u, 1, Handles) )
      {
        v21 = StringCchPrintfW(Value, 0x14u, L"%p", Handles[0]);
        if ( v21 < 0 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
            goto LABEL_107;
          v28 = 42;
          goto LABEL_106;
        }
        if ( !SetEnvironmentVariableW(L"__WINRM_RUNAS_CLIENT_TOKEN__", Value) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            v30 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, v30);
          }
          if ( (int)GetLastError() > 0 )
            v21 = (unsigned __int16)GetLastError() | 0x80070000;
          else
            v21 = GetLastError();
          goto LABEL_107;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v31 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, v31);
      }
      v21 = CoRevertToSelf();
      if ( v21 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          goto LABEL_107;
        v28 = 45;
        goto LABEL_106;
      }
      Handles[0] = 0;
      AutoCleanup<AutoHandle,void *>::ReleasePtr(Handles);
    }
    (*(void (__fastcall **)(struct IWSManHostEntrySink *))(*(_QWORD *)a3 + 8LL))(a3);
    *((_QWORD *)this + 14) = a3;
    *((_DWORD *)this + 70) = 1;
    *((_DWORD *)this + 61) = a6;
    *((_DWORD *)this + 62) = a7;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_769441059adc374bf6ea72702644ec2e_Traceguids);
    return 0;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  AutoHandle::operator=((char *)this + 400, EventW);
  if ( !*((_QWORD *)this + 50) )
  {
    v21 = GetLastError();
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v23 = 35;
      goto LABEL_39;
    }
    goto LABEL_40;
  }
  (*(void (__fastcall **)(WSManProvHost *))(*(_QWORD *)this + 8LL))(this);
  if ( !QueueUserWorkItem(WSManProvHost::StartupPlugin, this, 0x10u) )
  {
    (*(void (__fastcall **)(WSManProvHost *))(*(_QWORD *)this + 16LL))(this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, 0);
    result = GetLastError();
    goto LABEL_56;
  }
  Handles[0] = *((HANDLE *)this + 50);
  Handles[1] = *((HANDLE *)this + 49);
  v25 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
  if ( !v25 )
  {
    v26 = *((unsigned int *)this + 102);
    if ( (_DWORD)v26 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, v26);
      result = *((_DWORD *)this + 102);
LABEL_56:
      if ( result <= 0 )
        return result;
      return (unsigned __int16)result | 0x80070000;
    }
    v41[0] = 0;
    *(_QWORD *)Value = &CErrorContext::`vftable';
    v41[2] = 0;
    v41[3] = -1;
    v43 = &Class;
    v44 = &Class;
    v45 = &Class;
    v46 = &Class;
    v42 = 1;
    _InterlockedIncrement(v41);
    if ( !Timer::StartTimer((char *)this + 288, (struct IRequestContext *)Value, 1000 * *((_DWORD *)this + 60)) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_769441059adc374bf6ea72702644ec2e_Traceguids);
      result = CErrorContext::GetErrorCode((CErrorContext *)Value);
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    *(_QWORD *)Value = &ILifeTimeMgmt::`vftable';
    goto LABEL_80;
  }
  if ( v25 != 1 )
  {
    v21 = GetLastError();
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v23 = 39;
      goto LABEL_39;
    }
    goto LABEL_40;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_769441059adc374bf6ea72702644ec2e_Traceguids);
  return -2147023901;
}

```

## disassembly

```asm
0x1801b3860  push    rbp
0x1801b3862  push    rbx
0x1801b3863  push    rsi
0x1801b3864  push    rdi
0x1801b3865  push    r12
0x1801b3867  push    r13
0x1801b3869  push    r14
0x1801b386b  push    r15
0x1801b386d  lea     rbp, [rsp-7]
0x1801b3872  sub     rsp, 0D8h
0x1801b3879  mov     rax, cs:__security_cookie
0x1801b3880  xor     rax, rsp
0x1801b3883  mov     [rbp+3Fh+var_50], rax
0x1801b3887  mov     rsi, r9
0x1801b388a  mov     r15, r8
0x1801b388d  mov     rbx, rdx
0x1801b3890  mov     rdi, rcx
0x1801b3893  lea     rax, WPP_GLOBAL_Control
0x1801b389a  mov     r13d, 100h
0x1801b38a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b38a7  cmp     rcx, rax
0x1801b38aa  jz      short loc_1801B38D5
0x1801b38ac  test    [rcx+1Ch], r13d
0x1801b38b0  jz      short loc_1801B38D5
0x1801b38b2  mov     edx, 19h
0x1801b38b7  lea     r8, WPP_769441059adc374bf6ea72702644ec2e_Traceguids
0x1801b38be  mov     rcx, [rcx+10h]
0x1801b38c2  call    WPP_SF_
0x1801b38c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b38ce  lea     rax, WPP_GLOBAL_Control
0x1801b38d5  xor     r12d, r12d
0x1801b38d8  test    rbx, rbx
0x1801b38db  jz      loc_1801B4092
0x1801b38e1  cmp     [rbx], r12
0x1801b38e4  jz      loc_1801B4092
0x1801b38ea  test    r15, r15
0x1801b38ed  jz      loc_1801B4092
0x1801b38f3  lea     r8, [rbx+68h]; lpName
0x1801b38f7  xor     edx, edx; bInheritHandle
0x1801b38f9  mov     ecx, 100000h; dwDesiredAccess
0x1801b38fe  call    cs:__imp_OpenEventW
0x1801b3904  lea     r14, [rdi+188h]
0x1801b390b  mov     rdx, rax
0x1801b390e  mov     rcx, r14
0x1801b3911  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x1801b3916  cmp     [r14], r12
0x1801b3919  jnz     short loc_1801B3968
0x1801b391b  call    cs:__imp_GetLastError
0x1801b3921  mov     ebx, eax
0x1801b3923  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b392a  lea     rdx, WPP_GLOBAL_Control
0x1801b3931  cmp     rcx, rdx
0x1801b3934  jz      short loc_1801B3954
0x1801b3936  test    [rcx+1Ch], r13d
0x1801b393a  jz      short loc_1801B3954
0x1801b393c  lea     edx, [r12+1Dh]
0x1801b3941  mov     r9d, eax
0x1801b3944  lea     r8, WPP_769441059adc374bf6ea72702644ec2e_Traceguids
0x1801b394b  mov     rcx, [rcx+10h]
0x1801b394f  call    WPP_SF_d
0x1801b3954  test    ebx, ebx
0x1801b3956  jle     short loc_1801B3961
0x1801b3958  movzx   ebx, bx
0x1801b395b  or      ebx, 80070000h
0x1801b3961  mov     eax, ebx
0x1801b3963  jmp     loc_1801B40B7
0x1801b3968  lea     r9, [rbx+10h]; unsigned __int16 *
0x1801b396c  mov     r8d, [rbx+0Ch]; unsigned int
0x1801b3970  mov     edx, [rbx+8]; unsigned int
0x1801b3973  mov     rcx, rdi; this
0x1801b3976  call    ?EnforceQuota@WSManProvHost@@AEAAHKKPEBG@Z; WSManProvHost::EnforceQuota(ulong,ulong,ushort const *)
0x1801b397b  test    eax, eax
0x1801b397d  jnz     short loc_1801B39A7
0x1801b397f  call    cs:__imp_GetLastError
0x1801b3985  test    eax, eax
0x1801b3987  jg      short loc_1801B3994
0x1801b3989  call    cs:__imp_GetLastError
0x1801b398f  jmp     loc_1801B40B7
0x1801b3994  call    cs:__imp_GetLastError
0x1801b399a  movzx   eax, ax
0x1801b399d  or      eax, 80070000h
0x1801b39a2  jmp     loc_1801B40B7
0x1801b39a7  lea     rcx, [rdi+10h]; this
0x1801b39ab  mov     rdx, [rbx]; unsigned __int16 *
0x1801b39ae  call    ?Initialize@IPCListener@@IEAAKPEBG@Z; IPCListener::Initialize(ushort const *)
0x1801b39b3  test    eax, eax
0x1801b39b5  jz      short loc_1801B3A34
0x1801b39b7  mov     r9d, 0Eh
0x1801b39bd  cmp     eax, r9d
0x1801b39c0  jnz     short loc_1801B39F9
0x1801b39c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b39c9  lea     rdx, WPP_GLOBAL_Control
0x1801b39d0  cmp     rcx, rdx
0x1801b39d3  jz      short loc_1801B39EF
0x1801b39d5  test    [rcx+1Ch], r13d
0x1801b39d9  jz      short loc_1801B39EF
0x1801b39db  lea     edx, [r9+10h]
0x1801b39df  lea     r8, WPP_769441059adc374bf6ea72702644ec2e_Traceguids
0x1801b39e6  mov     rcx, [rcx+10h]
0x1801b39ea  call    WPP_SF_d
0x1801b39ef  mov     eax, 8007000Eh
0x1801b39f4  jmp     loc_1801B40B7
0x1801b39f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b3a00  lea     rdx, WPP_GLOBAL_Control
0x1801b3a07  cmp     rcx, rdx
0x1801b3a0a  jz      short loc_1801B3A2A
0x1801b3a0c  test    [rcx+1Ch], r13d
0x1801b3a10  jz      short loc_1801B3A2A
0x1801b3a12  mov     edx, 1Fh
0x1801b3a17  mov     r9d, eax
0x1801b3a1a  lea     r8, WPP_769441059adc374bf6ea72702644ec2e_Traceguids
0x1801b3a21  mov     rcx, [rcx+10h]
0x1801b3a25  call    WPP_SF_d
0x1801b3a2a  mov     eax, 8000FFFFh
0x1801b3a2f  jmp     loc_1801B40B7
0x1801b3a34  mov     [rsp+110h+var_C8], r12d
0x1801b3a39  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x1801b3a40  mov     [rsp+110h+var_D0], rax
0x1801b3a45  mov     [rsp+110h+var_C0], r12d
0x1801b3a4a  mov     [rbp+3Fh+var_BC], 0FFFFFFFFh
0x1801b3a51  lea     rax, Class
0x1801b3a58  mov     [rbp+3Fh+var_B0], rax
0x1801b3a5c  mov     [rbp+3Fh+var_A8], rax
0x1801b3a60  mov     [rbp+3Fh+var_A0], rax
0x1801b3a64  mov     [rbp+3Fh+var_98], rax
0x1801b3a68  mov     [rbp+3Fh+var_B8], 1
0x1801b3a6c  lock inc [rsp+110h+var_C8]
0x1801b3a71  mov     dword ptr [rsp+110h+Handles], r12d
0x1801b3a76  lea     r8, [rsp+110h+var_D0]; struct IRequestContext *
0x1801b3a7b  lea     rdx, [rsp+110h+Handles]; int *
0x1801b3a80  mov     rcx, rsi; unsigned __int16 *
0x1801b3a83  call    ?CopyString@@YAPEAGPEBGAEBHAEAVIRequestContext@@@Z; CopyString(ushort const *,int const &,IRequestContext &)
0x1801b3a88  lea     rbx, [rdi+0D8h]
0x1801b3a8f  mov     rdx, rax
0x1801b3a92  mov     rcx, rbx
0x1801b3a95  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x1801b3a9a  cmp     [rbx], r12
0x1801b3a9d  jnz     short loc_1801B3B08
0x1801b3a9f  mov     rax, cs:WPP_GLOBAL_Control
0x1801b3aa6  lea     rdx, WPP_GLOBAL_Control
0x1801b3aad  cmp     rax, rdx
0x1801b3ab0  jz      short loc_1801B3AE1
0x1801b3ab2  test    [rax+1Ch], r13d
0x1801b3ab6  jz      short loc_1801B3AE1
0x1801b3ab8  lea     rcx, [rsp+110h+var_D0]; this
0x1801b3abd  call    ?GetErrorCode@CErrorContext@@UEBAKXZ; CErrorContext::GetErrorCode(void)
0x1801b3ac2  mov     edx, 20h ; ' '
0x1801b3ac7  mov     r9d, eax
0x1801b3aca  lea     r8, WPP_769441059adc374bf6ea72702644ec2e_Traceguids
0x1801b3ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b3ad8  mov     rcx, [rcx+10h]
0x1801b3adc  call    WPP_SF_d
0x1801b3ae1  lea     rcx, [rsp+110h+var_D0]; this
0x1801b3ae6  call    ?GetErrorCode@CErrorContext@@UEBAKXZ; CErrorContext::GetErrorCode(void)
0x1801b3aeb  lea     rcx, [rsp+110h+var_D0]; this
0x1801b3af0  test    eax, eax
0x1801b3af2  jg      short loc_1801B3AFE
0x1801b3af4  call    ?GetErrorCode@CErrorContext@@UEBAKXZ; CErrorContext::GetErrorCode(void)
0x1801b3af9  jmp     loc_1801B4021
0x1801b3afe  call    ?GetErrorCode@CErrorContext@@UEBAKXZ; CErrorContext::GetErrorCode(void)
0x1801b3b03  jmp     loc_1801B3CB2
0x1801b3b08  mov     rcx, [rdi+20h]
0x1801b3b0c  add     rcx, 20h ; ' '; this
0x1801b3b10  mov     rdx, rsi; unsigned __int16 *
0x1801b3b13  call    ?GetProvider@Catalog@@QEBAPEBVProvider@1@PEBG@Z; Catalog::GetProvider(ushort const *)
0x1801b3b18  mov     [rdi+0E8h], rax
0x1801b3b1f  mov     ecx, [rax+0ECh]
0x1801b3b25  mov     [rdi+0F0h], ecx
0x1801b3b2b  mov     esi, [rbp+3Fh+arg_20]
0x1801b3b2e  mov     [rax+0E8h], esi
0x1801b3b34  lea     rcx, [rdi+78h]; this
0x1801b3b38  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x1801b3b3d  test    eax, eax
0x1801b3b3f  jnz     short loc_1801B3B90
0x1801b3b41  call    cs:__imp_GetLastError
0x1801b3b47  mov     ebx, eax
0x1801b3b49  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b3b50  lea     rdx, WPP_GLOBAL_Control
0x1801b3b57  cmp     rcx, rdx
0x1801b3b5a  jz      short loc_1801B3B7A
0x1801b3b5c  test    [rcx+1Ch], r13d
0x1801b3b60  jz      short loc_1801B3B7A
0x1801b3b62  mov     edx, 21h ; '!'
0x1801b3b67  mov     r9d, ebx
0x1801b3b6a  lea     r8, WPP_769441059adc374bf6ea72702644ec2e_Traceguids
0x1801b3b71  mov     rcx, [rcx+10h]
0x1801b3b75  call    WPP_SF_d
0x1801b3b7a  test    ebx, ebx
0x1801b3b7c  jle     loc_1801B401F
0x1801b3b82  movzx   ebx, bx
0x1801b3b85  or      ebx, 80070000h
0x1801b3b8b  jmp     loc_1801B401F
0x1801b3b90  lea     rcx, [rdi+0A8h]; this
0x1801b3b97  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x1801b3b9c  test    eax, eax
0x1801b3b9e  jnz     short loc_1801B3BC8
0x1801b3ba0  call    cs:__imp_GetLastError
0x1801b3ba6  mov     ebx, eax
0x1801b3ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b3baf  lea     rdx, WPP_GLOBAL_Control
0x1801b3bb6  cmp     rcx, rdx
0x1801b3bb9  jz      short loc_1801B3B7A
0x1801b3bbb  test    [rcx+1Ch], r13d
0x1801b3bbf  jz      short loc_1801B3B7A
0x1801b3bc1  mov     edx, 22h ; '"'
0x1801b3bc6  jmp     short loc_1801B3B67
0x1801b3bc8  lea     rbx, [rdi+120h]
0x1801b3bcf  mov     [rbx+50h], rdi
0x1801b3bd3  lea     eax, [rsi-1]
0x1801b3bd6  cmp     eax, 1
0x1801b3bd9  ja      loc_1801B3E48
0x1801b3bdf  xor     r9d, r9d; lpName
0x1801b3be2  xor     r8d, r8d; bInitialState
0x1801b3be5  lea     edx, [r9+1]; bManualReset
0x1801b3be9  xor     ecx, ecx; lpEventAttributes
0x1801b3beb  call    cs:__imp_CreateEventW
0x1801b3bf1  lea     rsi, [rdi+190h]
0x1801b3bf8  mov     rdx, rax
0x1801b3bfb  mov     rcx, rsi
0x1801b3bfe  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x1801b3c03  cmp     [rsi], r12
0x1801b3c06  jnz     short loc_1801B3C3B
0x1801b3c08  call    cs:__imp_GetLastError
0x1801b3c0e  mov     ebx, eax
0x1801b3c10  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b3c17  lea     rdx, WPP_GLOBAL_Control
0x1801b3c1e  cmp     rcx, rdx
0x1801b3c21  jz      loc_1801B3B7A
0x1801b3c27  test    [rcx+1Ch], r13d
0x1801b3c2b  jz      loc_1801B3B7A
0x1801b3c31  mov     edx, 23h ; '#'
0x1801b3c36  jmp     loc_1801B3B67
0x1801b3c3b  mov     rax, [rdi]
0x1801b3c3e  mov     rcx, rdi
0x1801b3c41  mov     rax, [rax+8]
0x1801b3c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b3c4a  mov     r8d, 10h; Flags
0x1801b3c50  mov     rdx, rdi; Context
0x1801b3c53  lea     rcx, ?StartupPlugin@WSManProvHost@@SAKPEAX@Z; Function
0x1801b3c5a  call    cs:__imp_QueueUserWorkItem
0x1801b3c60  test    eax, eax
0x1801b3c62  jnz     short loc_1801B3CBF
0x1801b3c64  mov     rax, [rdi]
0x1801b3c67  mov     rcx, rdi
0x1801b3c6a  mov     rax, [rax+10h]
0x1801b3c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b3c73  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b3c7a  lea     rdx, WPP_GLOBAL_Control
0x1801b3c81  cmp     rcx, rdx
0x1801b3c84  jz      short loc_1801B3CA4
0x1801b3c86  test    [rcx+1Ch], r13d
0x1801b3c8a  jz      short loc_1801B3CA4
0x1801b3c8c  mov     edx, 24h ; '$'
0x1801b3c91  xor     r9d, r9d
0x1801b3c94  lea     r8, WPP_769441059adc374bf6ea72702644ec2e_Traceguids
0x1801b3c9b  mov     rcx, [rcx+10h]
0x1801b3c9f  call    WPP_SF_d
0x1801b3ca4  call    cs:__imp_GetLastError
0x1801b3caa  test    eax, eax
0x1801b3cac  jle     loc_1801B4021
0x1801b3cb2  movzx   eax, ax
0x1801b3cb5  or      eax, 80070000h
0x1801b3cba  jmp     loc_1801B4021
0x1801b3cbf  mov     rax, [rsi]
0x1801b3cc2  mov     [rsp+110h+Handles], rax
0x1801b3cc7  mov     rax, [r14]
0x1801b3cca  mov     [rsp+110h+var_D8], rax
0x1801b3ccf  mov     [rsp+110h+bAlertable], r12d; bAlertable
0x1801b3cd4  or      esi, 0FFFFFFFFh
0x1801b3cd7  mov     r9d, esi; dwMilliseconds
0x1801b3cda  xor     r8d, r8d; bWaitAll
0x1801b3cdd  lea     rdx, [rsp+110h+Handles]; lpHandles
0x1801b3ce2  lea     ecx, [r8+2]; nCount
0x1801b3ce6  call    cs:__imp_WaitForMultipleObjectsEx
0x1801b3cec  test    eax, eax
0x1801b3cee  jz      short loc_1801B3D60
0x1801b3cf0  cmp     eax, 1
0x1801b3cf3  jz      short loc_1801B3D28
0x1801b3cf5  call    cs:__imp_GetLastError
0x1801b3cfb  mov     ebx, eax
0x1801b3cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b3d04  lea     rdx, WPP_GLOBAL_Control
0x1801b3d0b  cmp     rcx, rdx
0x1801b3d0e  jz      loc_1801B3B7A
0x1801b3d14  test    [rcx+1Ch], r13d
0x1801b3d18  jz      loc_1801B3B7A
0x1801b3d1e  mov     edx, 27h ; '''
0x1801b3d23  jmp     loc_1801B3B67
0x1801b3d28  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b3d2f  lea     rdx, WPP_GLOBAL_Control
0x1801b3d36  cmp     rcx, rdx
0x1801b3d39  jz      short loc_1801B3D56
0x1801b3d3b  test    [rcx+1Ch], r13d
0x1801b3d3f  jz      short loc_1801B3D56
0x1801b3d41  mov     edx, 26h ; '&'
0x1801b3d46  lea     r8, WPP_769441059adc374bf6ea72702644ec2e_Traceguids
0x1801b3d4d  mov     rcx, [rcx+10h]
0x1801b3d51  call    WPP_SF_
0x1801b3d56  mov     eax, 800703E3h
0x1801b3d5b  jmp     loc_1801B4021
  ... truncated ...
```
