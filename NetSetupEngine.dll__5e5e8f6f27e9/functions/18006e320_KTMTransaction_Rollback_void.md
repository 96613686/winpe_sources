# KTMTransaction::Rollback(void)

- ea: `0x18006e320`
- end: `0x18006e399`
- name: `?Rollback@KTMTransaction@@UEBAXXZ`
- size: `121`
- prototype: `void __fastcall(KTMTransaction *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x180065035`
- `0x18006e0b4`
- `0x18006e320`
- `0x18006e4d8`

## import_xrefs

- `ntdll!NtRollbackTransaction` at `0x18006e32f`
- `ntdll!NtRollbackTransaction` at `0x18006e32f`

## pseudocode

```c
void __fastcall KTMTransaction::Rollback(KTMTransaction *this, __int64 a2)
{
  int v2; // ebx
  __int64 v3; // r8
  _BYTE pExceptionObject[216]; // [rsp+30h] [rbp-D8h] BYREF

  LOBYTE(a2) = 1;
  v2 = NtRollbackTransaction(*((_QWORD *)this + 1), a2);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = (unsigned int)v2;
      LODWORD(v3) = v2 | 0x10000000;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v3, (unsigned int)v2, v2 | 0x10000000);
    }
    NtStatusException::NtStatusException((NtStatusException *)pExceptionObject, v2);
    throw (NtStatusException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18006e320  push    rbx
0x18006e322  sub     rsp, 100h
0x18006e329  mov     rcx, [rcx+8]
0x18006e32d  mov     dl, 1
0x18006e32f  call    cs:__imp_NtRollbackTransaction
0x18006e335  mov     ebx, eax
0x18006e337  test    eax, eax
0x18006e339  jns     short loc_18006E390
0x18006e33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e342  lea     rax, WPP_GLOBAL_Control
0x18006e349  cmp     rcx, rax
0x18006e34c  jz      short loc_18006E372
0x18006e34e  cmp     byte ptr [rcx+19h], 2
0x18006e352  jb      short loc_18006E372
0x18006e354  mov     rcx, [rcx+10h]
0x18006e358  mov     r8d, ebx
0x18006e35b  bts     r8d, 1Ch
0x18006e360  mov     edx, 0Fh
0x18006e365  mov     r9d, ebx
0x18006e368  mov     [rsp+108h+var_E8], r8d
0x18006e36d  call    WPP_SF_dd
0x18006e372  mov     edx, ebx; int
0x18006e374  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18006e379  call    ??0NtStatusException@@QEAA@J@Z; NtStatusException::NtStatusException(long)
0x18006e37e  lea     rdx, _TI4?AVNtStatusException@@; pThrowInfo
0x18006e385  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18006e38a  call    _CxxThrowException_0
0x18006e390  add     rsp, 100h
0x18006e397  pop     rbx
0x18006e398  retn
```
