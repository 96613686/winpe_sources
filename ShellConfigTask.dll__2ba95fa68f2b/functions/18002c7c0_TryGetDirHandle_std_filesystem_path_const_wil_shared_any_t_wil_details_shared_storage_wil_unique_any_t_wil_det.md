# TryGetDirHandle(std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)

- ea: `0x18002c7c0`
- end: `0x18002cbcc`
- name: `?TryGetDirHandle@@YAJAEBVpath@filesystem@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `1036`
- prototype: `__int64 __fastcall(struct std::filesystem::path *, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029644`
- `0x1800299f4`

## callees

- `0x1800086c4`
- `0x18002062c`
- `0x1800284fc`
- `0x1800285f0`
- `0x180029348`
- `0x18002c7c0`
- `0x18002e27c`
- `0x18002ef10`
- `0x180033010`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18002c8cc`
- `ntdll!NtCreateFile` at `0x18002ca51`
- `ntdll!NtCreateFile` at `0x18002c8cc`
- `ntdll!NtCreateFile` at `0x18002ca51`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002c80b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002c80b`
- `ntdll!RtlFreeHeap` at `0x18002c830`
- `ntdll!RtlFreeHeap` at `0x18002c937`
- `ntdll!RtlFreeHeap` at `0x18002cb2a`
- `ntdll!RtlFreeHeap` at `0x18002cbbf`
- `ntdll!RtlFreeHeap` at `0x18002c830`
- `ntdll!RtlFreeHeap` at `0x18002c937`
- `ntdll!RtlFreeHeap` at `0x18002cb2a`
- `ntdll!RtlFreeHeap` at `0x18002cbbf`

## string_xrefs

- `0x18002c977`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002cac0`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall TryGetDirHandle(struct std::filesystem::path *a1, _QWORD *a2)
{
  const struct std::filesystem::path *v3; // rbx
  char IsEnabled; // al
  void **v6; // rax
  NTSTATUS v7; // eax
  int v8; // edx
  unsigned int v9; // esi
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rsi
  WCHAR *v12; // rcx
  int matched; // eax
  volatile signed __int32 *v14; // rdi
  __int64 v15; // r14
  volatile signed __int32 *v16; // rsi
  signed __int32 v17; // eax
  void **v18; // rax
  NTSTATUS v19; // esi
  _QWORD *v20; // rdi
  WCHAR *v21; // rcx
  int v22; // eax
  volatile signed __int32 *v23; // rdi
  int AllocationSize; // [rsp+20h] [rbp-79h]
  int AllocationSizea; // [rsp+20h] [rbp-79h]
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-39h] BYREF
  __int128 v27; // [rsp+70h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING *p_NtPathName; // [rsp+90h] [rbp-9h]
  char v30; // [rsp+98h] [rbp-1h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  bool v33; // [rsp+100h] [rbp+67h] BYREF

  v3 = a1;
  NtPathName = 0;
  p_NtPathName = &NtPathName;
  v30 = 1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(struct std::filesystem::path **)a1;
  if ( !RtlDosPathNameToNtPathName_U((PCWSTR)a1, &NtPathName, 0, 0) )
  {
    if ( NtPathName.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    return 2147942403LL;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl'::`2'::impl);
  v27 = 0;
  if ( IsEnabled )
  {
    v6 = (void **)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::operator&(&v27);
    v7 = NtCreateFile(v6, 0x1000A1u, &ObjectAttributes, &IoStatusBlock, 0, 0x10u, 7u, 1u, 0x21u, 0, 0);
    if ( v7 < 0 )
    {
      v9 = wil::details::NtStatusToHr((wil::details *)(unsigned int)v7, v8);
      v10 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
      if ( *((_QWORD *)&v27 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        goto LABEL_11;
      }
      goto LABEL_13;
    }
    v11 = v27;
    if ( !(_QWORD)v27 )
      goto LABEL_39;
    v12 = *(WCHAR **)v27;
    if ( ((*(_QWORD *)v27 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      goto LABEL_39;
    v33 = 0;
    matched = DoesExpectedPathMatchFinalPath(v12, v3, &v33);
    if ( matched < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
        (const char *)(unsigned int)matched,
        AllocationSize);
      goto LABEL_39;
    }
    if ( v33 )
    {
      v14 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
      if ( *((_QWORD *)&v27 + 1) )
      {
        v15 = *((_QWORD *)&v27 + 1) + 8LL;
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL));
      }
      else
      {
        v15 = 8;
      }
      *a2 = v11;
      v16 = (volatile signed __int32 *)a2[1];
      a2[1] = v14;
      if ( v16 )
      {
        if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      if ( !v14 )
        goto LABEL_52;
      v17 = _InterlockedExchangeAdd((volatile signed __int32 *)v15, 0xFFFFFFFF);
      goto LABEL_49;
    }
LABEL_39:
    v23 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
    if ( *((_QWORD *)&v27 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    if ( NtPathName.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    return 2147942406LL;
  }
  v18 = (void **)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::operator&(&v27);
  v19 = NtCreateFile(v18, 0x100081u, &ObjectAttributes, &IoStatusBlock, 0, 0x10u, 7u, 1u, 0x21u, 0, 0);
  if ( v19 < 0 )
  {
    v9 = v19 | 0x10000000;
    v10 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
    if ( *((_QWORD *)&v27 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
LABEL_11:
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
LABEL_13:
    if ( NtPathName.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    return v9;
  }
  v20 = (_QWORD *)v27;
  if ( !(_QWORD)v27 )
    goto LABEL_39;
  v21 = *(WCHAR **)v27;
  if ( (unsigned __int64)(*(_QWORD *)v27 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_39;
  v33 = 0;
  v22 = DoesExpectedPathMatchFinalPath(v21, v3, &v33);
  if ( v22 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)(unsigned int)v22,
      AllocationSizea);
    goto LABEL_39;
  }
  if ( !v33 )
    goto LABEL_39;
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
    a2,
    *v20);
  v14 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
  if ( *((_QWORD *)&v27 + 1) )
  {
    v17 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL), 0xFFFFFFFF);
LABEL_49:
    if ( v17 == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
LABEL_52:
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  return 0;
}

```

## disassembly

```asm
0x18002c7c0  mov     [rsp-8+arg_8], rbx
0x18002c7c5  mov     [rsp-8+arg_10], rsi
0x18002c7ca  push    rbp
0x18002c7cb  push    rdi
0x18002c7cc  push    r12
0x18002c7ce  push    r14
0x18002c7d0  push    r15
0x18002c7d2  lea     rbp, [rsp-37h]
0x18002c7d7  sub     rsp, 0D0h
0x18002c7de  mov     r15, rdx
0x18002c7e1  mov     rbx, rcx
0x18002c7e4  xorps   xmm0, xmm0
0x18002c7e7  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x18002c7eb  lea     rax, [rbp+57h+NtPathName]
0x18002c7ef  mov     [rbp+57h+var_60], rax
0x18002c7f3  mov     [rbp+57h+var_58], 1
0x18002c7f7  cmp     qword ptr [rcx+18h], 7
0x18002c7fc  jbe     short loc_18002C801
0x18002c7fe  mov     rcx, [rcx]; DosPathName
0x18002c801  xor     r9d, r9d; DirectoryInfo
0x18002c804  xor     r8d, r8d; NtFileNamePart
0x18002c807  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18002c80b  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18002c811  xor     r12d, r12d
0x18002c814  test    al, al
0x18002c816  jnz     short loc_18002C840
0x18002c818  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x18002c81c  test    r8, r8
0x18002c81f  jz      short loc_18002C836
0x18002c821  mov     rcx, gs:60h
0x18002c82a  xor     edx, edx; Flags
0x18002c82c  mov     rcx, [rcx+30h]; HeapHandle
0x18002c830  call    cs:__imp_RtlFreeHeap
0x18002c836  mov     eax, 80070003h
0x18002c83b  jmp     loc_18002CB35
0x18002c840  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002c848  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002c850  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18002c854  lea     rax, [rbp+57h+NtPathName]
0x18002c858  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002c85c  xorps   xmm0, xmm0
0x18002c85f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c864  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002c868  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59302972@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972> `wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl(void)'::`2'::impl
0x18002c86f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(void)
0x18002c874  xorps   xmm1, xmm1
0x18002c877  movdqu  [rbp+57h+var_80], xmm1
0x18002c87c  test    al, al
0x18002c87e  jz      loc_18002CA09
0x18002c884  lea     rcx, [rbp+57h+var_80]
0x18002c888  call    ??I?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>::operator&(void)
0x18002c88d  mov     rcx, rax; FileHandle
0x18002c890  mov     [rsp+0F0h+EaLength], r12d; EaLength
0x18002c895  mov     [rsp+0F0h+EaBuffer], r12; EaBuffer
0x18002c89a  mov     [rsp+0F0h+CreateOptions], 21h ; '!'; CreateOptions
0x18002c8a2  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x18002c8aa  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x18002c8b2  mov     [rsp+0F0h+FileAttributes], 10h; FileAttributes
0x18002c8ba  mov     [rsp+0F0h+AllocationSize], r12; int
0x18002c8bf  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002c8c3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002c8c7  mov     edx, 1000A1h; DesiredAccess
0x18002c8cc  call    cs:__imp_NtCreateFile
0x18002c8d2  test    eax, eax
0x18002c8d4  jns     short loc_18002C944
0x18002c8d6  mov     ecx, eax; this
0x18002c8d8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18002c8dd  mov     esi, eax
0x18002c8df  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x18002c8e3  test    rdi, rdi
0x18002c8e6  jz      short loc_18002C91F
0x18002c8e8  or      ebx, 0FFFFFFFFh
0x18002c8eb  mov     ecx, ebx
0x18002c8ed  lock xadd [rdi+8], ecx
0x18002c8f2  add     ecx, ebx
0x18002c8f4  jnz     short loc_18002C91F
0x18002c8f6  mov     rdx, [rdi]
0x18002c8f9  mov     rax, [rdx]
0x18002c8fc  mov     rcx, rdi
0x18002c8ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c904  mov     eax, ebx
0x18002c906  lock xadd [rdi+0Ch], eax
0x18002c90b  add     eax, ebx
0x18002c90d  jnz     short loc_18002C91F
0x18002c90f  mov     rax, [rdi]
0x18002c912  mov     rcx, rdi
0x18002c915  mov     rax, [rax+8]
0x18002c919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c91e  nop
0x18002c91f  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x18002c923  test    r8, r8
0x18002c926  jz      short loc_18002C93D
0x18002c928  mov     rcx, gs:60h
0x18002c931  xor     edx, edx; Flags
0x18002c933  mov     rcx, [rcx+30h]; HeapHandle
0x18002c937  call    cs:__imp_RtlFreeHeap
0x18002c93d  mov     eax, esi
0x18002c93f  jmp     loc_18002CB35
0x18002c944  mov     rsi, qword ptr [rbp+57h+var_80]
0x18002c948  test    rsi, rsi
0x18002c94b  jz      short loc_18002C989
0x18002c94d  mov     rcx, [rsi]; void *
0x18002c950  lea     rax, [rcx+1]
0x18002c954  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002c95a  jz      short loc_18002C989
0x18002c95c  mov     [rbp+57h+arg_0], r12b
0x18002c960  lea     r8, [rbp+57h+arg_0]; bool *
0x18002c964  mov     rdx, rbx; struct std::filesystem::path *
0x18002c967  call    ?DoesExpectedPathMatchFinalPath@@YAJPEAXAEBVpath@filesystem@std@@PEA_N@Z; DoesExpectedPathMatchFinalPath(void *,std::filesystem::path const &,bool *)
0x18002c96c  mov     rcx, [rbp+5Fh]; this
0x18002c970  test    eax, eax
0x18002c972  jns     short loc_18002C98E
0x18002c974  mov     r9d, eax; char *
0x18002c977  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002c97e  mov     edx, 106h; void *
0x18002c983  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c988  nop
0x18002c989  jmp     loc_18002CAD2
0x18002c98e  cmp     [rbp+57h+arg_0], r12b
0x18002c992  jz      short loc_18002C989
0x18002c994  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x18002c998  test    rdi, rdi
0x18002c99b  jz      short loc_18002C9A7
0x18002c99d  lea     r14, [rdi+8]
0x18002c9a1  lock inc dword ptr [r14]
0x18002c9a5  jmp     short loc_18002C9AD
0x18002c9a7  mov     r14d, 8
0x18002c9ad  mov     [r15], rsi
0x18002c9b0  mov     rsi, [r15+8]
0x18002c9b4  mov     [r15+8], rdi
0x18002c9b8  or      ebx, 0FFFFFFFFh
0x18002c9bb  test    rsi, rsi
0x18002c9be  jz      short loc_18002C9F4
0x18002c9c0  mov     eax, ebx
0x18002c9c2  lock xadd [rsi+8], eax
0x18002c9c7  add     eax, ebx
0x18002c9c9  jnz     short loc_18002C9F4
0x18002c9cb  mov     rax, [rsi]
0x18002c9ce  mov     rcx, rsi
0x18002c9d1  mov     rax, [rax]
0x18002c9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9d9  mov     eax, ebx
0x18002c9db  lock xadd [rsi+0Ch], eax
0x18002c9e0  add     eax, ebx
0x18002c9e2  jnz     short loc_18002C9F4
0x18002c9e4  mov     rax, [rsi]
0x18002c9e7  mov     rcx, rsi
0x18002c9ea  mov     rax, [rax+8]
0x18002c9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9f3  nop
0x18002c9f4  test    rdi, rdi
0x18002c9f7  jz      loc_18002CBA7
0x18002c9fd  mov     eax, ebx
0x18002c9ff  lock xadd [r14], eax
0x18002ca04  jmp     loc_18002CB7A
0x18002ca09  lea     rcx, [rbp+57h+var_80]
0x18002ca0d  call    ??I?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>::operator&(void)
0x18002ca12  mov     rcx, rax; FileHandle
0x18002ca15  mov     [rsp+0F0h+EaLength], r12d; EaLength
0x18002ca1a  mov     [rsp+0F0h+EaBuffer], r12; EaBuffer
0x18002ca1f  mov     [rsp+0F0h+CreateOptions], 21h ; '!'; CreateOptions
0x18002ca27  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x18002ca2f  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x18002ca37  mov     [rsp+0F0h+FileAttributes], 10h; FileAttributes
0x18002ca3f  mov     [rsp+0F0h+AllocationSize], r12; int
0x18002ca44  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002ca48  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002ca4c  mov     edx, 100081h; DesiredAccess
0x18002ca51  call    cs:__imp_NtCreateFile
0x18002ca57  mov     esi, eax
0x18002ca59  test    eax, eax
0x18002ca5b  jns     short loc_18002CA8B
0x18002ca5d  bts     esi, 1Ch
0x18002ca61  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x18002ca65  test    rdi, rdi
0x18002ca68  jz      loc_18002C91F
0x18002ca6e  or      ebx, 0FFFFFFFFh
0x18002ca71  mov     ecx, ebx
0x18002ca73  lock xadd [rdi+8], ecx
0x18002ca78  add     ecx, ebx
0x18002ca7a  jnz     loc_18002C91F
0x18002ca80  mov     rax, [rdi]
0x18002ca83  mov     rax, [rax]
0x18002ca86  jmp     loc_18002C8FC
0x18002ca8b  mov     rdi, qword ptr [rbp+57h+var_80]
0x18002ca8f  test    rdi, rdi
0x18002ca92  jz      short loc_18002CAD2
0x18002ca94  mov     rcx, [rdi]; void *
0x18002ca97  lea     rax, [rcx-1]
0x18002ca9b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ca9f  ja      short loc_18002CAD2
0x18002caa1  mov     [rbp+57h+arg_0], r12b
0x18002caa5  lea     r8, [rbp+57h+arg_0]; bool *
0x18002caa9  mov     rdx, rbx; struct std::filesystem::path *
0x18002caac  call    ?DoesExpectedPathMatchFinalPath@@YAJPEAXAEBVpath@filesystem@std@@PEA_N@Z; DoesExpectedPathMatchFinalPath(void *,std::filesystem::path const &,bool *)
0x18002cab1  mov     rcx, [rbp+5Fh]; this
0x18002cab5  test    eax, eax
0x18002cab7  jns     loc_18002CB51
0x18002cabd  mov     r9d, eax; char *
0x18002cac0  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002cac7  mov     edx, 129h; void *
0x18002cacc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002cad1  nop
0x18002cad2  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x18002cad6  test    rdi, rdi
0x18002cad9  jz      short loc_18002CB12
0x18002cadb  or      ebx, 0FFFFFFFFh
0x18002cade  mov     eax, ebx
0x18002cae0  lock xadd [rdi+8], eax
0x18002cae5  add     eax, ebx
0x18002cae7  jnz     short loc_18002CB12
0x18002cae9  mov     rax, [rdi]
0x18002caec  mov     rcx, rdi
0x18002caef  mov     rax, [rax]
0x18002caf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002caf7  mov     eax, ebx
0x18002caf9  lock xadd [rdi+0Ch], eax
0x18002cafe  add     eax, ebx
0x18002cb00  jnz     short loc_18002CB12
0x18002cb02  mov     rax, [rdi]
0x18002cb05  mov     rcx, rdi
0x18002cb08  mov     rax, [rax+8]
0x18002cb0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb11  nop
0x18002cb12  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x18002cb16  test    r8, r8
0x18002cb19  jz      short loc_18002CB30
0x18002cb1b  mov     rcx, gs:60h
0x18002cb24  xor     edx, edx; Flags
0x18002cb26  mov     rcx, [rcx+30h]; HeapHandle
0x18002cb2a  call    cs:__imp_RtlFreeHeap
0x18002cb30  mov     eax, 80070006h
0x18002cb35  lea     r11, [rsp+0F0h+var_20]
0x18002cb3d  mov     rbx, [r11+38h]
0x18002cb41  mov     rsi, [r11+40h]
0x18002cb45  mov     rsp, r11
0x18002cb48  pop     r15
0x18002cb4a  pop     r14
0x18002cb4c  pop     r12
0x18002cb4e  pop     rdi
0x18002cb4f  pop     rbp
0x18002cb50  retn
0x18002cb51  cmp     [rbp+57h+arg_0], r12b
0x18002cb55  jz      loc_18002CAD2
0x18002cb5b  mov     rdx, [rdi]
0x18002cb5e  mov     rcx, r15
0x18002cb61  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18002cb66  nop
0x18002cb67  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x18002cb6b  test    rdi, rdi
0x18002cb6e  jz      short loc_18002CBA7
0x18002cb70  or      ebx, 0FFFFFFFFh
0x18002cb73  mov     eax, ebx
0x18002cb75  lock xadd [rdi+8], eax
0x18002cb7a  add     eax, ebx
0x18002cb7c  jnz     short loc_18002CBA7
0x18002cb7e  mov     rax, [rdi]
0x18002cb81  mov     rcx, rdi
0x18002cb84  mov     rax, [rax]
0x18002cb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb8c  mov     eax, ebx
0x18002cb8e  lock xadd [rdi+0Ch], eax
0x18002cb93  add     eax, ebx
0x18002cb95  jnz     short loc_18002CBA7
0x18002cb97  mov     rax, [rdi]
0x18002cb9a  mov     rcx, rdi
0x18002cb9d  mov     rax, [rax+8]
0x18002cba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cba6  nop
0x18002cba7  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x18002cbab  test    r8, r8
0x18002cbae  jz      short loc_18002CBC5
0x18002cbb0  mov     rcx, gs:60h
0x18002cbb9  xor     edx, edx; Flags
0x18002cbbb  mov     rcx, [rcx+30h]; HeapHandle
0x18002cbbf  call    cs:__imp_RtlFreeHeap
0x18002cbc5  xor     eax, eax
0x18002cbc7  jmp     loc_18002CB35
```
