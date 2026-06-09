# MpRegCallback

- ea: `0x14004d0d0`
- end: `0x14004da57`
- name: `MpRegCallback`
- size: `2439`
- prototype: `EX_CALLBACK_FUNCTION`
- caller_count: `0`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003d20`
- `0x1400051bc`
- `0x14000fddc`
- `0x1400118d0`
- `0x1400444b0`
- `0x1400496d8`
- `0x140049ec0`
- `0x14004a930`
- `0x14004b6d0`
- `0x14004b990`
- `0x14004d0d0`
- `0x14004da60`
- `0x14004dda0`
- `0x14004ea60`
- `0x14004ef30`
- `0x14004f660`
- `0x14004f9a8`
- `0x14004ffb0`
- `0x1400508c4`
- `0x14006c960`
- `0x14007dae8`
- `0x14007dd00`
- `0x14007df24`
- `0x14007e274`
- `0x14007ea68`
- `0x14007f16c`

## import_xrefs

- `ntoskrnl!PsInitialSystemProcess` at `0x14004d208`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d3ef`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d3ef`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004d168`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004d168`
- `ntoskrnl!IoThreadToProcess` at `0x14004d1cf`
- `ntoskrnl!IoThreadToProcess` at `0x14004d1f7`
- `ntoskrnl!IoThreadToProcess` at `0x14004d2fe`
- `ntoskrnl!IoThreadToProcess` at `0x14004d32a`
- `ntoskrnl!IoThreadToProcess` at `0x14004d41a`
- `ntoskrnl!IoThreadToProcess` at `0x14004d442`
- `ntoskrnl!IoThreadToProcess` at `0x14004d1cf`
- `ntoskrnl!IoThreadToProcess` at `0x14004d1f7`
- `ntoskrnl!IoThreadToProcess` at `0x14004d2fe`
- `ntoskrnl!IoThreadToProcess` at `0x14004d32a`
- `ntoskrnl!IoThreadToProcess` at `0x14004d41a`
- `ntoskrnl!IoThreadToProcess` at `0x14004d442`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004d8f2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004d8f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d7a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d7a5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004d376`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004d4f3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004d376`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004d4f3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d49c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d71f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d49c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d71f`

## string_xrefs

- `0x14004d5b0`: `RegNtPreCreateKeyEx`
- `0x14004d74b`: `RegNtPreDeleteValueKey`
- `0x14004d75b`: `RegNtPreDeleteKey`
- `0x14004d794`: `RegNtPreReplaceKey`
- `0x14004d7fe`: `RegNtPreRenameKey`
- `0x14004d7ed`: `RegNtPreSetKeySecurity`

## pseudocode

