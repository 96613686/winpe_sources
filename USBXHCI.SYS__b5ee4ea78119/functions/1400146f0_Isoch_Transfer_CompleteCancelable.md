# Isoch_Transfer_CompleteCancelable

- ea: `0x1400146f0`
- end: `0x140014bb8`
- name: `Isoch_Transfer_CompleteCancelable`
- size: `1224`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000cb4c`
- `0x14000cce0`
- `0x140011760`
- `0x140012ab0`
- `0x1400144a0`

## callees

- `0x140014270`
- `0x1400146f0`
- `0x140029410`
- `0x1400295e4`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400148b1`
- `ntoskrnl!KfRaiseIrql` at `0x1400148b1`
- `ntoskrnl!KeLowerIrql` at `0x1400148e5`
- `ntoskrnl!KeLowerIrql` at `0x1400148e5`
- `ntoskrnl!IoFreeMdl` at `0x140014885`
- `ntoskrnl!IoFreeMdl` at `0x140014885`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014773`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014aab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014773`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014aab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400148f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a72`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400148f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a72`

## pseudocode

```c
void __fastcall Isoch_Transfer_CompleteCancelable(__int64 a1, __int64 *a2, int a3, int a4, char a5, char a6)
{
  int v7; // ebp
  __int64 *v10; // rax
  __int64 **v11; // rcx
  int v12; // eax
  __int64 v13; // r10
  _DWORD *v14; // rcx
  int v15; // r8d
  __int64 v16; // r9
  unsigned int v17; // edx
  unsigned int v18; // eax
  int v19; // eax
  int v20; // eax
  struct _MDL *v21; // rcx
  __int64 v22; // r8
  KIRQL v23; // bl
  __int64 v24; // rsi
  __int64 **v25; // rax
  __int64 v26; // rcx
  __int64 **v27; // rax
  __int64 **v28; // rdx
  __int64 v29; // rdx
  int v30; // r8d

  v7 = a4;
  if ( *((_DWORD *)a2 + 16) == 1 )
  {
    v10 = (__int64 *)*a2;
    if ( *(__int64 **)(*a2 + 8) != a2 )
      goto LABEL_37;
    v11 = (__int64 **)a2[1];
    if ( *v11 != a2 )
      goto LABEL_37;
    *v11 = v10;
    v10[1] = (__int64)v11;
    v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 2048))(WdfDriverGlobals, a2[3]);
    if ( v12 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v29 = *(_QWORD *)(a1 + 48);
        v30 = *(unsigned __int8 *)(v29 + 143);
        LOBYTE(v29) = 4;
        WPP_RECORDER_SF_DDqd(
          *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
          v29,
          v30,
          17,
          (__int64)WPP_3bb012812b813cd0ec02732545724755_Traceguids,
          v30,
          *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL),
          a2[3],
          v12);
      }
      v24 = a1 + 408;
      *((_DWORD *)a2 + 16) = 2;
      v25 = *(__int64 ***)(v24 + 8);
      if ( *v25 == (__int64 *)v24 )
      {
        *a2 = v24;
        a2[1] = (__int64)v25;
        *v25 = a2;
        *(_QWORD *)(v24 + 8) = a2;
        return;
      }
      goto LABEL_37;
    }
    *((_DWORD *)a2 + 16) = 0;
LABEL_6:
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
    v13 = a2[6];
    if ( *(_WORD *)(v13 + 2) == 56 )
    {
LABEL_7:
      v14 = (_DWORD *)(v13 + 36);
    }
    else
    {
      switch ( *(_WORD *)(v13 + 2) )
      {
        case '9':
        case ':':
          v14 = (_DWORD *)(v13 + 52);
          break;
        default:
          goto LABEL_7;
      }
    }
    v15 = 0;
    v16 = v13 + 128;
    *v14 = *((_DWORD *)a2 + 21);
    v17 = 0;
    v18 = *((_DWORD *)a2 + 24);
    if ( v18 )
    {
      do
      {
        if ( a3 == -1 )
        {
          v19 = *(_DWORD *)(v16 + 12LL * v17 + 20);
          if ( v19 == -1 )
          {
            *(_DWORD *)(v16 + 12LL * v17 + 20) = -1073610752;
LABEL_32:
            ++*(_DWORD *)(v13 + 136);
            ++*(_DWORD *)(a1 + 268);
            goto LABEL_13;
          }
        }
        else
        {
          *(_DWORD *)(v16 + 12LL * v17 + 20) = a3;
          v19 = a3;
        }
        if ( v19 )
          goto LABEL_32;
        ++v15;
LABEL_13:
        ++*(_DWORD *)(a1 + 264);
        ++v17;
        v18 = *((_DWORD *)a2 + 24);
      }
      while ( v17 < v18 );
    }
    if ( v7 == -1 )
    {
      if ( *(_DWORD *)(v13 + 136) != v18 )
      {
        *(_DWORD *)(v13 + 4) = 0;
        goto LABEL_18;
      }
      *(_DWORD *)(v13 + 4) = -1073739008;
    }
    else
    {
      *(_DWORD *)(v13 + 4) = v7;
      if ( v7 == 1 )
        goto LABEL_18;
      if ( v7 <= -1073738240 )
      {
        if ( v7 == -1073738240 )
        {
          v20 = -1073741637;
          goto LABEL_19;
        }
        if ( v7 == -1073739264 || v7 == -2147483136 || v7 == -2147482880 || v7 == -2147482112 )
        {
          v20 = -1073741811;
          goto LABEL_19;
        }
      }
      else
      {
        switch ( v7 )
        {
          case -1073676288:
            v20 = -1073741536;
            goto LABEL_19;
          case -1073737728:
            v20 = -1073741670;
            goto LABEL_19;
          case -1073713152:
            v20 = -1073741810;
            goto LABEL_19;
          case 0:
LABEL_18:
            v20 = 0;
LABEL_19:
            *((_DWORD *)a2 + 17) = v20;
            ++*(_DWORD *)(a1 + 248);
            *(_QWORD *)(a1 + 256) += *((unsigned int *)a2 + 21);
            if ( *((int *)a2 + 17) < 0 )
              ++*(_DWORD *)(a1 + 252);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_DDqdDDDD(
                *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
                *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL),
                v15,
                v16);
            v21 = (struct _MDL *)a2[9];
            if ( v21 )
            {
              v22 = a2[6];
              if ( *(_WORD *)(v22 + 2) != 56 )
              {
                switch ( *(_WORD *)(v22 + 2) )
                {
                  case '9':
                  case ':':
                    goto LABEL_26;
                  default:
                    break;
                }
              }
              if ( v21 != *(struct _MDL **)(v22 + 48) )
              {
LABEL_26:
                IoFreeMdl(v21);
                a2[9] = 0;
              }
            }
            *((_BYTE *)a2 + 16) = 0;
            if ( !a6 )
            {
              v23 = KfRaiseIrql(2u);
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
                WdfDriverGlobals,
                a2[3],
                *((unsigned int *)a2 + 17));
              KeLowerIrql(v23);
LABEL_29:
              *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
              return;
            }
            *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
            v28 = *(__int64 ***)(a1 + 432);
            if ( *v28 == (__int64 *)(a1 + 424) )
            {
              *a2 = a1 + 424;
              a2[1] = (__int64)v28;
              *v28 = a2;
              *(_QWORD *)(a1 + 432) = a2;
              KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
              TR_QueueDpcForTransferCompletion(a1);
              goto LABEL_29;
            }
LABEL_37:
            __fastfail(3u);
        }
      }
    }
    v20 = -1073741823;
    goto LABEL_19;
  }
  if ( *((_DWORD *)a2 + 16) != 3 )
    goto LABEL_6;
  if ( a5 )
  {
    v26 = *a2;
    v7 = -1073676288;
    if ( a4 != -1 )
      v7 = a4;
    if ( *(__int64 **)(v26 + 8) != a2 )
      goto LABEL_37;
    v27 = (__int64 **)a2[1];
    if ( *v27 != a2 )
      goto LABEL_37;
    *v27 = (__int64 *)v26;
    *(_QWORD *)(v26 + 8) = v27;
    goto LABEL_6;
  }
}

```

