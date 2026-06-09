# CCbsTiSession::EnumeratePackages(uint,IEnumCbsIdentity * *)

- ea: `0x14000f8a4`
- end: `0x14000f929`
- name: `?EnumeratePackages@CCbsTiSession@@UEAAJIPEAPEAUIEnumCbsIdentity@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(CCbsTiSession *__hidden this, unsigned int, struct IEnumCbsIdentity **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000f890`

## callees

- `0x14000f8a4`
- `0x1400106c4`
- `0x140017658`
- `0x14002b010`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::EnumeratePackages(CCbsTiSession *this, unsigned int a2, struct IEnumCbsIdentity **a3)
{
  unsigned int v6; // ebx
  int SureWorkerSessionAvailable; // eax
  const char *v8; // r9

  if ( a3 )
  {
    SureWorkerSessionAvailable = CCbsTiSession::MakeSureWorkerSessionAvailable((CCbsTiSession *)((char *)this - 256), 1);
    v6 = SureWorkerSessionAvailable;
    if ( SureWorkerSessionAvailable >= 0 )
    {
      SureWorkerSessionAvailable = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IEnumCbsIdentity **))(**((_QWORD **)this - 27) + 56LL))(
                                     *((_QWORD *)this - 27),
                                     a2,
                                     a3);
      v6 = SureWorkerSessionAvailable;
      if ( SureWorkerSessionAvailable >= 0 )
        return v6;
      v8 = "Failed to EnumeratePackages using worker session";
    }
    else
    {
      v8 = "Failed to get worker session.";
    }
    CBSWdsLogLight(0x4000000u, (unsigned int)SureWorkerSessionAvailable, (size_t *)1, v8);
    return v6;
  }
  v6 = -2147467261;
  CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "Invalid argument: ppPackageList.");
  return v6;
}

```

## disassembly

```asm
0x14000f8a4  push    rbx
0x14000f8a6  push    rbp
0x14000f8a7  push    rsi
0x14000f8a8  push    rdi
0x14000f8a9  sub     rsp, 28h
0x14000f8ad  mov     rdi, r8
0x14000f8b0  mov     ebp, edx
0x14000f8b2  mov     rsi, rcx
0x14000f8b5  test    r8, r8
0x14000f8b8  jnz     short loc_14000F8CA
0x14000f8ba  mov     ebx, 80004003h
0x14000f8bf  lea     r9, aInvalidArgumen_18; "Invalid argument: ppPackageList."
0x14000f8c6  mov     edx, ebx
0x14000f8c8  jmp     short loc_14000F90E
0x14000f8ca  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x14000f8d1  mov     dl, 1; bool
0x14000f8d3  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x14000f8d8  mov     ebx, eax
0x14000f8da  test    eax, eax
0x14000f8dc  jns     short loc_14000F8E7
0x14000f8de  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x14000f8e5  jmp     short loc_14000F90C
0x14000f8e7  mov     rcx, [rsi-0D8h]
0x14000f8ee  mov     r8, rdi
0x14000f8f1  mov     edx, ebp
0x14000f8f3  mov     rax, [rcx]
0x14000f8f6  mov     rax, [rax+38h]
0x14000f8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8ff  mov     ebx, eax
0x14000f901  test    eax, eax
0x14000f903  jns     short loc_14000F91E
0x14000f905  lea     r9, aFailedToEnumer; "Failed to EnumeratePackages using worke"...
0x14000f90c  mov     edx, eax
0x14000f90e  mov     r8d, 1
0x14000f914  mov     ecx, 4000000h
0x14000f919  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000f91e  mov     eax, ebx
0x14000f920  add     rsp, 28h
0x14000f924  pop     rdi
0x14000f925  pop     rsi
0x14000f926  pop     rbp
0x14000f927  pop     rbx
0x14000f928  retn
```
