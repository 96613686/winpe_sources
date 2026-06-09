# BdeCfgpCheckVolumeFileSystemAndSpace(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,int,unsigned __int64 *)

- ea: `0x180005284`
- end: `0x18000556f`
- name: `?BdeCfgpCheckVolumeFileSystemAndSpace@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@HPEA_K@Z`
- size: `747`
- prototype: `__int64 __fastcall(struct IVdsVolume *, unsigned __int64, struct _BDECFG_SIZE_REQUIREMENTS *const, int, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180002460`
- `0x1800050b8`

## callees

- `0x180004210`
- `0x1800042a0`
- `0x180005284`
- `0x180006860`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005530`
- `ole32!CoTaskMemFree` at `0x180005547`
- `ole32!CoTaskMemFree` at `0x180005530`
- `ole32!CoTaskMemFree` at `0x180005547`

## pseudocode

```c
__int64 __fastcall BdeCfgpCheckVolumeFileSystemAndSpace(
        struct IVdsVolume *a1,
        unsigned __int64 a2,
        struct _BDECFG_SIZE_REQUIREMENTS *const a3,
        int a4,
        unsigned __int64 *a5)
{
  struct IVdsVolumeVtbl *lpVtbl; // rax
  int MaxShrinkSize; // ebx
  int NtfsVolumeSize; // eax
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // rdx
  double v16; // xmm0_8
  __int64 v17; // rcx
  double v18; // xmm0_8
  double v19; // xmm1_8
  __int64 v20; // rax
  double v21; // xmm0_8
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rax
  DWORD v24; // ecx
  unsigned __int64 v25; // [rsp+20h] [rbp-91h] BYREF
  unsigned __int64 v26; // [rsp+28h] [rbp-89h] BYREF
  unsigned __int64 v27; // [rsp+30h] [rbp-81h] BYREF
  unsigned __int64 *v28; // [rsp+38h] [rbp-79h]
  _VDS_FILE_SYSTEM_PROP v29; // [rsp+40h] [rbp-71h] BYREF
  _BYTE v30[56]; // [rsp+78h] [rbp-39h] BYREF

  v28 = a5;
  memset(v30, 0, sizeof(v30));
  v27 = 0;
  v25 = 0;
  v26 = 0;
  memset(&v29, 0, sizeof(v29));
  if ( !g_pService )
    return 3231711254LL;
  if ( !a1 || !a3 && a2 )
  {
    MaxShrinkSize = -2147467261;
    goto LABEL_44;
  }
  lpVtbl = a1->lpVtbl;
  memset(v30, 0, sizeof(v30));
  MaxShrinkSize = ((__int64 (__fastcall *)(struct IVdsVolume *, _BYTE *))lpVtbl->GetProperties)(a1, v30);
  if ( MaxShrinkSize >= 0 )
  {
    if ( *(_DWORD *)&v30[16] != 10 || *(_QWORD *)&v30[20] != 0x100000001LL )
    {
      MaxShrinkSize = -1063256055;
      goto LABEL_44;
    }
    NtfsVolumeSize = BdeCfgGetNtfsVolumeSize(a1, &v26, &v27, &v29);
    MaxShrinkSize = NtfsVolumeSize;
    if ( NtfsVolumeSize < 0 )
    {
      if ( NtfsVolumeSize == -1063256056 )
        BdeCfgpLogFailedTarget(0x40A00042u, a1);
      goto LABEL_44;
    }
    if ( a2 )
    {
      v13 = v26;
      if ( v26 < a2 )
      {
        BdeCfgpLogFailedTarget(0x40A00039u, a1);
        MaxShrinkSize = -(a4 != 0) - 1063256032;
        goto LABEL_44;
      }
      v14 = v27;
      if ( v27 < a2 )
      {
LABEL_16:
        BdeCfgpLogFailedTarget(0x40A0003Au, a1);
        MaxShrinkSize = -1063256016;
        goto LABEL_44;
      }
      if ( a4 )
      {
        MaxShrinkSize = BdeCfgGetMaxShrinkSize(a1, &v25);
        if ( MaxShrinkSize < 0 )
          goto LABEL_44;
        v15 = v25;
        if ( v25 < a2 )
        {
          BdeCfgpLogFailedTarget(0x40A0003Bu, a1);
          MaxShrinkSize = -1063256046;
          goto LABEL_44;
        }
        if ( (v13 & 0x8000000000000000uLL) != 0LL )
          v16 = (double)(int)(v13 & 1 | (v13 >> 1)) + (double)(int)(v13 & 1 | (v13 >> 1));
        else
          v16 = (double)(int)v13;
        v17 = *((_QWORD *)a3 + 2);
        v18 = v16 * *((double *)a3 + 1);
        if ( v17 < 0 )
        {
          v20 = *((_QWORD *)a3 + 2) & 1LL | (*((_QWORD *)a3 + 2) >> 1);
          v19 = (double)(int)v20 + (double)(int)v20;
        }
        else
        {
          v19 = (double)(int)v17;
        }
        v21 = fmax(v18, v19);
        v22 = 0;
        if ( v21 >= 9.223372036854776e18 )
        {
          v21 = v21 - 9.223372036854776e18;
          if ( v21 < 9.223372036854776e18 )
            v22 = 0x8000000000000000uLL;
        }
        v23 = v22 + (unsigned int)(int)v21;
        goto LABEL_39;
      }
      if ( v26 >= *(_QWORD *)a3 - *((_QWORD *)a3 + 3) )
      {
        if ( v29.ulAllocationUnitSize <= 0x1000 )
        {
          if ( (v29.ulFlags & 1) == 0 )
          {
            v15 = v25;
            v23 = 0;
LABEL_39:
            if ( v14 - a2 >= v23 )
            {
              if ( v28 )
                *v28 = v15;
              goto LABEL_44;
            }
            goto LABEL_16;
          }
          v24 = 1084227644;
        }
        else
        {
          v24 = 1084227640;
        }
      }
      else
      {
        v24 = 1084227641;
      }
      BdeCfgpLogFailedTarget(v24, a1);
      MaxShrinkSize = -1063256032;
    }
  }
LABEL_44:
  if ( *(_QWORD *)&v30[48] )
  {
    CoTaskMemFree(*(LPVOID *)&v30[48]);
    *(_QWORD *)&v30[48] = 0;
  }
  if ( v29.pwszLabel )
    CoTaskMemFree(v29.pwszLabel);
  return (unsigned int)MaxShrinkSize;
}

