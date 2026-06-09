# CDriveConfiguration::Thread_ConfigureDrive(void)

- ea: `0x1800101a0`
- end: `0x1800107f5`
- name: `?Thread_ConfigureDrive@CDriveConfiguration@@AEAAJXZ`
- size: `1621`
- prototype: `__int64 __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18000f890`

## callees

- `0x18000202c`
- `0x180002d24`
- `0x180003390`
- `0x180004170`
- `0x180004410`
- `0x180004dfc`
- `0x180005ce8`
- `0x180006a48`
- `0x180007070`
- `0x180007bd0`
- `0x180007ec8`
- `0x18000e300`
- `0x18000e7c4`
- `0x18000eb40`
- `0x18000ed1c`
- `0x18000f360`
- `0x180010120`
- `0x1800101a0`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800102c9`
- `KERNEL32!EnterCriticalSection` at `0x18001049c`
- `KERNEL32!EnterCriticalSection` at `0x1800102c9`
- `KERNEL32!EnterCriticalSection` at `0x18001049c`
- `KERNEL32!LeaveCriticalSection` at `0x1800102f2`
- `KERNEL32!LeaveCriticalSection` at `0x1800104c0`
- `KERNEL32!LeaveCriticalSection` at `0x1800102f2`
- `KERNEL32!LeaveCriticalSection` at `0x1800104c0`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::Thread_ConfigureDrive(CDriveConfiguration *this)
{
  int FirstVolume; // edi
  struct IVdsVolume *v3; // r14
  __int64 v4; // rdx
  unsigned __int16 *v5; // r12
  const unsigned __int16 *v6; // rbx
  _WORD *v7; // r15
  __int64 v8; // r14
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  unsigned __int16 v14; // r8
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // rdx
  struct IVdsVolume *v20; // [rsp+28h] [rbp-2D0h] BYREF
  int v21; // [rsp+30h] [rbp-2C8h] BYREF
  struct IVdsDisk *v22; // [rsp+38h] [rbp-2C0h] BYREF
  struct IVdsVolume *v23; // [rsp+40h] [rbp-2B8h] BYREF
  struct IVdsVolume *v24; // [rsp+48h] [rbp-2B0h] BYREF
  unsigned __int64 v25; // [rsp+50h] [rbp-2A8h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-2A0h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-298h]
  __int64 v28; // [rsp+68h] [rbp-290h]
  _WORD *v29; // [rsp+70h] [rbp-288h]
  __int64 v30; // [rsp+78h] [rbp-280h]
  __int64 v31; // [rsp+80h] [rbp-278h]
  CDriveConfiguration *v32; // [rsp+88h] [rbp-270h]
  _OWORD v33[2]; // [rsp+90h] [rbp-268h] BYREF
  unsigned __int16 v34[264]; // [rsp+B0h] [rbp-248h] BYREF

  v32 = this;
  v21 = 0;
  memset(v33, 0, sizeof(v33));
  v25 = 0;
  v26 = 0;
  v22 = 0;
  v23 = 0;
  v20 = 0;
  v24 = 0;
  memset_0(v34, 0, 0x208u);
  *((_DWORD *)this + 2) = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 157) + 16LL))(*((_QWORD *)this + 157), 0, 0);
  if ( *((_DWORD *)this + 16) == 1 )
  {
    CDriveConfiguration::SetConfigurationStep(this, 0);
    FirstVolume = BdeCfgpFindFirstVolume(BdeCfgpFilterVolumesByName, (unsigned __int64)this + 600, &v23);
    if ( FirstVolume == 1 )
      FirstVolume = -1063256034;
    if ( FirstVolume < 0 )
      goto LABEL_52;
    v3 = v23;
    FirstVolume = BdeCfgFindBasicVolumeExtent(v23, &v25, &v26);
    if ( FirstVolume < 0 )
      goto LABEL_52;
    if ( *((_BYTE *)this + 12) )
      goto LABEL_52;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    FirstVolume = BdeCfgpShrinkSimpleVolumeCancellable(v3, *((_QWORD *)this + 145), (struct IVdsAsync **)this + 159);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( FirstVolume < 0 )
      goto LABEL_52;
    FirstVolume = (*(__int64 (__fastcall **)(_QWORD, int *, _OWORD *))(**((_QWORD **)this + 159) + 32LL))(
                    *((_QWORD *)this + 159),
                    &v21,
                    v33);
    if ( FirstVolume < 0 )
      goto LABEL_52;
    if ( *((_BYTE *)this + 12) )
      goto LABEL_52;
    FirstVolume = v21;
    if ( v21 < 0 )
      goto LABEL_52;
    v4 = *((_QWORD *)&v33[0] + 1);
    v25 += v26 - *((_QWORD *)&v33[0] + 1);
    *((_QWORD *)this + 74) = v25;
    *((_QWORD *)this + 75) = v4;
    v5 = (unsigned __int16 *)((char *)this + 608);
    *((_WORD *)this + 304) = *((_WORD *)this + 584);
  }
  else
  {
    v5 = (unsigned __int16 *)((char *)this + 608);
  }
  v6 = (const unsigned __int16 *)((char *)this + 68);
  FirstVolume = BdeCfgpFindFirstVolume(BdeCfgpFilterVolumesByName, (unsigned __int64)this + 68, &v24);
  if ( FirstVolume == 1 )
    FirstVolume = -1063256034;
  if ( FirstVolume < 0 )
  {
LABEL_52:
    v10 = 3;
    goto LABEL_53;
  }
  if ( ((*((_DWORD *)this + 16) - 1) & 0xFFFFFFFD) != 0 )
  {
    v7 = (_WORD *)((char *)this + 600);
    v8 = 260;
LABEL_37:
    if ( *((_DWORD *)this + 16) )
    {
      CDriveConfiguration::SetConfigurationStep(this, 2);
      if ( *((_DWORD *)this + 16) == 2 )
      {
        v11 = 2147483646;
        v31 = 2147483646;
        v29 = v7;
        v30 = 260;
        v12 = v34;
        v27 = v34;
        FirstVolume = 0;
        v13 = 0;
        v28 = 0;
        while ( v8 )
        {
          if ( !v11 )
            goto LABEL_46;
          v14 = *v7;
          if ( !*v7 )
            goto LABEL_46;
          v29 = ++v7;
          *v12++ = v14;
          v27 = v12;
          v30 = --v8;
          v31 = --v11;
          v28 = ++v13;
        }
        v27 = --v12;
        v28 = v13 - 1;
        FirstVolume = -2147024774;
LABEL_46:
        *v12 = 0;
      }
      if ( FirstVolume < 0 )
        goto LABEL_52;
      if ( *((_BYTE *)this + 12) )
        goto LABEL_52;
      FirstVolume = BdeCfgMigrateBootHive(v6, v34, ((*((_DWORD *)this + 16) - 1) & 0xFFFFFFFD) != 0);
      if ( FirstVolume < 0 )
        goto LABEL_52;
      BdeCfgCleanupOldBootFiles(v6);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 157) + 16LL))(*((_QWORD *)this + 157), 2);
    BdeCfgLogStatus(v15);
    goto LABEL_52;
  }
  CDriveConfiguration::SetConfigurationStep(this, 1);
  CQueryCancelAutoPlay::RegisterForCancel(*v5, (unsigned int *)this + 316);
  FirstVolume = BdeCfgGetVolumeDisk(v24, &v22);
  if ( FirstVolume < 0 )
    goto LABEL_52;
  if ( *((_BYTE *)this + 12) )
    goto LABEL_52;
  v7 = (_WORD *)((char *)this + 600);
  FirstVolume = BdeCfgCreatePrimaryPartition(v22, *((_QWORD *)this + 74), *((_QWORD *)this + 75), &v20);
  if ( FirstVolume < 0 )
    goto LABEL_52;
  if ( *((_BYTE *)this + 12) )
    goto LABEL_52;
  v8 = 260;
  FirstVolume = BdeCfgGetDeviceNameFromVolume(v20, 0x104u, v34);
  if ( FirstVolume < 0 )
    goto LABEL_52;
  if ( *((_BYTE *)this + 12) )
    goto LABEL_52;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  FirstVolume = BdeCfgSecureFormatVolume(v20, (struct IBdeCfgAsync **)this + 160);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( FirstVolume < 0 )
    goto LABEL_52;
  if ( *((_BYTE *)this + 12) )
    goto LABEL_52;
  FirstVolume = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 160) + 24LL))(
                  *((_QWORD *)this + 160),
                  &v21);
  if ( FirstVolume < 0 )
    goto LABEL_52;
  if ( *((_BYTE *)this + 12) )
    goto LABEL_52;
  FirstVolume = v21;
  if ( v21 < 0 )
    goto LABEL_52;
  FirstVolume = BdeCfgSetVolumeDacl(v34, v9);
  if ( FirstVolume >= 0 )
  {
    if ( *((_BYTE *)this + 12) )
      goto LABEL_52;
    if ( *v5 )
      FirstVolume = BdeCfgAssignLetterToVolume(v20, *v5);
    if ( FirstVolume < 0 || *((_BYTE *)this + 12) )
      goto LABEL_52;
    v6 = (const unsigned __int16 *)((char *)this + 68);
    goto LABEL_37;
  }
  v10 = 3;
  BdeCfgLogError(3, 1084227653);
LABEL_53:
  if ( *((_BYTE *)this + 12) && ((*((_DWORD *)this + 16) - 1) & 0xFFFFFFFD) == 0 && v20 )
    ((void (__fastcall *)(struct IVdsVolume *, __int64))v20->lpVtbl->Delete)(v20, 1);
  if ( v20 )
  {
    ((void (__fastcall *)(struct IVdsVolume *))v20->lpVtbl->Release)(v20);
    v20 = 0;
  }
  if ( v23 )
    ((void (__fastcall *)(struct IVdsVolume *))v23->lpVtbl->Release)(v23);
  if ( v22 )
  {
    ((void (__fastcall *)(struct IVdsDisk *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( v24 )
    ((void (__fastcall *)(struct IVdsVolume *))v24->lpVtbl->Release)(v24);
  CDriveConfiguration::Cleanup(this);
  if ( *((_BYTE *)this + 12) )
  {
    BdeCfgLogWarning(0xC0A00011);
    *((_DWORD *)this + 2) = -1063256047;
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 157) + 16LL))(*((_QWORD *)this + 157), 2);
    FirstVolume = 1;
  }
  if ( FirstVolume < 0 )
  {
    *((_DWORD *)this + 2) = FirstVolume;
    v16 = *((_DWORD *)this + 4);
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = (unsigned int)FirstVolume;
        if ( v17 == 1 )
          v10 = 4;
        else
          v10 = 0;
        goto LABEL_75;
      }
    }
    else
    {
      v10 = 2;
    }
    v18 = (unsigned int)FirstVolume;
LABEL_75:
    BdeCfgLogError(v10, v18);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 157) + 8LL))(
      *((_QWORD *)this + 157),
      (unsigned int)FirstVolume);
  }
  return (unsigned int)FirstVolume;
}

```

