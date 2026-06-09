# CCbsTiSession::CreateCbsIdentity(ICbsIdentity * *)

- ea: `0x14000eee4`
- end: `0x14000ef72`
- name: `?CreateCbsIdentity@CCbsTiSession@@UEAAJPEAPEAUICbsIdentity@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(CCbsTiSession *__hidden this, struct ICbsIdentity **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000eed0`

## callees

- `0x14000eee4`
- `0x1400106c4`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x14000ef47`: `Failed to CreateCbsIdentity using worker session`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::CreateCbsIdentity(CCbsTiSession *this, struct ICbsIdentity **a2)
{
  unsigned int v4; // ebx
  int SureWorkerSessionAvailable; // eax
  const char *v6; // r9

  if ( a2 )
  {
    SureWorkerSessionAvailable = CCbsTiSession::MakeSureWorkerSessionAvailable((CCbsTiSession *)((char *)this - 256), 1);
    v4 = SureWorkerSessionAvailable;
    if ( SureWorkerSessionAvailable >= 0 )
    {
      SureWorkerSessionAvailable = (*(__int64 (__fastcall **)(_QWORD, struct ICbsIdentity **))(**((_QWORD **)this - 27)
                                                                                             + 64LL))(
                                     *((_QWORD *)this - 27),
                                     a2);
      v4 = SureWorkerSessionAvailable;
      if ( SureWorkerSessionAvailable >= 0 )
        return v4;
      v6 = "Failed to CreateCbsIdentity using worker session";
    }
    else
    {
      v6 = "Failed to get worker session.";
    }
    CBSWdsLogLight(0x4000000u, (unsigned int)SureWorkerSessionAvailable, (size_t *)1, v6);
    return v4;
  }
  v4 = -2147467261;
  CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "Invalid argument: ppIdentity.");
  return v4;
}

```

## disassembly

```asm
0x14000eee4  mov     [rsp+arg_0], rbx
0x14000eee9  mov     [rsp+arg_8], rsi
0x14000eeee  push    rdi
0x14000eeef  sub     rsp, 20h
0x14000eef3  mov     rdi, rdx
0x14000eef6  mov     rsi, rcx
0x14000eef9  test    rdx, rdx
0x14000eefc  jnz     short loc_14000EF0E
0x14000eefe  mov     ebx, 80004003h
0x14000ef03  lea     r9, aInvalidArgumen_28; "Invalid argument: ppIdentity."
0x14000ef0a  mov     edx, ebx
0x14000ef0c  jmp     short loc_14000EF50
0x14000ef0e  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x14000ef15  mov     dl, 1; bool
0x14000ef17  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x14000ef1c  mov     ebx, eax
0x14000ef1e  test    eax, eax
0x14000ef20  jns     short loc_14000EF2B
0x14000ef22  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x14000ef29  jmp     short loc_14000EF4E
0x14000ef2b  mov     rcx, [rsi-0D8h]
0x14000ef32  mov     rdx, rdi
0x14000ef35  mov     rax, [rcx]
0x14000ef38  mov     rax, [rax+40h]
0x14000ef3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef41  mov     ebx, eax
0x14000ef43  test    eax, eax
0x14000ef45  jns     short loc_14000EF60
0x14000ef47  lea     r9, aFailedToCreate_3; "Failed to CreateCbsIdentity using worke"...
0x14000ef4e  mov     edx, eax
0x14000ef50  mov     r8d, 1
0x14000ef56  mov     ecx, 4000000h
0x14000ef5b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ef60  mov     rsi, [rsp+28h+arg_8]
0x14000ef65  mov     eax, ebx
0x14000ef67  mov     rbx, [rsp+28h+arg_0]
0x14000ef6c  add     rsp, 20h
0x14000ef70  pop     rdi
0x14000ef71  retn
```