```c
__int64 __fastcall MpRegCallback(PVOID CallbackContext, unsigned __int64 Argument1, int *Argument2)
{
  UNICODE_STRING *v4; // rsi
  int *v5; // r12
  __int64 v6; // rbx
  char v7; // r13
  __int64 v8; // rcx
  struct _KPROCESS *CurrentProcess; // r15
  struct _KPROCESS *v10; // rdi
  struct _KPROCESS *v11; // rdi
  __int64 v13; // rcx
  struct _KPROCESS *v14; // rdi
  struct _KPROCESS *v15; // rdi
  __int64 v16; // rcx
  struct _KTHREAD *CurrentThread; // r15
  _QWORD *v18; // rdi
  _QWORD *i; // rax
  _QWORD *v20; // rdx
  __int64 v21; // r15
  int v22; // ecx
  struct _KPROCESS *v23; // rdi
  struct _KPROCESS *v24; // rdi
  const UNICODE_STRING *v25; // rcx
  _QWORD *v26; // r9
  __int64 v27; // rdx
  char v28; // r15
  __int64 v29; // rdi
  char *v30; // rbx
  struct _FAST_MUTEX *v31; // rcx
  char *v32; // rcx
  char *j; // rdx
  __int64 v34; // rax
  _QWORD *v35; // rdi
  const char *v36; // rcx
  int v37; // edx
  __int64 v38; // r9
  char *v39; // r8
  char **v40; // rax
  int KeyName; // eax
  int v42; // ecx
  unsigned int v43; // ecx
  char v44[8]; // [rsp+40h] [rbp-30h] BYREF
  int v45[2]; // [rsp+48h] [rbp-28h] BYREF
  PCUNICODE_STRING String1; // [rsp+50h] [rbp-20h] BYREF
  int v47; // [rsp+58h] [rbp-18h] BYREF

  *(_QWORD *)v45 = 0;
  v4 = 0;
  v5 = Argument2;
  LODWORD(Argument2) = 0;
  String1 = 0;
  v6 = *((_QWORD *)MpRegData + 3);
  v7 = 1;
  LOBYTE(v47) = 0;
  v44[0] = 0;
  if ( (*(_DWORD *)(MpData + 868) & 8) != 0
    && *((_QWORD *)MpRegData + 2)
    && (*(_DWORD *)(MpData + 868) & 0x10) != 0
    && ((v6 & 0x380000) != 0 || (v6 & 0x400000) != 0 || (v6 & 0x800000) != 0 || (v6 & 0x40000) != 0) )
  {
    goto LABEL_4;
  }
  if ( (unsigned int)Argument1 > 0x2D )
    goto LABEL_4;
  v8 = 0x224004000017LL;
  if ( !_bittest64(&v8, Argument1) )
    goto LABEL_4;
  LODWORD(v36) = 0;
  if ( (_DWORD)Argument1 == 26 )
  {
    v37 = (int)v5;
    v36 = "RegNtPreCreateKeyEx";
LABEL_57:
    LODWORD(v38) = 0;
    goto LABEL_58;
  }
  v37 = 0;
  switch ( (_DWORD)Argument1 )
  {
    case 0:
      Argument2 = *(int **)v5;
      v36 = "RegNtPreDeleteKey";
      goto LABEL_57;
    case 1:
      v36 = "RegNtPreSetValueKey";
LABEL_71:
      Argument2 = *(int **)v5;
      goto LABEL_57;
    case 2:
      Argument2 = *(int **)v5;
      v36 = "RegNtPreDeleteValueKey";
      goto LABEL_57;
  }
  if ( (_DWORD)Argument1 != 4 )
  {
    switch ( (_DWORD)Argument1 )
    {
      case '-':
        Argument2 = *(int **)v5;
        v36 = "RegNtPreReplaceKey";
        goto LABEL_57;
      case ')':
        v36 = "RegNtPreRestoreKey";
        break;
      case '&':
        v36 = "RegNtPreSetKeySecurity";
        break;
      default:
        goto LABEL_57;
    }
    goto LABEL_71;
  }
  v38 = *((_QWORD *)v5 + 1);
  v36 = "RegNtPreRenameKey";
  Argument2 = *(int **)v5;
LABEL_58:
  if ( (int)MpRegHardenningBlockOperation(
              (_DWORD)v36,
              v37,
              (_DWORD)Argument2,
              v38,
              (__int64)&String1,
              (__int64)v44,
              (__int64)&v47) < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
      KeGetCurrentThread());
  }
  v4 = (UNICODE_STRING *)String1;
LABEL_4:
  CurrentProcess = IoGetCurrentProcess();
  if ( !MpDlpData
    || !*((_BYTE *)MpDlpData + 32)
    || (*(_DWORD *)(MpData + 864) & 0x400) == 0
    || !*(_QWORD *)(MpData + 320) && !*(_QWORD *)(MpData + 336) )
  {
    goto LABEL_12;
  }
  v10 = *(struct _KPROCESS **)(MpData + 232);
  if ( IoThreadToProcess(KeGetCurrentThread()) != v10 )
  {
    v11 = *(struct _KPROCESS **)(MpData + 256);
    if ( IoThreadToProcess(KeGetCurrentThread()) != v11
      && PsInitialSystemProcess == CurrentProcess
      && !(unsigned __int8)MpIsPotentialRemoteOpen(0) )
    {
      goto LABEL_12;
    }
  }
  String1 = 0;
  if ( (_DWORD)Argument1 != 16 )
    goto LABEL_12;
  if ( v5[2] < 0 )
    goto LABEL_12;
  v21 = *((_QWORD *)v5 + 2);
  v22 = *(_DWORD *)(MpData + 864);
  if ( (v22 & 0x2000) != 0 )
    goto LABEL_12;
  if ( (v22 & 0x400) == 0 )
    goto LABEL_12;
  if ( !RtlEqualUnicodeString(&ValueName, *(PCUNICODE_STRING *)(v21 + 8), 1u) )
    goto LABEL_12;
  v23 = *(struct _KPROCESS **)(MpData + 232);
  if ( IoThreadToProcess(KeGetCurrentThread()) != v23 )
  {
    v24 = *(struct _KPROCESS **)(MpData + 256);
    if ( IoThreadToProcess(KeGetCurrentThread()) != v24 )
      goto LABEL_12;
  }
  if ( v4 )
  {
    v25 = v4;
    String1 = v4;
  }
  else
  {
    KeyName = MpRegpGetKeyName(*(PVOID *)v5);
    if ( KeyName < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          76,
          WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
          KeGetCurrentThread(),
          KeyName);
      }
      goto LABEL_97;
    }
    v25 = String1;
  }
  if ( !RtlCompareUnicodeString(v25, &stru_140026570, 1u) )
  {
    v42 = *((_DWORD *)MpDlpData + 10);
    if ( (**(_BYTE **)(v21 + 24) & 1) != 0 )
      v43 = v42 | 1;
    else
      v43 = v42 & 0xFFFFFFFE;
    *((_DWORD *)MpDlpData + 10) = v43;
    MpDlpUpdateEnlightmentForRunningProcesses();
  }
LABEL_97:
  if ( String1 )
  {
    if ( v4 )
    {
      if ( v4 != String1 )
        MpRegpFreeKeyName((PVOID)String1);
    }
    else
    {
      v4 = (UNICODE_STRING *)String1;
    }
  }
LABEL_12:
  if ( v6 )
  {
    if ( (unsigned int)Argument1 <= 0x2E )
    {
      v13 = 0x66C00C0B8017LL;
      if ( _bittest64(&v13, Argument1) )
      {
        v14 = *(struct _KPROCESS **)(MpData + 232);
        if ( IoThreadToProcess(KeGetCurrentThread()) != v14 )
        {
          v15 = *(struct _KPROCESS **)(MpData + 256);
          if ( IoThreadToProcess(KeGetCurrentThread()) != v15 )
          {
            v16 = 0x4080080B8000LL;
            if ( _bittest64(&v16, Argument1) )
            {
              CurrentThread = KeGetCurrentThread();
              v18 = 0;
              ExAcquireFastMutex((PFAST_MUTEX)((char *)MpRegData + 296));
              for ( i = (_QWORD *)*((_QWORD *)MpRegData + 44); ; i = (_QWORD *)*i )
              {
                if ( i == (_QWORD *)((char *)MpRegData + 352) )
                  goto LABEL_42;
                v20 = (_QWORD *)*i;
                if ( (struct _KTHREAD *)i[2] == CurrentThread )
                  break;
              }
              if ( (_QWORD *)v20[1] != i || (v26 = (_QWORD *)i[1], (_QWORD *)*v26 != i) )
LABEL_49:
                __fastfail(3u);
              *v26 = v20;
              v18 = i - 2;
              v20[1] = v26;
LABEL_42:
              ExReleaseFastMutex((PFAST_MUTEX)((char *)MpRegData + 296));
              *(_QWORD *)v45 = v18;
              v28 = 1;
              if ( (_DWORD)Argument1 == 27 )
              {
                MpRegPostCreateKeyEx(v5, v27, v18);
                goto LABEL_13;
              }
            }
            else
            {
              v28 = 0;
            }
            switch ( (int)Argument1 )
            {
              case 0:
                MpRegPreDeleteKey((_DWORD)v5, v6, (unsigned int)v45, (unsigned int)&v47, (__int64)v4);
                v7 = 0;
                break;
              case 1:
                MpRegPreSetValueKey((_DWORD)v5, v6, (unsigned int)v45, (unsigned int)&v47, (__int64)v4);
                v7 = 0;
                break;
              case 2:
                MpRegPreDeleteValueKey((int)v5, v6, (int)v45, (int)&v47, v4);
                v7 = 0;
                break;
              case 4:
                MpRegPreRenameKey((int)v5, v6, (int)v45, (int)&v47, v4);
                v7 = 0;
                break;
              case 15:
                MpRegPostDeleteKey(v5, 0x140000000uLL, *(_QWORD *)v45);
                break;
              case 16:
                MpRegPostSetValueKey(v5, *(_QWORD *)v45);
                break;
              case 17:
                MpRegPostDeleteValueKey(v5, *(_QWORD *)v45);
                break;
              case 19:
                MpRegPostRenameKey(v5, 0x140000000uLL, *(_QWORD *)v45);
                break;
              case 26:
                MpRegPreCreateKeyEx((_DWORD)v5, v6, (unsigned int)v45, (unsigned int)&v47, (__int64)v4, v44[0]);
                v7 = 0;
                break;
              case 38:
                MpRegPreSetKeySecurity((_DWORD)v5, v6, (unsigned int)v45, (unsigned int)&v47, (__int64)v4);
                v7 = 0;
                break;
              case 39:
                MpRegPostSetKeySecurity(v5, 0x140000000uLL, *(_QWORD *)v45);
                break;
              case 41:
                MpRegPreRestoreKey((int)v5, v6, (int)v45, (int)&v47, v4);
                v7 = 0;
                break;
              case 42:
                MpRegPostRestoreKey(v5, 0x140000000uLL, *(_QWORD *)v45);
                break;
              case 45:
                MpRegPreReplaceKey((int)v5, v6, (int)v45, (int)&v47, v4);
                v7 = 0;
                break;
              case 46:
                MpRegPostReplaceKey(v5, 0x140000000uLL, *(_QWORD *)v45);
                break;
              default:
                break;
            }
            if ( !v28 )
            {
              v29 = *(_QWORD *)v45;
              if ( *(_QWORD *)v45 )
              {
                v30 = 0;
                v31 = (struct _FAST_MUTEX *)((char *)MpRegData + 296);
                *(_QWORD *)(*(_QWORD *)v45 + 32LL) = KeGetCurrentThread();
                ExAcquireFastMutex(v31);
                v32 = (char *)MpRegData + 352;
                for ( j = (char *)*((_QWORD *)MpRegData + 44); ; j = *(char **)j )
                {
                  if ( j == v32 )
                    goto LABEL_48;
                  v39 = *(char **)j;
                  if ( *((_QWORD *)j + 2) == *(_QWORD *)(v29 + 32) )
                    break;
                }
                if ( *((char **)v39 + 1) != j )
                  goto LABEL_49;
                v40 = (char **)*((_QWORD *)j + 1);
                if ( *v40 != j )
                  goto LABEL_49;
                *v40 = v39;
                v30 = j - 16;
                *((_QWORD *)v39 + 1) = v40;
LABEL_48:
                v34 = *(_QWORD *)v32;
                v35 = (_QWORD *)(v29 + 16);
                if ( *(char **)(*(_QWORD *)v32 + 8LL) != v32 )
                  goto LABEL_49;
                v35[1] = v32;
                *v35 = v34;
                *(_QWORD *)(v34 + 8) = v35;
                *(_QWORD *)v32 = v35;
                ExReleaseFastMutex((PFAST_MUTEX)((char *)MpRegData + 296));
                if ( v30 )
                  MpRegpFreeCallContext(v30);
                *(_QWORD *)v45 = 0;
              }
            }
          }
        }
      }
    }
  }
LABEL_13:
  if ( v4 && v7 == 1 )
  {
    if ( (_DWORD)Argument1 == 26 )
      ExFreePoolWithTag(v4, 0x5364504Du);
    else
      MpRegpFreeKeyName(v4);
  }
  return (_BYTE)v47 != 0 ? 0xC0000022 : 0;
}

```

