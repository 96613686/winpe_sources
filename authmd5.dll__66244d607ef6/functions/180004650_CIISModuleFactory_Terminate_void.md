# CIISModuleFactory::Terminate(void)

- ea: `0x180004650`
- end: `0x1800046d0`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `128`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001064`
- `0x180004650`
- `0x1800046d8`
- `0x180004c44`
- `0x180005fc8`
- `0x180006078`

## import_xrefs

- `iisutil!PuDeleteDebugPrintsObject` at `0x1800046a5`
- `iisutil!PuDeleteDebugPrintsObject` at `0x1800046a5`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  if ( s_pDigestAuthProvider )
  {
    DIGEST_AUTH_PROVIDER::TerminateInstance(s_pDigestAuthProvider);
    operator delete(s_pDigestAuthProvider);
    s_pDigestAuthProvider = 0;
  }
  DIGEST_CONTEXT_CACHE_ENTRY::Terminate();
  SSPI_SECURITY_CONTEXT::Terminate();
  SSPI_CREDENTIAL::Terminate();
  if ( g_pDebug && *(_DWORD *)(g_pDebug + 640) )
    g_pDebug = PuDeleteDebugPrintsObject();
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180004650  push    rbx
0x180004652  sub     rsp, 20h
0x180004656  mov     rbx, rcx
0x180004659  mov     rcx, cs:?s_pDigestAuthProvider@@3PEAVDIGEST_AUTH_PROVIDER@@EA; this
0x180004660  test    rcx, rcx
0x180004663  jz      short loc_180004681
0x180004665  call    ?TerminateInstance@DIGEST_AUTH_PROVIDER@@QEAAXXZ; DIGEST_AUTH_PROVIDER::TerminateInstance(void)
0x18000466a  mov     rcx, cs:?s_pDigestAuthProvider@@3PEAVDIGEST_AUTH_PROVIDER@@EA; Block
0x180004671  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004676  mov     cs:?s_pDigestAuthProvider@@3PEAVDIGEST_AUTH_PROVIDER@@EA, 0; DIGEST_AUTH_PROVIDER * s_pDigestAuthProvider
0x180004681  call    ?Terminate@DIGEST_CONTEXT_CACHE_ENTRY@@SAXXZ; DIGEST_CONTEXT_CACHE_ENTRY::Terminate(void)
0x180004686  call    ?Terminate@SSPI_SECURITY_CONTEXT@@SAXXZ; SSPI_SECURITY_CONTEXT::Terminate(void)
0x18000468b  call    ?Terminate@SSPI_CREDENTIAL@@SAXXZ; SSPI_CREDENTIAL::Terminate(void)
0x180004690  mov     rcx, cs:g_pDebug
0x180004697  test    rcx, rcx
0x18000469a  jz      short loc_1800046B2
0x18000469c  cmp     dword ptr [rcx+280h], 0
0x1800046a3  jz      short loc_1800046B2
0x1800046a5  call    cs:__imp_PuDeleteDebugPrintsObject
0x1800046ab  mov     cs:g_pDebug, rax
0x1800046b2  test    rbx, rbx
0x1800046b5  jz      short loc_1800046CA
0x1800046b7  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x1800046be  mov     rcx, rbx; Block
0x1800046c1  mov     [rbx+8], rax
0x1800046c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800046ca  add     rsp, 20h
0x1800046ce  pop     rbx
0x1800046cf  retn
```
