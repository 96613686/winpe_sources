# ATL::CSecurityDesc::MakeSelfRelative(void)

- ea: `0x180012288`
- end: `0x180012373`
- name: `?MakeSelfRelative@CSecurityDesc@ATL@@QEAAXXZ`
- size: `235`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001039c`

## callees

- `0x180012288`
- `0x18002bd78`
- `0x18002bd9c`
- `0x18002ccf0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012347`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012347`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001230e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001230e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122f9`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800122f3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180012333`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800122f3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180012333`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800122bb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800122bb`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::MakeSelfRelative(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rax
  void *v5; // rdi
  int Error; // ebx
  WORD pControl; // [rsp+30h] [rbp+8h] BYREF
  DWORD dwBufferLength; // [rsp+38h] [rbp+10h] BYREF
  DWORD dwRevision; // [rsp+40h] [rbp+18h] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    dwRevision = 0;
    pControl = 0;
    if ( !GetSecurityDescriptorControl(v2, &pControl, &dwRevision) )
      ATL::AtlThrowImpl(-2147467259);
    if ( (pControl & 0x8000u) == 0 )
    {
      v3 = (void *)*((_QWORD *)this + 1);
      dwBufferLength = 0;
      MakeSelfRelativeSD(v3, 0, &dwBufferLength);
      if ( GetLastError() != 122 )
        ATL::AtlThrowLastWin32();
      v4 = malloc(dwBufferLength);
      v5 = v4;
      if ( !v4 )
        ATL::AtlThrowImpl(-2147024882);
      if ( !MakeSelfRelativeSD(*((PSECURITY_DESCRIPTOR *)this + 1), v4, &dwBufferLength) )
      {
        Error = ATL::AtlHresultFromLastError();
        free(v5);
        ATL::AtlThrowImpl(Error);
      }
      (*(void (__fastcall **)(ATL::CSecurityDesc *))(*(_QWORD *)this + 8LL))(this);
      *((_QWORD *)this + 1) = v5;
    }
  }
}

```

## disassembly

```asm
0x180012288  mov     [rsp+arg_18], rbx
0x18001228d  push    rdi
0x18001228e  sub     rsp, 20h
0x180012292  mov     rbx, rcx
0x180012295  mov     rcx, [rcx+8]; pSecurityDescriptor
0x180012299  test    rcx, rcx
0x18001229c  jz      loc_180012368
0x1800122a2  xor     eax, eax
0x1800122a4  mov     [rsp+28h+dwRevision], 0
0x1800122ac  lea     r8, [rsp+28h+dwRevision]; lpdwRevision
0x1800122b1  mov     [rsp+28h+pControl], ax
0x1800122b6  lea     rdx, [rsp+28h+pControl]; pControl
0x1800122bb  call    cs:__imp_GetSecurityDescriptorControl
0x1800122c1  test    eax, eax
0x1800122c3  jnz     short loc_1800122D0
0x1800122c5  mov     ecx, 80004005h; int
0x1800122ca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800122d0  mov     eax, 8000h
0x1800122d5  test    [rsp+28h+pControl], ax
0x1800122da  jnz     loc_180012368
0x1800122e0  mov     rcx, [rbx+8]; pAbsoluteSecurityDescriptor
0x1800122e4  lea     r8, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x1800122e9  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1800122eb  mov     [rsp+28h+dwBufferLength], 0
0x1800122f3  call    cs:__imp_MakeSelfRelativeSD
0x1800122f9  call    cs:__imp_GetLastError
0x1800122ff  cmp     eax, 7Ah ; 'z'
0x180012302  jz      short loc_18001230A
0x180012304  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18001230a  mov     ecx, [rsp+28h+dwBufferLength]; Size
0x18001230e  call    cs:__imp_malloc
0x180012314  mov     rdi, rax
0x180012317  test    rax, rax
0x18001231a  jnz     short loc_180012327
0x18001231c  mov     ecx, 8007000Eh; int
0x180012321  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012327  mov     rcx, [rbx+8]; pAbsoluteSecurityDescriptor
0x18001232b  lea     r8, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x180012330  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x180012333  call    cs:__imp_MakeSelfRelativeSD
0x180012339  test    eax, eax
0x18001233b  jnz     short loc_180012355
0x18001233d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180012342  mov     rcx, rdi; Block
0x180012345  mov     ebx, eax
0x180012347  call    cs:__imp_free
0x18001234d  mov     ecx, ebx; int
0x18001234f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012355  mov     rax, [rbx]
0x180012358  mov     rcx, rbx
0x18001235b  mov     rax, [rax+8]
0x18001235f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012364  mov     [rbx+8], rdi
0x180012368  mov     rbx, [rsp+28h+arg_18]
0x18001236d  add     rsp, 20h
0x180012371  pop     rdi
0x180012372  retn
```
