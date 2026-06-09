# DllMain

- ea: `0x18001bb10`
- end: `0x18001c2f8`
- name: `DllMain`
- size: `2024`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d124`

## callees

- `0x180005288`
- `0x180009820`
- `0x180017510`
- `0x18001bb10`
- `0x180026dc0`
- `0x1800278d0`
- `0x18002d2b0`
- `0x180067520`
- `0x18006b240`
- `0x18006e8e0`
- `0x1800735e0`
- `0x1800981e0`
- `0x18009e020`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18001c15a`
- `ntdll!NtOpenKey` at `0x18001c15a`
- `ntdll!LdrUnloadDll` at `0x18001c287`
- `ntdll!LdrUnloadDll` at `0x18001c287`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001bc39`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001bc89`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001bf87`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001bfdb`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001c0a9`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001c0fd`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001bc39`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001bc89`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001bf87`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001bfdb`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001c0a9`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18001c0fd`
- `ntdll!NtQueryValueKey` at `0x18001c191`
- `ntdll!NtQueryValueKey` at `0x18001c191`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001c075`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001c075`
- `ntdll!NtCreateFile` at `0x18001bdce`
- `ntdll!NtCreateFile` at `0x18001bdce`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001bd5f`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001bd5f`
- `ntdll!NtClose` at `0x18001be0d`
- `ntdll!NtClose` at `0x18001c1c3`
- `ntdll!NtClose` at `0x18001be0d`
- `ntdll!NtClose` at `0x18001c1c3`
- `ntdll!RtlFreeHeap` at `0x18001bdef`
- `ntdll!RtlFreeHeap` at `0x18001bdef`
- `ntdll!RtlRaiseStatus` at `0x18001bd85`
- `ntdll!RtlRaiseStatus` at `0x18001bd85`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int *v3; // rax
  PWSTR v4; // rcx
  NTSTATUS v5; // eax
  USHORT v6; // di
  PCWSTR v7; // rsi
  __int64 v8; // rdx
  _BOOL8 v9; // r8
  unsigned int *v10; // r14
  bool v11; // zf
  const WCHAR *v12; // rcx
  NTSTATUS v13; // edi
  char *v14; // rcx
  Windows::WCP::Implementation::Rtl *v15; // rcx
  size_t v16; // r8
  unsigned __int64 v17; // rdi
  const wchar_t *v18; // rdi
  PVOID Pointer; // rsi
  NTSTATUS v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  USHORT v23; // si
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  NTSTATUS v27; // eax
  USHORT v28; // di
  const wchar_t *v29; // rdi
  unsigned int Information_high; // esi
  void *v31; // rcx
  void *v32; // rcx
  __int64 v33; // rbx
  signed __int32 v35[8]; // [rsp+0h] [rbp-100h] BYREF
  struct _UNICODE_STRING Value; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR DosPathName[2]; // [rsp+A0h] [rbp-60h] BYREF
  UNICODE_STRING Name; // [rsp+B0h] [rbp-50h] BYREF
  ULONG ResultLength[4]; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v42; // [rsp+E0h] [rbp-20h]
  const char *v43; // [rsp+E8h] [rbp-18h]
  char Source[25]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v45[231]; // [rsp+109h] [rbp+9h] BYREF

  if ( !fdwReason )
  {
    v32 = (void *)_InterlockedExchange64((volatile __int64 *)&BaseAddress, 0);
    if ( v32 && LdrUnloadDll(v32) < 0 )
      __fastfail(7u);
    LODWORD(v3) = _InterlockedExchange64((volatile __int64 *)&ProcedureAddress, 0);
    v33 = _InterlockedExchange64((volatile __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream, 0);
    if ( v33 )
      LODWORD(v3) = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID))(*(_QWORD *)v33 + 504LL))(v33, 1, lpvReserved);
    g_TracingInitialized = 0;
    goto LABEL_91;
  }
  if ( fdwReason != 1 )
    goto LABEL_91;
  LODWORD(v3) = RtlRegisterErrorOriginationCallback(TraceErrorOrigination, fdwReason, lpvReserved);
  v4 = Windows::WCP::Implementation::Rtl::g_TracingStream;
  if ( !g_TracingInitialized && !Windows::WCP::Implementation::Rtl::g_TracingStream )
  {
    Src = (void *)&byte_1800AEEA5;
    xmmword_1800D2850 = xmmword_1800A3F28;
    *(_OWORD *)&Windows::WCP::Rtl::Facility_General = 0u;
    xmmword_1800D27F0 = xmmword_1800A3EF8;
    *(&Src + 1) = (void *)&byte_1800AEEA5;
    Windows::WCP::Rtl::Facility_ComponentStore = xmmword_1800A3EE8;
    Windows::WCP::Rtl::Facility_SIL = xmmword_1800A3EB8;
    xmmword_1800D2800 = *(_OWORD *)off_1800A3F08;
    xmmword_1800D2830 = *(_OWORD *)off_1800A3ED8;
    xmmword_1800D2820 = xmmword_1800A3EC8;
    *(_OWORD *)DosPathName = 0;
    Value = 0;
    Name = *(UNICODE_STRING *)L".0";
    v5 = RtlQueryEnvironmentVariable_U(0, &Name, &Value);
    if ( v5 == -1073741789 )
    {
      v6 = Value.Length + 2;
      if ( (unsigned __int16)(Value.Length + 2) < Value.Length
        || (int)RtlReallocateUnicodeString(0, (unsigned __int16)(Value.Length + 2), DosPathName) < 0 )
      {
        v7 = DosPathName[1];
LABEL_15:
        v3 = (unsigned int *)operator new(0x20u);
        v10 = v3;
        if ( v3 )
        {
          v11 = LOWORD(DosPathName[0]) == 0;
          *(_QWORD *)v3 = &off_1800A2198;
          v12 = 0;
          *((_QWORD *)v3 + 1) = 0;
          if ( !v11 )
            v12 = v7;
          *((_QWORD *)v3 + 2) = 0;
          *((_BYTE *)v3 + 24) = 0;
          *(_QWORD *)&ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.ObjectName = &Name;
          *(_QWORD *)&ObjectAttributes.Attributes = 64;
          Name = 0;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          IoStatusBlock = 0;
          if ( v12 && *v12 && RtlDosPathNameToNtPathName_U(v12, &Name, 0, 0) )
          {
            if ( (unsigned __int64)(*((_QWORD *)v10 + 2) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
              RtlRaiseStatus(-1073741595);
            v13 = NtCreateFile(
                    (PHANDLE)v10 + 2,
                    0x40100080u,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    0,
                    0,
                    7u,
                    3u,
                    0x60u,
                    0,
                    0);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Name.Buffer);
            if ( v13 < 0 )
            {
              v14 = (char *)*((_QWORD *)v10 + 2);
              if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                if ( NtClose(v14) < 0 )
                  __fastfail(7u);
                *((_QWORD *)v10 + 2) = 0;
              }
            }
          }
          v3 = (unsigned int *)operator new(0x890u);
          if ( v3 )
          {
            v3 = (unsigned int *)Windows::WCP::Implementation::Rtl::CBaseTracingStream::CBaseTracingStream(
                                   (Windows::WCP::Implementation::Rtl::CBaseTracingStream *)v3,
                                   (struct Windows::Rtl::IRtlOutputSink *)v10,
                                   v9);
            v9 = (_BOOL8)v3;
            if ( v3 )
            {
              *((_QWORD *)v10 + 1) = v3;
              if ( _InterlockedCompareExchange64(
                     (volatile signed __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream,
                     (signed __int64)v3,
                     0) )
              {
                (*(void (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v3 + 504LL))(v3, 1);
              }
              Windows::WCP::Implementation::Rtl::InitializeWdscore(v15);
            }
          }
        }
        if ( v7 )
          LODWORD(v3) = anonymous_namespace_::OurRtlFreeStringRoutine(v7, v8, v9);
        _InterlockedOr(v35, 0);
        g_TracingInitialized = 1;
        _InterlockedOr(v35, 0);
        v4 = Windows::WCP::Implementation::Rtl::g_TracingStream;
        goto LABEL_36;
      }
      v7 = DosPathName[1];
      Value.Buffer = (PWSTR)DosPathName[1];
      Value.Length = 0;
      Value.MaximumLength = v6;
      v5 = RtlQueryEnvironmentVariable_U(0, &Name, &Value);
    }
    else
    {
      v7 = DosPathName[1];
    }
    if ( v5 != -1073741568 )
    {
      if ( v5 >= 0 )
      {
        LOWORD(DosPathName[0]) = Value.Length;
      }
      else
      {
        IoStatusBlock.Pointer = "onecore\\internal\\base\\inc\\rtlsystemutil.h";
        IoStatusBlock.Information = (ULONG_PTR)"RtlSystemUtil::QueryNullTerminatedEnvironmentValue";
        v42 = 104;
        v43 = "Status";
        RtlReportErrorOrigination(&IoStatusBlock, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v5);
      }
    }
    goto LABEL_15;
  }
LABEL_36:
  if ( (*(_BYTE *)(&Windows::WCP::Rtl::Facility_General + 2) & 1) == 0 )
  {
    if ( v4 )
    {
      v16 = -1;
      *(&Windows::WCP::Rtl::Facility_General + 3) = 3;
      do
        ++v16;
      while ( *((_BYTE *)Src + v16) );
      v17 = v16 + 25;
      if ( v16 < 0xFFFFFFFFFFFFFFE7uLL && v17 >= v16 )
      {
        Source[0] = 0;
        if ( v16 + 32 >= v16 + 25 && v17 <= 0xF9 )
        {
          qmemcpy(Source, "WINDOWS_TRACING_FACILITY_", sizeof(Source));
          memmove(v45, Src, v16);
          *(_DWORD *)&Source[v17] = *(_DWORD *)"_FLAGS";
          *(_WORD *)&Source[v17 + 4] = *(_WORD *)"GS";
          Source[v17 + 6] = aFlags_1[6];
        }
        if ( dword_1800D2D30 )
        {
LABEL_59:
          *(&Windows::WCP::Rtl::Facility_General + 3) |= dword_1800D2D30;
          Name = 0;
          if ( !RtlCreateUnicodeStringFromAsciiz(&Name, Source) )
          {
LABEL_74:
            if ( Name.Buffer )
              anonymous_namespace_::OurRtlFreeStringRoutine(Name.Buffer, v25, v26);
            goto LABEL_84;
          }
          IoStatusBlock = (struct _IO_STATUS_BLOCK)Name;
          *(_OWORD *)DosPathName = 0;
          Value = 0;
          v27 = RtlQueryEnvironmentVariable_U(0, (PCUNICODE_STRING)&IoStatusBlock, &Value);
          if ( v27 == -1073741789 )
          {
            v28 = Value.Length + 2;
            if ( (unsigned __int16)(Value.Length + 2) < Value.Length )
            {
              v29 = DosPathName[1];
              goto LABEL_66;
            }
            if ( (int)RtlReallocateUnicodeString(0, (unsigned __int16)(Value.Length + 2), DosPathName) < 0 )
            {
              v29 = DosPathName[1];
              goto LABEL_81;
            }
            Value.MaximumLength = v28;
            v29 = DosPathName[1];
            Value.Buffer = (PWSTR)DosPathName[1];
            Value.Length = 0;
            v27 = RtlQueryEnvironmentVariable_U(0, (PCUNICODE_STRING)&IoStatusBlock, &Value);
          }
          else
          {
            v29 = DosPathName[1];
          }
          if ( v27 != -1073741568 )
          {
            if ( v27 >= 0 )
            {
              LOWORD(DosPathName[0]) = Value.Length;
            }
            else
            {
              *(_QWORD *)&ObjectAttributes.Length = "onecore\\internal\\base\\inc\\rtlsystemutil.h";
              ObjectAttributes.RootDirectory = "RtlSystemUtil::QueryNullTerminatedEnvironmentValue";
              ObjectAttributes.ObjectName = (PUNICODE_STRING)104;
              *(_QWORD *)&ObjectAttributes.Attributes = "Status";
              RtlReportErrorOrigination(
                &ObjectAttributes,
                &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab,
                (unsigned int)v27);
            }
          }
LABEL_81:
          if ( LOWORD(DosPathName[0]) )
          {
            Information_high = wcstoul(v29, 0, 16);
LABEL_72:
            *(&Windows::WCP::Rtl::Facility_General + 3) |= Information_high;
            if ( v29 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v29, v25, v26);
            goto LABEL_74;
          }
LABEL_66:
          *(_QWORD *)&Value.Length = 0;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&g_UNICODE_STRING__bslash_Registry_bslash_Machine_bslash_SOFTWARE_bslash_Microsoft_bslash_Windows_bslash_CurrentVersion_bslash_SideBySide_bslash_Tracing;
          *(_QWORD *)&ObjectAttributes.Length = 48;
          *(_QWORD *)&ObjectAttributes.Attributes = 64;
          ObjectAttributes.RootDirectory = 0;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Information_high = 0;
          if ( !NtOpenKey((PHANDLE)&Value, 0x101u, &ObjectAttributes) )
          {
            ResultLength[0] = 0;
            if ( NtQueryValueKey(
                   *(HANDLE *)&Value.Length,
                   &Name,
                   KeyValuePartialInformation,
                   &IoStatusBlock,
                   0x14u,
                   ResultLength) >= 0
              && *(PVOID *)((char *)&IoStatusBlock.Pointer + 4) == (PVOID)0x400000004LL )
            {
              Information_high = HIDWORD(IoStatusBlock.Information);
            }
          }
          v31 = *(void **)&Value.Length;
          if ( (unsigned __int64)(*(_QWORD *)&Value.Length - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            *(_QWORD *)&Value.Length = 0;
            NtClose(v31);
          }
          goto LABEL_72;
        }
        IoStatusBlock.Information = 0;
        v42 = 0;
        *(_OWORD *)DosPathName = *(_OWORD *)L"*,";
        IoStatusBlock.Pointer = 0;
        v18 = 0;
        Value = 0;
        Pointer = 0;
        v20 = RtlQueryEnvironmentVariable_U(0, (PCUNICODE_STRING)DosPathName, &Value);
        if ( v20 == -1073741789 )
        {
          v23 = Value.Length + 2;
          if ( (unsigned __int16)(Value.Length + 2) < Value.Length )
          {
LABEL_57:
            if ( v18 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v18, v21, v22);
            goto LABEL_59;
          }
          v24 = RtlReallocateLUnicodeString(0, (unsigned __int16)(Value.Length + 2), &IoStatusBlock);
          v18 = (const wchar_t *)v42;
          if ( v24 < 0 )
          {
            Pointer = IoStatusBlock.Pointer;
LABEL_55:
            if ( Pointer )
              dword_1800D2D30 = wcstoul(v18, 0, 16) & 0xFFFE | 1;
            goto LABEL_57;
          }
          Value.Length = 0;
          Value.MaximumLength = v23;
          Value.Buffer = (PWSTR)v42;
          v20 = RtlQueryEnvironmentVariable_U(0, (PCUNICODE_STRING)DosPathName, &Value);
          Pointer = IoStatusBlock.Pointer;
        }
        if ( v20 != -1073741568 )
        {
          if ( v20 >= 0 )
          {
            Pointer = (PVOID)Value.Length;
          }
          else
          {
            IoStatusBlock.Pointer = "onecore\\internal\\base\\inc\\rtlsystemutil.h";
            IoStatusBlock.Information = (ULONG_PTR)"RtlSystemUtil::QueryNullTerminatedEnvironmentValue";
            v42 = 104;
            v43 = "Status";
            RtlReportErrorOrigination(&IoStatusBlock, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v20);
          }
        }
        goto LABEL_55;
      }
    }
    else
    {
      *(&Windows::WCP::Rtl::Facility_General + 3) = 0;
    }
LABEL_84:
    v3 = &Windows::WCP::Rtl::Facility_General;
    *(&Windows::WCP::Rtl::Facility_General + 2) = 1;
    *(_QWORD *)&Windows::WCP::Rtl::Facility_General = &Windows::WCP::Rtl::Facility_General;
  }
LABEL_91:
  LOBYTE(v3) = 1;
  return (int)v3;
}

```

## disassembly

```asm
0x18001bb10  push    rbp
0x18001bb12  push    rbx
0x18001bb13  push    rsi
0x18001bb14  push    rdi
0x18001bb15  push    r12
0x18001bb17  push    r13
0x18001bb19  push    r14
0x18001bb1b  push    r15
0x18001bb1d  lea     rbp, [rsp-108h]
0x18001bb25  sub     rsp, 208h
0x18001bb2c  mov     rax, cs:__security_cookie
0x18001bb33  xor     rax, rsp
0x18001bb36  mov     [rbp+140h+var_50], rax
0x18001bb3d  test    edx, edx
0x18001bb3f  jz      loc_18001C277
0x18001bb45  cmp     edx, 1
0x18001bb48  jnz     loc_18001C2D2
0x18001bb4e  lea     rcx, ?TraceErrorOrigination@@YAXPEBU_RTL_CALL_SITE@ErrorHandling@Windows@@AEBU_GUID@@K@Z; TraceErrorOrigination(Windows::ErrorHandling::_RTL_CALL_SITE const *,_GUID const &,ulong)
0x18001bb55  call    RtlRegisterErrorOriginationCallback
0x18001bb5a  mov     rcx, cs:?g_TracingStream@Rtl@Implementation@WCP@Windows@@3PEAVCBaseTracingStream@1234@EA; Environment
0x18001bb61  lea     r12, aOnecoreInterna_6; "onecore\\internal\\base\\inc\\rtlsystem"...
0x18001bb68  xor     ebx, ebx
0x18001bb6a  lea     r13, aRtlsystemutilQ; "RtlSystemUtil::QueryNullTerminatedEnvir"...
0x18001bb71  cmp     cs:?g_TracingInitialized@@3_NA, bl; bool g_TracingInitialized
0x18001bb77  lea     r14, aStatus; "Status"
0x18001bb7e  jnz     loc_18001BEA1
0x18001bb84  test    rcx, rcx
0x18001bb87  jnz     loc_18001BEA1
0x18001bb8d  movups  xmm0, cs:xmmword_1800A3F28
0x18001bb94  mov     rax, cs:off_1800A3F38
0x18001bb9b  lea     r8, [rsp+240h+Value]; Value
0x18001bba0  movups  xmm1, cs:xmmword_1800A3EF8
0x18001bba7  mov     qword ptr cs:Src, rax
0x18001bbae  lea     rdx, [rbp+140h+Name]; Name
0x18001bbb2  mov     rax, cs:off_1800A3F40
0x18001bbb9  movups  cs:xmmword_1800D2850, xmm0
0x18001bbc0  mov     qword ptr cs:?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A, rbx; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_General
0x18001bbc7  movups  xmm0, cs:xmmword_1800A3EE8
0x18001bbce  mov     qword ptr cs:?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A+8, rbx; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_General
0x18001bbd5  movups  cs:xmmword_1800D27F0, xmm1
0x18001bbdc  mov     qword ptr cs:Src+8, rax
0x18001bbe3  movups  xmm1, cs:xmmword_1800A3EB8
0x18001bbea  movups  cs:?Facility_ComponentStore@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A, xmm0; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_ComponentStore
0x18001bbf1  movups  xmm0, xmmword ptr cs:off_1800A3F08; "COMPONENT_STORE"
0x18001bbf8  movups  cs:?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A, xmm1; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x18001bbff  movups  xmm1, xmmword ptr cs:off_1800A3ED8; "SIL"
0x18001bc06  movups  cs:xmmword_1800D2800, xmm0
0x18001bc0d  movups  xmm0, cs:xmmword_1800A3EC8
0x18001bc14  movups  cs:xmmword_1800D2830, xmm1
0x18001bc1b  movups  xmm1, xmmword ptr cs:g_UNICODE_STRING_WINDOWS_under_TRACING_under_LOGFILE; ".0"
0x18001bc22  movups  cs:xmmword_1800D2820, xmm0
0x18001bc29  xorps   xmm0, xmm0
0x18001bc2c  movups  xmmword ptr [rbp+140h+DosPathName], xmm0
0x18001bc30  movups  xmmword ptr [rsp+240h+Value.Length], xmm0
0x18001bc35  movups  xmmword ptr [rbp+140h+Name.Length], xmm1
0x18001bc39  call    cs:__imp_RtlQueryEnvironmentVariable_U
0x18001bc40  nop     dword ptr [rax+rax+00h]
0x18001bc45  cmp     eax, 0C0000023h
0x18001bc4a  jnz     short loc_18001BC9D
0x18001bc4c  movzx   eax, [rsp+240h+Value.Length]
0x18001bc51  lea     edi, [rax+2]
0x18001bc54  cmp     di, ax
0x18001bc57  jb      short loc_18001BC97
0x18001bc59  movzx   edx, di
0x18001bc5c  lea     r8, [rbp+140h+DosPathName]
0x18001bc60  xor     ecx, ecx
0x18001bc62  call    RtlReallocateUnicodeString
0x18001bc67  test    eax, eax
0x18001bc69  js      short loc_18001BC97
0x18001bc6b  mov     rsi, [rbp+140h+DosPathName+8]
0x18001bc6f  lea     r8, [rsp+240h+Value]; Value
0x18001bc74  lea     rdx, [rbp+140h+Name]; Name
0x18001bc78  mov     [rsp+240h+Value.Buffer], rsi
0x18001bc7d  xor     ecx, ecx; Environment
0x18001bc7f  mov     [rsp+240h+Value.Length], bx
0x18001bc84  mov     [rsp+240h+Value.MaximumLength], di
0x18001bc89  call    cs:__imp_RtlQueryEnvironmentVariable_U
0x18001bc90  nop     dword ptr [rax+rax+00h]
0x18001bc95  jmp     short loc_18001BCA1
0x18001bc97  mov     rsi, [rbp+140h+DosPathName+8]
0x18001bc9b  jmp     short loc_18001BCDE
0x18001bc9d  mov     rsi, [rbp+140h+DosPathName+8]
0x18001bca1  cmp     eax, 0C0000100h
0x18001bca6  jz      short loc_18001BCDE
0x18001bca8  test    eax, eax
0x18001bcaa  jns     short loc_18001BCD5
0x18001bcac  mov     r8d, eax
0x18001bcaf  mov     qword ptr [rbp+140h+IoStatusBlock], r12
0x18001bcb3  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001bcba  mov     [rbp+140h+IoStatusBlock.Information], r13
0x18001bcbe  lea     rcx, [rbp+140h+IoStatusBlock]
0x18001bcc2  mov     [rbp+140h+var_160], 68h ; 'h'
0x18001bcca  mov     [rbp+140h+var_158], r14
0x18001bcce  call    RtlReportErrorOrigination
0x18001bcd3  jmp     short loc_18001BCDE
0x18001bcd5  movzx   eax, [rsp+240h+Value.Length]
0x18001bcda  mov     word ptr [rbp+140h+DosPathName], ax
0x18001bcde  mov     ecx, 20h ; ' '; Size
0x18001bce3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bce8  mov     r14, rax
0x18001bceb  test    rax, rax
0x18001bcee  jz      loc_18001BE77
0x18001bcf4  cmp     word ptr [rbp+140h+DosPathName], bx
0x18001bcf8  lea     rax, off_1800A2198
0x18001bcff  xorps   xmm0, xmm0
0x18001bd02  mov     [r14], rax
0x18001bd05  mov     rcx, rbx
0x18001bd08  mov     [r14+8], rbx
0x18001bd0c  cmovnz  rcx, rsi; DosPathName
0x18001bd10  mov     [r14+10h], rbx
0x18001bd14  mov     [r14+18h], bl
0x18001bd18  lea     rax, [rbp+140h+Name]
0x18001bd1c  mov     qword ptr [rsp+240h+ObjectAttributes.Length], 30h ; '0'
0x18001bd25  mov     [rsp+240h+ObjectAttributes.RootDirectory], rbx
0x18001bd2a  mov     [rbp+140h+ObjectAttributes.ObjectName], rax
0x18001bd2e  mov     qword ptr [rbp+140h+ObjectAttributes.Attributes], 40h ; '@'
0x18001bd36  movups  xmmword ptr [rbp+140h+Name.Length], xmm0
0x18001bd3a  movdqu  xmmword ptr [rbp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001bd3f  movups  xmmword ptr [rbp+140h+IoStatusBlock], xmm0
0x18001bd43  test    rcx, rcx
0x18001bd46  jz      loc_18001BE28
0x18001bd4c  cmp     [rcx], bx
0x18001bd4f  jz      loc_18001BE28
0x18001bd55  xor     r9d, r9d; DirectoryInfo
0x18001bd58  lea     rdx, [rbp+140h+Name]; NtPathName
0x18001bd5c  xor     r8d, r8d; NtFileNamePart
0x18001bd5f  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18001bd66  nop     dword ptr [rax+rax+00h]
0x18001bd6b  test    al, al
0x18001bd6d  jz      loc_18001BE28
0x18001bd73  mov     rax, [r14+10h]
0x18001bd77  dec     rax
0x18001bd7a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001bd7e  ja      short loc_18001BD92
0x18001bd80  mov     ecx, 0C00000E5h; Status
0x18001bd85  call    cs:__imp_RtlRaiseStatus
0x18001bd8c  nop     dword ptr [rax+rax+00h]
0x18001bd91  int     3; Trap to Debugger
0x18001bd92  mov     [rsp+240h+EaLength], ebx; EaLength
0x18001bd96  lea     r9, [rbp+140h+IoStatusBlock]; IoStatusBlock
0x18001bd9a  mov     [rsp+240h+EaBuffer], rbx; EaBuffer
0x18001bd9f  lea     r8, [rsp+240h+ObjectAttributes]; ObjectAttributes
0x18001bda4  mov     [rsp+240h+CreateOptions], 60h ; '`'; CreateOptions
0x18001bdac  lea     rcx, [r14+10h]; FileHandle
0x18001bdb0  mov     [rsp+240h+CreateDisposition], 3; CreateDisposition
0x18001bdb8  mov     edx, 40100080h; DesiredAccess
0x18001bdbd  mov     [rsp+240h+ShareAccess], 7; ShareAccess
0x18001bdc5  mov     [rsp+240h+FileAttributes], ebx; FileAttributes
0x18001bdc9  mov     [rsp+240h+AllocationSize], rbx; AllocationSize
0x18001bdce  call    cs:__imp_NtCreateFile
0x18001bdd5  nop     dword ptr [rax+rax+00h]
0x18001bdda  mov     rcx, gs:60h
0x18001bde3  xor     edx, edx; Flags
0x18001bde5  mov     r8, [rbp+140h+Name.Buffer]; P
0x18001bde9  mov     edi, eax
0x18001bdeb  mov     rcx, [rcx+30h]; HeapHandle
0x18001bdef  call    cs:__imp_RtlFreeHeap
0x18001bdf6  nop     dword ptr [rax+rax+00h]
0x18001bdfb  test    edi, edi
0x18001bdfd  jns     short loc_18001BE28
0x18001bdff  mov     rcx, [r14+10h]; Handle
0x18001be03  lea     rax, [rcx-1]
0x18001be07  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001be0b  ja      short loc_18001BE28
0x18001be0d  call    cs:__imp_NtClose
0x18001be14  nop     dword ptr [rax+rax+00h]
0x18001be19  test    eax, eax
0x18001be1b  jns     short loc_18001BE24
0x18001be1d  mov     ecx, 7
0x18001be22  int     29h; Win8: RtlFailFast(ecx)
0x18001be24  mov     [r14+10h], rbx
0x18001be28  mov     ecx, 890h; Size
0x18001be2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001be32  test    rax, rax
0x18001be35  jz      short loc_18001BE77
0x18001be37  mov     rdx, r14; struct Windows::Rtl::IRtlOutputSink *
0x18001be3a  mov     rcx, rax; this
0x18001be3d  call    ??0CBaseTracingStream@Rtl@Implementation@WCP@Windows@@QEAA@PEAUIRtlOutputSink@14@_N@Z; Windows::WCP::Implementation::Rtl::CBaseTracingStream::CBaseTracingStream(Windows::Rtl::IRtlOutputSink *,bool)
0x18001be42  mov     r8, rax
0x18001be45  test    rax, rax
0x18001be48  jz      short loc_18001BE77
0x18001be4a  mov     [r14+8], rax
0x18001be4e  xor     eax, eax
0x18001be50  lock cmpxchg cs:?g_TracingStream@Rtl@Implementation@WCP@Windows@@3PEAVCBaseTracingStream@1234@EA, r8; Windows::WCP::Implementation::Rtl::CBaseTracingStream * Windows::WCP::Implementation::Rtl::g_TracingStream
0x18001be59  jz      short loc_18001BE72
0x18001be5b  mov     rcx, [r8]
0x18001be5e  mov     edx, 1
0x18001be63  mov     rax, [rcx+1F8h]
0x18001be6a  mov     rcx, r8
0x18001be6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be72  call    ?InitializeWdscore@Rtl@Implementation@WCP@Windows@@YAXXZ; Windows::WCP::Implementation::Rtl::InitializeWdscore(void)
0x18001be77  test    rsi, rsi
0x18001be7a  jz      short loc_18001BE84
0x18001be7c  mov     rcx, rsi
0x18001be7f  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001be84  lea     r14, aStatus; "Status"
0x18001be8b  lock or [rsp+240h+var_240], ebx
0x18001be8f  mov     cs:?g_TracingInitialized@@3_NA, 1; bool g_TracingInitialized
0x18001be96  lock or [rsp+240h+var_240], ebx
0x18001be9a  mov     rcx, cs:?g_TracingStream@Rtl@Implementation@WCP@Windows@@3PEAVCBaseTracingStream@1234@EA; Windows::WCP::Implementation::Rtl::CBaseTracingStream * Windows::WCP::Implementation::Rtl::g_TracingStream
0x18001bea1  test    byte ptr cs:?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A+8, 1; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_General
0x18001bea8  jnz     loc_18001C2D2
0x18001beae  test    rcx, rcx
0x18001beb1  jz      loc_18001C257
0x18001beb7  mov     rdx, qword ptr cs:Src; Src
0x18001bebe  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001bec5  mov     dword ptr cs:?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A+0Ch, 3; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_General
0x18001becf  nop
0x18001bed0  inc     r8; Size
0x18001bed3  cmp     [rdx+r8], bl
0x18001bed7  jnz     short loc_18001BED0
0x18001bed9  lea     rdi, [r8+19h]
0x18001bedd  cmp     rdi, 19h
0x18001bee1  jb      loc_18001C25D
0x18001bee7  cmp     rdi, r8
0x18001beea  jb      loc_18001C25D
0x18001bef0  lea     rax, [rdi+7]
0x18001bef4  mov     [rbp+140h+Source], bl
0x18001bef7  cmp     rax, rdi
0x18001befa  jb      short loc_18001BF4B
0x18001befc  cmp     rdi, 0F9h
0x18001bf03  ja      short loc_18001BF4B
0x18001bf05  movups  xmm0, xmmword ptr cs:aWindowsTracing+1; "INDOWS_TRACING_FACILITY_"
0x18001bf0c  lea     rcx, [rbp+140h+var_137]; void *
0x18001bf10  mov     [rbp+140h+Source], 57h ; 'W'
0x18001bf14  movsd   xmm1, qword ptr cs:aWindowsTracing+11h; "ACILITY_"
0x18001bf1c  movups  xmmword ptr [rbp+140h+Source+1], xmm0
0x18001bf20  movsd   [rbp+140h+var_13F], xmm1
0x18001bf25  call    memmove
0x18001bf2a  mov     eax, dword ptr cs:aFlags_1; "_FLAGS"
0x18001bf30  mov     dword ptr [rbp+rdi+140h+Source], eax
0x18001bf34  movzx   eax, word ptr cs:aFlags_1+4; "GS"
0x18001bf3b  mov     [rbp+rdi+140h+var_14C], ax
0x18001bf40  movzx   eax, byte ptr cs:aFlags_1+6; ""
0x18001bf47  mov     [rbp+rdi+140h+var_14A], al
0x18001bf4b  cmp     cs:dword_1800D2D30, ebx
0x18001bf51  jnz     loc_18001C05A
0x18001bf57  movups  xmm0, xmmword ptr cs:g_UNICODE_STRING_WINDOWS_under_TRACING_under_FLAGS; "*,"
0x18001bf5e  lea     r8, [rsp+240h+Value]; Value
0x18001bf63  mov     [rbp+140h+IoStatusBlock.Information], rbx
0x18001bf67  lea     rdx, [rbp+140h+DosPathName]; Name
0x18001bf6b  mov     [rbp+140h+var_160], rbx
0x18001bf6f  movups  xmmword ptr [rbp+140h+DosPathName], xmm0
0x18001bf73  mov     qword ptr [rbp+140h+IoStatusBlock], rbx
0x18001bf77  xor     ecx, ecx; Environment
0x18001bf79  xorps   xmm0, xmm0
0x18001bf7c  mov     rdi, rbx
0x18001bf7f  movups  xmmword ptr [rsp+240h+Value.Length], xmm0
0x18001bf84  mov     rsi, rbx
0x18001bf87  call    cs:__imp_RtlQueryEnvironmentVariable_U
0x18001bf8e  nop     dword ptr [rax+rax+00h]
0x18001bf93  cmp     eax, 0C0000023h
0x18001bf98  jnz     short loc_18001BFEB
0x18001bf9a  movzx   eax, [rsp+240h+Value.Length]
0x18001bf9f  lea     esi, [rax+2]
0x18001bfa2  cmp     si, ax
0x18001bfa5  jb      loc_18001C04D
0x18001bfab  movzx   edx, si
0x18001bfae  lea     r8, [rbp+140h+IoStatusBlock]
0x18001bfb2  xor     ecx, ecx
0x18001bfb4  call    RtlReallocateLUnicodeString
0x18001bfb9  mov     rdi, [rbp+140h+var_160]
0x18001bfbd  test    eax, eax
0x18001bfbf  js      short loc_18001C01F
0x18001bfc1  lea     r8, [rsp+240h+Value]; Value
0x18001bfc6  mov     [rsp+240h+Value.Length], bx
0x18001bfcb  lea     rdx, [rbp+140h+DosPathName]; Name
0x18001bfcf  mov     [rsp+240h+Value.MaximumLength], si
0x18001bfd4  xor     ecx, ecx; Environment
0x18001bfd6  mov     [rsp+240h+Value.Buffer], rdi
0x18001bfdb  call    cs:__imp_RtlQueryEnvironmentVariable_U
0x18001bfe2  nop     dword ptr [rax+rax+00h]
0x18001bfe7  mov     rsi, qword ptr [rbp+140h+IoStatusBlock]
0x18001bfeb  cmp     eax, 0C0000100h
0x18001bff0  jz      short loc_18001C02A
0x18001bff2  test    eax, eax
0x18001bff4  jns     short loc_18001C025
0x18001bff6  mov     r8d, eax
0x18001bff9  mov     qword ptr [rbp+140h+IoStatusBlock], r12
0x18001bffd  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001c004  mov     [rbp+140h+IoStatusBlock.Information], r13
0x18001c008  lea     rcx, [rbp+140h+IoStatusBlock]
0x18001c00c  mov     [rbp+140h+var_160], 68h ; 'h'
0x18001c014  mov     [rbp+140h+var_158], r14
0x18001c018  call    RtlReportErrorOrigination
0x18001c01d  jmp     short loc_18001C02A
0x18001c01f  mov     rsi, qword ptr [rbp+140h+IoStatusBlock]
0x18001c023  jmp     short loc_18001C02A
0x18001c025  movzx   esi, [rsp+240h+Value.Length]
0x18001c02a  test    rsi, rsi
0x18001c02d  jz      short loc_18001C04D
0x18001c02f  xor     edx, edx; EndPtr
0x18001c031  mov     r8d, 10h; Radix
0x18001c037  mov     rcx, rdi; String
0x18001c03a  call    wcstoul
0x18001c03f  and     eax, 0FFFEh
0x18001c044  or      eax, 1
0x18001c047  mov     cs:dword_1800D2D30, eax
0x18001c04d  test    rdi, rdi
0x18001c050  jz      short loc_18001C05A
  ... truncated ...
```
