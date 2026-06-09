# Action::ActionFactory(CSchedule *,_TASK_ACTION * const,Action * *)

- ea: `0x180003c10`
- end: `0x180003f8d`
- name: `?ActionFactory@Action@@SAJPEAVCSchedule@@QEAU_TASK_ACTION@@PEAPEAV1@@Z`
- size: `893`
- prototype: `__int64 __fastcall(struct CSchedule *, struct _TASK_ACTION *const, struct Action **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180003fa0`

## callees

- `0x1800030a8`
- `0x180003100`
- `0x180003c10`
- `0x18000e970`
- `0x180010094`
- `0x180019d80`
- `0x18001a7d8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall Action::ActionFactory(struct _GUID *a1, struct _TASK_ACTION *const a2, struct _WNF_STATE_NAME **a3)
{
  __int64 v6; // r8
  struct _WNF_STATE_NAME *v8; // rax
  __int64 v9; // rcx
  struct _WNF_STATE_NAME *v10; // rbx
  __int64 v11; // rcx
  void *v12; // rax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  Action *v16; // rax
  Action *v17; // rax
  Action *v18; // rax

  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( (byte_180030D03 & 4) != 0 )
    McTemplateU0q_EventWriteTransfer((__int64)a1, (const EVENT_DESCRIPTOR *)ScheduleActionType, *(unsigned int *)a2);
  v6 = *(unsigned int *)a2;
  switch ( (_DWORD)v6 )
  {
    case 2:
      v18 = (Action *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
      v10 = (struct _WNF_STATE_NAME *)v18;
      if ( !v18 )
      {
        if ( (byte_180030D01 & 2) == 0 )
          return 2194604294LL;
LABEL_42:
        McTemplateU0q_EventWriteTransfer(v9, (const EVENT_DESCRIPTOR *)ActionCreationError, *(unsigned int *)a2);
        return 2194604294LL;
      }
      Action::Action(v18);
      v10[9].Data[0] = 2;
      v10[21] = 0;
      *v10 = (struct _WNF_STATE_NAME)&off_180023278;
      v10[10] = (struct _WNF_STATE_NAME)&v10[20];
      if ( anonymous_namespace_::ActionEvent::Set((__int64)v10, (__int64)a1, *((_QWORD *)a2 + 1)) )
        goto LABEL_40;
      (*(void (__fastcall **)(struct _WNF_STATE_NAME *, __int64))(*(_QWORD *)v10 + 64LL))(v10, 1);
      if ( (byte_180030D01 & 2) != 0 )
        goto LABEL_39;
      return 2194604297LL;
    case 0:
      v17 = (Action *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
      v10 = (struct _WNF_STATE_NAME *)v17;
      if ( !v17 )
        goto LABEL_20;
      Action::Action(v17);
      v10[22].Data[0] = 0;
      v10[20] = 0;
      *v10 = (struct _WNF_STATE_NAME)&off_180023F98;
      v10[10] = (struct _WNF_STATE_NAME)&v10[20];
      v10[21] = 0;
      v10[9].Data[0] = 0;
      v14 = anonymous_namespace_::ActionLaunch::Set((__int64)v10, (__int64)a1, *((unsigned __int16 ***)a2 + 1));
      goto LABEL_25;
    case 1:
      if ( !ActionExtensionFunctionTable )
        return 2194604312LL;
      v16 = (Action *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
      v10 = (struct _WNF_STATE_NAME *)v16;
      if ( !v16 )
        goto LABEL_20;
      Action::Action(v16);
      v10[20] = 0;
      *v10 = (struct _WNF_STATE_NAME)&off_180024030;
      v10[1] = (struct _WNF_STATE_NAME)a1;
      v10[9].Data[0] = *(_DWORD *)a2;
      if ( (*(int (__fastcall **)(struct _TASK_ACTION *const))ActionExtensionFunctionTable)(a2) >= 0 )
        goto LABEL_40;
      (*(void (__fastcall **)(struct _WNF_STATE_NAME *, __int64))(*(_QWORD *)v10 + 64LL))(v10, 1);
      if ( (byte_180030D01 & 2) != 0 )
        goto LABEL_39;
      return 2194604297LL;
    case 3:
      v12 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v12 )
        goto LABEL_20;
      v13 = anonymous_namespace_::ActionWNF::ActionWNF(v12);
      v10 = (struct _WNF_STATE_NAME *)v13;
      if ( !v13 )
        goto LABEL_20;
      v14 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, _QWORD))(*(_QWORD *)v13 + 72LL))(
              v13,
              a1,
              *((_QWORD *)a2 + 1));
LABEL_25:
      if ( v14 )
        goto LABEL_40;
      (*(void (__fastcall **)(struct _WNF_STATE_NAME *, __int64))(*(_QWORD *)v10 + 64LL))(v10, 1);
      if ( (byte_180030D01 & 2) == 0 )
        return 2194604297LL;
LABEL_39:
      McTemplateU0q_EventWriteTransfer(v15, (const EVENT_DESCRIPTOR *)ActionCreationError, *(unsigned int *)a2);
      return 2194604297LL;
    case 4:
      v8 = (struct _WNF_STATE_NAME *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
      v10 = v8;
      if ( v8 )
      {
        anonymous_namespace_::ActionWNF::ActionWNF(v8);
        v10[9].Data[0] = 4;
        *v10 = (struct _WNF_STATE_NAME)&off_180023FE0;
        if ( !(unsigned int)anonymous_namespace_::ActionWNFAdHoc::Set(v10, a1, *((__int128 **)a2 + 1)) )
        {
          if ( (byte_180030D01 & 2) != 0 )
            McTemplateU0q_EventWriteTransfer(v11, (const EVENT_DESCRIPTOR *)ActionCreationError, *(unsigned int *)a2);
          (*(void (__fastcall **)(struct _WNF_STATE_NAME *, __int64))(*(_QWORD *)v10 + 64LL))(v10, 1);
          return 2194604297LL;
        }
LABEL_40:
        *a3 = v10;
        return 0;
      }
LABEL_20:
      if ( (byte_180030D01 & 2) == 0 )
        return 2194604294LL;
      goto LABEL_42;
  }
  if ( (byte_180030D01 & 2) != 0 )
    McTemplateU0q_EventWriteTransfer((unsigned int)(v6 - 3), (const EVENT_DESCRIPTOR *)ActionCreationError, v6);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180003c10  push    rbp
0x180003c12  push    rsi
0x180003c13  push    rdi
0x180003c14  sub     rsp, 20h
0x180003c18  mov     rdi, r8
0x180003c1b  mov     rsi, rdx
0x180003c1e  mov     rbp, rcx
0x180003c21  test    rdx, rdx
0x180003c24  jz      loc_180003F83
0x180003c2a  test    r8, r8
0x180003c2d  jz      loc_180003F83
0x180003c33  mov     [rsp+38h+arg_10], r14
0x180003c38  xor     r14d, r14d
0x180003c3b  mov     [r8], r14
0x180003c3e  test    cs:byte_180030D03, 4
0x180003c45  jz      short loc_180003C56
0x180003c47  mov     r8d, [rdx]
0x180003c4a  lea     rdx, ScheduleActionType
0x180003c51  call    McTemplateU0q_EventWriteTransfer
0x180003c56  mov     r8d, [rsi]
0x180003c59  mov     [rsp+38h+arg_0], rbx
0x180003c5e  cmp     r8d, 2
0x180003c62  jz      loc_180003EC9
0x180003c68  mov     ecx, r8d
0x180003c6b  test    r8d, r8d
0x180003c6e  jz      loc_180003E61
0x180003c74  sub     ecx, 1
0x180003c77  jz      loc_180003DC3
0x180003c7d  sub     ecx, 2
0x180003c80  jz      loc_180003D54
0x180003c86  cmp     ecx, 1
0x180003c89  jz      short loc_180003CAA
0x180003c8b  test    cs:byte_180030D01, 2
0x180003c92  jz      short loc_180003CA0
0x180003c94  lea     rdx, ActionCreationError
0x180003c9b  call    McTemplateU0q_EventWriteTransfer
0x180003ca0  mov     eax, 80004005h
0x180003ca5  jmp     loc_180003D30
0x180003caa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003cb1  mov     ecx, 0B8h; unsigned __int64
0x180003cb6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003cbb  mov     [rsp+38h+arg_8], rax
0x180003cc0  mov     rbx, rax
0x180003cc3  test    rax, rax
0x180003cc6  jz      short loc_180003D42
0x180003cc8  mov     rcx, rax
0x180003ccb  call    _anonymous_namespace___ActionWNF__ActionWNF
0x180003cd0  mov     dword ptr [rbx+48h], 4
0x180003cd7  lea     rcx, off_180023FE0
0x180003cde  mov     [rbx], rcx
0x180003ce1  mov     rdx, rbp
0x180003ce4  mov     r8, [rsi+8]
0x180003ce8  mov     rcx, rbx
0x180003ceb  mov     rax, cs:off_180024028
0x180003cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cf7  test    eax, eax
0x180003cf9  jnz     loc_180003F57
0x180003cff  test    cs:byte_180030D01, 2
0x180003d06  jz      short loc_180003D17
0x180003d08  mov     r8d, [rsi]
0x180003d0b  lea     rdx, ActionCreationError
0x180003d12  call    McTemplateU0q_EventWriteTransfer
0x180003d17  mov     rax, [rbx]
0x180003d1a  mov     edx, 1
0x180003d1f  mov     rcx, rbx
0x180003d22  mov     rax, [rax+40h]
0x180003d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d2b  mov     eax, 82CF0109h
0x180003d30  mov     rbx, [rsp+38h+arg_0]
0x180003d35  mov     r14, [rsp+38h+arg_10]
0x180003d3a  add     rsp, 20h
0x180003d3e  pop     rdi
0x180003d3f  pop     rsi
0x180003d40  pop     rbp
0x180003d41  retn
0x180003d42  test    cs:byte_180030D01, 2
0x180003d49  jnz     loc_180003F6A
0x180003d4f  jmp     loc_180003F79
0x180003d54  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003d5b  mov     ecx, 0B8h; unsigned __int64
0x180003d60  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003d65  mov     [rsp+38h+arg_8], rax
0x180003d6a  test    rax, rax
0x180003d6d  jz      short loc_180003D42
0x180003d6f  mov     rcx, rax
0x180003d72  call    _anonymous_namespace___ActionWNF__ActionWNF
0x180003d77  mov     rbx, rax
0x180003d7a  test    rax, rax
0x180003d7d  jz      short loc_180003D42
0x180003d7f  mov     rax, [rax]
0x180003d82  mov     rdx, rbp
0x180003d85  mov     r8, [rsi+8]
0x180003d89  mov     rcx, rbx
0x180003d8c  mov     rax, [rax+48h]
0x180003d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d95  test    eax, eax
0x180003d97  jnz     loc_180003F57
0x180003d9d  mov     rax, [rbx]
0x180003da0  mov     edx, 1
0x180003da5  mov     rcx, rbx
0x180003da8  mov     rax, [rax+40h]
0x180003dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db1  test    cs:byte_180030D01, 2
0x180003db8  jnz     loc_180003F43
0x180003dbe  jmp     loc_180003D2B
0x180003dc3  cmp     cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA, r14; _ActionExtFunctions * ActionExtensionFunctionTable
0x180003dca  jz      loc_180003E57
0x180003dd0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003dd7  mov     ecx, 0A8h; unsigned __int64
0x180003ddc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003de1  mov     [rsp+38h+arg_8], rax
0x180003de6  mov     rbx, rax
0x180003de9  test    rax, rax
0x180003dec  jz      loc_180003D42
0x180003df2  mov     rcx, rax; this
0x180003df5  call    ??0Action@@QEAA@XZ; Action::Action(void)
0x180003dfa  lea     rdx, [rbx+0A0h]
0x180003e01  mov     [rdx], r14
0x180003e04  lea     rcx, off_180024030
0x180003e0b  mov     [rbx], rcx
0x180003e0e  mov     rcx, rsi
0x180003e11  mov     [rbx+8], rbp
0x180003e15  mov     eax, [rsi]
0x180003e17  mov     [rbx+48h], eax
0x180003e1a  mov     rax, cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA; _ActionExtFunctions * ActionExtensionFunctionTable
0x180003e21  mov     rax, [rax]
0x180003e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e29  test    eax, eax
0x180003e2b  jns     loc_180003F57
0x180003e31  mov     rax, [rbx]
0x180003e34  mov     edx, 1
0x180003e39  mov     rcx, rbx
0x180003e3c  mov     rax, [rax+40h]
0x180003e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e45  test    cs:byte_180030D01, 2
0x180003e4c  jnz     loc_180003F43
0x180003e52  jmp     loc_180003D2B
0x180003e57  mov     eax, 82CF0118h
0x180003e5c  jmp     loc_180003D30
0x180003e61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003e68  mov     ecx, 0B8h; unsigned __int64
0x180003e6d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003e72  mov     [rsp+38h+arg_8], rax
0x180003e77  mov     rbx, rax
0x180003e7a  test    rax, rax
0x180003e7d  jz      loc_180003D42
0x180003e83  mov     rcx, rax; this
0x180003e86  call    ??0Action@@QEAA@XZ; Action::Action(void)
0x180003e8b  lea     rax, [rbx+0A0h]
0x180003e92  mov     [rbx+0B0h], r14d
0x180003e99  lea     rcx, off_180023F98
0x180003ea0  mov     [rax], r14
0x180003ea3  mov     [rbx], rcx
0x180003ea6  mov     rdx, rbp
0x180003ea9  mov     [rbx+50h], rax
0x180003ead  mov     rcx, rbx
0x180003eb0  mov     [rbx+0A8h], r14
0x180003eb7  mov     [rbx+48h], r14d
0x180003ebb  mov     r8, [rsi+8]
0x180003ebf  call    _anonymous_namespace___ActionLaunch__Set
0x180003ec4  jmp     loc_180003D95
0x180003ec9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003ed0  mov     ecx, 0B0h; unsigned __int64
0x180003ed5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003eda  mov     [rsp+38h+arg_8], rax
0x180003edf  mov     rbx, rax
0x180003ee2  test    rax, rax
0x180003ee5  jz      short loc_180003F61
0x180003ee7  mov     rcx, rax; this
0x180003eea  call    ??0Action@@QEAA@XZ; Action::Action(void)
0x180003eef  lea     rax, [rbx+0A0h]
0x180003ef6  mov     dword ptr [rbx+48h], 2
0x180003efd  lea     rcx, off_180023278
0x180003f04  mov     [rax+8], r14
0x180003f08  mov     [rbx], rcx
0x180003f0b  mov     rdx, rbp
0x180003f0e  mov     [rbx+50h], rax
0x180003f12  mov     rcx, rbx
0x180003f15  mov     r8, [rsi+8]
0x180003f19  call    _anonymous_namespace___ActionEvent__Set
0x180003f1e  test    eax, eax
0x180003f20  jnz     short loc_180003F57
0x180003f22  mov     rax, [rbx]
0x180003f25  mov     edx, 1
0x180003f2a  mov     rcx, rbx
0x180003f2d  mov     rax, [rax+40h]
0x180003f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f36  test    cs:byte_180030D01, 2
0x180003f3d  jz      loc_180003D2B
0x180003f43  mov     r8d, [rsi]
0x180003f46  lea     rdx, ActionCreationError
0x180003f4d  call    McTemplateU0q_EventWriteTransfer
0x180003f52  jmp     loc_180003D2B
0x180003f57  mov     [rdi], rbx
0x180003f5a  xor     eax, eax
0x180003f5c  jmp     loc_180003D30
0x180003f61  test    cs:byte_180030D01, 2
0x180003f68  jz      short loc_180003F79
0x180003f6a  mov     r8d, [rsi]
0x180003f6d  lea     rdx, ActionCreationError
0x180003f74  call    McTemplateU0q_EventWriteTransfer
0x180003f79  mov     eax, 82CF0106h
0x180003f7e  jmp     loc_180003D30
0x180003f83  mov     eax, 80004003h
0x180003f88  jmp     loc_180003D3A
```
