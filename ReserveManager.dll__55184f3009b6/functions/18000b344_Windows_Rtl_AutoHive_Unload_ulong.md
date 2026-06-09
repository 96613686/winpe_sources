# Windows::Rtl::AutoHive::Unload(ulong)

- ea: `0x18000b344`
- end: `0x18000b7fd`
- name: `?Unload@AutoHive@Rtl@Windows@@QEAAJK@Z`
- size: `1209`
- prototype: `__int64 __fastcall(Windows::Rtl::AutoHive *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005878`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000b344`
- `0x18000efd4`
- `0x18000fafc`
- `0x180010794`
- `0x180010d84`
- `0x180010ea4`
- `0x180010fe0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18000b59a`
- `ntdll!NtCreateFile` at `0x18000b59a`
- `ntdll!NtClose` at `0x18000b3dd`
- `ntdll!NtClose` at `0x18000b5da`
- `ntdll!NtClose` at `0x18000b75a`
- `ntdll!NtClose` at `0x18000b77d`
- `ntdll!NtClose` at `0x18000b3dd`
- `ntdll!NtClose` at `0x18000b5da`
- `ntdll!NtClose` at `0x18000b75a`
- `ntdll!NtClose` at `0x18000b77d`
- `ntdll!NtUnloadKey2` at `0x18000b48a`
- `ntdll!NtUnloadKey2` at `0x18000b48a`
- `ntdll!NtFlushKey` at `0x18000b3cf`
- `ntdll!NtFlushKey` at `0x18000b3cf`

## string_xrefs

- `0x18000b509`: `Open keys still exist for {}`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::AutoHive::Unload(Windows::Rtl::AutoHive *this)
{
  int v2; // r14d
  int v3; // edi
  _QWORD *v4; // rcx
  unsigned int *v5; // rsi
  ULONG v6; // edx
  NTSTATUS v7; // eax
  unsigned int v8; // edx
  Windows::WCP::Rtl *v9; // rcx
  unsigned int v10; // r8d
  int v11; // r15d
  char v12; // r12
  __int64 v14; // rcx
  char *v15; // rbx
  __int64 v16; // rcx
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *ShareAccess; // [rsp+30h] [rbp-D0h]
  _QWORD v18[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v19[4]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v20[5]; // [rsp+A0h] [rbp-60h] BYREF
  _OBJECT_ATTRIBUTES TargetKey; // [rsp+C8h] [rbp-38h] BYREF
  int v22; // [rsp+F8h] [rbp-8h] BYREF
  NTSTATUS v23; // [rsp+FCh] [rbp-4h] BYREF
  void *FileHandle[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v25; // [rsp+110h] [rbp+10h]
  HANDLE v26; // [rsp+118h] [rbp+18h] BYREF
  char v27; // [rsp+120h] [rbp+20h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+128h] [rbp+28h] BYREF
  void **v29; // [rsp+138h] [rbp+38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+140h] [rbp+40h] BYREF
  __int64 v31; // [rsp+170h] [rbp+70h]
  __int64 (__fastcall *v32)(); // [rsp+178h] [rbp+78h]
  int *v33; // [rsp+180h] [rbp+80h]
  __int64 v34; // [rsp+188h] [rbp+88h]
  __int64 (__fastcall *v35)(); // [rsp+190h] [rbp+90h]
  NTSTATUS *v36; // [rsp+198h] [rbp+98h]

  v20[4] = -2;
  v2 = *((_DWORD *)this + 11);
  v26 = 0;
  v27 = 0;
  if ( *((_BYTE *)this + 40) )
  {
    FileHandle[0] = (void *)&RtlSystemUtil::RestorePrivilegeAcquisition::Privs;
    FileHandle[1] = (void *)2;
    v3 = RtlSystemUtil::PrivilegeAcquisition::Acquire((__int64)&v26, (__int64)FileHandle);
    if ( v3 < 0 )
      goto LABEL_44;
  }
  if ( *(_QWORD *)this && *((_BYTE *)this + 40) && (v2 & 2) == 0 )
    NtFlushKey(*(HANDLE *)this);
  if ( *(_QWORD *)this )
  {
    v3 = NtClose(*(HANDLE *)this);
    if ( v3 < 0 )
    {
      v18[0] = "OneCore\\Internal\\Base\\inc\\auto_hive.h";
      v18[1] = "Windows::Rtl::AutoHive::Unload";
      v18[2] = 346;
      v18[3] = "::NtClose(m_RootKey)";
      v4 = v18;
LABEL_10:
      RtlReportErrorOrigination(v4, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v3);
LABEL_44:
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v26);
      return (unsigned int)v3;
    }
    *(_QWORD *)this = 0;
  }
  v5 = (unsigned int *)((char *)this + 8);
  if ( *((_BYTE *)this + 40) )
  {
    *(_QWORD *)&TargetKey.Length = 48;
    TargetKey.RootDirectory = 0;
    TargetKey.ObjectName = (PUNICODE_STRING)((char *)this + 8);
    *(_QWORD *)&TargetKey.Attributes = 64;
    *(_OWORD *)&TargetKey.SecurityDescriptor = 0;
    v6 = 0;
    v22 = 0;
    if ( (v2 & 0x400) != 0 || (v2 & 0x20) == 0 )
    {
      v6 = 1;
      v22 = 1;
    }
    if ( (v2 & 0x200) == 0 )
      *((_BYTE *)this + 40) = 0;
    v7 = NtUnloadKey2(&TargetKey, v6);
    v3 = v7;
    v23 = v7;
    if ( v7 == -1073741811 )
    {
      *((_BYTE *)this + 40) = 0;
      goto LABEL_47;
    }
    v11 = 20;
    if ( v7 == -1073741535 )
    {
      if ( (v2 & 0x800) != 0 )
      {
        v12 = 1;
        *(__m128i *)FileHandle = _mm_unpacklo_epi32(
                                   _mm_unpacklo_epi16(_mm_cvtsi32_si128(*v5), (__m128i)0LL),
                                   (__m128i)0LL);
        v25 = *((_QWORD *)this + 2);
        IoStatusBlock.Pointer = 0;
        IoStatusBlock.Information = (ULONG_PTR)`Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
        v29 = FileHandle;
        Windows::WCP::Rtl::RtlTraceFromParameterList(
          v9,
          v8,
          v10,
          (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Open keys still exist for {}",
          (const char *const)1,
          (unsigned __int64)&IoStatusBlock,
          ShareAccess);
LABEL_23:
        *((_BYTE *)this + 40) = 0;
        if ( (v2 & 0x80u) == 0 )
        {
          while ( !v12 )
          {
            FileHandle[0] = 0;
            *(_QWORD *)&ObjectAttributes.Length = 48;
            *(_QWORD *)&ObjectAttributes.Attributes = 64;
            IoStatusBlock = 0;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)this + 24);
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v3 = NtCreateFile(FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, 0x4060u, 0, 0);
            if ( (((unsigned __int64)FileHandle[0] + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
            {
              if ( NtClose(FileHandle[0]) < 0 )
                __fastfail(7u);
              goto LABEL_47;
            }
            if ( v3 != -1073741757 )
            {
              if ( v3 >= 0 )
                INTERNAL_ERROR_ACTION(-1073741595);
              v20[0] = "OneCore\\Internal\\Base\\inc\\auto_hive.h";
              v20[1] = "Windows::Rtl::AutoHive::Unload";
              v20[2] = 464;
              v20[3] = 0;
              RtlReportErrorOrigination(v20, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v3);
              if ( (unsigned __int64)FileHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                if ( NtClose(FileHandle[0]) < 0 )
                  __fastfail(7u);
                FileHandle[0] = 0;
              }
              goto LABEL_44;
            }
            --v11;
            DelayExecution();
            if ( (unsigned __int64)FileHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileHandle[0]) < 0 )
              __fastfail(7u);
            if ( !v11 )
              goto LABEL_47;
          }
        }
        goto LABEL_47;
      }
    }
    else if ( v7 >= 0 )
    {
      goto LABEL_34;
    }
    *(__m128i *)FileHandle = _mm_unpacklo_epi32(_mm_unpacklo_epi16(_mm_cvtsi32_si128(*v5), (__m128i)0LL), (__m128i)0LL);
    v25 = *((_QWORD *)this + 2);
    IoStatusBlock = (_IO_STATUS_BLOCK)_mm_unpacklo_epi32(
                                        _mm_unpacklo_epi16(_mm_cvtsi32_si128(*((_DWORD *)this + 6)), (__m128i)0LL),
                                        (__m128i)0LL);
    v29 = (void **)*((_QWORD *)this + 4);
    *(_QWORD *)&ObjectAttributes.Length = 0;
    ObjectAttributes.RootDirectory = `Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&IoStatusBlock;
    *(_QWORD *)&ObjectAttributes.Attributes = 0;
    ObjectAttributes.SecurityDescriptor = `Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
    ObjectAttributes.SecurityQualityOfService = FileHandle;
    v31 = 0;
    v32 = `Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING,_LUNICODE_STRING,unsigned long,long>'::`2'::_lambda_3_::_lambda_invoker_cdecl_;
    v33 = &v22;
    v34 = 0;
    v35 = `Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING,_LUNICODE_STRING,unsigned long,long>'::`2'::_lambda_4_::_lambda_invoker_cdecl_;
    v36 = &v23;
    Windows::WCP::Rtl::RtlTraceFromParameterList(
      v9,
      v8,
      v10,
      (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Failed unloading hive file: {0}, key: {1}, with flags: {2}, NTSTATUS: {3}\n",
      (const char *const)4,
      (unsigned __int64)&ObjectAttributes,
      ShareAccess);
    v3 = v23;
LABEL_34:
    v12 = 0;
    if ( (v2 & 0x40) != 0 )
    {
      if ( v3 < 0 )
        goto LABEL_44;
    }
    else if ( v3 < 0 )
    {
      v19[0] = "OneCore\\Internal\\Base\\inc\\auto_hive.h";
      v19[1] = "Windows::Rtl::AutoHive::Unload";
      v19[2] = 424;
      v19[3] = "UnloadStatus";
      v4 = v19;
      goto LABEL_10;
    }
    goto LABEL_23;
  }
