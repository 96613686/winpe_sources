# COutputQueue::COutputQueue(IPin *,long *,int,int,long,int,long,ulong,bool)

- ea: `0x180032fbc`
- end: `0x180033187`
- name: `??0COutputQueue@@QEAA@PEAUIPin@@PEAJHHJHJK_N@Z`
- size: `459`
- prototype: `COutputQueue *__usercall@<rax>(COutputQueue *__hidden this@<rcx>, struct IPin *@<rdx>, int *@<r8>, int@<r9d>, int, int, int, int, unsigned int, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000bda0`
- `0x180022510`

## callees

- `0x180001008`
- `0x180001054`
- `0x180006f44`
- `0x180032fbc`
- `0x180034010`

## import_xrefs

- `KERNEL32!CreateSemaphoreW` at `0x1800330d9`
- `KERNEL32!CreateSemaphoreW` at `0x1800330d9`
- `KERNEL32!GetLastError` at `0x1800330e8`
- `KERNEL32!GetLastError` at `0x1800330e8`
- `KERNEL32!SetThreadPriority` at `0x180033163`
- `KERNEL32!SetThreadPriority` at `0x180033163`
- `KERNEL32!CreateThread` at `0x18003314f`
- `KERNEL32!CreateThread` at `0x18003314f`
- `KERNEL32!InitializeCriticalSection` at `0x180032fd7`
- `KERNEL32!InitializeCriticalSection` at `0x180032fd7`

## pseudocode

