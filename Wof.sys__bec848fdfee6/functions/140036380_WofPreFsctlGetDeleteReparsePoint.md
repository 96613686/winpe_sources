# WofPreFsctlGetDeleteReparsePoint

- ea: `0x140036380`
- end: `0x140036537`
- name: `WofPreFsctlGetDeleteReparsePoint`
- size: `439`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140034740`

## callees

- `0x140036380`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140036425`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400364c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140036425`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400364c4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036419`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400364b8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036419`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400364b8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400363d9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400363d9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400363ec`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400363ec`
- `FLTMGR!FltGetStreamContext` at `0x1400363b5`
- `FLTMGR!FltGetStreamContext` at `0x1400363b5`
- `FLTMGR!FltGetStreamHandleContext` at `0x140036487`
- `FLTMGR!FltGetStreamHandleContext` at `0x140036487`
- `FLTMGR!FltReleaseContext` at `0x140036436`
- `FLTMGR!FltReleaseContext` at `0x1400364a5`
- `FLTMGR!FltReleaseContext` at `0x1400364d5`
- `FLTMGR!FltReleaseContext` at `0x1400364fa`
- `FLTMGR!FltReleaseContext` at `0x140036524`
- `FLTMGR!FltReleaseContext` at `0x140036436`
- `FLTMGR!FltReleaseContext` at `0x1400364a5`
- `FLTMGR!FltReleaseContext` at `0x1400364d5`
- `FLTMGR!FltReleaseContext` at `0x1400364fa`
- `FLTMGR!FltReleaseContext` at `0x140036524`

## pseudocode

```c
__int64 __fastcall WofPreFsctlGetDeleteReparsePoint(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  _DWORD *v7; // rsi
  int v8; // eax
  bool v9; // bl
  struct _FILE_OBJECT *v10; // rdx
  struct _FLT_INSTANCE *v11; // rcx
  PFLT_CONTEXT v12; // [rsp+20h] [rbp-38h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp+18h] BYREF

  Context = 0;
  if ( !a4 && !byte_140018454
    || FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) < 0 )
  {
    return 1;
  }
  v7 = Context;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
  v8 = v7[2] & 0xF000000;
  if ( v8 == 0x1000000 )
  {
    v9 = 0;
  }
  else if ( v8 == 0x2000000 )
  {
    v9 = *(_QWORD *)(a2 + 40) == *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v7 + 16LL) + 56LL);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 40) )
    {
      v10 = *(struct _FILE_OBJECT **)(a2 + 32);
      v11 = *(struct _FLT_INSTANCE **)(a2 + 24);
      v12 = 0;
      if ( FltGetStreamHandleContext(v11, v10, &v12) != -1073741275 )
      {
        if ( (*(_DWORD *)v12 & 1) != 0 )
        {
          FltReleaseContext(v12);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
          KeLeaveCriticalRegion();
          FltReleaseContext(Context);
          return 1;
        }
        if ( (*(_DWORD *)v12 & 2) != 0 && v7[3] < 4u )
        {
          FltReleaseContext(v12);
          v9 = 0;
          goto LABEL_7;
        }
        FltReleaseContext(v12);
      }
    }
    v9 = 1;
  }
LABEL_7:
  if ( (v7[2] & 0x20) != 0 )
    v9 = 1;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
  KeLeaveCriticalRegion();
  FltReleaseContext(Context);
  if ( v9 )
    return 1;
  *(_DWORD *)(a1 + 24) = -1073741195;
  return 4;
}

