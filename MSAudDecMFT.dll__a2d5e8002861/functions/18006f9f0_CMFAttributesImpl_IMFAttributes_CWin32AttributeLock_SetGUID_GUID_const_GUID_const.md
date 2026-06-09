# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x18006f9f0`
- end: `0x18006fa94`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006e004`

## callees

- `0x18006cf6c`
- `0x18006f9f0`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fa7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fa7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006fa33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006fa33`

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
0x18006f9f0  push    rbx
0x18006f9f2  push    rbp
0x18006f9f3  push    rsi
0x18006f9f4  push    rdi
0x18006f9f5  push    r14
0x18006f9f7  sub     rsp, 20h
0x18006f9fb  mov     rdi, rcx
0x18006f9fe  mov     r14, r8
0x18006fa01  add     rcx, 8; lpCriticalSection
0x18006fa05  mov     rbx, rdx
0x18006fa08  call    cs:__imp_EnterCriticalSection
0x18006fa0f  nop     dword ptr [rax+rax+00h]
0x18006fa14  mov     rdx, rbx
0x18006fa17  mov     rcx, rdi
0x18006fa1a  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18006fa1f  mov     rsi, rax
0x18006fa22  test    rax, rax
0x18006fa25  jnz     short loc_18006FA2E
0x18006fa27  mov     ebx, 8007000Eh
0x18006fa2c  jmp     short loc_18006FA76
0x18006fa2e  mov     ecx, 10h; cb
0x18006fa33  call    cs:__imp_CoTaskMemAlloc
0x18006fa3a  nop     dword ptr [rax+rax+00h]
0x18006fa3f  mov     [rsi+8], rax
0x18006fa43  test    rax, rax
0x18006fa46  jnz     short loc_18006FA60
0x18006fa48  mov     rax, [rdi]
0x18006fa4b  mov     rdx, rbx
0x18006fa4e  mov     rcx, rdi
0x18006fa51  mov     rax, [rax+98h]
0x18006fa58  call    cs:__guard_dispatch_icall_fptr
0x18006fa5e  jmp     short loc_18006FA27
0x18006fa60  mov     word ptr [rsi], 48h ; 'H'
0x18006fa65  xor     ebx, ebx
0x18006fa67  movups  xmm0, xmmword ptr [r14]
0x18006fa6b  movdqu  xmmword ptr [rax], xmm0
0x18006fa6f  mov     dword ptr [rdi+40h], 1
0x18006fa76  lea     rcx, [rdi+8]; lpCriticalSection
0x18006fa7a  call    cs:__imp_LeaveCriticalSection
0x18006fa81  nop     dword ptr [rax+rax+00h]
0x18006fa86  mov     eax, ebx
0x18006fa88  add     rsp, 20h
0x18006fa8c  pop     r14
0x18006fa8e  pop     rdi
0x18006fa8f  pop     rsi
0x18006fa90  pop     rbp
0x18006fa91  pop     rbx
0x18006fa92  retn
```
