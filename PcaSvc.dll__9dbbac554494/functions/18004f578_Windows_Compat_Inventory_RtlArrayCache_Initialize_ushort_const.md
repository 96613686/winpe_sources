# Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)

- ea: `0x18004f578`
- end: `0x18004f865`
- name: `?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `749`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::RtlArrayCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a1638`

## callees

- `0x18000dc08`
- `0x18004aaa0`
- `0x18004abc4`
- `0x18004e92c`
- `0x18004f578`
- `0x18004f878`
- `0x18007a6e8`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004f5fb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004f5fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f5be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f62a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f5be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f62a`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18004f693`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18004f693`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004f70b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004f70b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004f6c1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004f6c1`

## string_xrefs

- `0x18004f637`: `RtlArrayCache%lsMemory%d`
- `0x18004f5cb`: `RtlArrayCache%lsMutex%d`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::RtlArrayCache::Initialize(
        Windows::Compat::Inventory::RtlArrayCache *this,
        const unsigned __int16 *a2)
{
  signed int v4; // ebx
  wil::details *v5; // rcx
  HANDLE Mutex; // rbx
  signed int v7; // eax
  HANDLE FileMappingW; // rax
  signed int LastError; // eax
  char v10; // bl
  _DWORD *v11; // rax
  _OWORD *v12; // rax
  _OWORD *v13; // rdx
  _OWORD *v14; // rax
  _OWORD *v15; // rdx
  _QWORD *v16; // rcx
  DWORD dwMaximumSizeLowa; // [rsp+20h] [rbp-E0h]
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-E0h]
  _BYTE v20[8]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD *v21; // [rsp+38h] [rbp-C8h]
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(Name, 0, 0x208u);
  dwMaximumSizeLowa = GetCurrentProcessId();
  v4 = StringCchPrintfW(Name, 0x104u, L"RtlArrayCache%lsMutex%d", a2, dwMaximumSizeLowa);
  if ( v4 >= 0 )
  {
    Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
    if ( Mutex )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 40,
        Mutex);
      goto LABEL_4;
    }
    if ( (int)wil::details::GetLastErrorFailHr(v5) >= 0 )
    {
LABEL_4:
      _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        (char *)this + 40,
        v20);
      dwMaximumSizeLow[0] = GetCurrentProcessId();
      v4 = StringCchPrintfW(Name, 0x104u, L"RtlArrayCache%lsMemory%d", a2, *(_QWORD *)dwMaximumSizeLow);
      if ( v4 < 0 )
      {
LABEL_5:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
        return (unsigned int)v4;
      }
      FileMappingW = OpenFileMappingW(2u, 0, Name);
      *((_QWORD *)this + 4) = FileMappingW;
      if ( FileMappingW )
      {
        v10 = 1;
      }
      else
      {
        FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x18u, Name);
        *((_QWORD *)this + 4) = FileMappingW;
        if ( !FileMappingW )
        {
LABEL_11:
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_5;
        }
        v10 = 0;
      }
      v11 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
      *((_QWORD *)this + 6) = v11;
      if ( v11 )
      {
        if ( v10 )
          goto LABEL_26;
        v11[4] = 0;
        v12 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
        v13 = v12;
        v21 = v12;
        if ( v12 )
        {
          *v12 = 0;
          v12[1] = 0;
          v12[2] = 0;
          *(_QWORD *)v12 = NtCurrentPeb()->ProcessHeap;
          *((_QWORD *)v12 + 4) = 16;
          *((_QWORD *)v12 + 2) = 0;
          *((_QWORD *)v12 + 3) = 0;
          *((_QWORD *)v12 + 5) = 0;
          *((_QWORD *)v12 + 1) = 8;
        }
        else
        {
          v13 = 0;
        }
        **((_QWORD **)this + 6) = v13;
        v14 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
        v15 = v14;
        v21 = v14;
        if ( v14 )
        {
          *v14 = 0;
          v14[1] = 0;
          v14[2] = 0;
          *(_QWORD *)v14 = NtCurrentPeb()->ProcessHeap;
          *((_QWORD *)v14 + 4) = 16;
          *((_QWORD *)v14 + 2) = 0;
          *((_QWORD *)v14 + 3) = 0;
          *((_QWORD *)v14 + 5) = 0;
          *((_QWORD *)v14 + 1) = 8;
        }
        else
        {
          v15 = 0;
        }
        *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = v15;
        v11 = (_DWORD *)*((_QWORD *)this + 6);
        if ( *(_QWORD *)v11 )
        {
          if ( *((_QWORD *)v11 + 1) )
          {
LABEL_26:
            ++v11[4];
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
            v16 = (_QWORD *)*((_QWORD *)this + 6);
            *((_QWORD *)this + 2) = v16[1];
            *((_QWORD *)this + 1) = *v16;
            return 0;
          }
        }
        v4 = -2147024882;
        goto LABEL_5;
      }
      goto LABEL_11;
    }
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004f578  mov     [rsp-8+arg_10], rbx
0x18004f57d  mov     [rsp-8+arg_18], rsi
0x18004f582  push    rbp
0x18004f583  push    rdi
0x18004f584  push    r14
0x18004f586  lea     rbp, [rsp-160h]
0x18004f58e  sub     rsp, 260h
0x18004f595  mov     rax, cs:__security_cookie
0x18004f59c  xor     rax, rsp
0x18004f59f  mov     [rbp+170h+var_20], rax
0x18004f5a6  mov     r14, rdx
0x18004f5a9  mov     rdi, rcx
0x18004f5ac  xor     edx, edx; Val
0x18004f5ae  mov     r8d, 208h; Size
0x18004f5b4  lea     rcx, [rsp+270h+Name]; void *
0x18004f5b9  call    memset_0
0x18004f5be  call    cs:__imp_GetCurrentProcessId
0x18004f5c4  mov     [rsp+270h+dwMaximumSizeLow], eax
0x18004f5c8  mov     r9, r14
0x18004f5cb  lea     r8, aRtlarraycacheL; "RtlArrayCache%lsMutex%d"
0x18004f5d2  mov     edx, 104h; unsigned __int64
0x18004f5d7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004f5dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f5e1  mov     ebx, eax
0x18004f5e3  test    eax, eax
0x18004f5e5  js      loc_18004F83C
0x18004f5eb  mov     r9d, 1F0001h; dwDesiredAccess
0x18004f5f1  xor     r8d, r8d; dwFlags
0x18004f5f4  lea     rdx, [rsp+270h+Name]; lpName
0x18004f5f9  xor     ecx, ecx; lpMutexAttributes
0x18004f5fb  call    cs:__imp_CreateMutexExW
0x18004f601  mov     rbx, rax
0x18004f604  test    rax, rax
0x18004f607  jz      short loc_18004F662
0x18004f609  call    cs:__imp_GetLastError
0x18004f60f  mov     rdx, rbx
0x18004f612  lea     rcx, [rdi+28h]
0x18004f616  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004f61b  lea     rdx, [rsp+270h+var_240]
0x18004f620  lea     rcx, [rdi+28h]
0x18004f624  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18004f629  nop
0x18004f62a  call    cs:__imp_GetCurrentProcessId
0x18004f630  mov     [rsp+270h+dwMaximumSizeLow], eax
0x18004f634  mov     r9, r14
0x18004f637  lea     r8, aRtlarraycacheL_0; "RtlArrayCache%lsMemory%d"
0x18004f63e  mov     edx, 104h; unsigned __int64
0x18004f643  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004f648  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f64d  mov     ebx, eax
0x18004f64f  test    eax, eax
0x18004f651  jns     short loc_18004F689
0x18004f653  lea     rcx, [rsp+270h+var_240]
0x18004f658  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f65d  jmp     loc_18004F83C
0x18004f662  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004f667  test    eax, eax
0x18004f669  jns     short loc_18004F61B
0x18004f66b  call    cs:__imp_GetLastError
0x18004f671  mov     ebx, eax
0x18004f673  test    eax, eax
0x18004f675  jle     loc_18004F83C
0x18004f67b  movzx   ebx, ax
0x18004f67e  or      ebx, 80070000h
0x18004f684  jmp     loc_18004F83C
0x18004f689  lea     r8, [rsp+270h+Name]; lpName
0x18004f68e  xor     edx, edx; bInheritHandle
0x18004f690  lea     ecx, [rdx+2]; dwDesiredAccess
0x18004f693  call    cs:__imp_OpenFileMappingW
0x18004f699  mov     [rdi+20h], rax
0x18004f69d  test    rax, rax
0x18004f6a0  jnz     short loc_18004F6F2
0x18004f6a2  lea     rax, [rsp+270h+Name]
0x18004f6a7  mov     [rsp+270h+lpName], rax; lpName
0x18004f6ac  mov     [rsp+270h+dwMaximumSizeLow], 18h; dwMaximumSizeLow
0x18004f6b4  xor     r9d, r9d; dwMaximumSizeHigh
0x18004f6b7  xor     edx, edx; lpFileMappingAttributes
0x18004f6b9  lea     r8d, [r9+4]; flProtect
0x18004f6bd  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18004f6c1  call    cs:__imp_CreateFileMappingW
0x18004f6c7  mov     [rdi+20h], rax
0x18004f6cb  test    rax, rax
0x18004f6ce  jnz     short loc_18004F6EE
0x18004f6d0  call    cs:__imp_GetLastError
0x18004f6d6  mov     ebx, eax
0x18004f6d8  test    eax, eax
0x18004f6da  jle     loc_18004F653
0x18004f6e0  movzx   ebx, ax
0x18004f6e3  or      ebx, 80070000h
0x18004f6e9  jmp     loc_18004F653
0x18004f6ee  xor     bl, bl
0x18004f6f0  jmp     short loc_18004F6F4
0x18004f6f2  mov     bl, 1
0x18004f6f4  mov     qword ptr [rsp+270h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18004f6fd  xor     r9d, r9d; dwFileOffsetLow
0x18004f700  xor     r8d, r8d; dwFileOffsetHigh
0x18004f703  mov     edx, 0F001Fh; dwDesiredAccess
0x18004f708  mov     rcx, rax; hFileMappingObject
0x18004f70b  call    cs:__imp_MapViewOfFile
0x18004f711  mov     [rdi+30h], rax
0x18004f715  test    rax, rax
0x18004f718  jz      short loc_18004F6D0
0x18004f71a  test    bl, bl
0x18004f71c  jnz     loc_18004F81A
0x18004f722  mov     dword ptr [rax+10h], 0
0x18004f729  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f730  mov     ebx, 30h ; '0'
0x18004f735  mov     ecx, ebx; unsigned __int64
0x18004f737  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004f73c  mov     rdx, rax
0x18004f73f  mov     [rsp+270h+var_238], rax
0x18004f744  lea     esi, [rbx-20h]
0x18004f747  lea     r14d, [rbx-28h]
0x18004f74b  test    rax, rax
0x18004f74e  jz      short loc_18004F790
0x18004f750  xorps   xmm1, xmm1
0x18004f753  movups  xmmword ptr [rax], xmm1
0x18004f756  movups  xmmword ptr [rax+10h], xmm1
0x18004f75a  movups  xmmword ptr [rax+20h], xmm1
0x18004f75e  mov     rax, gs:60h
0x18004f767  mov     rcx, [rax+30h]
0x18004f76b  mov     [rdx], rcx
0x18004f76e  mov     [rdx+20h], rsi
0x18004f772  mov     qword ptr [rdx+10h], 0
0x18004f77a  mov     qword ptr [rdx+18h], 0
0x18004f782  mov     qword ptr [rdx+28h], 0
0x18004f78a  mov     [rdx+8], r14
0x18004f78e  jmp     short loc_18004F792
0x18004f790  xor     edx, edx
0x18004f792  mov     rax, [rdi+30h]
0x18004f796  mov     [rax], rdx
0x18004f799  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f7a0  mov     rcx, rbx; unsigned __int64
0x18004f7a3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004f7a8  mov     rdx, rax
0x18004f7ab  mov     [rsp+270h+var_238], rax
0x18004f7b0  test    rax, rax
0x18004f7b3  jz      short loc_18004F7F5
0x18004f7b5  xorps   xmm1, xmm1
0x18004f7b8  movups  xmmword ptr [rax], xmm1
0x18004f7bb  movups  xmmword ptr [rax+10h], xmm1
0x18004f7bf  movups  xmmword ptr [rax+20h], xmm1
0x18004f7c3  mov     rax, gs:60h
0x18004f7cc  mov     rcx, [rax+30h]
0x18004f7d0  mov     [rdx], rcx
0x18004f7d3  mov     [rdx+20h], rsi
0x18004f7d7  mov     qword ptr [rdx+10h], 0
0x18004f7df  mov     qword ptr [rdx+18h], 0
0x18004f7e7  mov     qword ptr [rdx+28h], 0
0x18004f7ef  mov     [rdx+8], r14
0x18004f7f3  jmp     short loc_18004F7F7
0x18004f7f5  xor     edx, edx
0x18004f7f7  mov     rax, [rdi+30h]
0x18004f7fb  mov     [rax+8], rdx
0x18004f7ff  mov     rax, [rdi+30h]
0x18004f803  cmp     qword ptr [rax], 0
0x18004f807  jz      short loc_18004F810
0x18004f809  cmp     qword ptr [rax+8], 0
0x18004f80e  jnz     short loc_18004F81A
0x18004f810  mov     ebx, 8007000Eh
0x18004f815  jmp     loc_18004F653
0x18004f81a  inc     dword ptr [rax+10h]
0x18004f81d  lea     rcx, [rsp+270h+var_240]
0x18004f822  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f827  mov     rcx, [rdi+30h]
0x18004f82b  mov     rax, [rcx+8]
0x18004f82f  mov     [rdi+10h], rax
0x18004f833  mov     rax, [rcx]
0x18004f836  mov     [rdi+8], rax
0x18004f83a  xor     ebx, ebx
0x18004f83c  mov     eax, ebx
0x18004f83e  mov     rcx, [rbp+170h+var_20]
0x18004f845  xor     rcx, rsp; StackCookie
0x18004f848  call    __security_check_cookie
0x18004f84d  lea     r11, [rsp+270h+var_10]
0x18004f855  mov     rbx, [r11+30h]
0x18004f859  mov     rsi, [r11+38h]
0x18004f85d  mov     rsp, r11
0x18004f860  pop     r14
0x18004f862  pop     rdi
0x18004f863  pop     rbp
0x18004f864  retn
```
