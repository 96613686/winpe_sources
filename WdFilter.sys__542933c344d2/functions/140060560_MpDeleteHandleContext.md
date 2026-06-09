# MpDeleteHandleContext

- ea: `0x140060560`
- end: `0x14006076e`
- name: `MpDeleteHandleContext`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140011890`
- `0x140030060`
- `0x140060560`
- `0x140066180`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14006073f`
- `ntoskrnl!KeBugCheckEx` at `0x14006073f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400606fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060712`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400606fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060712`
- `ntoskrnl!ExQueryDepthSList` at `0x140060600`
- `ntoskrnl!ExQueryDepthSList` at `0x14006065f`
- `ntoskrnl!ExQueryDepthSList` at `0x140060600`
- `ntoskrnl!ExQueryDepthSList` at `0x14006065f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006061a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140060679`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006061a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140060679`
- `FLTMGR!FltDeletePushLock` at `0x14006059d`
- `FLTMGR!FltDeletePushLock` at `0x1400605ad`
- `FLTMGR!FltDeletePushLock` at `0x14006059d`
- `FLTMGR!FltDeletePushLock` at `0x1400605ad`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006075d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006075d`

## pseudocode

```c
void __fastcall MpDeleteHandleContext(__int64 a1, unsigned __int16 a2)
{
  _QWORD *v3; // rsi
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v6; // rcx
  struct _SLIST_ENTRY *v7; // rsi
  struct _SLIST_ENTRY *v8; // r14
  ULONG_PTR v9; // rsi
  USHORT v10; // di
  ULONG_PTR v11; // r14
  USHORT v12; // di
  _QWORD *v13; // r14
  _QWORD *v14; // rax
  __int64 v15; // rcx
  void *v16; // rcx

  if ( a2 != 16 )
    KeBugCheckEx(0x108u, a2, 0x10u, 0, 0);
  v3 = *(_QWORD **)(a1 + 48);
  v4 = (_QWORD *)(a1 + 48);
  while ( v3 != v4 )
  {
    v13 = v3;
    v3 = (_QWORD *)*v3;
    if ( (_QWORD *)v3[1] != v13 || (v14 = (_QWORD *)v13[1], (_QWORD *)*v14 != v13) )
      __fastfail(3u);
    *v14 = v3;
    v3[1] = v14;
    v15 = v13[2];
    if ( v15 )
    {
      MpReleaseProcessContext(v15);
      v13[2] = 0;
    }
    v16 = (void *)v13[4];
    if ( v16 )
    {
      ExFreePoolWithTag(v16, 0x6E66504Du);
      v13[4] = 0;
    }
    ExFreePoolWithTag(v13, 0x6670504Du);
  }
  FltDeletePushLock((PULONG_PTR)(a1 + 72));
  FltDeletePushLock((PULONG_PTR)(a1 + 64));
  v5 = *(_QWORD *)(a1 + 80);
  if ( v5 )
    MpFreeString(v5);
  v6 = (struct _FLT_FILE_NAME_INFORMATION *)_InterlockedExchange64((volatile __int64 *)(a1 + 112), 0);
  if ( v6 )
    FltReleaseFileNameInformation(v6);
  v7 = *(struct _SLIST_ENTRY **)(a1 + 96);
  if ( v7 )
  {
    v11 = MpData + 4224;
    ++*(_DWORD *)(MpData + 4252);
    v12 = *(_WORD *)(v11 + 16);
    if ( ExQueryDepthSList((PSLIST_HEADER)v11) >= v12 )
    {
      ++*(_DWORD *)(v11 + 32);
      (*(void (__fastcall **)(struct _SLIST_ENTRY *))(v11 + 56))(v7);
    }
    else
    {
      _mm_lfence();
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v11, v7);
    }
    *(_QWORD *)(a1 + 96) = 0;
  }
  v8 = *(struct _SLIST_ENTRY **)(a1 + 104);
  if ( v8 )
  {
    v9 = MpData + 4352;
    ++*(_DWORD *)(MpData + 4380);
    v10 = *(_WORD *)(v9 + 16);
    if ( ExQueryDepthSList((PSLIST_HEADER)v9) >= v10 )
    {
      ++*(_DWORD *)(v9 + 32);
      (*(void (__fastcall **)(struct _SLIST_ENTRY *))(v9 + 56))(v8);
    }
    else
    {
      _mm_lfence();
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v9, v8);
    }
    *(_QWORD *)(a1 + 104) = 0;
  }
}

