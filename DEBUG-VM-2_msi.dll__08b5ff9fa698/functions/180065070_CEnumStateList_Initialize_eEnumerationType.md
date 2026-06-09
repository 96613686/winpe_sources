# CEnumStateList::Initialize(eEnumerationType)

- ea: `0x180065070`
- end: `0x18006522a`
- name: `?Initialize@CEnumStateList@@QEAAIW4eEnumerationType@@@Z`
- size: `442`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18006431c`
- `0x180212034`
- `0x180212448`

## callees

- `0x18005f300`
- `0x180061334`
- `0x180065070`
- `0x180211d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800650d1`
- `KERNEL32!LeaveCriticalSection` at `0x180065134`
- `KERNEL32!LeaveCriticalSection` at `0x1800650d1`
- `KERNEL32!LeaveCriticalSection` at `0x180065134`
- `KERNEL32!GetCurrentThreadId` at `0x180065092`
- `KERNEL32!GetCurrentThreadId` at `0x18006511b`
- `KERNEL32!GetCurrentThreadId` at `0x180065092`
- `KERNEL32!GetCurrentThreadId` at `0x18006511b`
- `KERNEL32!EnterCriticalSection` at `0x18006508c`
- `KERNEL32!EnterCriticalSection` at `0x18006509d`
- `KERNEL32!EnterCriticalSection` at `0x18006508c`
- `KERNEL32!EnterCriticalSection` at `0x18006509d`
- `KERNEL32!GlobalAlloc` at `0x180065197`
- `KERNEL32!GlobalAlloc` at `0x180065197`
- `KERNEL32!GlobalFree` at `0x18006516b`
- `KERNEL32!GlobalFree` at `0x18006516b`

## pseudocode

```c
__int64 __fastcall CEnumStateList::Initialize(__int64 a1, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  unsigned int v5; // edi
  DWORD CurrentThreadId; // esi
  __int64 i; // r8
  __int64 v8; // rdx
  int v9; // esi
  __int64 v10; // rdi
  __int64 j; // rdx
  __int64 v12; // r8
  _QWORD *v13; // rax
  __int64 v14; // rbx
  DWORD v15; // eax
  unsigned int v17; // edx
  unsigned int v18; // ebp
  _QWORD *v19; // rsi
  int v20; // r8d
  __int64 v21; // rcx
  CClientEnumState *v22; // rax
  CClientEnumState *v23; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 32);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(v2);
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 24); i = (unsigned int)(i + 1) )
  {
    v8 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
    if ( v8 && *(_DWORD *)(v8 + 1776) == CurrentThreadId )
    {
      v9 = 0;
      goto LABEL_6;
    }
  }
  v9 = 259;
LABEL_6:
  LeaveCriticalSection(v2);
  if ( v9 )
  {
    v10 = *(unsigned int *)(a1 + 24);
    if ( (_DWORD)v10 == *(_DWORD *)(a1 + 8) )
    {
      for ( j = 0; (unsigned int)j < (unsigned int)v10; j = (unsigned int)(j + 1) )
      {
        v12 = *(_QWORD *)(*(_QWORD *)a1 + 8 * j);
        if ( !v12 || !*(_DWORD *)(v12 + 1776) )
        {
          v10 = (unsigned int)j;
          goto LABEL_13;
        }
      }
      v18 = v10 + 10;
      if ( (int)v10 + 10 <= 1 )
        v19 = (_QWORD *)(a1 + 16);
      else
        v19 = GlobalAlloc(0x40u, 8LL * (int)v18);
      if ( !v19 )
        goto LABEL_33;
      if ( *(_QWORD **)a1 != v19 )
      {
        v20 = v10 + 10;
        if ( (signed int)v18 >= *(_DWORD *)(a1 + 8) )
          v20 = *(_DWORD *)(a1 + 8);
        for ( ; v20; v19[v20] = *(_QWORD *)(*(_QWORD *)a1 + 8LL * v20) )
          --v20;
      }
      if ( *(_QWORD *)a1 != a1 + 16 )
        GlobalFree(*(HGLOBAL *)a1);
      *(_QWORD *)a1 = v19;
      *(_DWORD *)(a1 + 8) = v18;
      v17 = *(_DWORD *)(a1 + 24);
      if ( v17 < v18 )
      {
        do
        {
          v21 = v17++;
          *(_QWORD *)(*(_QWORD *)a1 + 8 * v21) = 0;
        }
        while ( v17 < *(_DWORD *)(a1 + 8) );
      }
    }
    ++*(_DWORD *)(a1 + 24);
LABEL_13:
    v13 = *(_QWORD **)a1;
    if ( *(_QWORD *)(*(_QWORD *)a1 + 8 * v10)
      || ((v22 = (CClientEnumState *)operator new(0x710u)) == 0
        ? (v23 = 0)
        : (v23 = CClientEnumState::CClientEnumState(v22)),
          *(_QWORD *)(*(_QWORD *)a1 + 8 * v10) = v23,
          v13 = *(_QWORD **)a1,
          *(_QWORD *)(*(_QWORD *)a1 + 8 * v10)) )
    {
      v14 = v13[v10];
      v15 = GetCurrentThreadId();
      v5 = CClientEnumState::Initialize(v14, a2, v15);
      goto LABEL_15;
    }
LABEL_33:
    v5 = 14;
  }