## disassembly

```asm
0x14004d0d0  mov     [rsp-28h+arg_0], rbx
0x14004d0d5  mov     [rsp-28h+arg_8], rsi
0x14004d0da  mov     [rsp-28h+arg_18], rdi
0x14004d0df  push    rbp
0x14004d0e0  push    r12
0x14004d0e2  push    r13
0x14004d0e4  push    r14
0x14004d0e6  push    r15
0x14004d0e8  mov     rbp, rsp
0x14004d0eb  sub     rsp, 70h
0x14004d0ef  mov     rax, cs:__security_cookie
0x14004d0f6  xor     rax, rsp
0x14004d0f9  mov     [rbp+var_10], rax
0x14004d0fd  mov     rbx, cs:MpRegData
0x14004d104  lea     rdi, WPP_GLOBAL_Control
0x14004d10b  mov     r14, rdx
0x14004d10e  mov     qword ptr [rbp+var_28], 0
0x14004d116  xor     esi, esi
0x14004d118  mov     r12, r8
0x14004d11b  xor     r8d, r8d
0x14004d11e  mov     [rbp+String1], rsi
0x14004d122  mov     rbx, [rbx+18h]
0x14004d126  mov     r13b, 1
0x14004d129  mov     rax, cs:MpData
0x14004d130  mov     rdx, rbx
0x14004d133  mov     byte ptr [rbp+var_18], r8b
0x14004d137  shr     rdx, 10h
0x14004d13b  mov     [rbp+var_30], r8b
0x14004d13f  mov     ecx, [rax+364h]
0x14004d145  test    cl, 8
0x14004d148  jnz     loc_14004D274
0x14004d14e  cmp     r14d, 2Dh ; '-'
0x14004d152  ja      short loc_14004D168
0x14004d154  mov     rcx, 224004000017h
0x14004d15e  bt      rcx, r14
0x14004d162  jb      loc_14004D5A1
0x14004d168  call    cs:__imp_IoGetCurrentProcess
0x14004d16f  nop     dword ptr [rax+rax+00h]
0x14004d174  mov     rcx, cs:MpDlpData
0x14004d17b  mov     r15, rax
0x14004d17e  test    rcx, rcx
0x14004d181  jz      loc_14004D22A
0x14004d187  movzx   edx, byte ptr [rcx+20h]
0x14004d18b  test    dl, dl
0x14004d18d  jz      loc_14004D22A
0x14004d193  mov     rax, cs:MpData
0x14004d19a  test    dword ptr [rax+360h], 400h
0x14004d1a4  jz      loc_14004D22A
0x14004d1aa  cmp     qword ptr [rax+140h], 0
0x14004d1b2  jz      loc_14004D6D7
0x14004d1b8  mov     rcx, gs:188h; Thread
0x14004d1c1  mov     rax, cs:MpData
0x14004d1c8  mov     rdi, [rax+0E8h]
0x14004d1cf  call    cs:__imp_IoThreadToProcess
0x14004d1d6  nop     dword ptr [rax+rax+00h]
0x14004d1db  cmp     rax, rdi
0x14004d1de  jz      short loc_14004D218
0x14004d1e0  mov     rcx, gs:188h; Thread
0x14004d1e9  mov     rax, cs:MpData
0x14004d1f0  mov     rdi, [rax+100h]
0x14004d1f7  call    cs:__imp_IoThreadToProcess
0x14004d1fe  nop     dword ptr [rax+rax+00h]
0x14004d203  cmp     rax, rdi
0x14004d206  jz      short loc_14004D218
0x14004d208  mov     rax, cs:__imp_PsInitialSystemProcess
0x14004d20f  cmp     [rax], r15
0x14004d212  jz      loc_14004D60B
0x14004d218  mov     [rbp+String1], 0
0x14004d220  cmp     r14d, 10h
0x14004d224  jz      loc_14004D3AE
0x14004d22a  test    rbx, rbx
0x14004d22d  jnz     loc_14004D2C9
0x14004d233  test    rsi, rsi
0x14004d236  jnz     loc_14004D767
0x14004d23c  movzx   eax, byte ptr [rbp+var_18]
0x14004d240  neg     al
0x14004d242  sbb     eax, eax
0x14004d244  and     eax, 0C0000022h
0x14004d249  mov     rcx, [rbp+var_10]
0x14004d24d  xor     rcx, rsp; StackCookie
0x14004d250  call    __security_check_cookie
0x14004d255  lea     r11, [rsp+70h+var_s0]
0x14004d25a  mov     rbx, [r11+30h]
0x14004d25e  mov     rsi, [r11+38h]
0x14004d262  mov     rdi, [r11+48h]
0x14004d266  mov     rsp, r11
0x14004d269  pop     r15
0x14004d26b  pop     r14
0x14004d26d  pop     r13
0x14004d26f  pop     r12
0x14004d271  pop     rbp
0x14004d272  retn
0x14004d274  mov     rax, cs:MpRegData
0x14004d27b  cmp     [rax+10h], rsi
0x14004d27f  jz      loc_14004D14E
0x14004d285  mov     rax, cs:MpData
0x14004d28c  mov     ecx, [rax+364h]
0x14004d292  test    cl, 10h
0x14004d295  jz      loc_14004D14E
0x14004d29b  test    dl, 38h
0x14004d29e  jnz     loc_14004D168
0x14004d2a4  test    dl, 40h
0x14004d2a7  jnz     loc_14004D168
0x14004d2ad  test    dl, dl
0x14004d2af  js      loc_14004D168
0x14004d2b5  mov     rax, rbx
0x14004d2b8  shr     rax, 10h
0x14004d2bc  test    al, 4
0x14004d2be  jnz     loc_14004D168
0x14004d2c4  jmp     loc_14004D14E
0x14004d2c9  cmp     r14d, 2Eh ; '.'
0x14004d2cd  ja      loc_14004D233
0x14004d2d3  mov     rcx, 66C00C0B8017h
0x14004d2dd  bt      rcx, r14
0x14004d2e1  jnb     loc_14004D233
0x14004d2e7  mov     rcx, gs:188h; Thread
0x14004d2f0  mov     rax, cs:MpData
0x14004d2f7  mov     rdi, [rax+0E8h]
0x14004d2fe  call    cs:__imp_IoThreadToProcess
0x14004d305  nop     dword ptr [rax+rax+00h]
0x14004d30a  cmp     rax, rdi
0x14004d30d  jz      loc_14004D233
0x14004d313  mov     rcx, gs:188h; Thread
0x14004d31c  mov     rax, cs:MpData
0x14004d323  mov     rdi, [rax+100h]
0x14004d32a  call    cs:__imp_IoThreadToProcess
0x14004d331  nop     dword ptr [rax+rax+00h]
0x14004d336  cmp     rax, rdi
0x14004d339  jz      loc_14004D233
0x14004d33f  cmp     r14d, 2Eh ; '.'
0x14004d343  ja      loc_14004D531
0x14004d349  mov     rcx, 4080080B8000h
0x14004d353  bt      rcx, r14
0x14004d357  jnb     loc_14004D531
0x14004d35d  mov     r15, gs:188h
0x14004d366  xor     edi, edi
0x14004d368  mov     rcx, cs:MpRegData
0x14004d36f  add     rcx, 128h; FastMutex
0x14004d376  call    cs:__imp_ExAcquireFastMutex
0x14004d37d  nop     dword ptr [rax+rax+00h]
0x14004d382  mov     rcx, cs:MpRegData
0x14004d389  add     rcx, 160h
0x14004d390  mov     rax, [rcx]
0x14004d393  cmp     rax, rcx
0x14004d396  jz      loc_14004D48E
0x14004d39c  mov     rdx, [rax]
0x14004d39f  cmp     [rax+10h], r15
0x14004d3a3  jz      loc_14004D46C
0x14004d3a9  mov     rax, rdx
0x14004d3ac  jmp     short loc_14004D393
0x14004d3ae  cmp     dword ptr [r12+8], 0
0x14004d3b4  jl      loc_14004D22A
0x14004d3ba  mov     rax, cs:MpData
0x14004d3c1  mov     r15, [r12+10h]
0x14004d3c6  mov     ecx, [rax+360h]
0x14004d3cc  bt      ecx, 0Dh
0x14004d3d0  jb      loc_14004D22A
0x14004d3d6  bt      ecx, 0Ah
0x14004d3da  jnb     loc_14004D22A
0x14004d3e0  mov     rdx, [r15+8]; String2
0x14004d3e4  lea     rcx, ValueName; String1
0x14004d3eb  movzx   r8d, r13b; CaseInSensitive
0x14004d3ef  call    cs:__imp_RtlEqualUnicodeString
0x14004d3f6  nop     dword ptr [rax+rax+00h]
0x14004d3fb  test    al, al
0x14004d3fd  jz      loc_14004D22A
0x14004d403  mov     rcx, gs:188h; Thread
0x14004d40c  mov     rax, cs:MpData
0x14004d413  mov     rdi, [rax+0E8h]
0x14004d41a  call    cs:__imp_IoThreadToProcess
0x14004d421  nop     dword ptr [rax+rax+00h]
0x14004d426  cmp     rax, rdi
0x14004d429  jz      short loc_14004D457
0x14004d42b  mov     rcx, gs:188h; Thread
0x14004d434  mov     rax, cs:MpData
0x14004d43b  mov     rdi, [rax+100h]
0x14004d442  call    cs:__imp_IoThreadToProcess
0x14004d449  nop     dword ptr [rax+rax+00h]
0x14004d44e  cmp     rax, rdi
0x14004d451  jnz     loc_14004D22A
0x14004d457  test    rsi, rsi
0x14004d45a  jz      loc_14004D87E
0x14004d460  mov     rcx, rsi
0x14004d463  mov     [rbp+String1], rcx
0x14004d467  jmp     loc_14004D8E7
0x14004d46c  cmp     [rdx+8], rax
0x14004d470  jnz     loc_14004D52A
0x14004d476  mov     r9, [rax+8]
0x14004d47a  cmp     [r9], rax
0x14004d47d  jnz     loc_14004D52A
0x14004d483  mov     [r9], rdx
0x14004d486  lea     rdi, [rax-10h]
0x14004d48a  mov     [rdx+8], r9
0x14004d48e  mov     rcx, cs:MpRegData
0x14004d495  add     rcx, 128h; FastMutex
0x14004d49c  call    cs:__imp_ExReleaseFastMutex
0x14004d4a3  nop     dword ptr [rax+rax+00h]
0x14004d4a8  mov     qword ptr [rbp+var_28], rdi
0x14004d4ac  movzx   r15d, r13b
0x14004d4b0  cmp     r14d, 1Bh
0x14004d4b4  jz      loc_14004D580
0x14004d4ba  cmp     r14d, 2Eh; switch 47 cases
0x14004d4be  jbe     short loc_14004D536
0x14004d4c0  test    r15b, r15b; jumptable 000000014004D552 default case, cases 3,5-14,18,20-25,27-37,40,43,44
0x14004d4c3  jnz     loc_14004D233
0x14004d4c9  mov     rdi, qword ptr [rbp+var_28]
0x14004d4cd  test    rdi, rdi
0x14004d4d0  jz      loc_14004D233
0x14004d4d6  mov     rax, gs:188h
0x14004d4df  xor     ebx, ebx
0x14004d4e1  mov     rcx, cs:MpRegData
0x14004d4e8  add     rcx, 128h; FastMutex
0x14004d4ef  mov     [rdi+20h], rax
0x14004d4f3  call    cs:__imp_ExAcquireFastMutex
0x14004d4fa  nop     dword ptr [rax+rax+00h]
0x14004d4ff  mov     rcx, cs:MpRegData
0x14004d506  add     rcx, 160h
0x14004d50d  mov     rdx, [rcx]
0x14004d510  cmp     rdx, rcx
0x14004d513  jnz     loc_14004D6EA
0x14004d519  mov     rax, [rcx]
0x14004d51c  add     rdi, 10h
0x14004d520  cmp     [rax+8], rcx
0x14004d524  jz      loc_14004D703
0x14004d52a  mov     ecx, 3
0x14004d52f  int     29h; Win8: RtlFailFast(ecx)
0x14004d531  xor     r15b, r15b
0x14004d534  jmp     short loc_14004D4BA
0x14004d536  lea     rdx, cs:140000000h
0x14004d53d  movsxd  rax, r14d
0x14004d540  movzx   eax, ds:(byte_14004DA28 - 140000000h)[rdx+rax]
0x14004d548  mov     ecx, ds:(jpt_14004D552 - 140000000h)[rdx+rax*4]
0x14004d54f  add     rcx, rdx
0x14004d552  jmp     rcx; switch jump
0x14004d558  movzx   eax, [rbp+var_30]; jumptable 000000014004D552 case 26
0x14004d55c  lea     r9, [rbp+var_18]
0x14004d560  mov     byte ptr [rsp+70h+var_48], al
0x14004d564  lea     r8, [rbp+var_28]
0x14004d568  mov     rdx, rbx
0x14004d56b  mov     [rsp+70h+var_50], rsi
0x14004d570  mov     rcx, r12
0x14004d573  call    MpRegPreCreateKeyEx
0x14004d578  xor     r13b, r13b
0x14004d57b  jmp     def_14004D552; jumptable 000000014004D552 default case, cases 3,5-14,18,20-25,27-37,40,43,44
0x14004d580  mov     r8, rdi
0x14004d583  mov     rcx, r12
0x14004d586  call    MpRegPostCreateKeyEx
0x14004d58b  jmp     loc_14004D233
0x14004d590  mov     rdx, qword ptr [rbp+var_28]; jumptable 000000014004D552 case 16
0x14004d594  mov     rcx, r12
0x14004d597  call    MpRegPostSetValueKey
0x14004d59c  jmp     def_14004D552; jumptable 000000014004D552 default case, cases 3,5-14,18,20-25,27-37,40,43,44
0x14004d5a1  xor     ecx, ecx
0x14004d5a3  cmp     r14d, 1Ah
0x14004d5a7  jnz     loc_14004D692
0x14004d5ad  mov     rdx, r12
0x14004d5b0  lea     rcx, aRegntprecreate; "RegNtPreCreateKeyEx"
0x14004d5b7  xor     r9d, r9d
0x14004d5ba  lea     rax, [rbp+var_18]
0x14004d5be  mov     [rsp+70h+var_40], rax
0x14004d5c3  lea     rax, [rbp+var_30]
0x14004d5c7  mov     [rsp+70h+var_48], rax
0x14004d5cc  lea     rax, [rbp+String1]
0x14004d5d0  mov     [rsp+70h+var_50], rax
0x14004d5d5  call    MpRegHardenningBlockOperation
0x14004d5da  test    eax, eax
0x14004d5dc  js      loc_14004D838
0x14004d5e2  mov     rsi, [rbp+String1]
0x14004d5e6  jmp     loc_14004D168
0x14004d5eb  lea     r9, [rbp+var_18]; jumptable 000000014004D552 case 1
0x14004d5ef  mov     [rsp+70h+var_50], rsi
0x14004d5f4  lea     r8, [rbp+var_28]
0x14004d5f8  mov     rdx, rbx
0x14004d5fb  mov     rcx, r12
0x14004d5fe  call    MpRegPreSetValueKey
0x14004d603  xor     r13b, r13b
0x14004d606  jmp     def_14004D552; jumptable 000000014004D552 default case, cases 3,5-14,18,20-25,27-37,40,43,44
0x14004d60b  xor     ecx, ecx
0x14004d60d  call    MpIsPotentialRemoteOpen
0x14004d612  test    al, al
0x14004d614  jnz     loc_14004D218
0x14004d61a  jmp     loc_14004D22A
0x14004d61f  mov     rdx, qword ptr [rbp+var_28]; jumptable 000000014004D552 case 17
0x14004d623  mov     rcx, r12
0x14004d626  call    MpRegPostDeleteValueKey
0x14004d62b  jmp     def_14004D552; jumptable 000000014004D552 default case, cases 3,5-14,18,20-25,27-37,40,43,44
0x14004d630  lea     r9, [rbp+var_18]; jumptable 000000014004D552 case 2
0x14004d634  mov     [rsp+70h+var_50], rsi; PVOID
0x14004d639  lea     r8, [rbp+var_28]; int
0x14004d63d  mov     rdx, rbx; int
0x14004d640  mov     rcx, r12; int
0x14004d643  call    MpRegPreDeleteValueKey
0x14004d648  xor     r13b, r13b
0x14004d64b  jmp     def_14004D552; jumptable 000000014004D552 default case, cases 3,5-14,18,20-25,27-37,40,43,44
0x14004d650  mov     r8, qword ptr [rbp+var_28]; jumptable 000000014004D552 case 15
0x14004d654  mov     rcx, r12
0x14004d657  call    MpRegPostDeleteKey
0x14004d65c  jmp     def_14004D552; jumptable 000000014004D552 default case, cases 3,5-14,18,20-25,27-37,40,43,44
0x14004d661  lea     r9, [rbp+var_18]; jumptable 000000014004D552 case 0
0x14004d665  mov     [rsp+70h+var_50], rsi
  ... truncated ...
```
