# AIXPolicyHelper::IsWipUser(void)

- ea: `0x18002c5f4`
- end: `0x18002c687`
- name: `?IsWipUser@AIXPolicyHelper@@YA_NXZ`
- size: `147`
- prototype: `bool __fastcall(AIXPolicyHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c00c`

## callees

- `0x180010ea8`
- `0x18002c5f4`
- `0x18003105c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c625`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c625`

## string_xrefs

- `0x18002c658`: `shellcommon\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall AIXPolicyHelper::IsWipUser(AIXPolicyHelper *this)
{
  char v1; // bl
  int v2; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int16 v6; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  v1 = 1;
  if ( CoCreateInstance(
         &GUID_3185a766_b338_11e4_a71e_12e3f512a338,
         0,
         1u,
         &GUID_e833feb2_c58a_45e4_8d93_08874744febb,
         &v7) < 0 )
    goto LABEL_5;
  v6 = 0;
  v2 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v7 + 24LL))(v7, &v6);
  if ( v2 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x197,
      (unsigned int)"shellcommon\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)v2,
      ppv);
LABEL_5:
    v1 = 0;
    goto LABEL_6;
  }
  if ( v6 != -1 )
    goto LABEL_5;
LABEL_6:
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v7);
  return v1;
}

```

## disassembly

```asm
0x18002c5f4  push    rbx
0x18002c5f6  sub     rsp, 30h
0x18002c5fa  mov     [rsp+38h+arg_8], 0
0x18002c603  lea     rax, [rsp+38h+arg_8]
0x18002c608  mov     qword ptr [rsp+38h+ppv], rax; int
0x18002c60d  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x18002c614  mov     ebx, 1
0x18002c619  mov     r8d, ebx; dwClsContext
0x18002c61c  xor     edx, edx; pUnkOuter
0x18002c61e  lea     rcx, _GUID_3185a766_b338_11e4_a71e_12e3f512a338; rclsid
0x18002c625  call    cs:__imp_CoCreateInstance
0x18002c62b  test    eax, eax
0x18002c62d  js      short loc_18002C673
0x18002c62f  xor     eax, eax
0x18002c631  mov     [rsp+38h+arg_0], ax
0x18002c636  mov     rcx, [rsp+38h+arg_8]
0x18002c63b  mov     rax, [rcx]
0x18002c63e  lea     rdx, [rsp+38h+arg_0]
0x18002c643  mov     rax, [rax+18h]
0x18002c647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c64c  mov     rcx, [rsp+38h]; this
0x18002c651  test    eax, eax
0x18002c653  jns     short loc_18002C66B
0x18002c655  mov     r9d, eax; char *
0x18002c658  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\inc\\AIXPolicyHelpe"...
0x18002c65f  mov     edx, 197h; void *
0x18002c664  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c669  jmp     short loc_18002C673
0x18002c66b  cmp     [rsp+38h+arg_0], 0FFFFh
0x18002c671  jz      short loc_18002C675
0x18002c673  xor     bl, bl
0x18002c675  lea     rcx, [rsp+38h+arg_8]
0x18002c67a  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18002c67f  mov     al, bl
0x18002c681  add     rsp, 30h
0x18002c685  pop     rbx
0x18002c686  retn
```
