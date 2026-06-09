# CTabsArray::Cache(long const *,long)

- ea: `0x1800455e0`
- end: `0x180045700`
- name: `?Cache@CTabsArray@@QEAAJPEBJJ@Z`
- size: `288`
- prototype: `__int64 __fastcall(CTabsArray *__hidden this, void *Src, int)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180045358`
- `0x1800512f8`
- `0x180084998`
- `0x180085a40`
- `0x180089d70`

## callees

- `0x180022780`
- `0x180027f70`
- `0x1800455e0`
- `0x1800471b4`
- `0x1800910e6`
- `0x1800910fe`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180045606`
- `KERNEL32!EnterCriticalSection` at `0x180045606`
- `KERNEL32!LeaveCriticalSection` at `0x1800456d9`
- `KERNEL32!LeaveCriticalSection` at `0x1800456ea`
- `KERNEL32!LeaveCriticalSection` at `0x1800456d9`
- `KERNEL32!LeaveCriticalSection` at `0x1800456ea`

## pseudocode

```c
__int64 __fastcall CTabsArray::Cache(CTabsArray *this, void *Src, int a3)
{
  __int64 v3; // rbp
  int i; // ebx
  const void **v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // esi
  _QWORD *v11; // r14
  void *v12; // rax

  v3 = a3;
  if ( a3 > 0 )
  {
    EnterCriticalSection(&g_CriticalSection);
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_DWORD *)this + 2) )
        goto LABEL_10;
      if ( *(int *)(*((_DWORD *)this + 4) * (i + 1) + *(_QWORD *)this - 4LL) > 0 )
      {
        v7 = (const void **)CArrayBase::Elem(this, i);
        if ( *(_DWORD *)v7 == (_DWORD)v3 && !memcmp_0(v7[1], Src, 4 * v3) )
          break;
      }
    }
    if ( i >= 0 )
    {
      v8 = *((_DWORD *)this + 4) * (i + 1);
      ++*(_DWORD *)(v8 + *(_QWORD *)this - 4);
LABEL_16:
      LeaveCriticalSection(&g_CriticalSection);
      return (unsigned int)i;
    }
LABEL_10:
    v9 = CFixArrayBase::Add(this);
    i = v9;
    if ( v9 >= 0 )
    {
      v10 = 4 * v3;
      v11 = CArrayBase::Elem(this, v9);
      if ( (unsigned int)(4 * v3) >= 4 && v10 >= (unsigned int)v3 && v10 <= 0x7FFFFFFF )
      {
        v12 = CW32System::PvAlloc(v10, 0);
        v11[1] = v12;
        if ( v12 )
        {
          memmove_0(v12, Src, (int)v10);
          *(_DWORD *)v11 = v3;
          *(_DWORD *)(*((_DWORD *)this + 4) * (i + 1) + *(_QWORD *)this - 4LL) = 1;
          goto LABEL_16;
        }
      }
    }
    LeaveCriticalSection(&g_CriticalSection);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800455e0  push    rbx
0x1800455e2  push    rbp
0x1800455e3  push    rsi
0x1800455e4  push    rdi
0x1800455e5  push    r14
0x1800455e7  push    r15
0x1800455e9  sub     rsp, 28h
0x1800455ed  movsxd  rbp, r8d
0x1800455f0  mov     r15, rdx
0x1800455f3  mov     rdi, rcx
0x1800455f6  test    r8d, r8d
0x1800455f9  jle     loc_1800456F0
0x1800455ff  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045606  call    cs:__imp_EnterCriticalSection
0x18004560c  xor     ebx, ebx
0x18004560e  cmp     ebx, [rdi+8]
0x180045611  jge     short loc_180045667
0x180045613  lea     eax, [rbx+1]
0x180045616  imul    eax, [rdi+10h]
0x18004561a  movsxd  rcx, eax
0x18004561d  mov     rax, [rdi]
0x180045620  cmp     dword ptr [rcx+rax-4], 0
0x180045625  jle     short loc_18004564C
0x180045627  mov     edx, ebx; int
0x180045629  mov     rcx, rdi; this
0x18004562c  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x180045631  cmp     [rax], ebp
0x180045633  jnz     short loc_18004564C
0x180045635  mov     rcx, [rax+8]; Buf1
0x180045639  mov     r8, rbp
0x18004563c  shl     r8, 2; Size
0x180045640  mov     rdx, r15; Buf2
0x180045643  call    memcmp_0
0x180045648  test    eax, eax
0x18004564a  jz      short loc_180045650
0x18004564c  inc     ebx
0x18004564e  jmp     short loc_18004560E
0x180045650  test    ebx, ebx
0x180045652  js      short loc_180045667
0x180045654  lea     eax, [rbx+1]
0x180045657  imul    eax, [rdi+10h]
0x18004565b  movsxd  rcx, eax
0x18004565e  mov     rax, [rdi]
0x180045661  inc     dword ptr [rcx+rax-4]
0x180045665  jmp     short loc_1800456D2
0x180045667  mov     rcx, rdi; this
0x18004566a  call    ?Add@CFixArrayBase@@QEAAJXZ; CFixArrayBase::Add(void)
0x18004566f  mov     ebx, eax
0x180045671  test    eax, eax
0x180045673  js      short loc_1800456E3
0x180045675  mov     edx, eax; int
0x180045677  mov     rcx, rdi; this
0x18004567a  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18004567f  lea     esi, ds:0[rbp*4]
0x180045686  mov     r14, rax
0x180045689  cmp     esi, 4
0x18004568c  jb      short loc_1800456E3
0x18004568e  cmp     esi, ebp
0x180045690  jb      short loc_1800456E3
0x180045692  cmp     esi, 7FFFFFFFh
0x180045698  ja      short loc_1800456E3
0x18004569a  xor     edx, edx; unsigned int
0x18004569c  mov     ecx, esi; unsigned int
0x18004569e  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x1800456a3  mov     [r14+8], rax
0x1800456a7  test    rax, rax
0x1800456aa  jz      short loc_1800456E3
0x1800456ac  movsxd  r8, esi; Size
0x1800456af  mov     rdx, r15; Src
0x1800456b2  mov     rcx, rax; void *
0x1800456b5  call    memmove_0
0x1800456ba  mov     [r14], ebp
0x1800456bd  lea     eax, [rbx+1]
0x1800456c0  imul    eax, [rdi+10h]
0x1800456c4  movsxd  rdx, eax
0x1800456c7  mov     rax, [rdi]
0x1800456ca  mov     dword ptr [rdx+rax-4], 1
0x1800456d2  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800456d9  call    cs:__imp_LeaveCriticalSection
0x1800456df  mov     eax, ebx
0x1800456e1  jmp     short loc_1800456F3
0x1800456e3  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800456ea  call    cs:__imp_LeaveCriticalSection
0x1800456f0  or      eax, 0FFFFFFFFh
0x1800456f3  add     rsp, 28h
0x1800456f7  pop     r15
0x1800456f9  pop     r14
0x1800456fb  pop     rdi
0x1800456fc  pop     rsi
0x1800456fd  pop     rbp
0x1800456fe  pop     rbx
0x1800456ff  retn
```