## disassembly

```asm
0x1400146f0  push    rbx
0x1400146f2  push    rbp
0x1400146f3  push    rsi
0x1400146f4  push    rdi
0x1400146f5  push    r14
0x1400146f7  push    r15
0x1400146f9  sub     rsp, 78h
0x1400146fd  mov     rsi, rcx
0x140014700  xor     r15d, r15d
0x140014703  mov     ecx, [rdx+40h]
0x140014706  mov     ebp, r9d
0x140014709  mov     ebx, r8d
0x14001470c  mov     rdi, rdx
0x14001470f  sub     ecx, 1
0x140014712  jnz     loc_140014968
0x140014718  mov     rax, [rdx]
0x14001471b  cmp     [rax+8], rdx
0x14001471f  jnz     loc_140014961
0x140014725  mov     rcx, [rdx+8]
0x140014729  cmp     [rcx], rdx
0x14001472c  jnz     loc_140014961
0x140014732  mov     [rcx], rax
0x140014735  mov     [rax+8], rcx
0x140014739  mov     rax, cs:WdfFunctions_01033
0x140014740  mov     rdx, [rdx+18h]
0x140014744  mov     rcx, cs:WdfDriverGlobals
0x14001474b  mov     rax, [rax+800h]
0x140014752  call    _guard_dispatch_icall
0x140014757  test    eax, eax
0x140014759  js      loc_140014936
0x14001475f  mov     [rdi+40h], r15d
0x140014763  movzx   edx, byte ptr [rsi+68h]; NewIrql
0x140014767  lea     rcx, [rsi+60h]; SpinLock
0x14001476b  mov     [rsp+0A8h+arg_0], r12
0x140014773  call    cs:__imp_KeReleaseSpinLock
0x14001477a  nop     dword ptr [rax+rax+00h]
0x14001477f  mov     r10, [rdi+30h]
0x140014783  lea     r12, cs:140000000h
0x14001478a  movzx   eax, word ptr [r10+2]
0x14001478f  cmp     eax, 38h ; '8'
0x140014792  jz      short def_140014AFA; jumptable 0000000140014AFA default case, cases 8-56
0x140014794  add     eax, 0FFFFFFF8h; switch 51 cases
0x140014797  cmp     eax, 32h
0x14001479a  jbe     loc_140014AE4
0x1400147a0  lea     rcx, [r10+24h]; jumptable 0000000140014AFA default case, cases 8-56
0x1400147a4  mov     eax, 80h
0x1400147a9  mov     rdx, r10
0x1400147ac  mov     r8d, r15d
0x1400147af  lea     r9, [rax+rdx]
0x1400147b3  mov     eax, [rdi+54h]
0x1400147b6  mov     [rcx], eax
0x1400147b8  mov     edx, r15d
0x1400147bb  mov     eax, [rdi+60h]
0x1400147be  test    eax, eax
0x1400147c0  jz      short loc_140014806
0x1400147c2  nop     dword ptr [rax+00h]
0x1400147c6  nop     word ptr [rax+rax+00000000h]
0x1400147d0  mov     eax, edx
0x1400147d2  lea     rcx, [rax+rax*2]
0x1400147d6  cmp     ebx, 0FFFFFFFFh
0x1400147d9  jnz     loc_14001492A
0x1400147df  mov     eax, [r9+rcx*4+14h]
0x1400147e4  cmp     eax, ebx
0x1400147e6  jz      loc_140014912
0x1400147ec  test    eax, eax
0x1400147ee  jnz     loc_14001491B
0x1400147f4  inc     r8d
0x1400147f7  inc     dword ptr [rsi+108h]
0x1400147fd  inc     edx
0x1400147ff  mov     eax, [rdi+60h]
0x140014802  cmp     edx, eax
0x140014804  jb      short loc_1400147D0
0x140014806  cmp     ebp, 0FFFFFFFFh
0x140014809  jnz     short loc_14001481B
0x14001480b  cmp     [r9+8], eax
0x14001480f  jz      loc_140014B25
0x140014815  mov     [r10+4], r15d
0x140014819  jmp     short loc_140014828
0x14001481b  mov     [r10+4], ebp
0x14001481f  cmp     ebp, 1
0x140014822  jnz     loc_140014A22
0x140014828  mov     eax, r15d
0x14001482b  mov     [rdi+44h], eax
0x14001482e  inc     dword ptr [rsi+0F8h]
0x140014834  mov     eax, [rdi+54h]
0x140014837  add     [rsi+100h], rax
0x14001483e  cmp     [rdi+44h], r15d
0x140014842  jl      loc_140014A17
0x140014848  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001484f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140014856  jnz     loc_1400149C2
0x14001485c  mov     rcx, [rdi+48h]; Mdl
0x140014860  test    rcx, rcx
0x140014863  jz      short loc_140014895
0x140014865  mov     r8, [rdi+30h]
0x140014869  movzx   eax, word ptr [r8+2]
0x14001486e  cmp     eax, 38h ; '8'
0x140014871  jz      short def_140014B1F; jumptable 0000000140014B1F default case, cases 8-56
0x140014873  add     eax, 0FFFFFFF8h; switch 51 cases
0x140014876  cmp     eax, 32h
0x140014879  jbe     loc_140014B09
0x14001487f  cmp     rcx, [r8+30h]; jumptable 0000000140014B1F default case, cases 8-56
0x140014883  jz      short loc_140014895
0x140014885  call    cs:__imp_IoFreeMdl; jumptable 0000000140014B1F cases 57,58
0x14001488c  nop     dword ptr [rax+rax+00h]
0x140014891  mov     [rdi+48h], r15
0x140014895  mov     r12, [rsp+0A8h+arg_0]
0x14001489d  mov     [rdi+10h], r15b
0x1400148a1  cmp     [rsp+0A8h+arg_28], r15b
0x1400148a9  jnz     loc_140014A6E
0x1400148af  mov     cl, 2; NewIrql
0x1400148b1  call    cs:__imp_KfRaiseIrql
0x1400148b8  nop     dword ptr [rax+rax+00h]
0x1400148bd  mov     rcx, cs:WdfFunctions_01033
0x1400148c4  movzx   ebx, al
0x1400148c7  mov     r8d, [rdi+44h]
0x1400148cb  mov     rdx, [rdi+18h]
0x1400148cf  mov     rax, [rcx+838h]
0x1400148d6  mov     rcx, cs:WdfDriverGlobals
0x1400148dd  call    _guard_dispatch_icall
0x1400148e2  movzx   ecx, bl; NewIrql
0x1400148e5  call    cs:__imp_KeLowerIrql
0x1400148ec  nop     dword ptr [rax+rax+00h]
0x1400148f1  lea     rcx, [rsi+60h]; SpinLock
0x1400148f5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400148fc  nop     dword ptr [rax+rax+00h]
0x140014901  mov     [rsi+68h], al
0x140014904  add     rsp, 78h
0x140014908  pop     r15
0x14001490a  pop     r14
0x14001490c  pop     rdi
0x14001490d  pop     rsi
0x14001490e  pop     rbp
0x14001490f  pop     rbx
0x140014910  retn
0x140014912  mov     dword ptr [r9+rcx*4+14h], 0C0020000h
0x14001491b  inc     dword ptr [r9+8]
0x14001491f  inc     dword ptr [rsi+10Ch]
0x140014925  jmp     loc_1400147F7
0x14001492a  mov     [r9+rcx*4+14h], ebx
0x14001492f  mov     eax, ebx
0x140014931  jmp     loc_1400147EC
0x140014936  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001493d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140014944  jnz     loc_140014B37
0x14001494a  add     rsi, 198h
0x140014951  mov     dword ptr [rdi+40h], 2
0x140014958  mov     rax, [rsi+8]
0x14001495c  cmp     [rax], rsi
0x14001495f  jz      short loc_1400149A6
0x140014961  mov     ecx, 3
0x140014966  int     29h; Win8: RtlFailFast(ecx)
0x140014968  cmp     ecx, 2
0x14001496b  jnz     loc_140014763
0x140014971  cmp     [rsp+0A8h+arg_20], r15b
0x140014979  jz      short loc_140014904
0x14001497b  mov     rcx, [rdx]
0x14001497e  cmp     r9d, 0FFFFFFFFh
0x140014982  mov     ebp, 0C0010000h
0x140014987  cmovnz  ebp, r9d
0x14001498b  cmp     [rcx+8], rdi
0x14001498f  jnz     short loc_140014961
0x140014991  mov     rax, [rdx+8]
0x140014995  cmp     [rax], rdi
0x140014998  jnz     short loc_140014961
0x14001499a  mov     [rax], rcx
0x14001499d  mov     [rcx+8], rax
0x1400149a1  jmp     loc_140014763
0x1400149a6  mov     [rdi], rsi
0x1400149a9  mov     [rdi+8], rax
0x1400149ad  mov     [rax], rdi
0x1400149b0  mov     [rsi+8], rdi
0x1400149b4  add     rsp, 78h
0x1400149b8  pop     r15
0x1400149ba  pop     r14
0x1400149bc  pop     rdi
0x1400149bd  pop     rsi
0x1400149be  pop     rbp
0x1400149bf  pop     rbx
0x1400149c0  retn
0x1400149c2  mov     rax, [rsi+30h]
0x1400149c6  mov     rcx, [rsi+38h]
0x1400149ca  movzx   edx, byte ptr [rax+8Fh]
0x1400149d1  mov     eax, [rdi+54h]
0x1400149d4  mov     [rsp+0A8h+var_48], eax
0x1400149d8  mov     eax, [rdi+60h]
0x1400149db  mov     [rsp+0A8h+var_50], eax
0x1400149df  mov     eax, [r9]
0x1400149e2  mov     [rsp+0A8h+var_58], r8d
0x1400149e7  mov     [rsp+0A8h+var_60], eax
0x1400149eb  mov     eax, [rdi+44h]
0x1400149ee  mov     [rsp+0A8h+var_68], eax
0x1400149f2  mov     rax, [rdi+18h]
0x1400149f6  mov     [rsp+0A8h+var_70], rax
0x1400149fb  mov     eax, [rcx+98h]
0x140014a01  mov     rcx, [rcx+50h]
0x140014a05  mov     [rsp+0A8h+var_78], eax
0x140014a09  mov     [rsp+0A8h+var_80], edx
0x140014a0d  call    WPP_RECORDER_SF_DDqdDDDD
0x140014a12  jmp     loc_14001485C
0x140014a17  inc     dword ptr [rsi+0FCh]
0x140014a1d  jmp     loc_140014848
0x140014a22  cmp     ebp, 0C0000E00h
0x140014a28  jle     short loc_140014A3C
0x140014a2a  cmp     ebp, 0C0010000h
0x140014a30  jnz     short loc_140014A4C
0x140014a32  mov     eax, 0C0000120h
0x140014a37  jmp     loc_14001482B
0x140014a3c  jnz     loc_140014AC4
0x140014a42  mov     eax, 0C00000BBh
0x140014a47  jmp     loc_14001482B
0x140014a4c  cmp     ebp, 0C0001000h
0x140014a52  jz      loc_140014ADA
0x140014a58  cmp     ebp, 0C0007000h
0x140014a5e  jnz     loc_140014BAB
0x140014a64  mov     eax, 0C000000Eh
0x140014a69  jmp     loc_14001482B
0x140014a6e  lea     rcx, [rsi+60h]; SpinLock
0x140014a72  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014a79  nop     dword ptr [rax+rax+00h]
0x140014a7e  mov     [rsi+68h], al
0x140014a81  lea     rax, [rsi+1A8h]
0x140014a88  mov     rdx, [rax+8]
0x140014a8c  cmp     [rdx], rax
0x140014a8f  jnz     loc_140014961
0x140014a95  mov     [rdi], rax
0x140014a98  lea     rcx, [rsi+60h]; SpinLock
0x140014a9c  mov     [rdi+8], rdx
0x140014aa0  mov     [rdx], rdi
0x140014aa3  mov     [rax+8], rdi
0x140014aa7  movzx   edx, byte ptr [rsi+68h]; NewIrql
0x140014aab  call    cs:__imp_KeReleaseSpinLock
0x140014ab2  nop     dword ptr [rax+rax+00h]
0x140014ab7  mov     rcx, rsi
0x140014aba  call    TR_QueueDpcForTransferCompletion
0x140014abf  jmp     loc_1400148F1
0x140014ac4  cmp     ebp, 0C0000A00h
0x140014aca  jnz     loc_140014B85
0x140014ad0  mov     eax, 0C000000Dh
0x140014ad5  jmp     loc_14001482B
0x140014ada  mov     eax, 0C000009Ah
0x140014adf  jmp     loc_14001482B
0x140014ae4  cdqe
0x140014ae6  movzx   eax, ds:(byte_140064AD3 - 140000000h)[r12+rax]
0x140014aef  mov     ecx, ds:(jpt_140014AFA - 140000000h)[r12+rax*4]
0x140014af7  add     rcx, r12
0x140014afa  jmp     rcx; switch jump
0x140014b00  lea     rcx, [r10+34h]; jumptable 0000000140014AFA cases 57,58
0x140014b04  jmp     loc_1400147A4
0x140014b09  cdqe
0x140014b0b  movzx   eax, ds:(byte_140064B12 - 140000000h)[r12+rax]
0x140014b14  mov     edx, ds:(jpt_140014B1F - 140000000h)[r12+rax*4]
0x140014b1c  add     rdx, r12
0x140014b1f  jmp     rdx; switch jump
0x140014b25  mov     dword ptr [r10+4], 0C0000B00h
0x140014b2d  mov     eax, 0C0000001h
0x140014b32  jmp     loc_14001482B
0x140014b37  mov     rcx, [rsi+38h]
0x140014b3b  mov     r9d, 11h
0x140014b41  mov     rdx, [rsi+30h]
0x140014b45  mov     [rsp+0A8h+var_68], eax
0x140014b49  mov     rax, [rdi+18h]
0x140014b4d  mov     [rsp+0A8h+var_70], rax
0x140014b52  mov     eax, [rcx+98h]
0x140014b58  movzx   r8d, byte ptr [rdx+8Fh]
0x140014b60  mov     dl, 4
0x140014b62  mov     rcx, [rcx+50h]
0x140014b66  mov     [rsp+0A8h+var_78], eax
0x140014b6a  lea     rax, WPP_3bb012812b813cd0ec02732545724755_Traceguids
0x140014b71  mov     [rsp+0A8h+var_80], r8d
0x140014b76  mov     [rsp+0A8h+var_88], rax
0x140014b7b  call    WPP_RECORDER_SF_DDqd
0x140014b80  jmp     loc_14001494A
0x140014b85  cmp     ebp, 80000200h
0x140014b8b  jz      loc_140014AD0
0x140014b91  cmp     ebp, 80000300h
0x140014b97  jz      loc_140014AD0
0x140014b9d  cmp     ebp, 80000600h
0x140014ba3  jz      loc_140014AD0
0x140014ba9  jmp     short loc_140014B2D
0x140014bab  test    ebp, ebp
0x140014bad  jz      loc_140014828
0x140014bb3  jmp     loc_140014B2D
```
