# CommonUtil::CMpPrivateThreadPool::Initialize(unsigned __int64)

- ea: `0x1800e3624`
- end: `0x1800e36b9`
- name: `?Initialize@CMpPrivateThreadPool@CommonUtil@@QEAAJ_K@Z`
- size: `149`
- prototype: `int(CommonUtil::CMpPrivateThreadPool *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800e33d4`

## callees

- `0x18000d7fc`
- `0x1800e1690`
- `0x1800e3624`

## import_xrefs

- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800e36a6`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800e36a6`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1800e368f`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1800e368f`
- `KERNEL32!CreateThreadpool` at `0x1800e363f`
- `KERNEL32!CreateThreadpool` at `0x1800e363f`

## pseudocode

```c
__int64 __fastcall CommonUtil::CMpPrivateThreadPool::Initialize(CommonUtil::CMpPrivateThreadPool *this, __int64 a2)
{
  DWORD v3; // ebx
  struct _TP_POOL *Threadpool; // rax
  unsigned int LastFailure; // ebx

  v3 = 500;
  if ( a2 )
    v3 = a2;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 2) = Threadpool;
  if ( Threadpool )
  {
    if ( SetThreadpoolThreadMinimum(Threadpool, 0) )
    {
      SetThreadpoolThreadMaximum(*((PTP_POOL *)this + 2), v3);
      return 0;
    }
    else
    {
      return HrGetLastFailure();
    }
  }
  else
  {
    LastFailure = HrGetLastFailure();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9224ac78a9b3321a5dea704e91cbad1f_Traceguids, LastFailure);
    return LastFailure;
  }
}

```

## disassembly

```asm
0x1800e3624  mov     [rsp+arg_0], rbx
0x1800e3629  push    rdi
0x1800e362a  sub     rsp, 20h
0x1800e362e  test    rdx, rdx
0x1800e3631  mov     rdi, rcx
0x1800e3634  mov     ebx, 1F4h
0x1800e3639  cmovnz  rbx, rdx
0x1800e363d  xor     ecx, ecx; reserved
0x1800e363f  call    cs:__imp_CreateThreadpool
0x1800e3645  mov     [rdi+10h], rax
0x1800e3649  test    rax, rax
0x1800e364c  jnz     short loc_1800E368A
0x1800e364e  call    HrGetLastFailure
0x1800e3653  mov     ebx, eax
0x1800e3655  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e365c  lea     rax, WPP_GLOBAL_Control
0x1800e3663  cmp     rcx, rax
0x1800e3666  jz      short loc_1800E3686
0x1800e3668  test    byte ptr [rcx+1Ch], 1
0x1800e366c  jz      short loc_1800E3686
0x1800e366e  mov     rcx, [rcx+10h]
0x1800e3672  lea     r8, WPP_9224ac78a9b3321a5dea704e91cbad1f_Traceguids
0x1800e3679  mov     edx, 0Bh
0x1800e367e  mov     r9d, ebx
0x1800e3681  call    WPP_SF_d
0x1800e3686  mov     eax, ebx
0x1800e3688  jmp     short loc_1800E36AE
0x1800e368a  xor     edx, edx; cthrdMic
0x1800e368c  mov     rcx, rax; ptpp
0x1800e368f  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800e3695  test    eax, eax
0x1800e3697  jnz     short loc_1800E36A0
0x1800e3699  call    HrGetLastFailure
0x1800e369e  jmp     short loc_1800E36AE
0x1800e36a0  mov     rcx, [rdi+10h]; ptpp
0x1800e36a4  mov     edx, ebx; cthrdMost
0x1800e36a6  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800e36ac  xor     eax, eax
0x1800e36ae  mov     rbx, [rsp+28h+arg_0]
0x1800e36b3  add     rsp, 20h
0x1800e36b7  pop     rdi
0x1800e36b8  retn
```
