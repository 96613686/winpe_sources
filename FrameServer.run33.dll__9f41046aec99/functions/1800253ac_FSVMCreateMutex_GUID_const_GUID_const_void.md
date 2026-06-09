# FSVMCreateMutex(_GUID const &,_GUID const &,void * *)

- ea: `0x1800253ac`
- end: `0x180025753`
- name: `?FSVMCreateMutex@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `935`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e60f0`

## callees

- `0x1800041f0`
- `0x180009608`
- `0x180009b5c`
- `0x180009cc0`
- `0x180015b40`
- `0x1800198f4`
- `0x18001c444`
- `0x18002432c`
- `0x180024394`
- `0x1800253ac`
- `0x1800261ec`
- `0x180026d90`
- `0x18004d714`
- `0x18004da70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180025660`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180025660`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18002568c`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18002568c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256a4`
- `ntdll!NtCreateCrossVmMutant` at `0x18002551e`
- `ntdll!NtCreateCrossVmMutant` at `0x18002551e`

## pseudocode

```c
__int64 __fastcall FSVMCreateMutex(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  char v4; // bl
  GuidTrace *v7; // rax
  const char *String; // rbx
  GuidTrace *v9; // rax
  const char *v10; // rax
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned __int64 v14; // rdi
  int v15; // eax
  const struct std::nothrow_t *v16; // rdx
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  int v19; // eax
  const struct std::nothrow_t *v20; // rdx
  WCHAR *v21; // rcx
  HANDLE v22; // rax
  const struct std::nothrow_t *v23; // rdx
  HANDLE v24; // rax
  signed int LastError; // eax
  WCHAR *v26; // rcx
  __int64 v27; // rdx
  LPCWSTR *p_lpName; // [rsp+30h] [rbp-50h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v31[4]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v32; // [rsp+70h] [rbp-10h]
  LPCWSTR lpName; // [rsp+C0h] [rbp+40h] BYREF
  void *v34; // [rsp+C8h] [rbp+48h] BYREF

  v4 = 0;
  LODWORD(lpName) = 0;
  v34 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v7 = GuidTrace::GuidTrace((GuidTrace *)v31, a2);
    String = GuidTrace::GetString(v7);
    v9 = GuidTrace::GuidTrace((GuidTrace *)&p_lpName, a1);
    v10 = GuidTrace::GetString(v9);
    WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v10, (__int64)String);
    v4 = 3;
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    FSString::~FSString((FSString *)&p_lpName);
  }
  if ( (v4 & 1) != 0 )
    FSString::~FSString((FSString *)v31);
  if ( !a3 )
  {
    v11 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_40;
    v12 = 29;
    goto LABEL_10;
  }
  *a3 = 0;
  v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  v14 = (unsigned __int64)a2 & -(__int64)(v13 != 0);
  if ( byte_18010ED54 )
  {
    v31[0] = 48;
    memset(&v31[1], 0, 24);
    v32 = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v34,
      0);
    v15 = NtCreateCrossVmMutant(&v34, 2031617, v31, 0, a1, v14);
    v11 = v15 | 0x10000000;
    if ( v15 < 0 )
    {
      if ( g_wppLevels )
      {
        v12 = 30;
LABEL_10:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v11);
      }
LABEL_40:
      if ( byte_18010EC4D )
      {
        v27 = 34;
LABEL_44:
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v27,
          &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids,
          (unsigned int)v11);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
    goto LABEL_38;
  }
  lpName = 0;
  p_lpName = &lpName;
  *(_QWORD *)&MutexAttributes.nLength = 0;
  LOBYTE(MutexAttributes.lpSecurityDescriptor) = 1;
  v11 = BuildObjectName(a1, L"mutex", (unsigned __int16 **)&MutexAttributes);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>(&p_lpName);
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_21;
    v17 = 31;
    goto LABEL_20;
  }
  if ( v14 )
  {
    p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
    memset(&MutexAttributes, 0, sizeof(MutexAttributes));
    v19 = FSVMSecurityAttributes::Set(
            (FSVMSecurityAttributes *)&p_lpName,
            L"O:LSD:AI(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;WD)(A;;GA;;;S-1-15-3-3845273463-1331427702-1186551195-1148109977)");
    v11 = v19;
    if ( v19 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v19);
      p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
      AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&p_lpName);
      v21 = (WCHAR *)lpName;
      lpName = 0;
      if ( v21 )
        operator delete(v21, v20);
      goto LABEL_40;
    }
    v22 = CreateMutexW(&MutexAttributes, 0, lpName);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v34,
      v22);
    p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
    AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&p_lpName);
  }
  else
  {
    v24 = OpenMutexW(0x1F0001u, 0, lpName);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v34,
      v24);
  }
  if ( v34 )
  {
    v26 = (WCHAR *)lpName;
    lpName = 0;
    if ( v26 )
      operator delete(v26, v23);
LABEL_38:
    *a3 = v34;
    v34 = 0;
    goto LABEL_39;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( g_wppLevels )
  {
    v17 = 33;
LABEL_20:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v11);
  }
