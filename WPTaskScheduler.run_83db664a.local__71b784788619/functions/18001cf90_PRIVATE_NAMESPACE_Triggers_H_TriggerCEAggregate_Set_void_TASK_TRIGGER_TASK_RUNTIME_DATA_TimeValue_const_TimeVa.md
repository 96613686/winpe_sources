# PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::Set(void *,_TASK_TRIGGER *,_TASK_RUNTIME_DATA *,TimeValue const &,TimeValue const &,uchar,ulong)

- ea: `0x18001cf90`
- end: `0x18001d2e6`
- name: `?Set@TriggerCEAggregate@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAXPEAU_TASK_TRIGGER@@PEAU_TASK_RUNTIME_DATA@@AEBVTimeValue@@3EK@Z`
- size: `854`
- prototype: `int(PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate *__hidden this, void *, struct _TASK_TRIGGER *, struct _TASK_RUNTIME_DATA *, const struct TimeValue *, const struct TimeValue *, unsigned __int8, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x180009aa0`
- `0x180010208`
- `0x180019c80`
- `0x18001cf90`
- `0x180020c30`
- `0x180022010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d2af`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d2af`
- `EventAggregation!EACreateAggregateEvent` at `0x18001d21f`
- `EventAggregation!EACreateAggregateEvent` at `0x18001d21f`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::Set(
        PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate *this,
        void *a2,
        struct _TASK_TRIGGER *a3,
        struct _TASK_RUNTIME_DATA *a4,
        const struct TimeValue *a5,
        const struct TimeValue *a6,
        unsigned __int8 a7,
        unsigned int a8)
{
  const struct TimeValue *v8; // r10
  const struct TimeValue *v10; // r11
  __int128 **v13; // rbx
  __int64 v14; // r8
  int v15; // ebx
  __int64 v16; // r9
  int v18; // ecx
  __int128 v19; // xmm0
  bool v20; // zf
  struct Trigger *v21; // rax
  struct _TASK_TRIGGER *v22; // rbx
  unsigned __int64 v23; // rax
  unsigned int v24; // r14d
  struct Trigger *v25; // rax
  struct Trigger *v26; // rsi
  __int64 v27; // rax
  __int64 **v28; // rsi
  __int64 v29; // rcx
  __int64 *v30; // rax
  __int64 *v31; // rdx
  void (__fastcall ***v32)(_QWORD, __int64); // rcx
  __int64 v33; // [rsp+50h] [rbp-39h] BYREF
  int v34; // [rsp+58h] [rbp-31h]
  unsigned int v35; // [rsp+5Ch] [rbp-2Dh]
  char *v36; // [rsp+60h] [rbp-29h]
  BOOL v37; // [rsp+68h] [rbp-21h]
  int v38; // [rsp+6Ch] [rbp-1Dh]
  void (__fastcall *v39)(__int64, __int64, __int64, const void *, unsigned int); // [rsp+70h] [rbp-19h]
  __int64 v40; // [rsp+78h] [rbp-11h]
  void *v41; // [rsp+80h] [rbp-9h]

  v8 = a5;
  v10 = a6;
  if ( a3 && a2 )
  {
    v13 = *(__int128 ***)&a3->wBeginDay;
    if ( !v13 )
      return (unsigned int)-2147467261;
    v14 = *((unsigned int *)v13 + 2);
    if ( (int)v14 >= 2 )
      return (unsigned int)-2100362983;
    if ( !*v13 )
      return (unsigned int)-2147467261;
    v16 = *((unsigned int *)v13 + 3);
    if ( (_DWORD)v16 )
    {
      if ( !v13[2] )
        return (unsigned int)-2147467261;
    }
    if ( (byte_180030D06 & 0x10) != 0 )
    {
      McTemplateU0qq_EventWriteTransfer(this, CEAggregateTriggerSet, v14, v16);
      v8 = a5;
      v10 = a6;
    }
    *((_QWORD *)this + 22) = a2;
    v18 = *((_DWORD *)v13 + 2);
    *((_DWORD *)this + 48) = v18;
    v19 = **v13;
    *((_QWORD *)this + 28) = 0;
    v33 = 0;
    v34 = 0;
    *((_OWORD *)this + 13) = v19;
    *((_DWORD *)this + 58) = 0;
    *((_DWORD *)this + 46) = 0;
    v35 = *((_DWORD *)v13 + 3);
    v36 = 0;
    v40 = 0;
    v41 = a2;
    v37 = v18 != 0;
    v20 = *((_DWORD *)this + 52) == 3;
    v38 = 0;
    v39 = CScheduleMgr::BaseCentralEventAggregateCallback;
    if ( v20 )
    {
      v21 = Trigger::Alloc(a2, (struct _TASK_TRIGGER *)((char *)this + 208), v8, v10, a4, a7 + 1, a8 | 1);
      *((_QWORD *)this + 28) = v21;
      if ( !v21 )
      {
LABEL_15:
        v15 = -2147024882;
        goto LABEL_32;
      }
      if ( (*(unsigned int (__fastcall **)(struct Trigger *, __int64 *))(*(_QWORD *)v21 + 32LL))(v21, &v33) )
      {
        if ( v35 )
        {
          v22 = (struct _TASK_TRIGGER *)v13[2];
          v23 = 8LL * v35;
          if ( !is_mul_ok(v35, 8u) )
            v23 = -1;
          v36 = (char *)operator new[](v23, (const struct std::nothrow_t *)&std::nothrow);
          if ( !v36 )
            goto LABEL_15;
          v24 = 0;
          while ( v24 < v35 )
          {
            if ( *(_DWORD *)&v22->cbTriggerSize != 3 )
              goto LABEL_31;
            v25 = Trigger::Alloc(*((void **)this + 22), v22, a5, a6, a4, a7 + 1, a8 | 1);
            v26 = v25;
            if ( !v25 )
              goto LABEL_15;
            if ( !(*(unsigned int (__fastcall **)(struct Trigger *, char *))(*(_QWORD *)v25 + 32LL))(
                    v25,
                    &v36[8 * *((unsigned int *)this + 58)]) )
            {
              v15 = -2147467262;
              (**(void (__fastcall ***)(struct Trigger *, __int64))v26)(v26, 1);
              goto LABEL_32;
            }
            ++v24;
            v27 = *((_QWORD *)this + 30);
            *((_QWORD *)v26 + 1) = v27;
            *((_QWORD *)v26 + 2) = (char *)this + 240;
            *(_QWORD *)(v27 + 8) = (char *)v26 + 8;
            *((_QWORD *)this + 30) = (char *)v26 + 8;
            ++*((_DWORD *)this + 58);
            v22 = (struct _TASK_TRIGGER *)((char *)v22 + 16);
          }
        }
        v15 = EACreateAggregateEvent(&v33, (char *)this + 200);
        if ( v15 >= 0 )
        {
LABEL_40:
          if ( v36 )
            operator delete[](v36);
          return (unsigned int)v15;
        }
      }
      else
      {
        v15 = -2147467262;
      }
    }
    else
    {
LABEL_31:
      v15 = -2100362983;
    }
LABEL_32:
    v28 = (__int64 **)((char *)this + 240);
    while ( 1 )
    {
      v31 = *v28;
      if ( *v28 == (__int64 *)v28 )
        break;
      v29 = *v31;
      v30 = (__int64 *)v31[1];
      *v30 = *v31;
      *(_QWORD *)(v29 + 8) = v30;
      if ( v31 != (__int64 *)8 )
        (*(void (__fastcall **)(__int64 *, __int64))*(v31 - 1))(v31 - 1, 1);
      --*((_DWORD *)this + 58);
    }
    v32 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 28);
    if ( v32 )
    {
      (**v32)(v32, 1);
      *((_QWORD *)this + 28) = 0;
    }
    *((_QWORD *)this + 22) = 0;
    goto LABEL_40;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001cf90  mov     [rsp-8+arg_8], rbx
0x18001cf95  push    rbp
0x18001cf96  push    rsi
0x18001cf97  push    rdi
0x18001cf98  push    r12
0x18001cf9a  push    r13
0x18001cf9c  push    r14
0x18001cf9e  push    r15
0x18001cfa0  lea     rbp, [rsp-7]
0x18001cfa5  sub     rsp, 90h
0x18001cfac  mov     rax, cs:__security_cookie
0x18001cfb3  xor     rax, rsp
0x18001cfb6  mov     [rbp+37h+var_38], rax
0x18001cfba  mov     r10, [rbp+37h+arg_20]
0x18001cfbe  mov     r13, r9
0x18001cfc1  mov     r11, [rbp+37h+arg_28]
0x18001cfc5  mov     rsi, rdx
0x18001cfc8  mov     r15b, [rbp+37h+arg_30]
0x18001cfcc  mov     rdi, rcx
0x18001cfcf  mov     r12d, [rbp+37h+arg_38]
0x18001cfd3  mov     [rbp+37h+var_78], r10
0x18001cfd7  mov     [rbp+37h+var_80], r11
0x18001cfdb  test    r8, r8
0x18001cfde  jz      loc_18001D2BA
0x18001cfe4  test    rdx, rdx
0x18001cfe7  jz      loc_18001D2BA
0x18001cfed  mov     rbx, [r8+8]
0x18001cff1  test    rbx, rbx
0x18001cff4  jz      short loc_18001D01D
0x18001cff6  mov     r8d, [rbx+8]
0x18001cffa  cmp     r8d, 2
0x18001cffe  jl      short loc_18001D007
0x18001d000  mov     ebx, 82CF0119h
0x18001d005  jmp     short loc_18001D022
0x18001d007  cmp     qword ptr [rbx], 0
0x18001d00b  jz      short loc_18001D01D
0x18001d00d  mov     r9d, [rbx+0Ch]
0x18001d011  test    r9d, r9d
0x18001d014  jz      short loc_18001D029
0x18001d016  cmp     qword ptr [rbx+10h], 0
0x18001d01b  jnz     short loc_18001D029
0x18001d01d  mov     ebx, 80004003h
0x18001d022  mov     eax, ebx
0x18001d024  jmp     loc_18001D2BF
0x18001d029  test    cs:byte_180030D06, 10h
0x18001d030  jz      short loc_18001D046
0x18001d032  lea     rdx, CEAggregateTriggerSet
0x18001d039  call    McTemplateU0qq_EventWriteTransfer
0x18001d03e  mov     r10, [rbp+37h+var_78]
0x18001d042  mov     r11, [rbp+37h+var_80]
0x18001d046  mov     [rdi+0B0h], rsi
0x18001d04d  lea     rdx, [rdi+0D0h]; struct _TASK_TRIGGER *
0x18001d054  mov     ecx, [rbx+8]
0x18001d057  mov     [rdi+0C0h], ecx
0x18001d05d  mov     rax, [rbx]
0x18001d060  movups  xmm0, xmmword ptr [rax]
0x18001d063  xor     eax, eax
0x18001d065  mov     qword ptr [rdi+0E0h], 0
0x18001d070  mov     [rbp+37h+var_70], rax
0x18001d074  mov     [rbp+37h+var_68], eax
0x18001d077  movdqu  xmmword ptr [rdx], xmm0
0x18001d07b  mov     dword ptr [rdi+0E8h], 0
0x18001d085  mov     dword ptr [rdi+0B8h], 0
0x18001d08f  mov     eax, [rbx+0Ch]
0x18001d092  mov     [rbp+37h+var_64], eax
0x18001d095  xor     eax, eax
0x18001d097  test    ecx, ecx
0x18001d099  mov     [rbp+37h+var_60], 0
0x18001d0a1  mov     [rbp+37h+var_48], 0
0x18001d0a9  setnz   al
0x18001d0ac  mov     [rbp+37h+var_40], rsi
0x18001d0b0  mov     [rbp+37h+var_58], eax
0x18001d0b3  xor     eax, eax
0x18001d0b5  cmp     dword ptr [rdx], 3
0x18001d0b8  mov     [rbp+37h+var_54], eax
0x18001d0bb  lea     rax, ?BaseCentralEventAggregateCallback@CScheduleMgr@@SAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; CScheduleMgr::BaseCentralEventAggregateCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x18001d0c2  mov     [rbp+37h+var_50], rax
0x18001d0c6  jnz     loc_18001D22D
0x18001d0cc  or      r12d, 1
0x18001d0d0  inc     r15b
0x18001d0d3  mov     [rsp+0C0h+var_90], r12d; unsigned int
0x18001d0d8  mov     r9, r11; struct TimeValue *
0x18001d0db  mov     [rsp+0C0h+var_98], r15b; char
0x18001d0e0  mov     r8, r10; struct TimeValue *
0x18001d0e3  mov     rcx, rsi; void *
0x18001d0e6  mov     [rsp+0C0h+var_A0], r13; struct _TASK_RUNTIME_DATA *
0x18001d0eb  call    ?Alloc@Trigger@@SAPEAV1@PEAXPEAU_TASK_TRIGGER@@AEBVTimeValue@@2PEAU_TASK_RUNTIME_DATA@@EK@Z; Trigger::Alloc(void *,_TASK_TRIGGER *,TimeValue const &,TimeValue const &,_TASK_RUNTIME_DATA *,uchar,ulong)
0x18001d0f0  mov     [rdi+0E0h], rax
0x18001d0f7  mov     rcx, rax
0x18001d0fa  test    rax, rax
0x18001d0fd  jnz     short loc_18001D109
0x18001d0ff  mov     ebx, 8007000Eh
0x18001d104  jmp     loc_18001D232
0x18001d109  mov     rax, [rax]
0x18001d10c  lea     rdx, [rbp+37h+var_70]
0x18001d110  mov     rax, [rax+20h]
0x18001d114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d119  test    eax, eax
0x18001d11b  jnz     short loc_18001D127
0x18001d11d  mov     ebx, 80004002h
0x18001d122  jmp     loc_18001D232
0x18001d127  mov     eax, [rbp+37h+var_64]
0x18001d12a  test    eax, eax
0x18001d12c  jz      loc_18001D214
0x18001d132  mov     rbx, [rbx+10h]
0x18001d136  mov     ecx, eax
0x18001d138  mov     eax, 8
0x18001d13d  mul     rcx
0x18001d140  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d147  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d14e  cmovb   rax, rcx
0x18001d152  mov     rcx, rax; unsigned __int64
0x18001d155  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d15a  mov     [rbp+37h+var_60], rax
0x18001d15e  test    rax, rax
0x18001d161  jz      short loc_18001D0FF
0x18001d163  xor     r14d, r14d
0x18001d166  cmp     r14d, [rbp+37h+var_64]
0x18001d16a  jnb     loc_18001D214
0x18001d170  cmp     dword ptr [rbx], 3
0x18001d173  jnz     loc_18001D22D
0x18001d179  mov     r9, [rbp+37h+var_80]; struct TimeValue *
0x18001d17d  mov     rdx, rbx; struct _TASK_TRIGGER *
0x18001d180  mov     r8, [rbp+37h+var_78]; struct TimeValue *
0x18001d184  mov     rcx, [rdi+0B0h]; void *
0x18001d18b  mov     [rsp+0C0h+var_90], r12d; unsigned int
0x18001d190  mov     [rsp+0C0h+var_98], r15b; char
0x18001d195  mov     [rsp+0C0h+var_A0], r13; struct _TASK_RUNTIME_DATA *
0x18001d19a  call    ?Alloc@Trigger@@SAPEAV1@PEAXPEAU_TASK_TRIGGER@@AEBVTimeValue@@2PEAU_TASK_RUNTIME_DATA@@EK@Z; Trigger::Alloc(void *,_TASK_TRIGGER *,TimeValue const &,TimeValue const &,_TASK_RUNTIME_DATA *,uchar,ulong)
0x18001d19f  mov     rsi, rax
0x18001d1a2  test    rax, rax
0x18001d1a5  jz      loc_18001D0FF
0x18001d1ab  mov     rcx, [rbp+37h+var_60]
0x18001d1af  mov     edx, [rdi+0E8h]
0x18001d1b5  mov     rax, [rax]
0x18001d1b8  lea     rdx, [rcx+rdx*8]
0x18001d1bc  mov     rcx, rsi
0x18001d1bf  mov     rax, [rax+20h]
0x18001d1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1c8  test    eax, eax
0x18001d1ca  jz      short loc_18001D1FA
0x18001d1cc  lea     rdx, [rdi+0F0h]
0x18001d1d3  inc     r14d
0x18001d1d6  mov     rax, [rdx]
0x18001d1d9  lea     rcx, [rsi+8]
0x18001d1dd  mov     [rcx], rax
0x18001d1e0  mov     [rsi+10h], rdx
0x18001d1e4  mov     [rax+8], rcx
0x18001d1e8  mov     [rdx], rcx
0x18001d1eb  inc     dword ptr [rdi+0E8h]
0x18001d1f1  add     rbx, 10h
0x18001d1f5  jmp     loc_18001D166
0x18001d1fa  mov     rax, [rsi]
0x18001d1fd  mov     edx, 1
0x18001d202  mov     rcx, rsi
0x18001d205  mov     ebx, 80004002h
0x18001d20a  mov     rax, [rax]
0x18001d20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d212  jmp     short loc_18001D232
0x18001d214  lea     rdx, [rdi+0C8h]
0x18001d21b  lea     rcx, [rbp+37h+var_70]
0x18001d21f  call    cs:__imp_EACreateAggregateEvent
0x18001d225  mov     ebx, eax
0x18001d227  test    eax, eax
0x18001d229  js      short loc_18001D232
0x18001d22b  jmp     short loc_18001D2A2
0x18001d22d  mov     ebx, 82CF0119h
0x18001d232  lea     rsi, [rdi+0F0h]
0x18001d239  jmp     short loc_18001D268
0x18001d23b  mov     rcx, [rdx]
0x18001d23e  mov     rax, [rdx+8]
0x18001d242  mov     [rax], rcx
0x18001d245  mov     [rcx+8], rax
0x18001d249  lea     rcx, [rdx-8]
0x18001d24d  test    rcx, rcx
0x18001d250  jz      short loc_18001D262
0x18001d252  mov     rax, [rcx]
0x18001d255  mov     edx, 1
0x18001d25a  mov     rax, [rax]
0x18001d25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d262  dec     dword ptr [rdi+0E8h]
0x18001d268  mov     rdx, [rsi]
0x18001d26b  cmp     rdx, rsi
0x18001d26e  jnz     short loc_18001D23B
0x18001d270  mov     rcx, [rdi+0E0h]
0x18001d277  test    rcx, rcx
0x18001d27a  jz      short loc_18001D297
0x18001d27c  mov     rax, [rcx]
0x18001d27f  mov     edx, 1
0x18001d284  mov     rax, [rax]
0x18001d287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d28c  mov     qword ptr [rdi+0E0h], 0
0x18001d297  mov     qword ptr [rdi+0B0h], 0
0x18001d2a2  mov     rcx, [rbp+37h+var_60]
0x18001d2a6  test    rcx, rcx
0x18001d2a9  jz      loc_18001D022
0x18001d2af  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001d2b5  jmp     loc_18001D022
0x18001d2ba  mov     eax, 80004003h
0x18001d2bf  mov     rcx, [rbp+37h+var_38]
0x18001d2c3  xor     rcx, rsp; StackCookie
0x18001d2c6  call    __security_check_cookie
0x18001d2cb  mov     rbx, [rsp+0C0h+arg_8]
0x18001d2d3  add     rsp, 90h
0x18001d2da  pop     r15
0x18001d2dc  pop     r14
0x18001d2de  pop     r13
0x18001d2e0  pop     r12
0x18001d2e2  pop     rdi
0x18001d2e3  pop     rsi
0x18001d2e4  pop     rbp
0x18001d2e5  retn
```
