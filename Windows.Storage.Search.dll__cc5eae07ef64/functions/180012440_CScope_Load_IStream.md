# CScope::Load(IStream *)

- ea: `0x180012440`
- end: `0x180012636`
- name: `?Load@CScope@@UEAAJPEAUIStream@@@Z`
- size: `502`
- prototype: `int(CScope *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180010cb0`
- `0x180012440`
- `0x180012978`
- `0x18001e4c4`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Read` at `0x180012488`
- `SHCORE!IStream_Read` at `0x1800124c3`
- `SHCORE!IStream_Read` at `0x1800124f3`
- `SHCORE!IStream_Read` at `0x18001250c`
- `SHCORE!IStream_Read` at `0x180012488`
- `SHCORE!IStream_Read` at `0x1800124c3`
- `SHCORE!IStream_Read` at `0x1800124f3`
- `SHCORE!IStream_Read` at `0x18001250c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012518`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012518`

## pseudocode

```c
__int64 __fastcall CScope::Load(RTL_SRWLOCK *this, struct IStream *a2, int a3)
{
  int v5; // ecx
  HRESULT Instance; // ebx
  int v7; // r8d
  const struct _GUID *v8; // rdx
  struct IUnknown *v9; // rcx
  unsigned int v10; // eax
  unsigned int v12; // esi
  unsigned int pv; // [rsp+30h] [rbp-30h] BYREF
  struct IScopeItem *v14; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v15[2]; // [rsp+40h] [rbp-20h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer((_DWORD)this, (unsigned int)"qB", a3, 1, (__int64)v15);
  pv = 0;
  Instance = IStream_Read(a2, &pv, 4u);
  if ( Instance >= 0 )
  {
    if ( pv == -2147483646 )
    {
      AcquireSRWLockExclusive(this + 10);
      pv = 0;
      Instance = IStream_Read(a2, &pv, 4u);
      if ( Instance >= 0 )
      {
        v10 = pv;
        if ( pv )
        {
          if ( pv > 0x40 )
          {
            Instance = -2147024809;
            goto LABEL_11;
          }
          v12 = 0;
          while ( v12 < v10 )
          {
            v14 = 0;
            Instance = CScopeItem_CreateInstance(v9, v8, (void **)&v14);
            if ( Instance >= 0 )
            {
              v15[0] = 0;
              Instance = (**(__int64 (__fastcall ***)(struct IScopeItem *, GUID *, _QWORD *))v14)(
                           v14,
                           &GUID_00000109_0000_0000_c000_000000000046,
                           v15);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(_QWORD, struct IStream *))(*(_QWORD *)v15[0] + 40LL))(v15[0], a2);
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15[0] + 16LL))(v15[0]);
                if ( Instance >= 0 )
                  Instance = CScope::_AddScopeTreeItemInternal((CScope *)&this[-3], v14, 0, 0);
              }
              (*(void (__fastcall **)(struct IScopeItem *))(*(_QWORD *)v14 + 16LL))(v14);
            }
            ++v12;
            if ( Instance < 0 )
              goto LABEL_11;
            v10 = pv;
          }
        }
        Instance = IStream_Read(a2, (char *)&this[3].Ptr + 4, 0x10u);
        if ( Instance >= 0 )
          Instance = IStream_Read(a2, (char *)&this[5].Ptr + 4, 4u);
      }
LABEL_11:
      ReleaseSRWLockExclusive(this + 10);
      goto LABEL_12;
    }
    Instance = -2147024809;
  }
LABEL_12:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v5, (unsigned int)Scope_Load_From_Stream_Stop, v7, 1, (__int64)v15);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180012440  mov     [rsp-28h+arg_10], rbx
0x180012445  push    rbp
0x180012446  push    rsi
0x180012447  push    rdi
0x180012448  push    r14
0x18001244a  push    r15
0x18001244c  mov     rbp, rsp
0x18001244f  sub     rsp, 60h
0x180012453  mov     rax, cs:__security_cookie
0x18001245a  xor     rax, rsp
0x18001245d  mov     [rbp+var_10], rax
0x180012461  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180012468  mov     rdi, rdx
0x18001246b  mov     r14, rcx
0x18001246e  jnz     loc_180012550
0x180012474  mov     r8d, 4; cb
0x18001247a  mov     [rbp+pv], 0
0x180012481  lea     rdx, [rbp+pv]; pv
0x180012485  mov     rcx, rdi; pstm
0x180012488  call    cs:__imp_IStream_Read
0x18001248e  mov     ebx, eax
0x180012490  test    eax, eax
0x180012492  js      loc_18001251E
0x180012498  cmp     [rbp+pv], 80000002h
0x18001249f  jnz     loc_180012549
0x1800124a5  lea     rcx, [r14+50h]; SRWLock
0x1800124a9  call    cs:__imp_AcquireSRWLockExclusive
0x1800124af  mov     r8d, 4; cb
0x1800124b5  mov     [rbp+pv], 0
0x1800124bc  lea     rdx, [rbp+pv]; pv
0x1800124c0  mov     rcx, rdi; pstm
0x1800124c3  call    cs:__imp_IStream_Read
0x1800124c9  mov     ebx, eax
0x1800124cb  test    eax, eax
0x1800124cd  js      short loc_180012514
0x1800124cf  mov     eax, [rbp+pv]
0x1800124d2  test    eax, eax
0x1800124d4  jz      short loc_1800124E6
0x1800124d6  cmp     eax, 40h ; '@'
0x1800124d9  jbe     loc_18001258D
0x1800124df  mov     ebx, 80070057h
0x1800124e4  jmp     short loc_180012514
0x1800124e6  lea     rdx, [r14+1Ch]; pv
0x1800124ea  mov     r8d, 10h; cb
0x1800124f0  mov     rcx, rdi; pstm
0x1800124f3  call    cs:__imp_IStream_Read
0x1800124f9  mov     ebx, eax
0x1800124fb  test    eax, eax
0x1800124fd  js      short loc_180012514
0x1800124ff  lea     rdx, [r14+2Ch]; pv
0x180012503  mov     r8d, 4; cb
0x180012509  mov     rcx, rdi; pstm
0x18001250c  call    cs:__imp_IStream_Read
0x180012512  mov     ebx, eax
0x180012514  lea     rcx, [r14+50h]; SRWLock
0x180012518  call    cs:__imp_ReleaseSRWLockExclusive
0x18001251e  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180012525  jnz     short loc_180012570
0x180012527  mov     eax, ebx
0x180012529  mov     rcx, [rbp+var_10]
0x18001252d  xor     rcx, rsp; StackCookie
0x180012530  call    __security_check_cookie
0x180012535  mov     rbx, [rsp+60h+arg_10]
0x18001253d  add     rsp, 60h
0x180012541  pop     r15
0x180012543  pop     r14
0x180012545  pop     rdi
0x180012546  pop     rsi
0x180012547  pop     rbp
0x180012548  retn
0x180012549  mov     ebx, 80070057h
0x18001254e  jmp     short loc_18001251E
0x180012550  lea     rax, [rbp+var_20]
0x180012554  mov     r9d, 1
0x18001255a  lea     rdx, Scope_Load_From_Stream_Start; "qB"
0x180012561  mov     [rsp+60h+var_40], rax
0x180012566  call    McGenEventWrite_EtwEventWriteTransfer
0x18001256b  jmp     loc_180012474
0x180012570  lea     rax, [rbp+var_20]
0x180012574  mov     r9d, 1
0x18001257a  lea     rdx, Scope_Load_From_Stream_Stop
0x180012581  mov     [rsp+60h+var_40], rax
0x180012586  call    McGenEventWrite_EtwEventWriteTransfer
0x18001258b  jmp     short loc_180012527
0x18001258d  xor     esi, esi
0x18001258f  cmp     esi, eax
0x180012591  jnb     loc_1800124E6
0x180012597  lea     r8, [rbp+var_28]; void **
0x18001259b  mov     [rbp+var_28], 0
0x1800125a3  call    ?CScopeItem_CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CScopeItem_CreateInstance(IUnknown *,_GUID const &,void * *)
0x1800125a8  mov     ebx, eax
0x1800125aa  test    eax, eax
0x1800125ac  js      short loc_180012624
0x1800125ae  mov     rcx, [rbp+var_28]
0x1800125b2  lea     r8, [rbp+var_20]
0x1800125b6  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x1800125bd  mov     [rbp+var_20], 0
0x1800125c5  mov     rax, [rcx]
0x1800125c8  mov     rax, [rax]
0x1800125cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125d0  mov     ebx, eax
0x1800125d2  test    eax, eax
0x1800125d4  js      short loc_180012614
0x1800125d6  mov     rcx, [rbp+var_20]
0x1800125da  mov     rdx, rdi
0x1800125dd  mov     rax, [rcx]
0x1800125e0  mov     rax, [rax+28h]
0x1800125e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125e9  mov     rcx, [rbp+var_20]
0x1800125ed  mov     ebx, eax
0x1800125ef  mov     rax, [rcx]
0x1800125f2  mov     rax, [rax+10h]
0x1800125f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125fb  test    ebx, ebx
0x1800125fd  js      short loc_180012614
0x1800125ff  mov     rdx, [rbp+var_28]; struct IScopeItem *
0x180012603  lea     rcx, [r14-18h]; this
0x180012607  xor     r9d, r9d; int *
0x18001260a  xor     r8d, r8d; struct IScopeItem **
0x18001260d  call    ?_AddScopeTreeItemInternal@CScope@@AEAAJPEAUIScopeItem@@PEAPEAU2@PEAH@Z; CScope::_AddScopeTreeItemInternal(IScopeItem *,IScopeItem * *,int *)
0x180012612  mov     ebx, eax
0x180012614  mov     rcx, [rbp+var_28]
0x180012618  mov     rax, [rcx]
0x18001261b  mov     rax, [rax+10h]
0x18001261f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012624  inc     esi
0x180012626  test    ebx, ebx
0x180012628  js      loc_180012514
0x18001262e  mov     eax, [rbp+pv]
0x180012631  jmp     loc_18001258F
```