## disassembly

```asm
0x1800101a0  mov     [rsp+arg_8], rbx
0x1800101a5  mov     [rsp+arg_10], rsi
0x1800101aa  push    rdi
0x1800101ab  push    r12
0x1800101ad  push    r13
0x1800101af  push    r14
0x1800101b1  push    r15
0x1800101b3  sub     rsp, 2D0h
0x1800101ba  mov     rax, cs:__security_cookie
0x1800101c1  xor     rax, rsp
0x1800101c4  mov     [rsp+2F8h+var_38], rax
0x1800101cc  mov     rsi, rcx
0x1800101cf  mov     [rsp+2F8h+var_270], rcx
0x1800101d7  xor     r14d, r14d
0x1800101da  mov     [rsp+2F8h+var_2D8], r14d
0x1800101df  mov     [rsp+2F8h+var_2C8], r14d
0x1800101e4  xorps   xmm0, xmm0
0x1800101e7  movups  [rsp+2F8h+var_268], xmm0
0x1800101ef  movups  [rsp+2F8h+var_258], xmm0
0x1800101f7  mov     [rsp+2F8h+var_2A8], r14
0x1800101fc  mov     [rsp+2F8h+var_2A0], r14
0x180010201  mov     [rsp+2F8h+var_2C0], r14
0x180010206  mov     [rsp+2F8h+var_2B8], r14
0x18001020b  mov     [rsp+2F8h+var_2D0], r14
0x180010210  mov     [rsp+2F8h+var_2B0], r14
0x180010215  xor     edx, edx; Val
0x180010217  mov     r8d, 208h; Size
0x18001021d  lea     rcx, [rsp+2F8h+var_248]; void *
0x180010225  call    memset_0
0x18001022a  nop
0x18001022b  mov     [rsi+8], r14d
0x18001022f  mov     rcx, [rsi+4E8h]
0x180010236  mov     rax, [rcx]
0x180010239  xor     r8d, r8d
0x18001023c  xor     edx, edx
0x18001023e  mov     rax, [rax+10h]
0x180010242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010247  cmp     dword ptr [rsi+40h], 1
0x18001024b  jnz     loc_180010386
0x180010251  xor     edx, edx
0x180010253  mov     rcx, rsi
0x180010256  call    ?SetConfigurationStep@CDriveConfiguration@@AEAAJW4_BDECFG_STEP_ID@@@Z; CDriveConfiguration::SetConfigurationStep(_BDECFG_STEP_ID)
0x18001025b  lea     r12, [rsi+258h]
0x180010262  lea     r8, [rsp+2F8h+var_2B8]; struct IVdsVolume **
0x180010267  mov     rdx, r12; unsigned __int64
0x18001026a  lea     rcx, ?BdeCfgpFilterVolumesByName@@YAHPEAUIVdsVolume@@_K@Z; int (*)(struct IVdsVolume *, unsigned __int64)
0x180010271  call    ?BdeCfgpFindFirstVolume@@YAJP6AHPEAUIVdsVolume@@_K@Z1PEAPEAU1@@Z; BdeCfgpFindFirstVolume(int (*)(IVdsVolume *,unsigned __int64),unsigned __int64,IVdsVolume * *)
0x180010276  mov     edi, eax
0x180010278  mov     [rsp+2F8h+var_2D8], eax
0x18001027c  mov     r13d, 0C0A0001Eh
0x180010282  cmp     eax, 1
0x180010285  cmovz   edi, r13d
0x180010289  mov     [rsp+2F8h+var_2D8], edi
0x18001028d  test    edi, edi
0x18001028f  js      loc_1800106A3
0x180010295  lea     r8, [rsp+2F8h+var_2A0]; unsigned __int64 *
0x18001029a  lea     rdx, [rsp+2F8h+var_2A8]; unsigned __int64 *
0x18001029f  mov     r14, [rsp+2F8h+var_2B8]
0x1800102a4  mov     rcx, r14; struct IVdsVolume *
0x1800102a7  call    ?BdeCfgFindBasicVolumeExtent@@YAJPEAUIVdsVolume@@PEA_K1@Z; BdeCfgFindBasicVolumeExtent(IVdsVolume *,unsigned __int64 *,unsigned __int64 *)
0x1800102ac  mov     edi, eax
0x1800102ae  mov     [rsp+2F8h+var_2D8], eax
0x1800102b2  test    eax, eax
0x1800102b4  js      loc_1800106A0
0x1800102ba  mov     dl, [rsi+0Ch]
0x1800102bd  test    dl, dl
0x1800102bf  jnz     loc_1800106A0
0x1800102c5  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800102c9  call    cs:__imp_EnterCriticalSection
0x1800102cf  lea     r15, [rsi+4F8h]
0x1800102d6  mov     r8, r15; struct IVdsAsync **
0x1800102d9  mov     rdx, [rsi+488h]; unsigned __int64
0x1800102e0  mov     rcx, r14; struct IVdsVolume *
0x1800102e3  call    ?BdeCfgpShrinkSimpleVolumeCancellable@@YAJPEAUIVdsVolume@@_KPEAPEAUIVdsAsync@@@Z; BdeCfgpShrinkSimpleVolumeCancellable(IVdsVolume *,unsigned __int64,IVdsAsync * *)
0x1800102e8  mov     edi, eax
0x1800102ea  mov     [rsp+2F8h+var_2D8], eax
0x1800102ee  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800102f2  call    cs:__imp_LeaveCriticalSection
0x1800102f8  xor     r14d, r14d
0x1800102fb  test    edi, edi
0x1800102fd  js      loc_1800106A3
0x180010303  mov     rcx, [r15]
0x180010306  mov     rax, [rcx]
0x180010309  lea     r8, [rsp+2F8h+var_268]
0x180010311  lea     rdx, [rsp+2F8h+var_2C8]
0x180010316  mov     rax, [rax+20h]
0x18001031a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001031f  mov     edi, eax
0x180010321  mov     [rsp+2F8h+var_2D8], eax
0x180010325  test    eax, eax
0x180010327  js      loc_1800106A3
0x18001032d  mov     al, [rsi+0Ch]
0x180010330  test    al, al
0x180010332  jnz     loc_1800106A3
0x180010338  mov     edi, [rsp+2F8h+var_2C8]
0x18001033c  test    edi, edi
0x18001033e  jns     short loc_180010349
0x180010340  mov     [rsp+2F8h+var_2D8], edi
0x180010344  jmp     loc_1800106A3
0x180010349  mov     rcx, [rsp+2F8h+var_2A0]
0x18001034e  mov     rdx, qword ptr [rsp+2F8h+var_268+8]
0x180010356  sub     rcx, rdx
0x180010359  mov     rax, [rsp+2F8h+var_2A8]
0x18001035e  add     rax, rcx
0x180010361  mov     [rsp+2F8h+var_2A8], rax
0x180010366  mov     [rsi+250h], rax
0x18001036d  mov     [r12], rdx
0x180010371  lea     r12, [rsi+260h]
0x180010378  movzx   eax, word ptr [rsi+490h]
0x18001037f  mov     [r12], ax
0x180010384  jmp     short loc_180010393
0x180010386  lea     r12, [rsi+260h]
0x18001038d  mov     r13d, 0C0A0001Eh
0x180010393  lea     rbx, [rsi+44h]
0x180010397  lea     r8, [rsp+2F8h+var_2B0]; struct IVdsVolume **
0x18001039c  mov     rdx, rbx; unsigned __int64
0x18001039f  lea     rcx, ?BdeCfgpFilterVolumesByName@@YAHPEAUIVdsVolume@@_K@Z; int (*)(struct IVdsVolume *, unsigned __int64)
0x1800103a6  call    ?BdeCfgpFindFirstVolume@@YAJP6AHPEAUIVdsVolume@@_K@Z1PEAPEAU1@@Z; BdeCfgpFindFirstVolume(int (*)(IVdsVolume *,unsigned __int64),unsigned __int64,IVdsVolume * *)
0x1800103ab  mov     edi, eax
0x1800103ad  mov     [rsp+2F8h+var_2D8], eax
0x1800103b1  cmp     eax, 1
0x1800103b4  cmovz   edi, r13d
0x1800103b8  mov     [rsp+2F8h+var_2D8], edi
0x1800103bc  xor     r13d, r13d
0x1800103bf  test    edi, edi
0x1800103c1  js      loc_1800106A0
0x1800103c7  mov     eax, [rsi+40h]
0x1800103ca  dec     eax
0x1800103cc  test    eax, 0FFFFFFFDh
0x1800103d1  jz      short loc_1800103E5
0x1800103d3  lea     r15, [rsi+258h]
0x1800103da  mov     r14d, 104h
0x1800103e0  jmp     loc_180010587
0x1800103e5  mov     edx, 1
0x1800103ea  mov     rcx, rsi
0x1800103ed  call    ?SetConfigurationStep@CDriveConfiguration@@AEAAJW4_BDECFG_STEP_ID@@@Z; CDriveConfiguration::SetConfigurationStep(_BDECFG_STEP_ID)
0x1800103f2  lea     rdx, [rsi+4F0h]; unsigned int *
0x1800103f9  movzx   ecx, word ptr [r12]; unsigned __int16
0x1800103fe  call    ?RegisterForCancel@CQueryCancelAutoPlay@@SAJGPEAK@Z; CQueryCancelAutoPlay::RegisterForCancel(ushort,ulong *)
0x180010403  lea     rdx, [rsp+2F8h+var_2C0]; struct IVdsDisk **
0x180010408  mov     rcx, [rsp+2F8h+var_2B0]; struct IVdsVolume *
0x18001040d  call    ?BdeCfgGetVolumeDisk@@YAJPEAUIVdsVolume@@PEAPEAUIVdsDisk@@@Z; BdeCfgGetVolumeDisk(IVdsVolume *,IVdsDisk * *)
0x180010412  mov     edi, eax
0x180010414  mov     [rsp+2F8h+var_2D8], eax
0x180010418  test    eax, eax
0x18001041a  js      loc_1800106A0
0x180010420  mov     al, [rsi+0Ch]
0x180010423  test    al, al
0x180010425  jnz     loc_1800106A0
0x18001042b  lea     r15, [rsi+258h]
0x180010432  lea     r9, [rsp+2F8h+var_2D0]; struct IVdsVolume **
0x180010437  mov     r8, [r15]; unsigned __int64
0x18001043a  mov     rdx, [rsi+250h]; unsigned __int64
0x180010441  mov     rcx, [rsp+2F8h+var_2C0]; struct IVdsDisk *
0x180010446  call    ?BdeCfgCreatePrimaryPartition@@YAJPEAUIVdsDisk@@_K1PEAPEAUIVdsVolume@@@Z; BdeCfgCreatePrimaryPartition(IVdsDisk *,unsigned __int64,unsigned __int64,IVdsVolume * *)
0x18001044b  mov     edi, eax
0x18001044d  mov     [rsp+2F8h+var_2D8], eax
0x180010451  test    eax, eax
0x180010453  js      loc_1800106A0
0x180010459  mov     al, [rsi+0Ch]
0x18001045c  test    al, al
0x18001045e  jnz     loc_1800106A0
0x180010464  lea     r8, [rsp+2F8h+var_248]; unsigned __int16 *
0x18001046c  mov     r14d, 104h
0x180010472  mov     edx, r14d; unsigned __int64
0x180010475  mov     rcx, [rsp+2F8h+var_2D0]; struct IVdsVolume *
0x18001047a  call    ?BdeCfgGetDeviceNameFromVolume@@YAJPEAUIVdsVolume@@_KPEAG@Z; BdeCfgGetDeviceNameFromVolume(IVdsVolume *,unsigned __int64,ushort *)
0x18001047f  mov     edi, eax
0x180010481  mov     [rsp+2F8h+var_2D8], eax
0x180010485  test    eax, eax
0x180010487  js      loc_1800106A0
0x18001048d  mov     al, [rsi+0Ch]
0x180010490  test    al, al
0x180010492  jnz     loc_1800106A0
0x180010498  lea     rcx, [rsi+18h]; lpCriticalSection
0x18001049c  call    cs:__imp_EnterCriticalSection
0x1800104a2  lea     r13, [rsi+500h]
0x1800104a9  mov     rdx, r13; struct IBdeCfgAsync **
0x1800104ac  mov     rcx, [rsp+2F8h+var_2D0]; struct IVdsVolume *
0x1800104b1  call    ?BdeCfgSecureFormatVolume@@YAJPEAUIVdsVolume@@PEAPEAVIBdeCfgAsync@@@Z; BdeCfgSecureFormatVolume(IVdsVolume *,IBdeCfgAsync * *)
0x1800104b6  mov     edi, eax
0x1800104b8  mov     [rsp+2F8h+var_2D8], eax
0x1800104bc  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800104c0  call    cs:__imp_LeaveCriticalSection
0x1800104c6  test    edi, edi
0x1800104c8  js      loc_1800106A0
0x1800104ce  mov     al, [rsi+0Ch]
0x1800104d1  test    al, al
0x1800104d3  jnz     loc_1800106A0
0x1800104d9  mov     rcx, [r13+0]
0x1800104dd  mov     rax, [rcx]
0x1800104e0  lea     rdx, [rsp+2F8h+var_2C8]
0x1800104e5  mov     rax, [rax+18h]
0x1800104e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104ee  mov     edi, eax
0x1800104f0  mov     [rsp+2F8h+var_2D8], eax
0x1800104f4  xor     r13d, r13d
0x1800104f7  test    eax, eax
0x1800104f9  js      loc_1800106A0
0x1800104ff  mov     al, [rsi+0Ch]
0x180010502  test    al, al
0x180010504  jnz     loc_1800106A0
0x18001050a  mov     edi, [rsp+2F8h+var_2C8]
0x18001050e  test    edi, edi
0x180010510  jns     short loc_18001051B
0x180010512  mov     [rsp+2F8h+var_2D8], edi
0x180010516  jmp     loc_1800106A0
0x18001051b  lea     rcx, [rsp+2F8h+var_248]; unsigned __int16 *
0x180010523  call    ?BdeCfgSetVolumeDacl@@YAJPEBG0@Z; BdeCfgSetVolumeDacl(ushort const *,ushort const *)
0x180010528  mov     edi, eax
0x18001052a  mov     [rsp+2F8h+var_2D8], eax
0x18001052e  test    eax, eax
0x180010530  jns     short loc_18001054B
0x180010532  mov     edx, 40A00045h
0x180010537  mov     ebx, 3
0x18001053c  mov     ecx, ebx
0x18001053e  call    BdeCfgLogError
0x180010543  xor     r14d, r14d
0x180010546  jmp     loc_1800106A8
0x18001054b  mov     al, [rsi+0Ch]
0x18001054e  test    al, al
0x180010550  jnz     loc_1800106A0
0x180010556  movzx   edx, word ptr [r12]; unsigned __int16
0x18001055b  test    dx, dx
0x18001055e  jz      short loc_180010570
0x180010560  mov     rcx, [rsp+2F8h+var_2D0]; struct IVdsVolume *
0x180010565  call    ?BdeCfgAssignLetterToVolume@@YAJPEAUIVdsVolume@@G@Z; BdeCfgAssignLetterToVolume(IVdsVolume *,ushort)
0x18001056a  mov     edi, eax
0x18001056c  mov     [rsp+2F8h+var_2D8], eax
0x180010570  test    edi, edi
0x180010572  js      loc_1800106A0
0x180010578  mov     al, [rsi+0Ch]
0x18001057b  test    al, al
0x18001057d  jnz     loc_1800106A0
0x180010583  lea     rbx, [rsi+44h]
0x180010587  cmp     [rsi+40h], r13d
0x18001058b  jz      loc_180010681
0x180010591  mov     edx, 2
0x180010596  mov     rcx, rsi
0x180010599  call    ?SetConfigurationStep@CDriveConfiguration@@AEAAJW4_BDECFG_STEP_ID@@@Z; CDriveConfiguration::SetConfigurationStep(_BDECFG_STEP_ID)
0x18001059e  cmp     dword ptr [rsi+40h], 2
0x1800105a2  jnz     loc_180010643
0x1800105a8  mov     edx, 7FFFFFFEh
0x1800105ad  mov     [rsp+2F8h+var_278], rdx
0x1800105b5  mov     [rsp+2F8h+var_288], r15
0x1800105ba  mov     [rsp+2F8h+var_280], r14
0x1800105bf  lea     rcx, [rsp+2F8h+var_248]
0x1800105c7  mov     [rsp+2F8h+var_298], rcx
0x1800105cc  mov     edi, r13d
0x1800105cf  mov     rax, r13
0x1800105d2  mov     [rsp+2F8h+var_290], rax
0x1800105d7  test    r14, r14
0x1800105da  jz      short loc_180010623
0x1800105dc  test    rdx, rdx
0x1800105df  jz      short loc_18001061E
0x1800105e1  movzx   r8d, word ptr [r15]
0x1800105e5  test    r8w, r8w
0x1800105e9  jz      short loc_18001061E
0x1800105eb  add     r15, 2
0x1800105ef  mov     [rsp+2F8h+var_288], r15
0x1800105f4  mov     [rcx], r8w
0x1800105f8  add     rcx, 2
0x1800105fc  mov     [rsp+2F8h+var_298], rcx
0x180010601  dec     r14
0x180010604  mov     [rsp+2F8h+var_280], r14
0x180010609  dec     rdx
0x18001060c  mov     [rsp+2F8h+var_278], rdx
0x180010614  inc     rax
0x180010617  mov     [rsp+2F8h+var_290], rax
0x18001061c  jmp     short loc_1800105D7
0x18001061e  test    r14, r14
0x180010621  jnz     short loc_180010639
0x180010623  sub     rcx, 2
0x180010627  mov     [rsp+2F8h+var_298], rcx
0x18001062c  dec     rax
0x18001062f  mov     [rsp+2F8h+var_290], rax
0x180010634  mov     edi, 8007007Ah
0x180010639  mov     eax, r13d
0x18001063c  mov     [rcx], ax
0x18001063f  mov     [rsp+2F8h+var_2D8], edi
0x180010643  test    edi, edi
0x180010645  js      short loc_1800106A0
0x180010647  mov     al, [rsi+0Ch]
0x18001064a  test    al, al
0x18001064c  jnz     short loc_1800106A0
0x18001064e  mov     eax, [rsi+40h]
0x180010651  dec     eax
0x180010653  test    eax, 0FFFFFFFDh
0x180010658  mov     r8d, r13d
0x18001065b  setnz   r8b; int
0x18001065f  lea     rdx, [rsp+2F8h+var_248]; unsigned __int16 *
0x180010667  mov     rcx, rbx; unsigned __int16 *
0x18001066a  call    ?BdeCfgMigrateBootHive@@YAJPEBG0H@Z; BdeCfgMigrateBootHive(ushort const *,ushort const *,int)
0x18001066f  mov     edi, eax
0x180010671  mov     [rsp+2F8h+var_2D8], eax
0x180010675  test    eax, eax
0x180010677  js      short loc_1800106A0
0x180010679  mov     rcx, rbx; unsigned __int16 *
0x18001067c  call    ?BdeCfgCleanupOldBootFiles@@YAJPEBG@Z; BdeCfgCleanupOldBootFiles(ushort const *)
0x180010681  mov     rcx, [rsi+4E8h]
  ... truncated ...
```
