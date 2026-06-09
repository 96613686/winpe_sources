# CImpIRowsetUpdate::GetOriginalData(unsigned __int64,unsigned __int64,void *)

- ea: `0x180018060`
- end: `0x1800181f0`
- name: `?GetOriginalData@CImpIRowsetUpdate@@UEAAJ_K0PEAX@Z`
- size: `400`
- prototype: `int(CImpIRowsetUpdate *__hidden this, unsigned __int64, unsigned __int64, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180015fb4`
- `0x180018060`
- `0x180020998`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001809b`
- `KERNEL32!GetCurrentThreadId` at `0x18001809b`
- `KERNEL32!LeaveCriticalSection` at `0x1800181d7`
- `KERNEL32!LeaveCriticalSection` at `0x1800181d7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800180ba`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800180ba`
- `MSDART!UMSEnterCSWraper` at `0x180018088`
- `MSDART!UMSEnterCSWraper` at `0x180018088`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetUpdate::GetOriginalData(
        CImpIRowsetUpdate *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        char *a4)
{
  __int64 v8; // rbx
  DWORD *v9; // rsi
  __int64 v10; // r12
  int DataArgs; // eax
  unsigned int v12; // edi
  struct tagACCESSOR *v13; // rdi
  unsigned int v14; // r13d
  int v15; // ebp
  __int64 v16; // r9
  int v17; // ecx
  char *v18; // r10
  char *v19; // r8
  char *v20; // rdx
  int v21; // eax
  int v22; // ecx
  __int64 v24; // rcx
  int v26; // [rsp+20h] [rbp-88h]
  struct tagACCESSOR *v27; // [rsp+B0h] [rbp+8h] BYREF

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  v10 = 0;
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  v27 = 0;
  SetErrorInfo(0, 0);
  DataArgs = CRowset::ValidateGetDataArgs(*((CRowset **)this + 3), a2, a3, a4, &v27);
  if ( DataArgs >= 0 )
  {
    v13 = v27;
    v14 = *((_DWORD *)v27 + 2);
    v15 = 0;
    LODWORD(v27) = 0;
    if ( v14 )
    {
      do
      {
        v16 = 88 * v10;
        v17 = *((_DWORD *)v13 + 22 * v10 + 18);
        if ( (v17 & 1) != 0 )
          v18 = &a4[*(_QWORD *)((char *)v13 + v16 + 24)];
        else
          v18 = 0;
        if ( (v17 & 2) != 0 )
          v19 = &a4[*(_QWORD *)((char *)v13 + v16 + 32)];
        else
          v19 = 0;
        if ( (v17 & 4) != 0 )
          v20 = &a4[*(_QWORD *)((char *)v13 + v16 + 40)];
        else
          v20 = 0;
        LOBYTE(v26) = 1;
        v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, char *, char *, char *))(**((_QWORD **)this + 3) + 48LL))(
                *((_QWORD *)this + 3),
                *((unsigned int *)v13 + 22 * v10 + 4),
                *(_QWORD *)((char *)v13 + v16 + 88),
                *(unsigned __int16 *)((char *)v13 + v16 + 100),
                v26,
                v20,
                v19,
                v18);
        v22 = v15 + 1;
        if ( !v21 )
          v22 = v15;
        v15 = v22;
        LODWORD(v27) = (_DWORD)v27 + 1;
        ++v10;
      }
      while ( (unsigned int)v27 < v14 );
    }
    v12 = v15 != 0 ? 0x40EDA : 0;
  }
  else
  {
    v12 = Exit(DataArgs, 0);
  }
  --*(_DWORD *)(v8 + 16);
  if ( (*(_DWORD *)(v8 + 12))-- == 1 )
    *v9 = -1;
  v24 = *(_QWORD *)v8;
  --*(_DWORD *)(v24 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
  return v12;
}

