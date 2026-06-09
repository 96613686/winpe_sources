# CCbsTiSession::OpenPackage(uint,ICbsIdentity *,wchar_t const *,IUnknown * *)

- ea: `0x140010a54`
- end: `0x140010c49`
- name: `?OpenPackage@CCbsTiSession@@UEAAJIPEAUICbsIdentity@@PEB_WPEAPEAUIUnknown@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(CCbsTiSession *__hidden this, unsigned int, struct ICbsIdentity *, const wchar_t *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140010a40`

## callees

- `0x140002070`
- `0x1400023e0`
- `0x1400106c4`
- `0x140010a54`
- `0x1400130e0`
- `0x1400139cc`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x140010b39`: `Failed to OpenPackage using worker session`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::OpenPackage(
        CCbsTiSession *this,
        unsigned int a2,
        struct ICbsIdentity *a3,
        const wchar_t *a4,
        struct IUnknown **a5)
{
  unsigned int v9; // ebx
  CCbsTiPackage *v10; // rax
  CCbsTiPackage *v11; // rdi
  int SureWorkerSessionAvailable; // eax
  int v13; // eax
  int v14; // eax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, struct IUnknown **); // rcx
  char *v16; // rcx
  struct _GUID v18; // [rsp+30h] [rbp-68h] BYREF
  struct ICbsPackage *v19; // [rsp+40h] [rbp-58h] BYREF
  __int64 v20; // [rsp+48h] [rbp-50h] BYREF

  v20 = 0;
  v19 = 0;
  if ( a5 )
  {
    v10 = (CCbsTiPackage *)operator new(0x60u);
    if ( v10 && (v11 = CCbsTiPackage::CCbsTiPackage(v10, (CCbsTiSession *)((char *)this - 256))) != 0 )
    {
      SureWorkerSessionAvailable = CCbsTiSession::MakeSureWorkerSessionAvailable(
                                     (CCbsTiSession *)((char *)this - 256),
                                     1);
      v9 = SureWorkerSessionAvailable;
      if ( SureWorkerSessionAvailable >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct ICbsIdentity *, const wchar_t *, __int64 *))(**((_QWORD **)this - 27) + 48LL))(
                *((_QWORD *)this - 27),
                a2,
                a3,
                a4,
                &v20);
        v9 = v13;
        if ( v13 >= 0 )
        {
          v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ICbsPackage **))v20)(
                  v20,
                  &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed,
                  &v19);
          v9 = v14;
          if ( v14 >= 0 )
          {
            v18 = GUID_NULL;
            CCbsTiPackage::Initialize(v11, 0, v19, 0, &v18, 0);
            v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))((char *)v11
                                                                               + *(int *)(*((_QWORD *)v11 + 1) + 4LL)
                                                                               + 8);
            v9 = (**v15)(v15, &GUID_00000000_0000_0000_c000_000000000046, a5);
          }
          else
          {
            CBSWdsLogLight(0x4000000, (unsigned int)v14, 1, "Failed to query worker package.");
          }
        }
        else
        {
          CBSWdsLogLight(0x4000000, (unsigned int)v13, 1, "Failed to OpenPackage using worker session");
        }
      }
      else
      {
        CBSWdsLogLight(0x4000000, (unsigned int)SureWorkerSessionAvailable, 1, "Failed to get worker session.");
      }
      v16 = (char *)v11 + *(int *)(*((_QWORD *)v11 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    else
    {
      v9 = -2147024882;
      CBSWdsLogLight(0x4000000, 2147942414LL, 1, "Failed to allocate new Ti Package");
    }
  }
  else
  {
    v9 = -2147467261;
    CBSWdsLogLight(0x4000000, 2147500035LL, 1, "Invalid argument: ppPackage.");
  }
  if ( v19 )
    (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return v9;
}

```

## disassembly

