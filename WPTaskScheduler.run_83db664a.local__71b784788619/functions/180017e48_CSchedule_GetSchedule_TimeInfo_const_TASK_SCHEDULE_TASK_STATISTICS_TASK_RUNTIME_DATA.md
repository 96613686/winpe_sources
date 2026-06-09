# CSchedule::GetSchedule(TimeInfo const &,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)

- ea: `0x180017e48`
- end: `0x180018121`
- name: `?GetSchedule@CSchedule@@QEAAJAEBVTimeInfo@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z`
- size: `729`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const struct TimeInfo *, struct _TASK_SCHEDULE **, struct _TASK_STATISTICS **, struct _TASK_RUNTIME_DATA **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800192ec`

## callees

- `0x18000be70`
- `0x18000f760`
- `0x180017e48`
- `0x18001c0e0`
- `0x18001fdfc`
- `0x1800209f8`
- `0x180020a2c`
- `0x180020a48`
- `0x180020c02`
- `0x180022010`

## import_xrefs

- `msvcrt!malloc` at `0x180017ea0`
- `msvcrt!malloc` at `0x180017ec5`
- `msvcrt!malloc` at `0x180017edb`
- `msvcrt!malloc` at `0x18001801e`
- `msvcrt!malloc` at `0x18001808c`
- `msvcrt!malloc` at `0x180017ea0`
- `msvcrt!malloc` at `0x180017ec5`
- `msvcrt!malloc` at `0x180017edb`
- `msvcrt!malloc` at `0x18001801e`
- `msvcrt!malloc` at `0x18001808c`

## pseudocode

```c
__int64 __fastcall CSchedule::GetSchedule(
        CSchedule *this,
        const struct TimeInfo *a2,
        struct _TASK_SCHEDULE **a3,
        struct _TASK_STATISTICS **a4,
        struct _TASK_RUNTIME_DATA **a5)
{
  _OWORD *v9; // r15
  char *v10; // rbx
  struct _TASK_RUNTIME_DATA *v11; // rsi
  unsigned int v12; // ebp
  char *v13; // rax
  void *v14; // rax
  void *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  _OWORD *v20; // rax
  struct _TASK_TRIGGER *v21; // rcx
  const unsigned __int16 *v22; // r8
  _OWORD *v23; // rax
  struct _TASK_RUNTIME_DATA *v24; // rax
  __int64 v25; // rcx
  SecurityContext *v26; // rcx
  struct _TASK_TRIGGER Block; // [rsp+20h] [rbp-58h] BYREF

