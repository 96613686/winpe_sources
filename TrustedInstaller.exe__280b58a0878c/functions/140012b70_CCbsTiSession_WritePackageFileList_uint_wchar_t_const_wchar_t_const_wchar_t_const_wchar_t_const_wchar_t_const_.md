# CCbsTiSession::WritePackageFileList(uint,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x140012b70`
- end: `0x140012d17`
- name: `?WritePackageFileList@CCbsTiSession@@UEAAJIPEB_W00000@Z`
- size: `423`
- prototype: `__int64 __fastcall(CCbsTiSession *this, unsigned int, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400023e0`
- `0x140007630`
- `0x14000ee64`
- `0x1400106c4`
- `0x140011ad0`
- `0x140012b70`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x140012bd4`: `Invalid argument: szActionListPath.`
- `0x140012bec`: `Invalid argument: szSandboxPath.`
- `0x140012c1c`: `Invalid argument: szPackageFilePath.`
- `0x140012c34`: `Invalid argument: szFileListPath.`
- `0x140012cd4`: `Failed to call WritePackageFileList on TiWorker session`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::WritePackageFileList(
        CCbsTiSession *this,
        unsigned int a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        const wchar_t *a7,
        const wchar_t *a8)
{
  unsigned int v12; // ebx
  int SureWorkerSessionAvailable; // eax
  const char *v14; // r9
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  __int64 v18; // [rsp+58h] [rbp-60h] BYREF

  v18 = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      if ( a5 )
      {
        if ( a7 )
        {
          if ( a8 )
          {
            SureWorkerSessionAvailable = CCbsTiSession::MakeSureWorkerSessionAvailable(this, 0);
            v12 = SureWorkerSessionAvailable;
            if ( SureWorkerSessionAvailable >= 0 )
            {
              CCbsTiSession::RegisterTiUIHandler(this);
              v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)this + 5);
              InitPointer = Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v18);
              SureWorkerSessionAvailable = (**v15)(v15, &GUID_be996087_7c81_465a_9bb1_39ce7350adcd, InitPointer);
              v12 = SureWorkerSessionAvailable;
              if ( SureWorkerSessionAvailable >= 0 )
              {
                SureWorkerSessionAvailable = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v18 + 40LL))(
                                               v18,
                                               a2,
                                               a3,
                                               a4,
                                               a5,
                                               a6,
                                               a7,
                                               a8);
                v12 = SureWorkerSessionAvailable;
                if ( SureWorkerSessionAvailable >= 0 )
                  goto LABEL_18;
                v14 = "Failed to call WritePackageFileList on TiWorker session";
              }
              else
              {
                v14 = "Failed to query servicing processor";
              }
            }
            else
            {
              v14 = "Failed to get worker session.";
            }
            CBSWdsLogLight(0x4000000, (unsigned int)SureWorkerSessionAvailable, 1, v14);
            goto LABEL_18;
          }
          v12 = -2147467261;
          CBSWdsLogLight(0x4000000, 2147500035LL, 1, "Invalid argument: szFileListPath.");
        }
        else
        {
          v12 = -2147467261;
          CBSWdsLogLight(0x4000000, 2147500035LL, 1, "Invalid argument: szPackageFilePath.");
        }
      }
      else
      {
        v12 = -2147467261;
        CBSWdsLogLight(0x4000000, 2147500035LL, 1, "Invalid argument: szClientID.");
      }
    }
    else
    {
      v12 = -2147467261;
      CBSWdsLogLight(0x4000000, 2147500035LL, 1, "Invalid argument: szSandboxPath.");
    }
  }
  else
  {
    v12 = -2147467261;
    CBSWdsLogLight(0x4000000, 2147500035LL, 1, "Invalid argument: szActionListPath.");
  }
LABEL_18:
  Windows::AutoComPtr<ICbsServicingProcessor>::Close(&v18);
  return v12;
}

```

## disassembly

