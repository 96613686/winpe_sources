# Bulk_Transfer_CompleteCancelable

- ea: `0x1400095a0`
- end: `0x140009a83`
- name: `Bulk_Transfer_CompleteCancelable`
- size: `1251`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006e40`
- `0x140007c88`
- `0x1400082d0`
- `0x140009ea4`
- `0x14000c0c0`

## callees

- `0x1400095a0`
- `0x140009a90`
- `0x140033854`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14000972e`
- `ntoskrnl!KfRaiseIrql` at `0x14000972e`
- `ntoskrnl!KeLowerIrql` at `0x140009763`
- `ntoskrnl!KeLowerIrql` at `0x140009763`
- `ntoskrnl!IoFreeMdl` at `0x1400097c0`
- `ntoskrnl!IoFreeMdl` at `0x1400097c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000961a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000970f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000961a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000970f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400096d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009773`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400096d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009773`

## pseudocode

```c
void __fastcall Bulk_Transfer_CompleteCancelable(__int64 a1, __int64 *a2, int a3, char a4)
{
  int v5; // edi
  __int64 *v7; // rax
  __int64 **v8; // rcx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v13; // eax
  int v14; // eax
  _QWORD *v15; // rdi
  __int64 v16; // rbp
  _QWORD *v17; // rdx
  struct _MDL *v18; // rcx
  KIRQL v19; // di
  __int64 v20; // r8
  __int64 v21; // rsi
  __int64 **v22; // rax
  __int64 v23; // rcx
  __int64 **v24; // rax
  __int64 v25; // rdx
  int v26; // r8d
  int v27; // eax

  v5 = a3;
  if ( *((_DWORD *)a2 + 16) == 1 )
  {
    v7 = (__int64 *)*a2;
    if ( *(__int64 **)(*a2 + 8) == a2 )
    {
      v8 = (__int64 **)a2[1];
      if ( *v8 == a2 )
      {
        *v8 = v7;
        v7[1] = (__int64)v8;
        if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 2048))(WdfDriverGlobals, a2[3]) >= 0 )
        {
          *((_DWORD *)a2 + 16) = 0;
          goto LABEL_6;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v25 = *(_QWORD *)(a1 + 48);
          v26 = *(unsigned __int8 *)(v25 + 143);
          LOBYTE(v25) = 4;
          WPP_RECORDER_SF_DDDqd(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL), v25, v26, 43);
        }
        v21 = a1 + 392;
        *((_DWORD *)a2 + 16) = 2;
        v22 = *(__int64 ***)(v21 + 8);
        if ( *v22 == (__int64 *)v21 )
        {
          *a2 = v21;
          a2[1] = (__int64)v22;
          *v22 = a2;
          *(_QWORD *)(v21 + 8) = a2;
          return;
        }
      }
    }
LABEL_19:
    __fastfail(3u);
  }
  if ( *((_DWORD *)a2 + 16) == 3 )
  {
    if ( !a4 )
      return;
    v23 = *a2;
    v5 = -1073676288;
    if ( a3 != -1 )
      v5 = a3;
    if ( *(__int64 **)(v23 + 8) != a2 )
      goto LABEL_19;
    v24 = (__int64 **)a2[1];
    if ( *v24 != a2 )
      goto LABEL_19;
    *v24 = (__int64 *)v23;
    *(_QWORD *)(v23 + 8) = v24;
  }
