# XilCoreCommonBuffer_AllocateBuffers

- ea: `0x14002c5b0`
- end: `0x14002c93e`
- name: `XilCoreCommonBuffer_AllocateBuffers`
- size: `910`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140006484`
- `0x14002bea0`
- `0x14002c4d8`
- `0x1400574dc`

## callees

- `0x140002568`
- `0x14001ac48`
- `0x14002c5b0`
- `0x14002c944`
- `0x14002cb28`
- `0x14003b408`
- `0x140057364`
- `0x1400599b0`
- `0x14008358c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002c85e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c85e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c6ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c6ac`

## pseudocode

```c
__int64 __fastcall XilCoreCommonBuffer_AllocateBuffers(__int64 **a1, __int64 a2, int a3)
{
  unsigned int v3; // ebp
  __int64 v5; // rdi
  unsigned int v7; // r13d
  __int64 result; // rax
  unsigned int v9; // edx
  unsigned int i; // r12d
  int v11; // edx
  __int64 v12; // rcx
  int v13; // edx
  __int64 *v14; // r14
  KIRQL v15; // al
  __int64 v16; // rsi
  _QWORD *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 ***v24; // rdx
  int v25; // eax
  int v26; // [rsp+20h] [rbp-78h]
  int v27; // [rsp+38h] [rbp-60h]
  __int64 v28; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v29; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v30; // [rsp+B0h] [rbp+18h]

  v3 = 0;
  v29 = 0;
  v5 = a2;
  v28 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v27 = *(_DWORD *)(a2 + 28);
    v25 = *(_DWORD *)(a2 + 24);
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qDD(a1[1][9], a2, 8, 12, (__int64)WPP_2cbb8eaba4893cb9c10a668c9784ba4d_Traceguids, v5, v25, v27);
  }
  _InterlockedIncrement((volatile signed __int32 *)a1 + 52);
  v7 = ((unsigned int)(a3 * *(_DWORD *)v5) >> 12) + (((a3 * *(_DWORD *)v5) & 0xFFF) != 0);
  v9 = 0x1000u % *(_DWORD *)v5;
  result = 0x1000u / *(_DWORD *)v5;
  v30 = 0x1000u / *(_DWORD *)v5;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_DD(a1[1][9], v9, 8, 13, (__int64)WPP_2cbb8eaba4893cb9c10a668c9784ba4d_Traceguids, v7, result);
    result = v30;
  }
  for ( i = 0; i < v7; ++i )
  {
    v11 = 104 * result + 32;
    v12 = **a1;
    result = *((_BYTE *)*a1 + 80)
           ? SecureDmaEnabler_AllocateCommonBufferPage(
               *(_QWORD *)(v12 + 104),
               v11,
               4096,
               (unsigned int)&v28,
               (__int64)&v29)
           : DmaEnabler_AllocateCommonBufferPage(*(_QWORD *)(v12 + 96), v11, 4096, (unsigned int)&v28, (__int64)&v29);
    if ( (int)result < 0 )
      break;
    v14 = (__int64 *)v28;
    if ( (*(_DWORD *)(v28 + 8) & 0xFFF) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 3;
        WPP_RECORDER_SF_(a1[1][9], v13, 8, 14, (__int64)WPP_2cbb8eaba4893cb9c10a668c9784ba4d_Traceguids);
      }
      if ( *((_BYTE *)*a1 + 80) )
        SecureDmaEnabler_FreeCommonBufferPage(*(_QWORD *)(**a1 + 104), v14);
      else
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 1664))(WdfDriverGlobals, v14[2]);
    }
    else
    {
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
      v16 = v29;
      *((_BYTE *)a1 + 25) = v15;
      ++*((_DWORD *)a1 + 50);
      *(_QWORD *)(v16 + 24) = v14;
      *(_BYTE *)(v16 + 16) = 1;
      v17 = *(_QWORD **)(v5 + 56);
      if ( *v17 != v5 + 48 )
        goto LABEL_15;
      *(_QWORD *)v16 = v5 + 48;
      *(_QWORD *)(v16 + 8) = v17;
      *v17 = v16;
      *(_QWORD *)(v5 + 56) = v16;
      if ( v30 )
      {
        v18 = v5 + 32;
        while ( 1 )
        {
          v19 = *v14;
          v20 = v16 + 104LL * v3 + 32;
          *(_QWORD *)(v20 + 16) = *v14;
          *(_QWORD *)(v20 + 16) = v19 + *(_DWORD *)v5 * v3;
          v21 = v14[1];
          *(_QWORD *)(v20 + 24) = v21;
          v22 = *(_DWORD *)v5 * v3;
          *(_QWORD *)(v20 + 32) = v16;
          *(_QWORD *)(v20 + 24) = v21 + v22;
          *(_DWORD *)(v20 + 40) = *(_DWORD *)v5;
          v23 = *(_QWORD **)(v18 + 8);
          if ( *v23 != v18 )
            break;
          *(_QWORD *)v20 = v18;
          *(_QWORD *)(v20 + 8) = v23;
          *v23 = v20;
          *(_QWORD *)(v18 + 8) = v20;
          v24 = (__int64 ***)a1[21];
          if ( *v24 != a1 + 20 )
            break;
          *(_QWORD *)(v20 + 48) = a1 + 20;
          *(_QWORD *)(v20 + 56) = v24;
          *v24 = (__int64 **)(v20 + 48);
          a1[21] = (__int64 *)(v20 + 48);
          ++*(_DWORD *)(v5 + 24);
          ++*(_DWORD *)(v5 + 28);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              WPP_RECORDER_SF_ddqDddd(
                a1[1][9],
                *(_DWORD *)(v5 + 24),
                v20,
                v18,
                v26,
                i,
                v3,
                *(_QWORD *)(v20 + 16),
                *(_DWORD *)(v20 + 24),
                *(_DWORD *)(v20 + 40),
                *(_DWORD *)(v5 + 24),
                *(_DWORD *)(v5 + 28));
              v18 = v5 + 32;
            }
          }
          if ( ++v3 >= v30 )
            goto LABEL_24;
        }
