# CommonUtil::UtilSetFilePointer(void *,unsigned __int64,ulong,unsigned __int64 *)

- ea: `0x140004740`
- end: `0x1400047dd`
- name: `?UtilSetFilePointer@CommonUtil@@YAJPEAX_KKPEA_K@Z`
- size: `157`
- prototype: `int(CommonUtil *__hidden this, void *, unsigned __int64, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002380c`

## callees

- `0x140004740`
- `0x14000493c`
- `0x140005c20`
- `0x14001da70`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x140004775`
- `KERNEL32!SetFilePointerEx` at `0x140004775`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilSetFilePointer(CommonUtil *this, LARGE_INTEGER a2, DWORD a3, _QWORD *a4)
{
  unsigned int LastFailure; // ebx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  if ( SetFilePointerEx(this, a2, (PLARGE_INTEGER)((unsigned __int64)&v7 & -(__int64)(a4 != 0)), a3) )
  {
    if ( a4 )
      *a4 = v7;
    return 0;
  }
  else
  {
    LastFailure = HrGetLastFailure();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_bed851edf8673fd54b380593fb017a56_Traceguids, LastFailure);
    return LastFailure;
  }
}

```

## disassembly

```asm
0x140004740  push    rbx
0x140004742  sub     rsp, 30h
0x140004746  mov     rax, cs:__security_cookie
0x14000474d  xor     rax, rsp
0x140004750  mov     [rsp+38h+var_10], rax
0x140004755  mov     rbx, r9
0x140004758  mov     [rsp+38h+var_18], 0
0x140004761  mov     r9d, r8d; dwMoveMethod
0x140004764  mov     rax, rbx
0x140004767  neg     rax
0x14000476a  lea     rax, [rsp+38h+var_18]
0x14000476f  sbb     r8, r8
0x140004772  and     r8, rax; lpNewFilePointer
0x140004775  call    cs:__imp_SetFilePointerEx
0x14000477b  test    eax, eax
0x14000477d  jnz     short loc_1400047BB
0x14000477f  call    HrGetLastFailure
0x140004784  mov     ebx, eax
0x140004786  mov     rcx, cs:WPP_GLOBAL_Control
0x14000478d  lea     rax, WPP_GLOBAL_Control
0x140004794  cmp     rcx, rax
0x140004797  jz      short loc_1400047B7
0x140004799  test    byte ptr [rcx+1Ch], 1
0x14000479d  jz      short loc_1400047B7
0x14000479f  mov     rcx, [rcx+10h]
0x1400047a3  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x1400047aa  mov     edx, 18h
0x1400047af  mov     r9d, ebx
0x1400047b2  call    WPP_SF_d
0x1400047b7  mov     eax, ebx
0x1400047b9  jmp     short loc_1400047CA
0x1400047bb  test    rbx, rbx
0x1400047be  jz      short loc_1400047C8
0x1400047c0  mov     rax, [rsp+38h+var_18]
0x1400047c5  mov     [rbx], rax
0x1400047c8  xor     eax, eax
0x1400047ca  mov     rcx, [rsp+38h+var_10]
0x1400047cf  xor     rcx, rsp; StackCookie
0x1400047d2  call    __security_check_cookie
0x1400047d7  add     rsp, 30h
0x1400047db  pop     rbx
0x1400047dc  retn
```