LABEL_6:
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
  v11 = a2[6];
  if ( *(_WORD *)(v11 + 2) == 56 )
  {
LABEL_7:
    v12 = (_DWORD *)(v11 + 36);
  }
  else
  {
    switch ( *(_WORD *)(v11 + 2) )
    {
      case '9':
      case ':':
        v12 = (_DWORD *)(v11 + 52);
        break;
      default:
        goto LABEL_7;
    }
  }
  *v12 = *((_DWORD *)a2 + 27);
  v13 = *((_DWORD *)a2 + 17);
  if ( v13 != 28 )
  {
    switch ( v13 )
    {
      case 0:
        *(_DWORD *)(v11 + 4) = v5;
        if ( v5 == 1 )
          goto LABEL_12;
        if ( v5 <= -1073738240 )
        {
          if ( v5 == -1073738240 )
          {
            v14 = -1073741637;
            goto LABEL_13;
          }
          if ( v5 == -1073739264 || v5 == -2147483136 || v5 == -2147482880 || v5 == -2147482112 )
          {
            v14 = -1073741811;
            goto LABEL_13;
          }
        }
        else
        {
          switch ( v5 )
          {
            case -1073676288:
              v14 = -1073741536;
              goto LABEL_13;
            case -1073737728:
              v14 = -1073741670;
              goto LABEL_13;
            case -1073713152:
              v14 = -1073741810;
              goto LABEL_13;
            case 0:
              goto LABEL_12;
          }
        }
LABEL_33:
        v14 = -1073741823;
        goto LABEL_13;
      case 1:
      case 13:
      case 26:
        break;
      case 2:
        *(_DWORD *)(v11 + 4) = -1073741805;
        goto LABEL_33;
      case 3:
      case 31:
        *(_DWORD *)(v11 + 4) = -1073741806;
        v14 = -1073741823;
        goto LABEL_13;
      case 6:
        *(_DWORD *)(v11 + 4) = -1073741820;
        v14 = -1073741823;
        goto LABEL_13;
      case 10:
        *(_DWORD *)(v11 + 4) = -1073741803;
        goto LABEL_33;
      case 20:
        *(_DWORD *)(v11 + 4) = -1073741804;
        goto LABEL_33;
      case 23:
        *(_DWORD *)(v11 + 4) = -1073545216;
        v14 = -1073741823;
        goto LABEL_13;
      case 27:
        *(_DWORD *)(v11 + 4) = -1073610752;
        goto LABEL_33;
      case 34:
        *(_DWORD *)(v11 + 4) = -1073741802;
        goto LABEL_33;
      case 199:
        v27 = -1073741807;
        if ( _bittest64((const signed __int64 *)(*(_QWORD *)(a1 + 40) + 736LL), 0x3Eu) )
          v27 = -1073709056;
        *(_DWORD *)(v11 + 4) = v27;
        goto LABEL_33;
      default:
        *(_DWORD *)(v11 + 4) = -1073741807;
        goto LABEL_33;
    }
  }
  *(_DWORD *)(v11 + 4) = 0;
LABEL_12:
  v14 = 0;
LABEL_13:
  *((_DWORD *)a2 + 18) = v14;
  ++*(_DWORD *)(a1 + 248);
  *(_QWORD *)(a1 + 256) += *((unsigned int *)a2 + 27);
  if ( *((int *)a2 + 18) < 0 )
    ++*(_DWORD *)(a1 + 252);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DDDqdD(
      *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
      *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL),
      v9,
      v10);
  v15 = (_QWORD *)a2[12];
  if ( v15 )
  {
    v16 = a2[7];
    *(_BYTE *)(v16 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v16 + 96));
    v17 = *(_QWORD **)(v16 + 232);
    if ( *v17 != v16 + 224 )
      goto LABEL_19;
    *v15 = v16 + 224;
    v15[1] = v17;
    *v17 = v15;
    *(_QWORD *)(v16 + 232) = v15;
    KeReleaseSpinLock((PKSPIN_LOCK)(v16 + 96), *(_BYTE *)(v16 + 104));
    a2[12] = 0;
  }
  v18 = (struct _MDL *)a2[10];
  if ( v18 )
  {
    v20 = a2[6];
    if ( *(_WORD *)(v20 + 2) != 56 )
    {
      switch ( *(_WORD *)(v20 + 2) )
      {
        case '9':
        case ':':
          goto LABEL_26;
        default:
          break;
      }
    }
    if ( v18 != *(struct _MDL **)(v20 + 48) )
    {
LABEL_26:
      if ( v18 != *(struct _MDL **)(a2[7] + 120) )
      {
        IoFreeMdl(v18);
        a2[10] = 0;
      }
    }
  }
  *((_BYTE *)a2 + 16) = 0;
  v19 = KfRaiseIrql(2u);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
    WdfDriverGlobals,
    a2[3],
    *((unsigned int *)a2 + 18));
  KeLowerIrql(v19);
  *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
}

