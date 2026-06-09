# UTSemReadWrite::LockWrite(void)

- ea: `0x18007d2bc`
- end: `0x18007d446`
- name: `?LockWrite@UTSemReadWrite@@QEAAXXZ`
- size: `394`
- prototype: `void __fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `25`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a1b4`
- `0x18000b608`
- `0x18000b9d0`
- `0x18003ada0`
- `0x18003c150`
- `0x18004fab0`
- `0x18004fc10`
- `0x18004fed0`
- `0x18004ff20`
- `0x18004ff70`
- `0x18004ffc0`
- `0x180050080`
- `0x18007a350`
- `0x18007a5a8`
- `0x18007b150`
- `0x18007b18c`
- `0x18007b240`
- `0x18007bab0`
- `0x18007bb10`
- `0x18007bb70`
- `0x18007bce0`
- `0x18007bd40`
- `0x18007bea0`
- `0x18007bf00`
- `0x18007bf60`

## callees

- `0x18000792c`
- `0x18000fa40`
- `0x18007d218`
- `0x18007d2bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007d33e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007d33e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d348`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007d30c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007d30c`

## string_xrefs

- `0x18007d369`: `com\complus\src\shared\util\utsem.cpp`
- `0x18007d3b0`: `com\complus\src\shared\util\utsem.cpp`
- `0x18007d405`: `com\complus\src\shared\util\utsem.cpp`
- `0x18007d354`: `WaitForSingleObject failed in UTSemReadWrite:LockWrite`
- `0x18007d3ed`: `Problem with Writer info in UTSemReadWrite::LockWrite`
- `0x18007d398`: `Problem with Reader info in UTSemReadWrite::LockWrite`

## pseudocode

```c
void __fastcall UTSemReadWrite::LockWrite(UTSemReadWrite *this)
{
  unsigned int v1; // edi
  signed __int32 v3; // edx
  unsigned int v4; // eax
  void *v5; // rax
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
        if ( v3 )
          break;
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 1, 1024, 0) )
          goto LABEL_11;
      }
      if ( (v3 & 0xFFC00000) != 0xFFC00000 )
        break;
      Sleep(0x3E8u);
    }
    v4 = v1++;
  }
  while ( v4 < *(_DWORD *)this
       || v3 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v3 + 0x400000, v3) );
  v5 = UTSemReadWrite::GetWriteWaiterEvent(this);
  if ( WaitForSingleObject(v5, 0xFFFFFFFF) == -1 )
  {
    LastError = GetLastError();
    CErrorWin32::CErrorWin32(
      (CErrorWin32 *)&v13,
      LastError,
      v7,
      v8,
      L"WaitForSingleObject failed in UTSemReadWrite:LockWrite",
      v9,
      v10,
      v11,
      v12);
    v19 = 1;
    CError::WriteToLog((CError *)&v13, L"com\\complus\\src\\shared\\util\\utsem.cpp", 0x1ADu, v16);
  }
LABEL_11:
  if ( (*((_DWORD *)this + 1) & 0x3FF) != 0 )
  {
    v13 = 0;
    v16 = L"Problem with Reader info in UTSemReadWrite::LockWrite";
    v14 = 21;
    v15 = -1073606063;
    v17 = 0;
    v18 = 0;
    v20 = 1;
    v19 = 1;
    CError::WriteToLog(
      (CError *)&v13,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x1B8u,
      L"Problem with Reader info in UTSemReadWrite::LockWrite");
  }
  if ( (*((_DWORD *)this + 1) & 0xC00) != 0x400 )
  {
    v13 = 0;
    v16 = L"Problem with Writer info in UTSemReadWrite::LockWrite";
    v14 = 21;
    v15 = -1073606063;
    v17 = 0;
    v18 = 0;
    v20 = 1;
    v19 = 1;
    CError::WriteToLog(
      (CError *)&v13,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x1BAu,
      L"Problem with Writer info in UTSemReadWrite::LockWrite");
  }
}

