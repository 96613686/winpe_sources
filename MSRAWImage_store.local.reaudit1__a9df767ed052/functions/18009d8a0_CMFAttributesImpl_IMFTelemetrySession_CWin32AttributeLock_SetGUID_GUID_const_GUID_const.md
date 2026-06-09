# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x18009d8a0`
- end: `0x18009d95e`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180098fe4`
- `0x18009d8a0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d8f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d8f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d936`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d936`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d8c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d8c5`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::SetGUID(
        __int64 a1,
        __int64 a2,
        _OWORD *a3)
{
  unsigned int v6; // ebx
  __int64 Item; // rsi
  _OWORD *v8; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v6 = 0;
  Item = CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v8 = CoTaskMemAlloc(0x10u);
    *(_QWORD *)(Item + 8) = v8;
    if ( v8 )
    {
      *(_WORD *)Item = 72;
      *v8 = *a3;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v6 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v6;
}

```

## disassembly

```asm
0x18009d8a0  mov     [rsp+arg_0], rbx
0x18009d8a5  mov     [rsp+arg_8], rbp
0x18009d8aa  mov     [rsp+arg_10], rsi
0x18009d8af  push    rdi
0x18009d8b0  push    r14
0x18009d8b2  push    r15
0x18009d8b4  sub     rsp, 20h
0x18009d8b8  mov     rdi, rcx
0x18009d8bb  mov     r15, r8
0x18009d8be  add     rcx, 8; lpCriticalSection
0x18009d8c2  mov     r14, rdx
0x18009d8c5  call    cs:__imp_EnterCriticalSection
0x18009d8cc  nop     dword ptr [rax+rax+00h]
0x18009d8d1  mov     rdx, r14
0x18009d8d4  mov     rcx, rdi
0x18009d8d7  call    ?CreateItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18009d8dc  xor     ebx, ebx
0x18009d8de  mov     rsi, rax
0x18009d8e1  test    rax, rax
0x18009d8e4  jnz     short loc_18009D8ED
0x18009d8e6  mov     ebx, 8007000Eh
0x18009d8eb  jmp     short loc_18009D932
0x18009d8ed  mov     ecx, 10h; cb
0x18009d8f2  call    cs:__imp_CoTaskMemAlloc
0x18009d8f9  nop     dword ptr [rax+rax+00h]
0x18009d8fe  mov     [rsi+8], rax
0x18009d902  test    rax, rax
0x18009d905  jnz     short loc_18009D91E
0x18009d907  mov     rax, [rdi]
0x18009d90a  mov     rdx, r14
0x18009d90d  mov     rcx, rdi
0x18009d910  mov     rax, [rax+98h]
0x18009d917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d91c  jmp     short loc_18009D8E6
0x18009d91e  mov     word ptr [rsi], 48h ; 'H'
0x18009d923  movups  xmm0, xmmword ptr [r15]
0x18009d927  movdqu  xmmword ptr [rax], xmm0
0x18009d92b  mov     dword ptr [rdi+40h], 1
0x18009d932  lea     rcx, [rdi+8]; lpCriticalSection
0x18009d936  call    cs:__imp_LeaveCriticalSection
0x18009d93d  nop     dword ptr [rax+rax+00h]
0x18009d942  mov     rbp, [rsp+38h+arg_8]
0x18009d947  mov     eax, ebx
0x18009d949  mov     rbx, [rsp+38h+arg_0]
0x18009d94e  mov     rsi, [rsp+38h+arg_10]
0x18009d953  add     rsp, 20h
0x18009d957  pop     r15
0x18009d959  pop     r14
0x18009d95b  pop     rdi
0x18009d95c  retn
```
