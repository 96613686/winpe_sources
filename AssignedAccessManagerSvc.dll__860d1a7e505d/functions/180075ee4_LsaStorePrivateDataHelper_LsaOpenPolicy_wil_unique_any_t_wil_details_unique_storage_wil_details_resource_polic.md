# LsaStorePrivateDataHelper::LsaOpenPolicy(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x180075ee4`
- end: `0x180075f68`
- name: `?LsaOpenPolicy@LsaStorePrivateDataHelper@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(PLSA_HANDLE PolicyHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180075d04`
- `0x180075f94`

## callees

- `0x180009a74`
- `0x180009d58`
- `0x180075ee4`
- `0x180075f70`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180075f3d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180075f3d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180075f16`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180075f16`

## pseudocode

```c
int __fastcall LsaStorePrivateDataHelper::LsaOpenPolicy(PLSA_HANDLE PolicyHandle)
{
  PVOID v1; // rdi
  NTSTATUS v3; // eax
  unsigned int v4; // r8d
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v8; // [rsp+60h] [rbp+8h] BYREF

  v1 = *PolicyHandle;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( v1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
    LsaClose(v1);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
  }
  *PolicyHandle = 0;
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 0x20u, PolicyHandle);
  if ( v3 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x55,
             v4,
             (const char *)(unsigned int)v3,
             ObjectAttributes.Length);
}

```

## disassembly

```asm
0x180075ee4  mov     rax, rsp
0x180075ee7  mov     [rax+10h], rbx
0x180075eeb  push    rdi
0x180075eec  sub     rsp, 50h
0x180075ef0  mov     rdi, [rcx]
0x180075ef3  xorps   xmm0, xmm0
0x180075ef6  mov     rbx, rcx
0x180075ef9  movups  xmmword ptr [rax-38h], xmm0
0x180075efd  movups  xmmword ptr [rax-28h], xmm0
0x180075f01  movups  xmmword ptr [rax-18h], xmm0
0x180075f05  test    rdi, rdi
0x180075f08  jz      short loc_180075F26
0x180075f0a  lea     rcx, [rax+8]; this
0x180075f0e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180075f13  mov     rcx, rdi; ObjectHandle
0x180075f16  call    cs:__imp_LsaClose
0x180075f1c  lea     rcx, [rsp+58h+arg_0]; this
0x180075f21  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180075f26  mov     r9, rbx; PolicyHandle
0x180075f29  mov     qword ptr [rbx], 0
0x180075f30  mov     r8d, 20h ; ' '; DesiredAccess
0x180075f36  lea     rdx, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x180075f3b  xor     ecx, ecx; SystemName
0x180075f3d  call    cs:__imp_LsaOpenPolicy
0x180075f43  test    eax, eax
0x180075f45  jns     short loc_180075F5B
0x180075f47  mov     rcx, [rsp+58h]; this
0x180075f4c  mov     r9d, eax; char *
0x180075f4f  mov     edx, 55h ; 'U'; void *
0x180075f54  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180075f59  jmp     short loc_180075F5D
0x180075f5b  xor     eax, eax
0x180075f5d  mov     rbx, [rsp+58h+arg_8]
0x180075f62  add     rsp, 50h
0x180075f66  pop     rdi
0x180075f67  retn
```
