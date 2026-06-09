# VidClientBufferShare

- ea: `0x1400f0210`
- end: `0x1400f0498`
- name: `VidClientBufferShare`
- size: `648`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID Object, __int64)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140008674`
- `0x140008db8`
- `0x14007ad9c`
- `0x14007b144`
- `0x1400856d4`
- `0x14008aad0`
- `0x14008b1c0`
- `0x14008b320`
- `0x1400ef750`
- `0x1400efa4c`
- `0x1400f0158`
- `0x14010092c`

## callees

- `0x140021c60`
- `0x1400f0010`
- `0x1400f0210`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f0460`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f0460`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400f02de`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400f02de`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f02ee`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f02ee`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400f032c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400f032c`
- `ntoskrnl!ExAllocatePool2` at `0x1400f03f7`
- `ntoskrnl!ExAllocatePool2` at `0x1400f03f7`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f0442`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f0442`

## pseudocode

```c
__int64 __fastcall VidClientBufferShare(__int64 a1, __int64 a2, _QWORD *a3, int a4, PVOID Object, _QWORD *a6)
{
  _QWORD *v7; // rdi
  unsigned int v10; // esi
  _QWORD *v11; // r15
  _QWORD *v12; // rax
  char v13; // r15
  struct _KPROCESS *v14; // r14
  ULONG Priority; // eax
  __int64 v16; // rax
  _QWORD **v18; // rcx
  _QWORD *v19; // rdx
  __int64 Pool2; // rax
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  struct _KAPC_STATE ApcState; // [rsp+50h] [rbp-68h] BYREF

  v7 = a3;
  memset(&ApcState, 0, sizeof(ApcState));
  v10 = 0;
  if ( a6 )
    *a6 = 0;
  if ( !*(_QWORD *)(a1 + 24) && !*(_QWORD *)(a1 + 32) )
  {
    v11 = (_QWORD *)(a1 + 40);
    if ( a3 != (_QWORD *)a1 || (_QWORD *)*v11 == v11 )
    {
      v12 = 0;
      if ( a2 )
      {
        v18 = (_QWORD **)(a1 + 40);
        v19 = *v18;
        if ( *v18 == v18 )
        {
          v11 = v18;
        }
        else
        {
          do
          {
            v12 = v19 - 1;
            v11 = v18;
            if ( *(v19 - 1) == a2 )
              break;
            v19 = (_QWORD *)*v19;
            v12 = 0;
          }
          while ( v19 != v18 );
        }
      }
      if ( !v12 )
      {
        if ( a3 != (_QWORD *)a1 )
        {
          Pool2 = ExAllocatePool2(64, 40, 1917084758);
          v21 = (_QWORD *)Pool2;
          if ( !Pool2 )
            goto LABEL_30;
          v22 = (_QWORD *)v11[1];
          if ( (_QWORD *)*v22 != v11 )
            __fastfail(3u);
          v23 = (_QWORD *)(Pool2 + 8);
          *v23 = v11;
          v23[1] = v22;
          *v22 = v23;
          v11[1] = v23;
          v7 = v21;
        }
        v13 = 0;
        *v7 = a2;
        v7[3] = Object;
        ObfReferenceObjectWithTag(Object, 0x72446456u);
        v14 = (struct _KPROCESS *)v7[3];
        if ( v14 != (struct _KPROCESS *)PsGetCurrentProcess() )
        {
          KeStackAttachProcess(v14, &ApcState);
          v13 = 1;
        }
        Priority = -536870896;
        if ( !a4 )
          Priority = 1610612752;
        v7[4] = MmMapLockedPagesSpecifyCache(*(PMDL *)(a1 + 56), 1, MmCached, 0, 0, Priority);
        if ( v13 )
          KeUnstackDetachProcess(&ApcState);
        v16 = v7[4];
        if ( v16 )
        {
          if ( a6 )
            *a6 = v16;
          return v10;
        }
LABEL_30:
        v10 = -1073741670;
        if ( v7 )
          VidClientBufferpUnShareInternal(a1, v7);
        return v10;
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400f0210  mov     [rsp+arg_8], rbx
0x1400f0215  mov     [rsp+arg_18], rsi
0x1400f021a  push    rdi
0x1400f021b  push    r12
0x1400f021d  push    r13
0x1400f021f  push    r14
0x1400f0221  push    r15
0x1400f0223  sub     rsp, 90h
0x1400f022a  mov     rax, cs:__security_cookie
0x1400f0231  xor     rax, rsp
0x1400f0234  mov     [rsp+0B8h+var_38], rax
0x1400f023c  mov     r13d, r9d
0x1400f023f  mov     rdi, r8
0x1400f0242  mov     r14, rdx
0x1400f0245  mov     rbx, rcx
0x1400f0248  mov     [rsp+0B8h+var_78], rcx
0x1400f024d  mov     [rsp+0B8h+var_80], r8
0x1400f0252  mov     r12, [rsp+0B8h+arg_28]
0x1400f025a  mov     [rsp+0B8h+var_70], r12
0x1400f025f  xorps   xmm0, xmm0
0x1400f0262  movups  xmmword ptr [rsp+0B8h+ApcState.ApcListHead.Flink], xmm0
0x1400f0267  movups  xmmword ptr [rsp+0B8h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400f026c  movups  xmmword ptr [rsp+0B8h+ApcState.Process], xmm0
0x1400f0271  xor     esi, esi
0x1400f0273  test    r12, r12
0x1400f0276  jz      short loc_1400F027C
0x1400f0278  mov     [r12], rsi
0x1400f027c  cmp     qword ptr [rcx+18h], 0
0x1400f0281  jnz     loc_1400F03AC
0x1400f0287  cmp     qword ptr [rcx+20h], 0
0x1400f028c  jnz     loc_1400F03AC
0x1400f0292  lea     r15, [rcx+28h]
0x1400f0296  cmp     rdi, rbx
0x1400f0299  jnz     short loc_1400F02A4
0x1400f029b  cmp     [r15], r15
0x1400f029e  jnz     loc_1400F03AC
0x1400f02a4  mov     rax, rsi
0x1400f02a7  test    r14, r14
0x1400f02aa  jnz     loc_1400F03B3
0x1400f02b0  test    rax, rax
0x1400f02b3  jnz     loc_1400F03AC
0x1400f02b9  cmp     rdi, rbx
0x1400f02bc  jnz     loc_1400F03E7
0x1400f02c2  xor     r15b, r15b
0x1400f02c5  mov     [rsp+0B8h+var_88], r15b
0x1400f02ca  mov     [rdi], r14
0x1400f02cd  mov     rcx, [rsp+0B8h+Object]; Object
0x1400f02d5  mov     [rdi+18h], rcx
0x1400f02d9  mov     edx, 72446456h; Tag
0x1400f02de  call    cs:__imp_ObfReferenceObjectWithTag
0x1400f02e5  nop     dword ptr [rax+rax+00h]
0x1400f02ea  mov     r14, [rdi+18h]
0x1400f02ee  call    cs:__imp_PsGetCurrentProcess
0x1400f02f5  nop     dword ptr [rax+rax+00h]
0x1400f02fa  cmp     r14, rax
0x1400f02fd  jnz     loc_1400F043A
0x1400f0303  mov     eax, 0E0000010h
0x1400f0308  mov     ecx, 60000010h
0x1400f030d  test    r13d, r13d
0x1400f0310  cmovz   eax, ecx
0x1400f0313  mov     [rsp+0B8h+Priority], eax; Priority
0x1400f0317  mov     [rsp+0B8h+BugCheckOnFailure], esi; BugCheckOnFailure
0x1400f031b  xor     r9d, r9d; RequestedAddress
0x1400f031e  mov     r8d, 1; CacheType
0x1400f0324  movzx   edx, r8b; AccessMode
0x1400f0328  mov     rcx, [rbx+38h]; MemoryDescriptorList
0x1400f032c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400f0333  nop     dword ptr [rax+rax+00h]
0x1400f0338  mov     [rdi+20h], rax
0x1400f033c  jmp     short loc_1400F035D
0x1400f033e  mov     rdi, [rsp+0B8h+var_80]
0x1400f0343  mov     qword ptr [rdi+20h], 0
0x1400f034b  xor     esi, esi
0x1400f034d  movzx   r15d, [rsp+0B8h+var_88]
0x1400f0353  mov     rbx, [rsp+0B8h+var_78]
0x1400f0358  mov     r12, [rsp+0B8h+var_70]
0x1400f035d  test    r15b, r15b
0x1400f0360  jnz     loc_1400F045B
0x1400f0366  mov     rax, [rdi+20h]
0x1400f036a  test    rax, rax
0x1400f036d  jz      loc_1400F0471
0x1400f0373  test    r12, r12
0x1400f0376  jnz     loc_1400F048F
0x1400f037c  mov     eax, esi
0x1400f037e  mov     rcx, [rsp+0B8h+var_38]
0x1400f0386  xor     rcx, rsp; StackCookie
0x1400f0389  call    __security_check_cookie
0x1400f038e  lea     r11, [rsp+0B8h+var_28]
0x1400f0396  mov     rbx, [r11+38h]
0x1400f039a  mov     rsi, [r11+48h]
0x1400f039e  mov     rsp, r11
0x1400f03a1  pop     r15
0x1400f03a3  pop     r14
0x1400f03a5  pop     r13
0x1400f03a7  pop     r12
0x1400f03a9  pop     rdi
0x1400f03aa  retn
0x1400f03ac  mov     eax, 0C000000Dh
0x1400f03b1  jmp     short loc_1400F037E
0x1400f03b3  add     rcx, 28h ; '('
0x1400f03b7  mov     rdx, [rcx]
0x1400f03ba  cmp     rdx, rcx
0x1400f03bd  jz      short loc_1400F03DF
0x1400f03bf  lea     rax, [rdx-8]
0x1400f03c3  mov     r15, rcx
0x1400f03c6  cmp     [rax], r14
0x1400f03c9  jz      loc_1400F02B0
0x1400f03cf  mov     rdx, [rdx]
0x1400f03d2  mov     rax, rsi
0x1400f03d5  cmp     rdx, rcx
0x1400f03d8  jnz     short loc_1400F03BF
0x1400f03da  jmp     loc_1400F02B0
0x1400f03df  mov     r15, rcx
0x1400f03e2  jmp     loc_1400F02B0
0x1400f03e7  mov     edx, 28h ; '('
0x1400f03ec  mov     ecx, 40h ; '@'
0x1400f03f1  mov     r8d, 72446456h
0x1400f03f7  call    cs:__imp_ExAllocatePool2
0x1400f03fe  nop     dword ptr [rax+rax+00h]
0x1400f0403  mov     rdx, rax
0x1400f0406  test    rax, rax
0x1400f0409  jz      short loc_1400F0471
0x1400f040b  mov     rcx, [r15+8]
0x1400f040f  cmp     [rcx], r15
0x1400f0412  jnz     short loc_1400F0433
0x1400f0414  add     rax, 8
0x1400f0418  mov     [rax], r15
0x1400f041b  mov     [rax+8], rcx
0x1400f041f  mov     [rcx], rax
0x1400f0422  mov     [r15+8], rax
0x1400f0426  mov     rdi, rdx
0x1400f0429  mov     [rsp+0B8h+var_80], rdx
0x1400f042e  jmp     loc_1400F02C2
0x1400f0433  mov     ecx, 3
0x1400f0438  int     29h; Win8: RtlFailFast(ecx)
0x1400f043a  lea     rdx, [rsp+0B8h+ApcState]; ApcState
0x1400f043f  mov     rcx, r14; PROCESS
0x1400f0442  call    cs:__imp_KeStackAttachProcess
0x1400f0449  nop     dword ptr [rax+rax+00h]
0x1400f044e  mov     r15b, 1
0x1400f0451  mov     [rsp+0B8h+var_88], r15b
0x1400f0456  jmp     loc_1400F0303
0x1400f045b  lea     rcx, [rsp+0B8h+ApcState]; ApcState
0x1400f0460  call    cs:__imp_KeUnstackDetachProcess
0x1400f0467  nop     dword ptr [rax+rax+00h]
0x1400f046c  jmp     loc_1400F0366
0x1400f0471  mov     esi, 0C000009Ah
0x1400f0476  test    rdi, rdi
0x1400f0479  jz      loc_1400F037C
0x1400f047f  mov     rdx, rdi
0x1400f0482  mov     rcx, rbx
0x1400f0485  call    VidClientBufferpUnShareInternal
0x1400f048a  jmp     loc_1400F037C
0x1400f048f  mov     [r12], rax
0x1400f0493  jmp     loc_1400F037C
```