```c
COutputQueue *__fastcall COutputQueue::COutputQueue(
        COutputQueue *this,
        struct IPin *a2,
        int *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        unsigned int a9,
        DWORD ThreadId)
{
  BOOL v14; // edi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  void *v18; // rax
  HANDLE SemaphoreW; // rax
  _DWORD *v20; // rax
  HANDLE v21; // rax

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 6) = 0;
  v14 = 1;
  if ( !a7 || (v15 = 1, a6 <= 1) )
    v15 = 0;
  *((_DWORD *)this + 15) = a6;
  *((_DWORD *)this + 14) = v15;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  CAMEvent::CAMEvent((COutputQueue *)((char *)this + 80), 0, a3);
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 29) = 1;
  *((_BYTE *)this + 120) = 0;
  *(_QWORD *)((char *)this + 124) = 0;
  *((_DWORD *)this + 33) = 0;
  *((_QWORD *)this + 17) = 0;
  if ( *a3 >= 0 )
  {
    v16 = ((__int64 (__fastcall *)(struct IPin *, GUID *, char *))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IMemInputPin,
            (char *)this + 48);
    *a3 = v16;
    if ( v16 >= 0 )
    {
      if ( a4 )
      {
        v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
        if ( v17 >= 0 )
          v14 = v17 == 0;
      }
      v18 = operator new[](saturated_mul(*((int *)this + 15), 8u));
      *((_QWORD *)this + 12) = v18;
      if ( !v18 )
        goto LABEL_17;
      if ( v14 )
      {
        SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
        *((_QWORD *)this + 9) = SemaphoreW;
        if ( !SemaphoreW )
        {
LABEL_12:
          *a3 = GetLastError() | 0x80070000;
          return this;
        }
        v20 = operator new(0x28u);
        if ( v20 )
        {
          v20[6] = a8;
          *(_QWORD *)v20 = 0;
          *((_QWORD *)v20 + 1) = 0;
          v20[4] = 0;
          v20[7] = 0;
          *((_QWORD *)v20 + 4) = 0;
          *((_QWORD *)this + 8) = v20;
          ThreadId = 0;
          v21 = CreateThread(0, 0, COutputQueue::InitialThreadProc, this, 0, &ThreadId);
          *((_QWORD *)this + 11) = v21;
          if ( v21 )
          {
            SetThreadPriority(v21, 0);
            return this;
          }
          goto LABEL_12;
        }
        *((_QWORD *)this + 8) = 0;
LABEL_17:
        *a3 = -2147024882;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180032fbc  push    rbx
0x180032fbe  push    rbp
0x180032fbf  push    rsi
0x180032fc0  push    rdi
0x180032fc1  push    r12
0x180032fc3  push    r14
0x180032fc5  push    r15
0x180032fc7  sub     rsp, 30h
0x180032fcb  mov     ebp, r9d
0x180032fce  mov     rsi, r8
0x180032fd1  mov     r15, rdx
0x180032fd4  mov     rbx, rcx
0x180032fd7  call    cs:__imp_InitializeCriticalSection
0x180032fdd  mov     ecx, [rsp+68h+arg_28]
0x180032fe4  lea     r14, [rbx+30h]
0x180032fe8  xor     r12d, r12d
0x180032feb  mov     [rbx+28h], r15
0x180032fef  mov     [r14], r12
0x180032ff2  lea     edi, [r12+1]
0x180032ff7  cmp     [rsp+68h+arg_30], r12d
0x180032fff  jz      short loc_180033007
0x180033001  mov     eax, edi
0x180033003  cmp     ecx, edi
0x180033005  jg      short loc_18003300A
0x180033007  mov     eax, r12d
0x18003300a  mov     [rbx+3Ch], ecx
0x18003300d  mov     r8, rsi; int *
0x180033010  lea     rcx, [rbx+50h]; this
0x180033014  mov     [rbx+38h], eax
0x180033017  xor     edx, edx; int
0x180033019  mov     [rbx+40h], r12
0x18003301d  mov     [rbx+48h], r12
0x180033021  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x180033026  mov     [rbx+58h], r12
0x18003302a  mov     [rbx+60h], r12
0x18003302e  mov     [rbx+68h], r12
0x180033032  mov     [rbx+70h], r12d
0x180033036  mov     [rbx+74h], edi
0x180033039  mov     [rbx+78h], r12b
0x18003303d  mov     [rbx+7Ch], r12
0x180033041  mov     [rbx+84h], r12d
0x180033048  mov     [rbx+88h], r12
0x18003304f  cmp     [rsi], r12d
0x180033052  jl      loc_180033175
0x180033058  mov     rax, [r15]
0x18003305b  lea     rdx, IID_IMemInputPin
0x180033062  mov     r8, r14
0x180033065  mov     rcx, r15
0x180033068  mov     rax, [rax]
0x18003306b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033070  mov     [rsi], eax
0x180033072  test    eax, eax
0x180033074  js      loc_180033175
0x18003307a  test    ebp, ebp
0x18003307c  jz      short loc_180033098
0x18003307e  mov     rcx, [r14]
0x180033081  mov     rax, [rcx]
0x180033084  mov     rax, [rax+40h]
0x180033088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003308d  test    eax, eax
0x18003308f  js      short loc_180033098
0x180033091  mov     edi, r12d
0x180033094  setz    dil
0x180033098  movsxd  rcx, dword ptr [rbx+3Ch]
0x18003309c  mov     eax, 8
0x1800330a1  mul     rcx
0x1800330a4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800330ab  cmovb   rax, rcx
0x1800330af  mov     rcx, rax; unsigned __int64
0x1800330b2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800330b7  mov     [rbx+60h], rax
0x1800330bb  test    rax, rax
0x1800330be  jz      loc_18003316F
0x1800330c4  test    edi, edi
0x1800330c6  jz      loc_180033175
0x1800330cc  xor     r9d, r9d; lpName
0x1800330cf  xor     edx, edx; lInitialCount
0x1800330d1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800330d3  mov     r8d, 7FFFFFFFh; lMaximumCount
0x1800330d9  call    cs:__imp_CreateSemaphoreW
0x1800330df  mov     [rbx+48h], rax
0x1800330e3  test    rax, rax
0x1800330e6  jnz     short loc_1800330F7
0x1800330e8  call    cs:__imp_GetLastError
0x1800330ee  or      eax, 80070000h
0x1800330f3  mov     [rsi], eax
0x1800330f5  jmp     short loc_180033175
0x1800330f7  mov     ecx, 28h ; '('; Size
0x1800330fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033101  test    rax, rax
0x180033104  jz      short loc_18003316B
0x180033106  mov     ecx, [rsp+68h+arg_38]
0x18003310d  lea     r8, ?InitialThreadProc@COutputQueue@@KAKPEAX@Z; lpStartAddress
0x180033114  mov     [rax+18h], ecx
0x180033117  mov     r9, rbx; lpParameter
0x18003311a  mov     [rax], r12
0x18003311d  xor     edx, edx; dwStackSize
0x18003311f  mov     [rax+8], r12
0x180033123  xor     ecx, ecx; lpThreadAttributes
0x180033125  mov     [rax+10h], r12d
0x180033129  mov     [rax+1Ch], r12d
0x18003312d  mov     [rax+20h], r12
0x180033131  mov     [rbx+40h], rax
0x180033135  lea     rax, [rsp+68h+ThreadId]
0x18003313d  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180033142  mov     [rsp+68h+dwCreationFlags], r12d; dwCreationFlags
0x180033147  mov     [rsp+68h+ThreadId], r12d
0x18003314f  call    cs:__imp_CreateThread
0x180033155  mov     [rbx+58h], rax
0x180033159  test    rax, rax
0x18003315c  jz      short loc_1800330E8
0x18003315e  xor     edx, edx; nPriority
0x180033160  mov     rcx, rax; hThread
0x180033163  call    cs:__imp_SetThreadPriority
0x180033169  jmp     short loc_180033175
0x18003316b  mov     [rbx+40h], r12
0x18003316f  mov     dword ptr [rsi], 8007000Eh
0x180033175  mov     rax, rbx
0x180033178  add     rsp, 30h
0x18003317c  pop     r15
0x18003317e  pop     r14
0x180033180  pop     r12
0x180033182  pop     rdi
0x180033183  pop     rsi
0x180033184  pop     rbp
0x180033185  pop     rbx
0x180033186  retn
```
