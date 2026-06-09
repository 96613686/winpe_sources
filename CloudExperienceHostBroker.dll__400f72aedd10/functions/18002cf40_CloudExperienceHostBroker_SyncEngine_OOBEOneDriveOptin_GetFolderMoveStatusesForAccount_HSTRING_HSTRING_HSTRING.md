# CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::GetFolderMoveStatusesForAccount(HSTRING__ *,HSTRING__ *,HSTRING__ *,uint *,CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry * *)

- ea: `0x18002cf40`
- end: `0x18002d10b`
- name: `?GetFolderMoveStatusesForAccount@OOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@UEAAJPEAUHSTRING__@@00PEAIPEAPEAUOneDriveKnownFolderMoveStatusEntry@23@@Z`
- size: `459`
- prototype: `int(CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *__hidden this, HSTRING, HSTRING, HSTRING, unsigned int *, struct CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180004760`
- `0x180007df0`
- `0x180008344`
- `0x18002cf40`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cfd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cfdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cfee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cfd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cfdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cfee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d0df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d0df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d07d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d07d`

## string_xrefs

- `0x18002cf90`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002d03b`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::GetFolderMoveStatusesForAccount(
        const struct _GUID *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        unsigned int *a5,
        struct CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry **a6)
{
  unsigned int *v8; // r15
  struct CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry **v9; // r12
  int OOBEUserObjectForceBroker; // eax
  unsigned int v11; // ebx
  unsigned int *v12; // r14
  __int64 (__fastcall *v13)(unsigned int *, PCWSTR, PCWSTR, PCWSTR); // rsi
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v15; // rbx
  PCWSTR v16; // rax
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  unsigned __int64 v20; // rbx
  struct CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry *v21; // r8
  unsigned int i; // r9d
  __int64 v23; // rdx
  int v25; // [rsp+20h] [rbp-48h]
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp-20h]
  LPVOID *p_pv; // [rsp+50h] [rbp-18h]
  int v29; // [rsp+58h] [rbp-10h] BYREF
  char v30; // [rsp+5Ch] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v8 = a5;
  *a5 = 0;
  v9 = a6;
  *a6 = 0;
  a5 = 0;
  OOBEUserObjectForceBroker = CloudExperienceHostCreateOOBEUserObjectForceBroker(
                                this,
                                &GUID_5a1b2c3d_4e5f_6789_abcd_ef0123456789,
                                (void **)&a5);
  v11 = OOBEUserObjectForceBroker;
  if ( OOBEUserObjectForceBroker < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)OOBEUserObjectForceBroker,
      v25);
    goto LABEL_18;
  }
  pv = 0;
  v27 = 0;
  v12 = a5;
  v13 = *(__int64 (__fastcall **)(unsigned int *, PCWSTR, PCWSTR, PCWSTR))(*(_QWORD *)a5 + 56LL);
  p_pv = &pv;
  v29 = 0;
  v30 = 1;
  StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
  v15 = WindowsGetStringRawBuffer(a3, 0);
  v16 = WindowsGetStringRawBuffer(a2, 0);
  v17 = v13(v12, v16, v15, StringRawBuffer);
  v11 = v17;
  if ( v30 )
    p_pv[1] = (LPVOID)(unsigned int)v29;
  if ( v17 < 0 )
  {
    v18 = (unsigned int)v17;
    v19 = 519;
    goto LABEL_7;
  }
  v20 = v27;
  if ( v27 )
  {
    v21 = (struct CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry *)CoTaskMemAlloc(20 * v27);
    if ( !v21 )
    {
      v11 = -2147024882;
      v18 = 2147942414LL;
      v19 = 530;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
        (const char *)v18,
        (int)&v29);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
        v27 = 0;
      }
      goto LABEL_18;
    }
    for ( i = 0; i < v20; ++i )
    {
      v23 = 5LL * i;
      *(_OWORD *)((char *)v21 + 4 * v23) = *(_OWORD *)((char *)pv + 20 * i);
      *((_DWORD *)v21 + v23 + 4) = *((_DWORD *)pv + 5 * i + 4);
    }
    *v8 = v20;
    *v9 = v21;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    v27 = 0;
    pv = 0;
  }
  v11 = 0;
LABEL_18:
  wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&a5);
  return v11;
}

