# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x1800026b4`
- end: `0x180002800`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `332`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002420`
- `0x180002810`
- `0x1800043a0`
- `0x180004410`
- `0x180004980`
- `0x1800049e0`
- `0x1800065cc`

## callees

- `0x1800026b4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800027b4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800027b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002777`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002777`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002794`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800027ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002794`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800027ab`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::TerminateMap(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const unsigned __int16 *a3)
{
  char v3; // r12
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r15
  struct Microsoft::WRL::Details::ModuleBase *v8; // rcx
  char *v9; // r8
  int v10; // edx
  int v11; // eax
  RTL_SRWLOCK *v12; // rdi
  void **v13; // rax
  void *v14; // rbp
  PVOID v15; // rax

  v3 = (char)a3;
  v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 32LL))(this) + 8;
  v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
  if ( v6 >= v7 )
    return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  while ( 1 )
  {
    if ( *(_QWORD *)v6 )
    {
      if ( !a2 )
        break;
      v8 = *(struct Microsoft::WRL::Details::ModuleBase **)(*(_QWORD *)v6 + 32LL);
      if ( v8 )
      {
        v9 = (char *)(a2 - v8);
        do
        {
          v10 = *(unsigned __int16 *)&v9[(_QWORD)v8];
          v11 = *(unsigned __int16 *)v8 - v10;
          if ( v11 )
            break;
          v8 = (struct Microsoft::WRL::Details::ModuleBase *)((char *)v8 + 2);
        }
        while ( v10 );
        if ( !v11 )
          break;
      }
    }
LABEL_18:
    v6 += 8LL;
    if ( v6 >= v7 )
      return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  }
  if ( !(*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) || v3 )
  {
    if ( **(_QWORD **)(*(_QWORD *)v6 + 24LL) )
    {
      v12 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
      AcquireSRWLockExclusive(v12);
      v13 = *(void ***)(*(_QWORD *)v6 + 24LL);
      v14 = *v13;
      if ( *v13 )
      {
        *v13 = 0;
        if ( v12 )
          ReleaseSRWLockExclusive(v12);
        v15 = DecodePointer(v14);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v15 + 16LL))(v15);
      }
      else if ( v12 )
      {
        ReleaseSRWLockExclusive(v12);
      }
    }
    goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x1800026b4  push    rbx
0x1800026b6  push    rbp
0x1800026b7  push    rsi
0x1800026b8  push    rdi
0x1800026b9  push    r12
0x1800026bb  push    r14
0x1800026bd  push    r15
0x1800026bf  sub     rsp, 20h
0x1800026c3  mov     r12b, r8b
0x1800026c6  mov     r14, rdx
0x1800026c9  mov     rsi, rcx
0x1800026cc  mov     rax, [rcx]
0x1800026cf  mov     rax, [rax+20h]
0x1800026d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026d8  lea     rbx, [rax+8]
0x1800026dc  mov     r9, [rsi]
0x1800026df  mov     rcx, rsi
0x1800026e2  mov     rax, [r9+30h]
0x1800026e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026eb  mov     r15, rax
0x1800026ee  cmp     rbx, rax
0x1800026f1  jnb     loc_1800027D9
0x1800026f7  mov     rcx, [rbx]
0x1800026fa  test    rcx, rcx
0x1800026fd  jz      loc_1800027CC
0x180002703  test    r14, r14
0x180002706  jz      short loc_180002737
0x180002708  mov     rcx, [rcx+20h]
0x18000270c  test    rcx, rcx
0x18000270f  jz      loc_1800027CC
0x180002715  mov     r8, r14
0x180002718  sub     r8, rcx
0x18000271b  movzx   eax, word ptr [rcx]
0x18000271e  movzx   edx, word ptr [rcx+r8]
0x180002723  sub     eax, edx
0x180002725  jnz     short loc_18000272F
0x180002727  add     rcx, 2
0x18000272b  test    edx, edx
0x18000272d  jnz     short loc_18000271B
0x18000272f  test    eax, eax
0x180002731  jnz     loc_1800027CC
0x180002737  mov     rax, [rsi]
0x18000273a  mov     rcx, rsi
0x18000273d  mov     rax, [rax+18h]
0x180002741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002746  test    eax, eax
0x180002748  jz      short loc_180002753
0x18000274a  test    r12b, r12b
0x18000274d  jz      loc_1800027FC
0x180002753  mov     rax, [rbx]
0x180002756  mov     rcx, [rax+18h]
0x18000275a  mov     rax, [rcx]
0x18000275d  test    rax, rax
0x180002760  jz      short loc_1800027CC
0x180002762  mov     rax, [rsi]
0x180002765  mov     rcx, rsi
0x180002768  mov     rax, [rax+38h]
0x18000276c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002771  mov     rdi, rax
0x180002774  mov     rcx, rax; SRWLock
0x180002777  call    cs:__imp_AcquireSRWLockExclusive
0x18000277d  mov     rcx, [rbx]
0x180002780  mov     rax, [rcx+18h]
0x180002784  mov     rbp, [rax]
0x180002787  test    rbp, rbp
0x18000278a  jnz     short loc_18000279C
0x18000278c  test    rdi, rdi
0x18000278f  jz      short loc_1800027CC
0x180002791  mov     rcx, rdi; SRWLock
0x180002794  call    cs:__imp_ReleaseSRWLockExclusive
0x18000279a  jmp     short loc_1800027CC
0x18000279c  mov     qword ptr [rax], 0
0x1800027a3  test    rdi, rdi
0x1800027a6  jz      short loc_1800027B1
0x1800027a8  mov     rcx, rdi; SRWLock
0x1800027ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1800027b1  mov     rcx, rbp; Ptr
0x1800027b4  call    cs:__imp_DecodePointer
0x1800027ba  mov     rdx, rax
0x1800027bd  mov     rcx, [rax]
0x1800027c0  mov     rax, [rcx+10h]
0x1800027c4  mov     rcx, rdx
0x1800027c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027cc  add     rbx, 8
0x1800027d0  cmp     rbx, r15
0x1800027d3  jb      loc_1800026F7
0x1800027d9  mov     rax, [rsi]
0x1800027dc  mov     rcx, rsi
0x1800027df  mov     rax, [rax+18h]
0x1800027e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027e8  test    eax, eax
0x1800027ea  setz    al
0x1800027ed  add     rsp, 20h
0x1800027f1  pop     r15
0x1800027f3  pop     r14
0x1800027f5  pop     r12
0x1800027f7  pop     rdi
0x1800027f8  pop     rsi
0x1800027f9  pop     rbp
0x1800027fa  pop     rbx
0x1800027fb  retn
0x1800027fc  xor     al, al
0x1800027fe  jmp     short loc_1800027ED
```
