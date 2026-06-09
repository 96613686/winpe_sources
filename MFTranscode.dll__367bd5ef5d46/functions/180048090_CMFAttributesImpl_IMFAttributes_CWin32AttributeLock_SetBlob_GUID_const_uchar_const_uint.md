# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x180048090`
- end: `0x180048133`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007130`
- `0x180048090`
- `0x1800594bc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004811c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004811c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800480af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800480af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800480d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800480d2`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetBlob(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4)
{
  SIZE_T v5; // r15
  __int64 Item; // rsi
  unsigned int v9; // ebx
  void *v10; // rax

  v5 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v10 = CoTaskMemAlloc(v5);
    *(_QWORD *)(Item + 16) = v10;
    if ( v10 )
    {
      v9 = 0;
      memcpy_0(v10, a3, v5);
      *(_WORD *)Item = 4113;
      *(_DWORD *)(Item + 8) = v5;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v9 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v9;
}

```

## disassembly

```asm
0x180048090  push    rbx
0x180048092  push    rbp
0x180048093  push    rsi
0x180048094  push    rdi
0x180048095  push    r12
0x180048097  push    r14
0x180048099  push    r15
0x18004809b  sub     rsp, 20h
0x18004809f  mov     rdi, rcx
0x1800480a2  mov     r15d, r9d
0x1800480a5  add     rcx, 8; lpCriticalSection
0x1800480a9  mov     r12, r8
0x1800480ac  mov     rbx, rdx
0x1800480af  call    cs:__imp_EnterCriticalSection
0x1800480b5  mov     rdx, rbx
0x1800480b8  mov     rcx, rdi
0x1800480bb  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x1800480c0  mov     rsi, rax
0x1800480c3  test    rax, rax
0x1800480c6  jnz     short loc_1800480CF
0x1800480c8  mov     ebx, 8007000Eh
0x1800480cd  jmp     short loc_180048118
0x1800480cf  mov     rcx, r15; cb
0x1800480d2  call    cs:__imp_CoTaskMemAlloc
0x1800480d8  mov     [rsi+10h], rax
0x1800480dc  test    rax, rax
0x1800480df  jnz     short loc_1800480F8
0x1800480e1  mov     rax, [rdi]
0x1800480e4  mov     rdx, rbx
0x1800480e7  mov     rcx, rdi
0x1800480ea  mov     rax, [rax+98h]
0x1800480f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480f6  jmp     short loc_1800480C8
0x1800480f8  xor     ebx, ebx
0x1800480fa  mov     r8, r15; Size
0x1800480fd  mov     rdx, r12; Src
0x180048100  mov     rcx, rax; void *
0x180048103  call    memcpy_0
0x180048108  mov     word ptr [rsi], 1011h
0x18004810d  mov     [rsi+8], r15d
0x180048111  mov     dword ptr [rdi+40h], 1
0x180048118  lea     rcx, [rdi+8]; lpCriticalSection
0x18004811c  call    cs:__imp_LeaveCriticalSection
0x180048122  mov     eax, ebx
0x180048124  add     rsp, 20h
0x180048128  pop     r15
0x18004812a  pop     r14
0x18004812c  pop     r12
0x18004812e  pop     rdi
0x18004812f  pop     rsi
0x180048130  pop     rbp
0x180048131  pop     rbx
0x180048132  retn
```