```asm
0x140010a54  push    rbx
0x140010a56  push    rbp
0x140010a57  push    rsi
0x140010a58  push    rdi
0x140010a59  push    r12
0x140010a5b  push    r14
0x140010a5d  push    r15
0x140010a5f  sub     rsp, 60h
0x140010a63  mov     rax, cs:__security_cookie
0x140010a6a  xor     rax, rsp
0x140010a6d  mov     [rsp+98h+var_48], rax
0x140010a72  mov     rbp, [rsp+98h+arg_20]
0x140010a7a  mov     r12, r9
0x140010a7d  mov     r15, r8
0x140010a80  mov     [rsp+98h+var_50], 0
0x140010a89  mov     r14d, edx
0x140010a8c  mov     [rsp+98h+var_58], 0
0x140010a95  mov     rsi, rcx
0x140010a98  test    rbp, rbp
0x140010a9b  jnz     short loc_140010AAE
0x140010a9d  mov     ebx, 80004003h
0x140010aa2  lea     r9, aInvalidArgumen_26; "Invalid argument: ppPackage."
0x140010aa9  jmp     loc_140010BED
0x140010aae  mov     ecx, 60h ; '`'; Size
0x140010ab3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010ab8  test    rax, rax
0x140010abb  jz      loc_140010BE1
0x140010ac1  lea     rbx, [rsi-100h]
0x140010ac8  mov     rcx, rax; this
0x140010acb  mov     rdx, rbx; struct CCbsTiSession *
0x140010ace  call    ??0CCbsTiPackage@@QEAA@PEAVCCbsTiSession@@@Z; CCbsTiPackage::CCbsTiPackage(CCbsTiSession *)
0x140010ad3  mov     rdi, rax
0x140010ad6  test    rax, rax
0x140010ad9  jz      loc_140010BE1
0x140010adf  mov     dl, 1; bool
0x140010ae1  mov     rcx, rbx; this
0x140010ae4  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x140010ae9  mov     ebx, eax
0x140010aeb  test    eax, eax
0x140010aed  jns     short loc_140010B0D
0x140010aef  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x140010af6  mov     r8d, 1
0x140010afc  mov     edx, eax
0x140010afe  mov     ecx, 4000000h
0x140010b03  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140010b08  jmp     loc_140010BC4
0x140010b0d  mov     rcx, [rsi-0D8h]
0x140010b14  lea     rdx, [rsp+98h+var_50]
0x140010b19  mov     [rsp+98h+var_78], rdx
0x140010b1e  mov     r9, r12
0x140010b21  mov     r8, r15
0x140010b24  mov     edx, r14d
0x140010b27  mov     rax, [rcx]
0x140010b2a  mov     rax, [rax+30h]
0x140010b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b33  mov     ebx, eax
0x140010b35  test    eax, eax
0x140010b37  jns     short loc_140010B42
0x140010b39  lea     r9, aFailedToOpenpa; "Failed to OpenPackage using worker sess"...
0x140010b40  jmp     short loc_140010AF6
0x140010b42  mov     rcx, [rsp+98h+var_50]
0x140010b47  lea     r8, [rsp+98h+var_58]
0x140010b4c  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x140010b53  mov     rax, [rcx]
0x140010b56  mov     rax, [rax]
0x140010b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b5e  mov     ebx, eax
0x140010b60  test    eax, eax
0x140010b62  jns     short loc_140010B6D
0x140010b64  lea     r9, aFailedToQueryW; "Failed to query worker package."
0x140010b6b  jmp     short loc_140010AF6
0x140010b6d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140010b74  mov     r8, [rsp+98h+var_58]; struct ICbsPackage *
0x140010b79  lea     rax, [rsp+98h+var_68]
0x140010b7e  mov     [rsp+98h+var_70], 0; unsigned int
0x140010b86  xor     r9d, r9d; wchar_t *
0x140010b89  xor     edx, edx; wchar_t *
0x140010b8b  mov     [rsp+98h+var_78], rax; struct _GUID *
0x140010b90  mov     rcx, rdi; this
0x140010b93  movdqu  xmmword ptr [rsp+98h+var_68.Data1], xmm0
0x140010b99  call    ?Initialize@CCbsTiPackage@@QEAAJPEB_WPEAUICbsPackage@@0U_GUID@@I@Z; CCbsTiPackage::Initialize(wchar_t const *,ICbsPackage *,wchar_t const *,_GUID,uint)
0x140010b9e  mov     rax, [rdi+8]
0x140010ba2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140010ba9  mov     r8, rbp
0x140010bac  movsxd  rcx, dword ptr [rax+4]
0x140010bb0  add     rcx, 8
0x140010bb4  add     rcx, rdi
0x140010bb7  mov     rax, [rcx]
0x140010bba  mov     rax, [rax]
0x140010bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bc2  mov     ebx, eax
0x140010bc4  mov     rax, [rdi+8]
0x140010bc8  movsxd  rcx, dword ptr [rax+4]
0x140010bcc  add     rcx, 8
0x140010bd0  add     rcx, rdi
0x140010bd3  mov     rax, [rcx]
0x140010bd6  mov     rax, [rax+10h]
0x140010bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bdf  jmp     short loc_140010BFF
0x140010be1  mov     ebx, 8007000Eh
0x140010be6  lea     r9, aFailedToAlloca_2; "Failed to allocate new Ti Package"
0x140010bed  mov     r8d, 1
0x140010bf3  mov     edx, ebx
0x140010bf5  mov     ecx, 4000000h
0x140010bfa  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140010bff  mov     rcx, [rsp+98h+var_58]
0x140010c04  test    rcx, rcx
0x140010c07  jz      short loc_140010C15
0x140010c09  mov     rax, [rcx]
0x140010c0c  mov     rax, [rax+10h]
0x140010c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c15  mov     rcx, [rsp+98h+var_50]
0x140010c1a  test    rcx, rcx
0x140010c1d  jz      short loc_140010C2B
0x140010c1f  mov     rax, [rcx]
0x140010c22  mov     rax, [rax+10h]
0x140010c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c2b  mov     eax, ebx
0x140010c2d  mov     rcx, [rsp+98h+var_48]
0x140010c32  xor     rcx, rsp; StackCookie
0x140010c35  call    __security_check_cookie
0x140010c3a  add     rsp, 60h
0x140010c3e  pop     r15
0x140010c40  pop     r14
0x140010c42  pop     r12
0x140010c44  pop     rdi
0x140010c45  pop     rsi
0x140010c46  pop     rbp
0x140010c47  pop     rbx
0x140010c48  retn
```
