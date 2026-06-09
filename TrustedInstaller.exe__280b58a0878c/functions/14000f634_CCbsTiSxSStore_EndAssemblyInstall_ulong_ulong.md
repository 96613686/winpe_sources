# CCbsTiSxSStore::EndAssemblyInstall(ulong,ulong *)

- ea: `0x14000f634`
- end: `0x14000f6ba`
- name: `?EndAssemblyInstall@CCbsTiSxSStore@@UEAAJKPEAK@Z`
- size: `134`
- prototype: `__int64 __fastcall(CCbsTiSxSStore *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000f620`

## callees

- `0x14000f634`
- `0x1400108cc`
- `0x140017658`
- `0x1400200b8`
- `0x14002b010`

## string_xrefs

- `0x14000f68f`: `Failed to create worker SxS store`

## pseudocode

```c
__int64 __fastcall CCbsTiSxSStore::EndAssemblyInstall(CCbsTiSxSStore *this, unsigned int a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  const char *v7; // r9
  size_t v8; // rdx
  int IsAdministrator; // eax

  if ( a3 )
  {
    IsAdministrator = EnsureCallerIsAdministrator();
    v6 = IsAdministrator;
    if ( IsAdministrator >= 0 )
    {
      IsAdministrator = CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable((CCbsTiSxSStore *)((char *)this - 88));
      v6 = IsAdministrator;
      if ( IsAdministrator >= 0 )
        return (*(unsigned int (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)this - 2) + 40LL))(
                 *((_QWORD *)this - 2),
                 a2,
                 a3);
      v7 = "Failed to create worker SxS store";
    }
    else
    {
      v7 = "Client failed admin check.";
    }
    v8 = (unsigned int)IsAdministrator;
  }
  else
  {
    v6 = -2147467261;
    v7 = "Invalid argument: pdwDisposition.";
    v8 = 2147500035LL;
  }
  CBSWdsLogLight(0x4000000u, v8, (size_t *)1, v7);
  return v6;
}

```

## disassembly

```asm
0x14000f634  push    rbx
0x14000f636  push    rbp
0x14000f637  push    rsi
0x14000f638  push    rdi
0x14000f639  sub     rsp, 28h
0x14000f63d  mov     rsi, r8
0x14000f640  mov     ebp, edx
0x14000f642  mov     rdi, rcx
0x14000f645  test    r8, r8
0x14000f648  jnz     short loc_14000F66A
0x14000f64a  mov     ebx, 80004003h
0x14000f64f  lea     r9, aInvalidArgumen_6; "Invalid argument: pdwDisposition."
0x14000f656  mov     edx, ebx
0x14000f658  mov     r8d, 1
0x14000f65e  mov     ecx, 4000000h
0x14000f663  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000f668  jmp     short loc_14000F6AF
0x14000f66a  call    EnsureCallerIsAdministrator
0x14000f66f  mov     ebx, eax
0x14000f671  test    eax, eax
0x14000f673  jns     short loc_14000F680
0x14000f675  lea     r9, aClientFailedAd; "Client failed admin check."
0x14000f67c  mov     edx, eax
0x14000f67e  jmp     short loc_14000F658
0x14000f680  lea     rcx, [rdi-58h]; this
0x14000f684  call    ?MakeSureWorkerSxSStoreAvailable@CCbsTiSxSStore@@AEAAJXZ; CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable(void)
0x14000f689  mov     ebx, eax
0x14000f68b  test    eax, eax
0x14000f68d  jns     short loc_14000F698
0x14000f68f  lea     r9, aFailedToCreate_15; "Failed to create worker SxS store"
0x14000f696  jmp     short loc_14000F67C
0x14000f698  mov     rcx, [rdi-10h]
0x14000f69c  mov     r8, rsi
0x14000f69f  mov     edx, ebp
0x14000f6a1  mov     rax, [rcx]
0x14000f6a4  mov     rax, [rax+28h]
0x14000f6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6ad  mov     ebx, eax
0x14000f6af  mov     eax, ebx
0x14000f6b1  add     rsp, 28h
0x14000f6b5  pop     rdi
0x14000f6b6  pop     rsi
0x14000f6b7  pop     rbp
0x14000f6b8  pop     rbx
0x14000f6b9  retn
```
