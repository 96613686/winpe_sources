# CQuery::Create(_BROKER *,_BROKERED_EVENT *,_DEV_OBJECT_TYPE,ulong,ulong,ushort const * *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,ushort const *,_GUID,CQuery * *)

- ea: `0x18000383c`
- end: `0x180003997`
- name: `?Create@CQuery@@SAJPEAU_BROKER@@PEAU_BROKERED_EVENT@@W4_DEV_OBJECT_TYPE@@KKPEAPEBGKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@PEBGU_GUID@@PEAPEAV1@@Z`
- size: `347`
- prototype: `__int64 __fastcall(void *, ULONG_PTR, unsigned int, unsigned int, unsigned int, __int64, int, __int64, int, __int64, int, __int64, __int64, _OWORD *, CQuery **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003f80`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x1800031f4`
- `0x180003454`
- `0x18000383c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800038e7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800038e7`

## pseudocode

```c
__int64 __fastcall CQuery::Create(
        void *a1,
        ULONG_PTR a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9,
        __int64 a10,
        int a11,
        __int64 a12,
        __int64 a13,
        _OWORD *a14,
        CQuery **a15)
{
  struct _RTL_CRITICAL_SECTION *v19; // rax
  CQuery *v20; // rbx
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  struct _RTL_CRITICAL_SECTION *v22; // rax
  int v23; // edi

  *a15 = 0;
  v19 = (struct _RTL_CRITICAL_SECTION *)operator new(0xD0u);
  v20 = (CQuery *)v19;
  if ( v19 )
  {
    v21 = v19 + 4;
    v19->LockSemaphore = 0;
    LODWORD(v19->SpinCount) = 0;
    v19[1].DebugInfo = 0;
    *(_OWORD *)&v19[1].LockCount = *a14;
    v19[1].LockSemaphore = 0;
    v19[1].SpinCount = 0;
    v19[2].DebugInfo = 0;
    v19[2].LockCount = 0;
    v19[2].OwningThread = 0;
    LODWORD(v19[2].LockSemaphore) = 0;
    v19[2].SpinCount = 0;
    LODWORD(v19[3].OwningThread) = 0;
    v19[3].LockSemaphore = a1;
    v19[3].SpinCount = a2;
    v19[5].DebugInfo = 0;
    v22 = v19 + 3;
    *(_QWORD *)&v22->LockCount = v22;
    v22->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v22;
    *(_OWORD *)v20 = 0;
    InitializeCriticalSection(v21);
    v23 = CQuery::CopyParameters(v20, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13);
    if ( v23 < 0 )
    {
      CQuery::~CQuery(v20);
      operator delete(v20);
    }
    else
    {
      *a15 = v20;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18000383c  push    rbx
0x18000383e  push    rbp
0x18000383f  push    rsi
0x180003840  push    rdi
0x180003841  push    r12
0x180003843  push    r14
0x180003845  push    r15
0x180003847  sub     rsp, 60h
0x18000384b  mov     rsi, [rsp+98h+arg_70]
0x180003853  mov     r15, rcx
0x180003856  xor     r12d, r12d
0x180003859  mov     ecx, 0D0h; Size
0x18000385e  mov     edi, r9d
0x180003861  mov     ebp, r8d
0x180003864  mov     r14, rdx
0x180003867  mov     [rsi], r12
0x18000386a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000386f  mov     rbx, rax
0x180003872  test    rax, rax
0x180003875  jz      loc_180003981
0x18000387b  mov     rdx, [rsp+98h+arg_68]
0x180003883  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18000388a  mov     [rax+18h], r12
0x18000388e  mov     [rax+20h], r12d
0x180003892  mov     [rax+28h], r12
0x180003896  movaps  xmm0, xmmword ptr [rdx]
0x180003899  movdqu  xmmword ptr [rax+30h], xmm0
0x18000389e  mov     [rax+40h], r12
0x1800038a2  mov     [rax+48h], r12
0x1800038a6  xorps   xmm0, xmm0
0x1800038a9  mov     [rax+50h], r12
0x1800038ad  mov     [rax+58h], r12d
0x1800038b1  mov     [rax+60h], r12
0x1800038b5  mov     [rax+68h], r12d
0x1800038b9  mov     [rax+70h], r12
0x1800038bd  mov     [rax+88h], r12d
0x1800038c4  mov     [rax+90h], r15
0x1800038cb  mov     [rax+98h], r14
0x1800038d2  mov     [rax+0C8h], r12
0x1800038d9  add     rax, 78h ; 'x'
0x1800038dd  mov     [rax+8], rax
0x1800038e1  mov     [rax], rax
0x1800038e4  movups  xmmword ptr [rbx], xmm0
0x1800038e7  call    cs:__imp_InitializeCriticalSection
0x1800038ed  mov     rax, [rsp+98h+arg_60]
0x1800038f5  mov     r8d, edi
0x1800038f8  mov     r9d, [rsp+98h+arg_20]
0x180003900  mov     edx, ebp
0x180003902  mov     [rsp+98h+var_40], rax
0x180003907  mov     rcx, rbx
0x18000390a  mov     rax, [rsp+98h+arg_58]
0x180003912  mov     [rsp+98h+var_48], rax
0x180003917  mov     eax, [rsp+98h+arg_50]
0x18000391e  mov     [rsp+98h+var_50], eax
0x180003922  mov     rax, [rsp+98h+arg_48]
0x18000392a  mov     [rsp+98h+var_58], rax
0x18000392f  mov     eax, [rsp+98h+arg_40]
0x180003936  mov     [rsp+98h+var_60], eax
0x18000393a  mov     rax, [rsp+98h+arg_38]
0x180003942  mov     [rsp+98h+var_68], rax
0x180003947  mov     eax, [rsp+98h+arg_30]
0x18000394e  mov     [rsp+98h+var_70], eax
0x180003952  mov     rax, [rsp+98h+arg_28]
0x18000395a  mov     [rsp+98h+var_78], rax
0x18000395f  call    ?CopyParameters@CQuery@@IEAAJW4_DEV_OBJECT_TYPE@@KKPEAPEBGKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@PEBG@Z; CQuery::CopyParameters(_DEV_OBJECT_TYPE,ulong,ulong,ushort const * *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,ushort const *)
0x180003964  mov     edi, eax
0x180003966  test    eax, eax
0x180003968  js      short loc_18000396F
0x18000396a  mov     [rsi], rbx
0x18000396d  jmp     short loc_180003986
0x18000396f  mov     rcx, rbx; this
0x180003972  call    ??1CQuery@@QEAA@XZ; CQuery::~CQuery(void)
0x180003977  mov     rcx, rbx; Block
0x18000397a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000397f  jmp     short loc_180003986
0x180003981  mov     edi, 8007000Eh
0x180003986  mov     eax, edi
0x180003988  add     rsp, 60h
0x18000398c  pop     r15
0x18000398e  pop     r14
0x180003990  pop     r12
0x180003992  pop     rdi
0x180003993  pop     rsi
0x180003994  pop     rbp
0x180003995  pop     rbx
0x180003996  retn
```
