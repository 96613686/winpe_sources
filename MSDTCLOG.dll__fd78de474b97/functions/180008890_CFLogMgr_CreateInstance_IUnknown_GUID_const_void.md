# CFLogMgr::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008890`
- end: `0x18000893a`
- name: `?CreateInstance@CFLogMgr@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `170`
- prototype: `__int64 __fastcall(CFLogMgr *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x180005ff0`
- `0x1800062a0`
- `0x180008890`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CFLogMgr::CreateInstance(CFLogMgr *this, struct IUnknown *a2, const struct _GUID *a3, void **a4)
{
  bool v6; // zf
  CLogMgr *v7; // rcx
  __int64 result; // rax
  unsigned int v9; // ebx
  CLogMgr *v10; // rdi

  if ( !a4 )
    return 2147942487LL;
  v6 = fCreated == 0;
  *a4 = 0;
  if ( v6 )
  {
    result = CLogMgr::CreateInstance2(&gpCLogMgr, a2);
    if ( (int)result < 0 )
      return result;
    v7 = gpCLogMgr;
  }
  else
  {
    v7 = gpCLogMgr;
    if ( !gpCLogMgr )
      return 2147942487LL;
  }
  result = (**(__int64 (__fastcall ***)(CLogMgr *, const struct _GUID *, void **))v7)(v7, a3, a4);
  v9 = result;
  if ( (int)result >= 0 )
  {
    if ( !(_DWORD)result )
      fCreated = 1;
  }
  else
  {
    v10 = gpCLogMgr;
    if ( gpCLogMgr )
    {
      CLogMgr::~CLogMgr((void (***)(void))gpCLogMgr);
      operator delete(v10);
    }
    gpCLogMgr = 0;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180008890  mov     [rsp+arg_0], rbx
0x180008895  push    rdi
0x180008896  sub     rsp, 20h
0x18000889a  mov     rbx, r9
0x18000889d  mov     rdi, r8
0x1800088a0  test    r9, r9
0x1800088a3  jz      short loc_1800088C1
0x1800088a5  cmp     cs:?fCreated@@3HA, 0; int fCreated
0x1800088ac  mov     qword ptr [r9], 0
0x1800088b3  jz      short loc_1800088D1
0x1800088b5  mov     rcx, cs:?gpCLogMgr@@3PEAVCLogMgr@@EA; CLogMgr * gpCLogMgr
0x1800088bc  test    rcx, rcx
0x1800088bf  jnz     short loc_1800088E8
0x1800088c1  mov     eax, 80070057h
0x1800088c6  mov     rbx, [rsp+28h+arg_0]
0x1800088cb  add     rsp, 20h
0x1800088cf  pop     rdi
0x1800088d0  retn
0x1800088d1  lea     rcx, ?gpCLogMgr@@3PEAVCLogMgr@@EA; struct CLogMgr **
0x1800088d8  call    ?CreateInstance2@CLogMgr@@SAJPEAPEAV1@PEAUIUnknown@@@Z; CLogMgr::CreateInstance2(CLogMgr * *,IUnknown *)
0x1800088dd  test    eax, eax
0x1800088df  js      short loc_1800088C6
0x1800088e1  mov     rcx, cs:?gpCLogMgr@@3PEAVCLogMgr@@EA; CLogMgr * gpCLogMgr
0x1800088e8  mov     rax, [rcx]
0x1800088eb  mov     r8, rbx
0x1800088ee  mov     rdx, rdi
0x1800088f1  mov     rax, [rax]
0x1800088f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088f9  mov     ebx, eax
0x1800088fb  test    eax, eax
0x1800088fd  jns     short loc_18000892A
0x1800088ff  mov     rdi, cs:?gpCLogMgr@@3PEAVCLogMgr@@EA; CLogMgr * gpCLogMgr
0x180008906  test    rdi, rdi
0x180008909  jz      short loc_18000891B
0x18000890b  mov     rcx, rdi; this
0x18000890e  call    ??1CLogMgr@@QEAA@XZ; CLogMgr::~CLogMgr(void)
0x180008913  mov     rcx, rdi; Block
0x180008916  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000891b  mov     cs:?gpCLogMgr@@3PEAVCLogMgr@@EA, 0; CLogMgr * gpCLogMgr
0x180008926  mov     eax, ebx
0x180008928  jmp     short loc_1800088C6
0x18000892a  test    ebx, ebx
0x18000892c  jnz     short loc_1800088C6
0x18000892e  mov     cs:?fCreated@@3HA, 1; int fCreated
0x180008938  jmp     short loc_1800088C6
```
