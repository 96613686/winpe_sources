# BthEnumWaitWakeCancelRoutine

- ea: `0x140002330`
- end: `0x1400024b8`
- name: `BthEnumWaitWakeCancelRoutine`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001328`
- `0x140001ab8`
- `0x140002330`
- `0x140007d40`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002474`
- `ntoskrnl!IofCompleteRequest` at `0x140002474`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000239c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400023ff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000239c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400023ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002439`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002439`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400023ef`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400023ef`

## pseudocode

```c
void __fastcall BthEnumWaitWakeCancelRoutine(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rdi
  __int64 v4; // r14
  __int64 v6; // rbp
  KIRQL v7; // al
  __int64 v8; // rdi
  KIRQL v9; // al
  __int64 v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rcx
  void (__fastcall *v13)(__int64, __int64, __int64); // rax
  int v14; // edx

  v2 = *(_QWORD **)(a1 + 64);
  v4 = *(_QWORD *)(a2 + 144);
  v6 = *(_QWORD *)(v2[1] + 64LL);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      25,
      (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids,
      a2,
      a1);
  v7 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(v4 + 24));
  _InterlockedExchange64((volatile __int64 *)(a2 + 120), 0);
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(v4 + 24), v7);
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(v6 + 48))(*(_QWORD *)(v6 + 40), v2[24], 2);
  v2[21] = 0;
  v8 = *(_QWORD *)(a2 + 144);
  IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
  v9 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(v8 + 24));
  v10 = a2 + 168;
  v11 = *(_QWORD *)(a2 + 168);
  if ( v11 != a2 + 168 )
  {
    if ( *(_QWORD *)(v11 + 8) != v10 || (v12 = *(_QWORD **)(a2 + 176), *v12 != v10) )
      __fastfail(3u);
    *v12 = v11;
    *(_QWORD *)(v11 + 8) = v12;
    --*(_DWORD *)(v8 + 32);
  }
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(v8 + 24), v9);
  v13 = *(void (__fastcall **)(__int64, __int64, __int64))(v8 + 48);
  if ( v13 )
  {
    v13(a1, a2, 3221225760LL);
  }
  else
  {
    *(_DWORD *)(a2 + 48) = -1073741536;
    IofCompleteRequest((PIRP)a2, 0);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      3,
      26,
      (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids);
}

```

## disassembly

```asm
0x140002330  push    rbx
0x140002332  push    rbp
0x140002333  push    rsi
0x140002334  push    rdi
0x140002335  push    r12
0x140002337  push    r13
0x140002339  push    r14
0x14000233b  sub     rsp, 40h
0x14000233f  mov     rdi, [rcx+40h]
0x140002343  mov     rbx, rdx
0x140002346  mov     r14, [rdx+90h]
0x14000234d  mov     rsi, rcx
0x140002350  mov     rax, [rdi+8]
0x140002354  mov     rbp, [rax+40h]
0x140002358  lea     r12, WPP_RECORDER_INITIALIZED
0x14000235f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002366  lea     r13, WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids
0x14000236d  jz      short loc_140002398
0x14000236f  mov     [rsp+78h+var_48], rcx
0x140002374  mov     r9d, 19h
0x14000237a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002381  mov     [rsp+78h+var_50], rdx
0x140002386  mov     [rsp+78h+var_58], r13
0x14000238b  lea     r8d, [r9-16h]
0x14000238f  mov     rcx, [rcx+40h]
0x140002393  call    WPP_RECORDER_SF_qq
0x140002398  mov     rcx, [r14+18h]; SpinLock
0x14000239c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400023a3  nop     dword ptr [rax+rax+00h]
0x1400023a8  xor     edx, edx
0x1400023aa  xchg    rdx, [rbx+78h]
0x1400023ae  mov     rcx, [r14+18h]; SpinLock
0x1400023b2  mov     dl, al; NewIrql
0x1400023b4  call    cs:__imp_KeReleaseSpinLock
0x1400023bb  nop     dword ptr [rax+rax+00h]
0x1400023c0  mov     rax, [rbp+30h]
0x1400023c4  mov     r8d, 2
0x1400023ca  mov     rdx, [rdi+0C0h]
0x1400023d1  mov     rcx, [rbp+28h]
0x1400023d5  call    _guard_dispatch_icall
0x1400023da  mov     qword ptr [rdi+0A8h], 0
0x1400023e5  mov     cl, [rbx+45h]; Irql
0x1400023e8  mov     rdi, [rbx+90h]
0x1400023ef  call    cs:__imp_IoReleaseCancelSpinLock
0x1400023f6  nop     dword ptr [rax+rax+00h]
0x1400023fb  mov     rcx, [rdi+18h]; SpinLock
0x1400023ff  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002406  nop     dword ptr [rax+rax+00h]
0x14000240b  lea     rdx, [rbx+0A8h]
0x140002412  mov     r8, [rdx]
0x140002415  cmp     r8, rdx
0x140002418  jz      short loc_140002433
0x14000241a  cmp     [r8+8], rdx
0x14000241e  jnz     short loc_140002461
0x140002420  mov     rcx, [rdx+8]
0x140002424  cmp     [rcx], rdx
0x140002427  jnz     short loc_140002461
0x140002429  mov     [rcx], r8
0x14000242c  mov     [r8+8], rcx
0x140002430  dec     dword ptr [rdi+20h]
0x140002433  mov     rcx, [rdi+18h]; SpinLock
0x140002437  mov     dl, al; NewIrql
0x140002439  call    cs:__imp_KeReleaseSpinLock
0x140002440  nop     dword ptr [rax+rax+00h]
0x140002445  mov     rax, [rdi+30h]
0x140002449  test    rax, rax
0x14000244c  jz      short loc_140002468
0x14000244e  mov     r8d, 0C0000120h
0x140002454  mov     rdx, rbx
0x140002457  mov     rcx, rsi
0x14000245a  call    _guard_dispatch_icall
0x14000245f  jmp     short loc_140002480
0x140002461  mov     ecx, 3
0x140002466  int     29h; Win8: RtlFailFast(ecx)
0x140002468  xor     edx, edx; PriorityBoost
0x14000246a  mov     dword ptr [rbx+30h], 0C0000120h
0x140002471  mov     rcx, rbx; Irp
0x140002474  call    cs:__imp_IofCompleteRequest
0x14000247b  nop     dword ptr [rax+rax+00h]
0x140002480  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002487  jz      short loc_1400024A8
0x140002489  mov     rcx, cs:WPP_GLOBAL_Control
0x140002490  mov     r9d, 1Ah
0x140002496  mov     [rsp+78h+var_58], r13
0x14000249b  mov     rcx, [rcx+40h]
0x14000249f  lea     r8d, [r9-17h]
0x1400024a3  call    WPP_RECORDER_SF_
0x1400024a8  add     rsp, 40h
0x1400024ac  pop     r14
0x1400024ae  pop     r13
0x1400024b0  pop     r12
0x1400024b2  pop     rdi
0x1400024b3  pop     rsi
0x1400024b4  pop     rbp
0x1400024b5  pop     rbx
0x1400024b6  retn
```
