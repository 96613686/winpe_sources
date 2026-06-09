# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x1800481c0`
- end: `0x180048250`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007130`
- `0x1800481c0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004823d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004823d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800481d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800481d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800481fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800481fd`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 Item; // rsi
  unsigned int v7; // ebx
  _OWORD *v8; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v8 = CoTaskMemAlloc(0x10u);
    *(_QWORD *)(Item + 8) = v8;
    if ( v8 )
    {
      *(_WORD *)Item = 72;
      v7 = 0;
      *v8 = *a3;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v7 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x1800481c0  push    rbx
0x1800481c2  push    rbp
0x1800481c3  push    rsi
0x1800481c4  push    rdi
0x1800481c5  push    r14
0x1800481c7  sub     rsp, 20h
0x1800481cb  mov     rdi, rcx
0x1800481ce  mov     r14, r8
0x1800481d1  add     rcx, 8; lpCriticalSection
0x1800481d5  mov     rbx, rdx
0x1800481d8  call    cs:__imp_EnterCriticalSection
0x1800481de  mov     rdx, rbx
0x1800481e1  mov     rcx, rdi
0x1800481e4  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x1800481e9  mov     rsi, rax
0x1800481ec  test    rax, rax
0x1800481ef  jnz     short loc_1800481F8
0x1800481f1  mov     ebx, 8007000Eh
0x1800481f6  jmp     short loc_180048239
0x1800481f8  mov     ecx, 10h; cb
0x1800481fd  call    cs:__imp_CoTaskMemAlloc
0x180048203  mov     [rsi+8], rax
0x180048207  test    rax, rax
0x18004820a  jnz     short loc_180048223
0x18004820c  mov     rax, [rdi]
0x18004820f  mov     rdx, rbx
0x180048212  mov     rcx, rdi
0x180048215  mov     rax, [rax+98h]
0x18004821c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048221  jmp     short loc_1800481F1
0x180048223  mov     word ptr [rsi], 48h ; 'H'
0x180048228  xor     ebx, ebx
0x18004822a  movups  xmm0, xmmword ptr [r14]
0x18004822e  movdqu  xmmword ptr [rax], xmm0
0x180048232  mov     dword ptr [rdi+40h], 1
0x180048239  lea     rcx, [rdi+8]; lpCriticalSection
0x18004823d  call    cs:__imp_LeaveCriticalSection
0x180048243  mov     eax, ebx
0x180048245  add     rsp, 20h
0x180048249  pop     r14
0x18004824b  pop     rdi
0x18004824c  pop     rsi
0x18004824d  pop     rbp
0x18004824e  pop     rbx
0x18004824f  retn
```
