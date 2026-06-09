# NDXGI::CUMDAdapter::OpenAdapter<0>(void)

- ea: `0x18005fc0c`
- end: `0x18005fd50`
- name: `??$OpenAdapter@$0A@@CUMDAdapter@NDXGI@@IEAAJXZ`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180119ad8`
- `0x180119e94`

## callees

- `0x18005fc0c`
- `0x18007f054`
- `0x1800bc094`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fc67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fc67`

## string_xrefs

- `0x18005fc60`: `OpenAdapter12`
- `0x18005fc82`: `OpenAdapter12`
- `0x18005fd2d`: `OpenAdapter12`
- `0x18005fca5`: `Driver does not have OpenAdapter entrypoint`

## pseudocode

```c
__int64 __fastcall NDXGI::CUMDAdapter::OpenAdapter<0>(__int64 a1)
{
  __int64 v1; // rbx
  HMODULE v3; // rcx
  FARPROC ProcAddress; // rax
  __int64 v5; // rcx
  __int64 v6; // r9
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned int v10; // ebx
  void (__fastcall *v12)(__int64); // rax
  __int64 v13; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+38h] [rbp-20h]
  __int64 v15; // [rsp+40h] [rbp-18h]
  __int64 v16; // [rsp+48h] [rbp-10h]

  v1 = a1 + 488;
  memset_0((void *)(a1 + 488), 0, 0x40u);
  v3 = *(HMODULE *)(a1 + 392);
  v13 = a1;
  v14 = 0;
  v15 = a1 + 456;
  v16 = v1;
  if ( !v3 )
    v3 = *(HMODULE *)(a1 + 384);
  ProcAddress = GetProcAddress(v3, "OpenAdapter12");
  if ( !ProcAddress )
  {
    CJournal::RecordJournal(v5, -2005270526, (__int64)"Driver does not have OpenAdapter entrypoint", v6, 0);
    return 2289696770LL;
  }
  v7 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v13);
  v10 = v7;
  if ( v7 < 0 )
  {
    CJournal::RecordJournal(v8, v7, (__int64)"OpenAdapter12", v9, 0);
    return v10;
  }
  v12 = *(void (__fastcall **)(__int64))(a1 + 504);
  if ( v12 )
  {
    v8 = v14;
    if ( !*(_QWORD *)(a1 + 520) || !*(_QWORD *)(a1 + 512) || !*(_QWORD *)(a1 + 536) || !*(_QWORD *)(a1 + 528) )
    {
LABEL_16:
      if ( v14 )
        v12(v14);
      goto LABEL_18;
    }
    if ( v14 )
    {
      if ( *(_QWORD *)(a1 + 544) )
      {
        *(_QWORD *)(a1 + 552) = v14;
        *(_DWORD *)(a1 + 376) = 0;
        return v10;
      }
      goto LABEL_16;
    }
  }
LABEL_18:
  CJournal::RecordJournal(v8, -2005270524, (__int64)"OpenAdapter12", v9, 0);
  return 2289696772LL;
}

```

## disassembly

```asm
0x18005fc0c  mov     [rsp+arg_0], rbx
0x18005fc11  push    rdi
0x18005fc12  sub     rsp, 50h
0x18005fc16  xor     edx, edx; Val
0x18005fc18  lea     rbx, [rcx+1E8h]
0x18005fc1f  mov     rdi, rcx
0x18005fc22  mov     rcx, rbx; void *
0x18005fc25  lea     r8d, [rdx+40h]; Size
0x18005fc29  call    memset_0
0x18005fc2e  mov     rcx, [rdi+188h]
0x18005fc35  lea     rax, [rdi+1C8h]
0x18005fc3c  mov     [rsp+58h+var_28], rdi
0x18005fc41  mov     [rsp+58h+var_20], 0
0x18005fc4a  mov     [rsp+58h+var_18], rax
0x18005fc4f  mov     [rsp+58h+var_10], rbx
0x18005fc54  test    rcx, rcx
0x18005fc57  jnz     short loc_18005FC60
0x18005fc59  mov     rcx, [rdi+180h]; hModule
0x18005fc60  lea     rdx, aOpenadapter12; "OpenAdapter12"
0x18005fc67  call    cs:__imp_GetProcAddress
0x18005fc6d  test    rax, rax
0x18005fc70  jz      short loc_18005FCA5
0x18005fc72  lea     rcx, [rsp+58h+var_28]
0x18005fc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc7c  mov     ebx, eax
0x18005fc7e  test    eax, eax
0x18005fc80  jns     short loc_18005FCC5
0x18005fc82  lea     r8, aOpenadapter12; "OpenAdapter12"
0x18005fc89  mov     [rsp+58h+var_38], 0
0x18005fc91  mov     edx, eax
0x18005fc93  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005fc98  mov     eax, ebx
0x18005fc9a  mov     rbx, [rsp+58h+arg_0]
0x18005fc9f  add     rsp, 50h
0x18005fca3  pop     rdi
0x18005fca4  retn
0x18005fca5  lea     r8, aDriverDoesNotH; "Driver does not have OpenAdapter entryp"...
0x18005fcac  mov     [rsp+58h+var_38], 0
0x18005fcb4  mov     edx, 887A0002h
0x18005fcb9  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005fcbe  mov     eax, 887A0002h
0x18005fcc3  jmp     short loc_18005FC9A
0x18005fcc5  mov     rax, [rdi+1F8h]
0x18005fccc  test    rax, rax
0x18005fccf  jz      short loc_18005FD2D
0x18005fcd1  cmp     qword ptr [rdi+208h], 0
0x18005fcd9  mov     rcx, [rsp+58h+var_20]
0x18005fcde  jz      short loc_18005FD23
0x18005fce0  cmp     qword ptr [rdi+200h], 0
0x18005fce8  jz      short loc_18005FD23
0x18005fcea  cmp     qword ptr [rdi+218h], 0
0x18005fcf2  jz      short loc_18005FD23
0x18005fcf4  cmp     qword ptr [rdi+210h], 0
0x18005fcfc  jz      short loc_18005FD23
0x18005fcfe  test    rcx, rcx
0x18005fd01  jz      short loc_18005FD2D
0x18005fd03  cmp     qword ptr [rdi+220h], 0
0x18005fd0b  jz      short loc_18005FD23
0x18005fd0d  mov     [rdi+228h], rcx
0x18005fd14  mov     dword ptr [rdi+178h], 0
0x18005fd1e  jmp     loc_18005FC98
0x18005fd23  test    rcx, rcx
0x18005fd26  jz      short loc_18005FD2D
0x18005fd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd2d  lea     r8, aOpenadapter12; "OpenAdapter12"
0x18005fd34  mov     [rsp+58h+var_38], 0
0x18005fd3c  mov     edx, 887A0004h
0x18005fd41  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005fd46  mov     eax, 887A0004h
0x18005fd4b  jmp     loc_18005FC9A
```
