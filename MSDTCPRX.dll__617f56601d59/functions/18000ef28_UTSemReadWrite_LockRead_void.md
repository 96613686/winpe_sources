# UTSemReadWrite::LockRead(void)

- ea: `0x18000ef28`
- end: `0x18000f0ba`
- name: `?LockRead@UTSemReadWrite@@QEAAXXZ`
- size: `402`
- prototype: `void __fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `20`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009e40`
- `0x18003b194`
- `0x18003c260`
- `0x18004ef40`
- `0x18004f330`
- `0x18004f370`
- `0x18004f4f0`
- `0x18004f550`
- `0x18004f5d0`
- `0x18004f630`
- `0x18004f930`
- `0x18007a3dc`
- `0x18007a4c4`
- `0x18007b2d0`
- `0x18007b330`
- `0x18007b390`
- `0x18007b540`
- `0x18007b6e0`
- `0x18007b890`
- `0x18007ba30`

## callees

- `0x18000792c`
- `0x18000ef28`
- `0x18000fa40`
- `0x18007d168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000efb7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000efb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efc1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ef85`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ef85`

## string_xrefs

- `0x18000efe2`: `com\complus\src\shared\util\utsem.cpp`
- `0x18000f027`: `com\complus\src\shared\util\utsem.cpp`
- `0x18000f079`: `com\complus\src\shared\util\utsem.cpp`
- `0x18000f00f`: `Problem with Reader info in UTSemReadWrite::LockRead`
- `0x18000efcd`: `WaitForSingleObject failed in UTSemReadWrite:LockRead`
- `0x18000f061`: `Problem with Writer info in UTSemReadWrite::LockRead`

## pseudocode

```c
void __fastcall UTSemReadWrite::LockRead(UTSemReadWrite *this)
{
  unsigned int v1; // edi
  unsigned __int32 v3; // edx
  unsigned int v4; // eax
  void *WaiterSemaphore; // rax
  DWORD LastError; // eax
  unsigned __int16 v7; // r8
  unsigned int v8; // r9d
  const void *v9; // [rsp+28h] [rbp-31h]
  unsigned int v10; // [rsp+30h] [rbp-29h]
  int v11; // [rsp+38h] [rbp-21h]
  int v12; // [rsp+40h] [rbp-19h]
  int v13; // [rsp+50h] [rbp-9h] BYREF
  __int16 v14; // [rsp+54h] [rbp-5h]
  int v15; // [rsp+58h] [rbp-1h]
  unsigned __int16 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  __int64 v18; // [rsp+70h] [rbp+17h]
  int v19; // [rsp+78h] [rbp+1Fh]
  int v20; // [rsp+7Ch] [rbp+23h]

  v1 = 0;
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v3 = *((_DWORD *)this + 1);
        if ( v3 >= 0x3FF )
          break;
        if ( v3 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v3 + 1, v3) )
          goto LABEL_12;
      }
      if ( (*((_DWORD *)this + 1) & 0x3FF) != 0x3FF && (v3 & 0x3FF000) != 0x3FF000 )
        break;
      Sleep(0x3E8u);
    }
    v4 = v1++;
  }
  while ( v4 < *(_DWORD *)this || v3 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v3 + 4096, v3) );
  WaiterSemaphore = UTSemReadWrite::GetReadWaiterSemaphore(this);
  if ( WaitForSingleObject(WaiterSemaphore, 0xFFFFFFFF) == -1 )
  {
    LastError = GetLastError();
    CErrorWin32::CErrorWin32(
      (CErrorWin32 *)&v13,
      LastError,
      v7,
      v8,
      L"WaitForSingleObject failed in UTSemReadWrite:LockRead",
      v9,
      v10,
      v11,
      v12);
    v19 = 1;
    CError::WriteToLog((CError *)&v13, L"com\\complus\\src\\shared\\util\\utsem.cpp", 0x165u, v16);
  }
LABEL_12:
  if ( (*((_DWORD *)this + 1) & 0x3FF) == 0 )
  {
    v13 = 0;
    v16 = L"Problem with Reader info in UTSemReadWrite::LockRead";
    v14 = 21;
    v15 = -1073606063;
    v17 = 0;
    v18 = 0;
    v20 = 1;
    v19 = 1;
    CError::WriteToLog(
      (CError *)&v13,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x16Fu,
      L"Problem with Reader info in UTSemReadWrite::LockRead");
  }
  if ( (*((_DWORD *)this + 1) & 0xC00) != 0 )
  {
    v13 = 0;
    v16 = L"Problem with Writer info in UTSemReadWrite::LockRead";
    v14 = 21;
    v15 = -1073606063;
    v17 = 0;
    v18 = 0;
    v20 = 1;
    v19 = 1;
    CError::WriteToLog(
      (CError *)&v13,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x171u,
      L"Problem with Writer info in UTSemReadWrite::LockRead");
  }
}

