# COutputQueue::ThreadProc(void)

- ea: `0x1800338e0`
- end: `0x180033b01`
- name: `?ThreadProc@COutputQueue@@IEAAKXZ`
- size: `545`
- prototype: `unsigned int __fastcall(COutputQueue *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180033510`

## callees

- `0x180001048`
- `0x180006860`
- `0x180033434`
- `0x1800338e0`
- `0x180034010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800339db`
- `KERNEL32!WaitForSingleObject` at `0x1800339db`
- `KERNEL32!SetEvent` at `0x180033918`
- `KERNEL32!SetEvent` at `0x180033939`
- `KERNEL32!SetEvent` at `0x1800339ad`
- `KERNEL32!SetEvent` at `0x180033a9c`
- `KERNEL32!SetEvent` at `0x180033918`
- `KERNEL32!SetEvent` at `0x180033939`
- `KERNEL32!SetEvent` at `0x1800339ad`
- `KERNEL32!SetEvent` at `0x180033a9c`
- `KERNEL32!LeaveCriticalSection` at `0x1800339c9`
- `KERNEL32!LeaveCriticalSection` at `0x180033a36`
- `KERNEL32!LeaveCriticalSection` at `0x180033aec`
- `KERNEL32!LeaveCriticalSection` at `0x1800339c9`
- `KERNEL32!LeaveCriticalSection` at `0x180033a36`
- `KERNEL32!LeaveCriticalSection` at `0x180033aec`
- `KERNEL32!EnterCriticalSection` at `0x1800338f6`
- `KERNEL32!EnterCriticalSection` at `0x180033a1d`
- `KERNEL32!EnterCriticalSection` at `0x1800338f6`
- `KERNEL32!EnterCriticalSection` at `0x180033a1d`

## pseudocode

```c
__int64 __fastcall COutputQueue::ThreadProc(COutputQueue *this)
{
  _QWORD *v2; // r15
  __int64 v3; // rax
  void *v4; // rcx
  unsigned __int64 v5; // rsi
  unsigned int *v6; // rdi
  __int64 v7; // rax
  bool v8; // zf
  __int64 v9; // rax
  void *v10; // rcx
  unsigned int v11; // ebp
  int v12; // r14d
  int v13; // eax
  int v14; // edi
  __int64 v15; // rcx
  void *v16; // rcx
  int v18; // [rsp+70h] [rbp+8h] BYREF

LABEL_1:
  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  while ( !*((_DWORD *)this + 31) )
  {
    if ( *((_DWORD *)this + 28) )
    {
      COutputQueue::FreeSamples(this);
      SetEvent(*((HANDLE *)this + 10));
    }
    v3 = CBaseList::RemoveI(*((CBaseList **)this + 8), **((struct __POSITION ***)this + 8));
    v4 = (void *)*((_QWORD *)this + 17);
    v5 = v3;
    if ( v4 )
      SetEvent(v4);
    if ( v5 )
    {
      v6 = (unsigned int *)((char *)this + 104);
      if ( v5 > 0xFFFFFFFFFFFFFFF0uLL )
        goto LABEL_15;
      v7 = (int)*v6;
      v8 = (_DWORD)v7 == *((_DWORD *)this + 15);
      if ( (int)v7 < *((_DWORD *)this + 15) )
      {
        *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v7) = v5;
        v8 = ++*v6 == *((_DWORD *)this + 15);
      }
      if ( v8 )
        goto LABEL_21;
    }
    else
    {
      if ( *((_DWORD *)this + 14) || (v6 = (unsigned int *)((char *)this + 104), !*((_DWORD *)this + 26)) )
      {
        ++*((_DWORD *)this + 27);
        v11 = 0;
        v12 = 1;
        goto LABEL_23;
      }
LABEL_15:
      if ( v5 != -2 )
      {
        if ( v5 == -5 )
        {
          v9 = CBaseList::RemoveI(*((CBaseList **)this + 8), **((struct __POSITION ***)this + 8));
          v10 = (void *)*((_QWORD *)this + 17);
          v2 = (_QWORD *)v9;
          if ( v10 )
            SetEvent(v10);
        }
LABEL_21:
        v11 = *v6;
        v12 = 0;
        *v6 = 0;
LABEL_23:
        LeaveCriticalSection((LPCRITICAL_SECTION)this);
        if ( v12 )
        {
          WaitForSingleObject(*((HANDLE *)this + 9), 0xFFFFFFFF);
        }
        else
        {
          if ( v11 )
          {
            v13 = *((_DWORD *)this + 33);
            v18 = 0;
            if ( !v13 )
            {
              v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 6) + 56LL))(
                      *((_QWORD *)this + 6),
                      *((_QWORD *)this + 12),
                      v11,
                      &v18);
              EnterCriticalSection((LPCRITICAL_SECTION)this);
              if ( !*((_DWORD *)this + 33) )
                *((_DWORD *)this + 33) = v14;
              LeaveCriticalSection((LPCRITICAL_SECTION)this);
            }
            do
            {
              v15 = *(_QWORD *)(*((_QWORD *)this + 12) + 8LL * (int)--v11);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            }
            while ( v11 );
          }
          switch ( v5 )
          {
            case 0xFFFFFFFFFFFFFFFDuLL:
              if ( !*((_DWORD *)this + 33) )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 112LL))(*((_QWORD *)this + 5));
              break;
            case 0xFFFFFFFFFFFFFFFCuLL:
              v16 = (void *)*((_QWORD *)this + 10);
              *((_DWORD *)this + 33) = 0;
              SetEvent(v16);
              break;
            case 0xFFFFFFFFFFFFFFFBuLL:
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 5) + 136LL))(
                *((_QWORD *)this + 5),
                *v2,
                v2[1]);
              operator delete(v2);
              break;
          }
        }
        goto LABEL_1;
      }
      if ( *v6 )
        goto LABEL_21;
    }
  }
  COutputQueue::FreeSamples(this);
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  return 0;
}

```