LABEL_47:
  v14 = *((_QWORD *)this + 2);
  if ( v14 )
  {
    if ( this != (Windows::Rtl::AutoHive *)-8LL )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
    *(_OWORD *)v5 = 0;
  }
  v15 = (char *)this + 24;
  v16 = *((_QWORD *)v15 + 1);
  if ( v16 )
  {
    if ( v15 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v16);
    *(_OWORD *)v15 = 0;
  }
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v26);
  return 0;
}

```

## disassembly

```asm
0x18000b344  push    rbp
0x18000b346  push    rbx
0x18000b347  push    rsi
0x18000b348  push    rdi
0x18000b349  push    r12
0x18000b34b  push    r13
0x18000b34d  push    r14
0x18000b34f  push    r15
0x18000b351  lea     rbp, [rsp-0B8h]
0x18000b359  sub     rsp, 1B8h
0x18000b360  mov     [rbp+0F0h+var_130], 0FFFFFFFFFFFFFFFEh
0x18000b368  mov     rax, cs:__security_cookie
0x18000b36f  xor     rax, rsp
0x18000b372  mov     [rbp+0F0h+var_50], rax
0x18000b379  mov     rbx, rcx
0x18000b37c  mov     r14d, [rcx+2Ch]
0x18000b380  xor     r13d, r13d
0x18000b383  mov     [rbp+0F0h+var_D8], r13
0x18000b387  mov     [rbp+0F0h+var_D0], r13b
0x18000b38b  cmp     [rcx+28h], r13b
0x18000b38f  jz      short loc_18000B3BB
0x18000b391  lea     rax, ?Privs@RestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::RestorePrivilegeAcquisition::Privs
0x18000b398  mov     [rbp+0F0h+FileHandle], rax
0x18000b39c  mov     [rbp+0F0h+FileHandle+8], 2
0x18000b3a4  lea     rdx, [rbp+0F0h+FileHandle]
0x18000b3a8  lea     rcx, [rbp+0F0h+var_D8]
0x18000b3ac  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x18000b3b1  mov     edi, eax
0x18000b3b3  test    eax, eax
0x18000b3b5  js      loc_18000B76D
0x18000b3bb  mov     rcx, [rbx]; KeyHandle
0x18000b3be  test    rcx, rcx
0x18000b3c1  jz      short loc_18000B3D5
0x18000b3c3  cmp     [rbx+28h], r13b
0x18000b3c7  jz      short loc_18000B3D5
0x18000b3c9  test    r14b, 2
0x18000b3cd  jnz     short loc_18000B3D5
0x18000b3cf  call    cs:__imp_NtFlushKey
0x18000b3d5  mov     rcx, [rbx]; Handle
0x18000b3d8  test    rcx, rcx
0x18000b3db  jz      short loc_18000B432
0x18000b3dd  call    cs:__imp_NtClose
0x18000b3e3  mov     edi, eax
0x18000b3e5  test    eax, eax
0x18000b3e7  jns     short loc_18000B42F
0x18000b3e9  lea     rcx, aOnecoreInterna_2; "OneCore\\Internal\\Base\\inc\\auto_hive"...
0x18000b3f0  mov     [rsp+1F0h+var_190], rcx
0x18000b3f5  lea     rcx, aWindowsRtlAuto; "Windows::Rtl::AutoHive::Unload"
0x18000b3fc  mov     [rsp+1F0h+var_188], rcx
0x18000b401  mov     [rsp+1F0h+var_180], 15Ah
0x18000b40a  lea     rax, aNtcloseMRootke; "::NtClose(m_RootKey)"
0x18000b411  mov     [rsp+1F0h+var_178], rax
0x18000b416  lea     rcx, [rsp+1F0h+var_190]
0x18000b41b  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000b422  mov     r8d, edi
0x18000b425  call    RtlReportErrorOrigination
0x18000b42a  jmp     loc_18000B76D
0x18000b42f  mov     [rbx], r13
0x18000b432  lea     rsi, [rbx+8]
0x18000b436  cmp     [rbx+28h], r13b
0x18000b43a  jz      loc_18000B78C
0x18000b440  mov     qword ptr [rbp+0F0h+TargetKey.Length], 30h ; '0'
0x18000b448  mov     [rbp+0F0h+TargetKey.RootDirectory], r13
0x18000b44c  mov     [rbp+0F0h+TargetKey.ObjectName], rsi
0x18000b450  mov     qword ptr [rbp+0F0h+TargetKey.Attributes], 40h ; '@'
0x18000b458  xorps   xmm0, xmm0
0x18000b45b  movdqu  xmmword ptr [rbp+0F0h+TargetKey.SecurityDescriptor], xmm0
0x18000b460  mov     edx, r13d
0x18000b463  mov     [rbp+0F0h+var_F8], edx
0x18000b466  bt      r14d, 0Ah
0x18000b46b  jb      short loc_18000B473
0x18000b46d  test    r14b, 20h
0x18000b471  jnz     short loc_18000B47B
0x18000b473  mov     edx, 1; Flags
0x18000b478  mov     [rbp+0F0h+var_F8], edx
0x18000b47b  bt      r14d, 9
0x18000b480  jb      short loc_18000B486
0x18000b482  mov     [rbx+28h], r13b
0x18000b486  lea     rcx, [rbp+0F0h+TargetKey]; TargetKey
0x18000b48a  call    cs:__imp_NtUnloadKey2
0x18000b490  mov     edi, eax
0x18000b492  mov     [rbp+0F0h+var_F4], eax
0x18000b495  cmp     eax, 0C000000Dh
0x18000b49a  jnz     short loc_18000B4A5
0x18000b49c  mov     [rbx+28h], r13b
0x18000b4a0  jmp     loc_18000B78C
0x18000b4a5  mov     r15d, 14h
0x18000b4ab  cmp     eax, 0C0000121h
0x18000b4b0  jnz     loc_18000B5F7
0x18000b4b6  bt      r14d, 0Bh
0x18000b4bb  jnb     loc_18000B5FF
0x18000b4c1  mov     r12b, 1
0x18000b4c4  movd    xmm1, dword ptr [rsi]
0x18000b4c8  xorps   xmm0, xmm0
0x18000b4cb  punpcklwd xmm1, xmm0
0x18000b4cf  punpckldq xmm1, xmm0
0x18000b4d3  movdqu  xmmword ptr [rbp+0F0h+FileHandle], xmm1
0x18000b4d8  mov     rax, [rsi+8]
0x18000b4dc  mov     [rbp+0F0h+var_E0], rax
0x18000b4e0  mov     qword ptr [rbp+0F0h+IoStatusBlock], r13
0x18000b4e4  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@U_LUNICODE_STRING@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBU_LUNICODE_STRING@@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_LUNICODE_STRING const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18000b4eb  mov     [rbp+0F0h+IoStatusBlock.Information], rax
0x18000b4ef  lea     rax, [rbp+0F0h+FileHandle]
0x18000b4f3  mov     [rbp+0F0h+var_B8], rax
0x18000b4f7  lea     rax, [rbp+0F0h+IoStatusBlock]
0x18000b4fb  mov     qword ptr [rsp+1F0h+FileAttributes], rax; unsigned __int64
0x18000b500  mov     [rsp+1F0h+AllocationSize], 1; char *
0x18000b509  lea     r9, aOpenKeysStillE; "Open keys still exist for {}"
0x18000b510  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x18000b515  mov     [rbx+28h], r13b
0x18000b519  test    r14b, r14b
0x18000b51c  js      loc_18000B78C
0x18000b522  mov     r14d, 7
0x18000b528  test    r12b, r12b
0x18000b52b  jnz     loc_18000B78C
0x18000b531  mov     [rbp+0F0h+FileHandle], r13
0x18000b535  mov     qword ptr [rbp+0F0h+ObjectAttributes.Length], 30h ; '0'
0x18000b53d  mov     qword ptr [rbp+0F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000b545  xorps   xmm0, xmm0
0x18000b548  movups  xmmword ptr [rbp+0F0h+IoStatusBlock], xmm0
0x18000b54c  mov     [rbp+0F0h+ObjectAttributes.RootDirectory], r13
0x18000b550  lea     rax, [rbx+18h]
0x18000b554  mov     [rbp+0F0h+ObjectAttributes.ObjectName], rax
0x18000b558  movdqu  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b55d  mov     [rsp+1F0h+EaLength], r13d; EaLength
0x18000b562  mov     [rsp+1F0h+EaBuffer], r13; EaBuffer
0x18000b567  mov     [rsp+1F0h+CreateOptions], 4060h; CreateOptions
0x18000b56f  mov     [rsp+1F0h+CreateDisposition], 1; CreateDisposition
0x18000b577  mov     dword ptr [rsp+1F0h+ShareAccess], r13d; ShareAccess
0x18000b57c  mov     [rsp+1F0h+FileAttributes], 80h; FileAttributes
0x18000b584  mov     [rsp+1F0h+AllocationSize], r13; AllocationSize
0x18000b589  lea     r9, [rbp+0F0h+IoStatusBlock]; IoStatusBlock
0x18000b58d  lea     r8, [rbp+0F0h+ObjectAttributes]; ObjectAttributes
0x18000b591  mov     edx, 120089h; DesiredAccess
0x18000b596  lea     rcx, [rbp+0F0h+FileHandle]; FileHandle
0x18000b59a  call    cs:__imp_NtCreateFile
0x18000b5a0  mov     edi, eax
0x18000b5a2  mov     rax, [rbp+0F0h+FileHandle]
0x18000b5a6  lea     rcx, [rax+1]
0x18000b5aa  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18000b5b1  jnz     loc_18000B77A
0x18000b5b7  cmp     edi, 0C0000043h
0x18000b5bd  jnz     loc_18000B70E
0x18000b5c3  dec     r15d
0x18000b5c6  call    DelayExecution
0x18000b5cb  nop
0x18000b5cc  mov     rcx, [rbp+0F0h+FileHandle]; Handle
0x18000b5d0  lea     rax, [rcx-1]
0x18000b5d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b5d8  ja      short loc_18000B5E9
0x18000b5da  call    cs:__imp_NtClose
0x18000b5e0  test    eax, eax
0x18000b5e2  jns     short loc_18000B5E9
0x18000b5e4  mov     rcx, r14
0x18000b5e7  int     29h; Win8: RtlFailFast(ecx)
0x18000b5e9  test    r15d, r15d
0x18000b5ec  jnz     loc_18000B528
0x18000b5f2  jmp     loc_18000B78C
0x18000b5f7  test    eax, eax
0x18000b5f9  jns     loc_18000B6BE
0x18000b5ff  movd    xmm1, dword ptr [rsi]
0x18000b603  xorps   xmm0, xmm0
0x18000b606  punpcklwd xmm1, xmm0
0x18000b60a  punpckldq xmm1, xmm0
0x18000b60e  movdqu  xmmword ptr [rbp+0F0h+FileHandle], xmm1
0x18000b613  mov     rax, [rsi+8]
0x18000b617  mov     [rbp+0F0h+var_E0], rax
0x18000b61b  movd    xmm1, dword ptr [rbx+18h]
0x18000b620  punpcklwd xmm1, xmm0
0x18000b624  punpckldq xmm1, xmm0
0x18000b628  movdqu  xmmword ptr [rbp+0F0h+IoStatusBlock], xmm1
0x18000b62d  mov     rax, [rbx+20h]
0x18000b631  mov     [rbp+0F0h+var_B8], rax
0x18000b635  mov     qword ptr [rbp+0F0h+ObjectAttributes.Length], r13
0x18000b639  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@U_LUNICODE_STRING@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBU_LUNICODE_STRING@@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_LUNICODE_STRING const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18000b640  mov     [rbp+0F0h+ObjectAttributes.RootDirectory], rax
0x18000b644  lea     rax, [rbp+0F0h+IoStatusBlock]
0x18000b648  mov     [rbp+0F0h+ObjectAttributes.ObjectName], rax
0x18000b64c  mov     qword ptr [rbp+0F0h+ObjectAttributes.Attributes], r13
0x18000b650  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@U_LUNICODE_STRING@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBU_LUNICODE_STRING@@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_LUNICODE_STRING const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18000b657  mov     [rbp+0F0h+ObjectAttributes.SecurityDescriptor], rax
0x18000b65b  lea     rax, [rbp+0F0h+FileHandle]
0x18000b65f  mov     [rbp+0F0h+ObjectAttributes.SecurityQualityOfService], rax
0x18000b663  mov     [rbp+0F0h+var_80], r13
0x18000b667  lea     rax, ?_lambda_invoker_cdecl_@_lambda_3_@?1???$RtlAutoTrace@U_LUNICODE_STRING@@U1@KJ@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBU_LUNICODE_STRING@@2AEBKAEBJ@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING,_LUNICODE_STRING,ulong,long>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_LUNICODE_STRING const &,_LUNICODE_STRING const &,ulong const &,long const &)'::`2'::_lambda_3_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18000b66e  mov     [rbp+0F0h+var_78], rax
0x18000b672  lea     rax, [rbp+0F0h+var_F8]
0x18000b676  mov     [rbp+0F0h+var_70], rax
0x18000b67d  mov     [rbp+0F0h+var_68], r13
0x18000b684  lea     rax, ?_lambda_invoker_cdecl_@_lambda_4_@?1???$RtlAutoTrace@U_LUNICODE_STRING@@U1@KJ@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBU_LUNICODE_STRING@@2AEBKAEBJ@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<_LUNICODE_STRING,_LUNICODE_STRING,ulong,long>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_LUNICODE_STRING const &,_LUNICODE_STRING const &,ulong const &,long const &)'::`2'::_lambda_4_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18000b68b  mov     [rbp+0F0h+var_60], rax
0x18000b692  lea     rax, [rbp+0F0h+var_F4]
0x18000b696  mov     [rbp+0F0h+var_58], rax
0x18000b69d  lea     rax, [rbp+0F0h+ObjectAttributes]
0x18000b6a1  mov     qword ptr [rsp+1F0h+FileAttributes], rax; unsigned __int64
0x18000b6a6  mov     [rsp+1F0h+AllocationSize], 4; char *
0x18000b6af  lea     r9, aFailedUnloadin; "Failed unloading hive file: {0}, key: {"...
0x18000b6b6  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x18000b6bb  mov     edi, [rbp+0F0h+var_F4]
0x18000b6be  mov     r12b, r13b
0x18000b6c1  test    r14b, 40h
0x18000b6c5  jz      short loc_18000B6D4
0x18000b6c7  test    edi, edi
0x18000b6c9  js      loc_18000B76D
0x18000b6cf  jmp     loc_18000B515
0x18000b6d4  test    edi, edi
0x18000b6d6  jns     loc_18000B515
0x18000b6dc  lea     rcx, aOnecoreInterna_2; "OneCore\\Internal\\Base\\inc\\auto_hive"...
0x18000b6e3  mov     [rbp+0F0h+var_170], rcx
0x18000b6e7  lea     rcx, aWindowsRtlAuto; "Windows::Rtl::AutoHive::Unload"
0x18000b6ee  mov     [rbp+0F0h+var_168], rcx
0x18000b6f2  mov     [rbp+0F0h+var_160], 1A8h
0x18000b6fa  lea     rax, aUnloadstatus; "UnloadStatus"
0x18000b701  mov     [rbp+0F0h+var_158], rax
0x18000b705  lea     rcx, [rbp+0F0h+var_170]
0x18000b709  jmp     loc_18000B41B
0x18000b70e  test    edi, edi
0x18000b710  jns     loc_18000B7F2
0x18000b716  lea     rcx, aOnecoreInterna_2; "OneCore\\Internal\\Base\\inc\\auto_hive"...
0x18000b71d  mov     [rbp+0F0h+var_150], rcx
0x18000b721  lea     rcx, aWindowsRtlAuto; "Windows::Rtl::AutoHive::Unload"
0x18000b728  mov     [rbp+0F0h+var_148], rcx
0x18000b72c  mov     [rbp+0F0h+var_140], 1D0h
0x18000b734  mov     [rbp+0F0h+var_138], r13
0x18000b738  mov     r8d, edi
0x18000b73b  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000b742  lea     rcx, [rbp+0F0h+var_150]
0x18000b746  call    RtlReportErrorOrigination
0x18000b74b  nop
0x18000b74c  mov     rcx, [rbp+0F0h+FileHandle]; Handle
0x18000b750  lea     rax, [rcx-1]
0x18000b754  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b758  ja      short loc_18000B76D
0x18000b75a  call    cs:__imp_NtClose
0x18000b760  test    eax, eax
0x18000b762  jns     short loc_18000B769
0x18000b764  mov     rcx, r14
0x18000b767  int     29h; Win8: RtlFailFast(ecx)
0x18000b769  mov     [rbp+0F0h+FileHandle], r13
0x18000b76d  lea     rcx, [rbp+0F0h+var_D8]; this
0x18000b771  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18000b776  mov     eax, edi
0x18000b778  jmp     short loc_18000B7CF
0x18000b77a  mov     rcx, rax; Handle
0x18000b77d  call    cs:__imp_NtClose
0x18000b783  test    eax, eax
0x18000b785  jns     short loc_18000B78C
0x18000b787  mov     rcx, r14
0x18000b78a  int     29h; Win8: RtlFailFast(ecx)
0x18000b78c  mov     rcx, [rsi+8]
0x18000b790  test    rcx, rcx
0x18000b793  jz      short loc_18000B7A6
0x18000b795  test    rsi, rsi
0x18000b798  jz      short loc_18000B79F
0x18000b79a  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18000b79f  xorps   xmm0, xmm0
0x18000b7a2  movdqu  xmmword ptr [rsi], xmm0
0x18000b7a6  add     rbx, 18h
0x18000b7aa  mov     rcx, [rbx+8]
0x18000b7ae  test    rcx, rcx
0x18000b7b1  jz      short loc_18000B7C4
0x18000b7b3  test    rbx, rbx
0x18000b7b6  jz      short loc_18000B7BD
0x18000b7b8  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18000b7bd  xorps   xmm0, xmm0
0x18000b7c0  movdqu  xmmword ptr [rbx], xmm0
0x18000b7c4  lea     rcx, [rbp+0F0h+var_D8]; this
0x18000b7c8  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18000b7cd  xor     eax, eax
0x18000b7cf  mov     rcx, [rbp+0F0h+var_50]
0x18000b7d6  xor     rcx, rsp; StackCookie
0x18000b7d9  call    __security_check_cookie
0x18000b7de  add     rsp, 1B8h
0x18000b7e5  pop     r15
0x18000b7e7  pop     r14
0x18000b7e9  pop     r13
0x18000b7eb  pop     r12
0x18000b7ed  pop     rdi
0x18000b7ee  pop     rsi
0x18000b7ef  pop     rbx
0x18000b7f0  pop     rbp
0x18000b7f1  retn
0x18000b7f2  mov     ecx, 0C00000E5h; int
0x18000b7f7  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
