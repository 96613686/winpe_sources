# UpdateReserveManager::DetermineReserveSize(unsigned __int64,unsigned __int64,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180014854`
- end: `0x180014957`
- name: `?DetermineReserveSize@UpdateReserveManager@@AEAAJ_K0PEA_K1@Z`
- size: `259`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this, unsigned __int64, unsigned __int64, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180019634`

## callees

- `0x18000fafc`
- `0x180014854`
- `0x180015ad0`

## string_xrefs

- `0x1800148b0`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014918`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800148c2`: `UpdateReserveManager::DetermineReserveSize`
- `0x180014923`: `UpdateReserveManager::DetermineReserveSize`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::DetermineReserveSize(
        UpdateReserveManager *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5)
{
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  const char *v10; // rax
  unsigned __int64 v11; // rax
  const char *v12; // [rsp+20h] [rbp-20h] BYREF
  const char *v13; // [rsp+28h] [rbp-18h]
  __int64 v14; // [rsp+30h] [rbp-10h]
  const char *v15; // [rsp+38h] [rbp-8h]

  result = UpdateReserveManager::EnsureNotInSafeMode(this);
  if ( (int)result >= 0 )
  {
    if ( a2 >= a3 )
    {
      *a5 = a3;
      return 0;
    }
    v9 = a3 - a2;
    if ( *a4 <= a3 - a2 )
    {
      v11 = a2 + *a4;
      if ( v11 >= a2 )
      {
        *a5 = v11;
        *a4 = 0;
        return 0;
      }
      *a5 = -1;
      v12 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v13 = "UpdateReserveManager::DetermineReserveSize";
      v10 = "::ULongLongAdd(UsedSpaceInReserve, *FreeSpaceRemaining, ReserveSize)";
      v14 = 2644;
    }
    else
    {
      *a5 = a3;
      if ( *a4 >= v9 )
      {
        *a4 -= v9;
        return 0;
      }
      *a4 = -1;
      v12 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v13 = "UpdateReserveManager::DetermineReserveSize";
      v10 = "::ULongLongSub(*FreeSpaceRemaining, SpaceNeeded, FreeSpaceRemaining)";
      v14 = 2640;
    }
    v15 = v10;
    RtlReportErrorOrigination(&v12, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942934LL);
    return 2147942934LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014854  mov     [rsp-18h+arg_0], rbx
0x180014859  mov     [rsp-18h+arg_8], rsi
0x18001485e  push    rbp
0x18001485f  push    rdi
0x180014860  push    r14
0x180014862  mov     rbp, rsp
0x180014865  sub     rsp, 40h
0x180014869  mov     rsi, [rbp+arg_20]
0x18001486d  mov     rbx, r9
0x180014870  mov     rdi, r8
0x180014873  mov     r14, rdx
0x180014876  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001487b  test    eax, eax
0x18001487d  js      loc_180014944
0x180014883  cmp     r14, rdi
0x180014886  jnb     loc_18001493F
0x18001488c  mov     rax, [rbx]
0x18001488f  mov     rcx, rdi
0x180014892  sub     rcx, r14
0x180014895  cmp     rax, rcx
0x180014898  jbe     short loc_1800148FD
0x18001489a  mov     [rsi], rdi
0x18001489d  mov     rax, [rbx]
0x1800148a0  cmp     rax, rcx
0x1800148a3  jb      short loc_1800148B0
0x1800148a5  sub     rax, rcx
0x1800148a8  mov     [rbx], rax
0x1800148ab  jmp     loc_180014942
0x1800148b0  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800148b7  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800148be  mov     [rbp+var_20], rax
0x1800148c2  lea     rax, aUpdatereservem_46; "UpdateReserveManager::DetermineReserveS"...
0x1800148c9  mov     [rbp+var_18], rax
0x1800148cd  lea     rax, aUlonglongsubFr_0; "::ULongLongSub(*FreeSpaceRemaining, Spa"...
0x1800148d4  mov     [rbp+var_10], 0A50h
0x1800148dc  mov     r8d, 80070216h
0x1800148e2  mov     [rbp+var_8], rax
0x1800148e6  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800148ed  lea     rcx, [rbp+var_20]
0x1800148f1  call    RtlReportErrorOrigination
0x1800148f6  mov     eax, 80070216h
0x1800148fb  jmp     short loc_180014944
0x1800148fd  add     rax, r14
0x180014900  cmp     rax, r14
0x180014903  jb      short loc_180014911
0x180014905  mov     [rsi], rax
0x180014908  mov     qword ptr [rbx], 0
0x18001490f  jmp     short loc_180014942
0x180014911  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180014918  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001491f  mov     [rbp+var_20], rax
0x180014923  lea     rax, aUpdatereservem_46; "UpdateReserveManager::DetermineReserveS"...
0x18001492a  mov     [rbp+var_18], rax
0x18001492e  lea     rax, aUlonglongaddUs; "::ULongLongAdd(UsedSpaceInReserve, *Fre"...
0x180014935  mov     [rbp+var_10], 0A54h
0x18001493d  jmp     short loc_1800148DC
0x18001493f  mov     [rsi], rdi
0x180014942  xor     eax, eax
0x180014944  mov     rbx, [rsp+40h+arg_0]
0x180014949  mov     rsi, [rsp+40h+arg_8]
0x18001494e  add     rsp, 40h
0x180014952  pop     r14
0x180014954  pop     rdi
0x180014955  pop     rbp
0x180014956  retn
```
