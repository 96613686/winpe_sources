# CUpdateDeploymentSession::CreateUpdateDeploymentJob(IUnknown *,unsigned __int64,unsigned __int64,ulong,unsigned __int64,IUpdateDeploymentJob * *)

- ea: `0x18001cd60`
- end: `0x18001cfbf`
- name: `?CreateUpdateDeploymentJob@CUpdateDeploymentSession@@UEAAJPEAUIUnknown@@_K1K1PEAPEAUIUpdateDeploymentJob@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(CUpdateDeploymentSession *__hidden this, struct IUnknown *, unsigned __int64, unsigned __int64, unsigned int, unsigned __int64, struct IUpdateDeploymentJob **)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x180011b44`
- `0x18001cd60`
- `0x18001cfc8`
- `0x180032d44`
- `0x1800382d8`
- `0x180061960`
- `0x180062558`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001ce04`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001ce04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cf47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cf47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cf7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cf7c`

## string_xrefs

- `0x18001cea7`: `Deployment job Id %ws : Created successfully.`
- `0x18001cf32`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentSession.cpp`
- `0x18001ce1b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18001ce37`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CUpdateDeploymentSession::CreateUpdateDeploymentJob(
        CUpdateDeploymentSession *this,
        struct IUnknown *a2,
        __int64 a3,
        unsigned __int64 a4,
        unsigned int a5,
        unsigned __int64 a6,
        struct IUpdateDeploymentJob **a7)
{
  CUpdateDeploymentJob *v11; // rbx
  __int64 v12; // rdx
  int v13; // edi
  CUpdateDeploymentJob *v14; // rax
  CUpdateDeploymentJob *v15; // rsi
  HRESULT Guid; // eax
  __int64 v17; // rax
  int v19; // [rsp+20h] [rbp-108h]
  int v20; // [rsp+20h] [rbp-108h]
  struct _GUID v21; // [rsp+40h] [rbp-E8h] BYREF
  CUpdateDeploymentJob *v22; // [rsp+50h] [rbp-D8h]
  _BYTE v23[24]; // [rsp+58h] [rbp-D0h] BYREF
  _BYTE v24[80]; // [rsp+70h] [rbp-B8h] BYREF
  struct _GUID v25; // [rsp+C0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v11 = 0;
  v25 = GUID_NULL;
  if ( !a2 )
  {
    v12 = 144;
LABEL_5:
    v13 = -2147467261;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentSession.cpp",
      (const char *)(unsigned int)v13,
      v19);
    goto LABEL_19;
  }
  if ( !a7 )
  {
    v12 = 145;
    goto LABEL_5;
  }
  v14 = (CUpdateDeploymentJob *)operator new(0x3E0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v14 )
    v15 = CUpdateDeploymentJob::CUpdateDeploymentJob(v14);
  else
    v15 = 0;
  (*(void (__fastcall **)(CUpdateDeploymentJob *))(*(_QWORD *)v15 + 8LL))(v15);
  Guid = CoCreateGuid((GUID *)v15 + 1);
  v13 = Guid;
  if ( Guid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)Guid,
      v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v13,
      v20);
    (*(void (__fastcall **)(CUpdateDeploymentJob *, __int64))(*(_QWORD *)v15 + 112LL))(v15, 1);
    v12 = 147;
    goto LABEL_17;
  }
  v11 = v15;
  v13 = (*(__int64 (__fastcall **)(CUpdateDeploymentJob *, struct _GUID *))(*(_QWORD *)v15 + 24LL))(v15, &v25);
  if ( v13 < 0 )
  {
    v12 = 148;
    goto LABEL_17;
  }
  v17 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v24, &v25);
  WUTrace(0, 0, 0x1000000, 4, 0, L"Deployment job Id %ws : Created successfully.", v17);
  v13 = CUpdateDeploymentJob::Initialize(v15, a2, a3, a5, a6, a4);
  if ( v13 < 0 )
  {
    v12 = 159;
    goto LABEL_17;
  }
  v13 = (**(__int64 (__fastcall ***)(CUpdateDeploymentJob *, GUID *, struct IUpdateDeploymentJob **))v15)(
          v15,
          &GUID_ea89c1da_c962_4f4f_9da7_8a2db832a986,
          a7);
  if ( v13 < 0 )
  {
    v12 = 160;
    goto LABEL_17;
  }
  EnterCriticalSection(&stru_1800A1698);
  v11 = 0;
  v21 = v25;
  v22 = v15;
  std::map<_GUID,CUpdateDeploymentJob *>::insert<std::pair<_GUID,CUpdateDeploymentJob *>,0>(
    (char *)this + 16,
    v23,
    &v21);
  LeaveCriticalSection(&stru_1800A1698);
  v13 = 0;
LABEL_19:
  if ( v11 )
    (*(void (__fastcall **)(CUpdateDeploymentJob *))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001cd60  push    rbx
0x18001cd62  push    rbp
0x18001cd63  push    rsi
0x18001cd64  push    rdi
0x18001cd65  push    r12
0x18001cd67  push    r13
0x18001cd69  push    r14
0x18001cd6b  push    r15
0x18001cd6d  sub     rsp, 0E8h
0x18001cd74  mov     rax, cs:__security_cookie
0x18001cd7b  xor     rax, rsp
0x18001cd7e  mov     [rsp+128h+var_58], rax
0x18001cd86  mov     r13, r9
0x18001cd89  mov     r12, r8
0x18001cd8c  mov     r14, rdx
0x18001cd8f  mov     r15, rcx
0x18001cd92  mov     rbp, [rsp+128h+arg_30]
0x18001cd9a  xor     ebx, ebx
0x18001cd9c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001cda3  movdqu  xmmword ptr [rsp+128h+var_68.Data1], xmm0
0x18001cdac  test    rdx, rdx
0x18001cdaf  jnz     short loc_18001CDB8
0x18001cdb1  mov     edx, 90h
0x18001cdb6  jmp     short loc_18001CDC2
0x18001cdb8  test    rbp, rbp
0x18001cdbb  jnz     short loc_18001CDCC
0x18001cdbd  mov     edx, 91h
0x18001cdc2  mov     edi, 80004003h
0x18001cdc7  jmp     loc_18001CF27
0x18001cdcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001cdd3  mov     ecx, 3E0h; unsigned __int64
0x18001cdd8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001cddd  test    rax, rax
0x18001cde0  jz      short loc_18001CDEF
0x18001cde2  mov     rcx, rax; this
0x18001cde5  call    ??0CUpdateDeploymentJob@@QEAA@XZ; CUpdateDeploymentJob::CUpdateDeploymentJob(void)
0x18001cdea  mov     rsi, rax
0x18001cded  jmp     short loc_18001CDF1
0x18001cdef  xor     esi, esi
0x18001cdf1  mov     rax, [rsi]
0x18001cdf4  mov     rcx, rsi
0x18001cdf7  mov     rax, [rax+8]
0x18001cdfb  call    _guard_dispatch_icall
0x18001ce00  lea     rcx, [rsi+10h]; pguid
0x18001ce04  call    cs:__imp_CoCreateGuid
0x18001ce0a  mov     edi, eax
0x18001ce0c  test    eax, eax
0x18001ce0e  jns     short loc_18001CE66
0x18001ce10  mov     rcx, [rsp+128h]; this
0x18001ce18  mov     r9d, eax; char *
0x18001ce1b  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001ce22  mov     edx, 152h; void *
0x18001ce27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ce2c  mov     rcx, [rsp+128h]; this
0x18001ce34  mov     r9d, edi; char *
0x18001ce37  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001ce3e  mov     edx, 11Dh; void *
0x18001ce43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ce48  mov     rax, [rsi]
0x18001ce4b  mov     edx, 1
0x18001ce50  mov     rcx, rsi
0x18001ce53  mov     rax, [rax+70h]
0x18001ce57  call    _guard_dispatch_icall
0x18001ce5c  mov     edx, 93h
0x18001ce61  jmp     loc_18001CF27
0x18001ce66  mov     rbx, rsi
0x18001ce69  mov     rax, [rsi]
0x18001ce6c  lea     rdx, [rsp+128h+var_68]
0x18001ce74  mov     rcx, rsi
0x18001ce77  mov     rax, [rax+18h]
0x18001ce7b  call    _guard_dispatch_icall
0x18001ce80  mov     edi, eax
0x18001ce82  test    eax, eax
0x18001ce84  jns     short loc_18001CE90
0x18001ce86  mov     edx, 94h
0x18001ce8b  jmp     loc_18001CF27
0x18001ce90  lea     rdx, [rsp+128h+var_68]; struct _GUID *
0x18001ce98  lea     rcx, [rsp+128h+var_B8]; this
0x18001ce9d  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18001cea2  mov     [rsp+128h+var_F8], rax
0x18001cea7  lea     rax, aDeploymentJobI_61; "Deployment job Id %ws : Created success"...
0x18001ceae  mov     [rsp+128h+var_100], rax
0x18001ceb3  mov     [rsp+128h+var_108], 0
0x18001cebc  xor     edx, edx
0x18001cebe  xor     ecx, ecx
0x18001cec0  lea     r9d, [rdx+4]
0x18001cec4  mov     r8d, 1000000h
0x18001ceca  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001cecf  mov     [rsp+128h+var_100], r13; unsigned __int64
0x18001ced4  mov     rax, [rsp+128h+arg_28]
0x18001cedc  mov     [rsp+128h+var_108], rax; int
0x18001cee1  mov     r9d, [rsp+128h+arg_20]; unsigned int
0x18001cee9  mov     r8, r12; unsigned __int64
0x18001ceec  mov     rdx, r14; struct IUnknown *
0x18001ceef  mov     rcx, rbx; this
0x18001cef2  call    ?Initialize@CUpdateDeploymentJob@@QEAAJPEAUIUnknown@@_KK_K1@Z; CUpdateDeploymentJob::Initialize(IUnknown *,unsigned __int64,ulong,unsigned __int64,unsigned __int64)
0x18001cef7  mov     edi, eax
0x18001cef9  test    eax, eax
0x18001cefb  jns     short loc_18001CF04
0x18001cefd  mov     edx, 9Fh
0x18001cf02  jmp     short loc_18001CF27
0x18001cf04  mov     rax, [rsi]
0x18001cf07  mov     r8, rbp
0x18001cf0a  lea     rdx, _GUID_ea89c1da_c962_4f4f_9da7_8a2db832a986
0x18001cf11  mov     rcx, rbx
0x18001cf14  mov     rax, [rax]
0x18001cf17  call    _guard_dispatch_icall
0x18001cf1c  mov     edi, eax
0x18001cf1e  test    eax, eax
0x18001cf20  jns     short loc_18001CF40
0x18001cf22  mov     edx, 0A0h; void *
0x18001cf27  mov     rcx, [rsp+128h]; this
0x18001cf2f  mov     r9d, edi; char *
0x18001cf32  lea     r8, aCW1SSrcClientU_7; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001cf39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf3e  jmp     short loc_18001CF84
0x18001cf40  lea     rcx, stru_1800A1698; lpCriticalSection
0x18001cf47  call    cs:__imp_EnterCriticalSection
0x18001cf4d  xor     ebx, ebx
0x18001cf4f  movups  xmm0, xmmword ptr [rsp+128h+var_68.Data1]
0x18001cf57  movdqu  [rsp+128h+var_E8], xmm0
0x18001cf5d  mov     [rsp+128h+var_D8], rsi
0x18001cf62  lea     rcx, [r15+10h]
0x18001cf66  lea     r8, [rsp+128h+var_E8]
0x18001cf6b  lea     rdx, [rsp+128h+var_D0]
0x18001cf70  call    ??$insert@U?$pair@U_GUID@@PEAVCUpdateDeploymentJob@@@std@@$0A@@?$map@U_GUID@@PEAVCUpdateDeploymentJob@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCUpdateDeploymentJob@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCUpdateDeploymentJob@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@U_GUID@@PEAVCUpdateDeploymentJob@@@1@@Z; std::map<_GUID,CUpdateDeploymentJob *>::insert<std::pair<_GUID,CUpdateDeploymentJob *>,0>(std::pair<_GUID,CUpdateDeploymentJob *> &&)
0x18001cf75  lea     rcx, stru_1800A1698; lpCriticalSection
0x18001cf7c  call    cs:__imp_LeaveCriticalSection
0x18001cf82  xor     edi, edi
0x18001cf84  test    rbx, rbx
0x18001cf87  jz      short loc_18001CF99
0x18001cf89  mov     rcx, [rbx]
0x18001cf8c  mov     rax, [rcx+10h]
0x18001cf90  mov     rcx, rbx
0x18001cf93  call    _guard_dispatch_icall
0x18001cf98  nop
0x18001cf99  mov     eax, edi
0x18001cf9b  mov     rcx, [rsp+128h+var_58]
0x18001cfa3  xor     rcx, rsp; StackCookie
0x18001cfa6  call    __security_check_cookie
0x18001cfab  add     rsp, 0E8h
0x18001cfb2  pop     r15
0x18001cfb4  pop     r14
0x18001cfb6  pop     r13
0x18001cfb8  pop     r12
0x18001cfba  pop     rdi
0x18001cfbb  pop     rsi
0x18001cfbc  pop     rbp
0x18001cfbd  pop     rbx
0x18001cfbe  retn
```
