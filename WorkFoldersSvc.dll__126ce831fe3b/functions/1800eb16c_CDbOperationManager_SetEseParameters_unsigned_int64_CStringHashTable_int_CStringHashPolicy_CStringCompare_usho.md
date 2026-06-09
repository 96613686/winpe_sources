# CDbOperationManager::SetEseParameters(unsigned __int64 *,CStringHashTable<int,CStringHashPolicy,CStringCompare> &,ushort const *)

- ea: `0x1800eb16c`
- end: `0x1800eb415`
- name: `?SetEseParameters@CDbOperationManager@@CAJPEA_KAEAV?$CStringHashTable@HVCStringHashPolicy@@VCStringCompare@@@@PEBG@Z`
- size: `681`
- prototype: `__int64 __fastcall(JET_INSTANCE *pinstance)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800eaeec`
- `0x1800eb080`

## callees

- `0x180002ab0`
- `0x18001137c`
- `0x18002db48`
- `0x1800e8538`
- `0x1800eb16c`
- `0x1800eb41c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x1800eb2e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x1800eb2e3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eb2c8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eb2ec`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eb2c8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eb2ec`
- `KERNEL32!CompareStringOrdinal` at `0x1800eb228`
- `KERNEL32!CompareStringOrdinal` at `0x1800eb250`
- `KERNEL32!CompareStringOrdinal` at `0x1800eb228`
- `KERNEL32!CompareStringOrdinal` at `0x1800eb250`

## pseudocode

```c
__int64 __fastcall CDbOperationManager::SetEseParameters(JET_INSTANCE *pinstance, __int64 a2, unsigned __int16 *a3)
{
  int v6; // edi
  int v7; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  JET_API_PTR v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned __int16 *v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 **v19; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *EndPtr; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t String[28]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String1[88]; // [rsp+80h] [rbp-80h] BYREF

  if ( !a3 )
    return 0;
  v18 = a3;
  v19 = &v18;
  v6 = 0;
  v7 = 0;
  while ( *v18 )
  {
    v7 = lambda_7c696190340494de8a5eec35b4d80fad_::operator()(&v19, String1, 81);
    if ( v7 < 0 )
      break;
    if ( *v18++ )
    {
      v7 = lambda_7c696190340494de8a5eec35b4d80fad_::operator()(&v19, String, 21);
      v11 = *v18++;
      if ( (_WORD)v11 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 100;
LABEL_37:
          WPP_SF_S(v16[2], v17, &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids, String1);
        }
        return (unsigned int)-2147024809;
      }
      *(_DWORD *)_o__errno(v11, v9, v10) = 0;
      EndPtr = 0;
      v12 = _wcstoi64(String, &EndPtr, 0);
      if ( *(_DWORD *)_o__errno(v14, v13, v15) || *EndPtr || EndPtr == String )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            99,
            (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
            (unsigned int)String,
            (__int64)String1);
        goto LABEL_14;
      }
      if ( !v6 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 98;
          goto LABEL_37;
        }
        return (unsigned int)-2147024809;
      }
      if ( v6 == 1 && !*pinstance || v6 == 2 && *pinstance )
        v7 = CDbOperationManager::SetEseParametersHelper(pinstance, a2, String1, v12);
LABEL_23:
      if ( v7 < 0 )
        return (unsigned int)v7;
    }
    else if ( CompareStringOrdinal(String1, -1, L"[GLOBAL]", -1, 0) == 2 )
    {
      v6 = 1;
    }
    else
    {
      if ( CompareStringOrdinal(String1, -1, L"[INSTANCE]", -1, 0) != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids, String1);
LABEL_14:
        v7 = -2147024809;
        goto LABEL_23;
      }
      v6 = 2;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800eb16c  mov     [rsp-8+arg_10], rbx
