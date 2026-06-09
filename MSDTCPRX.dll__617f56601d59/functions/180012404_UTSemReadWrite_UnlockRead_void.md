# UTSemReadWrite::UnlockRead(void)

- ea: `0x180012404`
- end: `0x1800125f3`
- name: `?UnlockRead@UTSemReadWrite@@QEAAXXZ`
- size: `495`
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
- `0x18000fa40`
- `0x180012404`
- `0x18007d218`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800125a1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800125a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125ab`

## string_xrefs

- `0x18001241c`: `com\complus\src\shared\util\utsem.cpp`
- `0x180012429`: `Problem with Reader info in UTSemReadWrite::UnlockRead`
- `0x1800124f6`: `Problem with Reader info in UTSemReadWrite::UnlockRead`
- `0x1800124bb`: `Problem with WriteWatier info in UTSemReadWrite::UnlockRead`
- `0x180012534`: `Problem with WriteWatier info in UTSemReadWrite::UnlockRead`
- `0x180012587`: `Problem with WriteWatier info in UTSemReadWrite::UnlockRead`
- `0x180012480`: `Problem with Writer info in UTSemReadWrite::UnlockRead`
- `0x1800125b7`: `SetEvent failed in UTSemReadWrite:UnlockRead`

## pseudocode

```c
void __fastcall UTSemReadWrite::UnlockRead(UTSemReadWrite *this)
{
  signed __int32 v2; // edi
  bool v3; // zf
  unsigned int v4; // eax
  void *v5; // rax
  DWORD LastError; // eax
  unsigned __int16 v7; // r8
  unsigned int v8; // r9d
  const void *v9; // [rsp+28h] [rbp-58h]
  unsigned int v10; // [rsp+30h] [rbp-50h]
  int v11; // [rsp+38h] [rbp-48h]
  int v12; // [rsp+40h] [rbp-40h]
  int v13; // [rsp+50h] [rbp-30h] BYREF
  __int16 v14; // [rsp+54h] [rbp-2Ch]
  int v15; // [rsp+58h] [rbp-28h]
  unsigned __int16 *v16; // [rsp+60h] [rbp-20h]
  __int64 v17; // [rsp+68h] [rbp-18h]
  __int64 v18; // [rsp+70h] [rbp-10h]
  int v19; // [rsp+78h] [rbp-8h]
  int v20; // [rsp+7Ch] [rbp-4h]

  if ( (*((_DWORD *)this + 1) & 0x3FF) == 0 )
  {
    v16 = L"Problem with Reader info in UTSemReadWrite::UnlockRead";
    v13 = 0;
    v14 = 21;
    v15 = -1073606063;
    v17 = 0;
    v18 = 0;
    v20 = 1;
    v19 = 1;
    CError::WriteToLog(
      (CError *)&v13,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x1E2u,
      L"Problem with Reader info in UTSemReadWrite::UnlockRead");
  }
  if ( (*((_DWORD *)this + 1) & 0xC00) != 0 )
  {
    v13 = 0;
    v16 = L"Problem with Writer info in UTSemReadWrite::UnlockRead";
    v14 = 21;
    v15 = -1073606063;
    v17 = 0;
    v18 = 0;
    v20 = 1;
    v19 = 1;
    CError::WriteToLog(
      (CError *)&v13,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x1E4u,
      L"Problem with Writer info in UTSemReadWrite::UnlockRead");
  }
  do
  {
    while ( 1 )
    {
      v2 = *((_DWORD *)this + 1);
      if ( v2 != 1 )
        break;
      v3 = _InterlockedCompareExchange((volatile signed __int32 *)this + 1, 0, 1) == 1;
LABEL_9:
      if ( v3 )
        return;
    }
    v4 = *((_DWORD *)this + 1) & 0x3FF;
    if ( v4 > 1 )
    {
      v3 = v2 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 1, v2);
      goto LABEL_9;
    }
    if ( v4 != 1 )
    {
      v13 = 0;
      v14 = 21;
      v15 = -1073606063;
      v16 = L"Problem with Reader info in UTSemReadWrite::UnlockRead";
      v17 = 0;
      v18 = 0;
      v20 = 1;
      v19 = 1;
      CError::WriteToLog(
        (CError *)&v13,
        L"com\\complus\\src\\shared\\util\\utsem.cpp",
        0x1F9u,
        L"Problem with Reader info in UTSemReadWrite::UnlockRead");
    }
    if ( (v2 & 0xFFC00000) == 0 )
    {
      v16 = L"Problem with WriteWatier info in UTSemReadWrite::UnlockRead";
      v13 = 0;
      v14 = 21;
      v15 = -1073606063;
      v17 = 0;
      v18 = 0;
      v20 = 1;
      v19 = 1;
      CError::WriteToLog(
        (CError *)&v13,
        L"com\\complus\\src\\shared\\util\\utsem.cpp",
        0x1FBu,
        L"Problem with WriteWatier info in UTSemReadWrite::UnlockRead");
    }
  }
  while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 4193281, v2) );
  v5 = UTSemReadWrite::GetWriteWaiterEvent(this);
  if ( !SetEvent(v5) )
  {
    LastError = GetLastError();
    CErrorWin32::CErrorWin32(
      (CErrorWin32 *)&v13,
      LastError,
      v7,
      v8,
      L"SetEvent failed in UTSemReadWrite:UnlockRead",
      v9,
      v10,
      v11,
      v12);
    v19 = 1;
    CError::WriteToLog((CError *)&v13, L"com\\complus\\src\\shared\\util\\utsem.cpp", 0x204u, v16);
  }
}

