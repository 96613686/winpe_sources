# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::SetString(_GUID const &,ushort const *)

- ea: `0x18009dbf0`
- end: `0x18009dcea`
- name: `?SetString@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180098fe4`
- `0x18009dbf0`
- `0x1800b0460`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009dc72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009dc72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009dcbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009dcbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009dc1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009dc1a`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::SetString(
        __int64 a1,
        __int64 a2,
        _WORD *a3)
{
  __int64 Item; // rax
  unsigned int v7; // ebx
  __int64 v8; // rsi
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  size_t v11; // rbp
  void *v12; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(a1, a2);
  v7 = 0;
  v8 = Item;
  if ( !a3 )
    goto LABEL_2;
  if ( !Item )
  {
LABEL_4:
    v7 = -2147024882;
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
    *(_QWORD *)(v8 + 8) = v12;
    if ( v12 )
    {
      memmove(v12, a3, v11);
      *(_WORD *)v8 = 31;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_11;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
    goto LABEL_4;
  }
LABEL_2:
  v7 = -2147024809;
LABEL_11:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x18009dbf0  mov     rax, rsp
0x18009dbf3  mov     [rax+8], rbx
0x18009dbf7  mov     [rax+10h], rbp
0x18009dbfb  mov     [rax+18h], rsi
0x18009dbff  mov     [rax+20h], rdi
0x18009dc03  push    r12
0x18009dc05  push    r14
0x18009dc07  push    r15
0x18009dc09  sub     rsp, 20h
0x18009dc0d  mov     rdi, rcx
0x18009dc10  mov     r14, r8
0x18009dc13  add     rcx, 8; lpCriticalSection
0x18009dc17  mov     r12, rdx
0x18009dc1a  call    cs:__imp_EnterCriticalSection
0x18009dc21  nop     dword ptr [rax+rax+00h]
0x18009dc26  mov     rdx, r12
0x18009dc29  mov     rcx, rdi
0x18009dc2c  call    ?CreateItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18009dc31  xor     ebx, ebx
0x18009dc33  mov     rsi, rax
0x18009dc36  test    r14, r14
0x18009dc39  jnz     short loc_18009DC42
0x18009dc3b  mov     ebx, 80070057h
0x18009dc40  jmp     short loc_18009DCB8
0x18009dc42  test    rsi, rsi
0x18009dc45  jnz     short loc_18009DC4E
0x18009dc47  mov     ebx, 8007000Eh
0x18009dc4c  jmp     short loc_18009DCB8
0x18009dc4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009dc52  inc     rax
0x18009dc55  cmp     [r14+rax*2], bx
0x18009dc5a  jnz     short loc_18009DC52
0x18009dc5c  lea     rax, ds:2[rax*2]
0x18009dc64  mov     ecx, 0FFFFFFFFh
0x18009dc69  cmp     rax, rcx
0x18009dc6c  jnb     short loc_18009DC3B
0x18009dc6e  mov     ecx, eax; cb
0x18009dc70  mov     ebp, eax
0x18009dc72  call    cs:__imp_CoTaskMemAlloc
0x18009dc79  nop     dword ptr [rax+rax+00h]
0x18009dc7e  mov     [rsi+8], rax
0x18009dc82  test    rax, rax
0x18009dc85  jnz     short loc_18009DC9E
0x18009dc87  mov     rax, [rdi]
0x18009dc8a  mov     rdx, r12
0x18009dc8d  mov     rcx, rdi
0x18009dc90  mov     rax, [rax+98h]
0x18009dc97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dc9c  jmp     short loc_18009DC47
0x18009dc9e  mov     r8, rbp; Size
0x18009dca1  mov     rdx, r14; Src
0x18009dca4  mov     rcx, rax; void *
0x18009dca7  call    memmove
0x18009dcac  mov     word ptr [rsi], 1Fh
0x18009dcb1  mov     dword ptr [rdi+40h], 1
0x18009dcb8  lea     rcx, [rdi+8]; lpCriticalSection
0x18009dcbc  call    cs:__imp_LeaveCriticalSection
0x18009dcc3  nop     dword ptr [rax+rax+00h]
0x18009dcc8  mov     rbp, [rsp+38h+arg_8]
0x18009dccd  mov     eax, ebx
0x18009dccf  mov     rbx, [rsp+38h+arg_0]
0x18009dcd4  mov     rsi, [rsp+38h+arg_10]
0x18009dcd9  mov     rdi, [rsp+38h+arg_18]
0x18009dcde  add     rsp, 20h
0x18009dce2  pop     r15
0x18009dce4  pop     r14
0x18009dce6  pop     r12
0x18009dce8  retn
```