LABEL_21:
  v18 = (WCHAR *)lpName;
  lpName = 0;
  if ( v18 )
    operator delete(v18, v16);
LABEL_39:
  if ( v11 < 0 )
    goto LABEL_40;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v27 = 35;
    goto LABEL_44;
  }
LABEL_45:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800253ac  mov     [rsp-28h+arg_0], rbx
0x1800253b1  mov     [rsp-28h+arg_8], rsi
0x1800253b6  push    rbp
0x1800253b7  push    rdi
0x1800253b8  push    r12
0x1800253ba  push    r14
0x1800253bc  push    r15
0x1800253be  mov     rbp, rsp
0x1800253c1  sub     rsp, 80h
0x1800253c8  xor     r12d, r12d
0x1800253cb  mov     r14, r8
0x1800253ce  mov     ebx, r12d
0x1800253d1  mov     rsi, rdx
0x1800253d4  mov     dword ptr [rbp+lpName], ebx
0x1800253d7  mov     r15, rcx
0x1800253da  mov     [rbp+arg_18], r12
0x1800253de  cmp     cs:byte_18010EC4D, 8
0x1800253e5  jb      short loc_18002544F
0x1800253e7  lea     rcx, [rbp+var_30]; this
0x1800253eb  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800253f0  mov     rcx, rax; this
0x1800253f3  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800253f8  lea     rcx, [rbp+var_50]; this
0x1800253fc  mov     rdx, r15; struct _GUID *
0x1800253ff  mov     rbx, rax
0x180025402  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180025407  mov     rcx, rax; this
0x18002540a  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18002540f  cmp     cs:byte_18010ED54, r12b
0x180025416  lea     rcx, aNovail; "novail"
0x18002541d  lea     r9, aVail; "vail"
0x180025424  mov     [rsp+80h+var_58], rbx; __int64
0x180025429  cmovz   r9, rcx
0x18002542d  mov     [rsp+80h+var_60], rax; __int64
0x180025432  mov     rcx, cs:WPP_GLOBAL_Control
0x180025439  lea     edx, [r12+1Ch]
0x18002543e  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180025445  call    WPP_SF_sss
0x18002544a  lea     ebx, [r12+3]
0x18002544f  test    bl, 2
0x180025452  jz      short loc_180025460
0x180025454  and     ebx, 0FFFFFFFDh
0x180025457  lea     rcx, [rbp+var_50]; this
0x18002545b  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180025460  test    bl, 1
0x180025463  jz      short loc_18002546E
0x180025465  lea     rcx, [rbp+var_30]; this
0x180025469  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18002546e  test    r14, r14
0x180025471  jnz     short loc_1800254AC
0x180025473  mov     ebx, 80004003h
0x180025478  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002547f  jb      loc_1800256F1
0x180025485  lea     edx, [r14+1Dh]
0x180025489  mov     rcx, cs:WPP_GLOBAL_Control
0x180025490  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025497  xor     r9d, r9d
0x18002549a  mov     dword ptr [rsp+80h+var_60], ebx
0x18002549e  mov     rcx, [rcx+10h]
0x1800254a2  call    WPP_SF_qD
0x1800254a7  jmp     loc_1800256F1
0x1800254ac  mov     [r14], r12
0x1800254af  mov     rax, [rsi]
0x1800254b2  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800254b9  jnz     short loc_1800254C6
0x1800254bb  mov     rax, [rsi+8]
0x1800254bf  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800254c6  test    rax, rax
0x1800254c9  setnz   al
0x1800254cc  neg     al
0x1800254ce  sbb     rdi, rdi
0x1800254d1  and     rdi, rsi
0x1800254d4  cmp     cs:byte_18010ED54, r12b
0x1800254db  jz      short loc_180025549
0x1800254dd  xorps   xmm0, xmm0
0x1800254e0  mov     [rbp+var_30], 30h ; '0'
0x1800254e8  xor     edx, edx
0x1800254ea  mov     [rbp+var_18], r12
0x1800254ee  lea     rcx, [rbp+arg_18]
0x1800254f2  mov     [rbp+var_28], r12
0x1800254f6  movdqu  [rbp+var_10], xmm0
0x1800254fb  mov     [rbp+var_20], r12
0x1800254ff  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180025504  xor     r9d, r9d
0x180025507  mov     [rsp+80h+var_58], rdi
0x18002550c  lea     r8, [rbp+var_30]
0x180025510  mov     [rsp+80h+var_60], r15
0x180025515  mov     edx, 1F0001h
0x18002551a  lea     rcx, [rbp+arg_18]
0x18002551e  call    cs:__imp_NtCreateCrossVmMutant
0x180025524  mov     ebx, eax
0x180025526  or      ebx, 10000000h
0x18002552c  jge     loc_1800256E2
0x180025532  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025539  jb      loc_1800256F1
0x18002553f  mov     edx, 1Eh
0x180025544  jmp     loc_180025489
0x180025549  lea     rax, [rbp+lpName]
0x18002554d  mov     [rbp+lpName], r12
0x180025551  lea     r8, [rbp+MutexAttributes]; unsigned __int16 **
0x180025555  mov     [rbp+var_50], rax
0x180025559  lea     rdx, aMutex; "mutex"
0x180025560  mov     qword ptr [rbp+MutexAttributes.nLength], r12
0x180025564  mov     rcx, r15; struct _GUID *
0x180025567  mov     byte ptr [rbp+MutexAttributes.lpSecurityDescriptor], 1
0x18002556b  call    ?BuildObjectName@@YAJAEBU_GUID@@PEBGPEAPEAG@Z; BuildObjectName(_GUID const &,ushort const *,ushort * *)
0x180025570  lea     rcx, [rbp+var_50]
0x180025574  mov     ebx, eax
0x180025576  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>>::~out_param_t<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>>(void)
0x18002557b  mov     eax, ebx
0x18002557d  shr     eax, 1Fh
0x180025580  test    al, al
0x180025582  jz      short loc_1800255CB
0x180025584  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002558b  jb      short loc_1800255B0
0x18002558d  mov     edx, 1Fh
0x180025592  mov     rcx, cs:WPP_GLOBAL_Control
0x180025599  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x1800255a0  xor     r9d, r9d
0x1800255a3  mov     dword ptr [rsp+80h+var_60], ebx
0x1800255a7  mov     rcx, [rcx+10h]
0x1800255ab  call    WPP_SF_qD
0x1800255b0  mov     rcx, [rbp+lpName]; void *
0x1800255b4  mov     [rbp+lpName], r12
0x1800255b8  test    rcx, rcx
0x1800255bb  jz      loc_1800256ED
0x1800255c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800255c6  jmp     loc_1800256ED
0x1800255cb  test    rdi, rdi
0x1800255ce  jz      loc_180025681
0x1800255d4  xorps   xmm0, xmm0
0x1800255d7  lea     rdi, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x1800255de  xor     eax, eax
0x1800255e0  mov     [rbp+var_50], rdi
0x1800255e4  lea     rdx, aOLsdAiAGaSyAGa; "O:LSD:AI(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;"...
0x1800255eb  mov     qword ptr [rbp+MutexAttributes.bInheritHandle], rax
0x1800255ef  lea     rcx, [rbp+var_50]; this
0x1800255f3  movups  xmmword ptr [rbp+MutexAttributes.nLength], xmm0
0x1800255f7  call    ?Set@FSVMSecurityAttributes@@QEAAJPEBG@Z; FSVMSecurityAttributes::Set(ushort const *)
0x1800255fc  mov     ebx, eax
0x1800255fe  test    eax, eax
0x180025600  jns     short loc_180025656
0x180025602  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025609  jb      short loc_18002562E
0x18002560b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025612  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025619  mov     edx, 20h ; ' '
0x18002561e  mov     dword ptr [rsp+80h+var_60], eax
0x180025622  xor     r9d, r9d
0x180025625  mov     rcx, [rcx+10h]
0x180025629  call    WPP_SF_qD
0x18002562e  lea     rcx, [rbp+var_50]; this
0x180025632  mov     [rbp+var_50], rdi
0x180025636  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18002563b  mov     rcx, [rbp+lpName]; void *
0x18002563f  mov     [rbp+lpName], r12
0x180025643  test    rcx, rcx
0x180025646  jz      loc_1800256F1
0x18002564c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025651  jmp     loc_1800256F1
0x180025656  mov     r8, [rbp+lpName]; lpName
0x18002565a  lea     rcx, [rbp+MutexAttributes]; lpMutexAttributes
0x18002565e  xor     edx, edx; bInitialOwner
0x180025660  call    cs:__imp_CreateMutexW
0x180025666  mov     rdx, rax
0x180025669  lea     rcx, [rbp+arg_18]
0x18002566d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180025672  lea     rcx, [rbp+var_50]; this
0x180025676  mov     [rbp+var_50], rdi
0x18002567a  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18002567f  jmp     short loc_18002569E
0x180025681  mov     r8, [rbp+lpName]; lpName
0x180025685  xor     edx, edx; bInheritHandle
0x180025687  mov     ecx, 1F0001h; dwDesiredAccess
0x18002568c  call    cs:__imp_OpenMutexW
0x180025692  mov     rdx, rax
0x180025695  lea     rcx, [rbp+arg_18]
0x180025699  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002569e  cmp     [rbp+arg_18], r12
0x1800256a2  jnz     short loc_1800256D0
0x1800256a4  call    cs:__imp_GetLastError
0x1800256aa  mov     ebx, eax
0x1800256ac  test    eax, eax
0x1800256ae  jle     short loc_1800256B9
0x1800256b0  movzx   ebx, ax
0x1800256b3  or      ebx, 80070000h
0x1800256b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800256c0  jb      loc_1800255B0
0x1800256c6  mov     edx, 21h ; '!'
0x1800256cb  jmp     loc_180025592
0x1800256d0  mov     rcx, [rbp+lpName]; void *
0x1800256d4  mov     [rbp+lpName], r12
0x1800256d8  test    rcx, rcx
0x1800256db  jz      short loc_1800256E2
0x1800256dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800256e2  mov     rax, [rbp+arg_18]
0x1800256e6  mov     [r14], rax
0x1800256e9  mov     [rbp+arg_18], r12
0x1800256ed  test    ebx, ebx
0x1800256ef  jns     short loc_180025701
0x1800256f1  cmp     cs:byte_18010EC4D, 1
0x1800256f8  jb      short loc_18002572C
0x1800256fa  mov     edx, 22h ; '"'
0x1800256ff  jmp     short loc_18002570F
0x180025701  cmp     cs:byte_18010EC4D, 8
0x180025708  jb      short loc_18002572C
0x18002570a  mov     edx, 23h ; '#'
0x18002570f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025716  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x18002571d  mov     r9d, ebx
0x180025720  mov     rcx, [rcx+0D8h]
0x180025727  call    WPP_SF_d
0x18002572c  lea     rcx, [rbp+arg_18]
0x180025730  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180025735  lea     r11, [rsp+80h+var_s0]
0x18002573d  mov     eax, ebx
0x18002573f  mov     rbx, [r11+30h]
0x180025743  mov     rsi, [r11+38h]
0x180025747  mov     rsp, r11
0x18002574a  pop     r15
0x18002574c  pop     r14
0x18002574e  pop     r12
0x180025750  pop     rdi
0x180025751  pop     rbp
0x180025752  retn
```