```

## disassembly

```asm
0x18002cf40  mov     [rsp-40h+string], rdx
0x18002cf45  push    rbp
0x18002cf46  push    rbx
0x18002cf47  push    rsi
0x18002cf48  push    rdi
0x18002cf49  push    r12
0x18002cf4b  push    r13
0x18002cf4d  push    r14
0x18002cf4f  push    r15
0x18002cf51  mov     rbp, rsp
0x18002cf54  sub     rsp, 68h
0x18002cf58  mov     rdi, r9
0x18002cf5b  mov     r13, r8
0x18002cf5e  xor     esi, esi
0x18002cf60  mov     r15, [rbp+arg_20]
0x18002cf64  mov     [r15], esi
0x18002cf67  mov     r12, [rbp+arg_28]
0x18002cf6b  mov     [r12], rsi
0x18002cf6f  mov     [rbp+arg_20], rsi
0x18002cf73  lea     r8, [rbp+arg_20]; void **
0x18002cf77  lea     rdx, _GUID_5a1b2c3d_4e5f_6789_abcd_ef0123456789; struct _GUID *
0x18002cf7e  call    ?CloudExperienceHostCreateOOBEUserObjectForceBroker@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateOOBEUserObjectForceBroker(_GUID const &,_GUID const &,void * *)
0x18002cf83  mov     ebx, eax
0x18002cf85  test    eax, eax
0x18002cf87  jns     short loc_18002CFA6
0x18002cf89  mov     rcx, [rbp+40h]; this
0x18002cf8d  mov     r9d, eax; char *
0x18002cf90  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002cf97  mov     edx, 1FEh; void *
0x18002cf9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cfa1  jmp     loc_18002D0EF
0x18002cfa6  mov     [rbp+pv], rsi
0x18002cfaa  mov     [rbp+var_20], rsi
0x18002cfae  mov     r14, [rbp+arg_20]
0x18002cfb2  mov     rax, [r14]
0x18002cfb5  mov     rsi, [rax+38h]
0x18002cfb9  lea     rax, [rbp+pv]
0x18002cfbd  mov     [rbp+var_18], rax
0x18002cfc1  mov     [rbp+var_10], 0
0x18002cfc8  mov     [rbp+var_C], 1
0x18002cfcc  xor     edx, edx; length
0x18002cfce  mov     rcx, rdi; string
0x18002cfd1  call    cs:__imp_WindowsGetStringRawBuffer
0x18002cfd7  mov     rdi, rax
0x18002cfda  xor     edx, edx; length
0x18002cfdc  mov     rcx, r13; string
0x18002cfdf  call    cs:__imp_WindowsGetStringRawBuffer
0x18002cfe5  mov     rbx, rax
0x18002cfe8  xor     edx, edx; length
0x18002cfea  mov     rcx, [rbp+string]; string
0x18002cfee  call    cs:__imp_WindowsGetStringRawBuffer
0x18002cff4  lea     rcx, [rbp+pv]
0x18002cff8  mov     [rsp+68h+var_40], rcx
0x18002cffd  lea     rcx, [rbp+var_10]
0x18002d001  mov     qword ptr [rsp+68h+var_48], rcx; int
0x18002d006  mov     r9, rdi
0x18002d009  mov     r8, rbx
0x18002d00c  mov     rdx, rax
0x18002d00f  mov     rcx, r14
0x18002d012  mov     rax, rsi
0x18002d015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d01a  mov     ebx, eax
0x18002d01c  xor     edi, edi
0x18002d01e  cmp     [rbp+var_C], dil
0x18002d022  jz      short loc_18002D02F
0x18002d024  mov     edx, [rbp+var_10]
0x18002d027  mov     rcx, [rbp+var_18]
0x18002d02b  mov     [rcx+8], rdx
0x18002d02f  test    eax, eax
0x18002d031  jns     short loc_18002D06C
0x18002d033  mov     r9d, eax; char *
0x18002d036  mov     edx, 207h; void *
0x18002d03b  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002d042  mov     rcx, [rbp+40h]; this
0x18002d046  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d04b  nop
0x18002d04c  mov     rcx, [rbp+pv]; pv
0x18002d050  test    rcx, rcx
0x18002d053  jz      loc_18002D0EF
0x18002d059  call    cs:__imp_CoTaskMemFree
0x18002d05f  mov     [rbp+pv], rdi
0x18002d063  mov     [rbp+var_20], rdi
0x18002d067  jmp     loc_18002D0EF
0x18002d06c  mov     rbx, [rbp+var_20]
0x18002d070  test    rbx, rbx
0x18002d073  jz      short loc_18002D0D6
0x18002d075  lea     rcx, [rbx+rbx*4]
0x18002d079  shl     rcx, 2; cb
0x18002d07d  call    cs:__imp_CoTaskMemAlloc
0x18002d083  mov     r8, rax
0x18002d086  test    rax, rax
0x18002d089  jnz     short loc_18002D09A
0x18002d08b  mov     ebx, 8007000Eh
0x18002d090  mov     r9d, ebx
0x18002d093  mov     edx, 212h
0x18002d098  jmp     short loc_18002D03B
0x18002d09a  mov     r9d, edi
0x18002d09d  test    rbx, rbx
0x18002d0a0  jz      short loc_18002D0CF
0x18002d0a2  mov     eax, r9d
0x18002d0a5  lea     rdx, [rax+rax*4]
0x18002d0a9  mov     rax, [rbp+pv]
0x18002d0ad  movups  xmm0, xmmword ptr [rax+rdx*4]
0x18002d0b1  movdqu  xmmword ptr [r8+rdx*4], xmm0
0x18002d0b7  mov     rax, [rbp+pv]
0x18002d0bb  mov     ecx, [rax+rdx*4+10h]
0x18002d0bf  mov     [r8+rdx*4+10h], ecx
0x18002d0c4  inc     r9d
0x18002d0c7  mov     eax, r9d
0x18002d0ca  cmp     rax, rbx
0x18002d0cd  jb      short loc_18002D0A2
0x18002d0cf  mov     [r15], ebx
0x18002d0d2  mov     [r12], r8
0x18002d0d6  mov     rcx, [rbp+pv]; pv
0x18002d0da  test    rcx, rcx
0x18002d0dd  jz      short loc_18002D0ED
0x18002d0df  call    cs:__imp_CoTaskMemFree
0x18002d0e5  mov     [rbp+var_20], rdi
0x18002d0e9  mov     [rbp+pv], rdi
0x18002d0ed  mov     ebx, edi
0x18002d0ef  lea     rcx, [rbp+arg_20]
0x18002d0f3  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002d0f8  mov     eax, ebx
0x18002d0fa  add     rsp, 68h
0x18002d0fe  pop     r15
0x18002d100  pop     r14
0x18002d102  pop     r13
0x18002d104  pop     r12
0x18002d106  pop     rdi
0x18002d107  pop     rsi
0x18002d108  pop     rbx
0x18002d109  pop     rbp
0x18002d10a  retn
```
