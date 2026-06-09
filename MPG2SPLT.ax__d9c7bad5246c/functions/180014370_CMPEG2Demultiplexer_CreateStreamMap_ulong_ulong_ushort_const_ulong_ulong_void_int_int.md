# CMPEG2Demultiplexer::CreateStreamMap_(ulong,ulong *,ushort const *,ulong,ulong,void *,int,int)

- ea: `0x180014370`
- end: `0x18001455d`
- name: `?CreateStreamMap_@CMPEG2Demultiplexer@@AEAAJKPEAKPEBGKKPEAXHH@Z`
- size: `493`
- prototype: `__int64 __usercall@<rax>(CMPEG2Demultiplexer *__hidden this@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, const unsigned __int16 *@<r9>, unsigned int, unsigned int, void *, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001c900`
- `0x18001c9a0`
- `0x18001e880`

## callees

- `0x180001048`
- `0x180001460`
- `0x180001e98`
- `0x180006b18`
- `0x180014370`
- `0x180014998`
- `0x180020a34`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800144c4`
- `KERNEL32!LeaveCriticalSection` at `0x1800144dd`
- `KERNEL32!LeaveCriticalSection` at `0x1800144c4`
- `KERNEL32!LeaveCriticalSection` at `0x1800144dd`
- `KERNEL32!EnterCriticalSection` at `0x1800143ea`
- `KERNEL32!EnterCriticalSection` at `0x1800143f4`
- `KERNEL32!EnterCriticalSection` at `0x1800143ea`
- `KERNEL32!EnterCriticalSection` at `0x1800143f4`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::CreateStreamMap_(
        CMPEG2Demultiplexer *this,
        unsigned int a2,
        unsigned int *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        void *a7,
        int a8,
        int a9)
{
  __int64 v12; // rax
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  int PinRecordLocked; // eax
  void **v15; // rbx
  int v16; // edi
  struct CMPEG2DemuxOutputPin *v17; // r15
  __int64 v18; // rbp
  unsigned int *v19; // rbx
  struct _RTL_CRITICAL_SECTION *v20; // rcx
  struct DEMUX_PIN_RECORD *v22; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int *v23; // [rsp+48h] [rbp-C0h]
  void *v24; // [rsp+50h] [rbp-B8h]
  struct _AMMediaType v25; // [rsp+60h] [rbp-A8h] BYREF

  v23 = a3;
  v24 = a7;
  memset_0(&v25, 0, sizeof(v25));
  v12 = *((_QWORD *)this + 42);
  v25.lSampleSize = 1;
  v25.bFixedSizeSamples = 1;
  v13 = *(struct _RTL_CRITICAL_SECTION **)(v12 + 184);
  if ( v13 )
    EnterCriticalSection(v13);
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  v22 = 0;
  PinRecordLocked = CMPEG2Demultiplexer::FindPinRecordLocked_(this, a4, &v22, 0);
  v15 = (void **)v22;
  v16 = PinRecordLocked;
  if ( PinRecordLocked >= 0 )
  {
    if ( *((_DWORD *)v22 + 3) == 1 )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _AMMediaType *))(**(_QWORD **)v22 + 104LL))(
              *(_QWORD *)v22,
              0,
              &v25);
      if ( !v16 )
      {
        v17 = (struct CMPEG2DemuxOutputPin *)*v15;
        v18 = 0;
        if ( a2 )
        {
          v19 = v23;
          do
          {
            v16 = CMPEG2Controller::MapStream(*((CMPEG2Controller **)this + 42), a6 & v19[v18], v17, a5, v24, a8, a9);
            if ( v16 < 0 )
              break;
            v18 = (unsigned int)(v18 + 1);
            *((_DWORD *)this + 33) = 1;
          }
          while ( (unsigned int)v18 < a2 );
          v15 = (void **)v22;
        }
      }
    }
    else
    {
      v16 = -2147467259;
    }
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  v20 = *(struct _RTL_CRITICAL_SECTION **)(*((_QWORD *)this + 42) + 184LL);
  if ( v20 )
    LeaveCriticalSection(v20);
  if ( v15 && _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 2, 0xFFFFFFFF) == 1 )
  {
    operator delete(v15[2]);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v15 + 1) + 16LL))(*((_QWORD *)*v15 + 1));
    operator delete(v15);
  }
  FreeMediaType(&v25);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180014370  mov     [rsp+arg_8], rbx
0x180014375  push    rbp
0x180014376  push    rsi
0x180014377  push    rdi
0x180014378  push    r12
0x18001437a  push    r13
0x18001437c  push    r14
0x18001437e  push    r15
0x180014380  sub     rsp, 0D0h
0x180014387  mov     rax, cs:__security_cookie
0x18001438e  xor     rax, rsp
0x180014391  mov     [rsp+108h+var_48], rax
0x180014399  mov     rax, [rsp+108h+arg_30]
0x1800143a1  mov     r14d, edx
0x1800143a4  xor     edx, edx; Val
0x1800143a6  mov     [rsp+108h+var_C0], r8
0x1800143ab  mov     rsi, rcx
0x1800143ae  mov     [rsp+108h+var_B8], rax
0x1800143b3  lea     rcx, [rsp+108h+var_A8]; void *
0x1800143b8  mov     rbx, r9
0x1800143bb  lea     r8d, [rdx+58h]; Size
0x1800143bf  call    memset_0
0x1800143c4  mov     rax, [rsi+150h]
0x1800143cb  mov     ebp, 1
0x1800143d0  mov     [rsp+108h+var_A8.lSampleSize], ebp
0x1800143d7  mov     [rsp+108h+var_A8.bFixedSizeSamples], ebp
0x1800143de  mov     rcx, [rax+0B8h]; lpCriticalSection
0x1800143e5  test    rcx, rcx
0x1800143e8  jz      short loc_1800143F0
0x1800143ea  call    cs:__imp_EnterCriticalSection
0x1800143f0  mov     rcx, [rsi+50h]; lpCriticalSection
0x1800143f4  call    cs:__imp_EnterCriticalSection
0x1800143fa  xor     r9d, r9d; unsigned int *
0x1800143fd  mov     [rsp+108h+var_C8], 0
0x180014406  lea     r8, [rsp+108h+var_C8]; struct DEMUX_PIN_RECORD **
0x18001440b  mov     rdx, rbx; unsigned __int16 *
0x18001440e  mov     rcx, rsi; this
0x180014411  call    ?FindPinRecordLocked_@CMPEG2Demultiplexer@@AEAAJPEBGPEAPEAUDEMUX_PIN_RECORD@@PEAK@Z; CMPEG2Demultiplexer::FindPinRecordLocked_(ushort const *,DEMUX_PIN_RECORD * *,ulong *)
0x180014416  mov     rbx, [rsp+108h+var_C8]
0x18001441b  mov     edi, eax
0x18001441d  test    eax, eax
0x18001441f  js      loc_1800144C0
0x180014425  cmp     [rbx+0Ch], ebp
0x180014428  jz      short loc_180014434
0x18001442a  mov     edi, 80004005h
0x18001442f  jmp     loc_1800144C0
0x180014434  mov     rcx, [rbx]
0x180014437  lea     r8, [rsp+108h+var_A8]
0x18001443c  xor     edx, edx
0x18001443e  mov     rax, [rcx]
0x180014441  mov     rax, [rax+68h]
0x180014445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001444a  mov     edi, eax
0x18001444c  test    eax, eax
0x18001444e  jnz     short loc_1800144C0
0x180014450  mov     r15, [rbx]
0x180014453  xor     ebp, ebp
0x180014455  test    r14d, r14d
0x180014458  jz      short loc_1800144C0
0x18001445a  mov     r12d, [rsp+108h+arg_40]
0x180014462  mov     r13d, [rsp+108h+arg_38]
0x18001446a  mov     rbx, [rsp+108h+var_C0]
0x18001446f  mov     edx, [rbx+rbp*4]
0x180014472  mov     r8, r15; struct CMPEG2DemuxOutputPin *
0x180014475  mov     rax, [rsp+108h+var_B8]
0x18001447a  and     edx, [rsp+108h+arg_28]; unsigned int
0x180014481  mov     r9d, [rsp+108h+arg_20]; unsigned int
0x180014489  mov     rcx, [rsi+150h]; this
0x180014490  mov     [rsp+108h+var_D8], r12d; int
0x180014495  mov     [rsp+108h+var_E0], r13d; int
0x18001449a  mov     [rsp+108h+var_E8], rax; void *
0x18001449f  call    ?MapStream@CMPEG2Controller@@QEAAJKPEAVCMPEG2DemuxOutputPin@@KPEAXHH@Z; CMPEG2Controller::MapStream(ulong,CMPEG2DemuxOutputPin *,ulong,void *,int,int)
0x1800144a4  mov     edi, eax
0x1800144a6  test    eax, eax
0x1800144a8  js      short loc_1800144BB
0x1800144aa  inc     ebp
0x1800144ac  mov     dword ptr [rsi+84h], 1
0x1800144b6  cmp     ebp, r14d
0x1800144b9  jb      short loc_18001446F
0x1800144bb  mov     rbx, [rsp+108h+var_C8]
0x1800144c0  mov     rcx, [rsi+50h]; lpCriticalSection
0x1800144c4  call    cs:__imp_LeaveCriticalSection
0x1800144ca  mov     rax, [rsi+150h]
0x1800144d1  mov     rcx, [rax+0B8h]; lpCriticalSection
0x1800144d8  test    rcx, rcx
0x1800144db  jz      short loc_1800144E3
0x1800144dd  call    cs:__imp_LeaveCriticalSection
0x1800144e3  test    rbx, rbx
0x1800144e6  jz      short loc_180014526
0x1800144e8  or      eax, 0FFFFFFFFh
0x1800144eb  lock xadd [rbx+8], eax
0x1800144f0  cmp     eax, 1
0x1800144f3  jnz     short loc_180014526
0x1800144f5  test    rbx, rbx
0x1800144f8  jz      short loc_180014526
0x1800144fa  mov     rcx, [rbx+10h]; void *
0x1800144fe  lea     edx, [rax+1]; unsigned __int64
0x180014501  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014506  mov     rax, [rbx]
0x180014509  mov     rcx, [rax+8]
0x18001450d  mov     rax, [rcx]
0x180014510  mov     rax, [rax+10h]
0x180014514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014519  mov     edx, 18h; unsigned __int64
0x18001451e  mov     rcx, rbx; void *
0x180014521  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014526  lea     rcx, [rsp+108h+var_A8]; struct _AMMediaType *
0x18001452b  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180014530  mov     eax, edi
0x180014532  mov     rcx, [rsp+108h+var_48]
0x18001453a  xor     rcx, rsp; StackCookie
0x18001453d  call    __security_check_cookie
0x180014542  mov     rbx, [rsp+108h+arg_8]
0x18001454a  add     rsp, 0D0h
0x180014551  pop     r15
0x180014553  pop     r14
0x180014555  pop     r13
0x180014557  pop     r12
0x180014559  pop     rdi
0x18001455a  pop     rsi
0x18001455b  pop     rbp
0x18001455c  retn
```