```

## disassembly

```asm
0x140036380  mov     [rsp+Context], r8
0x140036385  push    rbx
0x140036386  push    rbp
0x140036387  push    rsi
0x140036388  push    rdi
0x140036389  sub     rsp, 38h
0x14003638d  xor     ebp, ebp
0x14003638f  mov     rbx, rdx
0x140036392  mov     [rsp+58h+Context], rbp
0x140036397  mov     rdi, rcx
0x14003639a  test    r9b, r9b
0x14003639d  jnz     short loc_1400363A8
0x14003639f  cmp     cs:byte_140018454, bpl
0x1400363a6  jz      short loc_1400363C5
0x1400363a8  mov     rdx, [rdx+20h]; FileObject
0x1400363ac  lea     r8, [rsp+58h+Context]; Context
0x1400363b1  mov     rcx, [rbx+18h]; Instance
0x1400363b5  call    cs:__imp_FltGetStreamContext
0x1400363bc  nop     dword ptr [rax+rax+00h]
0x1400363c1  test    eax, eax
0x1400363c3  jns     short loc_1400363D4
0x1400363c5  mov     eax, 1
0x1400363ca  add     rsp, 38h
0x1400363ce  pop     rdi
0x1400363cf  pop     rsi
0x1400363d0  pop     rbp
0x1400363d1  pop     rbx
0x1400363d2  retn
0x1400363d4  mov     rsi, [rsp+58h+Context]
0x1400363d9  call    cs:__imp_KeEnterCriticalRegion
0x1400363e0  nop     dword ptr [rax+rax+00h]
0x1400363e5  mov     rcx, [rsi]
0x1400363e8  add     rcx, 20h ; ' '; FastMutex
0x1400363ec  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400363f3  nop     dword ptr [rax+rax+00h]
0x1400363f8  mov     eax, [rsi+8]
0x1400363fb  and     eax, 0F000000h
0x140036400  cmp     eax, 1000000h
0x140036405  jnz     short loc_140036460
0x140036407  xor     bl, bl
0x140036409  mov     eax, [rsi+8]
0x14003640c  test    al, 20h
0x14003640e  jz      short loc_140036412
0x140036410  mov     bl, 1
0x140036412  mov     rcx, [rsi]
0x140036415  add     rcx, 20h ; ' '; FastMutex
0x140036419  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140036420  nop     dword ptr [rax+rax+00h]
0x140036425  call    cs:__imp_KeLeaveCriticalRegion
0x14003642c  nop     dword ptr [rax+rax+00h]
0x140036431  mov     rcx, [rsp+58h+Context]; Context
0x140036436  call    cs:__imp_FltReleaseContext
0x14003643d  nop     dword ptr [rax+rax+00h]
0x140036442  test    bl, bl
0x140036444  jnz     loc_1400363C5
0x14003644a  mov     dword ptr [rdi+18h], 0C0000275h
0x140036451  mov     eax, 4
0x140036456  add     rsp, 38h
0x14003645a  pop     rdi
0x14003645b  pop     rsi
0x14003645c  pop     rbp
0x14003645d  pop     rbx
0x14003645e  retn
0x140036460  cmp     eax, 2000000h
0x140036465  jz      loc_14003650D
0x14003646b  cmp     [rbx+28h], rbp
0x14003646f  jz      loc_140036506
0x140036475  mov     rdx, [rbx+20h]; FileObject
0x140036479  lea     r8, [rsp+58h+var_38]; Context
0x14003647e  mov     rcx, [rbx+18h]; Instance
0x140036482  mov     [rsp+58h+var_38], rbp
0x140036487  call    cs:__imp_FltGetStreamHandleContext
0x14003648e  nop     dword ptr [rax+rax+00h]
0x140036493  cmp     eax, 0C0000225h
0x140036498  jz      short loc_140036506
0x14003649a  mov     rcx, [rsp+58h+var_38]; Context
0x14003649f  mov     eax, [rcx]
0x1400364a1  test    al, 1
0x1400364a3  jz      short loc_1400364F0
0x1400364a5  call    cs:__imp_FltReleaseContext
0x1400364ac  nop     dword ptr [rax+rax+00h]
0x1400364b1  mov     rcx, [rsi]
0x1400364b4  add     rcx, 20h ; ' '; FastMutex
0x1400364b8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400364bf  nop     dword ptr [rax+rax+00h]
0x1400364c4  call    cs:__imp_KeLeaveCriticalRegion
0x1400364cb  nop     dword ptr [rax+rax+00h]
0x1400364d0  mov     rcx, [rsp+58h+Context]; Context
0x1400364d5  call    cs:__imp_FltReleaseContext
0x1400364dc  nop     dword ptr [rax+rax+00h]
0x1400364e1  mov     eax, 1
0x1400364e6  add     rsp, 38h
0x1400364ea  pop     rdi
0x1400364eb  pop     rsi
0x1400364ec  pop     rbp
0x1400364ed  pop     rbx
0x1400364ee  retn
0x1400364f0  test    al, 2
0x1400364f2  jz      short loc_1400364FA
0x1400364f4  cmp     dword ptr [rsi+0Ch], 4
0x1400364f8  jb      short loc_140036524
0x1400364fa  call    cs:__imp_FltReleaseContext
0x140036501  nop     dword ptr [rax+rax+00h]
0x140036506  mov     bl, 1
0x140036508  jmp     loc_140036409
0x14003650d  mov     rax, [rsi]
0x140036510  mov     rcx, [rax+10h]
0x140036514  mov     rax, [rcx+38h]
0x140036518  cmp     [rbx+28h], rax
0x14003651c  setz    bl
0x14003651f  jmp     loc_140036409
0x140036524  call    cs:__imp_FltReleaseContext
0x14003652b  nop     dword ptr [rax+rax+00h]
0x140036530  xor     bl, bl
0x140036532  jmp     loc_140036409
```
