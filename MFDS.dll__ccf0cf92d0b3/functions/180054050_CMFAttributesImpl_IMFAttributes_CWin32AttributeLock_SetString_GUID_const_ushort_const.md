# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(_GUID const &,ushort const *)

- ea: `0x180054050`
- end: `0x180054130`
- name: `?SetString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fe60`
- `0x180054050`
- `0x180074a12`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054112`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054112`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005406c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005406c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800540c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800540c5`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(__int64 a1, __int64 a2, _WORD *a3)
{
  __int64 Item; // rax
  __int64 v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  size_t v11; // rbp
  void *v12; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
  v7 = Item;
  if ( !a3 )
    goto LABEL_2;
  if ( !Item )
  {
LABEL_4:
    v8 = -2147024882;
    goto LABEL_11;
  }
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = 2 * v9 + 2;
  if ( v10 < 0xFFFFFFFF )
  {
    v11 = (unsigned int)v10;
    v12 = CoTaskMemAlloc((unsigned int)v10);
    *(_QWORD *)(v7 + 8) = v12;
    if ( v12 )
    {
      v8 = 0;
      memcpy_0(v12, a3, v11);
      *(_WORD *)v7 = 31;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_11;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
    goto LABEL_4;
  }
LABEL_2:
  v8 = -2147024809;
LABEL_11:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v8;
}

```

## disassembly

```asm
0x180054050  push    rbx
0x180054052  push    rbp
0x180054053  push    rsi
0x180054054  push    rdi
0x180054055  push    r12
0x180054057  push    r14
0x180054059  push    r15
0x18005405b  sub     rsp, 20h
0x18005405f  mov     rdi, rcx
0x180054062  mov     r14, r8
0x180054065  add     rcx, 8; lpCriticalSection
0x180054069  mov     rbx, rdx
0x18005406c  call    cs:__imp_EnterCriticalSection
0x180054073  nop     dword ptr [rax+rax+00h]
0x180054078  mov     rdx, rbx
0x18005407b  mov     rcx, rdi
0x18005407e  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x180054083  xor     r12d, r12d
0x180054086  mov     rsi, rax
0x180054089  test    r14, r14
0x18005408c  jnz     short loc_180054095
0x18005408e  mov     ebx, 80070057h
0x180054093  jmp     short loc_18005410E
0x180054095  test    rsi, rsi
0x180054098  jnz     short loc_1800540A1
0x18005409a  mov     ebx, 8007000Eh
0x18005409f  jmp     short loc_18005410E
0x1800540a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800540a5  inc     rax
0x1800540a8  cmp     [r14+rax*2], r12w
0x1800540ad  jnz     short loc_1800540A5
0x1800540af  lea     rax, ds:2[rax*2]
0x1800540b7  mov     ecx, 0FFFFFFFFh
0x1800540bc  cmp     rax, rcx
0x1800540bf  jnb     short loc_18005408E
0x1800540c1  mov     ecx, eax; cb
0x1800540c3  mov     ebp, eax
0x1800540c5  call    cs:__imp_CoTaskMemAlloc
0x1800540cc  nop     dword ptr [rax+rax+00h]
0x1800540d1  mov     [rsi+8], rax
0x1800540d5  test    rax, rax
0x1800540d8  jnz     short loc_1800540F1
0x1800540da  mov     rax, [rdi]
0x1800540dd  mov     rdx, rbx
0x1800540e0  mov     rcx, rdi
0x1800540e3  mov     rax, [rax+98h]
0x1800540ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540ef  jmp     short loc_18005409A
0x1800540f1  mov     r8, rbp; Size
0x1800540f4  mov     rdx, r14; Src
0x1800540f7  mov     rcx, rax; void *
0x1800540fa  mov     ebx, r12d
0x1800540fd  call    memcpy_0
0x180054102  mov     word ptr [rsi], 1Fh
0x180054107  mov     dword ptr [rdi+40h], 1
0x18005410e  lea     rcx, [rdi+8]; lpCriticalSection
0x180054112  call    cs:__imp_LeaveCriticalSection
0x180054119  nop     dword ptr [rax+rax+00h]
0x18005411e  mov     eax, ebx
0x180054120  add     rsp, 20h
0x180054124  pop     r15
0x180054126  pop     r14
0x180054128  pop     r12
0x18005412a  pop     rdi
0x18005412b  pop     rsi
0x18005412c  pop     rbp
0x18005412d  pop     rbx
0x18005412e  retn
```
