# CspConsoleIoRead

- ea: `0x14001f0e0`
- end: `0x14001f364`
- name: `CspConsoleIoRead`
- size: `644`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callees

- `0x14001e7d4`
- `0x14001e8e8`
- `0x14001e9b4`
- `0x14001f0e0`
- `0x14001f40c`
- `0x14001f5bc`
- `0x14001ff00`
- `0x1400204b0`
- `0x140021e10`
- `0x140024010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001f2a9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001f2f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001f2a9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001f2f6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001f275`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001f2d3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001f275`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001f2d3`
- `ntdll!RtlFreeHeap` at `0x14001f31d`
- `ntdll!RtlFreeHeap` at `0x14001f31d`
- `ntdll!NtClose` at `0x14001f305`
- `ntdll!NtClose` at `0x14001f305`

## pseudocode

```c
__int64 __fastcall CspConsoleIoRead(__int64 a1, __int64 a2, __int64 a3, int *a4)
{
  int *v5; // rdi
  char v6; // bp
  int v7; // ecx
  __int64 v8; // rax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int Console; // eax
  __int64 v16; // rdi
  _QWORD *v18; // rdi
  __int64 v19; // rdx
  _QWORD *v20; // rax
  void *v21; // rcx

  if ( *a4 < 0 )
  {
    *(_QWORD *)(a2 + 208) = 0;
    return CspReadNextConsoleIo(a2);
  }
  v5 = (int *)(a2 + 336);
  if ( !*(_QWORD *)(a2 + 328) || ((*v5 - 5) & 0xFFFFFFFD) != 0 )
  {
    v6 = 0;
  }
  else
  {
    v6 = 1;
    (**(void (__fastcall ***)(_QWORD))(a2 + 32))(*(_QWORD *)(a2 + 16));
    *(_WORD *)(a2 + 288) = *(_WORD *)(*(_QWORD *)(a2 + 328) + 52LL);
  }
  *(_QWORD *)(a2 + 224) = 0;
  *(_QWORD *)(a2 + 232) = 0;
  *(_QWORD *)(a2 + 240) = 0;
  *(_QWORD *)(a2 + 248) = 0;
  *(_OWORD *)(a2 + 256) = 0;
  *(_OWORD *)(a2 + 272) = 0;
  *(_QWORD *)(a2 + 288) = 0;
  v7 = *v5;
  v8 = *(_QWORD *)(a2 + 312);
  *(_QWORD *)(a2 + 208) = a2 + 216;
  *(_QWORD *)(a2 + 216) = v8;
  v9 = v7 - 1;
  if ( !v9 )
  {
    ConsoleHandleConnectionRequest((_QWORD *)a2);
    goto LABEL_34;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v18 = *(_QWORD **)(a2 + 320);
    *(_DWORD *)(a2 + 224) = 0;
    RtlAcquireSRWLockExclusive(a2 + 48);
    v19 = *v18;
    if ( *(_QWORD **)(*v18 + 8LL) != v18 || (v20 = (_QWORD *)v18[1], (_QWORD *)*v20 != v18) )
      __fastfail(3u);
    *v20 = v19;
    *(_QWORD *)(v19 + 8) = v20;
    RtlReleaseSRWLockExclusive(a2 + 48);
    v21 = (void *)v18[3];
    if ( v21 )
      NtClose(v21);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
    goto LABEL_34;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    ConsoleCreateObject(a2);
    goto LABEL_34;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v16 = *(_QWORD *)(a2 + 328);
    if ( v16 )
    {
      RtlAcquireSRWLockExclusive(a2 + 48);
      if ( (*(_DWORD *)(v16 + 16))-- == 1 )
      {
        CspFreeServerScreen(v16);
        if ( *(_QWORD *)(a2 + 96) == v16 )
        {
          *(_QWORD *)(a2 + 96) = *(_QWORD *)(a2 + 80);
          CspTriggerScreenRedraw(a2, a2 + 216, 0);
        }
      }
      RtlReleaseSRWLockExclusive(a2 + 48);
    }
    goto LABEL_34;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      if ( v14 == 1 )
        ConsoleDispatchRequest(a2);
      else
        *(_DWORD *)(a2 + 224) = -1073741823;
      goto LABEL_34;
    }
    *(_OWORD *)(a2 + 360) = 0;
    *(_DWORD *)(a2 + 376) = 0;
    *(_DWORD *)(a2 + 352) = 16777221;
    Console = SrvReadConsole(a2);
  }
  else
  {
    *(_QWORD *)(a2 + 360) = 0;
    *(_DWORD *)(a2 + 352) = 16777222;
    Console = SrvWriteConsole(a2);
  }
  if ( Console == 259 )
    *(_QWORD *)(a2 + 208) = 0;
  else
    *(_DWORD *)(a2 + 224) = Console;
LABEL_34:
  if ( v6 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(a2 + 32) + 8LL))(*(_QWORD *)(a2 + 16));
  return CspReadNextConsoleIo(a2);
}

```

