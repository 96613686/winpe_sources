# Bulk_Transfer_PrepareForCompletion

- ea: `0x140009230`
- end: `0x14000958e`
- name: `Bulk_Transfer_PrepareForCompletion`
- size: `862`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009c48`

## callees

- `0x140009230`
- `0x140009a90`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400093ab`
- `ntoskrnl!IoFreeMdl` at `0x1400093ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009345`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009345`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009309`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009309`

## pseudocode

```c
void __fastcall Bulk_Transfer_PrepareForCompletion(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rdx
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  _QWORD *v9; // rdi
  __int64 v10; // rsi
  _QWORD *v11; // rcx
  struct _MDL *v12; // rcx
  __int64 v13; // r8
  int v14; // eax

  v4 = *(_QWORD *)(a2 + 48);
  if ( *(_WORD *)(v4 + 2) == 56 )
  {
LABEL_2:
    v6 = 36;
  }
  else
  {
    switch ( *(_WORD *)(v4 + 2) )
    {
      case '9':
      case ':':
        v6 = 52;
        break;
      default:
        goto LABEL_2;
    }
  }
  *(_DWORD *)(v4 + v6) = *(_DWORD *)(a2 + 108);
  v7 = *(_DWORD *)(a2 + 68);
  if ( v7 == 28 )
  {
LABEL_4:
    *(_DWORD *)(v4 + 4) = 0;
LABEL_7:
    v8 = 0;
    goto LABEL_8;
  }
  switch ( v7 )
  {
    case 0:
      *(_DWORD *)(v4 + 4) = a3;
      if ( a3 == 1 )
        goto LABEL_7;
      if ( a3 > -1073738240 )
      {
        switch ( a3 )
        {
          case -1073676288:
            v8 = -1073741536;
            goto LABEL_8;
          case -1073737728:
            v8 = -1073741670;
            goto LABEL_8;
          case -1073713152:
            v8 = -1073741810;
            goto LABEL_8;
          case 0:
            goto LABEL_7;
        }
LABEL_27:
        v8 = -1073741823;
        goto LABEL_8;
      }
      if ( a3 == -1073738240 )
      {
        v8 = -1073741637;
      }
      else
      {
        if ( a3 != -1073739264 && a3 != -2147483136 && a3 != -2147482880 && a3 != -2147482112 )
          goto LABEL_27;
        v8 = -1073741811;
      }
LABEL_8:
      *(_DWORD *)(a2 + 72) = v8;
      ++*(_DWORD *)(a1 + 248);
      *(_QWORD *)(a1 + 256) += *(unsigned int *)(a2 + 108);
      if ( *(int *)(a2 + 72) < 0 )
        ++*(_DWORD *)(a1 + 252);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_DDDqdD(
          *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
          *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL),
          a3,
          a1);
      v9 = *(_QWORD **)(a2 + 96);
      if ( v9 )
      {
        v10 = *(_QWORD *)(a2 + 56);
        *(_BYTE *)(v10 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 96));
        v11 = *(_QWORD **)(v10 + 232);
        if ( *v11 != v10 + 224 )
          __fastfail(3u);
        v9[1] = v11;
        *v9 = v10 + 224;
        *v11 = v9;
        *(_QWORD *)(v10 + 232) = v9;
        KeReleaseSpinLock((PKSPIN_LOCK)(v10 + 96), *(_BYTE *)(v10 + 104));
        *(_QWORD *)(a2 + 96) = 0;
      }
      v12 = *(struct _MDL **)(a2 + 80);
      if ( v12 )
      {
        v13 = *(_QWORD *)(a2 + 48);
        if ( *(_WORD *)(v13 + 2) != 56 )
        {
          switch ( *(_WORD *)(v13 + 2) )
          {
            case '9':
            case ':':
              goto LABEL_20;
            default:
              break;
          }
        }
        if ( v12 != *(struct _MDL **)(v13 + 48) )
        {
LABEL_20:
          if ( v12 != *(struct _MDL **)(*(_QWORD *)(a2 + 56) + 120LL) )
          {
            IoFreeMdl(v12);
            *(_QWORD *)(a2 + 80) = 0;
          }
        }
      }
      *(_BYTE *)(a2 + 16) = 0;
      return;
    case 1:
    case 13:
    case 26:
      goto LABEL_4;
    case 2:
      *(_DWORD *)(v4 + 4) = -1073741805;
      goto LABEL_27;
    case 3:
    case 31:
      *(_DWORD *)(v4 + 4) = -1073741806;
      v8 = -1073741823;
      goto LABEL_8;
    case 6:
      *(_DWORD *)(v4 + 4) = -1073741820;
      v8 = -1073741823;
      goto LABEL_8;
    case 10:
      *(_DWORD *)(v4 + 4) = -1073741803;
      goto LABEL_27;
    case 20:
      *(_DWORD *)(v4 + 4) = -1073741804;
      goto LABEL_27;
    case 23:
      *(_DWORD *)(v4 + 4) = -1073545216;
      v8 = -1073741823;
      goto LABEL_8;
    case 27:
      *(_DWORD *)(v4 + 4) = -1073610752;
      goto LABEL_27;
    case 34:
      *(_DWORD *)(v4 + 4) = -1073741802;
      goto LABEL_27;
    case 199:
      v14 = -1073741807;
      if ( _bittest64((const signed __int64 *)(*(_QWORD *)(a1 + 40) + 736LL), 0x3Eu) )
        v14 = -1073709056;
      *(_DWORD *)(v4 + 4) = v14;
      goto LABEL_27;
    default:
      *(_DWORD *)(v4 + 4) = -1073741807;
      goto LABEL_27;
  }
}