```

## disassembly

```asm
0x180018060  push    rbx
0x180018062  push    rbp
0x180018063  push    rsi
0x180018064  push    rdi
0x180018065  push    r12
0x180018067  push    r13
0x180018069  push    r14
0x18001806b  push    r15
0x18001806d  sub     rsp, 68h
0x180018071  mov     r14, r9
0x180018074  mov     rdi, r8
0x180018077  mov     rbp, rdx
0x18001807a  mov     r15, rcx
0x18001807d  mov     rbx, [rcx+18h]
0x180018081  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180018085  mov     rcx, rbx
0x180018088  call    cs:__imp_UMSEnterCSWraper
0x18001808e  lea     rsi, [rbx+8]
0x180018092  xor     r12d, r12d
0x180018095  cmp     [rbx+0Ch], r12d
0x180018099  jnz     short loc_1800180A3
0x18001809b  call    cs:__imp_GetCurrentThreadId
0x1800180a1  mov     [rsi], eax
0x1800180a3  inc     dword ptr [rbx+0Ch]
0x1800180a6  inc     dword ptr [rbx+10h]
0x1800180a9  mov     [rsp+0A8h+var_50], rbx
0x1800180ae  mov     [rsp+0A8h+arg_0], r12
0x1800180b6  xor     edx, edx; perrinfo
0x1800180b8  xor     ecx, ecx; dwReserved
0x1800180ba  call    cs:__imp_SetErrorInfo
0x1800180c0  lea     rax, [rsp+0A8h+arg_0]
0x1800180c8  mov     [rsp+0A8h+var_88], rax; struct tagACCESSOR **
0x1800180cd  mov     r9, r14; void *
0x1800180d0  mov     r8, rdi; unsigned __int64
0x1800180d3  mov     rdx, rbp; unsigned __int64
0x1800180d6  mov     rcx, [r15+18h]; this
0x1800180da  call    ?ValidateGetDataArgs@CRowset@@QEAAJ_K0PEAXPEAPEAUtagACCESSOR@@@Z; CRowset::ValidateGetDataArgs(unsigned __int64,unsigned __int64,void *,tagACCESSOR * *)
0x1800180df  test    eax, eax
0x1800180e1  jns     short loc_1800180F3
0x1800180e3  xor     edx, edx; unsigned int
0x1800180e5  mov     ecx, eax; int
0x1800180e7  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800180ec  mov     edi, eax
0x1800180ee  jmp     loc_1800181C0
0x1800180f3  mov     rdi, [rsp+0A8h+arg_0]
0x1800180fb  mov     r13d, [rdi+8]
0x1800180ff  mov     ebp, r12d
0x180018102  mov     dword ptr [rsp+0A8h+arg_0], r12d
0x18001810a  test    r13d, r13d
0x18001810d  jz      loc_1800181B6
0x180018113  imul    r9, r12, 58h ; 'X'
0x180018117  mov     eax, [r9+rdi+10h]
0x18001811c  mov     [rsp+0A8h+var_58], eax
0x180018120  mov     ecx, [r9+rdi+48h]
0x180018125  test    cl, 1
0x180018128  jz      short loc_180018134
0x18001812a  mov     r10, [r9+rdi+18h]
0x18001812f  add     r10, r14
0x180018132  jmp     short loc_180018137
0x180018134  xor     r10d, r10d
0x180018137  test    cl, 2
0x18001813a  jz      short loc_180018146
0x18001813c  mov     r8, [r9+rdi+20h]
0x180018141  add     r8, r14
0x180018144  jmp     short loc_180018149
0x180018146  xor     r8d, r8d
0x180018149  mov     r11, [r9+rdi+58h]
0x18001814e  test    cl, 4
0x180018151  jz      short loc_18001815D
0x180018153  mov     rdx, [r9+rdi+28h]
0x180018158  add     rdx, r14
0x18001815b  jmp     short loc_18001815F
0x18001815d  xor     edx, edx
0x18001815f  mov     rcx, [r15+18h]
0x180018163  mov     rax, [rcx]
0x180018166  mov     [rsp+0A8h+var_70], r10
0x18001816b  mov     [rsp+0A8h+var_78], r8
0x180018170  mov     [rsp+0A8h+var_80], rdx
0x180018175  mov     byte ptr [rsp+0A8h+var_88], 1
0x18001817a  movzx   r9d, word ptr [r9+rdi+64h]
0x180018180  mov     r8, r11
0x180018183  mov     edx, [rsp+0A8h+var_58]
0x180018187  mov     rax, [rax+30h]
0x18001818b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018190  lea     ecx, [rbp+1]
0x180018193  test    eax, eax
0x180018195  cmovz   ecx, ebp
0x180018198  mov     ebp, ecx
0x18001819a  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x1800181a1  inc     eax
0x1800181a3  mov     dword ptr [rsp+0A8h+arg_0], eax
0x1800181aa  inc     r12
0x1800181ad  cmp     eax, r13d
0x1800181b0  jb      loc_180018113
0x1800181b6  neg     ebp
0x1800181b8  sbb     edi, edi
0x1800181ba  and     edi, 40EDAh
0x1800181c0  or      edx, 0FFFFFFFFh
0x1800181c3  add     [rbx+10h], edx
0x1800181c6  add     [rbx+0Ch], edx
0x1800181c9  jnz     short loc_1800181CD
0x1800181cb  mov     [rsi], edx
0x1800181cd  mov     rcx, [rbx]
0x1800181d0  dec     dword ptr [rcx+30h]
0x1800181d3  add     rcx, 8; lpCriticalSection
0x1800181d7  call    cs:__imp_LeaveCriticalSection
0x1800181dd  mov     eax, edi
0x1800181df  add     rsp, 68h
0x1800181e3  pop     r15
0x1800181e5  pop     r14
0x1800181e7  pop     r13
0x1800181e9  pop     r12
0x1800181eb  pop     rdi
0x1800181ec  pop     rsi
0x1800181ed  pop     rbp
0x1800181ee  pop     rbx
0x1800181ef  retn
```
