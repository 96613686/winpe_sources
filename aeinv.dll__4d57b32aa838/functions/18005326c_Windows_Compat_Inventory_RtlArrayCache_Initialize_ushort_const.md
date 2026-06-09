# Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)

- ea: `0x18005326c`
- end: `0x180053512`
- name: `?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `678`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::RtlArrayCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002debc`

## callees

- `0x180015eec`
- `0x180040658`
- `0x1800407d8`
- `0x1800517e0`
- `0x18005326c`
- `0x180053518`
- `0x180059920`
- `0x180059db4`
- `0x18005a8bc`
- `0x18005e028`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800532ef`
- `KERNEL32!CreateMutexExW` at `0x1800532ef`
- `KERNEL32!GetCurrentProcessId` at `0x1800532b2`
- `KERNEL32!GetCurrentProcessId` at `0x18005331d`
- `KERNEL32!GetCurrentProcessId` at `0x1800532b2`
- `KERNEL32!GetCurrentProcessId` at `0x18005331d`
- `KERNEL32!OpenFileMappingW` at `0x180053386`
- `KERNEL32!OpenFileMappingW` at `0x180053386`
- `KERNEL32!CreateFileMappingW` at `0x1800533b4`
- `KERNEL32!CreateFileMappingW` at `0x1800533b4`
- `KERNEL32!MapViewOfFile` at `0x1800533fe`
- `KERNEL32!MapViewOfFile` at `0x1800533fe`
- `KERNEL32!GetProcessHeap` at `0x180053445`
- `KERNEL32!GetProcessHeap` at `0x180053445`
- `KERNEL32!GetLastError` at `0x1800532fd`
- `KERNEL32!GetLastError` at `0x18005335e`
- `KERNEL32!GetLastError` at `0x1800533c3`
- `KERNEL32!GetLastError` at `0x1800532fd`
- `KERNEL32!GetLastError` at `0x18005335e`
- `KERNEL32!GetLastError` at `0x1800533c3`

## string_xrefs

- `0x1800532bb`: `RtlArrayCache%lsMutex%d`
- `0x180053326`: `RtlArrayCache%lsMemory%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=45 #try_helpers=1
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
        v12 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
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
        v14 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
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
0x18005326c  mov     [rsp-8+arg_10], rbx
0x180053271  mov     [rsp-8+arg_18], rsi
0x180053276  push    rbp
0x180053277  push    rdi
0x180053278  push    r14
0x18005327a  lea     rbp, [rsp-160h]
0x180053282  sub     rsp, 260h
0x180053289  mov     rax, cs:__security_cookie
0x180053290  xor     rax, rsp
0x180053293  mov     [rbp+170h+var_20], rax
0x18005329a  mov     r14, rdx
0x18005329d  mov     rdi, rcx
0x1800532a0  xor     edx, edx; Val
0x1800532a2  lea     rcx, [rsp+270h+Name]; void *
0x1800532a7  mov     r8d, 208h; Size
0x1800532ad  call    memset_0
0x1800532b2  call    cs:__imp_GetCurrentProcessId
0x1800532b8  mov     r9, r14
0x1800532bb  lea     r8, aRtlarraycacheL; "RtlArrayCache%lsMutex%d"
0x1800532c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800532c7  mov     [rsp+270h+dwMaximumSizeLow], eax
0x1800532cb  mov     edx, 104h; unsigned __int64
0x1800532d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800532d5  mov     ebx, eax
0x1800532d7  test    eax, eax
0x1800532d9  js      loc_1800534E9
0x1800532df  mov     r9d, 1F0001h; dwDesiredAccess
0x1800532e5  lea     rdx, [rsp+270h+Name]; lpName
0x1800532ea  xor     r8d, r8d; dwFlags
0x1800532ed  xor     ecx, ecx; lpMutexAttributes
0x1800532ef  call    cs:__imp_CreateMutexExW
0x1800532f5  mov     rbx, rax
0x1800532f8  test    rax, rax
0x1800532fb  jz      short loc_180053355
0x1800532fd  call    cs:__imp_GetLastError
0x180053303  mov     rdx, rbx
0x180053306  lea     rcx, [rdi+28h]
0x18005330a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005330f  lea     rdx, [rsp+270h+var_240]
0x180053314  lea     rcx, [rdi+28h]
0x180053318  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18005331d  call    cs:__imp_GetCurrentProcessId
0x180053323  mov     r9, r14
0x180053326  lea     r8, aRtlarraycacheL_0; "RtlArrayCache%lsMemory%d"
0x18005332d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180053332  mov     [rsp+270h+dwMaximumSizeLow], eax
0x180053336  mov     edx, 104h; unsigned __int64
0x18005333b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180053340  mov     ebx, eax
0x180053342  test    eax, eax
0x180053344  jns     short loc_18005337C
0x180053346  lea     rcx, [rsp+270h+var_240]
0x18005334b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180053350  jmp     loc_1800534E9
0x180053355  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005335a  test    eax, eax
0x18005335c  jns     short loc_18005330F
0x18005335e  call    cs:__imp_GetLastError
0x180053364  mov     ebx, eax
0x180053366  test    eax, eax
0x180053368  jle     loc_1800534E9
0x18005336e  movzx   ebx, ax
0x180053371  or      ebx, 80070000h
0x180053377  jmp     loc_1800534E9
0x18005337c  xor     edx, edx; bInheritHandle
0x18005337e  lea     r8, [rsp+270h+Name]; lpName
0x180053383  lea     ecx, [rdx+2]; dwDesiredAccess
0x180053386  call    cs:__imp_OpenFileMappingW
0x18005338c  mov     [rdi+20h], rax
0x180053390  test    rax, rax
0x180053393  jnz     short loc_1800533E5
0x180053395  xor     r9d, r9d; dwMaximumSizeHigh
0x180053398  lea     rax, [rsp+270h+Name]
0x18005339d  mov     [rsp+270h+lpName], rax; lpName
0x1800533a2  xor     edx, edx; lpFileMappingAttributes
0x1800533a4  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800533a8  mov     [rsp+270h+dwMaximumSizeLow], 18h; dwMaximumSizeLow
0x1800533b0  lea     r8d, [r9+4]; flProtect
0x1800533b4  call    cs:__imp_CreateFileMappingW
0x1800533ba  mov     [rdi+20h], rax
0x1800533be  test    rax, rax
0x1800533c1  jnz     short loc_1800533E1
0x1800533c3  call    cs:__imp_GetLastError
0x1800533c9  mov     ebx, eax
0x1800533cb  test    eax, eax
0x1800533cd  jle     loc_180053346
0x1800533d3  movzx   ebx, ax
0x1800533d6  or      ebx, 80070000h
0x1800533dc  jmp     loc_180053346
0x1800533e1  xor     bl, bl
0x1800533e3  jmp     short loc_1800533E7
0x1800533e5  mov     bl, 1
0x1800533e7  xor     r9d, r9d; dwFileOffsetLow
0x1800533ea  mov     qword ptr [rsp+270h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1800533f3  xor     r8d, r8d; dwFileOffsetHigh
0x1800533f6  mov     edx, 0F001Fh; dwDesiredAccess
0x1800533fb  mov     rcx, rax; hFileMappingObject
0x1800533fe  call    cs:__imp_MapViewOfFile
0x180053404  mov     [rdi+30h], rax
0x180053408  test    rax, rax
0x18005340b  jz      short loc_1800533C3
0x18005340d  test    bl, bl
0x18005340f  jnz     loc_1800534C7
0x180053415  mov     esi, 30h ; '0'
0x18005341a  mov     dword ptr [rax+10h], 0
0x180053421  mov     ecx, esi; unsigned __int64
0x180053423  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005342a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005342f  mov     rbx, rax
0x180053432  test    rax, rax
0x180053435  jz      short loc_180053478
0x180053437  xorps   xmm0, xmm0
0x18005343a  movups  xmmword ptr [rax], xmm0
0x18005343d  movups  xmmword ptr [rax+10h], xmm0
0x180053441  movups  xmmword ptr [rax+20h], xmm0
0x180053445  call    cs:__imp_GetProcessHeap
0x18005344b  mov     [rbx], rax
0x18005344e  mov     qword ptr [rbx+20h], 10h
0x180053456  mov     qword ptr [rbx+10h], 0
0x18005345e  mov     qword ptr [rbx+18h], 0
0x180053466  mov     qword ptr [rbx+28h], 0
0x18005346e  mov     qword ptr [rbx+8], 8
0x180053476  jmp     short loc_18005347A
0x180053478  xor     ebx, ebx
0x18005347a  mov     rax, [rdi+30h]
0x18005347e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180053485  mov     rcx, rsi; unsigned __int64
0x180053488  mov     [rax], rbx
0x18005348b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180053490  test    rax, rax
0x180053493  jz      short loc_1800534A2
0x180053495  mov     rcx, rax
0x180053498  call    ??0?$RtlArray@PEAVRtlArrayCacheTuple@Inventory@Compat@Windows@@@@QEAA@XZ; RtlArray<Windows::Compat::Inventory::RtlArrayCacheTuple *>::RtlArray<Windows::Compat::Inventory::RtlArrayCacheTuple *>(void)
0x18005349d  mov     rcx, rax
0x1800534a0  jmp     short loc_1800534A4
0x1800534a2  xor     ecx, ecx
0x1800534a4  mov     rax, [rdi+30h]
0x1800534a8  mov     [rax+8], rcx
0x1800534ac  mov     rax, [rdi+30h]
0x1800534b0  cmp     qword ptr [rax], 0
0x1800534b4  jz      short loc_1800534BD
0x1800534b6  cmp     qword ptr [rax+8], 0
0x1800534bb  jnz     short loc_1800534C7
0x1800534bd  mov     ebx, 8007000Eh
0x1800534c2  jmp     loc_180053346
0x1800534c7  inc     dword ptr [rax+10h]
0x1800534ca  lea     rcx, [rsp+270h+var_240]
0x1800534cf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800534d4  mov     rcx, [rdi+30h]
0x1800534d8  xor     ebx, ebx
0x1800534da  mov     rax, [rcx+8]
0x1800534de  mov     [rdi+10h], rax
0x1800534e2  mov     rax, [rcx]
0x1800534e5  mov     [rdi+8], rax
0x1800534e9  mov     eax, ebx
0x1800534eb  mov     rcx, [rbp+170h+var_20]
0x1800534f2  xor     rcx, rsp; StackCookie
0x1800534f5  call    __security_check_cookie
0x1800534fa  lea     r11, [rsp+270h+var_10]
0x180053502  mov     rbx, [r11+30h]
0x180053506  mov     rsi, [r11+38h]
0x18005350a  mov     rsp, r11
0x18005350d  pop     r14
0x18005350f  pop     rdi
0x180053510  pop     rbp
0x180053511  retn
```
