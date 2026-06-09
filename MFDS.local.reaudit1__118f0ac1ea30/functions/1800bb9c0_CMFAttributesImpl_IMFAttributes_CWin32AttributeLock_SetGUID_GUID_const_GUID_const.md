# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x1800bb9c0`
- end: `0x1800bba63`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fe60`
- `0x1800bb9c0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bba49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bba49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb9d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb9d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bba03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bba03`

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
0x1800bb9c0  push    rbx
0x1800bb9c2  push    rbp
0x1800bb9c3  push    rsi
0x1800bb9c4  push    rdi
0x1800bb9c5  push    r14
0x1800bb9c7  sub     rsp, 20h
0x1800bb9cb  mov     rdi, rcx
0x1800bb9ce  mov     r14, r8
0x1800bb9d1  add     rcx, 8; lpCriticalSection
0x1800bb9d5  mov     rbx, rdx
0x1800bb9d8  call    cs:__imp_EnterCriticalSection
0x1800bb9df  nop     dword ptr [rax+rax+00h]
0x1800bb9e4  mov     rdx, rbx
0x1800bb9e7  mov     rcx, rdi
0x1800bb9ea  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x1800bb9ef  mov     rsi, rax
0x1800bb9f2  test    rax, rax
0x1800bb9f5  jnz     short loc_1800BB9FE
0x1800bb9f7  mov     ebx, 8007000Eh
0x1800bb9fc  jmp     short loc_1800BBA45
0x1800bb9fe  mov     ecx, 10h; cb
0x1800bba03  call    cs:__imp_CoTaskMemAlloc
0x1800bba0a  nop     dword ptr [rax+rax+00h]
0x1800bba0f  mov     [rsi+8], rax
0x1800bba13  test    rax, rax
0x1800bba16  jnz     short loc_1800BBA2F
0x1800bba18  mov     rax, [rdi]
0x1800bba1b  mov     rdx, rbx
0x1800bba1e  mov     rcx, rdi
0x1800bba21  mov     rax, [rax+98h]
0x1800bba28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bba2d  jmp     short loc_1800BB9F7
0x1800bba2f  mov     word ptr [rsi], 48h ; 'H'
0x1800bba34  xor     ebx, ebx
0x1800bba36  movups  xmm0, xmmword ptr [r14]
0x1800bba3a  movdqu  xmmword ptr [rax], xmm0
0x1800bba3e  mov     dword ptr [rdi+40h], 1
0x1800bba45  lea     rcx, [rdi+8]; lpCriticalSection
0x1800bba49  call    cs:__imp_LeaveCriticalSection
0x1800bba50  nop     dword ptr [rax+rax+00h]
0x1800bba55  mov     eax, ebx
0x1800bba57  add     rsp, 20h
0x1800bba5b  pop     r14
0x1800bba5d  pop     rdi
0x1800bba5e  pop     rsi
0x1800bba5f  pop     rbp
0x1800bba60  pop     rbx
0x1800bba61  retn
```
