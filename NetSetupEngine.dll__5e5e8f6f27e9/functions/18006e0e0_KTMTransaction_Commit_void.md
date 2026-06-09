# KTMTransaction::Commit(void)

- ea: `0x18006e0e0`
- end: `0x18006e159`
- name: `?Commit@KTMTransaction@@UEBAXXZ`
- size: `121`
- prototype: `void __fastcall(KTMTransaction *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180065035`
- `0x18006e0b4`
- `0x18006e0e0`
- `0x18006e4d8`

## import_xrefs

- `ntdll!NtCommitTransaction` at `0x18006e0ef`
- `ntdll!NtCommitTransaction` at `0x18006e0ef`

## pseudocode

```c
void __fastcall KTMTransaction::Commit(KTMTransaction *this, __int64 a2)
{
  int v2; // ebx
  __int64 v3; // r8
  _BYTE pExceptionObject[216]; // [rsp+30h] [rbp-D8h] BYREF

  LOBYTE(a2) = 1;
  v2 = NtCommitTransaction(*((_QWORD *)this + 1), a2);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = (unsigned int)v2;
      LODWORD(v3) = v2 | 0x10000000;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v3, (unsigned int)v2, v2 | 0x10000000);
    }
    NtStatusException::NtStatusException((NtStatusException *)pExceptionObject, v2);
    throw (NtStatusException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18006e0e0  push    rbx
0x18006e0e2  sub     rsp, 100h
0x18006e0e9  mov     rcx, [rcx+8]
0x18006e0ed  mov     dl, 1
0x18006e0ef  call    cs:__imp_NtCommitTransaction
0x18006e0f5  mov     ebx, eax
0x18006e0f7  test    eax, eax
0x18006e0f9  jns     short loc_18006E150
0x18006e0fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e102  lea     rax, WPP_GLOBAL_Control
0x18006e109  cmp     rcx, rax
0x18006e10c  jz      short loc_18006E132
0x18006e10e  cmp     byte ptr [rcx+19h], 2
0x18006e112  jb      short loc_18006E132
0x18006e114  mov     rcx, [rcx+10h]
0x18006e118  mov     r8d, ebx
0x18006e11b  bts     r8d, 1Ch
0x18006e120  mov     edx, 0Eh
0x18006e125  mov     r9d, ebx
0x18006e128  mov     [rsp+108h+var_E8], r8d
0x18006e12d  call    WPP_SF_dd
0x18006e132  mov     edx, ebx; int
0x18006e134  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18006e139  call    ??0NtStatusException@@QEAA@J@Z; NtStatusException::NtStatusException(long)
0x18006e13e  lea     rdx, _TI4?AVNtStatusException@@; pThrowInfo
0x18006e145  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18006e14a  call    _CxxThrowException_0
0x18006e150  add     rsp, 100h
0x18006e157  pop     rbx
0x18006e158  retn
```
