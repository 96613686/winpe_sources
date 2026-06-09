# RoutePolicyProxy::IsCallerWcmSvc

- ea: `0x14000865c`
- end: `0x140008792`
- name: `RoutePolicyProxy::IsCallerWcmSvc`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400081ec`

## callees

- `0x140001008`
- `0x14000865c`
- `0x14000a680`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14000868b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000868b`
- `ntoskrnl!SeLockSubjectContext` at `0x14000869b`
- `ntoskrnl!SeLockSubjectContext` at `0x14000869b`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140008714`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140008714`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140008724`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140008724`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400086b5`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400086b5`
- `ntoskrnl!SeAccessCheck` at `0x140008702`
- `ntoskrnl!SeAccessCheck` at `0x140008702`

## string_xrefs

- `0x14000874c`: `SeAccessCheck failed`

## pseudocode

```c
char RoutePolicyProxy::IsCallerWcmSvc()
{
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v1; // bl
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  int v6; // [rsp+50h] [rbp+17h] BYREF
  const char *v7; // [rsp+58h] [rbp+1Fh] BYREF
  int AccessStatus; // [rsp+60h] [rbp+27h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp+2Bh] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp+2Fh] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  GrantedAccess = 0;
  AccessStatus = 0;
  GenericMapping = IoGetFileObjectGenericMapping();
  v1 = SeAccessCheck(
         SecurityDescriptor,
         &SubjectContext,
         1u,
         0x1F01FFu,
         0,
         0,
         GenericMapping,
         1,
         &GrantedAccess,
         &AccessStatus);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  if ( v1 )
    return 1;
  if ( (unsigned int)dword_140012050 > 3 )
  {
    v6 = AccessStatus;
    v7 = "SeAccessCheck failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)&dword_140010884,
      v3,
      v4,
      (__int64)&v7,
      (__int64)&v6);
  }
  return 0;
}

```

## disassembly

```asm
0x14000865c  mov     [rsp-8+arg_0], rbx
0x140008661  push    rbp
0x140008662  lea     rbp, [rsp-57h]
0x140008667  sub     rsp, 90h
0x14000866e  mov     rax, cs:__security_cookie
0x140008675  xor     rax, rsp
0x140008678  mov     [rbp+57h+var_8], rax
0x14000867c  xorps   xmm0, xmm0
0x14000867f  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140008683  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x140008687  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14000868b  call    cs:__imp_SeCaptureSubjectContext
0x140008692  nop     dword ptr [rax+rax+00h]
0x140008697  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14000869b  call    cs:__imp_SeLockSubjectContext
0x1400086a2  nop     dword ptr [rax+rax+00h]
0x1400086a7  mov     [rbp+57h+var_2C], 0
0x1400086ae  mov     [rbp+57h+var_30], 0
0x1400086b5  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400086bc  nop     dword ptr [rax+rax+00h]
0x1400086c1  lea     rcx, [rbp+57h+var_30]
0x1400086c5  mov     r9d, 1F01FFh; DesiredAccess
0x1400086cb  mov     [rsp+90h+AccessStatus], rcx; AccessStatus
0x1400086d0  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1400086d4  lea     rcx, [rbp+57h+var_2C]
0x1400086d8  mov     r8b, 1; SubjectContextLocked
0x1400086db  mov     [rsp+90h+GrantedAccess], rcx; GrantedAccess
0x1400086e0  mov     rcx, cs:SecurityDescriptor; SecurityDescriptor
0x1400086e7  mov     [rsp+90h+AccessMode], 1; AccessMode
0x1400086ec  mov     [rsp+90h+GenericMapping], rax; GenericMapping
0x1400086f1  mov     [rsp+90h+Privileges], 0; Privileges
0x1400086fa  mov     [rsp+90h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140008702  call    cs:__imp_SeAccessCheck
0x140008709  nop     dword ptr [rax+rax+00h]
0x14000870e  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140008712  mov     bl, al
0x140008714  call    cs:__imp_SeUnlockSubjectContext
0x14000871b  nop     dword ptr [rax+rax+00h]
0x140008720  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140008724  call    cs:__imp_SeReleaseSubjectContext
0x14000872b  nop     dword ptr [rax+rax+00h]
0x140008730  test    bl, bl
0x140008732  jnz     short loc_140008772
0x140008734  mov     eax, cs:dword_140012050
0x14000873a  cmp     eax, 3
0x14000873d  jbe     short loc_14000876E
0x14000873f  mov     eax, [rbp+57h+var_30]
0x140008742  lea     rdx, dword_140010884
0x140008749  mov     [rbp+57h+var_40], eax
0x14000874c  lea     rax, aSeaccesscheckF; "SeAccessCheck failed"
0x140008753  mov     [rbp+57h+var_38], rax
0x140008757  lea     rax, [rbp+57h+var_40]
0x14000875b  mov     [rsp+90h+Privileges], rax
0x140008760  lea     rax, [rbp+57h+var_38]
0x140008764  mov     qword ptr [rsp+90h+PreviouslyGrantedAccess], rax
0x140008769  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000876e  xor     al, al
0x140008770  jmp     short loc_140008774
0x140008772  mov     al, 1
0x140008774  mov     rcx, [rbp+57h+var_8]
0x140008778  xor     rcx, rsp; StackCookie
0x14000877b  call    __security_check_cookie
0x140008780  mov     rbx, [rsp+90h+arg_0]
0x140008788  add     rsp, 90h
0x14000878f  pop     rbp
0x140008790  retn
```
