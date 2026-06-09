# CResourceManager::Save(void *)

- ea: `0x180074f78`
- end: `0x18007519f`
- name: `?Save@CResourceManager@@QEAAHPEAX@Z`
- size: `551`
- prototype: `int(CResourceManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800751b0`

## callees

- `0x180009924`
- `0x180064168`
- `0x1800641cc`
- `0x180073f44`
- `0x180074f78`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007510d`
- `KERNEL32!GetLastError` at `0x180075127`
- `KERNEL32!GetLastError` at `0x180075141`
- `KERNEL32!GetLastError` at `0x18007515b`
- `KERNEL32!GetLastError` at `0x180075175`
- `KERNEL32!GetLastError` at `0x18007510d`
- `KERNEL32!GetLastError` at `0x180075127`
- `KERNEL32!GetLastError` at `0x180075141`
- `KERNEL32!GetLastError` at `0x18007515b`
- `KERNEL32!GetLastError` at `0x180075175`
- `KERNEL32!LeaveCriticalSection` at `0x180075093`
- `KERNEL32!LeaveCriticalSection` at `0x1800750fc`
- `KERNEL32!LeaveCriticalSection` at `0x18007511e`
- `KERNEL32!LeaveCriticalSection` at `0x180075138`
- `KERNEL32!LeaveCriticalSection` at `0x180075152`
- `KERNEL32!LeaveCriticalSection` at `0x18007516c`
- `KERNEL32!LeaveCriticalSection` at `0x180075186`
- `KERNEL32!LeaveCriticalSection` at `0x180075093`
- `KERNEL32!LeaveCriticalSection` at `0x1800750fc`
- `KERNEL32!LeaveCriticalSection` at `0x18007511e`
- `KERNEL32!LeaveCriticalSection` at `0x180075138`
- `KERNEL32!LeaveCriticalSection` at `0x180075152`
- `KERNEL32!LeaveCriticalSection` at `0x18007516c`
- `KERNEL32!LeaveCriticalSection` at `0x180075186`
- `KERNEL32!WriteFile` at `0x180074fc2`
- `KERNEL32!WriteFile` at `0x180074ffc`
- `KERNEL32!WriteFile` at `0x180075034`
- `KERNEL32!WriteFile` at `0x1800750bc`
- `KERNEL32!WriteFile` at `0x1800750e9`
- `KERNEL32!WriteFile` at `0x180074fc2`
- `KERNEL32!WriteFile` at `0x180074ffc`
- `KERNEL32!WriteFile` at `0x180075034`
- `KERNEL32!WriteFile` at `0x1800750bc`
- `KERNEL32!WriteFile` at `0x1800750e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CResourceManager::Save(CResourceManager *this, void *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rcx
  DWORD LastError; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  __int64 v10; // [rsp+30h] [rbp-30h] BYREF
  _QWORD Buffer[2]; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v12[24]; // [rsp+48h] [rbp-18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+20h] BYREF
  int v14; // [rsp+90h] [rbp+30h] BYREF
  CTransaction *v15; // [rsp+98h] [rbp+38h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2808);
  Buffer[1] = (char *)this + 2808;
  CCriticalSection::Lock((CResourceManager *)((char *)this + 2808));
  NumberOfBytesWritten = 0;
  if ( WriteFile(a2, (char *)this + 112, 0x10u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 16 )
  {
    Buffer[0] = 0;
    if ( WriteFile(a2, Buffer, 8u, &NumberOfBytesWritten, 0)
      && NumberOfBytesWritten == 8
      && (v14 = *((_DWORD *)this + 7), WriteFile(a2, &v14, 4u, &NumberOfBytesWritten, 0))
      && NumberOfBytesWritten == 4 )
    {
      v5 = -(__int64)(*((_DWORD *)this + 7) != 0);
      v10 = v5;
      while ( v5 )
      {
        v15 = 0;
        CMap<BOID,BOID const &,CTransaction *,CTransaction *>::GetNextAssoc((char *)this + 8, &v10, v12, &v15);
        if ( !CTransaction::Save(v15, a2) )
        {
          LeaveCriticalSection(v4);
          return 0;
        }
        v5 = v10;
      }
      if ( WriteFile(a2, (char *)this + 128, 4u, &NumberOfBytesWritten, 0)
        && NumberOfBytesWritten == 4
        && WriteFile(a2, (char *)this + 132, 4u, &NumberOfBytesWritten, 0)
        && NumberOfBytesWritten == 4 )
      {
        LeaveCriticalSection(v4);
        return 1;
      }
      LastError = GetLastError();
      ReportWriteFailure(LastError);
      LeaveCriticalSection(v4);
    }
    else
    {
      v8 = GetLastError();
      ReportWriteFailure(v8);
      LeaveCriticalSection(v4);
    }
  }
  else
  {
    v9 = GetLastError();
    ReportWriteFailure(v9);
    LeaveCriticalSection(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180074f78  mov     [rsp-18h+arg_8], rbx
0x180074f7d  push    rbp
0x180074f7e  push    rsi
0x180074f7f  push    rdi
0x180074f80  mov     rbp, rsp
0x180074f83  sub     rsp, 60h
0x180074f87  mov     rsi, rdx
0x180074f8a  mov     rdi, rcx
0x180074f8d  lea     rbx, [rcx+0AF8h]
0x180074f94  mov     [rbp+var_20], rbx
0x180074f98  mov     rcx, rbx; this
0x180074f9b  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180074fa0  nop
0x180074fa1  mov     [rbp+NumberOfBytesWritten], 0
0x180074fa8  lea     rdx, [rdi+70h]; lpBuffer
0x180074fac  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x180074fb5  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180074fb9  mov     r8d, 10h; nNumberOfBytesToWrite
0x180074fbf  mov     rcx, rsi; hFile
0x180074fc2  call    cs:__imp_WriteFile
0x180074fc8  test    eax, eax
0x180074fca  jz      loc_180075175
0x180074fd0  cmp     [rbp+NumberOfBytesWritten], 10h
0x180074fd4  jnz     loc_180075175
0x180074fda  mov     [rbp+Buffer], 0
0x180074fe2  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x180074feb  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180074fef  mov     r8d, 8; nNumberOfBytesToWrite
0x180074ff5  lea     rdx, [rbp+Buffer]; lpBuffer
0x180074ff9  mov     rcx, rsi; hFile
0x180074ffc  call    cs:__imp_WriteFile
0x180075002  test    eax, eax
0x180075004  jz      loc_18007515B
0x18007500a  cmp     [rbp+NumberOfBytesWritten], 8
0x18007500e  jnz     loc_18007515B
0x180075014  mov     eax, [rdi+1Ch]
0x180075017  mov     [rbp+arg_10], eax
0x18007501a  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x180075023  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180075027  mov     r8d, 4; nNumberOfBytesToWrite
0x18007502d  lea     rdx, [rbp+arg_10]; lpBuffer
0x180075031  mov     rcx, rsi; hFile
0x180075034  call    cs:__imp_WriteFile
0x18007503a  test    eax, eax
0x18007503c  jz      loc_180075141
0x180075042  cmp     [rbp+NumberOfBytesWritten], 4
0x180075046  jnz     loc_180075141
0x18007504c  mov     eax, [rdi+1Ch]
0x18007504f  neg     eax
0x180075051  sbb     rcx, rcx
0x180075054  mov     [rbp+var_30], rcx
0x180075058  test    rcx, rcx
0x18007505b  jz      short loc_18007509F
0x18007505d  mov     [rbp+arg_18], 0
0x180075065  lea     rcx, [rdi+8]
0x180075069  lea     r9, [rbp+arg_18]
0x18007506d  lea     r8, [rbp+var_18]
0x180075071  lea     rdx, [rbp+var_30]
0x180075075  call    ?GetNextAssoc@?$CMap@UBOID@@AEBU1@PEAVCTransaction@@PEAV2@@@QEBAXAEAPEAU__POSITION@@AEAUBOID@@AEAPEAVCTransaction@@@Z; CMap<BOID,BOID const &,CTransaction *,CTransaction *>::GetNextAssoc(__POSITION * &,BOID &,CTransaction * &)
0x18007507a  mov     rdx, rsi; void *
0x18007507d  mov     rcx, [rbp+arg_18]; this
0x180075081  call    ?Save@CTransaction@@QEAAHPEAX@Z; CTransaction::Save(void *)
0x180075086  test    eax, eax
0x180075088  jz      short loc_180075090
0x18007508a  mov     rcx, [rbp+var_30]
0x18007508e  jmp     short loc_180075058
0x180075090  mov     rcx, rbx; lpCriticalSection
0x180075093  call    cs:__imp_LeaveCriticalSection
0x180075099  nop
0x18007509a  jmp     loc_18007518D
0x18007509f  lea     rdx, [rdi+80h]; lpBuffer
0x1800750a6  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x1800750af  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800750b3  mov     r8d, 4; nNumberOfBytesToWrite
0x1800750b9  mov     rcx, rsi; hFile
0x1800750bc  call    cs:__imp_WriteFile
0x1800750c2  test    eax, eax
0x1800750c4  jz      short loc_180075127
0x1800750c6  cmp     [rbp+NumberOfBytesWritten], 4
0x1800750ca  jnz     short loc_180075127
0x1800750cc  lea     rdx, [rdi+84h]; lpBuffer
0x1800750d3  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x1800750dc  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800750e0  mov     r8d, 4; nNumberOfBytesToWrite
0x1800750e6  mov     rcx, rsi; hFile
0x1800750e9  call    cs:__imp_WriteFile
0x1800750ef  test    eax, eax
0x1800750f1  jz      short loc_18007510D
0x1800750f3  cmp     [rbp+NumberOfBytesWritten], 4
0x1800750f7  jnz     short loc_18007510D
0x1800750f9  mov     rcx, rbx; lpCriticalSection
0x1800750fc  call    cs:__imp_LeaveCriticalSection
0x180075102  nop
0x180075103  mov     eax, 1
0x180075108  jmp     loc_18007518F
0x18007510d  call    cs:__imp_GetLastError
0x180075113  mov     ecx, eax; unsigned int
0x180075115  call    ?ReportWriteFailure@@YAXK@Z; ReportWriteFailure(ulong)
0x18007511a  nop
0x18007511b  mov     rcx, rbx; lpCriticalSection
0x18007511e  call    cs:__imp_LeaveCriticalSection
0x180075124  nop
0x180075125  jmp     short loc_18007518D
0x180075127  call    cs:__imp_GetLastError
0x18007512d  mov     ecx, eax; unsigned int
0x18007512f  call    ?ReportWriteFailure@@YAXK@Z; ReportWriteFailure(ulong)
0x180075134  nop
0x180075135  mov     rcx, rbx; lpCriticalSection
0x180075138  call    cs:__imp_LeaveCriticalSection
0x18007513e  nop
0x18007513f  jmp     short loc_18007518D
0x180075141  call    cs:__imp_GetLastError
0x180075147  mov     ecx, eax; unsigned int
0x180075149  call    ?ReportWriteFailure@@YAXK@Z; ReportWriteFailure(ulong)
0x18007514e  nop
0x18007514f  mov     rcx, rbx; lpCriticalSection
0x180075152  call    cs:__imp_LeaveCriticalSection
0x180075158  nop
0x180075159  jmp     short loc_18007518D
0x18007515b  call    cs:__imp_GetLastError
0x180075161  mov     ecx, eax; unsigned int
0x180075163  call    ?ReportWriteFailure@@YAXK@Z; ReportWriteFailure(ulong)
0x180075168  nop
0x180075169  mov     rcx, rbx; lpCriticalSection
0x18007516c  call    cs:__imp_LeaveCriticalSection
0x180075172  nop
0x180075173  jmp     short loc_18007518D
0x180075175  call    cs:__imp_GetLastError
0x18007517b  mov     ecx, eax; unsigned int
0x18007517d  call    ?ReportWriteFailure@@YAXK@Z; ReportWriteFailure(ulong)
0x180075182  nop
0x180075183  mov     rcx, rbx; lpCriticalSection
0x180075186  call    cs:__imp_LeaveCriticalSection
0x18007518c  nop
0x18007518d  xor     eax, eax
0x18007518f  mov     rbx, [rsp+60h+arg_8]
0x180075197  add     rsp, 60h
0x18007519b  pop     rdi
0x18007519c  pop     rsi
0x18007519d  pop     rbp
0x18007519e  retn
```
