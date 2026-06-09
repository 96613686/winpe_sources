# PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::Evaluate(TimeValue const &,void *,_CBROKERED_EVENT_ID,void * const,ulong)

- ea: `0x18000d310`
- end: `0x18000d3f6`
- name: `?Evaluate@TriggerAggregate@PRIVATE_NAMESPACE_Triggers_H@@EEAAHAEBVTimeValue@@PEAXU_CBROKERED_EVENT_ID@@QEAXK@Z`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d310`
- `0x18001dc2c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d336`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d34e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d34e`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::Evaluate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  unsigned int v11; // edi
  _QWORD *v12; // r15
  int v13; // edx
  int v14; // ecx
  BOOL v16; // esi
  __int64 v17; // rax
  _QWORD *v18; // rcx
  int v19; // edi
  int v20; // eax

  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 120);
  v11 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 120));
  v12 = *(_QWORD **)(a1 + 200);
  if ( v12 != (_QWORD *)(a1 + 200) )
  {
    v16 = *(_DWORD *)(a1 + 192) == 0;
    do
    {
      v17 = *(v12 - 1);
      v18 = v12 - 1;
      v12 = (_QWORD *)*v12;
      v19 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64, __int64, __int64, int))(v17 + 120))(
              v18,
              a2,
              a3,
              a4,
              a5,
              a6);
      v20 = v16 | v19;
      v11 = v16 & v19;
      if ( *(_DWORD *)(a1 + 192) )
        v11 = v20;
      v16 = v11;
    }
    while ( v12 != (_QWORD *)(a1 + 200) );
    v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 120);
  }
  LeaveCriticalSection(v6);
  if ( (byte_180030D05 & 4) != 0 )
    McTemplateU0jqt_EventWriteTransfer(v14, v13, *(_QWORD *)(a1 + 176) + 16, *(unsigned __int8 *)(a1 + 220), v11);
  return v11;
}

```

## disassembly

```asm
0x18000d310  push    rbx
0x18000d312  push    rbp
0x18000d313  push    rsi
0x18000d314  push    rdi
0x18000d315  push    r12
0x18000d317  push    r13
0x18000d319  push    r14
0x18000d31b  push    r15
0x18000d31d  sub     rsp, 48h
0x18000d321  lea     rsi, [rcx+78h]
0x18000d325  mov     rbp, rcx
0x18000d328  mov     rcx, rsi; lpCriticalSection
0x18000d32b  mov     rbx, r9
0x18000d32e  mov     r12, r8
0x18000d331  mov     r13, rdx
0x18000d334  xor     edi, edi
0x18000d336  call    cs:__imp_EnterCriticalSection
0x18000d33c  lea     r14, [rbp+0C8h]
0x18000d343  mov     r15, [r14]
0x18000d346  cmp     r15, r14
0x18000d349  jnz     short loc_18000D370
0x18000d34b  mov     rcx, rsi; lpCriticalSection
0x18000d34e  call    cs:__imp_LeaveCriticalSection
0x18000d354  test    cs:byte_180030D05, 4
0x18000d35b  jnz     short loc_18000D3D5
0x18000d35d  mov     eax, edi
0x18000d35f  add     rsp, 48h
0x18000d363  pop     r15
0x18000d365  pop     r14
0x18000d367  pop     r13
0x18000d369  pop     r12
0x18000d36b  pop     rdi
0x18000d36c  pop     rsi
0x18000d36d  pop     rbp
0x18000d36e  pop     rbx
0x18000d36f  retn
0x18000d370  xor     esi, esi
0x18000d372  cmp     [rbp+0C0h], esi
0x18000d378  setz    sil
0x18000d37c  nop     dword ptr [rax+00h]
0x18000d380  mov     rax, [r15-8]
0x18000d384  lea     rcx, [r15-8]
0x18000d388  mov     edx, [rsp+88h+arg_28]
0x18000d38f  mov     r9, rbx
0x18000d392  mov     r15, [r15]
0x18000d395  mov     r8, r12
0x18000d398  mov     [rsp+88h+var_60], edx
0x18000d39c  mov     rdx, [rsp+88h+arg_20]
0x18000d3a4  mov     rax, [rax+78h]
0x18000d3a8  mov     [rsp+88h+var_68], rdx
0x18000d3ad  mov     rdx, r13
0x18000d3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3b5  mov     edi, eax
0x18000d3b7  or      eax, esi
0x18000d3b9  and     edi, esi
0x18000d3bb  cmp     dword ptr [rbp+0C0h], 0
0x18000d3c2  cmovnz  edi, eax
0x18000d3c5  mov     esi, edi
0x18000d3c7  cmp     r15, r14
0x18000d3ca  jnz     short loc_18000D380
0x18000d3cc  lea     rsi, [rbp+78h]
0x18000d3d0  jmp     loc_18000D34B
0x18000d3d5  mov     r8, [rbp+0B0h]
0x18000d3dc  movzx   r9d, byte ptr [rbp+0DCh]
0x18000d3e4  add     r8, 10h
0x18000d3e8  mov     dword ptr [rsp+88h+var_68], edi
0x18000d3ec  call    McTemplateU0jqt_EventWriteTransfer
0x18000d3f1  jmp     loc_18000D35D
```
