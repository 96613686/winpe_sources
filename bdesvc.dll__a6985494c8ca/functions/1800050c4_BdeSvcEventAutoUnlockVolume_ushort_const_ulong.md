# BdeSvcEventAutoUnlockVolume(ushort const *,ulong)

- ea: `0x1800050c4`
- end: `0x18000536b`
- name: `?BdeSvcEventAutoUnlockVolume@@YAJPEBGK@Z`
- size: `679`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002d020`

## callees

- `0x1800050c4`
- `0x180006260`
- `0x180009f30`
- `0x180009f60`
- `0x18000f7e0`
- `0x180034070`
- `0x180047b90`

## import_xrefs

- `FVEAPI!FveAttemptAutoUnlock` at `0x180005299`
- `FVEAPI!FveAttemptAutoUnlock` at `0x180005299`
- `FVEAPI!FveSetAllowKeyExport` at `0x1800051ff`
- `FVEAPI!FveSetAllowKeyExport` at `0x1800051ff`
- `FVEAPI!FveOpenVolumeW` at `0x18000524e`
- `FVEAPI!FveOpenVolumeW` at `0x18000524e`
- `FVEAPI!FveCloseVolume` at `0x180005319`
- `FVEAPI!FveCloseVolume` at `0x180005319`

## pseudocode

```c
__int64 __fastcall BdeSvcEventAutoUnlockVolume(const unsigned __int16 *a1, __int16 a2)
{
  PVOID *v4; // rcx
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // eax
  int v10; // edx
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v12 = -1;
  if ( !a1 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
    {
      WPP_SF_(v4[2], 67, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v5 = -2147024809;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
    {
      v6 = 68;
LABEL_11:
      WPP_SF_d(v4[2], v6, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v5);
LABEL_44:
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_45;
    }
    goto LABEL_45;
  }
  if ( (a2 & 0x800) != 0 )
  {
    v5 = TryAutoUnlockVolumeWithSid(a1, 1);
    if ( v5 >= 0 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_45;
      v7 = 71;
      goto LABEL_43;
    }
    v8 = FveSetAllowKeyExport(1);
    v5 = v8;
    if ( v8 < 0 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
          (unsigned int)v8);
        goto LABEL_44;
      }
      goto LABEL_45;
    }
    v9 = FveOpenVolumeW(a1, 0, &v12);
    v5 = v9;
    if ( v9 >= 0 )
    {
      v9 = FveAttemptAutoUnlock(v12);
      v5 = v9;
      if ( v9 >= 0 )
      {
        if ( !v9 )
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_45;
          v7 = 76;
LABEL_43:
          WPP_SF_S(v4[2], v7, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, a1);
          goto LABEL_44;
        }
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_45;
        v10 = 75;
      }
      else
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_45;
        v10 = 74;
      }
    }
    else
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_45;
      v10 = 73;
    }
    WPP_SF_SD((unsigned int)v4[2], v10, (unsigned int)&WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (_DWORD)a1, v9);
    goto LABEL_44;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
  {
    WPP_SF_S(v4[2], 69, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, a1);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = 1;
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
  {
    v6 = 70;
    goto LABEL_11;
  }
LABEL_45:
  if ( v12 != -1 )
  {
    FveCloseVolume(v12);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v12 = -1;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_(v4[2], 77, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800050c4  push    rbx
0x1800050c6  push    rbp
0x1800050c7  push    rsi
0x1800050c8  push    r14
0x1800050ca  sub     rsp, 48h
0x1800050ce  mov     rax, cs:__security_cookie
0x1800050d5  xor     rax, rsp
0x1800050d8  mov     [rsp+68h+var_30], rax
0x1800050dd  mov     ebx, edx
0x1800050df  mov     rsi, rcx
0x1800050e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050e9  lea     rbp, WPP_GLOBAL_Control
0x1800050f0  lea     r14, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x1800050f7  cmp     rcx, rbp
0x1800050fa  jz      short loc_18000511A
0x1800050fc  test    byte ptr [rcx+1Ch], 20h
0x180005100  jz      short loc_18000511A
0x180005102  mov     rcx, [rcx+10h]
0x180005106  mov     edx, 42h ; 'B'
0x18000510b  mov     r8, r14
0x18000510e  call    WPP_SF_
0x180005113  mov     rcx, cs:WPP_GLOBAL_Control
0x18000511a  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x180005123  test    rsi, rsi
0x180005126  jnz     short loc_18000517A
0x180005128  cmp     rcx, rbp
0x18000512b  jz      short loc_180005149
0x18000512d  test    byte ptr [rcx+1Ch], 2
0x180005131  jz      short loc_180005149
0x180005133  mov     rcx, [rcx+10h]
0x180005137  lea     edx, [rsi+43h]
0x18000513a  mov     r8, r14
0x18000513d  call    WPP_SF_
0x180005142  mov     rcx, cs:WPP_GLOBAL_Control
0x180005149  mov     ebx, 80070057h
0x18000514e  cmp     rcx, rbp
0x180005151  jz      loc_18000530C
0x180005157  test    byte ptr [rcx+1Ch], 40h
0x18000515b  jz      loc_18000530C
0x180005161  mov     edx, 44h ; 'D'
0x180005166  mov     rcx, [rcx+10h]
0x18000516a  mov     r9d, ebx
0x18000516d  mov     r8, r14
0x180005170  call    WPP_SF_d
0x180005175  jmp     loc_180005305
0x18000517a  bt      ebx, 0Bh
0x18000517e  jb      short loc_1800051C3
0x180005180  cmp     rcx, rbp
0x180005183  jz      short loc_1800051A6
0x180005185  test    byte ptr [rcx+1Ch], 8
0x180005189  jz      short loc_1800051A6
0x18000518b  mov     rcx, [rcx+10h]
0x18000518f  mov     edx, 45h ; 'E'
0x180005194  mov     r9, rsi
0x180005197  mov     r8, r14
0x18000519a  call    WPP_SF_S
0x18000519f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051a6  mov     ebx, 1
0x1800051ab  cmp     rcx, rbp
0x1800051ae  jz      loc_18000530C
0x1800051b4  test    byte ptr [rcx+1Ch], 40h
0x1800051b8  jz      loc_18000530C
0x1800051be  lea     edx, [rbx+45h]
0x1800051c1  jmp     short loc_180005166
0x1800051c3  mov     edx, 1
0x1800051c8  mov     rcx, rsi
0x1800051cb  call    ?TryAutoUnlockVolumeWithSid@@YAJPEBGW4FveSidUnlockContext@@@Z; TryAutoUnlockVolumeWithSid(ushort const *,FveSidUnlockContext)
0x1800051d0  mov     ebx, eax
0x1800051d2  test    eax, eax
0x1800051d4  js      short loc_1800051FA
0x1800051d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051dd  cmp     rcx, rbp
0x1800051e0  jz      loc_18000530C
0x1800051e6  test    byte ptr [rcx+1Ch], 8
0x1800051ea  jz      loc_18000530C
0x1800051f0  mov     edx, 47h ; 'G'
0x1800051f5  jmp     loc_1800052F6
0x1800051fa  mov     ecx, 1
0x1800051ff  call    cs:__imp_FveSetAllowKeyExport
0x180005206  nop     dword ptr [rax+rax+00h]
0x18000520b  mov     ebx, eax
0x18000520d  test    eax, eax
0x18000520f  jns     short loc_180005244
0x180005211  mov     rcx, cs:WPP_GLOBAL_Control
0x180005218  cmp     rcx, rbp
0x18000521b  jz      loc_18000530C
0x180005221  test    byte ptr [rcx+1Ch], 2
0x180005225  jz      loc_18000530C
0x18000522b  mov     rcx, [rcx+10h]
0x18000522f  mov     edx, 48h ; 'H'
0x180005234  mov     r9d, eax
0x180005237  mov     r8, r14
0x18000523a  call    WPP_SF_d
0x18000523f  jmp     loc_180005305
0x180005244  lea     r8, [rsp+68h+var_38]
0x180005249  xor     edx, edx
0x18000524b  mov     rcx, rsi
0x18000524e  call    cs:__imp_FveOpenVolumeW
0x180005255  nop     dword ptr [rax+rax+00h]
0x18000525a  mov     ebx, eax
0x18000525c  test    eax, eax
0x18000525e  jns     short loc_180005294
0x180005260  mov     rcx, cs:WPP_GLOBAL_Control
0x180005267  cmp     rcx, rbp
0x18000526a  jz      loc_18000530C
0x180005270  test    byte ptr [rcx+1Ch], 2
0x180005274  jz      loc_18000530C
0x18000527a  mov     edx, 49h ; 'I'
0x18000527f  mov     rcx, [rcx+10h]
0x180005283  mov     r9, rsi
0x180005286  mov     r8, r14
0x180005289  mov     [rsp+68h+var_48], eax
0x18000528d  call    WPP_SF_SD
0x180005292  jmp     short loc_180005305
0x180005294  mov     rcx, [rsp+68h+var_38]
0x180005299  call    cs:__imp_FveAttemptAutoUnlock
0x1800052a0  nop     dword ptr [rax+rax+00h]
0x1800052a5  mov     ebx, eax
0x1800052a7  test    eax, eax
0x1800052a9  jns     short loc_1800052C4
0x1800052ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052b2  cmp     rcx, rbp
0x1800052b5  jz      short loc_18000530C
0x1800052b7  test    byte ptr [rcx+1Ch], 2
0x1800052bb  jz      short loc_18000530C
0x1800052bd  mov     edx, 4Ah ; 'J'
0x1800052c2  jmp     short loc_18000527F
0x1800052c4  jz      short loc_1800052DF
0x1800052c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052cd  cmp     rcx, rbp
0x1800052d0  jz      short loc_18000530C
0x1800052d2  test    byte ptr [rcx+1Ch], 8
0x1800052d6  jz      short loc_18000530C
0x1800052d8  mov     edx, 4Bh ; 'K'
0x1800052dd  jmp     short loc_18000527F
0x1800052df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052e6  cmp     rcx, rbp
0x1800052e9  jz      short loc_18000530C
0x1800052eb  test    byte ptr [rcx+1Ch], 8
0x1800052ef  jz      short loc_18000530C
0x1800052f1  mov     edx, 4Ch ; 'L'
0x1800052f6  mov     rcx, [rcx+10h]
0x1800052fa  mov     r9, rsi
0x1800052fd  mov     r8, r14
0x180005300  call    WPP_SF_S
0x180005305  mov     rcx, cs:WPP_GLOBAL_Control
0x18000530c  cmp     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x180005312  jz      short loc_180005335
0x180005314  mov     rcx, [rsp+68h+var_38]
0x180005319  call    cs:__imp_FveCloseVolume
0x180005320  nop     dword ptr [rax+rax+00h]
0x180005325  mov     rcx, cs:WPP_GLOBAL_Control
0x18000532c  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x180005335  cmp     rcx, rbp
0x180005338  jz      short loc_180005351
0x18000533a  test    byte ptr [rcx+1Ch], 20h
0x18000533e  jz      short loc_180005351
0x180005340  mov     rcx, [rcx+10h]
0x180005344  mov     edx, 4Dh ; 'M'
0x180005349  mov     r8, r14
0x18000534c  call    WPP_SF_
0x180005351  mov     eax, ebx
0x180005353  mov     rcx, [rsp+68h+var_30]
0x180005358  xor     rcx, rsp; StackCookie
0x18000535b  call    __security_check_cookie
0x180005360  add     rsp, 48h
0x180005364  pop     r14
0x180005366  pop     rsi
0x180005367  pop     rbp
0x180005368  pop     rbx
0x180005369  retn
```