0x1800eb171  mov     [rsp-8+arg_18], rsi
0x1800eb176  push    rbp
0x1800eb177  push    rdi
0x1800eb178  push    r12
0x1800eb17a  push    r14
0x1800eb17c  push    r15
0x1800eb17e  lea     rbp, [rsp-40h]
0x1800eb183  sub     rsp, 140h
0x1800eb18a  mov     rax, cs:__security_cookie
0x1800eb191  xor     rax, rsp
0x1800eb194  mov     [rbp+60h+var_30], rax
0x1800eb198  xor     r12d, r12d
0x1800eb19b  mov     r15, rdx
0x1800eb19e  mov     rsi, rcx
0x1800eb1a1  test    r8, r8
0x1800eb1a4  jnz     short loc_1800EB1AD
0x1800eb1a6  xor     eax, eax
0x1800eb1a8  jmp     loc_1800EB3ED
0x1800eb1ad  lea     rax, [rsp+160h+var_130]
0x1800eb1b2  mov     [rsp+160h+var_130], r8
0x1800eb1b7  mov     [rsp+160h+var_128], rax
0x1800eb1bc  lea     r14, WPP_GLOBAL_Control
0x1800eb1c3  mov     edi, r12d
0x1800eb1c6  mov     ebx, r12d
0x1800eb1c9  mov     rax, [rsp+160h+var_130]
0x1800eb1ce  cmp     [rax], r12w
0x1800eb1d2  jz      loc_1800EB3EB
0x1800eb1d8  mov     r8d, 51h ; 'Q'
0x1800eb1de  lea     rdx, [rbp+60h+String1]
0x1800eb1e2  lea     rcx, [rsp+160h+var_128]
0x1800eb1e7  call    _lambda_7c696190340494de8a5eec35b4d80fad___operator__
0x1800eb1ec  mov     ebx, eax
0x1800eb1ee  test    eax, eax
0x1800eb1f0  js      loc_1800EB3EB
0x1800eb1f6  mov     rcx, [rsp+160h+var_130]
0x1800eb1fb  movzx   edx, word ptr [rcx]
0x1800eb1fe  add     rcx, 2
0x1800eb202  mov     [rsp+160h+var_130], rcx
0x1800eb207  test    dx, dx
0x1800eb20a  jnz     loc_1800EB297
0x1800eb210  or      eax, 0FFFFFFFFh
0x1800eb213  mov     [rsp+160h+bIgnoreCase], r12d; bIgnoreCase
0x1800eb218  mov     r9d, eax; cchCount2
0x1800eb21b  lea     r8, aGlobal_0; "[GLOBAL]"
0x1800eb222  mov     edx, eax; cchCount1
0x1800eb224  lea     rcx, [rbp+60h+String1]; lpString1
0x1800eb228  call    cs:__imp_CompareStringOrdinal
0x1800eb22e  cmp     eax, 2
0x1800eb231  jnz     short loc_1800EB238
0x1800eb233  lea     edi, [rax-1]
0x1800eb236  jmp     short loc_1800EB1C9
0x1800eb238  or      eax, 0FFFFFFFFh
0x1800eb23b  mov     [rsp+160h+bIgnoreCase], r12d; bIgnoreCase
0x1800eb240  mov     r9d, eax; cchCount2
0x1800eb243  lea     r8, aInstance_1; "[INSTANCE]"
0x1800eb24a  mov     edx, eax; cchCount1
0x1800eb24c  lea     rcx, [rbp+60h+String1]; lpString1
0x1800eb250  call    cs:__imp_CompareStringOrdinal
0x1800eb256  cmp     eax, 2
0x1800eb259  jnz     short loc_1800EB262
0x1800eb25b  mov     edi, eax
0x1800eb25d  jmp     loc_1800EB1C9
0x1800eb262  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb269  cmp     rcx, r14
0x1800eb26c  jz      short loc_1800EB28D
0x1800eb26e  test    byte ptr [rcx+1Ch], 1
0x1800eb272  jz      short loc_1800EB28D
0x1800eb274  mov     rcx, [rcx+10h]
0x1800eb278  lea     r9, [rbp+60h+String1]
0x1800eb27c  mov     edx, 61h ; 'a'
0x1800eb281  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800eb288  call    WPP_SF_S
0x1800eb28d  mov     ebx, 80070057h
0x1800eb292  jmp     loc_1800EB339
0x1800eb297  mov     r8d, 15h
0x1800eb29d  lea     rdx, [rsp+160h+String]
0x1800eb2a2  lea     rcx, [rsp+160h+var_128]
0x1800eb2a7  call    _lambda_7c696190340494de8a5eec35b4d80fad___operator__
0x1800eb2ac  mov     ebx, eax
0x1800eb2ae  mov     rax, [rsp+160h+var_130]
0x1800eb2b3  movzx   ecx, word ptr [rax]
0x1800eb2b6  add     rax, 2
0x1800eb2ba  mov     [rsp+160h+var_130], rax
0x1800eb2bf  test    cx, cx
0x1800eb2c2  jnz     loc_1800EB3BB
0x1800eb2c8  call    cs:__imp__o__errno
0x1800eb2ce  xor     r8d, r8d; Radix
0x1800eb2d1  lea     rdx, [rsp+160h+EndPtr]; EndPtr
0x1800eb2d6  lea     rcx, [rsp+160h+String]; String
0x1800eb2db  mov     [rax], r12d
0x1800eb2de  mov     [rsp+160h+EndPtr], r12
0x1800eb2e3  call    cs:__imp__wcstoi64
0x1800eb2e9  mov     r14, rax
0x1800eb2ec  call    cs:__imp__o__errno
0x1800eb2f2  cmp     [rax], r12d
0x1800eb2f5  jnz     short loc_1800EB352
0x1800eb2f7  mov     rcx, [rsp+160h+EndPtr]
0x1800eb2fc  cmp     [rcx], r12w
0x1800eb300  jnz     short loc_1800EB352
0x1800eb302  lea     rax, [rsp+160h+String]
0x1800eb307  cmp     rcx, rax
0x1800eb30a  jz      short loc_1800EB352
0x1800eb30c  test    edi, edi
0x1800eb30e  jz      loc_1800EB39B
0x1800eb314  cmp     edi, 1
0x1800eb317  jnz     short loc_1800EB346
0x1800eb319  cmp     [rsi], r12
0x1800eb31c  jnz     short loc_1800EB346
0x1800eb31e  mov     r9, r14
0x1800eb321  lea     r8, [rbp+60h+String1]
0x1800eb325  mov     rdx, r15
0x1800eb328  mov     rcx, rsi; pinstance
0x1800eb32b  call    ?SetEseParametersHelper@CDbOperationManager@@CAJPEA_KAEAV?$CStringHashTable@HVCStringHashPolicy@@VCStringCompare@@@@PEBG_K@Z; CDbOperationManager::SetEseParametersHelper(unsigned __int64 *,CStringHashTable<int,CStringHashPolicy,CStringCompare> &,ushort const *,unsigned __int64)
0x1800eb330  mov     ebx, eax
0x1800eb332  lea     r14, WPP_GLOBAL_Control
0x1800eb339  test    ebx, ebx
0x1800eb33b  jns     loc_1800EB1C9
0x1800eb341  jmp     loc_1800EB3EB
0x1800eb346  cmp     edi, 2
0x1800eb349  jnz     short loc_1800EB332
0x1800eb34b  cmp     [rsi], r12
0x1800eb34e  jz      short loc_1800EB332
0x1800eb350  jmp     short loc_1800EB31E
0x1800eb352  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb359  lea     r14, WPP_GLOBAL_Control
0x1800eb360  cmp     rcx, r14
0x1800eb363  jz      loc_1800EB28D
0x1800eb369  test    byte ptr [rcx+1Ch], 1
0x1800eb36d  jz      loc_1800EB28D
0x1800eb373  mov     rcx, [rcx+10h]
0x1800eb377  lea     rax, [rbp+60h+String1]
0x1800eb37b  mov     edx, 63h ; 'c'
0x1800eb380  mov     qword ptr [rsp+160h+bIgnoreCase], rax
0x1800eb385  lea     r9, [rsp+160h+String]
0x1800eb38a  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800eb391  call    WPP_SF_SS
0x1800eb396  jmp     loc_1800EB28D
0x1800eb39b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb3a2  lea     rax, WPP_GLOBAL_Control
0x1800eb3a9  cmp     rcx, rax
0x1800eb3ac  jz      short loc_1800EB3E6
0x1800eb3ae  test    byte ptr [rcx+1Ch], 1
0x1800eb3b2  jz      short loc_1800EB3E6
0x1800eb3b4  mov     edx, 62h ; 'b'
0x1800eb3b9  jmp     short loc_1800EB3D2
0x1800eb3bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb3c2  cmp     rcx, r14
0x1800eb3c5  jz      short loc_1800EB3E6
0x1800eb3c7  test    byte ptr [rcx+1Ch], 1
0x1800eb3cb  jz      short loc_1800EB3E6
0x1800eb3cd  mov     edx, 64h ; 'd'
0x1800eb3d2  mov     rcx, [rcx+10h]
0x1800eb3d6  lea     r9, [rbp+60h+String1]
0x1800eb3da  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800eb3e1  call    WPP_SF_S
0x1800eb3e6  mov     ebx, 80070057h
0x1800eb3eb  mov     eax, ebx
0x1800eb3ed  mov     rcx, [rbp+60h+var_30]
0x1800eb3f1  xor     rcx, rsp; StackCookie
0x1800eb3f4  call    __security_check_cookie
0x1800eb3f9  lea     r11, [rsp+160h+var_20]
0x1800eb401  mov     rbx, [r11+40h]
0x1800eb405  mov     rsi, [r11+48h]
0x1800eb409  mov     rsp, r11
0x1800eb40c  pop     r15
0x1800eb40e  pop     r14
0x1800eb410  pop     r12
0x1800eb412  pop     rdi
0x1800eb413  pop     rbp
0x1800eb414  retn
```
