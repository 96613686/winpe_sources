# WofPostQueryInfoCallback

- ea: `0x140038fe0`
- end: `0x140039749`
- name: `WofPostQueryInfoCallback`
- size: `1897`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400014d0`
- `0x140007670`
- `0x140011640`
- `0x1400116c0`
- `0x140038fe0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140039176`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140039176`
- `ntoskrnl!RtlCompareMemory` at `0x140039565`
- `ntoskrnl!RtlCompareMemory` at `0x1400396b8`
- `ntoskrnl!RtlCompareMemory` at `0x140039565`
- `ntoskrnl!RtlCompareMemory` at `0x1400396b8`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400390ae`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400390ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140039196`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140039196`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003918a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003918a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140039108`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140039108`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003911c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003911c`
- `FLTMGR!FltGetStreamContext` at `0x140039058`
- `FLTMGR!FltGetStreamContext` at `0x140039058`
- `FLTMGR!FltGetStreamHandleContext` at `0x140039447`
- `FLTMGR!FltGetStreamHandleContext` at `0x140039447`
- `FLTMGR!FltReleaseContext` at `0x1400390bc`
- `FLTMGR!FltReleaseContext` at `0x1400390f2`
- `FLTMGR!FltReleaseContext` at `0x1400393f8`
- `FLTMGR!FltReleaseContext` at `0x14003946e`
- `FLTMGR!FltReleaseContext` at `0x140039696`
- `FLTMGR!FltReleaseContext` at `0x140039724`
- `FLTMGR!FltReleaseContext` at `0x1400390bc`
- `FLTMGR!FltReleaseContext` at `0x1400390f2`
- `FLTMGR!FltReleaseContext` at `0x1400393f8`
- `FLTMGR!FltReleaseContext` at `0x14003946e`
- `FLTMGR!FltReleaseContext` at `0x140039696`
- `FLTMGR!FltReleaseContext` at `0x140039724`

## pseudocode