LABEL_15:
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x180065070  push    rbx
0x180065072  push    rbp
0x180065073  push    rsi
0x180065074  push    rdi
0x180065075  push    r14
0x180065077  push    r15
0x180065079  sub     rsp, 28h
0x18006507d  lea     r14, [rcx+20h]
0x180065081  mov     rbx, rcx
0x180065084  mov     rcx, r14; lpCriticalSection
0x180065087  mov     r15d, edx
0x18006508a  xor     edi, edi
0x18006508c  call    cs:__imp_EnterCriticalSection
0x180065092  call    cs:__imp_GetCurrentThreadId
0x180065098  mov     rcx, r14; lpCriticalSection
0x18006509b  mov     esi, eax
0x18006509d  call    cs:__imp_EnterCriticalSection
0x1800650a3  xor     r8d, r8d
0x1800650a6  cmp     r8d, [rbx+18h]
0x1800650aa  jnb     loc_180065149
0x1800650b0  mov     rax, [rbx]
0x1800650b3  mov     rdx, [rax+r8*8]
0x1800650b7  test    rdx, rdx
0x1800650ba  jz      loc_180065153
0x1800650c0  cmp     [rdx+6F0h], esi
0x1800650c6  jnz     loc_180065153
0x1800650cc  xor     esi, esi
0x1800650ce  mov     rcx, r14; lpCriticalSection
0x1800650d1  call    cs:__imp_LeaveCriticalSection
0x1800650d7  test    esi, esi
0x1800650d9  jz      short loc_180065131
0x1800650db  mov     edi, [rbx+18h]
0x1800650de  cmp     edi, [rbx+8]
0x1800650e1  jnz     loc_18006517E
0x1800650e7  xor     edx, edx
0x1800650e9  cmp     edx, edi
0x1800650eb  jnb     loc_180065183
0x1800650f1  mov     rax, [rbx]
0x1800650f4  mov     r8, [rax+rdx*8]
0x1800650f8  test    r8, r8
0x1800650fb  jz      short loc_180065107
0x1800650fd  cmp     dword ptr [r8+6F0h], 0
0x180065105  jnz     short loc_18006515B
0x180065107  mov     edi, edx
0x180065109  mov     rax, [rbx]
0x18006510c  cmp     qword ptr [rax+rdi*8], 0
0x180065111  jz      loc_1800651F6
0x180065117  mov     rbx, [rax+rdi*8]
0x18006511b  call    cs:__imp_GetCurrentThreadId
0x180065121  mov     edx, r15d
0x180065124  mov     rcx, rbx
0x180065127  mov     r8d, eax
0x18006512a  call    ?Initialize@CClientEnumState@@QEAAIW4eEnumerationType@@K@Z; CClientEnumState::Initialize(eEnumerationType,ulong)
0x18006512f  mov     edi, eax
0x180065131  mov     rcx, r14; lpCriticalSection
0x180065134  call    cs:__imp_LeaveCriticalSection
0x18006513a  mov     eax, edi
0x18006513c  add     rsp, 28h
0x180065140  pop     r15
0x180065142  pop     r14
0x180065144  pop     rdi
0x180065145  pop     rsi
0x180065146  pop     rbp
0x180065147  pop     rbx
0x180065148  retn
0x180065149  mov     esi, 103h
0x18006514e  jmp     loc_1800650CE
0x180065153  inc     r8d
0x180065156  jmp     loc_1800650A6
0x18006515b  inc     edx
0x18006515d  jmp     short loc_1800650E9
0x18006515f  lea     rax, [rbx+10h]
0x180065163  cmp     [rbx], rax
0x180065166  jz      short loc_180065171
0x180065168  mov     rcx, [rbx]; hMem
0x18006516b  call    cs:__imp_GlobalFree
0x180065171  mov     [rbx], rsi
0x180065174  mov     [rbx+8], ebp
0x180065177  mov     edx, [rbx+18h]
0x18006517a  cmp     edx, ebp
0x18006517c  jb      short loc_1800651E0
0x18006517e  inc     dword ptr [rbx+18h]
0x180065181  jmp     short loc_180065109
0x180065183  lea     ebp, [rdi+0Ah]
0x180065186  cmp     ebp, 1
0x180065189  jle     short loc_1800651D0
0x18006518b  movsxd  rdx, ebp
0x18006518e  mov     ecx, 40h ; '@'; uFlags
0x180065193  shl     rdx, 3; dwBytes
0x180065197  call    cs:__imp_GlobalAlloc
0x18006519d  mov     rsi, rax
0x1800651a0  test    rsi, rsi
0x1800651a3  jz      short loc_1800651D6
0x1800651a5  cmp     [rbx], rsi
0x1800651a8  jz      short loc_18006515F
0x1800651aa  cmp     ebp, [rbx+8]
0x1800651ad  mov     r8d, ebp
0x1800651b0  cmovge  r8d, [rbx+8]
0x1800651b5  test    r8d, r8d
0x1800651b8  jz      short loc_18006515F
0x1800651ba  mov     rax, [rbx]
0x1800651bd  sub     r8d, 1
0x1800651c1  movsxd  rdx, r8d
0x1800651c4  mov     rcx, [rax+rdx*8]
0x1800651c8  mov     [rsi+rdx*8], rcx
0x1800651cc  jnz     short loc_1800651BA
0x1800651ce  jmp     short loc_18006515F
0x1800651d0  lea     rsi, [rbx+10h]
0x1800651d4  jmp     short loc_1800651A0
0x1800651d6  mov     edi, 0Eh
0x1800651db  jmp     loc_180065131
0x1800651e0  mov     rax, [rbx]
0x1800651e3  mov     ecx, edx
0x1800651e5  inc     edx
0x1800651e7  mov     qword ptr [rax+rcx*8], 0
0x1800651ef  cmp     edx, [rbx+8]
0x1800651f2  jb      short loc_1800651E0
0x1800651f4  jmp     short loc_18006517E
0x1800651f6  mov     ecx, 710h; unsigned __int64
0x1800651fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065200  test    rax, rax
0x180065203  jz      short loc_180065212
0x180065205  mov     rcx, rax; this
0x180065208  call    ??0CClientEnumState@@QEAA@XZ; CClientEnumState::CClientEnumState(void)
0x18006520d  mov     rcx, rax
0x180065210  jmp     short loc_180065214
0x180065212  xor     ecx, ecx
0x180065214  mov     rax, [rbx]
0x180065217  mov     [rax+rdi*8], rcx
0x18006521b  mov     rax, [rbx]
0x18006521e  cmp     qword ptr [rax+rdi*8], 0
0x180065223  jz      short loc_1800651D6
0x180065225  jmp     loc_180065117
```