```

## disassembly

```asm
0x180012404  push    rbp
0x180012406  push    rbx
0x180012407  push    rsi
0x180012408  push    rdi
0x180012409  push    r13
0x18001240b  push    r14
0x18001240d  push    r15
0x18001240f  mov     rbp, rsp
0x180012412  sub     rsp, 80h
0x180012419  mov     eax, [rcx+4]
0x18001241c  lea     r15, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180012423  xor     r14d, r14d
0x180012426  mov     rbx, rcx
0x180012429  lea     rcx, aProblemWithRea; "Problem with Reader info in UTSemReadWr"...
0x180012430  lea     r13d, [r14+15h]
0x180012434  lea     esi, [r14+1]
0x180012438  test    eax, 3FFh
0x18001243d  jnz     short loc_180012476
0x18001243f  mov     [rbp+var_20], rcx
0x180012443  mov     r9, rcx; unsigned __int16 *
0x180012446  lea     rcx, [rbp+var_30]; this
0x18001244a  mov     [rbp+var_30], r14d
0x18001244e  mov     r8d, 1E2h; unsigned int
0x180012454  mov     [rbp+var_2C], r13w
0x180012459  mov     rdx, r15; unsigned __int16 *
0x18001245c  mov     [rbp+var_28], 0C0021251h
0x180012463  mov     [rbp+var_18], r14
0x180012467  mov     [rbp+var_10], r14
0x18001246b  mov     [rbp+var_4], esi
0x18001246e  mov     [rbp+var_8], esi
0x180012471  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180012476  mov     eax, [rbx+4]
0x180012479  test    eax, 0C00h
0x18001247e  jz      short loc_1800124BB
0x180012480  lea     r9, aProblemWithWri; "Problem with Writer info in UTSemReadWr"...
0x180012487  mov     [rbp+var_30], r14d
0x18001248b  mov     r8d, 1E4h; unsigned int
0x180012491  mov     [rbp+var_20], r9
0x180012495  mov     rdx, r15; unsigned __int16 *
0x180012498  mov     [rbp+var_2C], r13w
0x18001249d  lea     rcx, [rbp+var_30]; this
0x1800124a1  mov     [rbp+var_28], 0C0021251h
0x1800124a8  mov     [rbp+var_18], r14
0x1800124ac  mov     [rbp+var_10], r14
0x1800124b0  mov     [rbp+var_4], esi
0x1800124b3  mov     [rbp+var_8], esi
0x1800124b6  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800124bb  lea     rcx, aProblemWithWri_1; "Problem with WriteWatier info in UTSemR"...
0x1800124c2  mov     edi, [rbx+4]
0x1800124c5  cmp     edi, esi
0x1800124c7  jnz     short loc_1800124D5
0x1800124c9  mov     ecx, r14d
0x1800124cc  mov     eax, esi
0x1800124ce  lock cmpxchg [rbx+4], ecx
0x1800124d3  jmp     short loc_1800124EC
0x1800124d5  mov     eax, edi
0x1800124d7  and     eax, 3FFh
0x1800124dc  cmp     eax, esi
0x1800124de  jbe     short loc_1800124F4
0x1800124e0  lea     ecx, [rdi-1]
0x1800124e3  mov     eax, edi
0x1800124e5  lock cmpxchg [rbx+4], ecx
0x1800124ea  cmp     edi, eax
0x1800124ec  jz      loc_1800125E1
0x1800124f2  jmp     short loc_1800124BB
0x1800124f4  jz      short loc_18001253B
0x1800124f6  lea     rax, aProblemWithRea; "Problem with Reader info in UTSemReadWr"...
0x1800124fd  mov     [rbp+var_30], r14d
0x180012501  mov     r9, rax; unsigned __int16 *
0x180012504  mov     [rbp+var_2C], r13w
0x180012509  mov     r8d, 1F9h; unsigned int
0x18001250f  mov     [rbp+var_28], 0C0021251h
0x180012516  mov     rdx, r15; unsigned __int16 *
0x180012519  mov     [rbp+var_20], rax
0x18001251d  lea     rcx, [rbp+var_30]; this
0x180012521  mov     [rbp+var_18], r14
0x180012525  mov     [rbp+var_10], r14
0x180012529  mov     [rbp+var_4], esi
0x18001252c  mov     [rbp+var_8], esi
0x18001252f  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180012534  lea     rcx, aProblemWithWri_1; "Problem with WriteWatier info in UTSemR"...
0x18001253b  test    edi, 0FFC00000h
0x180012541  jnz     short loc_18001257A
0x180012543  mov     [rbp+var_20], rcx
0x180012547  mov     r9, rcx; unsigned __int16 *
0x18001254a  lea     rcx, [rbp+var_30]; this
0x18001254e  mov     [rbp+var_30], r14d
0x180012552  mov     r8d, 1FBh; unsigned int
0x180012558  mov     [rbp+var_2C], r13w
0x18001255d  mov     rdx, r15; unsigned __int16 *
0x180012560  mov     [rbp+var_28], 0C0021251h
0x180012567  mov     [rbp+var_18], r14
0x18001256b  mov     [rbp+var_10], r14
0x18001256f  mov     [rbp+var_4], esi
0x180012572  mov     [rbp+var_8], esi
0x180012575  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18001257a  lea     ecx, [rdi-3FFC01h]
0x180012580  mov     eax, edi
0x180012582  lock cmpxchg [rbx+4], ecx
0x180012587  lea     rcx, aProblemWithWri_1; "Problem with WriteWatier info in UTSemR"...
0x18001258e  cmp     edi, eax
0x180012590  jnz     loc_1800124C2
0x180012596  mov     rcx, rbx; this
0x180012599  call    ?GetWriteWaiterEvent@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetWriteWaiterEvent(void)
0x18001259e  mov     rcx, rax; hEvent
0x1800125a1  call    cs:__imp_SetEvent
0x1800125a7  test    eax, eax
0x1800125a9  jnz     short loc_1800125E1
0x1800125ab  call    cs:__imp_GetLastError
0x1800125b1  mov     edx, eax; unsigned int
0x1800125b3  lea     rcx, [rbp+var_30]; this
0x1800125b7  lea     rax, aSeteventFailed; "SetEvent failed in UTSemReadWrite:Unloc"...
0x1800125be  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800125c3  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x1800125c8  mov     r9, [rbp+var_20]; unsigned __int16 *
0x1800125cc  lea     rcx, [rbp+var_30]; this
0x1800125d0  mov     r8d, 204h; unsigned int
0x1800125d6  mov     [rbp+var_8], esi
0x1800125d9  mov     rdx, r15; unsigned __int16 *
0x1800125dc  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800125e1  add     rsp, 80h
0x1800125e8  pop     r15
0x1800125ea  pop     r14
0x1800125ec  pop     r13
0x1800125ee  pop     rdi
0x1800125ef  pop     rsi
0x1800125f0  pop     rbx
0x1800125f1  pop     rbp
0x1800125f2  retn
```