```c
__int64 __fastcall WofPostQueryInfoCallback(__int64 a1, __int64 a2)
{
  struct _EX_RUNDOWN_REF *v4; // rsi
  int v5; // ecx
  int v6; // edi
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  bool v9; // r15
  _DWORD *v11; // r12
  int v12; // eax
  int v13; // r13d
  __int64 v14; // r8
  __int64 v15; // r10
  unsigned int *v16; // r11
  int v17; // edx
  int v18; // r9d
  int v19; // r8d
  unsigned int v20; // edi
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  __int64 (__fastcall *v24)(char *, char *, _QWORD); // rax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int *v28; // rdi
  __int64 v29; // rax
  unsigned int v30; // r12d
  _WORD *v31; // r15
  char *v32; // r13
  unsigned int v33; // r14d
  char *v34; // rdi
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-58h] BYREF
  PFLT_CONTEXT v40; // [rsp+38h] [rbp-50h] BYREF
  struct _EX_RUNDOWN_REF *v41; // [rsp+40h] [rbp-48h]
  __int128 v42; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v43; // [rsp+90h] [rbp+8h]

  Context = 0;
  v4 = 0;
  v41 = 0;
  v5 = *(_DWORD *)(a1 + 24);
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147483643 )
    goto LABEL_6;
  v6 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
  v7 = (unsigned int)(v6 - 18);
  if ( (unsigned int)v7 > 0x3B || (v8 = 0x814000000030411LL, !_bittest64(&v8, v7)) )
  {
    if ( (unsigned int)(v6 - 4) > 1 )
      goto LABEL_6;
  }
  v9 = 1;
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    v11 = Context;
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v11 + 32LL));
    v12 = v11[2] & 0xF000000;
    if ( v12 == 0x1000000 )
    {
      v9 = 0;
    }
    else
    {
      if ( v12 == 0x2000000 )
      {
        v13 = 0;
        v9 = *(_QWORD *)(a2 + 40) == *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 16LL) + 56LL);
LABEL_19:
        if ( (v11[2] & 0x20) != 0 )
          v9 = 1;
LABEL_21:
        if ( v13 >= 0 && (v11[2] & 2) == 0 )
        {
          if ( v9 )
          {
            v4 = (struct _EX_RUNDOWN_REF *)WofAcquireFileSystemRundown(*(_QWORD *)(a2 + 32));
            v41 = v4;
          }
          else
          {
            v4 = (struct _EX_RUNDOWN_REF *)(*(_QWORD *)v11 + 24LL);
            v41 = v4;
            ExAcquireRundownProtection(v4);
          }
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v11 + 32LL));
        KeLeaveCriticalRegion();
        if ( v13 < 0 )
        {
          *(_DWORD *)(a1 + 24) = v13;
          goto LABEL_6;
        }
        if ( (*((_DWORD *)Context + 2) & 2) == 0 && v9 && v6 != 22 )
          goto LABEL_6;
        goto LABEL_27;
      }
      if ( *(_QWORD *)(a2 + 40) )
      {
        v40 = 0;
        if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v40) != -1073741275 )
        {
          if ( (*(_DWORD *)v40 & 1) != 0 )
          {
            FltReleaseContext(v40);
            v13 = -1072103421;
            goto LABEL_21;
          }
          if ( (*(_DWORD *)v40 & 2) != 0 && v11[3] < 4u )
          {
            FltReleaseContext(v40);
            v9 = 0;
          }
          else
          {
            FltReleaseContext(v40);
          }
        }
      }
    }
    v13 = 0;
    goto LABEL_19;
  }
  if ( v6 != 22 )
    goto LABEL_6;
  v40 = 0;
  if ( (int)WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &v40) < 0 )
    goto LABEL_6;
  if ( (*((_DWORD *)v40 + 14) & 1) != 0 )
  {
    FltReleaseContext(v40);
    goto LABEL_6;
  }
  FltReleaseContext(v40);
LABEL_27:
  v15 = *(_QWORD *)(a1 + 16);
  v16 = *(unsigned int **)(v15 + 40);
  v40 = v16;
  if ( v6 == 22 )
  {
    if ( Context )
    {
      if ( !v9 && (*((_DWORD *)Context + 2) & 2) == 0 )
      {
        v26 = *((unsigned int *)Context + 3);
        if ( (unsigned int)v26 < 4 )
        {
          v27 = 53 * v26;
          if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v27 * 8) )
          {
            v28 = v16;
            if ( qword_14001A280[v27 + 1] )
            {
              while ( 1 )
              {
                if ( v28[1] == 14 && RtlCompareMemory(v28 + 6, L"::$DATA", 0xEu) == 14 )
                {
                  v38 = ((__int64 (__fastcall *)(char *, unsigned int *, _QWORD))qword_14001A280[53
                                                                                               * *((unsigned int *)Context
                                                                                                 + 3)
                                                                                               + 1])(
                          (char *)Context + 64,
                          v28 + 4,
                          0);
                  if ( v38 < 0 )
                    break;
                }
                v29 = *v28;
                if ( (_DWORD)v29 )
                {
                  v28 = (unsigned int *)((char *)v28 + v29);
                  if ( v28 )
                    continue;
                }
                goto LABEL_87;
              }
              *(_DWORD *)(a1 + 24) = v38;
LABEL_87:
              v16 = (unsigned int *)v40;
            }
          }
        }
      }
    }
    if ( *(int *)(a1 + 24) >= 0 && *(_QWORD *)(a1 + 32) )
    {
      v42 = 0;
      v20 = 0;
      v43 = 0;
LABEL_36:
      v21 = 424LL * v20;
      if ( !*(PVOID *)((char *)&WPP_MAIN_CB.Dpc.DeferredContext + v21) )
        goto LABEL_37;
      v30 = 0;
      v31 = v16;
      v32 = (char *)&WPP_MAIN_CB.Dpc.DeferredContext + v21;
      v33 = 0;
      v34 = (char *)v40;
      while ( 1 )
      {
        *((_QWORD *)&v42 + 1) = v31 + 12;
        WORD1(v42) = v31[2];
        LOWORD(v42) = WORD1(v42);
        v35 = *((unsigned int *)v31 + 1);
        if ( (unsigned int)v35 > 0xC && RtlCompareMemory((char *)v31 + v35 + 12, L":$DATA", 0xCu) == 12 )
          LOWORD(v42) = v42 - 12;
        LOBYTE(v14) = 1;
        v36 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64))v32)(0, &v42, v14);
        v37 = *(unsigned int *)v31;
        if ( v36 == -1073741275 )
        {
          if ( !(_DWORD)v37 )
          {
            *(_DWORD *)&v34[v33] = 0;
            LODWORD(v37) = *(_DWORD *)(a1 + 32) - v30;
          }
          *(_QWORD *)(a1 + 32) -= (unsigned int)v37;
          v14 = *(_QWORD *)(a1 + 32);
          if ( v14 == v30 )
          {
LABEL_94:
            v4 = v41;
            v20 = v43;
            if ( !*(_QWORD *)(a1 + 32) )
              break;
LABEL_37:
            v43 = ++v20;
            v16 = (unsigned int *)v40;
            if ( v20 >= 4 )
              break;
            goto LABEL_36;
          }
          memmove(v31, (char *)v31 + *(unsigned int *)v31, v14 - v30);
        }
        else
        {
          if ( !(_DWORD)v37 )
            goto LABEL_94;
          v33 = v30;
          v30 += v37;
          v31 = (_WORD *)((char *)v31 + v37);
        }
        if ( !v31 )
          goto LABEL_94;
      }
    }
  }
  else
  {
    if ( v6 == 68 )
    {
LABEL_39:
      v17 = 60;
      v19 = 56;
LABEL_40:
      v18 = 40;
    }
    else
    {
      v17 = -1;
      if ( v6 == 34 )
      {
        v19 = 48;
        v18 = 32;
      }
      else
      {
        v18 = -1;
        if ( v6 == 4 )
        {
          v19 = 32;
        }
        else
        {
          v19 = -1;
          switch ( v6 )
          {
            case 5:
            case 28:
              v18 = 0;
              break;
            case 18:
              v19 = 32;
              goto LABEL_40;
            case 35:
              v19 = 0;
              v17 = 4;
              break;
            case 70:
            case 77:
              goto LABEL_39;
            default:
              break;
          }
        }
      }
    }
    if ( v19 >= 0
      && (*(_DWORD *)(a1 + 24) != -2147483643 || *(unsigned int *)(v15 + 24) >= (unsigned __int64)(v19 + 4LL)) )
    {
      v22 = *(unsigned int *)((char *)v16 + v19);
      if ( byte_140018454 )
        v22 &= ~0x400u;
      if ( byte_140018455 && (*((_DWORD *)Context + 2) & 2) == 0 )
        v22 &= ~0x200u;
      if ( !v22 )
        v22 = 128;
      *(unsigned int *)((char *)v16 + v19) = v22;
    }
    if ( byte_140018454
      && v17 >= 0
      && (*(_DWORD *)(a1 + 24) != -2147483643
       || *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL) >= (unsigned __int64)(v17 + 4LL)) )
    {
      *(unsigned int *)((char *)v16 + v17) = 0;
    }
    if ( v18 >= 0
      && (*(_DWORD *)(a1 + 24) != -2147483643
       || *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL) >= (unsigned __int64)(v18 + 8LL))
      && (*((_DWORD *)Context + 2) & 2) == 0 )
    {
      v23 = *((unsigned int *)Context + 3);
      if ( (unsigned int)v23 < 4 )
      {
        if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * v23) )
        {
          v24 = (__int64 (__fastcall *)(char *, char *, _QWORD))qword_14001A280[53 * v23 + 1];
          if ( v24 )
          {
            v25 = v24((char *)Context + 64, (char *)v16 + v18, 0);
            if ( v25 < 0 )
              *(_DWORD *)(a1 + 24) = v25;
          }
        }
      }
    }
  }
LABEL_6:
  if ( v4 )
    ExReleaseRundownProtection(v4);
  if ( Context )
    FltReleaseContext(Context);
  return 0;
}

```

