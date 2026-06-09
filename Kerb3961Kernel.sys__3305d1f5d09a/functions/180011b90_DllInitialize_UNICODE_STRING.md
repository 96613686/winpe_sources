# DllInitialize(_UNICODE_STRING *)

- ea: `0x180011b90`
- end: `0x180011c67`
- name: `?DllInitialize@@YAJPEAU_UNICODE_STRING@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180011b90`
- `0x180012200`
- `0x180012240`
- `0x18001f078`

## import_xrefs

- `ntoskrnl!EtwSetInformation` at `0x180011c40`
- `ntoskrnl!EtwSetInformation` at `0x180011c40`
- `ntoskrnl!EtwRegister` at `0x180011c1b`
- `ntoskrnl!EtwRegister` at `0x180011c1b`

## pseudocode

```c
__int64 __fastcall DllInitialize(struct _UNICODE_STRING *a1)
{
  void (**i)(void); // rbx
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  for ( i = (void (**)(void))&__xc_a; i != (void (**)(void))&__xc_z; ++i )
  {
    if ( *i )
      (*i)();
  }
  wil_InitializeFeatureStaging();
  ProviderId = (GUID)*((_OWORD *)EventInformation - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_18001A028 = 0;
  if ( !EtwRegister(&ProviderId, tlgEnableCallback, &dword_18001A000, &RegHandle) )
    EtwSetInformation(RegHandle, EventProviderSetTraits, EventInformation, *(unsigned __int16 *)EventInformation);
  return 0;
}

```

## disassembly

```asm
0x180011b90  mov     [rsp+arg_0], rbx
0x180011b95  push    rdi
0x180011b96  sub     rsp, 40h
0x180011b9a  mov     rax, cs:__security_cookie
0x180011ba1  xor     rax, rsp
0x180011ba4  mov     [rsp+48h+var_18], rax
0x180011ba9  lea     rbx, ?__xc_a@@3P6AXXZEA; void (*__xc_a)(void)
0x180011bb0  lea     rdi, ?__xc_z@@3P6AXXZEA; void (*__xc_z)(void)
0x180011bb7  jmp     short loc_180011BCA
0x180011bb9  mov     rax, [rbx]
0x180011bbc  test    rax, rax
0x180011bbf  jz      short loc_180011BC6
0x180011bc1  call    _guard_dispatch_icall
0x180011bc6  add     rbx, 8
0x180011bca  cmp     rbx, rdi
0x180011bcd  jnz     short loc_180011BB9
0x180011bcf  call    wil_InitializeFeatureStaging
0x180011bd4  cmp     cs:RegHandle, 0
0x180011bdc  mov     rax, cs:EventInformation
0x180011be3  movups  xmm0, xmmword ptr [rax-10h]
0x180011be7  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180011bed  jz      short loc_180011BF6
0x180011bef  mov     ecx, 5
0x180011bf4  int     29h; Win8: RtlFailFast(ecx)
0x180011bf6  xorps   xmm0, xmm0
0x180011bf9  lea     r9, RegHandle; RegHandle
0x180011c00  lea     r8, dword_18001A000; CallbackContext
0x180011c07  lea     rdx, _tlgEnableCallback; EnableCallback
0x180011c0e  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180011c13  movdqu  cs:xmmword_18001A028, xmm0
0x180011c1b  call    cs:__imp_EtwRegister
0x180011c22  nop     dword ptr [rax+rax+00h]
0x180011c27  test    eax, eax
0x180011c29  jnz     short loc_180011C4C
0x180011c2b  mov     r8, cs:EventInformation; EventInformation
0x180011c32  lea     edx, [rax+2]; InformationClass
0x180011c35  mov     rcx, cs:RegHandle; RegHandle
0x180011c3c  movzx   r9d, word ptr [r8]; InformationLength
0x180011c40  call    cs:__imp_EtwSetInformation
0x180011c47  nop     dword ptr [rax+rax+00h]
0x180011c4c  xor     eax, eax
0x180011c4e  mov     rcx, [rsp+48h+var_18]
0x180011c53  xor     rcx, rsp; StackCookie
0x180011c56  call    __security_check_cookie
0x180011c5b  mov     rbx, [rsp+48h+arg_0]
0x180011c60  add     rsp, 40h
0x180011c64  pop     rdi
0x180011c65  retn
```