```

## disassembly

```asm
0x140009230  mov     [rsp+arg_10], rbx
0x140009235  push    rdi
0x140009236  push    r14
0x140009238  push    r15
0x14000923a  sub     rsp, 60h
0x14000923e  mov     rbx, rdx
0x140009241  lea     r15, cs:140000000h
0x140009248  mov     rdx, [rdx+30h]
0x14000924c  mov     r9, rcx
0x14000924f  movzx   eax, word ptr [rdx+2]
0x140009253  cmp     eax, 38h ; '8'
0x140009256  jz      short def_1400094D3; jumptable 00000001400094D3 default case, cases 8-56
0x140009258  add     eax, 0FFFFFFF8h; switch 51 cases
0x14000925b  cmp     eax, 32h
0x14000925e  jbe     loc_1400094BD
0x140009264  mov     ecx, 24h ; '$'; jumptable 00000001400094D3 default case, cases 8-56
0x140009269  mov     eax, [rbx+6Ch]
0x14000926c  xor     r14d, r14d
0x14000926f  mov     [rdx+rcx], eax
0x140009272  mov     eax, [rbx+44h]
0x140009275  cmp     eax, 1Ch
0x140009278  jnz     short loc_140009280
0x14000927a  mov     [rdx+4], r14d; jumptable 000000014000929F cases 1,13,26
0x14000927e  jmp     short loc_1400092B3
0x140009280  cmp     eax, 0C7h; switch 200 cases
0x140009285  ja      def_14000929F; jumptable 000000014000929F default case, cases 4,5,7-9,11,12,14-19,21,22,24,25,28-30,32,33,35-198
0x14000928b  movzx   eax, ds:(byte_140064E2E - 140000000h)[r15+rax]
0x140009294  mov     ecx, ds:(jpt_14000929F - 140000000h)[r15+rax*4]
0x14000929c  add     rcx, r15
0x14000929f  jmp     rcx; switch jump
0x1400092a5  mov     [rdx+4], r8d; jumptable 000000014000929F case 0
0x1400092a9  cmp     r8d, 1
0x1400092ad  jnz     loc_14000942F
0x1400092b3  mov     eax, r14d
0x1400092b6  mov     [rbx+48h], eax
0x1400092b9  inc     dword ptr [r9+0F8h]
0x1400092c0  mov     eax, [rbx+6Ch]
0x1400092c3  add     [r9+100h], rax
0x1400092ca  cmp     [rbx+48h], r14d
0x1400092ce  jl      loc_1400093D9
0x1400092d4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400092db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400092e2  jnz     loc_1400093E5
0x1400092e8  mov     rdi, [rbx+60h]
0x1400092ec  mov     [rsp+78h+arg_0], rbp
0x1400092f4  mov     [rsp+78h+arg_8], rsi
0x1400092fc  test    rdi, rdi
0x1400092ff  jz      short loc_140009355
0x140009301  mov     rsi, [rbx+38h]
0x140009305  lea     rcx, [rsi+60h]; SpinLock
0x140009309  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009310  nop     dword ptr [rax+rax+00h]
0x140009315  mov     [rsi+68h], al
0x140009318  lea     rax, [rsi+0E0h]
0x14000931f  mov     rcx, [rax+8]
0x140009323  cmp     [rcx], rax
0x140009326  jz      short loc_14000932F
0x140009328  mov     ecx, 3
0x14000932d  int     29h; Win8: RtlFailFast(ecx)
0x14000932f  mov     [rdi+8], rcx
0x140009333  mov     [rdi], rax
0x140009336  mov     [rcx], rdi
0x140009339  lea     rcx, [rsi+60h]; SpinLock
0x14000933d  mov     [rax+8], rdi
0x140009341  movzx   edx, byte ptr [rsi+68h]; NewIrql
0x140009345  call    cs:__imp_KeReleaseSpinLock
0x14000934c  nop     dword ptr [rax+rax+00h]
0x140009351  mov     [rbx+60h], r14
0x140009355  mov     rcx, [rbx+50h]; Mdl
0x140009359  test    rcx, rcx
0x14000935c  jnz     short loc_140009385
0x14000935e  mov     rsi, [rsp+78h+arg_8]
0x140009366  mov     rbp, [rsp+78h+arg_0]
0x14000936e  mov     [rbx+10h], r14b
0x140009372  mov     rbx, [rsp+78h+arg_10]
0x14000937a  add     rsp, 60h
0x14000937e  pop     r15
0x140009380  pop     r14
0x140009382  pop     rdi
0x140009383  retn
0x140009385  mov     r8, [rbx+30h]
0x140009389  movzx   eax, word ptr [r8+2]
0x14000938e  cmp     eax, 38h ; '8'
0x140009391  jz      short def_1400093D3; jumptable 00000001400093D3 default case, cases 8-56
0x140009393  add     eax, 0FFFFFFF8h; switch 51 cases
0x140009396  cmp     eax, 32h
0x140009399  jbe     short loc_1400093BD
0x14000939b  cmp     rcx, [r8+30h]; jumptable 00000001400093D3 default case, cases 8-56
0x14000939f  jz      short loc_14000935E
0x1400093a1  mov     rax, [rbx+38h]; jumptable 00000001400093D3 cases 57,58
0x1400093a5  cmp     rcx, [rax+78h]
0x1400093a9  jz      short loc_14000935E
0x1400093ab  call    cs:__imp_IoFreeMdl
0x1400093b2  nop     dword ptr [rax+rax+00h]
0x1400093b7  mov     [rbx+50h], r14
0x1400093bb  jmp     short loc_14000935E
0x1400093bd  cdqe
0x1400093bf  movzx   eax, ds:(byte_140064F02 - 140000000h)[r15+rax]
0x1400093c8  mov     edx, ds:(jpt_1400093D3 - 140000000h)[r15+rax*4]
0x1400093d0  add     rdx, r15
0x1400093d3  jmp     rdx; switch jump
0x1400093d9  inc     dword ptr [r9+0FCh]
0x1400093e0  jmp     loc_1400092D4
0x1400093e5  mov     rax, [r9+30h]
0x1400093e9  mov     rcx, [r9+38h]
0x1400093ed  movzx   edx, byte ptr [rax+8Fh]
0x1400093f4  mov     eax, [rbx+6Ch]
0x1400093f7  mov     [rsp+78h+var_28], eax
0x1400093fb  mov     eax, [rbx+48h]
0x1400093fe  mov     [rsp+78h+var_30], eax
0x140009402  mov     rax, [rbx+18h]
0x140009406  mov     [rsp+78h+var_38], rax
0x14000940b  mov     eax, [r9+40h]
0x14000940f  mov     [rsp+78h+var_40], eax
0x140009413  mov     eax, [rcx+98h]
0x140009419  mov     rcx, [rcx+50h]
0x14000941d  mov     [rsp+78h+var_48], eax
0x140009421  mov     [rsp+78h+var_50], edx
0x140009425  call    WPP_RECORDER_SF_DDDqdD
0x14000942a  jmp     loc_1400092E8
0x14000942f  cmp     r8d, 0C0000E00h
0x140009436  jle     loc_140009503
0x14000943c  cmp     r8d, 0C0010000h
0x140009443  jnz     short loc_140009460
0x140009445  mov     eax, 0C0000120h
0x14000944a  jmp     loc_1400092B6
0x14000944f  mov     dword ptr [rdx+4], 0C0000014h; jumptable 000000014000929F case 20
0x140009456  mov     eax, 0C0000001h
0x14000945b  jmp     loc_1400092B6
0x140009460  cmp     r8d, 0C0001000h
0x140009467  jnz     short loc_140009484
0x140009469  mov     eax, 0C000009Ah
0x14000946e  jmp     loc_1400092B6
0x140009473  mov     dword ptr [rdx+4], 0C0000004h; jumptable 000000014000929F case 6
0x14000947a  mov     eax, 0C0000001h
0x14000947f  jmp     loc_1400092B6
0x140009484  cmp     r8d, 0C0007000h
0x14000948b  jnz     loc_140009574
0x140009491  mov     eax, 0C000000Eh
0x140009496  jmp     loc_1400092B6
0x14000949b  mov     dword ptr [rdx+4], 0C0000012h; jumptable 000000014000929F cases 3,31
0x1400094a2  mov     eax, 0C0000001h
0x1400094a7  jmp     loc_1400092B6
0x1400094ac  mov     dword ptr [rdx+4], 0C0030000h; jumptable 000000014000929F case 23
0x1400094b3  mov     eax, 0C0000001h
0x1400094b8  jmp     loc_1400092B6
0x1400094bd  cdqe
0x1400094bf  movzx   eax, ds:(byte_140064F41 - 140000000h)[r15+rax]
0x1400094c8  mov     ecx, ds:(jpt_1400094D3 - 140000000h)[r15+rax*4]
0x1400094d0  add     rcx, r15
0x1400094d3  jmp     rcx; switch jump
0x1400094d9  mov     ecx, 34h ; '4'; jumptable 00000001400094D3 cases 57,58
0x1400094de  jmp     loc_140009269
0x1400094e3  cmp     r8d, 80000200h
0x1400094ea  jz      short loc_140009518
0x1400094ec  cmp     r8d, 80000300h
0x1400094f3  jz      short loc_140009518
0x1400094f5  cmp     r8d, 80000600h
0x1400094fc  jz      short loc_140009518
0x1400094fe  jmp     loc_140009456
0x140009503  jnz     short loc_14000950F
0x140009505  mov     eax, 0C00000BBh
0x14000950a  jmp     loc_1400092B6
0x14000950f  cmp     r8d, 0C0000A00h
0x140009516  jnz     short loc_1400094E3
0x140009518  mov     eax, 0C000000Dh
0x14000951d  jmp     loc_1400092B6
0x140009522  mov     dword ptr [rdx+4], 0C0000013h; jumptable 000000014000929F case 2
0x140009529  jmp     loc_140009456
0x14000952e  mov     dword ptr [rdx+4], 0C0020000h; jumptable 000000014000929F case 27
0x140009535  jmp     loc_140009456
0x14000953a  mov     dword ptr [rdx+4], 0C0000015h; jumptable 000000014000929F case 10
0x140009541  jmp     loc_140009456
0x140009546  mov     dword ptr [rdx+4], 0C0000016h; jumptable 000000014000929F case 34
0x14000954d  jmp     loc_140009456
0x140009552  mov     rax, [r9+28h]; jumptable 000000014000929F case 199
0x140009556  mov     ecx, 0C0008000h
0x14000955b  bt      qword ptr [rax+2E0h], 3Eh ; '>'
0x140009564  mov     eax, 0C0000011h
0x140009569  cmovb   eax, ecx
0x14000956c  mov     [rdx+4], eax
0x14000956f  jmp     loc_140009456
0x140009574  test    r8d, r8d
0x140009577  jz      loc_1400092B3
0x14000957d  jmp     loc_140009456
0x140009582  mov     dword ptr [rdx+4], 0C0000011h; jumptable 000000014000929F default case, cases 4,5,7-9,11,12,14-19,21,22,24,25,28-30,32,33,35-198
0x140009589  jmp     loc_140009456
```
