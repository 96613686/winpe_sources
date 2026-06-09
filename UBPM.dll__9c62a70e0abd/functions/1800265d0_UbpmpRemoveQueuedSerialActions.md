# UbpmpRemoveQueuedSerialActions

- ea: `0x1800265d0`
- end: `0x180026802`
- name: `UbpmpRemoveQueuedSerialActions`
- size: `562`
- prototype: `__int64 __usercall@<rax>(UUID *Uuid1@<rcx>, UUID *@<rdx>, UUID *@<r8>, __int16)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003da0`
- `0x180008b30`
- `0x18000a230`
- `0x18000f880`

## callees

- `0x18000fbf0`
- `0x18001af64`
- `0x1800265d0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026603`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026603`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026657`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026657`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002660f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002660f`
- `RPCRT4!UuidEqual` at `0x18002673e`
- `RPCRT4!UuidEqual` at `0x180026775`
- `RPCRT4!UuidEqual` at `0x18002679e`
- `RPCRT4!UuidEqual` at `0x18002673e`
- `RPCRT4!UuidEqual` at `0x180026775`
- `RPCRT4!UuidEqual` at `0x18002679e`

## string_xrefs

- `0x1800267e1`: `Removed`
- `0x1800267d3`: `Not removed`

## pseudocode

```c
__int64 __fastcall UbpmpRemoveQueuedSerialActions(UUID *Uuid1, UUID *a2, UUID *a3, void *a4, __int16 a5)
{
  unsigned __int8 v9; // bl
  DWORD CurrentThreadId; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  _UNKNOWN **v14; // rdi
  __int64 v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  _UNKNOWN ***v19; // rax
  _QWORD *v20; // rcx
  _UNKNOWN ***v21; // r13
  const wchar_t *v22; // r9
  RPC_STATUS Status[14]; // [rsp+30h] [rbp-38h] BYREF

  Status[0] = 0;
  v9 = 0;
  RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
  CurrentThreadId = GetCurrentThreadId();
  v14 = (_UNKNOWN **)g_leQueuedSerialActionsListHead;
  dword_18004FFA0 = CurrentThreadId;
  while ( v14 != &g_leQueuedSerialActionsListHead )
  {
    v21 = (_UNKNOWN ***)*v14;
    if ( Uuid1 )
    {
      if ( UuidEqual(Uuid1, (UUID *)v14 + 1, Status) )
      {
        if ( !a5 )
          goto LABEL_6;
        if ( a5 == *((_WORD *)v14 + 28) )
        {
          v19 = (_UNKNOWN ***)*v14;
          if ( *((_UNKNOWN ***)*v14 + 1) != v14 || (v20 = v14[1], (_UNKNOWN **)*v20 != v14) )
LABEL_7:
            __fastfail(3u);
          *v20 = v19;
          v19[1] = (_UNKNOWN **)v20;
          v14[1] = v14;
          *v14 = v14;
          UBPM_MIDL_user_free(v14, v11, v12, v13);
          v9 = 1;
          break;
        }
      }
    }
    else if ( a2 )
    {
      if ( UuidEqual(a2, (UUID *)v14 + 2, Status) && (!a3 || !UuidEqual(a3, (UUID *)v14 + 1, Status)) )
      {
LABEL_6:
        v16 = (__int64)*v14;
        if ( *((_UNKNOWN ***)*v14 + 1) != v14 )
          goto LABEL_7;
        v17 = v14[1];
        if ( (_UNKNOWN **)*v17 != v14 )
          goto LABEL_7;
        *v17 = v16;
        *(_QWORD *)(v16 + 8) = v17;
LABEL_10:
        v14[1] = v14;
        *v14 = v14;
        UBPM_MIDL_user_free(v14, v11, v12, v13);
        v9 = 1;
      }
    }
    else if ( a4 && a4 == v14[6] )
    {
      if ( v21[1] != v14 )
        goto LABEL_7;
      v18 = v14[1];
      if ( (_UNKNOWN **)*v18 != v14 )
        goto LABEL_7;
      *v18 = v21;
      v21[1] = (_UNKNOWN **)v18;
      goto LABEL_10;
    }
    v14 = (_UNKNOWN **)v21;
  }
  dword_18004FFA0 = 0;
  RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v22 = L"Removed";
    if ( !v9 )
      v22 = L"Not removed";
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      (_DWORD)v22,
      a5);
  }
  return v9;
}

```

## disassembly