```

## disassembly

```asm
0x18007d2bc  push    rbp
0x18007d2be  push    rbx
0x18007d2bf  push    rdi
0x18007d2c0  push    r13
0x18007d2c2  push    r14
0x18007d2c4  push    r15
0x18007d2c6  lea     rbp, [rsp-2Fh]
0x18007d2cb  sub     rsp, 88h
0x18007d2d2  xor     edi, edi
0x18007d2d4  mov     rbx, rcx
0x18007d2d7  mov     r13d, 400h
0x18007d2dd  mov     r15d, 0FFC00000h
0x18007d2e3  lea     r14d, [rdi+1]
0x18007d2e7  mov     edx, [rbx+4]
0x18007d2ea  test    edx, edx
0x18007d2ec  jnz     short loc_18007D2FD
0x18007d2ee  xor     eax, eax
0x18007d2f0  lock cmpxchg [rbx+4], r13d
0x18007d2f6  jnz     short loc_18007D2E7
0x18007d2f8  jmp     loc_18007D383
0x18007d2fd  mov     eax, edx
0x18007d2ff  and     eax, r15d
0x18007d302  cmp     eax, r15d
0x18007d305  jnz     short loc_18007D314
0x18007d307  mov     ecx, 3E8h; dwMilliseconds
0x18007d30c  call    cs:__imp_Sleep
0x18007d312  jmp     short loc_18007D2E7
0x18007d314  mov     eax, edi
0x18007d316  add     edi, r14d
0x18007d319  cmp     eax, [rbx]
0x18007d31b  jb      short loc_18007D2E7
0x18007d31d  lea     ecx, [rdx+400000h]
0x18007d323  mov     eax, edx
0x18007d325  lock cmpxchg [rbx+4], ecx
0x18007d32a  cmp     edx, eax
0x18007d32c  jnz     short loc_18007D2E7
0x18007d32e  mov     rcx, rbx; this
0x18007d331  call    ?GetWriteWaiterEvent@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetWriteWaiterEvent(void)
0x18007d336  or      edi, 0FFFFFFFFh
0x18007d339  mov     rcx, rax; hHandle
0x18007d33c  mov     edx, edi; dwMilliseconds
0x18007d33e  call    cs:__imp_WaitForSingleObject
0x18007d344  cmp     eax, edi
0x18007d346  jnz     short loc_18007D383
0x18007d348  call    cs:__imp_GetLastError
0x18007d34e  mov     edx, eax; unsigned int
0x18007d350  lea     rcx, [rbp+57h+var_60]; this
0x18007d354  lea     rax, aWaitforsingleo_0; "WaitForSingleObject failed in UTSemRead"...
0x18007d35b  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x18007d360  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x18007d365  mov     r9, [rbp+57h+var_50]; unsigned __int16 *
0x18007d369  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18007d370  mov     r8d, 1ADh; unsigned int
0x18007d376  mov     [rbp+57h+var_38], r14d
0x18007d37a  lea     rcx, [rbp+57h+var_60]; this
0x18007d37e  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18007d383  mov     eax, [rbx+4]
0x18007d386  mov     edi, 0C0021251h
0x18007d38b  mov     r15d, 15h
0x18007d391  test    eax, 3FFh
0x18007d396  jz      short loc_18007D3E0
0x18007d398  lea     r9, aProblemWithRea_0; "Problem with Reader info in UTSemReadWr"...
0x18007d39f  mov     [rbp+57h+var_60], 0
0x18007d3a6  mov     r8d, 1B8h; unsigned int
0x18007d3ac  mov     [rbp+57h+var_50], r9
0x18007d3b0  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18007d3b7  mov     [rbp+57h+var_5C], r15w
0x18007d3bc  lea     rcx, [rbp+57h+var_60]; this
0x18007d3c0  mov     [rbp+57h+var_58], edi
0x18007d3c3  mov     [rbp+57h+var_48], 0
0x18007d3cb  mov     [rbp+57h+var_40], 0
0x18007d3d3  mov     [rbp+57h+var_34], r14d
0x18007d3d7  mov     [rbp+57h+var_38], r14d
0x18007d3db  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18007d3e0  mov     eax, [rbx+4]
0x18007d3e3  and     eax, 0C00h
0x18007d3e8  cmp     eax, r13d
0x18007d3eb  jz      short loc_18007D435
0x18007d3ed  lea     r9, aProblemWithWri_2; "Problem with Writer info in UTSemReadWr"...
0x18007d3f4  mov     [rbp+57h+var_60], 0
0x18007d3fb  mov     r8d, 1BAh; unsigned int
0x18007d401  mov     [rbp+57h+var_50], r9
0x18007d405  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18007d40c  mov     [rbp+57h+var_5C], r15w
0x18007d411  lea     rcx, [rbp+57h+var_60]; this
0x18007d415  mov     [rbp+57h+var_58], edi
0x18007d418  mov     [rbp+57h+var_48], 0
0x18007d420  mov     [rbp+57h+var_40], 0
0x18007d428  mov     [rbp+57h+var_34], r14d
0x18007d42c  mov     [rbp+57h+var_38], r14d
0x18007d430  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18007d435  add     rsp, 88h
0x18007d43c  pop     r15
0x18007d43e  pop     r14
0x18007d440  pop     r13
0x18007d442  pop     rdi
0x18007d443  pop     rbx
0x18007d444  pop     rbp
0x18007d445  retn
```