```asm
0x140012b70  push    rbx
0x140012b72  push    rbp
0x140012b73  push    rsi
0x140012b74  push    rdi
0x140012b75  push    r12
0x140012b77  push    r13
0x140012b79  push    r14
0x140012b7b  push    r15
0x140012b7d  sub     rsp, 78h
0x140012b81  mov     rax, cs:__security_cookie
0x140012b88  xor     rax, rsp
0x140012b8b  mov     [rsp+0B8h+var_58], rax
0x140012b90  mov     rax, [rsp+0B8h+arg_28]
0x140012b98  mov     rdi, r9
0x140012b9b  mov     rsi, [rsp+0B8h+arg_20]
0x140012ba3  mov     r12, r8
0x140012ba6  mov     rbp, [rsp+0B8h+arg_30]
0x140012bae  mov     r13d, edx
0x140012bb1  mov     r14, [rsp+0B8h+arg_38]
0x140012bb9  mov     r15, rcx
0x140012bbc  mov     [rsp+0B8h+var_68], rax
0x140012bc1  mov     [rsp+0B8h+var_60], 0
0x140012bca  test    r8, r8
0x140012bcd  jnz     short loc_140012BE2
0x140012bcf  mov     edx, 80004003h
0x140012bd4  lea     r9, aInvalidArgumen_34; "Invalid argument: szActionListPath."
0x140012bdb  mov     ebx, edx
0x140012bdd  jmp     loc_140012CDD
0x140012be2  test    rdi, rdi
0x140012be5  jnz     short loc_140012BFA
0x140012be7  mov     edx, 80004003h
0x140012bec  lea     r9, aInvalidArgumen_9; "Invalid argument: szSandboxPath."
0x140012bf3  mov     ebx, edx
0x140012bf5  jmp     loc_140012CDD
0x140012bfa  test    rsi, rsi
0x140012bfd  jnz     short loc_140012C12
0x140012bff  mov     edx, 80004003h
0x140012c04  lea     r9, aInvalidArgumen_20; "Invalid argument: szClientID."
0x140012c0b  mov     ebx, edx
0x140012c0d  jmp     loc_140012CDD
0x140012c12  test    rbp, rbp
0x140012c15  jnz     short loc_140012C2A
0x140012c17  mov     edx, 80004003h
0x140012c1c  lea     r9, aInvalidArgumen_22; "Invalid argument: szPackageFilePath."
0x140012c23  mov     ebx, edx
0x140012c25  jmp     loc_140012CDD
0x140012c2a  test    r14, r14
0x140012c2d  jnz     short loc_140012C42
0x140012c2f  mov     edx, 80004003h
0x140012c34  lea     r9, aInvalidArgumen_7; "Invalid argument: szFileListPath."
0x140012c3b  mov     ebx, edx
0x140012c3d  jmp     loc_140012CDD
0x140012c42  xor     edx, edx; bool
0x140012c44  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x140012c49  mov     ebx, eax
0x140012c4b  test    eax, eax
0x140012c4d  jns     short loc_140012C5B
0x140012c4f  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x140012c56  jmp     loc_140012CDB
0x140012c5b  mov     rcx, r15; this
0x140012c5e  call    ?RegisterTiUIHandler@CCbsTiSession@@QEAAXXZ; CCbsTiSession::RegisterTiUIHandler(void)
0x140012c63  mov     rbx, [r15+28h]
0x140012c67  lea     rcx, [rsp+0B8h+var_60]
0x140012c6c  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x140012c71  mov     rdx, [rbx]
0x140012c74  mov     r8, rax
0x140012c77  mov     rcx, rbx
0x140012c7a  mov     r9, [rdx]
0x140012c7d  lea     rdx, _GUID_be996087_7c81_465a_9bb1_39ce7350adcd
0x140012c84  mov     rax, r9
0x140012c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c8c  mov     ebx, eax
0x140012c8e  test    eax, eax
0x140012c90  jns     short loc_140012C9B
0x140012c92  lea     r9, aFailedToQueryS_0; "Failed to query servicing processor"
0x140012c99  jmp     short loc_140012CDB
0x140012c9b  mov     rdx, [rsp+0B8h+var_68]
0x140012ca0  mov     r9, rdi
0x140012ca3  mov     rcx, [rsp+0B8h+var_60]
0x140012ca8  mov     r8, r12
0x140012cab  mov     [rsp+0B8h+var_80], r14
0x140012cb0  mov     [rsp+0B8h+var_88], rbp
0x140012cb5  mov     [rsp+0B8h+var_90], rdx
0x140012cba  mov     edx, r13d
0x140012cbd  mov     rax, [rcx]
0x140012cc0  mov     [rsp+0B8h+var_98], rsi
0x140012cc5  mov     rax, [rax+28h]
0x140012cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012cce  mov     ebx, eax
0x140012cd0  test    eax, eax
0x140012cd2  jns     short loc_140012CED
0x140012cd4  lea     r9, aFailedToCallWr; "Failed to call WritePackageFileList on "...
0x140012cdb  mov     edx, eax
0x140012cdd  mov     r8d, 1
0x140012ce3  mov     ecx, 4000000h
0x140012ce8  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012ced  lea     rcx, [rsp+0B8h+var_60]
0x140012cf2  call    ?Close@?$AutoComPtr@UICbsServicingProcessor@@@Windows@@QEAAXXZ; Windows::AutoComPtr<ICbsServicingProcessor>::Close(void)
0x140012cf7  mov     eax, ebx
0x140012cf9  mov     rcx, [rsp+0B8h+var_58]
0x140012cfe  xor     rcx, rsp; StackCookie
0x140012d01  call    __security_check_cookie
0x140012d06  add     rsp, 78h
0x140012d0a  pop     r15
0x140012d0c  pop     r14
0x140012d0e  pop     r13
0x140012d10  pop     r12
0x140012d12  pop     rdi
0x140012d13  pop     rsi
0x140012d14  pop     rbp
0x140012d15  pop     rbx
0x140012d16  retn
```
