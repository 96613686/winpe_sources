# CBackgroundWorkItemInstanceRemote::ReportDispatch(long)

- ea: `0x18003ab70`
- end: `0x18003ad4a`
- name: `?ReportDispatch@CBackgroundWorkItemInstanceRemote@@UEAAJJ@Z`
- size: `474`
- prototype: `__int64 __fastcall(CBackgroundWorkItemInstanceRemote *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000db40`
- `0x18003ab70`
- `0x18003ad50`
- `0x18003b128`
- `0x18003fd6c`
- `0x180049844`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ab95`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ac1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ab95`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ac1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003abf1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ac4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003abf1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ac4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ab9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ac25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ab9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ac25`

## pseudocode

```c
__int64 __fastcall CBackgroundWorkItemInstanceRemote::ReportDispatch(RTL_SRWLOCK *this, int a2)
{
  RTL_SRWLOCK *v2; // r15
  PVOID v5; // r14
  struct IStream *v6; // rbp
  bool v7; // r13
  bool v8; // si
  CBackgroundWorkItemInstanceRemote *v9; // rcx
  int Ptr; // eax
  int v12; // r9d
  unsigned __int8 v13; // r8

  v2 = this + 20;
  v5 = 0;
  v6 = 0;
  AcquireSRWLockExclusive(this + 20);
  LODWORD(this[19].Ptr) = GetCurrentThreadId();
  v7 = !((__int64)this[22].Ptr & 1);
  v8 = ((__int64)this[22].Ptr & 0x20) != 0 || ((__int64)this[22].Ptr & 1) != 0 || a2 < 0;
  if ( a2 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_558b95e84a653da449c09ebb4bbf2f1e_Traceguids,
        (unsigned int)a2);
    Ptr = (int)this[22].Ptr;
    if ( (Ptr & 1) == 0 )
    {
      v5 = this[23].Ptr;
      this[23].Ptr = 0;
      v6 = (struct IStream *)this[21].Ptr;
      this[21].Ptr = 0;
      LODWORD(this[22].Ptr) = Ptr | 1;
      CBackgroundWorkItemInstanceRemote::DisarmProcessWaitCallback((CBackgroundWorkItemInstanceRemote *)this);
    }
  }
  LODWORD(this[19].Ptr) = 0;
  ReleaseSRWLockExclusive(v2);
  if ( v7 )
    BipActivationCompletionCallback((char *)&this[11].Ptr + 4);
  AcquireSRWLockExclusive(v2);
  GetCurrentThreadId();
  LODWORD(this[22].Ptr) |= 0x10u;
  if ( ((__int64)this[22].Ptr & 0x20) != 0 )
    v8 = 1;
  LODWORD(this[19].Ptr) = 0;
  ReleaseSRWLockExclusive(v2);
  if ( v5 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v6 )
    CBackgroundWorkItemInstanceRemote::CleanupStream(v9, v6);
  if ( v8 )
  {
    if ( a2 >= 0 )
    {
      v12 = (int)this[26].Ptr;
      v13 = ((__int64)this[22].Ptr & 0x40) != 0;
    }
    else
    {
      v12 = a2;
      v13 = 0;
    }
    BipTaskCompletionCallback((unsigned __int8 *)&this[11].Ptr + 4, (char *)&this[9].Ptr + 4, v13, v12);
  }
  return 0;
}