```asm
0x1800265d0  mov     [rsp+arg_8], rbx
0x1800265d5  mov     [rsp+arg_10], rbp
0x1800265da  push    rsi
0x1800265db  push    rdi
0x1800265dc  push    r12
0x1800265de  push    r14
0x1800265e0  push    r15
0x1800265e2  sub     rsp, 40h
0x1800265e6  mov     r15, rcx
0x1800265e9  mov     [rsp+68h+Status], 0
0x1800265f1  lea     rcx, g_QueuedSerialActionsLock
0x1800265f8  mov     rsi, r9
0x1800265fb  mov     rbp, r8
0x1800265fe  mov     r14, rdx
0x180026601  xor     bl, bl
0x180026603  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002660a  nop     dword ptr [rax+rax+00h]
0x18002660f  call    cs:__imp_GetCurrentThreadId
0x180026616  nop     dword ptr [rax+rax+00h]
0x18002661b  mov     rdi, cs:g_leQueuedSerialActionsListHead
0x180026622  movzx   r12d, [rsp+68h+arg_20]
0x18002662b  mov     cs:dword_18004FFA0, eax
0x180026631  lea     rax, g_leQueuedSerialActionsListHead
0x180026638  mov     [rsp+68h+arg_0], r13
0x18002663d  cmp     rdi, rax
0x180026640  jnz     loc_18002672A
0x180026646  lea     rcx, g_QueuedSerialActionsLock
0x18002664d  mov     cs:dword_18004FFA0, 0
0x180026657  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002665e  nop     dword ptr [rax+rax+00h]
0x180026663  mov     rcx, cs:WPP_GLOBAL_Control
0x18002666a  lea     rax, WPP_GLOBAL_Control
0x180026671  cmp     rcx, rax
0x180026674  jz      short loc_180026680
0x180026676  test    byte ptr [rcx+1Ch], 20h
0x18002667a  jnz     loc_1800267CF
0x180026680  mov     r13, [rsp+68h+arg_0]
0x180026685  movzx   eax, bl
0x180026688  mov     rbx, [rsp+68h+arg_8]
0x18002668d  mov     rbp, [rsp+68h+arg_10]
0x180026695  add     rsp, 40h
0x180026699  pop     r15
0x18002669b  pop     r14
0x18002669d  pop     r12
0x18002669f  pop     rdi
0x1800266a0  pop     rsi
0x1800266a1  retn
0x1800266a3  mov     rax, [rdi]
0x1800266a6  cmp     [rax+8], rdi
0x1800266aa  jz      short loc_1800266B3
0x1800266ac  mov     ecx, 3
0x1800266b1  int     29h; Win8: RtlFailFast(ecx)
0x1800266b3  mov     rcx, [rdi+8]
0x1800266b7  cmp     [rcx], rdi
0x1800266ba  jnz     short loc_1800266AC
0x1800266bc  mov     [rcx], rax
0x1800266bf  mov     [rax+8], rcx
0x1800266c3  mov     [rdi+8], rdi
0x1800266c7  mov     rcx, rdi
0x1800266ca  mov     [rdi], rdi
0x1800266cd  call    UBPM_MIDL_user_free
0x1800266d2  mov     bl, 1
0x1800266d4  lea     rax, g_leQueuedSerialActionsListHead
0x1800266db  mov     rdi, r13
0x1800266de  jmp     loc_18002663D
0x1800266e3  cmp     [r13+8], rdi
0x1800266e7  jnz     short loc_1800266AC
0x1800266e9  mov     rax, [rdi+8]
0x1800266ed  cmp     [rax], rdi
0x1800266f0  jnz     short loc_1800266AC
0x1800266f2  mov     [rax], r13
0x1800266f5  mov     [r13+8], rax
0x1800266f9  jmp     short loc_1800266C3
0x1800266fb  mov     rax, [rdi]
0x1800266fe  cmp     [rax+8], rdi
0x180026702  jnz     short loc_1800266AC
0x180026704  mov     rcx, [rdi+8]
0x180026708  cmp     [rcx], rdi
0x18002670b  jnz     short loc_1800266AC
0x18002670d  mov     [rcx], rax
0x180026710  mov     [rax+8], rcx
0x180026714  mov     rcx, rdi
0x180026717  mov     [rdi+8], rdi
0x18002671b  mov     [rdi], rdi
0x18002671e  call    UBPM_MIDL_user_free
0x180026723  mov     bl, 1
0x180026725  jmp     loc_180026646
0x18002672a  mov     r13, [rdi]
0x18002672d  test    r15, r15
0x180026730  jz      short loc_180026764
0x180026732  lea     rdx, [rdi+10h]; Uuid2
0x180026736  mov     rcx, r15; Uuid1
0x180026739  lea     r8, [rsp+68h+Status]; Status
0x18002673e  call    cs:__imp_UuidEqual
0x180026745  nop     dword ptr [rax+rax+00h]
0x18002674a  test    eax, eax
0x18002674c  jz      short loc_1800266D4
0x18002674e  test    r12w, r12w
0x180026752  jz      loc_1800266A3
0x180026758  cmp     r12w, [rdi+38h]
0x18002675d  jz      short loc_1800266FB
0x18002675f  jmp     loc_1800266D4
0x180026764  test    r14, r14
0x180026767  jz      short loc_1800267B7
0x180026769  lea     rdx, [rdi+20h]; Uuid2
0x18002676d  mov     rcx, r14; Uuid1
0x180026770  lea     r8, [rsp+68h+Status]; Status
0x180026775  call    cs:__imp_UuidEqual
0x18002677c  nop     dword ptr [rax+rax+00h]
0x180026781  test    eax, eax
0x180026783  jz      loc_1800266D4
0x180026789  test    rbp, rbp
0x18002678c  jz      loc_1800266A3
0x180026792  lea     rdx, [rdi+10h]; Uuid2
0x180026796  mov     rcx, rbp; Uuid1
0x180026799  lea     r8, [rsp+68h+Status]; Status
0x18002679e  call    cs:__imp_UuidEqual
0x1800267a5  nop     dword ptr [rax+rax+00h]
0x1800267aa  test    eax, eax
0x1800267ac  jnz     loc_1800266D4
0x1800267b2  jmp     loc_1800266A3
0x1800267b7  test    rsi, rsi
0x1800267ba  jz      loc_1800266DB
0x1800267c0  cmp     rsi, [rdi+30h]
0x1800267c4  jnz     loc_1800266DB
0x1800267ca  jmp     loc_1800266E3
0x1800267cf  mov     rcx, [rcx+10h]
0x1800267d3  lea     rax, aNotRemoved; "Not removed"
0x1800267da  test    bl, bl
0x1800267dc  mov     [rsp+68h+var_48], r12d
0x1800267e1  lea     r9, aRemoved; "Removed"
0x1800267e8  mov     edx, 5Fh ; '_'
0x1800267ed  cmovz   r9, rax
0x1800267f1  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x1800267f8  call    WPP_SF_Sd
0x1800267fd  jmp     loc_180026680
```