```

## disassembly

```asm
0x18000ef28  push    rbp
0x18000ef2a  push    rbx
0x18000ef2b  push    rdi
0x18000ef2c  push    r12
0x18000ef2e  push    r14
0x18000ef30  push    r15
0x18000ef32  lea     rbp, [rsp-2Fh]
0x18000ef37  sub     rsp, 88h
0x18000ef3e  xor     edi, edi
0x18000ef40  mov     r15d, 3FFh
0x18000ef46  mov     rbx, rcx
0x18000ef49  lea     r12d, [r15-17h]
0x18000ef4d  lea     r14d, [rdi+1]
0x18000ef51  mov     edx, [rbx+4]
0x18000ef54  mov     eax, edx
0x18000ef56  cmp     edx, r15d
0x18000ef59  jnb     short loc_18000EF6C
0x18000ef5b  lea     ecx, [rdx+1]
0x18000ef5e  lock cmpxchg [rbx+4], ecx
0x18000ef63  cmp     edx, eax
0x18000ef65  jnz     short loc_18000EF51
0x18000ef67  jmp     loc_18000EFFC
0x18000ef6c  and     eax, r15d
0x18000ef6f  cmp     eax, r15d
0x18000ef72  jz      short loc_18000EF82
0x18000ef74  mov     eax, edx
0x18000ef76  and     eax, 3FF000h
0x18000ef7b  cmp     eax, 3FF000h
0x18000ef80  jnz     short loc_18000EF8D
0x18000ef82  mov     ecx, r12d; dwMilliseconds
0x18000ef85  call    cs:__imp_Sleep
0x18000ef8b  jmp     short loc_18000EF51
0x18000ef8d  mov     eax, edi
0x18000ef8f  add     edi, r14d
0x18000ef92  cmp     eax, [rbx]
0x18000ef94  jb      short loc_18000EF51
0x18000ef96  lea     ecx, [rdx+1000h]
0x18000ef9c  mov     eax, edx
0x18000ef9e  lock cmpxchg [rbx+4], ecx
0x18000efa3  cmp     edx, eax
0x18000efa5  jnz     short loc_18000EF51
0x18000efa7  mov     rcx, rbx; this
0x18000efaa  call    ?GetReadWaiterSemaphore@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetReadWaiterSemaphore(void)
0x18000efaf  or      edi, 0FFFFFFFFh
0x18000efb2  mov     rcx, rax; hHandle
0x18000efb5  mov     edx, edi; dwMilliseconds
0x18000efb7  call    cs:__imp_WaitForSingleObject
0x18000efbd  cmp     eax, edi
0x18000efbf  jnz     short loc_18000EFFC
0x18000efc1  call    cs:__imp_GetLastError
0x18000efc7  mov     edx, eax; unsigned int
0x18000efc9  lea     rcx, [rbp+57h+var_60]; this
0x18000efcd  lea     rax, aWaitforsingleo_1; "WaitForSingleObject failed in UTSemRead"...
0x18000efd4  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x18000efd9  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x18000efde  mov     r9, [rbp+57h+var_50]; unsigned __int16 *
0x18000efe2  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18000efe9  mov     r8d, 165h; unsigned int
0x18000efef  mov     [rbp+57h+var_38], r14d
0x18000eff3  lea     rcx, [rbp+57h+var_60]; this
0x18000eff7  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000effc  mov     eax, [rbx+4]
0x18000efff  mov     edi, 0C0021251h
0x18000f004  mov     r12d, 15h
0x18000f00a  test    r15d, eax
0x18000f00d  jnz     short loc_18000F057
0x18000f00f  lea     r9, aProblemWithRea_1; "Problem with Reader info in UTSemReadWr"...
0x18000f016  mov     [rbp+57h+var_60], 0
0x18000f01d  mov     r8d, 16Fh; unsigned int
0x18000f023  mov     [rbp+57h+var_50], r9
0x18000f027  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18000f02e  mov     [rbp+57h+var_5C], r12w
0x18000f033  lea     rcx, [rbp+57h+var_60]; this
0x18000f037  mov     [rbp+57h+var_58], edi
0x18000f03a  mov     [rbp+57h+var_48], 0
0x18000f042  mov     [rbp+57h+var_40], 0
0x18000f04a  mov     [rbp+57h+var_34], r14d
0x18000f04e  mov     [rbp+57h+var_38], r14d
0x18000f052  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000f057  mov     eax, [rbx+4]
0x18000f05a  test    eax, 0C00h
0x18000f05f  jz      short loc_18000F0A9
0x18000f061  lea     r9, aProblemWithWri_3; "Problem with Writer info in UTSemReadWr"...
0x18000f068  mov     [rbp+57h+var_60], 0
0x18000f06f  mov     r8d, 171h; unsigned int
0x18000f075  mov     [rbp+57h+var_50], r9
0x18000f079  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18000f080  mov     [rbp+57h+var_5C], r12w
0x18000f085  lea     rcx, [rbp+57h+var_60]; this
0x18000f089  mov     [rbp+57h+var_58], edi
0x18000f08c  mov     [rbp+57h+var_48], 0
0x18000f094  mov     [rbp+57h+var_40], 0
0x18000f09c  mov     [rbp+57h+var_34], r14d
0x18000f0a0  mov     [rbp+57h+var_38], r14d
0x18000f0a4  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000f0a9  add     rsp, 88h
0x18000f0b0  pop     r15
0x18000f0b2  pop     r14
0x18000f0b4  pop     r12
0x18000f0b6  pop     rdi
0x18000f0b7  pop     rbx
0x18000f0b8  pop     rbp
0x18000f0b9  retn
```