  CSchedule::UpdateState(this, a2);
  if ( *((_DWORD *)this + 66) && (*((_BYTE *)this + 44) & 4) != 0 )
    return 2194604304LL;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( a3 )
  {
    v12 = -2147024882;
    v13 = (char *)malloc(0x58u);
    v10 = v13;
    if ( !v13 )
      goto LABEL_36;
    memset_0(v13, 0, 0x58u);
    v14 = malloc(0x200u);
    *((_QWORD *)v10 + 2) = v14;
    if ( !v14 )
      goto LABEL_36;
    v15 = malloc(0x10u);
    *(_QWORD *)v10 = v15;
    if ( !v15 )
      goto LABEL_36;
    v16 = *((_QWORD *)this + 27);
    if ( v16 )
    {
      if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v16 + 32LL))(v16, v10 + 72) < 0 )
        goto LABEL_36;
    }
    v17 = *((_QWORD *)this + 25);
    if ( v17 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      *((_QWORD *)v10 + 8) = v18;
      if ( !v18 )
        goto LABEL_36;
    }
    if ( *((_DWORD *)this + 22) )
      *(_OWORD *)(v10 + 24) = *((_OWORD *)this + 3);
    if ( *((_DWORD *)this + 34) )
      *(_OWORD *)(v10 + 40) = *((_OWORD *)this + 6);
    *((_DWORD *)v10 + 14) = *((_DWORD *)this + 37);
    *((_DWORD *)v10 + 2) = *((_DWORD *)this + 11) & 0x7F;
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 25) + 56LL))(*((_QWORD *)this + 25)) )
      *((_DWORD *)v10 + 2) |= 0x10u;
    if ( *((_DWORD *)this + 52) == 5 )
    {
      v19 = *((_QWORD *)this + 25);
      *(_OWORD *)&Block.cbTriggerSize = 0;
      if ( (*(int (__fastcall **)(__int64, struct _TASK_TRIGGER *))(*(_QWORD *)v19 + 24LL))(v19, &Block) >= 0 )
      {
        v20 = *(_OWORD **)&Block.wBeginDay;
        *(_OWORD *)(v10 + 24) = **(_OWORD **)&Block.wBeginDay;
        *(_OWORD *)(v10 + 40) = *v20;
        Trigger::Free(&Block, 0);
      }
      v21 = (struct _TASK_TRIGGER *)*((_QWORD *)v10 + 8);
      if ( v21 )
      {
        Trigger::Free(v21, 1);
        *((_QWORD *)v10 + 8) = 0;
      }
    }
    *(_OWORD *)*(_QWORD *)v10 = *((_OWORD *)this + 1);
    v22 = (const unsigned __int16 *)*((_QWORD *)this + 4);
    if ( v22 )
      StringCchCopyW(*((unsigned __int16 **)v10 + 2), 0x100u, v22);
    *a3 = (struct _TASK_SCHEDULE *)v10;
  }
  v12 = 0;
  if ( a4 )
  {
    v12 = -2147024882;
    v23 = malloc(0x28u);
    v9 = v23;
    if ( !v23 )
      goto LABEL_36;
    *v23 = 0;
    v23[1] = 0;
    *((_QWORD *)v23 + 4) = 0;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 27) + 40LL))(
      *((_QWORD *)this + 27),
      (__int64)v23 + 4,
      (__int64)v23 + 8);
    v12 = 0;
    *(_DWORD *)v9 = *((_DWORD *)this + 36);
    *(_OWORD *)((char *)v9 + 24) = *(_OWORD *)((char *)this + 152);
    *a4 = (struct _TASK_STATISTICS *)v9;
  }
  if ( a5 )
  {
    v12 = -2147024882;
    v24 = (struct _TASK_RUNTIME_DATA *)malloc(0x20u);
    v11 = v24;
    if ( v24 )
    {
      *(_OWORD *)v24 = 0;
      *((_OWORD *)v24 + 1) = 0;
      v25 = *((_QWORD *)this + 25);
      if ( v25 )
        (*(void (__fastcall **)(__int64, struct _TASK_RUNTIME_DATA *))(*(_QWORD *)v25 + 80LL))(v25, v24);
      v26 = (SecurityContext *)*((_QWORD *)this + 34);
      if ( v26 )
        SecurityContext::GetRuntimeData(v26, v11);
      *a5 = v11;
      return 0;
    }
LABEL_36:
    TaskSchedulerFreeSchedule(v10);
    TaskSchedulerFreeScheduleStatistics(v9);
    TaskSchedulerFreeRunTime(v11);
    if ( a3 )
      *a3 = 0;
    if ( a4 )
      *a4 = 0;
    if ( a5 )
      *a5 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x180017e48  push    rbx
0x180017e4a  push    rbp
0x180017e4b  push    rsi
0x180017e4c  push    rdi
0x180017e4d  push    r12
0x180017e4f  push    r13
0x180017e51  push    r14
0x180017e53  push    r15
0x180017e55  sub     rsp, 38h
0x180017e59  mov     r13, r9
0x180017e5c  mov     r12, r8
0x180017e5f  mov     rdi, rcx
0x180017e62  call    ?UpdateState@CSchedule@@AEAAXAEBVTimeInfo@@@Z; CSchedule::UpdateState(TimeInfo const &)
0x180017e67  cmp     dword ptr [rdi+108h], 0
0x180017e6e  jz      short loc_180017E80
0x180017e70  test    byte ptr [rdi+2Ch], 4
0x180017e74  jz      short loc_180017E80
0x180017e76  mov     eax, 82CF0110h
0x180017e7b  jmp     loc_180018110
0x180017e80  mov     r14, [rsp+78h+arg_20]
0x180017e88  xor     r15d, r15d
0x180017e8b  xor     ebx, ebx
0x180017e8d  xor     esi, esi
0x180017e8f  test    r12, r12
0x180017e92  jz      loc_18001800D
0x180017e98  lea     ecx, [rbx+58h]; Size
0x180017e9b  mov     ebp, 8007000Eh
0x180017ea0  call    cs:__imp_malloc
0x180017ea6  mov     rbx, rax
0x180017ea9  test    rax, rax
0x180017eac  jz      loc_1800180DA
0x180017eb2  xor     edx, edx; Val
0x180017eb4  lea     r8d, [r15+58h]; Size
0x180017eb8  mov     rcx, rax; void *
0x180017ebb  call    memset_0
0x180017ec0  mov     ecx, 200h; Size
0x180017ec5  call    cs:__imp_malloc
0x180017ecb  mov     [rbx+10h], rax
0x180017ecf  test    rax, rax
0x180017ed2  jz      loc_1800180DA
0x180017ed8  lea     ecx, [rsi+10h]; Size
0x180017edb  call    cs:__imp_malloc
0x180017ee1  mov     [rbx], rax
0x180017ee4  test    rax, rax
0x180017ee7  jz      loc_1800180DA
0x180017eed  mov     rcx, [rdi+0D8h]
0x180017ef4  test    rcx, rcx
0x180017ef7  jz      short loc_180017F11
0x180017ef9  mov     rax, [rcx]
0x180017efc  lea     rdx, [rbx+48h]
0x180017f00  mov     rax, [rax+20h]
0x180017f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f09  test    eax, eax
0x180017f0b  js      loc_1800180DA
0x180017f11  mov     rcx, [rdi+0C8h]
0x180017f18  test    rcx, rcx
0x180017f1b  jz      short loc_180017F36
0x180017f1d  mov     rax, [rcx]
0x180017f20  mov     rax, [rax+8]
0x180017f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f29  mov     [rbx+40h], rax
0x180017f2d  test    rax, rax
0x180017f30  jz      loc_1800180DA
0x180017f36  cmp     [rdi+58h], esi
0x180017f39  jz      short loc_180017F44
0x180017f3b  movups  xmm0, xmmword ptr [rdi+30h]
0x180017f3f  movdqu  xmmword ptr [rbx+18h], xmm0
0x180017f44  cmp     [rdi+88h], esi
0x180017f4a  jz      short loc_180017F55
0x180017f4c  movups  xmm0, xmmword ptr [rdi+60h]
0x180017f50  movdqu  xmmword ptr [rbx+28h], xmm0
0x180017f55  mov     eax, [rdi+94h]
0x180017f5b  mov     [rbx+38h], eax
0x180017f5e  mov     eax, [rdi+2Ch]
0x180017f61  and     eax, 7Fh
0x180017f64  mov     [rbx+8], eax
0x180017f67  mov     rcx, [rdi+0C8h]
0x180017f6e  mov     rax, [rcx]
0x180017f71  mov     rax, [rax+38h]
0x180017f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f7a  test    eax, eax
0x180017f7c  jz      short loc_180017F82
0x180017f7e  or      dword ptr [rbx+8], 10h
0x180017f82  cmp     dword ptr [rdi+0D0h], 5
0x180017f89  jnz     short loc_180017FE7
0x180017f8b  mov     rcx, [rdi+0C8h]
0x180017f92  lea     rdx, [rsp+78h+Block]
0x180017f97  xorps   xmm0, xmm0
0x180017f9a  movups  xmmword ptr [rsp+78h+Block.cbTriggerSize], xmm0
0x180017f9f  mov     rax, [rcx]
0x180017fa2  mov     rax, [rax+18h]
0x180017fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fab  test    eax, eax
0x180017fad  js      short loc_180017FD0
0x180017faf  mov     rax, qword ptr [rsp+78h+Block.wBeginDay]
0x180017fb4  lea     rcx, [rsp+78h+Block]; Block
0x180017fb9  xor     edx, edx; int
0x180017fbb  movups  xmm0, xmmword ptr [rax]
0x180017fbe  movdqu  xmmword ptr [rbx+18h], xmm0
0x180017fc3  movups  xmm1, xmmword ptr [rax]
0x180017fc6  movdqu  xmmword ptr [rbx+28h], xmm1
0x180017fcb  call    ?Free@Trigger@@SAJPEAU_TASK_TRIGGER@@H@Z; Trigger::Free(_TASK_TRIGGER *,int)
0x180017fd0  mov     rcx, [rbx+40h]; Block
0x180017fd4  test    rcx, rcx
0x180017fd7  jz      short loc_180017FE7
0x180017fd9  mov     edx, 1; int
0x180017fde  call    ?Free@Trigger@@SAJPEAU_TASK_TRIGGER@@H@Z; Trigger::Free(_TASK_TRIGGER *,int)
0x180017fe3  mov     [rbx+40h], rsi
0x180017fe7  mov     rax, [rbx]
0x180017fea  movups  xmm0, xmmword ptr [rdi+10h]
0x180017fee  movdqu  xmmword ptr [rax], xmm0
0x180017ff2  mov     r8, [rdi+20h]; unsigned __int16 *
0x180017ff6  test    r8, r8
0x180017ff9  jz      short loc_180018009
0x180017ffb  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180017fff  mov     edx, 100h; unsigned __int64
0x180018004  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018009  mov     [r12], rbx
0x18001800d  xor     ebp, ebp
0x18001800f  test    r13, r13
0x180018012  jz      short loc_180018079
0x180018014  mov     ecx, 28h ; '('; Size
0x180018019  mov     ebp, 8007000Eh
0x18001801e  call    cs:__imp_malloc
0x180018024  mov     r15, rax
0x180018027  test    rax, rax
0x18001802a  jz      loc_1800180DA
0x180018030  xor     eax, eax
0x180018032  lea     r8, [r15+8]
0x180018036  xorps   xmm0, xmm0
0x180018039  lea     rdx, [r15+4]
0x18001803d  movups  xmmword ptr [r15], xmm0
0x180018041  movups  xmmword ptr [r15+10h], xmm0
0x180018046  mov     [r15+20h], rax
0x18001804a  mov     rcx, [rdi+0D8h]
0x180018051  mov     rax, [rcx]
0x180018054  mov     rax, [rax+28h]
0x180018058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001805d  mov     eax, [rdi+90h]
0x180018063  xor     ebp, ebp
0x180018065  mov     [r15], eax
0x180018068  movups  xmm0, xmmword ptr [rdi+98h]
0x18001806f  movdqu  xmmword ptr [r15+18h], xmm0
0x180018075  mov     [r13+0], r15
0x180018079  test    r14, r14
0x18001807c  jz      loc_18001810E
0x180018082  mov     ecx, 20h ; ' '; Size
0x180018087  mov     ebp, 8007000Eh
0x18001808c  call    cs:__imp_malloc
0x180018092  mov     rsi, rax
0x180018095  test    rax, rax
0x180018098  jz      short loc_1800180DA
0x18001809a  xorps   xmm0, xmm0
0x18001809d  movups  xmmword ptr [rax], xmm0
0x1800180a0  movups  xmmword ptr [rax+10h], xmm0
0x1800180a4  mov     rcx, [rdi+0C8h]
0x1800180ab  test    rcx, rcx
0x1800180ae  jz      short loc_1800180BF
0x1800180b0  mov     rdx, [rcx]
0x1800180b3  mov     rax, [rdx+50h]
0x1800180b7  mov     rdx, rsi
0x1800180ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180bf  mov     rcx, [rdi+110h]; this
0x1800180c6  test    rcx, rcx
0x1800180c9  jz      short loc_1800180D3
0x1800180cb  mov     rdx, rsi; struct _TASK_RUNTIME_DATA *
0x1800180ce  call    ?GetRuntimeData@SecurityContext@@QEAAJPEAU_TASK_RUNTIME_DATA@@@Z; SecurityContext::GetRuntimeData(_TASK_RUNTIME_DATA *)
0x1800180d3  mov     [r14], rsi
0x1800180d6  xor     ebp, ebp
0x1800180d8  jmp     short loc_18001810E
0x1800180da  mov     rcx, rbx
0x1800180dd  call    TaskSchedulerFreeSchedule
0x1800180e2  mov     rcx, r15
0x1800180e5  call    TaskSchedulerFreeScheduleStatistics
0x1800180ea  mov     rcx, rsi; void *
0x1800180ed  call    TaskSchedulerFreeRunTime
0x1800180f2  xor     eax, eax
0x1800180f4  test    r12, r12
0x1800180f7  jz      short loc_1800180FD
0x1800180f9  mov     [r12], rax
0x1800180fd  test    r13, r13
0x180018100  jz      short loc_180018106
0x180018102  mov     [r13+0], rax
0x180018106  test    r14, r14
0x180018109  jz      short loc_18001810E
0x18001810b  mov     [r14], rax
0x18001810e  mov     eax, ebp
0x180018110  add     rsp, 38h
0x180018114  pop     r15
0x180018116  pop     r14
0x180018118  pop     r13
0x18001811a  pop     r12
0x18001811c  pop     rdi
0x18001811d  pop     rsi
0x18001811e  pop     rbp
0x18001811f  pop     rbx
0x180018120  retn
```