```

## disassembly

```asm
0x1400095a0  push    rbx
0x1400095a2  push    rbp
0x1400095a3  push    rsi
0x1400095a4  push    rdi
0x1400095a5  push    r12
0x1400095a7  push    r14
0x1400095a9  push    r15
0x1400095ab  sub     rsp, 60h
0x1400095af  mov     rsi, rcx
0x1400095b2  xor     r15d, r15d
0x1400095b5  mov     ecx, [rdx+40h]
0x1400095b8  mov     edi, r8d
0x1400095bb  mov     rbx, rdx
0x1400095be  sub     ecx, 1
0x1400095c1  jnz     loc_14000997E
0x1400095c7  mov     rax, [rdx]
0x1400095ca  cmp     [rax+8], rdx
0x1400095ce  jnz     loc_1400096F2
0x1400095d4  mov     rcx, [rdx+8]
0x1400095d8  cmp     [rcx], rdx
0x1400095db  jnz     loc_1400096F2
0x1400095e1  mov     [rcx], rax
0x1400095e4  mov     [rax+8], rcx
0x1400095e8  mov     rax, cs:WdfFunctions_01033
0x1400095ef  mov     rdx, [rdx+18h]
0x1400095f3  mov     rcx, cs:WdfDriverGlobals
0x1400095fa  mov     rax, [rax+800h]
0x140009601  call    _guard_dispatch_icall
0x140009606  test    eax, eax
0x140009608  js      loc_140009992
0x14000960e  mov     [rbx+40h], r15d
0x140009612  movzx   edx, byte ptr [rsi+68h]; NewIrql
0x140009616  lea     rcx, [rsi+60h]; SpinLock
0x14000961a  call    cs:__imp_KeReleaseSpinLock
0x140009621  nop     dword ptr [rax+rax+00h]
0x140009626  mov     rdx, [rbx+30h]
0x14000962a  lea     r12, cs:140000000h
0x140009631  movzx   eax, word ptr [rdx+2]
0x140009635  cmp     eax, 38h ; '8'
0x140009638  jz      short def_140009903; jumptable 0000000140009903 default case, cases 8-56
0x14000963a  add     eax, 0FFFFFFF8h; switch 51 cases
0x14000963d  cmp     eax, 32h
0x140009640  jbe     loc_1400098ED
0x140009646  lea     rcx, [rdx+24h]; jumptable 0000000140009903 default case, cases 8-56
0x14000964a  mov     eax, [rbx+6Ch]
0x14000964d  mov     [rcx], eax
0x14000964f  mov     eax, [rbx+44h]
0x140009652  cmp     eax, 1Ch
0x140009655  jnz     short loc_14000965D
0x140009657  mov     [rdx+4], r15d; jumptable 000000014000967C cases 1,13,26
0x14000965b  jmp     short loc_14000968E
0x14000965d  cmp     eax, 0C7h; switch 200 cases
0x140009662  ja      def_14000967C; jumptable 000000014000967C default case, cases 4,5,7-9,11,12,14-19,21,22,24,25,28-30,32,33,35-198
0x140009668  movzx   eax, ds:(byte_140064CB4 - 140000000h)[r12+rax]
0x140009671  mov     ecx, ds:(jpt_14000967C - 140000000h)[r12+rax*4]
0x140009679  add     rcx, r12
0x14000967c  jmp     rcx; switch jump
0x140009682  mov     [rdx+4], edi; jumptable 000000014000967C case 0
0x140009685  cmp     edi, 1
0x140009688  jnz     loc_140009845
0x14000968e  mov     eax, r15d
0x140009691  mov     [rbx+48h], eax
0x140009694  inc     dword ptr [rsi+0F8h]
0x14000969a  mov     eax, [rbx+6Ch]
0x14000969d  add     [rsi+100h], rax
0x1400096a4  cmp     [rbx+48h], r15d
0x1400096a8  jl      loc_1400097F1
0x1400096ae  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400096b5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400096bc  jnz     loc_1400097FC
0x1400096c2  mov     rdi, [rbx+60h]
0x1400096c6  test    rdi, rdi
0x1400096c9  jz      short loc_14000971F
0x1400096cb  mov     rbp, [rbx+38h]
0x1400096cf  lea     rcx, [rbp+60h]; SpinLock
0x1400096d3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400096da  nop     dword ptr [rax+rax+00h]
0x1400096df  mov     [rbp+68h], al
0x1400096e2  lea     rax, [rbp+0E0h]
0x1400096e9  mov     rdx, [rax+8]
0x1400096ed  cmp     [rdx], rax
0x1400096f0  jz      short loc_1400096F9
0x1400096f2  mov     ecx, 3
0x1400096f7  int     29h; Win8: RtlFailFast(ecx)
0x1400096f9  mov     [rdi], rax
0x1400096fc  lea     rcx, [rbp+60h]; SpinLock
0x140009700  mov     [rdi+8], rdx
0x140009704  mov     [rdx], rdi
0x140009707  mov     [rax+8], rdi
0x14000970b  movzx   edx, byte ptr [rbp+68h]; NewIrql
0x14000970f  call    cs:__imp_KeReleaseSpinLock
0x140009716  nop     dword ptr [rax+rax+00h]
0x14000971b  mov     [rbx+60h], r15
0x14000971f  mov     rcx, [rbx+50h]; Mdl
0x140009723  test    rcx, rcx
0x140009726  jnz     short loc_140009792
0x140009728  mov     cl, 2; NewIrql
0x14000972a  mov     [rbx+10h], r15b
0x14000972e  call    cs:__imp_KfRaiseIrql
0x140009735  nop     dword ptr [rax+rax+00h]
0x14000973a  mov     rcx, cs:WdfFunctions_01033
0x140009741  movzx   edi, al
0x140009744  mov     r8d, [rbx+48h]
0x140009748  mov     rdx, [rbx+18h]
0x14000974c  mov     rax, [rcx+838h]
0x140009753  mov     rcx, cs:WdfDriverGlobals
0x14000975a  call    _guard_dispatch_icall
0x14000975f  movzx   ecx, dil; NewIrql
0x140009763  call    cs:__imp_KeLowerIrql
0x14000976a  nop     dword ptr [rax+rax+00h]
0x14000976f  lea     rcx, [rsi+60h]; SpinLock
0x140009773  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000977a  nop     dword ptr [rax+rax+00h]
0x14000977f  mov     [rsi+68h], al
0x140009782  add     rsp, 60h
0x140009786  pop     r15
0x140009788  pop     r14
0x14000978a  pop     r12
0x14000978c  pop     rdi
0x14000978d  pop     rsi
0x14000978e  pop     rbp
0x14000978f  pop     rbx
0x140009790  retn
0x140009792  mov     r8, [rbx+30h]
0x140009796  movzx   eax, word ptr [r8+2]
0x14000979b  cmp     eax, 38h ; '8'
0x14000979e  jz      short def_1400097EB; jumptable 00000001400097EB default case, cases 8-56
0x1400097a0  add     eax, 0FFFFFFF8h; switch 51 cases
0x1400097a3  cmp     eax, 32h
0x1400097a6  jbe     short loc_1400097D5
0x1400097a8  cmp     rcx, [r8+30h]; jumptable 00000001400097EB default case, cases 8-56
0x1400097ac  jz      loc_140009728
0x1400097b2  mov     rax, [rbx+38h]; jumptable 00000001400097EB cases 57,58
0x1400097b6  cmp     rcx, [rax+78h]
0x1400097ba  jz      loc_140009728
0x1400097c0  call    cs:__imp_IoFreeMdl
0x1400097c7  nop     dword ptr [rax+rax+00h]
0x1400097cc  mov     [rbx+50h], r15
0x1400097d0  jmp     loc_140009728
0x1400097d5  cdqe
0x1400097d7  movzx   eax, ds:(byte_140064D88 - 140000000h)[r12+rax]
0x1400097e0  mov     edx, ds:(jpt_1400097EB - 140000000h)[r12+rax*4]
0x1400097e8  add     rdx, r12
0x1400097eb  jmp     rdx; switch jump
0x1400097f1  inc     dword ptr [rsi+0FCh]
0x1400097f7  jmp     loc_1400096AE
0x1400097fc  mov     rax, [rsi+30h]
0x140009800  mov     rcx, [rsi+38h]
0x140009804  movzx   edx, byte ptr [rax+8Fh]
0x14000980b  mov     eax, [rbx+6Ch]
0x14000980e  mov     [rsp+98h+var_48], eax
0x140009812  mov     eax, [rbx+48h]
0x140009815  mov     [rsp+98h+var_50], eax
0x140009819  mov     rax, [rbx+18h]
0x14000981d  mov     [rsp+98h+var_58], rax
0x140009822  mov     eax, [rsi+40h]
0x140009825  mov     [rsp+98h+var_60], eax
0x140009829  mov     eax, [rcx+98h]
0x14000982f  mov     rcx, [rcx+50h]
0x140009833  mov     [rsp+98h+var_68], eax
0x140009837  mov     [rsp+98h+var_70], edx
0x14000983b  call    WPP_RECORDER_SF_DDDqdD
0x140009840  jmp     loc_1400096C2
0x140009845  cmp     edi, 0C0000E00h
0x14000984b  jle     short loc_140009870
0x14000984d  cmp     edi, 0C0010000h
0x140009853  jnz     short loc_14000987C
0x140009855  mov     eax, 0C0000120h
0x14000985a  jmp     loc_140009691
0x14000985f  mov     dword ptr [rdx+4], 0C0000014h; jumptable 000000014000967C case 20
0x140009866  mov     eax, 0C0000001h
0x14000986b  jmp     loc_140009691
0x140009870  jnz     short loc_1400098AB
0x140009872  mov     eax, 0C00000BBh
0x140009877  jmp     loc_140009691
0x14000987c  cmp     edi, 0C0001000h
0x140009882  jz      short loc_1400098C1
0x140009884  cmp     edi, 0C0007000h
0x14000988a  jnz     loc_140009A6A
0x140009890  mov     eax, 0C000000Eh
0x140009895  jmp     loc_140009691
0x14000989a  mov     dword ptr [rdx+4], 0C0000004h; jumptable 000000014000967C case 6
0x1400098a1  mov     eax, 0C0000001h
0x1400098a6  jmp     loc_140009691
0x1400098ab  cmp     edi, 0C0000A00h
0x1400098b1  jnz     loc_140009A41
0x1400098b7  mov     eax, 0C000000Dh
0x1400098bc  jmp     loc_140009691
0x1400098c1  mov     eax, 0C000009Ah
0x1400098c6  jmp     loc_140009691
0x1400098cb  mov     dword ptr [rdx+4], 0C0000012h; jumptable 000000014000967C cases 3,31
0x1400098d2  mov     eax, 0C0000001h
0x1400098d7  jmp     loc_140009691
0x1400098dc  mov     dword ptr [rdx+4], 0C0030000h; jumptable 000000014000967C case 23
0x1400098e3  mov     eax, 0C0000001h
0x1400098e8  jmp     loc_140009691
0x1400098ed  cdqe
0x1400098ef  movzx   eax, ds:(byte_140064DC7 - 140000000h)[r12+rax]
0x1400098f8  mov     ecx, ds:(jpt_140009903 - 140000000h)[r12+rax*4]
0x140009900  add     rcx, r12
0x140009903  jmp     rcx; switch jump
0x140009909  lea     rcx, [rdx+34h]; jumptable 0000000140009903 cases 57,58
0x14000990d  jmp     loc_14000964A
0x140009912  add     rsi, 188h
0x140009919  mov     dword ptr [rbx+40h], 2
0x140009920  mov     rax, [rsi+8]
0x140009924  cmp     [rax], rsi
0x140009927  jnz     loc_1400096F2
0x14000992d  mov     [rbx], rsi
0x140009930  mov     [rbx+8], rax
0x140009934  mov     [rax], rbx
0x140009937  mov     [rsi+8], rbx
0x14000993b  add     rsp, 60h
0x14000993f  pop     r15
0x140009941  pop     r14
0x140009943  pop     r12
0x140009945  pop     rdi
0x140009946  pop     rsi
0x140009947  pop     rbp
0x140009948  pop     rbx
0x140009949  retn
0x14000994b  mov     rcx, [rdx]
0x14000994e  cmp     r8d, 0FFFFFFFFh
0x140009952  mov     edi, 0C0010000h
0x140009957  cmovnz  edi, r8d
0x14000995b  cmp     [rcx+8], rbx
0x14000995f  jnz     loc_1400096F2
0x140009965  mov     rax, [rdx+8]
0x140009969  cmp     [rax], rbx
0x14000996c  jnz     loc_1400096F2
0x140009972  mov     [rax], rcx
0x140009975  mov     [rcx+8], rax
0x140009979  jmp     loc_140009612
0x14000997e  cmp     ecx, 2
0x140009981  jnz     loc_140009612
0x140009987  test    r9b, r9b
0x14000998a  jz      loc_140009782
0x140009990  jmp     short loc_14000994B
0x140009992  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009999  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400099a0  jz      loc_140009912
0x1400099a6  mov     rcx, [rsi+38h]
0x1400099aa  mov     r9d, 2Bh ; '+'
0x1400099b0  mov     rdx, [rsi+30h]
0x1400099b4  mov     [rsp+98h+var_50], eax
0x1400099b8  mov     rax, [rbx+18h]
0x1400099bc  mov     [rsp+98h+var_58], rax
0x1400099c1  mov     eax, [rsi+40h]
0x1400099c4  movzx   r8d, byte ptr [rdx+8Fh]
0x1400099cc  mov     dl, 4
0x1400099ce  mov     [rsp+98h+var_60], eax
0x1400099d2  mov     eax, [rcx+98h]
0x1400099d8  mov     rcx, [rcx+50h]
0x1400099dc  mov     [rsp+98h+var_68], eax
0x1400099e0  mov     [rsp+98h+var_70], r8d
0x1400099e5  call    WPP_RECORDER_SF_DDDqd
0x1400099ea  jmp     loc_140009912
0x1400099ef  mov     dword ptr [rdx+4], 0C0000013h; jumptable 000000014000967C case 2
0x1400099f6  jmp     loc_140009866
0x1400099fb  mov     dword ptr [rdx+4], 0C0020000h; jumptable 000000014000967C case 27
0x140009a02  jmp     loc_140009866
0x140009a07  mov     dword ptr [rdx+4], 0C0000015h; jumptable 000000014000967C case 10
0x140009a0e  jmp     loc_140009866
0x140009a13  mov     dword ptr [rdx+4], 0C0000016h; jumptable 000000014000967C case 34
0x140009a1a  jmp     loc_140009866
0x140009a1f  mov     rax, [rsi+28h]; jumptable 000000014000967C case 199
0x140009a23  mov     ecx, 0C0008000h
0x140009a28  bt      qword ptr [rax+2E0h], 3Eh ; '>'
0x140009a31  mov     eax, 0C0000011h
0x140009a36  cmovb   eax, ecx
0x140009a39  mov     [rdx+4], eax
0x140009a3c  jmp     loc_140009866
0x140009a41  cmp     edi, 80000200h
0x140009a47  jz      loc_1400098B7
0x140009a4d  cmp     edi, 80000300h
0x140009a53  jz      loc_1400098B7
0x140009a59  cmp     edi, 80000600h
0x140009a5f  jz      loc_1400098B7
0x140009a65  jmp     loc_140009866
0x140009a6a  test    edi, edi
0x140009a6c  jz      loc_14000968E
0x140009a72  jmp     loc_140009866
0x140009a77  mov     dword ptr [rdx+4], 0C0000011h; jumptable 000000014000967C default case, cases 4,5,7-9,11,12,14-19,21,22,24,25,28-30,32,33,35-198
0x140009a7e  jmp     loc_140009866
```
