# CmsLookasides::Allocate(unsigned __int64,EmsLookaside,ulong)

- ea: `0x1400f34d8`
- end: `0x1400f3605`
- name: `?Allocate@CmsLookasides@@SAPEAX_KW4EmsLookaside@@K@Z`
- size: `301`
- prototype: ``
- caller_count: `33`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007ec90`
- `0x140091818`
- `0x1400919d4`
- `0x14009f40c`
- `0x1400aa2ac`
- `0x1400aa3bc`
- `0x1400afda8`
- `0x1400b7fc4`
- `0x1400c26b8`
- `0x1400d989c`
- `0x1400e4d38`
- `0x1400e5008`
- `0x1400e8778`
- `0x1400ef514`
- `0x1400efb0c`
- `0x1400efc0c`
- `0x1400f092c`
- `0x1400f0aa0`
- `0x1400f21c4`
- `0x1400f2280`
- `0x1400f4170`
- `0x1400f57a0`
- `0x1400fd7ec`
- `0x1400fdc08`
- `0x14010e770`
- `0x140112698`
- `0x140118d2c`
- `0x140118dc4`
- `0x14011ac40`
- `0x1401308b0`
- `0x140131434`
- `0x140131480`
- `0x14013263c`

## callees

- `0x140004f44`
- `0x14007fe5c`
- `0x140093498`
- `0x1400ab4fc`
- `0x1400f34d8`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1400f353d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1400f35a3`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1400f353d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1400f35a3`

## pseudocode

```c
PSLIST_ENTRY __fastcall CmsLookasides::Allocate(unsigned __int64 a1, int a2, char a3)
{
  struct _SmsLookaside * near *v5; // rbx
  __int64 PoolWithTagImpl; // rax
  PSLIST_ENTRY v7; // rdi
  signed __int64 v8; // rcx
  int v9; // ecx
  unsigned __int64 v10; // rsi
  struct _SLIST_ENTRY *v11; // rax
  const char *v12; // rcx
  signed __int64 v14; // [rsp+68h] [rbp+20h]

  if ( (a3 & 2) != 0 || (v5 = (&LookasideLists)[a2], a1 > *(unsigned int *)v5) )
  {
    v5 = 0;
    goto LABEL_19;
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    PoolWithTagImpl = MsAllocatePoolWithTagImpl(a1, v5[3], *((unsigned int *)v5 + 8));
    v7 = (PSLIST_ENTRY)PoolWithTagImpl;
    if ( a2 == 1 )
      CmsTransactionContext::InitializeTransactionMemoryBuffer((void *)(PoolWithTagImpl + 8));
  }
  else if ( (a3 & 1) != 0 )
  {
    v7 = InterlockedPopEntrySList((PSLIST_HEADER)v5 + 1);
    do
    {
      v8 = (signed __int64)v5[5];
      LODWORD(v14) = v8 - 1;
      HIDWORD(v14) = HIDWORD(v8) - 1;
    }
    while ( _InterlockedCompareExchange64((volatile signed __int64 *)v5 + 5, v14, v8) != v8 );
  }
  else
  {
    if ( (int)v5[5] <= (int)HIDWORD(v5[5]) )
      goto LABEL_16;
    v9 = _InterlockedDecrement((volatile signed __int32 *)v5 + 10);
    if ( v9 < *((_DWORD *)v5 + 11) || v9 < 0 )
    {
      v7 = 0;
      _InterlockedIncrement((volatile signed __int32 *)v5 + 10);
    }
    else
    {
      v7 = InterlockedPopEntrySList((PSLIST_HEADER)v5 + 1);
    }
  }
  if ( v7 )
    goto LABEL_23;
LABEL_16:
  if ( !v5 )
  {
LABEL_19:
    v10 = a1 + 16;
    goto LABEL_20;
  }
  v10 = *((unsigned int *)v5 + 1);
LABEL_20:
  v11 = (struct _SLIST_ENTRY *)operator new[](v10);
  v7 = v11;
  if ( ((unsigned __int8)v11 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck(v12);
  if ( a2 == 1 )
    CmsTransactionContext::InitializeTransactionMemoryBuffer(&v11[1]);
LABEL_23:
  v7->Next = (struct _SLIST_ENTRY *)v5;
  return v7 + 1;
}

```

## disassembly

```asm
0x1400f34d8  push    rbx
0x1400f34da  push    rbp
0x1400f34db  push    rsi
0x1400f34dc  push    rdi
0x1400f34dd  sub     rsp, 28h
0x1400f34e1  mov     ebp, edx
0x1400f34e3  mov     rsi, rcx
0x1400f34e6  test    r8b, 2
0x1400f34ea  jnz     loc_1400F35CB
0x1400f34f0  lea     rbx, ?LookasideLists@@3PAPEAU_SmsLookaside@@A; _SmsLookaside * near * LookasideLists
0x1400f34f7  mov     rbx, [rbx+rbp*8]
0x1400f34fb  mov     eax, [rbx]
0x1400f34fd  cmp     rcx, rax
0x1400f3500  ja      loc_1400F35CB
0x1400f3506  cmp     byte ptr [rbx+8], 0
0x1400f350a  jz      short loc_1400F3533
0x1400f350c  mov     r8d, [rbx+20h]
0x1400f3510  mov     rdx, [rbx+18h]
0x1400f3514  call    ?MsAllocatePoolWithTagImpl@@YAPEAXW4_MS_POOL_TYPE@@_KK@Z; MsAllocatePoolWithTagImpl(_MS_POOL_TYPE,unsigned __int64,ulong)
0x1400f3519  mov     rdi, rax
0x1400f351c  cmp     ebp, 1
0x1400f351f  jnz     loc_1400F35BC
0x1400f3525  lea     rcx, [rax+8]; void *
0x1400f3529  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x1400f352e  jmp     loc_1400F35BC
0x1400f3533  test    r8b, 1
0x1400f3537  jz      short loc_1400F3579
0x1400f3539  lea     rcx, [rbx+10h]; ListHead
0x1400f353d  call    cs:__imp_InterlockedPopEntrySList
0x1400f3544  nop     dword ptr [rax+rax+00h]
0x1400f3549  mov     rdi, rax
0x1400f354c  mov     rcx, [rbx+28h]
0x1400f3550  lea     eax, [rcx-1]
0x1400f3553  mov     dword ptr [rsp+48h+arg_18], eax
0x1400f3557  mov     rax, rcx
0x1400f355a  shr     rax, 20h
0x1400f355e  dec     eax
0x1400f3560  mov     dword ptr [rsp+48h+arg_18+4], eax
0x1400f3564  mov     rax, rcx
0x1400f3567  mov     rdx, [rsp+48h+arg_18]
0x1400f356c  lock cmpxchg [rbx+28h], rdx
0x1400f3572  cmp     rax, rcx
0x1400f3575  jnz     short loc_1400F354C
0x1400f3577  jmp     short loc_1400F35BC
0x1400f3579  mov     rax, [rbx+28h]
0x1400f357d  mov     rcx, rax
0x1400f3580  shr     rcx, 20h
0x1400f3584  cmp     eax, ecx
0x1400f3586  jle     short loc_1400F35C1
0x1400f3588  nop
0x1400f3589  or      ecx, 0FFFFFFFFh
0x1400f358c  lock xadd [rbx+28h], ecx
0x1400f3591  nop
0x1400f3592  dec     ecx
0x1400f3594  mov     eax, [rbx+2Ch]
0x1400f3597  cmp     ecx, eax
0x1400f3599  jl      short loc_1400F35B4
0x1400f359b  test    ecx, ecx
0x1400f359d  js      short loc_1400F35B4
0x1400f359f  lea     rcx, [rbx+10h]; ListHead
0x1400f35a3  call    cs:__imp_InterlockedPopEntrySList
0x1400f35aa  nop     dword ptr [rax+rax+00h]
0x1400f35af  mov     rdi, rax
0x1400f35b2  jmp     short loc_1400F35BC
0x1400f35b4  xor     edi, edi
0x1400f35b6  nop
0x1400f35b7  lock inc dword ptr [rbx+28h]
0x1400f35bb  nop
0x1400f35bc  test    rdi, rdi
0x1400f35bf  jnz     short loc_1400F35EE
0x1400f35c1  test    rbx, rbx
0x1400f35c4  jz      short loc_1400F35CD
0x1400f35c6  mov     esi, [rbx+4]
0x1400f35c9  jmp     short loc_1400F35D1
0x1400f35cb  xor     ebx, ebx
0x1400f35cd  add     rsi, 10h
0x1400f35d1  mov     rcx, rsi; unsigned __int64
0x1400f35d4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400f35d9  mov     rdi, rax
0x1400f35dc  test    al, 0Fh
0x1400f35de  jnz     short loc_1400F35FF
0x1400f35e0  cmp     ebp, 1
0x1400f35e3  jnz     short loc_1400F35EE
0x1400f35e5  lea     rcx, [rax+10h]; void *
0x1400f35e9  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x1400f35ee  mov     [rdi], rbx
0x1400f35f1  lea     rax, [rdi+10h]
0x1400f35f5  add     rsp, 28h
0x1400f35f9  pop     rdi
0x1400f35fa  pop     rsi
0x1400f35fb  pop     rbp
0x1400f35fc  pop     rbx
0x1400f35fd  retn
0x1400f35ff  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