```

## disassembly

```asm
0x140060560  mov     [rsp+arg_18], rbx
0x140060565  push    rbp
0x140060566  sub     rsp, 30h
0x14006056a  xor     ebp, ebp
0x14006056c  mov     rbx, rcx
0x14006056f  cmp     dx, 10h
0x140060573  jnz     loc_140060729
0x140060579  mov     [rsp+38h+arg_0], rsi
0x14006057e  mov     rsi, [rcx+30h]
0x140060582  mov     [rsp+38h+arg_8], rdi
0x140060587  lea     rdi, [rcx+30h]
0x14006058b  mov     [rsp+38h+arg_10], r14
0x140060590  cmp     rsi, rdi
0x140060593  jnz     loc_1400606BA
0x140060599  lea     rcx, [rbx+48h]; PushLock
0x14006059d  call    cs:__imp_FltDeletePushLock
0x1400605a4  nop     dword ptr [rax+rax+00h]
0x1400605a9  lea     rcx, [rbx+40h]; PushLock
0x1400605ad  call    cs:__imp_FltDeletePushLock
0x1400605b4  nop     dword ptr [rax+rax+00h]
0x1400605b9  mov     rcx, [rbx+50h]
0x1400605bd  test    rcx, rcx
0x1400605c0  jnz     loc_140060753
0x1400605c6  mov     rcx, rbp
0x1400605c9  xchg    rcx, [rbx+70h]; FileNameInformation
0x1400605cd  test    rcx, rcx
0x1400605d0  jnz     loc_14006075D
0x1400605d6  mov     rsi, [rbx+60h]
0x1400605da  test    rsi, rsi
0x1400605dd  jnz     short loc_140060645
0x1400605df  mov     r14, [rbx+68h]
0x1400605e3  test    r14, r14
0x1400605e6  jz      short loc_14006062A
0x1400605e8  mov     rsi, cs:MpData
0x1400605ef  add     rsi, 1100h
0x1400605f6  mov     rcx, rsi; SListHead
0x1400605f9  inc     dword ptr [rsi+1Ch]
0x1400605fc  movzx   edi, word ptr [rsi+10h]
0x140060600  call    cs:__imp_ExQueryDepthSList
0x140060607  nop     dword ptr [rax+rax+00h]
0x14006060c  cmp     ax, di
0x14006060f  jnb     short loc_14006068E
0x140060611  lfence
0x140060614  mov     rdx, r14; ListEntry
0x140060617  mov     rcx, rsi; ListHead
0x14006061a  call    cs:__imp_ExpInterlockedPushEntrySList
0x140060621  nop     dword ptr [rax+rax+00h]
0x140060626  mov     [rbx+68h], rbp
0x14006062a  mov     rdi, [rsp+38h+arg_8]
0x14006062f  mov     rsi, [rsp+38h+arg_0]
0x140060634  mov     r14, [rsp+38h+arg_10]
0x140060639  mov     rbx, [rsp+38h+arg_18]
0x14006063e  add     rsp, 30h
0x140060642  pop     rbp
0x140060643  retn
0x140060645  mov     r14, cs:MpData
0x14006064c  add     r14, 1080h
0x140060653  mov     rcx, r14; SListHead
0x140060656  inc     dword ptr [r14+1Ch]
0x14006065a  movzx   edi, word ptr [r14+10h]
0x14006065f  call    cs:__imp_ExQueryDepthSList
0x140060666  nop     dword ptr [rax+rax+00h]
0x14006066b  cmp     ax, di
0x14006066e  jnb     short loc_1400606A0
0x140060670  lfence
0x140060673  mov     rdx, rsi; ListEntry
0x140060676  mov     rcx, r14; ListHead
0x140060679  call    cs:__imp_ExpInterlockedPushEntrySList
0x140060680  nop     dword ptr [rax+rax+00h]
0x140060685  mov     [rbx+60h], rbp
0x140060689  jmp     loc_1400605DF
0x14006068e  inc     dword ptr [rsi+20h]
0x140060691  mov     rcx, r14
0x140060694  mov     rax, [rsi+38h]
0x140060698  call    cs:__guard_dispatch_icall_fptr
0x14006069e  jmp     short loc_140060626
0x1400606a0  inc     dword ptr [r14+20h]
0x1400606a4  mov     rcx, rsi
0x1400606a7  mov     rax, [r14+38h]
0x1400606ab  call    cs:__guard_dispatch_icall_fptr
0x1400606b1  mov     [rbx+60h], rbp
0x1400606b5  jmp     loc_1400605DF
0x1400606ba  mov     r14, rsi
0x1400606bd  mov     rsi, [rsi]
0x1400606c0  cmp     [rsi+8], r14
0x1400606c4  jnz     loc_14006074C
0x1400606ca  mov     rax, [r14+8]
0x1400606ce  cmp     [rax], r14
0x1400606d1  jnz     short loc_14006074C
0x1400606d3  mov     [rax], rsi
0x1400606d6  mov     [rsi+8], rax
0x1400606da  mov     rcx, [r14+10h]
0x1400606de  test    rcx, rcx
0x1400606e1  jz      short loc_1400606EC
0x1400606e3  call    MpReleaseProcessContext
0x1400606e8  mov     [r14+10h], rbp
0x1400606ec  mov     rcx, [r14+20h]; P
0x1400606f0  test    rcx, rcx
0x1400606f3  jz      short loc_14006070A
0x1400606f5  mov     edx, 6E66504Dh; Tag
0x1400606fa  call    cs:__imp_ExFreePoolWithTag
0x140060701  nop     dword ptr [rax+rax+00h]
0x140060706  mov     [r14+20h], rbp
0x14006070a  mov     edx, 6670504Dh; Tag
0x14006070f  mov     rcx, r14; P
0x140060712  call    cs:__imp_ExFreePoolWithTag
0x140060719  nop     dword ptr [rax+rax+00h]
0x14006071e  cmp     rsi, rdi
0x140060721  jz      loc_140060599
0x140060727  jmp     short loc_1400606BA
0x140060729  movzx   edx, dx; BugCheckParameter1
0x14006072c  xor     r9d, r9d; BugCheckParameter3
0x14006072f  mov     ecx, 108h; BugCheckCode
0x140060734  mov     [rsp+38h+BugCheckParameter4], rbp; BugCheckParameter4
0x140060739  mov     r8d, 10h; BugCheckParameter2
0x14006073f  call    cs:__imp_KeBugCheckEx
0x14006074c  mov     ecx, 3
0x140060751  int     29h; Win8: RtlFailFast(ecx)
0x140060753  call    MpFreeString
0x140060758  jmp     loc_1400605C6
0x14006075d  call    cs:__imp_FltReleaseFileNameInformation
0x140060764  nop     dword ptr [rax+rax+00h]
0x140060769  jmp     loc_1400605D6
```
