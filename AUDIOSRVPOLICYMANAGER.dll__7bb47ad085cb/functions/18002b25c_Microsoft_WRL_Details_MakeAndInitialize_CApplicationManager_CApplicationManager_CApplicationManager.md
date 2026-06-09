# Microsoft::WRL::Details::MakeAndInitialize<CApplicationManager,CApplicationManager,>(CApplicationManager * *)

- ea: `0x18002b25c`
- end: `0x18002b353`
- name: `??$MakeAndInitialize@VCApplicationManager@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCApplicationManager@@@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180030408`

## callees

- `0x1800088a0`
- `0x18000f4e0`
- `0x18001ada0`
- `0x180025db0`
- `0x1800272f8`
- `0x18002acfc`
- `0x18002b25c`
- `0x18002b35c`
- `0x180031eb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b2c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b2c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002b2e5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002b2e5`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CApplicationManager,CApplicationManager,>(
        CApplicationManager **a1)
{
  CApplicationManager *v2; // rax
  int LastError; // edi
  CApplicationManager *v4; // rbx
  PSID *v5; // rdi
  void *v6; // rbp
  volatile int *v7; // rdx
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  CApplicationManager *v11; // [rsp+40h] [rbp+8h] BYREF
  char v12; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = (CApplicationManager *)operator new[](0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v2;
  if ( v2 )
  {
    v4 = CApplicationManager::CApplicationManager(v2);
    v11 = 0;
    v5 = (PSID *)((char *)v4 + 16);
    v6 = (void *)*((_QWORD *)v4 + 2);
    if ( v6 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
      LocalFree(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
    }
    *v5 = 0;
    if ( ConvertStringSidToSidW(
           L"S-1-15-3-1024-1692970155-4054893335-185714091-3362601943-3526593181-1159816984-2199008581-497492991",
           v5)
      || (LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x18A,
                        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
                        v8),
          LastError >= 0) )
    {
      if ( v4 )
      {
        Microsoft::WRL::Details::SafeUnknownIncrementReference((CApplicationManager *)((char *)v4 + 12), v7);
        *a1 = v4;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v4);
      }
      else
      {
        *a1 = 0;
      }
      LastError = 0;
    }
    else if ( v4 )
    {
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v4);
    }
  }
  else
  {
    LastError = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<CAudioSessionPropertyStore>::~MakeAllocator<CAudioSessionPropertyStore>(&v11);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002b25c  mov     [rsp+arg_10], rbx
0x18002b261  push    rbp
0x18002b262  push    rsi
0x18002b263  push    rdi
0x18002b264  sub     rsp, 20h
0x18002b268  mov     rsi, rcx
0x18002b26b  mov     qword ptr [rcx], 0
0x18002b272  mov     ecx, 0B0h; unsigned __int64
0x18002b277  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b27e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002b283  mov     [rsp+38h+arg_0], rax
0x18002b288  test    rax, rax
0x18002b28b  jnz     short loc_18002B297
0x18002b28d  mov     edi, 8007000Eh
0x18002b292  jmp     loc_18002B33A
0x18002b297  mov     rcx, rax; this
0x18002b29a  call    ??0CApplicationManager@@QEAA@XZ; CApplicationManager::CApplicationManager(void)
0x18002b29f  mov     rbx, rax
0x18002b2a2  mov     [rsp+38h+arg_0], 0
0x18002b2ab  lea     rdi, [rax+10h]
0x18002b2af  mov     rbp, [rdi]
0x18002b2b2  test    rbp, rbp
0x18002b2b5  jz      short loc_18002B2D4
0x18002b2b7  lea     rcx, [rsp+38h+arg_8]; this
0x18002b2bc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002b2c1  mov     rcx, rbp; hMem
0x18002b2c4  call    cs:__imp_LocalFree
0x18002b2ca  lea     rcx, [rsp+38h+arg_8]; this
0x18002b2cf  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002b2d4  mov     rdx, rdi; Sid
0x18002b2d7  mov     qword ptr [rdi], 0
0x18002b2de  lea     rcx, aS1153102416929; "S-1-15-3-1024-1692970155-4054893335-185"...
0x18002b2e5  call    cs:__imp_ConvertStringSidToSidW
0x18002b2eb  test    eax, eax
0x18002b2ed  jnz     short loc_18002B31A
0x18002b2ef  mov     rcx, [rsp+38h]; this
0x18002b2f4  lea     r8, aClientcoreMult_5; "clientcore\\multimedia\\audiocore\\serv"...
0x18002b2fb  mov     edx, 18Ah; void *
0x18002b300  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b305  mov     edi, eax
0x18002b307  test    eax, eax
0x18002b309  jns     short loc_18002B31A
0x18002b30b  test    rbx, rbx
0x18002b30e  jz      short loc_18002B33A
0x18002b310  mov     rcx, rbx
0x18002b313  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18002b318  jmp     short loc_18002B33A
0x18002b31a  test    rbx, rbx
0x18002b31d  jz      short loc_18002B335
0x18002b31f  lea     rcx, [rbx+0Ch]; this
0x18002b323  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18002b328  mov     rcx, rbx
0x18002b32b  mov     [rsi], rbx
0x18002b32e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18002b333  jmp     short loc_18002B338
0x18002b335  mov     [rsi], rbx
0x18002b338  xor     edi, edi
0x18002b33a  lea     rcx, [rsp+38h+arg_0]
0x18002b33f  call    ??1?$MakeAllocator@VCAudioSessionPropertyStore@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioSessionPropertyStore>::~MakeAllocator<CAudioSessionPropertyStore>(void)
0x18002b344  mov     rbx, [rsp+38h+arg_10]
0x18002b349  mov     eax, edi
0x18002b34b  add     rsp, 20h
0x18002b34f  pop     rdi
0x18002b350  pop     rsi
0x18002b351  pop     rbp
0x18002b352  retn
```
