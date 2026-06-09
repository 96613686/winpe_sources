# CBroker::SebEvent::~SebEvent(void)

- ea: `0x180012480`
- end: `0x180012693`
- name: `??1SebEvent@CBroker@@UEAA@XZ`
- size: `531`
- prototype: `void __fastcall(CBroker::SebEvent *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180012440`

## callees

- `0x180008c00`
- `0x180012480`
- `0x180019130`
- `0x18001d364`
- `0x18001e0d8`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800124a0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800124a0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800124d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800124d7`
- `ntdll!NtDeleteWnfStateName` at `0x1800124f9`
- `ntdll!NtDeleteWnfStateName` at `0x1800124f9`
- `ntdll!RtlWakeAddressAll` at `0x1800124ca`
- `ntdll!RtlWakeAddressAll` at `0x1800124ca`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012614`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012614`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800124a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800124a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBroker::SebEvent::~SebEvent(CBroker::SebEvent *this)
{
  int v2; // edi
  unsigned __int64 v3; // rdx
  void **v4; // rax
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  void *v7; // rcx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  void *v10; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = &CBroker::SebEvent::`vftable';
  RtlAcquireSRWLockExclusive((char *)this + 240);
  GetCurrentThreadId();
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
      (char *)this + 120);
  v2 = *((_DWORD *)this + 38);
  *((_DWORD *)this + 38) = 0;
  RtlWakeAddressAll();
  RtlReleaseSRWLockExclusive((char *)this + 240);
  if ( v2 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF__guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
        (char *)this + 120);
    RtlUnsubscribeWnfNotificationWaitForCompletion(*((_QWORD *)this + 21));
    *((_QWORD *)this + 21) = 0;
  }
  v4 = (void **)*((_QWORD *)this + 32);
  if ( v4 )
  {
    if ( *v4 )
      operator delete(*v4, v3);
    operator delete(*((void **)this + 32), 0x10u);
  }
  NtDeleteWnfStateName((char *)this + 112);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
      (char *)this + 120);
  v5 = *((_QWORD *)this + 11);
  if ( v5 > 7 )
    std::_Deallocate<16>(*((void **)this + 8), 2 * v5 + 2);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 7;
  *((_WORD *)this + 32) = 0;
  v6 = *((_QWORD *)this + 7);
  if ( v6 > 7 )
    std::_Deallocate<16>(*((void **)this + 4), 2 * v6 + 2);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 7;
  *((_WORD *)this + 16) = 0;
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    v8 = *((_QWORD *)this + 3) - (_QWORD)v7;
    v10 = (void *)*((_QWORD *)this + 1);
    v9 = v8;
    if ( v8 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v10, &v9);
      v8 = v9;
      v7 = v10;
    }
    operator delete(v7, v8);
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180012480  mov     [rsp+arg_10], rbx
0x180012485  push    rbp
0x180012486  push    rsi
0x180012487  push    rdi
0x180012488  sub     rsp, 20h
0x18001248c  lea     rax, ??_7SebEvent@CBroker@@6B@; const CBroker::SebEvent::`vftable'
0x180012493  mov     rbx, rcx
0x180012496  mov     [rcx], rax
0x180012499  add     rcx, 0F0h
0x1800124a0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800124a6  call    cs:__imp_GetCurrentThreadId
0x1800124ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124b3  test    byte ptr [rcx+1Ch], 1
0x1800124b7  jnz     loc_1800125B9
0x1800124bd  lea     rcx, [rbx+98h]
0x1800124c4  xor     ebp, ebp
0x1800124c6  mov     edi, [rcx]
0x1800124c8  mov     [rcx], ebp
0x1800124ca  call    cs:__imp_RtlWakeAddressAll
0x1800124d0  lea     rcx, [rbx+0F0h]
0x1800124d7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800124dd  test    edi, edi
0x1800124df  jnz     loc_1800125E1
0x1800124e5  mov     rax, [rbx+100h]
0x1800124ec  test    rax, rax
0x1800124ef  jnz     loc_180012626
0x1800124f5  lea     rcx, [rbx+70h]
0x1800124f9  call    cs:__imp_NtDeleteWnfStateName
0x1800124ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180012506  test    byte ptr [rcx+1Ch], 1
0x18001250a  jnz     loc_180012591
0x180012510  mov     rdx, [rbx+58h]
0x180012514  cmp     rdx, 7
0x180012518  ja      loc_180012649
0x18001251e  mov     [rbx+50h], rbp
0x180012522  mov     qword ptr [rbx+58h], 7
0x18001252a  mov     [rbx+40h], bp
0x18001252e  mov     rdx, [rbx+38h]
0x180012532  cmp     rdx, 7
0x180012536  ja      loc_18001265F
0x18001253c  mov     [rbx+30h], rbp
0x180012540  mov     qword ptr [rbx+38h], 7
0x180012548  mov     [rbx+20h], bp
0x18001254c  mov     rcx, [rbx+8]; void *
0x180012550  test    rcx, rcx
0x180012553  jz      short loc_180012584
0x180012555  mov     rdx, [rbx+18h]
0x180012559  sub     rdx, rcx; unsigned __int64
0x18001255c  mov     [rsp+38h+arg_8], rcx
0x180012561  mov     [rsp+38h+arg_0], rdx
0x180012566  cmp     rdx, 1000h
0x18001256d  jnb     loc_180012675
0x180012573  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012578  mov     [rbx+8], rbp
0x18001257c  mov     [rbx+10h], rbp
0x180012580  mov     [rbx+18h], rbp
0x180012584  mov     rbx, [rsp+38h+arg_10]
0x180012589  add     rsp, 20h
0x18001258d  pop     rdi
0x18001258e  pop     rsi
0x18001258f  pop     rbp
0x180012590  retn
0x180012591  cmp     byte ptr [rcx+19h], 4
0x180012595  jb      loc_180012510
0x18001259b  mov     rcx, [rcx+10h]
0x18001259f  lea     r9, [rbx+78h]
0x1800125a3  mov     edx, 1Ch
0x1800125a8  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x1800125af  call    WPP_SF__guid_
0x1800125b4  jmp     loc_180012510
0x1800125b9  cmp     byte ptr [rcx+19h], 4
0x1800125bd  jb      loc_1800124BD
0x1800125c3  mov     rcx, [rcx+10h]
0x1800125c7  lea     r9, [rbx+78h]
0x1800125cb  mov     edx, 1Ah
0x1800125d0  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x1800125d7  call    WPP_SF__guid_
0x1800125dc  jmp     loc_1800124BD
0x1800125e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125e8  test    byte ptr [rcx+1Ch], 1
0x1800125ec  jz      short loc_18001260D
0x1800125ee  cmp     byte ptr [rcx+19h], 4
0x1800125f2  jb      short loc_18001260D
0x1800125f4  mov     rcx, [rcx+10h]
0x1800125f8  lea     r9, [rbx+78h]
0x1800125fc  mov     edx, 1Bh
0x180012601  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180012608  call    WPP_SF__guid_
0x18001260d  mov     rcx, [rbx+0A8h]
0x180012614  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001261a  mov     [rbx+0A8h], rbp
0x180012621  jmp     loc_1800124E5
0x180012626  mov     rcx, [rax]; void *
0x180012629  test    rcx, rcx
0x18001262c  jz      short loc_180012633
0x18001262e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012633  mov     rcx, [rbx+100h]; void *
0x18001263a  mov     edx, 10h; unsigned __int64
0x18001263f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012644  jmp     loc_1800124F5
0x180012649  mov     rcx, [rbx+40h]
0x18001264d  lea     rdx, ds:2[rdx*2]
0x180012655  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001265a  jmp     loc_18001251E
0x18001265f  mov     rcx, [rbx+20h]
0x180012663  lea     rdx, ds:2[rdx*2]
0x18001266b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012670  jmp     loc_18001253C
0x180012675  lea     rdx, [rsp+38h+arg_0]; unsigned __int64 *
0x18001267a  lea     rcx, [rsp+38h+arg_8]; void **
0x18001267f  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180012684  mov     rdx, [rsp+38h+arg_0]
0x180012689  mov     rcx, [rsp+38h+arg_8]
0x18001268e  jmp     loc_180012573
```
