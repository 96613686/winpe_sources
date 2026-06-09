# CCbsTiSxSStore::BeginAssemblyInstall(ulong)

- ea: `0x14000ede4`
- end: `0x14000ee5c`
- name: `?BeginAssemblyInstall@CCbsTiSxSStore@@UEAAJK@Z`
- size: `120`
- prototype: `__int64 __fastcall(CCbsTiSxSStore *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000edd0`

## callees

- `0x14000ede4`
- `0x1400108cc`
- `0x140017658`
- `0x1400200b8`
- `0x14002b010`

## string_xrefs

- `0x14000ee2d`: `Failed to create worker SxS store`

## pseudocode

```c
__int64 __fastcall CCbsTiSxSStore::BeginAssemblyInstall(CCbsTiSxSStore *this, unsigned int a2)
{
  int IsAdministrator; // eax
  unsigned int v5; // ebx
  int SureWorkerSxSStoreAvailable; // eax

  IsAdministrator = EnsureCallerIsAdministrator();
  v5 = IsAdministrator;
  if ( IsAdministrator >= 0 )
  {
    SureWorkerSxSStoreAvailable = CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable((CCbsTiSxSStore *)((char *)this - 88));
    v5 = SureWorkerSxSStoreAvailable;
    if ( SureWorkerSxSStoreAvailable >= 0 )
      return (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this - 2) + 24LL))(
               *((_QWORD *)this - 2),
               a2);
    else
      CBSWdsLogLight(0x4000000, (unsigned int)SureWorkerSxSStoreAvailable, 1, "Failed to create worker SxS store");
  }
  else
  {
    CBSWdsLogLight(0x4000000, (unsigned int)IsAdministrator, 1, "Client failed admin check.");
  }
  return v5;
}

```

## disassembly

```asm
0x14000ede4  mov     [rsp+arg_0], rbx
0x14000ede9  mov     [rsp+arg_8], rsi
0x14000edee  push    rdi
0x14000edef  sub     rsp, 20h
0x14000edf3  mov     esi, edx
0x14000edf5  mov     rdi, rcx
0x14000edf8  call    EnsureCallerIsAdministrator
0x14000edfd  mov     ebx, eax
0x14000edff  test    eax, eax
0x14000ee01  jns     short loc_14000EE1E
0x14000ee03  lea     r9, aClientFailedAd; "Client failed admin check."
0x14000ee0a  mov     r8d, 1
0x14000ee10  mov     edx, eax
0x14000ee12  mov     ecx, 4000000h
0x14000ee17  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ee1c  jmp     short loc_14000EE4A
0x14000ee1e  lea     rcx, [rdi-58h]; this
0x14000ee22  call    ?MakeSureWorkerSxSStoreAvailable@CCbsTiSxSStore@@AEAAJXZ; CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable(void)
0x14000ee27  mov     ebx, eax
0x14000ee29  test    eax, eax
0x14000ee2b  jns     short loc_14000EE36
0x14000ee2d  lea     r9, aFailedToCreate_15; "Failed to create worker SxS store"
0x14000ee34  jmp     short loc_14000EE0A
0x14000ee36  mov     rcx, [rdi-10h]
0x14000ee3a  mov     edx, esi
0x14000ee3c  mov     rax, [rcx]
0x14000ee3f  mov     rax, [rax+18h]
0x14000ee43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee48  mov     ebx, eax
0x14000ee4a  mov     rsi, [rsp+28h+arg_8]
0x14000ee4f  mov     eax, ebx
0x14000ee51  mov     rbx, [rsp+28h+arg_0]
0x14000ee56  add     rsp, 20h
0x14000ee5a  pop     rdi
0x14000ee5b  retn
```
