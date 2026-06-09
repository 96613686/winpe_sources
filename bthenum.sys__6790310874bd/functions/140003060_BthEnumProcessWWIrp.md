# BthEnumProcessWWIrp

- ea: `0x140003060`
- end: `0x1400031b1`
- name: `BthEnumProcessWWIrp`
- size: `337`
- prototype: `__int128 *__fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400013e8`
- `0x140003060`
- `0x14000442c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003190`
- `ntoskrnl!IofCompleteRequest` at `0x140003190`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000313b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000313b`

## pseudocode

```c
__int128 *__fastcall BthEnumProcessWWIrp(__int64 a1, int a2)
{
  __int128 *result; // rax
  __int64 v5; // rbx
  _QWORD **v6; // rbx
  KIRQL v7; // al
  _QWORD *v8; // r11
  KIRQL v9; // r14
  _QWORD *v10; // rsi
  __int128 **v11; // r11
  __int128 ***v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int128 v17; // [rsp+30h] [rbp-10h] BYREF

  v17 = 0;
  result = (__int128 *)&WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    result = (__int128 *)WPP_RECORDER_SF_d(
                           WPP_GLOBAL_Control->DeviceExtension,
                           a2,
                           3,
                           36,
                           (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
                           a2,
                           v17);
  if ( a2 != -1073741536 )
  {
    v5 = *(_QWORD *)(a1 + 64);
    *((_QWORD *)&v17 + 1) = &v17;
    v6 = (_QWORD **)(v5 + 64);
    *(_QWORD *)&v17 = &v17;
    v7 = KeAcquireSpinLockRaiseToDpc(v6[3]);
    v8 = *v6;
    v9 = v7;
    if ( *v6 != v6 )
    {
      do
      {
        v10 = (_QWORD *)*v8;
        if ( (unsigned __int8)IrpList_DequeueIrpLocked(v6, v8 - 21) )
        {
          v12 = (__int128 ***)*((_QWORD *)&v17 + 1);
          if ( **((__int128 ***)&v17 + 1) != &v17 )
LABEL_14:
            __fastfail(3u);
          v11[1] = (__int128 *)*((_QWORD *)&v17 + 1);
          *v11 = &v17;
          *v12 = v11;
          *((_QWORD *)&v17 + 1) = v11;
        }
        v8 = v10;
      }
      while ( v10 != v6 );
    }
    KeReleaseSpinLock(v6[3], v9);
    while ( 1 )
    {
      v13 = v17;
      result = &v17;
      if ( (__int128 *)v17 == &v17 )
        break;
      if ( *(__int128 **)(v17 + 8) != &v17 )
        goto LABEL_14;
      v14 = *(_QWORD *)v17;
      if ( *(_QWORD *)(*(_QWORD *)v17 + 8LL) != (_QWORD)v17 )
        goto LABEL_14;
      *(_QWORD *)&v17 = *(_QWORD *)v17;
      *(_QWORD *)(v14 + 8) = &v17;
      v15 = v13 - 168;
      *(_QWORD *)(_InterlockedExchange64((volatile __int64 *)(v15 + 120), 0) + 168) = 0;
      *(_DWORD *)(v15 + 48) = a2;
      IofCompleteRequest((PIRP)v15, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003060  push    rbp
0x140003062  push    rbx
0x140003063  push    rsi
0x140003064  push    rdi
0x140003065  push    r14
0x140003067  mov     rbp, rsp
0x14000306a  sub     rsp, 40h
0x14000306e  xorps   xmm0, xmm0
0x140003071  mov     edi, edx
0x140003073  movups  [rbp+var_10], xmm0
0x140003077  mov     rbx, rcx
0x14000307a  lea     rax, WPP_RECORDER_INITIALIZED
0x140003081  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003088  jz      short loc_1400030B4
0x14000308a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003091  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x140003098  mov     r9d, 24h ; '$'
0x14000309e  mov     [rsp+40h+var_18], edx
0x1400030a2  mov     [rsp+40h+var_20], rax
0x1400030a7  mov     rcx, [rcx+40h]
0x1400030ab  lea     r8d, [r9-21h]
0x1400030af  call    WPP_RECORDER_SF_d
0x1400030b4  cmp     edi, 0C0000120h
0x1400030ba  jz      loc_1400031A5
0x1400030c0  mov     rbx, [rbx+40h]
0x1400030c4  lea     rax, [rbp+var_10]
0x1400030c8  mov     qword ptr [rbp+var_10+8], rax
0x1400030cc  add     rbx, 40h ; '@'
0x1400030d0  lea     rax, [rbp+var_10]
0x1400030d4  mov     qword ptr [rbp+var_10], rax
0x1400030d8  mov     rcx, [rbx+18h]; SpinLock
0x1400030dc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400030e3  nop     dword ptr [rax+rax+00h]
0x1400030e8  mov     r11, [rbx]
0x1400030eb  mov     r14b, al
0x1400030ee  cmp     r11, rbx
0x1400030f1  jz      short loc_140003134
0x1400030f3  mov     rsi, [r11]
0x1400030f6  lea     rdx, [r11-0A8h]
0x1400030fd  mov     rcx, rbx
0x140003100  call    IrpList_DequeueIrpLocked
0x140003105  test    al, al
0x140003107  jz      short loc_14000312C
0x140003109  mov     rax, qword ptr [rbp+var_10+8]
0x14000310d  lea     rcx, [rbp+var_10]
0x140003111  cmp     [rax], rcx
0x140003114  jnz     loc_14000319E
0x14000311a  mov     [r11+8], rax
0x14000311e  lea     rcx, [rbp+var_10]
0x140003122  mov     [r11], rcx
0x140003125  mov     [rax], r11
0x140003128  mov     qword ptr [rbp+var_10+8], r11
0x14000312c  mov     r11, rsi
0x14000312f  cmp     rsi, rbx
0x140003132  jnz     short loc_1400030F3
0x140003134  mov     rcx, [rbx+18h]; SpinLock
0x140003138  mov     dl, r14b; NewIrql
0x14000313b  call    cs:__imp_KeReleaseSpinLock
0x140003142  nop     dword ptr [rax+rax+00h]
0x140003147  mov     rcx, qword ptr [rbp+var_10]
0x14000314b  lea     rax, [rbp+var_10]
0x14000314f  cmp     rcx, rax
0x140003152  jz      short loc_1400031A5
0x140003154  lea     rax, [rbp+var_10]
0x140003158  cmp     [rcx+8], rax
0x14000315c  jnz     short loc_14000319E
0x14000315e  mov     rax, [rcx]
0x140003161  cmp     [rax+8], rcx
0x140003165  jnz     short loc_14000319E
0x140003167  mov     qword ptr [rbp+var_10], rax
0x14000316b  lea     rdx, [rbp+var_10]
0x14000316f  mov     [rax+8], rdx
0x140003173  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14000317a  xor     eax, eax
0x14000317c  xor     edx, edx; PriorityBoost
0x14000317e  xchg    rax, [rcx+78h]
0x140003182  mov     qword ptr [rax+0A8h], 0
0x14000318d  mov     [rcx+30h], edi
0x140003190  call    cs:__imp_IofCompleteRequest
0x140003197  nop     dword ptr [rax+rax+00h]
0x14000319c  jmp     short loc_140003147
0x14000319e  mov     ecx, 3
0x1400031a3  int     29h; Win8: RtlFailFast(ecx)
0x1400031a5  add     rsp, 40h
0x1400031a9  pop     r14
0x1400031ab  pop     rdi
0x1400031ac  pop     rsi
0x1400031ad  pop     rbx
0x1400031ae  pop     rbp
0x1400031af  retn
```
