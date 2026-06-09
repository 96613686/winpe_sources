# UpdateReserveManager::ReturnSpaceToUser(UpdateReserveManager::ReturnSpaceToUserFlags,unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18001ee88`
- end: `0x18001eff5`
- name: `?ReturnSpaceToUser@UpdateReserveManager@@AEAAJW4ReturnSpaceToUserFlags@1@_KPEA_K2222@Z`
- size: `365`
- prototype: `__int64 __fastcall(UpdateReserveManager *, char, unsigned __int64, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180019634`

## callees

- `0x18000fafc`
- `0x180015ad0`
- `0x18001ee88`

## string_xrefs

- `0x18001ef59`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001ef99`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001ef6c`: `UpdateReserveManager::ReturnSpaceToUser`
- `0x18001efac`: `UpdateReserveManager::ReturnSpaceToUser`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::ReturnSpaceToUser(
        UpdateReserveManager *a1,
        char a2,
        unsigned __int64 a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7,
        unsigned __int64 *a8)
{
  __int64 result; // rax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  const char *v21; // rax
  const char *v22; // [rsp+20h] [rbp-28h] BYREF
  const char *v23; // [rsp+28h] [rbp-20h]
  __int64 v24; // [rsp+30h] [rbp-18h]
  const char *v25; // [rsp+38h] [rbp-10h]

  result = UpdateReserveManager::EnsureNotInSafeMode(a1);
  if ( (int)result >= 0 )
  {
    v12 = *a8;
    v13 = *a5;
    if ( *a5 >= *a8 )
    {
      *a5 = v13 - v12;
LABEL_4:
      *a8 = 0;
      return 0;
    }
    *a8 = v12 - v13;
    *a5 = 0;
    v14 = *a8;
    v15 = *a7;
    if ( *a7 >= *a8 )
    {
      *a7 = v15 - v14;
      goto LABEL_4;
    }
    *a8 = v14 - v15;
    *a7 = 0;
    v16 = *a8;
    v17 = *a6;
    if ( *a6 >= *a8 )
    {
      *a6 = v17 - v16;
      goto LABEL_4;
    }
    *a8 = v16 - v17;
    *a6 = 0;
    if ( (a2 & 1) != 0 )
    {
      v18 = *a4;
      v19 = (*a4 - a3) & -(__int64)(a3 < *a4);
    }
    else
    {
      v19 = *a4;
      v18 = *a4;
    }
    v20 = *a8;
    if ( v19 < *a8 )
    {
      *a8 = v20 - v19;
      if ( *a4 >= v19 )
      {
        *a4 -= v19;
        return 0;
      }
      v24 = 2615;
      v22 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v23 = "UpdateReserveManager::ReturnSpaceToUser";
      v21 = "::ULongLongSub(*pUsedSpaceInHardTowardsTarget, StealableHardReserveTowardsTarget, pUsedSpaceInHardTowardsTarget)";
    }
    else
    {
      if ( v18 >= v20 )
      {
        *a4 = v18 - v20;
        goto LABEL_4;
      }
      v24 = 2608;
      v22 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v23 = "UpdateReserveManager::ReturnSpaceToUser";
      v21 = "::ULongLongSub(*pUsedSpaceInHardTowardsTarget, *pSpaceToReturn, pUsedSpaceInHardTowardsTarget)";
    }
    *a4 = -1;
    v25 = v21;
    RtlReportErrorOrigination(&v22, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942934LL);
    return 2147942934LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001ee88  push    rbp
0x18001ee8a  push    rbx
0x18001ee8b  push    rsi
0x18001ee8c  push    rdi
0x18001ee8d  push    r12
0x18001ee8f  push    r13
0x18001ee91  push    r14
0x18001ee93  push    r15
0x18001ee95  mov     rbp, rsp
0x18001ee98  sub     rsp, 48h
0x18001ee9c  mov     rsi, [rbp+arg_20]
0x18001eea0  mov     rdi, r9
0x18001eea3  mov     r14, [rbp+arg_28]
0x18001eea7  mov     r12, r8
0x18001eeaa  mov     r15, [rbp+arg_30]
0x18001eeae  mov     r13d, edx
0x18001eeb1  mov     rbx, [rbp+arg_38]
0x18001eeb8  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001eebd  xor     r8d, r8d
0x18001eec0  test    eax, eax
0x18001eec2  js      loc_18001EFE4
0x18001eec8  mov     rcx, [rbx]
0x18001eecb  mov     rax, [rsi]
0x18001eece  cmp     rax, rcx
0x18001eed1  jb      short loc_18001EEE3
0x18001eed3  sub     rax, rcx
0x18001eed6  mov     [rsi], rax
0x18001eed9  mov     [rbx], r8
0x18001eedc  xor     eax, eax
0x18001eede  jmp     loc_18001EFE4
0x18001eee3  sub     rcx, rax
0x18001eee6  mov     [rbx], rcx
0x18001eee9  mov     [rsi], r8
0x18001eeec  mov     rcx, [rbx]
0x18001eeef  mov     rax, [r15]
0x18001eef2  cmp     rax, rcx
0x18001eef5  jb      short loc_18001EEFF
0x18001eef7  sub     rax, rcx
0x18001eefa  mov     [r15], rax
0x18001eefd  jmp     short loc_18001EED9
0x18001eeff  sub     rcx, rax
0x18001ef02  mov     [rbx], rcx
0x18001ef05  mov     [r15], r8
0x18001ef08  mov     rcx, [rbx]
0x18001ef0b  mov     rax, [r14]
0x18001ef0e  cmp     rax, rcx
0x18001ef11  jb      short loc_18001EF1B
0x18001ef13  sub     rax, rcx
0x18001ef16  mov     [r14], rax
0x18001ef19  jmp     short loc_18001EED9
0x18001ef1b  sub     rcx, rax
0x18001ef1e  mov     [rbx], rcx
0x18001ef21  mov     [r14], r8
0x18001ef24  test    r13b, 1
0x18001ef28  jz      short loc_18001EF3E
0x18001ef2a  mov     rdx, [rdi]
0x18001ef2d  mov     rax, rdx
0x18001ef30  sub     rax, r12
0x18001ef33  cmp     r12, rdx
0x18001ef36  sbb     rcx, rcx
0x18001ef39  and     rcx, rax
0x18001ef3c  jmp     short loc_18001EF44
0x18001ef3e  mov     rcx, [rdi]
0x18001ef41  mov     rdx, rcx
0x18001ef44  mov     rax, [rbx]
0x18001ef47  cmp     rcx, rax
0x18001ef4a  jb      short loc_18001EF80
0x18001ef4c  cmp     rdx, rax
0x18001ef4f  jb      short loc_18001EF59
0x18001ef51  sub     rdx, rax
0x18001ef54  mov     [rdi], rdx
0x18001ef57  jmp     short loc_18001EED9
0x18001ef59  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001ef60  mov     [rbp+var_18], 0A30h
0x18001ef68  mov     [rbp+var_28], rax
0x18001ef6c  lea     rax, aUpdatereservem_4; "UpdateReserveManager::ReturnSpaceToUser"
0x18001ef73  mov     [rbp+var_20], rax
0x18001ef77  lea     rax, aUlonglongsubPu; "::ULongLongSub(*pUsedSpaceInHardTowards"...
0x18001ef7e  jmp     short loc_18001EFBE
0x18001ef80  sub     rax, rcx
0x18001ef83  mov     [rbx], rax
0x18001ef86  mov     rax, [rdi]
0x18001ef89  cmp     rax, rcx
0x18001ef8c  jb      short loc_18001EF99
0x18001ef8e  sub     rax, rcx
0x18001ef91  mov     [rdi], rax
0x18001ef94  jmp     loc_18001EEDC
0x18001ef99  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001efa0  mov     [rbp+var_18], 0A37h
0x18001efa8  mov     [rbp+var_28], rax
0x18001efac  lea     rax, aUpdatereservem_4; "UpdateReserveManager::ReturnSpaceToUser"
0x18001efb3  mov     [rbp+var_20], rax
0x18001efb7  lea     rax, aUlonglongsubPu_0; "::ULongLongSub(*pUsedSpaceInHardTowards"...
0x18001efbe  mov     r8d, 80070216h
0x18001efc4  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001efcb  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001efd2  mov     [rbp+var_10], rax
0x18001efd6  lea     rcx, [rbp+var_28]
0x18001efda  call    RtlReportErrorOrigination
0x18001efdf  mov     eax, 80070216h
0x18001efe4  add     rsp, 48h
0x18001efe8  pop     r15
0x18001efea  pop     r14
0x18001efec  pop     r13
0x18001efee  pop     r12
0x18001eff0  pop     rdi
0x18001eff1  pop     rsi
0x18001eff2  pop     rbx
0x18001eff3  pop     rbp
0x18001eff4  retn
```