```

## disassembly

```asm
0x180005284  push    rbp
0x180005286  push    rbx
0x180005287  push    rsi
0x180005288  push    rdi
0x180005289  push    r12
0x18000528b  push    r13
0x18000528d  push    r14
0x18000528f  push    r15
0x180005291  lea     rbp, [rsp-17h]
0x180005296  sub     rsp, 0C8h
0x18000529d  mov     rax, cs:__security_cookie
0x1800052a4  xor     rax, rsp
0x1800052a7  mov     [rbp+4Fh+var_50], rax
0x1800052ab  mov     rax, [rbp+4Fh+arg_20]
0x1800052af  xorps   xmm0, xmm0
0x1800052b2  mov     [rbp+4Fh+var_C8], rax
0x1800052b6  mov     r13d, r9d
0x1800052b9  xor     eax, eax
0x1800052bb  mov     dword ptr [rbp+4Fh+var_88], 0
0x1800052c2  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, rax; IVdsService * g_pService
0x1800052c9  mov     r15, r8
0x1800052cc  mov     r14, rdx
0x1800052cf  mov     [rbp+4Fh+var_54], eax
0x1800052d2  mov     rdi, rcx
0x1800052d5  mov     [rsp+100h+var_D0], rax
0x1800052da  movups  [rbp+4Fh+var_88+4], xmm0
0x1800052de  mov     [rsp+100h+var_E0], rax
0x1800052e3  movups  [rbp+4Fh+var_74], xmm0
0x1800052e7  mov     [rsp+100h+var_D8], rax
0x1800052ec  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x1800052f0  mov     [rbp+4Fh+var_C0.pwszLabel], rax
0x1800052f4  movups  xmmword ptr [rbp+4Fh+var_C0.type], xmm0
0x1800052f8  movups  xmmword ptr [rbp+4Fh+var_C0.volumeId.Data4+4], xmm0
0x1800052fc  movups  xmmword ptr [rbp+4Fh+var_C0.ullAvailableAllocationUnits], xmm0
0x180005300  jnz     short loc_18000530C
0x180005302  mov     eax, 0C0A00016h
0x180005307  jmp     loc_18000554F
0x18000530c  test    rdi, rdi
0x18000530f  jz      loc_180005522
0x180005315  test    r15, r15
0x180005318  jnz     short loc_180005323
0x18000531a  test    r14, r14
0x18000531d  jnz     loc_180005522
0x180005323  mov     [rbp+4Fh+pv+0Ch], rax
0x180005327  lea     rdx, [rbp+4Fh+var_88]
0x18000532b  mov     rax, [rcx]
0x18000532e  movups  [rbp+4Fh+var_88], xmm0
0x180005332  movups  xmmword ptr [rbp-29h], xmm0
0x180005336  mov     rax, [rax+18h]
0x18000533a  movups  [rbp+4Fh+var_74+0Ch], xmm0
0x18000533e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005343  mov     ebx, eax
0x180005345  test    eax, eax
0x180005347  js      loc_180005527
0x18000534d  cmp     [rbp+4Fh+var_78], 0Ah
0x180005351  jnz     loc_18000551B
0x180005357  cmp     dword ptr [rbp+4Fh+var_74], 1
0x18000535b  jnz     loc_18000551B
0x180005361  cmp     dword ptr [rbp+4Fh+var_74+4], 1
0x180005365  jnz     loc_18000551B
0x18000536b  lea     r9, [rbp+4Fh+var_C0]; struct _VDS_FILE_SYSTEM_PROP *
0x18000536f  mov     rcx, rdi; struct IVdsVolume *
0x180005372  lea     r8, [rsp+100h+var_D0]; unsigned __int64 *
0x180005377  lea     rdx, [rsp+100h+var_D8]; unsigned __int64 *
0x18000537c  call    ?BdeCfgGetNtfsVolumeSize@@YAJPEAUIVdsVolume@@PEA_K1PEAU_VDS_FILE_SYSTEM_PROP@@@Z; BdeCfgGetNtfsVolumeSize(IVdsVolume *,unsigned __int64 *,unsigned __int64 *,_VDS_FILE_SYSTEM_PROP *)
0x180005381  mov     ebx, eax
0x180005383  test    eax, eax
0x180005385  jns     short loc_1800053A4
0x180005387  cmp     eax, 0C0A00008h
0x18000538c  jnz     loc_180005527
0x180005392  mov     rdx, rdi; struct IVdsVolume *
0x180005395  mov     ecx, 40A00042h; dwMessageId
0x18000539a  call    ?BdeCfgpLogFailedTarget@@YAJJPEAUIVdsVolume@@@Z; BdeCfgpLogFailedTarget(long,IVdsVolume *)
0x18000539f  jmp     loc_180005527
0x1800053a4  test    r14, r14
0x1800053a7  jz      loc_180005527
0x1800053ad  mov     rsi, [rsp+100h+var_D8]
0x1800053b2  cmp     rsi, r14
0x1800053b5  jnb     short loc_1800053D4
0x1800053b7  mov     rdx, rdi; struct IVdsVolume *
0x1800053ba  mov     ecx, 40A00039h; dwMessageId
0x1800053bf  call    ?BdeCfgpLogFailedTarget@@YAJJPEAUIVdsVolume@@@Z; BdeCfgpLogFailedTarget(long,IVdsVolume *)
0x1800053c4  neg     r13d
0x1800053c7  sbb     ebx, ebx
0x1800053c9  add     ebx, 0C0A00020h
0x1800053cf  jmp     loc_180005527
0x1800053d4  mov     r12, [rsp+100h+var_D0]
0x1800053d9  cmp     r12, r14
0x1800053dc  jnb     short loc_1800053F5
0x1800053de  mov     rdx, rdi; struct IVdsVolume *
0x1800053e1  mov     ecx, 40A0003Ah; dwMessageId
0x1800053e6  call    ?BdeCfgpLogFailedTarget@@YAJJPEAUIVdsVolume@@@Z; BdeCfgpLogFailedTarget(long,IVdsVolume *)
0x1800053eb  mov     ebx, 0C0A00030h
0x1800053f0  jmp     loc_180005527
0x1800053f5  test    r13d, r13d
0x1800053f8  jz      loc_1800054BD
0x1800053fe  lea     rdx, [rsp+100h+var_E0]; unsigned __int64 *
0x180005403  mov     rcx, rdi; struct IVdsVolume *
0x180005406  call    ?BdeCfgGetMaxShrinkSize@@YAJPEAUIVdsVolume@@PEA_K@Z; BdeCfgGetMaxShrinkSize(IVdsVolume *,unsigned __int64 *)
0x18000540b  mov     ebx, eax
0x18000540d  test    eax, eax
0x18000540f  js      loc_180005527
0x180005415  mov     rdx, [rsp+100h+var_E0]
0x18000541a  cmp     rdx, r14
0x18000541d  jnb     short loc_180005436
0x18000541f  mov     rdx, rdi; struct IVdsVolume *
0x180005422  mov     ecx, 40A0003Bh; dwMessageId
0x180005427  call    ?BdeCfgpLogFailedTarget@@YAJJPEAUIVdsVolume@@@Z; BdeCfgpLogFailedTarget(long,IVdsVolume *)
0x18000542c  mov     ebx, 0C0A00012h
0x180005431  jmp     loc_180005527
0x180005436  xorps   xmm0, xmm0
0x180005439  test    rsi, rsi
0x18000543c  js      short loc_180005445
0x18000543e  cvtsi2sd xmm0, rsi
0x180005443  jmp     short loc_18000545A
0x180005445  mov     rax, rsi
0x180005448  and     esi, 1
0x18000544b  shr     rax, 1
0x18000544e  or      rax, rsi
0x180005451  cvtsi2sd xmm0, rax
0x180005456  addsd   xmm0, xmm0
0x18000545a  mov     rcx, [r15+10h]
0x18000545e  xorps   xmm1, xmm1
0x180005461  mulsd   xmm0, qword ptr [r15+8]
0x180005467  test    rcx, rcx
0x18000546a  js      short loc_180005473
0x18000546c  cvtsi2sd xmm1, rcx
0x180005471  jmp     short loc_180005488
0x180005473  mov     rax, rcx
0x180005476  and     ecx, 1
0x180005479  shr     rax, 1
0x18000547c  or      rax, rcx
0x18000547f  cvtsi2sd xmm1, rax
0x180005484  addsd   xmm1, xmm1
0x180005488  maxsd   xmm0, xmm1
0x18000548c  xor     ecx, ecx
0x18000548e  movsd   xmm1, cs:__real@43e0000000000000
0x180005496  comisd  xmm0, xmm1
0x18000549a  jb      short loc_1800054B3
0x18000549c  subsd   xmm0, xmm1
0x1800054a0  comisd  xmm0, xmm1
0x1800054a4  jnb     short loc_1800054B3
0x1800054a6  mov     rax, 8000000000000000h
0x1800054b0  mov     rcx, rax
0x1800054b3  cvttsd2si rax, xmm0
0x1800054b8  add     rax, rcx
0x1800054bb  jmp     short loc_180005501
0x1800054bd  mov     rax, [r15]
0x1800054c0  sub     rax, [r15+18h]
0x1800054c4  cmp     rsi, rax
0x1800054c7  jnb     short loc_1800054DD
0x1800054c9  mov     ecx, 40A00039h; dwMessageId
0x1800054ce  mov     rdx, rdi; struct IVdsVolume *
0x1800054d1  call    ?BdeCfgpLogFailedTarget@@YAJJPEAUIVdsVolume@@@Z; BdeCfgpLogFailedTarget(long,IVdsVolume *)
0x1800054d6  mov     ebx, 0C0A00020h
0x1800054db  jmp     short loc_180005527
0x1800054dd  cmp     [rbp+4Fh+var_C0.ulAllocationUnitSize], 1000h
0x1800054e4  jbe     short loc_1800054ED
0x1800054e6  mov     ecx, 40A00038h
0x1800054eb  jmp     short loc_1800054CE
0x1800054ed  test    byte ptr [rbp+4Fh+var_C0.ulFlags], 1
0x1800054f1  jz      short loc_1800054FA
0x1800054f3  mov     ecx, 40A0003Ch
0x1800054f8  jmp     short loc_1800054CE
0x1800054fa  mov     rdx, [rsp+100h+var_E0]
0x1800054ff  xor     eax, eax
0x180005501  sub     r12, r14
0x180005504  cmp     r12, rax
0x180005507  jb      loc_1800053DE
0x18000550d  mov     rax, [rbp+4Fh+var_C8]
0x180005511  test    rax, rax
0x180005514  jz      short loc_180005527
0x180005516  mov     [rax], rdx
0x180005519  jmp     short loc_180005527
0x18000551b  mov     ebx, 0C0A00009h
0x180005520  jmp     short loc_180005527
0x180005522  mov     ebx, 80004003h
0x180005527  mov     rcx, [rbp+4Fh+pv+0Ch]; pv
0x18000552b  test    rcx, rcx
0x18000552e  jz      short loc_18000553E
0x180005530  call    cs:__imp_CoTaskMemFree
0x180005536  mov     [rbp+4Fh+pv+0Ch], 0
0x18000553e  mov     rcx, [rbp+4Fh+var_C0.pwszLabel]; pv
0x180005542  test    rcx, rcx
0x180005545  jz      short loc_18000554D
0x180005547  call    cs:__imp_CoTaskMemFree
0x18000554d  mov     eax, ebx
0x18000554f  mov     rcx, [rbp+4Fh+var_50]
0x180005553  xor     rcx, rsp; StackCookie
0x180005556  call    __security_check_cookie
0x18000555b  add     rsp, 0C8h
0x180005562  pop     r15
0x180005564  pop     r14
0x180005566  pop     r13
0x180005568  pop     r12
0x18000556a  pop     rdi
0x18000556b  pop     rsi
0x18000556c  pop     rbx
0x18000556d  pop     rbp
0x18000556e  retn
```
