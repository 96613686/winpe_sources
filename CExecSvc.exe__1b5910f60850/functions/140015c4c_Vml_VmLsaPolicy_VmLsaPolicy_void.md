# Vml::VmLsaPolicy::~VmLsaPolicy(void)

- ea: `0x140015c4c`
- end: `0x140015c82`
- name: `??1VmLsaPolicy@Vml@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140023065`

## callees

- `0x140015c4c`
- `0x14001a950`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140015c5d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140015c5d`

## pseudocode

```c
void __fastcall Vml::VmLsaPolicy::~VmLsaPolicy(void **this)
{
  void *v2; // rcx
  NTSTATUS v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *this;
  if ( v2 )
  {
    v3 = LsaClose(v2);
    if ( v3 < 0 )
      wil::details::in1diag3::_FailFast_NtStatus(retaddr, v4, v5, (const char *)(unsigned int)v3, v6);
    *this = 0;
  }
}

```

## disassembly

```asm
0x140015c4c  push    rbx; int
0x140015c4e  sub     rsp, 20h
0x140015c52  mov     rbx, rcx
0x140015c55  mov     rcx, [rcx]; ObjectHandle
0x140015c58  test    rcx, rcx
0x140015c5b  jz      short loc_140015C6E
0x140015c5d  call    cs:__imp_LsaClose
0x140015c63  test    eax, eax
0x140015c65  js      short loc_140015C74
0x140015c67  mov     qword ptr [rbx], 0
0x140015c6e  add     rsp, 20h
0x140015c72  pop     rbx
0x140015c73  retn
0x140015c74  mov     rcx, [rsp+28h]; this
0x140015c79  mov     r9d, eax; char *
0x140015c7c  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
```
