# SecureEnrollmentDatabase::DeleteEnrollment(void * const)

- ea: `0x140060ab8`
- end: `0x140060b6e`
- name: `?DeleteEnrollment@SecureEnrollmentDatabase@@QEAAJQEAX@Z`
- size: `182`
- prototype: `__int64 __fastcall(Enrollments **this, void *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140054d80`

## callees

- `0x14000a420`
- `0x14000bd48`
- `0x140060ab8`
- `0x140062a0c`
- `0x140062a80`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x140060aec`
- `ntdll!RtlEqualSid` at `0x140060aec`

## string_xrefs

- `0x140060b15`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`
- `0x140060b2e`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall SecureEnrollmentDatabase::DeleteEnrollment(Enrollments **this, void *const a2)
{
  Enrollments *v4; // rdi
  __int64 i; // rbx
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v11; // [rsp+40h] [rbp+8h] BYREF
  char v12; // [rsp+50h] [rbp+18h] BYREF

  Enrollments::lock_exclusive(*this);
  v4 = *this;
  for ( i = *((_QWORD *)*this + 4); ; i += 128 )
  {
    if ( i == *((_QWORD *)v4 + 5) )
      goto LABEL_6;
    if ( RtlEqualSid(a2, *(PSID *)(i + 32)) )
      break;
  }
  if ( i == *((_QWORD *)v4 + 5) )
  {
LABEL_6:
    v6 = -2146861029;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
      (const char *)0x8009801BLL,
      v8);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
      (const char *)0x8009801BLL,
      v9);
    goto LABEL_8;
  }
  std::vector__anonymous_namespace_::Enrollment_std::allocator__anonymous_namespace_::Enrollment___::erase(
    (char *)v4 + 32,
    &v12,
    i);
  v6 = 0;
LABEL_8:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v11);
  return v6;
}

```

## disassembly

```asm
0x140060ab8  mov     [rsp+arg_8], rbx
0x140060abd  push    rbp
0x140060abe  push    rsi
0x140060abf  push    rdi; int
0x140060ac0  sub     rsp, 20h
0x140060ac4  mov     rbp, rdx
0x140060ac7  mov     rbx, rcx
0x140060aca  lea     rdx, [rsp+38h+arg_0]
0x140060acf  mov     rcx, [rcx]; this
0x140060ad2  call    ?lock_exclusive@Enrollments@@QEBA@XZ; Enrollments::lock_exclusive(void)
0x140060ad7  nop
0x140060ad8  mov     rdi, [rbx]
0x140060adb  mov     rbx, [rdi+20h]
0x140060adf  cmp     rbx, [rdi+28h]
0x140060ae3  jz      short loc_140060B08
0x140060ae5  mov     rdx, [rbx+20h]; Sid2
0x140060ae9  mov     rcx, rbp; Sid1
0x140060aec  call    cs:__imp_RtlEqualSid
0x140060af3  nop     dword ptr [rax+rax+00h]
0x140060af8  test    al, al
0x140060afa  jnz     short loc_140060B02
0x140060afc  sub     rbx, 0FFFFFFFFFFFFFF80h
0x140060b00  jmp     short loc_140060ADF
0x140060b02  cmp     rbx, [rdi+28h]
0x140060b06  jnz     short loc_140060B41
0x140060b08  mov     rcx, [rsp+38h]; this
0x140060b0d  mov     ebx, 8009801Bh
0x140060b12  mov     r9d, ebx; char *
0x140060b15  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x140060b1c  mov     edx, 29Bh; void *
0x140060b21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140060b26  mov     rcx, [rsp+38h]; this
0x140060b2b  mov     r9d, ebx; char *
0x140060b2e  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x140060b35  mov     edx, 139h; void *
0x140060b3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140060b3f  jmp     short loc_140060B54
0x140060b41  mov     r8, rbx
0x140060b44  lea     rdx, [rsp+38h+arg_10]
0x140060b49  lea     rcx, [rdi+20h]
0x140060b4d  call    std__vector__anonymous_namespace___Enrollment_std__allocator__anonymous_namespace___Enrollment_____erase
0x140060b52  xor     ebx, ebx
0x140060b54  lea     rcx, [rsp+38h+arg_0]
0x140060b59  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140060b5e  mov     eax, ebx
0x140060b60  mov     rbx, [rsp+38h+arg_8]
0x140060b65  add     rsp, 20h
0x140060b69  pop     rdi
0x140060b6a  pop     rsi
0x140060b6b  pop     rbp
0x140060b6c  retn
```