## disassembly

```asm
0x1800338e0  push    rbx
0x1800338e2  push    rbp
0x1800338e3  push    rsi
0x1800338e4  push    rdi
0x1800338e5  push    r14
0x1800338e7  push    r15
0x1800338e9  sub     rsp, 38h
0x1800338ed  mov     rbx, rcx
0x1800338f0  xor     r15d, r15d
0x1800338f3  mov     rcx, rbx; lpCriticalSection
0x1800338f6  call    cs:__imp_EnterCriticalSection
0x1800338fc  cmp     [rbx+7Ch], r15d
0x180033900  jnz     loc_180033AE1
0x180033906  cmp     [rbx+70h], r15d
0x18003390a  jz      short loc_18003391E
0x18003390c  mov     rcx, rbx; this
0x18003390f  call    ?FreeSamples@COutputQueue@@IEAAXXZ; COutputQueue::FreeSamples(void)
0x180033914  mov     rcx, [rbx+50h]; hEvent
0x180033918  call    cs:__imp_SetEvent
0x18003391e  mov     rcx, [rbx+40h]; this
0x180033922  mov     rdx, [rcx]; struct __POSITION *
0x180033925  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18003392a  mov     rcx, [rbx+88h]; hEvent
0x180033931  mov     rsi, rax
0x180033934  test    rcx, rcx
0x180033937  jz      short loc_18003393F
0x180033939  call    cs:__imp_SetEvent
0x18003393f  test    rsi, rsi
0x180033942  jz      short loc_18003396C
0x180033944  lea     rdi, [rbx+68h]
0x180033948  cmp     rsi, 0FFFFFFFFFFFFFFF0h
0x18003394c  ja      short loc_18003397B
0x18003394e  movsxd  rax, dword ptr [rdi]
0x180033951  cmp     eax, [rbx+3Ch]
0x180033954  jge     short loc_180033968
0x180033956  mov     rcx, rax
0x180033959  mov     rax, [rbx+60h]
0x18003395d  mov     [rax+rcx*8], rsi
0x180033961  inc     dword ptr [rdi]
0x180033963  mov     eax, [rdi]
0x180033965  cmp     eax, [rbx+3Ch]
0x180033968  jnz     short loc_1800338FC
0x18003396a  jmp     short loc_1800339B3
0x18003396c  cmp     [rbx+38h], r15d
0x180033970  jnz     short loc_1800339BD
0x180033972  lea     rdi, [rbx+68h]
0x180033976  cmp     [rdi], r15d
0x180033979  jz      short loc_1800339BD
0x18003397b  cmp     rsi, 0FFFFFFFFFFFFFFFEh
0x18003397f  jnz     short loc_18003398C
0x180033981  cmp     [rdi], r15d
0x180033984  jz      loc_1800338FC
0x18003398a  jmp     short loc_1800339B3
0x18003398c  cmp     rsi, 0FFFFFFFFFFFFFFFBh
0x180033990  jnz     short loc_1800339B3
0x180033992  mov     rcx, [rbx+40h]; this
0x180033996  mov     rdx, [rcx]; struct __POSITION *
0x180033999  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18003399e  mov     rcx, [rbx+88h]; hEvent
0x1800339a5  mov     r15, rax
0x1800339a8  test    rcx, rcx
0x1800339ab  jz      short loc_1800339B3
0x1800339ad  call    cs:__imp_SetEvent
0x1800339b3  mov     ebp, [rdi]
0x1800339b5  xor     r14d, r14d
0x1800339b8  mov     [rdi], r14d
0x1800339bb  jmp     short loc_1800339C6
0x1800339bd  inc     dword ptr [rbx+6Ch]
0x1800339c0  xor     ebp, ebp
0x1800339c2  lea     r14d, [rbp+1]
0x1800339c6  mov     rcx, rbx; lpCriticalSection
0x1800339c9  call    cs:__imp_LeaveCriticalSection
0x1800339cf  test    r14d, r14d
0x1800339d2  jz      short loc_1800339E6
0x1800339d4  mov     rcx, [rbx+48h]; hHandle
0x1800339d8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800339db  call    cs:__imp_WaitForSingleObject
0x1800339e1  jmp     loc_1800338F0
0x1800339e6  test    ebp, ebp
0x1800339e8  jz      short loc_180033A5F
0x1800339ea  mov     eax, [rbx+84h]
0x1800339f0  mov     [rsp+68h+arg_0], 0
0x1800339f8  test    eax, eax
0x1800339fa  jnz     short loc_180033A3C
0x1800339fc  mov     rcx, [rbx+30h]
0x180033a00  lea     r9, [rsp+68h+arg_0]
0x180033a05  mov     rdx, [rbx+60h]
0x180033a09  mov     r8d, ebp
0x180033a0c  mov     rax, [rcx]
0x180033a0f  mov     rax, [rax+38h]
0x180033a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a18  mov     rcx, rbx; lpCriticalSection
0x180033a1b  mov     edi, eax
0x180033a1d  call    cs:__imp_EnterCriticalSection
0x180033a23  mov     ecx, [rbx+84h]
0x180033a29  test    ecx, ecx
0x180033a2b  jnz     short loc_180033A33
0x180033a2d  mov     [rbx+84h], edi
0x180033a33  mov     rcx, rbx; lpCriticalSection
0x180033a36  call    cs:__imp_LeaveCriticalSection
0x180033a3c  mov     rax, [rbx+60h]
0x180033a40  dec     ebp
0x180033a42  movsxd  rcx, ebp
0x180033a45  mov     rcx, [rax+rcx*8]
0x180033a49  mov     rax, [rcx]
0x180033a4c  mov     rax, [rax+10h]
0x180033a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a55  test    ebp, ebp
0x180033a57  jnz     short loc_180033A3C
0x180033a59  mov     eax, [rbx+84h]
0x180033a5f  cmp     rsi, 0FFFFFFFFFFFFFFFDh
0x180033a63  jnz     short loc_180033A88
0x180033a65  mov     eax, [rbx+84h]
0x180033a6b  test    eax, eax
0x180033a6d  jnz     loc_1800338F0
0x180033a73  mov     rcx, [rbx+28h]
0x180033a77  mov     rax, [rcx]
0x180033a7a  mov     rax, [rax+70h]
0x180033a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a83  jmp     loc_1800338F0
0x180033a88  cmp     rsi, 0FFFFFFFFFFFFFFFCh
0x180033a8c  jnz     short loc_180033AA7
0x180033a8e  mov     rcx, [rbx+50h]; hEvent
0x180033a92  mov     dword ptr [rbx+84h], 0
0x180033a9c  call    cs:__imp_SetEvent
0x180033aa2  jmp     loc_1800338F0
0x180033aa7  cmp     rsi, 0FFFFFFFFFFFFFFFBh
0x180033aab  jnz     loc_1800338F0
0x180033ab1  mov     rcx, [rbx+28h]
0x180033ab5  movsd   xmm3, qword ptr [r15+10h]
0x180033abb  mov     r8, [r15+8]
0x180033abf  mov     rdx, [r15]
0x180033ac2  mov     rax, [rcx]
0x180033ac5  mov     rax, [rax+88h]
0x180033acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ad1  lea     edx, [rsi+1Dh]; unsigned __int64
0x180033ad4  mov     rcx, r15; void *
0x180033ad7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180033adc  jmp     loc_1800338F0
0x180033ae1  mov     rcx, rbx; this
0x180033ae4  call    ?FreeSamples@COutputQueue@@IEAAXXZ; COutputQueue::FreeSamples(void)
0x180033ae9  mov     rcx, rbx; lpCriticalSection
0x180033aec  call    cs:__imp_LeaveCriticalSection
0x180033af2  xor     eax, eax
0x180033af4  add     rsp, 38h
0x180033af8  pop     r15
0x180033afa  pop     r14
0x180033afc  pop     rdi
0x180033afd  pop     rsi
0x180033afe  pop     rbp
0x180033aff  pop     rbx
0x180033b00  retn
```