```

## disassembly

```asm
0x18003ab70  push    rbx
0x18003ab72  push    rbp
0x18003ab73  push    rsi
0x18003ab74  push    rdi
0x18003ab75  push    r12
0x18003ab77  push    r13
0x18003ab79  push    r14
0x18003ab7b  push    r15
0x18003ab7d  sub     rsp, 28h
0x18003ab81  lea     r15, [rcx+0A0h]
0x18003ab88  mov     rbx, rcx
0x18003ab8b  mov     rcx, r15; SRWLock
0x18003ab8e  mov     edi, edx
0x18003ab90  xor     r14d, r14d
0x18003ab93  xor     ebp, ebp
0x18003ab95  call    cs:__imp_AcquireSRWLockExclusive
0x18003ab9b  call    cs:__imp_GetCurrentThreadId
0x18003aba1  lea     edx, [rbp+1]
0x18003aba4  mov     [rbx+98h], eax
0x18003abaa  mov     eax, [rbx+0B0h]
0x18003abb0  mov     ecx, eax
0x18003abb2  and     ecx, edx
0x18003abb4  mov     r13b, cl
0x18003abb7  xor     r13b, dl
0x18003abba  test    al, 20h
0x18003abbc  jnz     loc_18003AC7E
0x18003abc2  test    ecx, ecx
0x18003abc4  jnz     loc_18003AC7E
0x18003abca  test    edi, edi
0x18003abcc  js      loc_18003AC7E
0x18003abd2  xor     sil, sil
0x18003abd5  mov     r12d, [rbx+0C8h]
0x18003abdc  test    edi, edi
0x18003abde  js      loc_18003AC90
0x18003abe4  mov     rcx, r15; SRWLock
0x18003abe7  mov     dword ptr [rbx+98h], 0
0x18003abf1  call    cs:__imp_ReleaseSRWLockExclusive
0x18003abf7  test    r13b, r13b
0x18003abfa  mov     r13d, 1
0x18003ac00  jz      short loc_18003AC1C
0x18003ac02  mov     r9d, edi
0x18003ac05  lea     rdx, [rbx+4Ch]
0x18003ac09  shr     r9d, 1Fh
0x18003ac0d  lea     rcx, [rbx+5Ch]; Source1
0x18003ac11  xor     r9b, r13b
0x18003ac14  mov     r8d, r12d
0x18003ac17  call    BipActivationCompletionCallback
0x18003ac1c  mov     rcx, r15; SRWLock
0x18003ac1f  call    cs:__imp_AcquireSRWLockExclusive
0x18003ac25  call    cs:__imp_GetCurrentThreadId
0x18003ac2b  or      dword ptr [rbx+0B0h], 10h
0x18003ac32  mov     rcx, r15; SRWLock
0x18003ac35  test    byte ptr [rbx+0B0h], 20h
0x18003ac3c  movzx   esi, sil
0x18003ac40  cmovnz  esi, r13d
0x18003ac44  mov     dword ptr [rbx+98h], 0
0x18003ac4e  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ac54  test    r14, r14
0x18003ac57  jnz     loc_18003AD03
0x18003ac5d  test    rbp, rbp
0x18003ac60  jnz     short loc_18003AC86
0x18003ac62  test    sil, sil
0x18003ac65  jnz     loc_18003AD17
0x18003ac6b  xor     eax, eax
0x18003ac6d  add     rsp, 28h
0x18003ac71  pop     r15
0x18003ac73  pop     r14
0x18003ac75  pop     r13
0x18003ac77  pop     r12
0x18003ac79  pop     rdi
0x18003ac7a  pop     rsi
0x18003ac7b  pop     rbp
0x18003ac7c  pop     rbx
0x18003ac7d  retn
0x18003ac7e  mov     sil, dl
0x18003ac81  jmp     loc_18003ABD5
0x18003ac86  mov     rdx, rbp; struct IStream *
0x18003ac89  call    ?CleanupStream@CBackgroundWorkItemInstanceRemote@@AEAAJPEAUIStream@@@Z; CBackgroundWorkItemInstanceRemote::CleanupStream(IStream *)
0x18003ac8e  jmp     short loc_18003AC62
0x18003ac90  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac97  test    byte ptr [rcx+1Ch], 2
0x18003ac9b  jz      short loc_18003ACC0
0x18003ac9d  cmp     byte ptr [rcx+19h], 2
0x18003aca1  jb      short loc_18003ACC0
0x18003aca3  mov     rcx, [rcx+10h]
0x18003aca7  lea     r8, WPP_558b95e84a653da449c09ebb4bbf2f1e_Traceguids
0x18003acae  mov     edx, 0Ch
0x18003acb3  mov     r9d, edi
0x18003acb6  call    WPP_SF_d
0x18003acbb  mov     edx, 1
0x18003acc0  mov     eax, [rbx+0B0h]
0x18003acc6  test    dl, al
0x18003acc8  jnz     loc_18003ABE4
0x18003acce  mov     r14, [rbx+0B8h]
0x18003acd5  or      eax, edx
0x18003acd7  mov     [rbx+0B8h], rbp
0x18003acde  mov     rcx, rbx; this
0x18003ace1  mov     rbp, [rbx+0A8h]
0x18003ace8  mov     qword ptr [rbx+0A8h], 0
0x18003acf3  mov     [rbx+0B0h], eax
0x18003acf9  call    ?DisarmProcessWaitCallback@CBackgroundWorkItemInstanceRemote@@AEAAXXZ; CBackgroundWorkItemInstanceRemote::DisarmProcessWaitCallback(void)
0x18003acfe  jmp     loc_18003ABE4
0x18003ad03  mov     rax, [r14]
0x18003ad06  mov     rcx, r14
0x18003ad09  mov     rax, [rax+10h]
0x18003ad0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad12  jmp     loc_18003AC5D
0x18003ad17  lea     rdx, [rbx+4Ch]; Source2
0x18003ad1b  lea     rcx, [rbx+5Ch]; Source1
0x18003ad1f  test    edi, edi
0x18003ad21  jns     short loc_18003AD2B
0x18003ad23  mov     r9d, edi
0x18003ad26  xor     r8d, r8d
0x18003ad29  jmp     short loc_18003AD40
0x18003ad2b  mov     r8d, [rbx+0B0h]
0x18003ad32  mov     r9d, [rbx+0D0h]
0x18003ad39  shr     r8d, 6
0x18003ad3d  and     r8b, r13b
0x18003ad40  call    BipTaskCompletionCallback
0x18003ad45  jmp     loc_18003AC6B
```