## disassembly

```asm
0x14001f0e0  mov     [rsp+arg_0], rbx
0x14001f0e5  mov     [rsp+arg_8], rbp
0x14001f0ea  push    rsi
0x14001f0eb  push    rdi
0x14001f0ec  push    r14
0x14001f0ee  sub     rsp, 20h
0x14001f0f2  cmp     dword ptr [r9], 0
0x14001f0f6  mov     rbx, rdx
0x14001f0f9  jge     short loc_14001F10B
0x14001f0fb  mov     qword ptr [rdx+0D0h], 0
0x14001f106  jmp     loc_14001F34A
0x14001f10b  cmp     qword ptr [rdx+148h], 0
0x14001f113  lea     rdi, [rdx+150h]
0x14001f11a  jz      short loc_14001F14F
0x14001f11c  mov     eax, [rdi]
0x14001f11e  sub     eax, 5
0x14001f121  test    eax, 0FFFFFFFDh
0x14001f126  jnz     short loc_14001F14F
0x14001f128  mov     rax, [rdx+20h]
0x14001f12c  mov     bpl, 1
0x14001f12f  mov     rcx, [rdx+10h]
0x14001f133  mov     rax, [rax]
0x14001f136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f13b  mov     rax, [rbx+148h]
0x14001f142  movzx   ecx, word ptr [rax+34h]
0x14001f146  mov     [rbx+120h], cx
0x14001f14d  jmp     short loc_14001F152
0x14001f14f  xor     bpl, bpl
0x14001f152  mov     qword ptr [rbx+0E0h], 0
0x14001f15d  lea     r14, [rbx+0D8h]
0x14001f164  mov     qword ptr [rbx+0E8h], 0
0x14001f16f  xor     eax, eax
0x14001f171  mov     qword ptr [rbx+0F0h], 0
0x14001f17c  xorps   xmm0, xmm0
0x14001f17f  mov     qword ptr [rbx+0F8h], 0
0x14001f18a  movups  xmmword ptr [rbx+100h], xmm0
0x14001f191  movups  xmmword ptr [rbx+110h], xmm0
0x14001f198  mov     [rbx+120h], rax
0x14001f19f  mov     ecx, [rdi]
0x14001f1a1  mov     rax, [rbx+138h]
0x14001f1a8  mov     [rbx+0D0h], r14
0x14001f1af  mov     [r14], rax
0x14001f1b2  sub     ecx, 1
0x14001f1b5  jz      loc_14001F32C
0x14001f1bb  sub     ecx, 1
0x14001f1be  jz      loc_14001F2BE
0x14001f1c4  sub     ecx, 1
0x14001f1c7  jz      loc_14001F2B4
0x14001f1cd  sub     ecx, 1
0x14001f1d0  jz      loc_14001F261
0x14001f1d6  sub     ecx, 1
0x14001f1d9  jz      short loc_14001F234
0x14001f1db  sub     ecx, 1
0x14001f1de  jz      short loc_14001F201
0x14001f1e0  cmp     ecx, 1
0x14001f1e3  jz      short loc_14001F1F4
0x14001f1e5  mov     dword ptr [rbx+0E0h], 0C0000001h
0x14001f1ef  jmp     loc_14001F334
0x14001f1f4  mov     rcx, rbx
0x14001f1f7  call    ConsoleDispatchRequest
0x14001f1fc  jmp     loc_14001F334
0x14001f201  movups  xmmword ptr [rbx+168h], xmm0
0x14001f208  xor     eax, eax
0x14001f20a  mov     rcx, rbx
0x14001f20d  mov     [rbx+178h], eax
0x14001f213  mov     dword ptr [rbx+160h], 1000005h
0x14001f21d  call    SrvReadConsole
0x14001f222  cmp     eax, 103h
0x14001f227  jz      short loc_14001F251
0x14001f229  mov     [rbx+0E0h], eax
0x14001f22f  jmp     loc_14001F334
0x14001f234  xor     eax, eax
0x14001f236  mov     rcx, rbx
0x14001f239  mov     [rbx+168h], rax
0x14001f240  mov     dword ptr [rbx+160h], 1000006h
0x14001f24a  call    SrvWriteConsole
0x14001f24f  jmp     short loc_14001F222
0x14001f251  mov     qword ptr [rbx+0D0h], 0
0x14001f25c  jmp     loc_14001F334
0x14001f261  mov     rdi, [rbx+148h]
0x14001f268  test    rdi, rdi
0x14001f26b  jz      loc_14001F334
0x14001f271  lea     rcx, [rbx+30h]
0x14001f275  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14001f27b  add     dword ptr [rdi+10h], 0FFFFFFFFh
0x14001f27f  jnz     short loc_14001F2A5
0x14001f281  mov     rcx, rdi
0x14001f284  call    CspFreeServerScreen
0x14001f289  cmp     [rbx+60h], rdi
0x14001f28d  jnz     short loc_14001F2A5
0x14001f28f  mov     rax, [rbx+50h]
0x14001f293  xor     r8d, r8d
0x14001f296  mov     rdx, r14
0x14001f299  mov     [rbx+60h], rax
0x14001f29d  mov     rcx, rbx
0x14001f2a0  call    CspTriggerScreenRedraw
0x14001f2a5  lea     rcx, [rbx+30h]
0x14001f2a9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14001f2af  jmp     loc_14001F334
0x14001f2b4  mov     rcx, rbx
0x14001f2b7  call    ConsoleCreateObject
0x14001f2bc  jmp     short loc_14001F334
0x14001f2be  mov     rdi, [rbx+140h]
0x14001f2c5  lea     rcx, [rbx+30h]
0x14001f2c9  mov     dword ptr [rbx+0E0h], 0
0x14001f2d3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14001f2d9  mov     rdx, [rdi]
0x14001f2dc  cmp     [rdx+8], rdi
0x14001f2e0  jnz     short loc_14001F325
0x14001f2e2  mov     rax, [rdi+8]
0x14001f2e6  cmp     [rax], rdi
0x14001f2e9  jnz     short loc_14001F325
0x14001f2eb  mov     [rax], rdx
0x14001f2ee  lea     rcx, [rbx+30h]
0x14001f2f2  mov     [rdx+8], rax
0x14001f2f6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14001f2fc  mov     rcx, [rdi+18h]; Handle
0x14001f300  test    rcx, rcx
0x14001f303  jz      short loc_14001F30B
0x14001f305  call    cs:__imp_NtClose
0x14001f30b  mov     rcx, gs:60h
0x14001f314  mov     r8, rdi; P
0x14001f317  xor     edx, edx; Flags
0x14001f319  mov     rcx, [rcx+30h]; HeapHandle
0x14001f31d  call    cs:__imp_RtlFreeHeap
0x14001f323  jmp     short loc_14001F334
0x14001f325  mov     ecx, 3
0x14001f32a  int     29h; Win8: RtlFailFast(ecx)
0x14001f32c  mov     rcx, rbx
0x14001f32f  call    ConsoleHandleConnectionRequest
0x14001f334  test    bpl, bpl
0x14001f337  jz      short loc_14001F34A
0x14001f339  mov     rax, [rbx+20h]
0x14001f33d  mov     rcx, [rbx+10h]
0x14001f341  mov     rax, [rax+8]
0x14001f345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f34a  mov     rcx, rbx
0x14001f34d  mov     rbx, [rsp+38h+arg_0]
0x14001f352  mov     rbp, [rsp+38h+arg_8]
0x14001f357  add     rsp, 20h
0x14001f35b  pop     r14
0x14001f35d  pop     rdi
0x14001f35e  pop     rsi
0x14001f35f  jmp     CspReadNextConsoleIo
```