## disassembly

```asm
0x140038fe0  mov     [rsp+arg_8], rbx
0x140038fe5  mov     [rsp+arg_10], rsi
0x140038fea  mov     [rsp+arg_0], rcx
0x140038fef  push    rdi
0x140038ff0  push    r12
0x140038ff2  push    r13
0x140038ff4  push    r14
0x140038ff6  push    r15
0x140038ff8  sub     rsp, 60h
0x140038ffc  mov     r14, rdx
0x140038fff  mov     rbx, rcx
0x140039002  mov     [rsp+88h+Context], 0
0x14003900b  xor     esi, esi
0x14003900d  mov     [rsp+88h+var_48], rsi
0x140039012  mov     ecx, [rcx+18h]
0x140039015  mov     edx, 80000000h
0x14003901a  lea     eax, [rcx+rdx]
0x14003901d  test    edx, eax
0x14003901f  jz      short loc_14003909D
0x140039021  mov     rax, [rbx+10h]
0x140039025  mov     edi, [rax+20h]
0x140039028  lea     eax, [rdi-12h]
0x14003902b  cmp     eax, 3Bh ; ';'
0x14003902e  ja      loc_140039713
0x140039034  mov     rcx, 814000000030411h
0x14003903e  bt      rcx, rax
0x140039042  jnb     loc_140039713
0x140039048  mov     r15b, 1
0x14003904b  lea     r8, [rsp+88h+Context]; Context
0x140039050  mov     rdx, [r14+20h]; FileObject
0x140039054  mov     rcx, [r14+18h]; Instance
0x140039058  call    cs:__imp_FltGetStreamContext
0x14003905f  nop     dword ptr [rax+rax+00h]
0x140039064  test    eax, eax
0x140039066  jns     loc_140039103
0x14003906c  cmp     edi, 16h
0x14003906f  jz      short loc_1400390CA
0x140039071  test    rsi, rsi
0x140039074  jnz     short loc_1400390AB
0x140039076  mov     rcx, [rsp+88h+Context]; Context
0x14003907b  test    rcx, rcx
0x14003907e  jnz     short loc_1400390BC
0x140039080  xor     eax, eax
0x140039082  lea     r11, [rsp+88h+var_28]
0x140039087  mov     rbx, [r11+38h]
0x14003908b  mov     rsi, [r11+40h]
0x14003908f  mov     rsp, r11
0x140039092  pop     r15
0x140039094  pop     r14
0x140039096  pop     r13
0x140039098  pop     r12
0x14003909a  pop     rdi
0x14003909b  retn
0x14003909d  cmp     ecx, 80000005h
0x1400390a3  jz      loc_140039021
0x1400390a9  jmp     short loc_140039071
0x1400390ab  mov     rcx, rsi; RunRef
0x1400390ae  call    cs:__imp_ExReleaseRundownProtection
0x1400390b5  nop     dword ptr [rax+rax+00h]
0x1400390ba  jmp     short loc_140039076
0x1400390bc  call    cs:__imp_FltReleaseContext
0x1400390c3  nop     dword ptr [rax+rax+00h]
0x1400390c8  jmp     short loc_140039080
0x1400390ca  mov     [rsp+88h+var_50], rsi
0x1400390cf  lea     rdx, [rsp+88h+var_50]
0x1400390d4  mov     rcx, [r14+18h]; Instance
0x1400390d8  call    WofGetVolumeContext
0x1400390dd  test    eax, eax
0x1400390df  js      short loc_140039071
0x1400390e1  mov     rcx, [rsp+88h+var_50]; Context
0x1400390e6  mov     eax, [rcx+38h]
0x1400390e9  test    r15b, al
0x1400390ec  jz      loc_1400393F8
0x1400390f2  call    cs:__imp_FltReleaseContext
0x1400390f9  nop     dword ptr [rax+rax+00h]
0x1400390fe  jmp     loc_140039071
0x140039103  mov     r12, [rsp+88h+Context]
0x140039108  call    cs:__imp_KeEnterCriticalRegion
0x14003910f  nop     dword ptr [rax+rax+00h]
0x140039114  mov     rcx, [r12]
0x140039118  add     rcx, 20h ; ' '; FastMutex
0x14003911c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140039123  nop     dword ptr [rax+rax+00h]
0x140039128  mov     eax, [r12+8]
0x14003912d  and     eax, 0F000000h
0x140039132  cmp     eax, 1000000h
0x140039137  jnz     loc_140039420
0x14003913d  xor     r15b, r15b
0x140039140  xor     r13d, r13d
0x140039143  mov     eax, [r12+8]
0x140039148  test    al, 20h
0x14003914a  jz      short loc_14003914F
0x14003914c  mov     r15b, 1
0x14003914f  test    r13d, r13d
0x140039152  js      short loc_140039182
0x140039154  mov     eax, [r12+8]
0x140039159  test    al, 2
0x14003915b  jnz     short loc_140039182
0x14003915d  test    r15b, r15b
0x140039160  jnz     loc_140039654
0x140039166  mov     rsi, [r12]
0x14003916a  add     rsi, 18h
0x14003916e  mov     [rsp+88h+var_48], rsi
0x140039173  mov     rcx, rsi; RunRef
0x140039176  call    cs:__imp_ExAcquireRundownProtection
0x14003917d  nop     dword ptr [rax+rax+00h]
0x140039182  mov     rcx, [r12]
0x140039186  add     rcx, 20h ; ' '; FastMutex
0x14003918a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140039191  nop     dword ptr [rax+rax+00h]
0x140039196  call    cs:__imp_KeLeaveCriticalRegion
0x14003919d  nop     dword ptr [rax+rax+00h]
0x1400391a2  test    r13d, r13d
0x1400391a5  js      loc_140039738
0x1400391ab  mov     rax, [rsp+88h+Context]
0x1400391b0  mov     ecx, [rax+8]
0x1400391b3  test    cl, 2
0x1400391b6  jz      loc_140039409
0x1400391bc  mov     r10, [rbx+10h]
0x1400391c0  mov     r11, [r10+28h]
0x1400391c4  mov     [rsp+88h+var_50], r11
0x1400391c9  cmp     edi, 16h
0x1400391cc  jz      short loc_140039203
0x1400391ce  lea     r14, cs:140000000h
0x1400391d5  cmp     edi, 44h ; 'D'
0x1400391d8  jz      loc_140039271; jumptable 00000001400395FA cases 70,77
0x1400391de  mov     edx, 0FFFFFFFFh
0x1400391e3  cmp     edi, 22h ; '"'
0x1400391e6  jz      loc_140039485
0x1400391ec  mov     r9d, edx
0x1400391ef  cmp     edi, 4
0x1400391f2  jnz     loc_1400395D4
0x1400391f8  mov     r8d, 20h ; ' '
0x1400391fe  jmp     def_1400395FA; jumptable 00000001400395FA default case, cases 6-17,19-27,29-34,36-69,71-76
0x140039203  mov     rcx, [rsp+88h+Context]
0x140039208  test    rcx, rcx
0x14003920b  jnz     loc_140039496
0x140039211  lea     r14, cs:140000000h
0x140039218  cmp     dword ptr [rbx+18h], 0
0x14003921c  jl      loc_140039071
0x140039222  cmp     qword ptr [rbx+20h], 0
0x140039227  jbe     loc_140039071
0x14003922d  xorps   xmm0, xmm0
0x140039230  movups  [rsp+88h+var_40], xmm0
0x140039235  xor     edi, edi
0x140039237  mov     dword ptr [rsp+88h+arg_0], edi
0x14003923e  xchg    ax, ax
0x140039240  mov     eax, edi
0x140039242  imul    rcx, rax, 1A8h
0x140039249  cmp     qword ptr [rcx+r14+1A1C8h], 0
0x140039252  jnz     loc_14003950E
0x140039258  inc     edi
0x14003925a  mov     dword ptr [rsp+88h+arg_0], edi
0x140039261  cmp     edi, 4
0x140039264  mov     r11, [rsp+88h+var_50]
0x140039269  jnb     loc_140039071
0x14003926f  jmp     short loc_140039240
0x140039271  mov     edx, 3Ch ; '<'; jumptable 00000001400395FA cases 70,77
0x140039276  mov     r8d, 38h ; '8'
0x14003927c  mov     r9d, 28h ; '('
0x140039282  test    r8d, r8d; jumptable 00000001400395FA default case, cases 6-17,19-27,29-34,36-69,71-76
0x140039285  js      short loc_1400392DA
0x140039287  cmp     dword ptr [rbx+18h], 80000005h
0x14003928e  jz      loc_14003937A
0x140039294  movsxd  r8, r8d
0x140039297  mov     rax, [rsp+88h+Context]
0x14003929c  mov     ecx, [rax+8]
0x14003929f  and     ecx, 2
0x1400392a2  mov     eax, [r8+r11]
0x1400392a6  mov     [rsp+88h+var_68], eax
0x1400392aa  cmp     cs:byte_140018454, 0
0x1400392b1  jz      short loc_1400392BB
0x1400392b3  btr     eax, 0Ah
0x1400392b7  mov     [rsp+88h+var_68], eax
0x1400392bb  cmp     cs:byte_140018455, 0
0x1400392c2  jnz     loc_140039365
0x1400392c8  mov     ecx, 80h
0x1400392cd  test    eax, eax
0x1400392cf  cmovz   eax, ecx
0x1400392d2  mov     [rsp+88h+var_68], eax
0x1400392d6  mov     [r8+r11], eax
0x1400392da  cmp     cs:byte_140018454, 0
0x1400392e1  jz      short loc_1400392EB
0x1400392e3  test    edx, edx
0x1400392e5  jns     loc_140039393
0x1400392eb  test    r9d, r9d
0x1400392ee  js      loc_1400393DE
0x1400392f4  cmp     dword ptr [rbx+18h], 80000005h
0x1400392fb  jz      loc_1400393AC
0x140039301  mov     rax, [rsp+88h+Context]
0x140039306  mov     ecx, [rax+8]
0x140039309  test    cl, 2
0x14003930c  jnz     loc_1400393DE
0x140039312  mov     rcx, [rsp+88h+Context]
0x140039317  mov     eax, [rcx+0Ch]
0x14003931a  cmp     eax, 4
0x14003931d  jnb     loc_1400393DE
0x140039323  imul    rdx, rax, 1A8h
0x14003932a  cmp     byte ptr [rdx+r14+1A140h], 0
0x140039333  jz      loc_1400393DE
0x140039339  mov     rax, [rdx+r14+1A288h]
0x140039341  test    rax, rax
0x140039344  jz      loc_1400393DE
0x14003934a  movsxd  rdx, r9d
0x14003934d  add     rdx, r11
0x140039350  add     rcx, 40h ; '@'
0x140039354  xor     r8d, r8d
0x140039357  call    _guard_dispatch_icall
0x14003935c  test    eax, eax
0x14003935e  jns     short loc_1400393DE
0x140039360  mov     [rbx+18h], eax
0x140039363  jmp     short loc_1400393DE
0x140039365  test    ecx, ecx
0x140039367  jnz     loc_1400392C8
0x14003936d  btr     eax, 9
0x140039371  mov     [rsp+88h+var_68], eax
0x140039375  jmp     loc_1400392C8
0x14003937a  mov     ecx, [r10+18h]
0x14003937e  movsxd  rax, r8d
0x140039381  add     rax, 4
0x140039385  cmp     rcx, rax
0x140039388  jb      loc_1400392DA
0x14003938e  jmp     loc_140039294
0x140039393  cmp     dword ptr [rbx+18h], 80000005h
0x14003939a  jz      short loc_1400393C5
0x14003939c  movsxd  rax, edx
0x14003939f  mov     dword ptr [rax+r11], 0
0x1400393a7  jmp     loc_1400392EB
0x1400393ac  mov     rax, [rbx+10h]
0x1400393b0  mov     ecx, [rax+18h]
0x1400393b3  movsxd  rax, r9d
0x1400393b6  add     rax, 8
0x1400393ba  cmp     rcx, rax
0x1400393bd  jnb     loc_140039301
0x1400393c3  jmp     short loc_1400393DE
0x1400393c5  mov     rax, [rbx+10h]
0x1400393c9  mov     ecx, [rax+18h]
0x1400393cc  movsxd  rax, edx
0x1400393cf  add     rax, 4
0x1400393d3  cmp     rcx, rax
0x1400393d6  jb      loc_1400392EB
0x1400393dc  jmp     short loc_14003939C
0x1400393de  jmp     loc_140039071
0x1400393e3  mov     rcx, [rsp+88h+arg_0]
0x1400393eb  mov     [rcx+18h], eax
0x1400393ee  mov     rsi, [rsp+88h+var_48]
0x1400393f3  jmp     loc_140039071
0x1400393f8  call    cs:__imp_FltReleaseContext
0x1400393ff  nop     dword ptr [rax+rax+00h]
0x140039404  jmp     loc_1400391BC
0x140039409  test    r15b, r15b
0x14003940c  jz      loc_1400391BC
0x140039412  cmp     edi, 16h
0x140039415  jz      loc_1400391BC
0x14003941b  jmp     loc_140039071
0x140039420  cmp     eax, 2000000h
0x140039425  jz      loc_14003966A
0x14003942b  cmp     [r14+28h], rsi
0x14003942f  jz      loc_140039140
0x140039435  mov     [rsp+88h+var_50], rsi
0x14003943a  lea     r8, [rsp+88h+var_50]; Context
0x14003943f  mov     rdx, [r14+20h]; FileObject
0x140039443  mov     rcx, [r14+18h]; Instance
0x140039447  call    cs:__imp_FltGetStreamHandleContext
0x14003944e  nop     dword ptr [rax+rax+00h]
0x140039453  cmp     eax, 0C0000225h
0x140039458  jz      loc_140039140
0x14003945e  mov     rcx, [rsp+88h+var_50]; Context
0x140039463  mov     eax, [rcx]
0x140039465  test    r15b, al
0x140039468  jz      loc_140039686
0x14003946e  call    cs:__imp_FltReleaseContext
0x140039475  nop     dword ptr [rax+rax+00h]
0x14003947a  mov     r13d, 0C0190003h
0x140039480  jmp     loc_14003914F
0x140039485  mov     r8d, 30h ; '0'
0x14003948b  mov     r9d, 20h ; ' '
0x140039491  jmp     def_1400395FA; jumptable 00000001400395FA default case, cases 6-17,19-27,29-34,36-69,71-76
0x140039496  test    r15b, r15b
0x140039499  jnz     loc_140039211
0x14003949f  mov     eax, [rcx+8]
0x1400394a2  test    al, 2
0x1400394a4  jnz     loc_140039211
0x1400394aa  mov     rax, [rsp+88h+Context]
0x1400394af  mov     ecx, [rax+0Ch]
0x1400394b2  lea     r14, cs:140000000h
0x1400394b9  cmp     ecx, 4
0x1400394bc  jnb     loc_140039218
0x1400394c2  imul    rcx, 1A8h
0x1400394c9  cmp     [rcx+r14+1A140h], r15b
0x1400394d1  jz      loc_140039218
0x1400394d7  mov     rdi, r11
0x1400394da  cmp     qword ptr [rcx+r14+1A288h], 0
0x1400394e3  jz      loc_140039218
0x1400394e9  nop     dword ptr [rax+00000000h]
0x1400394f0  cmp     dword ptr [rdi+4], 0Eh
0x1400394f4  jz      loc_1400396A7
0x1400394fa  mov     eax, [rdi]
0x1400394fc  test    eax, eax
0x1400394fe  jnz     loc_140039705
  ... truncated ...
```
