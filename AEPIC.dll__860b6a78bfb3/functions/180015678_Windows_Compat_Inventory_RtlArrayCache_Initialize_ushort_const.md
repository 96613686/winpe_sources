# Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)

- ea: `0x180015678`
- end: `0x18001591e`
- name: `?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `678`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::RtlArrayCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180015cf0`

## callees

- `0x180005890`
- `0x180005d6c`
- `0x180006938`
- `0x180008630`
- `0x180009da8`
- `0x18000cb74`
- `0x18000d98c`
- `0x18000dcb8`
- `0x18000fa5c`
- `0x180015678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800156fb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800156fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015851`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001576a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001576a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800156be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800156be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015729`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180015792`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180015792`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800157c0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800157c0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001580a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001580a`

## string_xrefs

- `0x1800156c7`: `RtlArrayCache%lsMutex%d`
- `0x180015732`: `RtlArrayCache%lsMemory%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
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
  _QWORD *v13; // rbx
  void *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  DWORD dwMaximumSizeLowa; // [rsp+20h] [rbp-E0h]
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-E0h]
  _BYTE v20[16]; // [rsp+30h] [rbp-D0h] BYREF
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
        if ( v12 )
        {
          *v12 = 0;
          v12[1] = 0;
          v12[2] = 0;
          *(_QWORD *)v12 = GetProcessHeap();
          v13[4] = 16;
          v13[2] = 0;
          v13[3] = 0;
          v13[5] = 0;
          v13[1] = 8;
        }
        else
        {
          v13 = 0;
        }
        **((_QWORD **)this + 6) = v13;
        v14 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
        v15 = v14
            ? RtlArray<Windows::Compat::Inventory::RtlArrayCacheTuple *>::RtlArray<Windows::Compat::Inventory::RtlArrayCacheTuple *>(v14)
            : 0LL;
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
            v4 = 0;
            *((_QWORD *)this + 2) = v16[1];
            *((_QWORD *)this + 1) = *v16;
            return (unsigned int)v4;
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
0x180015678  mov     [rsp-8+arg_10], rbx
0x18001567d  mov     [rsp-8+arg_18], rsi
0x180015682  push    rbp
0x180015683  push    rdi
0x180015684  push    r14
0x180015686  lea     rbp, [rsp-160h]
0x18001568e  sub     rsp, 260h
0x180015695  mov     rax, cs:__security_cookie
0x18001569c  xor     rax, rsp
0x18001569f  mov     [rbp+170h+var_20], rax
0x1800156a6  mov     r14, rdx
0x1800156a9  mov     rdi, rcx
0x1800156ac  xor     edx, edx; Val
0x1800156ae  lea     rcx, [rsp+270h+Name]; void *
0x1800156b3  mov     r8d, 208h; Size
0x1800156b9  call    memset_0
0x1800156be  call    cs:__imp_GetCurrentProcessId
0x1800156c4  mov     r9, r14
0x1800156c7  lea     r8, aRtlarraycacheL; "RtlArrayCache%lsMutex%d"
0x1800156ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800156d3  mov     [rsp+270h+dwMaximumSizeLow], eax
0x1800156d7  mov     edx, 104h; unsigned __int64
0x1800156dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800156e1  mov     ebx, eax
0x1800156e3  test    eax, eax
0x1800156e5  js      loc_1800158F5
0x1800156eb  mov     r9d, 1F0001h; dwDesiredAccess
0x1800156f1  lea     rdx, [rsp+270h+Name]; lpName
0x1800156f6  xor     r8d, r8d; dwFlags
0x1800156f9  xor     ecx, ecx; lpMutexAttributes
0x1800156fb  call    cs:__imp_CreateMutexExW
0x180015701  mov     rbx, rax
0x180015704  test    rax, rax
0x180015707  jz      short loc_180015761
0x180015709  call    cs:__imp_GetLastError
0x18001570f  mov     rdx, rbx
0x180015712  lea     rcx, [rdi+28h]
0x180015716  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001571b  lea     rdx, [rsp+270h+var_240]
0x180015720  lea     rcx, [rdi+28h]
0x180015724  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180015729  call    cs:__imp_GetCurrentProcessId
0x18001572f  mov     r9, r14
0x180015732  lea     r8, aRtlarraycacheL_0; "RtlArrayCache%lsMemory%d"
0x180015739  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001573e  mov     [rsp+270h+dwMaximumSizeLow], eax
0x180015742  mov     edx, 104h; unsigned __int64
0x180015747  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001574c  mov     ebx, eax
0x18001574e  test    eax, eax
0x180015750  jns     short loc_180015788
0x180015752  lea     rcx, [rsp+270h+var_240]
0x180015757  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001575c  jmp     loc_1800158F5
0x180015761  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180015766  test    eax, eax
0x180015768  jns     short loc_18001571B
0x18001576a  call    cs:__imp_GetLastError
0x180015770  mov     ebx, eax
0x180015772  test    eax, eax
0x180015774  jle     loc_1800158F5
0x18001577a  movzx   ebx, ax
0x18001577d  or      ebx, 80070000h
0x180015783  jmp     loc_1800158F5
0x180015788  xor     edx, edx; bInheritHandle
0x18001578a  lea     r8, [rsp+270h+Name]; lpName
0x18001578f  lea     ecx, [rdx+2]; dwDesiredAccess
0x180015792  call    cs:__imp_OpenFileMappingW
0x180015798  mov     [rdi+20h], rax
0x18001579c  test    rax, rax
0x18001579f  jnz     short loc_1800157F1
0x1800157a1  xor     r9d, r9d; dwMaximumSizeHigh
0x1800157a4  lea     rax, [rsp+270h+Name]
0x1800157a9  mov     [rsp+270h+lpName], rax; lpName
0x1800157ae  xor     edx, edx; lpFileMappingAttributes
0x1800157b0  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800157b4  mov     [rsp+270h+dwMaximumSizeLow], 18h; dwMaximumSizeLow
0x1800157bc  lea     r8d, [r9+4]; flProtect
0x1800157c0  call    cs:__imp_CreateFileMappingW
0x1800157c6  mov     [rdi+20h], rax
0x1800157ca  test    rax, rax
0x1800157cd  jnz     short loc_1800157ED
0x1800157cf  call    cs:__imp_GetLastError
0x1800157d5  mov     ebx, eax
0x1800157d7  test    eax, eax
0x1800157d9  jle     loc_180015752
0x1800157df  movzx   ebx, ax
0x1800157e2  or      ebx, 80070000h
0x1800157e8  jmp     loc_180015752
0x1800157ed  xor     bl, bl
0x1800157ef  jmp     short loc_1800157F3
0x1800157f1  mov     bl, 1
0x1800157f3  xor     r9d, r9d; dwFileOffsetLow
0x1800157f6  mov     qword ptr [rsp+270h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1800157ff  xor     r8d, r8d; dwFileOffsetHigh
0x180015802  mov     edx, 0F001Fh; dwDesiredAccess
0x180015807  mov     rcx, rax; hFileMappingObject
0x18001580a  call    cs:__imp_MapViewOfFile
0x180015810  mov     [rdi+30h], rax
0x180015814  test    rax, rax
0x180015817  jz      short loc_1800157CF
0x180015819  test    bl, bl
0x18001581b  jnz     loc_1800158D3
0x180015821  mov     esi, 30h ; '0'
0x180015826  mov     dword ptr [rax+10h], 0
0x18001582d  mov     ecx, esi; unsigned __int64
0x18001582f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015836  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001583b  mov     rbx, rax
0x18001583e  test    rax, rax
0x180015841  jz      short loc_180015884
0x180015843  xorps   xmm0, xmm0
0x180015846  movups  xmmword ptr [rax], xmm0
0x180015849  movups  xmmword ptr [rax+10h], xmm0
0x18001584d  movups  xmmword ptr [rax+20h], xmm0
0x180015851  call    cs:__imp_GetProcessHeap
0x180015857  mov     [rbx], rax
0x18001585a  mov     qword ptr [rbx+20h], 10h
0x180015862  mov     qword ptr [rbx+10h], 0
0x18001586a  mov     qword ptr [rbx+18h], 0
0x180015872  mov     qword ptr [rbx+28h], 0
0x18001587a  mov     qword ptr [rbx+8], 8
0x180015882  jmp     short loc_180015886
0x180015884  xor     ebx, ebx
0x180015886  mov     rax, [rdi+30h]
0x18001588a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015891  mov     rcx, rsi; unsigned __int64
0x180015894  mov     [rax], rbx
0x180015897  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001589c  test    rax, rax
0x18001589f  jz      short loc_1800158AE
0x1800158a1  mov     rcx, rax
0x1800158a4  call    ??0?$RtlArray@PEAVRtlArrayCacheTuple@Inventory@Compat@Windows@@@@QEAA@XZ; RtlArray<Windows::Compat::Inventory::RtlArrayCacheTuple *>::RtlArray<Windows::Compat::Inventory::RtlArrayCacheTuple *>(void)
0x1800158a9  mov     rcx, rax
0x1800158ac  jmp     short loc_1800158B0
0x1800158ae  xor     ecx, ecx
0x1800158b0  mov     rax, [rdi+30h]
0x1800158b4  mov     [rax+8], rcx
0x1800158b8  mov     rax, [rdi+30h]
0x1800158bc  cmp     qword ptr [rax], 0
0x1800158c0  jz      short loc_1800158C9
0x1800158c2  cmp     qword ptr [rax+8], 0
0x1800158c7  jnz     short loc_1800158D3
0x1800158c9  mov     ebx, 8007000Eh
0x1800158ce  jmp     loc_180015752
0x1800158d3  inc     dword ptr [rax+10h]
0x1800158d6  lea     rcx, [rsp+270h+var_240]
0x1800158db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800158e0  mov     rcx, [rdi+30h]
0x1800158e4  xor     ebx, ebx
0x1800158e6  mov     rax, [rcx+8]
0x1800158ea  mov     [rdi+10h], rax
0x1800158ee  mov     rax, [rcx]
0x1800158f1  mov     [rdi+8], rax
0x1800158f5  mov     eax, ebx
0x1800158f7  mov     rcx, [rbp+170h+var_20]
0x1800158fe  xor     rcx, rsp; StackCookie
0x180015901  call    __security_check_cookie
0x180015906  lea     r11, [rsp+270h+var_10]
0x18001590e  mov     rbx, [r11+30h]
0x180015912  mov     rsi, [r11+38h]
0x180015916  mov     rsp, r11
0x180015919  pop     r14
0x18001591b  pop     rdi
0x18001591c  pop     rbp
0x18001591d  retn
```