LABEL_15:
        __fastfail(3u);
      }
LABEL_24:
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 2, *((_BYTE *)a1 + 25));
      v3 = 0;
    }
    result = v30;
  }
  return result;
}

```

## disassembly

```asm
0x14002c5b0  mov     rax, rsp
0x14002c5b3  mov     [rax+20h], rbx
0x14002c5b7  push    rbp
0x14002c5b8  push    rsi
0x14002c5b9  push    rdi
0x14002c5ba  push    r12
0x14002c5bc  push    r13
0x14002c5be  push    r14
0x14002c5c0  push    r15
0x14002c5c2  sub     rsp, 60h
0x14002c5c6  xor     ebp, ebp
0x14002c5c8  mov     esi, r8d
0x14002c5cb  mov     [rax+10h], rbp
0x14002c5cf  mov     rdi, rdx
0x14002c5d2  mov     [rax+8], rbp
0x14002c5d6  mov     rbx, rcx
0x14002c5d9  lea     r15, WPP_RECORDER_INITIALIZED
0x14002c5e0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14002c5e7  lea     r8, WPP_2cbb8eaba4893cb9c10a668c9784ba4d_Traceguids
0x14002c5ee  jnz     loc_14002C775
0x14002c5f4  lock inc dword ptr [rbx+0D0h]
0x14002c5fb  mov     ecx, [rdi]
0x14002c5fd  mov     r13d, ebp
0x14002c600  mov     eax, ecx
0x14002c602  imul    eax, esi
0x14002c605  test    eax, 0FFFh
0x14002c60a  setnz   r13b
0x14002c60e  shr     eax, 0Ch
0x14002c611  add     r13d, eax
0x14002c614  xor     edx, edx
0x14002c616  mov     eax, 1000h
0x14002c61b  div     ecx
0x14002c61d  mov     [rsp+98h+arg_10], eax
0x14002c624  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14002c62b  jnz     loc_14002C7C3
0x14002c631  mov     r12d, ebp
0x14002c634  cmp     r12d, r13d
0x14002c637  jb      short loc_14002C652
0x14002c639  mov     rbx, [rsp+98h+arg_18]
0x14002c641  add     rsp, 60h
0x14002c645  pop     r15
0x14002c647  pop     r14
0x14002c649  pop     r13
0x14002c64b  pop     r12
0x14002c64d  pop     rdi
0x14002c64e  pop     rsi
0x14002c64f  pop     rbp
0x14002c650  retn
0x14002c652  imul    rdx, rax, 68h ; 'h'
0x14002c656  mov     rax, [rbx]
0x14002c659  lea     r9, [rsp+98h+arg_0]
0x14002c661  add     rdx, 20h ; ' '
0x14002c665  mov     r8d, 1000h
0x14002c66b  cmp     [rax+50h], bpl
0x14002c66f  mov     rcx, [rax]
0x14002c672  lea     rax, [rsp+98h+arg_8]
0x14002c67a  mov     [rsp+98h+var_78], rax
0x14002c67f  jnz     loc_14002C882
0x14002c685  mov     rcx, [rcx+60h]
0x14002c689  call    DmaEnabler_AllocateCommonBufferPage
0x14002c68e  test    eax, eax
0x14002c690  js      short loc_14002C639
0x14002c692  mov     r14, [rsp+98h+arg_0]
0x14002c69a  test    dword ptr [r14+8], 0FFFh
0x14002c6a2  jnz     loc_14002C8CA
0x14002c6a8  lea     rcx, [rbx+10h]; SpinLock
0x14002c6ac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c6b3  nop     dword ptr [rax+rax+00h]
0x14002c6b8  mov     rsi, [rsp+98h+arg_8]
0x14002c6c0  mov     [rbx+19h], al
0x14002c6c3  lea     rax, [rdi+30h]
0x14002c6c7  inc     dword ptr [rbx+0C8h]
0x14002c6cd  mov     [rsi+18h], r14
0x14002c6d1  mov     byte ptr [rsi+10h], 1
0x14002c6d5  mov     rcx, [rax+8]
0x14002c6d9  cmp     [rcx], rax
0x14002c6dc  jnz     loc_14002C76E
0x14002c6e2  mov     [rsi], rax
0x14002c6e5  xor     r11d, r11d
0x14002c6e8  mov     [rsi+8], rcx
0x14002c6ec  mov     [rcx], rsi
0x14002c6ef  mov     [rax+8], rsi
0x14002c6f3  cmp     [rsp+98h+arg_10], r11d
0x14002c6fb  jbe     loc_14002C857
0x14002c701  lea     r9, [rdi+20h]
0x14002c705  mov     rdx, [r14]
0x14002c708  mov     ecx, ebp
0x14002c70a  mov     eax, ebp
0x14002c70c  imul    r8, rax, 68h ; 'h'
0x14002c710  add     r8, 20h ; ' '
0x14002c714  add     r8, rsi
0x14002c717  mov     [r8+10h], rdx
0x14002c71b  imul    ecx, [rdi]
0x14002c71e  add     rcx, rdx
0x14002c721  mov     [r8+10h], rcx
0x14002c725  mov     ecx, ebp
0x14002c727  mov     rdx, [r14+8]
0x14002c72b  mov     [r8+18h], rdx
0x14002c72f  imul    ecx, [rdi]
0x14002c732  mov     [r8+20h], rsi
0x14002c736  add     rcx, rdx
0x14002c739  mov     [r8+18h], rcx
0x14002c73d  mov     eax, [rdi]
0x14002c73f  mov     [r8+28h], eax
0x14002c743  mov     rax, [r9+8]
0x14002c747  cmp     [rax], r9
0x14002c74a  jnz     short loc_14002C76E
0x14002c74c  mov     [r8], r9
0x14002c74f  lea     rcx, [rbx+0A0h]
0x14002c756  mov     [r8+8], rax
0x14002c75a  mov     [rax], r8
0x14002c75d  mov     [r9+8], r8
0x14002c761  mov     rdx, [rcx+8]
0x14002c765  cmp     [rdx], rcx
0x14002c768  jz      loc_14002C807
0x14002c76e  mov     ecx, 3
0x14002c773  int     29h; Win8: RtlFailFast(ecx)
0x14002c775  mov     rax, cs:WPP_GLOBAL_Control
0x14002c77c  cmp     [rax+48h], bp
0x14002c780  jz      loc_14002C5F4
0x14002c786  mov     eax, [rdx+1Ch]
0x14002c789  mov     r9d, 0Ch
0x14002c78f  mov     rcx, [rcx+8]
0x14002c793  mov     dword ptr [rsp+98h+var_60], eax
0x14002c797  mov     eax, [rdx+18h]
0x14002c79a  mov     dl, 5
0x14002c79c  mov     [rsp+98h+var_68], eax
0x14002c7a0  mov     rcx, [rcx+48h]
0x14002c7a4  mov     [rsp+98h+var_70], rdi
0x14002c7a9  mov     [rsp+98h+var_78], r8
0x14002c7ae  lea     r8d, [r9-4]
0x14002c7b2  call    WPP_RECORDER_SF_qDD
0x14002c7b7  lea     r8, WPP_2cbb8eaba4893cb9c10a668c9784ba4d_Traceguids
0x14002c7be  jmp     loc_14002C5F4
0x14002c7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c7ca  cmp     [rcx+48h], bp
0x14002c7ce  jz      loc_14002C631
0x14002c7d4  mov     rcx, [rbx+8]
0x14002c7d8  mov     r9d, 0Dh
0x14002c7de  mov     [rsp+98h+var_68], eax
0x14002c7e2  mov     dl, 5
0x14002c7e4  mov     dword ptr [rsp+98h+var_70], r13d
0x14002c7e9  mov     [rsp+98h+var_78], r8
0x14002c7ee  mov     rcx, [rcx+48h]
0x14002c7f2  lea     r8d, [r9-5]
0x14002c7f6  call    WPP_RECORDER_SF_DD
0x14002c7fb  mov     eax, [rsp+98h+arg_10]
0x14002c802  jmp     loc_14002C631
0x14002c807  lea     rax, [r8+30h]
0x14002c80b  mov     [rax], rcx
0x14002c80e  mov     [rax+8], rdx
0x14002c812  mov     [rdx], rax
0x14002c815  mov     [rcx+8], rax
0x14002c819  inc     dword ptr [rdi+18h]
0x14002c81c  inc     dword ptr [rdi+1Ch]
0x14002c81f  mov     r10d, [rdi+1Ch]
0x14002c823  mov     edx, [rdi+18h]
0x14002c826  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c82d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c834  jz      short loc_14002C848
0x14002c836  mov     rax, cs:WPP_GLOBAL_Control
0x14002c83d  cmp     [rax+48h], r11w
0x14002c842  jnz     loc_14002C8FA
0x14002c848  inc     ebp
0x14002c84a  cmp     ebp, [rsp+98h+arg_10]
0x14002c851  jb      loc_14002C705
0x14002c857  mov     dl, [rbx+19h]; NewIrql
0x14002c85a  lea     rcx, [rbx+10h]; SpinLock
0x14002c85e  call    cs:__imp_KeReleaseSpinLock
0x14002c865  nop     dword ptr [rax+rax+00h]
0x14002c86a  xor     ebp, ebp
0x14002c86c  lea     r15, WPP_RECORDER_INITIALIZED
0x14002c873  mov     eax, [rsp+98h+arg_10]
0x14002c87a  inc     r12d
0x14002c87d  jmp     loc_14002C634
0x14002c882  mov     rcx, [rcx+68h]
0x14002c886  call    SecureDmaEnabler_AllocateCommonBufferPage
0x14002c88b  jmp     loc_14002C68E
0x14002c890  mov     rcx, [rbx]
0x14002c893  cmp     [rcx+50h], bpl
0x14002c897  jz      short loc_14002C8AA
0x14002c899  mov     rcx, [rcx]
0x14002c89c  mov     rdx, r14
0x14002c89f  mov     rcx, [rcx+68h]
0x14002c8a3  call    SecureDmaEnabler_FreeCommonBufferPage
0x14002c8a8  jmp     short loc_14002C873
0x14002c8aa  mov     rax, cs:WdfFunctions_01033
0x14002c8b1  mov     rdx, [r14+10h]
0x14002c8b5  mov     rcx, cs:WdfDriverGlobals
0x14002c8bc  mov     rax, [rax+680h]
0x14002c8c3  call    _guard_dispatch_icall
0x14002c8c8  jmp     short loc_14002C873
0x14002c8ca  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14002c8d1  jz      short loc_14002C890
0x14002c8d3  mov     rcx, [rbx+8]
0x14002c8d7  lea     rax, WPP_2cbb8eaba4893cb9c10a668c9784ba4d_Traceguids
0x14002c8de  mov     r9d, 0Eh
0x14002c8e4  mov     [rsp+98h+var_78], rax
0x14002c8e9  mov     dl, 3
0x14002c8eb  mov     rcx, [rcx+48h]
0x14002c8ef  lea     r8d, [r9-6]
0x14002c8f3  call    WPP_RECORDER_SF_
0x14002c8f8  jmp     short loc_14002C890
0x14002c8fa  mov     eax, [r8+28h]
0x14002c8fe  mov     rcx, [rbx+8]
0x14002c902  mov     [rsp+98h+var_40], r10d
0x14002c907  mov     [rsp+98h+var_48], edx
0x14002c90b  mov     [rsp+98h+var_50], eax
0x14002c90f  mov     eax, [r8+18h]
0x14002c913  mov     rcx, [rcx+48h]
0x14002c917  mov     [rsp+98h+var_58], eax
0x14002c91b  mov     rax, [r8+10h]
0x14002c91f  mov     [rsp+98h+var_60], rax
0x14002c924  mov     [rsp+98h+var_68], ebp
0x14002c928  mov     dword ptr [rsp+98h+var_70], r12d
0x14002c92d  call    WPP_RECORDER_SF_ddqDddd
0x14002c932  lea     r9, [rdi+20h]
0x14002c936  xor     r11d, r11d
0x14002c939  jmp     loc_14002C848
```
