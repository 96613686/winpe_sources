# Register_ControllerReset

- ea: `0x14001b3b8`
- end: `0x14001b789`
- name: `Register_ControllerReset`
- size: `977`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140018190`
- `0x140018d90`
- `0x1400416f8`
- `0x14007e5c8`

## callees

- `0x140002568`
- `0x140019e84`
- `0x140019f10`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001ae98`
- `0x14001b310`
- `0x14001b3b8`
- `0x14001b790`
- `0x14001d02c`
- `0x14001d118`
- `0x14001f830`
- `0x14001fb30`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001b475`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001b577`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001b738`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001b761`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001b475`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001b577`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001b738`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001b761`

## pseudocode

```c
__int64 __fastcall Register_ControllerReset(__int64 a1, char a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // r15
  int v6; // eax
  int v7; // edx
  unsigned int v8; // ebx
  int v9; // ebp
  unsigned int v10; // r14d
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // edx
  int v17; // eax
  int v18; // r9d
  void (*v19)(void); // rax
  char v20; // [rsp+28h] [rbp-60h]
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp+8h] BYREF

  Interval.QuadPart = 0;
  v4 = (_QWORD *)(a1 + 8);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*(_QWORD *)(*v4 + 72LL), 4, 6, 63, (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids);
  if ( !(unsigned __int8)Controller_IsControllerAccessible(*v4) )
    return 0;
  v5 = *(_QWORD *)(a1 + 32);
  v6 = Register_WaitForControllerReady(a1);
  v8 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v20 = v6;
    v18 = 64;
    goto LABEL_35;
  }
  if ( a2 || (XilRegister_ReadUlong(a1, v5 + 4) & 1) != 0 )
  {
    Register_SetClearSSICPortUnused(a1, 0);
    XilRegister_WriteUlong(a1, v5, 2);
    if ( (*(_BYTE *)(*v4 + 744LL) & 2) != 0 )
    {
      Interval.QuadPart = -10000;
      KeDelayExecutionThread(0, 0, &Interval);
      v9 = 1;
      v10 = 2;
    }
    else
    {
      v9 = 0;
      v10 = 1;
    }
    v11 = v9;
    while ( (XilRegister_ReadUlong(a1, v5) & 2) != 0 )
    {
      if ( v9 == 100 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 1;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*v4 + 72LL),
            v12,
            6,
            68,
            (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
            v11);
        }
        Etw_StartDeviceFail(*v4, v12, 3);
        return (unsigned int)-1073741823;
      }
      Interval.QuadPart = -10000LL * v10;
      KeDelayExecutionThread(0, 0, &Interval);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 4;
        WPP_RECORDER_SF_DD(
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
          v16,
          6,
          69,
          (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
          v9,
          v10);
      }
      v11 += v10;
      v17 = 2 * v10;
      ++v9;
      if ( v10 == 16 )
        v17 = 16;
      v10 = v17;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_D(
        *(_QWORD *)(*v4 + 72LL),
        v12,
        6,
        66,
        (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
        v11);
    }
    if ( v11 > 0x32 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_D(
        *(_QWORD *)(*v4 + 72LL),
        v12,
        6,
        67,
        (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
        v11);
    }
    v14 = Register_WaitForControllerReady(a1);
    v8 = v14;
    if ( v14 >= 0 )
    {
      if ( (*(_BYTE *)(*v4 + 752LL) & 0x10) != 0 )
      {
        Interval.QuadPart = -1000000;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      if ( (*(_DWORD *)(*v4 + 744LL) & 0x2000000) != 0 )
      {
        Interval.QuadPart = -1800000;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      v15 = *(_QWORD *)(*v4 + 168LL);
      if ( v15 )
      {
        v19 = *(void (**)(void))(v15 + 32);
        if ( v19 )
          v19();
      }
      Register_RestoreRyzenFeatureBitsPostReset(a1);
      Register_DisableComplianceModeCapability(a1);
      return v8;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v20 = v14;
    v18 = 70;
LABEL_35:
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*v4 + 72LL),
      v7,
      6,
      v18,
      (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
      v20);
    return v8;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*(_QWORD *)(*v4 + 72LL), 2, 6, 65, (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids);
  return (unsigned int)-1073741823;
}

```

## disassembly

```asm
0x14001b3b8  mov     rax, rsp
0x14001b3bb  push    rbx
0x14001b3bc  push    rbp
0x14001b3bd  push    rsi
0x14001b3be  push    rdi
0x14001b3bf  push    r12
0x14001b3c1  push    r13
0x14001b3c3  push    r14
0x14001b3c5  push    r15
0x14001b3c7  sub     rsp, 48h
0x14001b3cb  mov     bpl, dl
0x14001b3ce  mov     qword ptr [rax+8], 0
0x14001b3d6  mov     rsi, rcx
0x14001b3d9  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b3e0  mov     r13d, 6
0x14001b3e6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001b3ed  lea     rdi, [rcx+8]
0x14001b3f1  lea     r14, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x14001b3f8  jnz     loc_14001B5B3
0x14001b3fe  mov     rcx, [rdi]
0x14001b401  call    Controller_IsControllerAccessible
0x14001b406  test    al, al
0x14001b408  jz      loc_14001B552
0x14001b40e  mov     r15, [rsi+20h]
0x14001b412  mov     rcx, rsi
0x14001b415  call    Register_WaitForControllerReady
0x14001b41a  mov     ebx, eax
0x14001b41c  test    eax, eax
0x14001b41e  js      loc_14001B5D4
0x14001b424  mov     ebx, 1
0x14001b429  test    bpl, bpl
0x14001b42c  jz      loc_14001B617
0x14001b432  xor     edx, edx
0x14001b434  mov     rcx, rsi
0x14001b437  call    Register_SetClearSSICPortUnused
0x14001b43c  mov     r8d, 2
0x14001b442  mov     rdx, r15
0x14001b445  mov     rcx, rsi
0x14001b448  call    XilRegister_WriteUlong
0x14001b44d  mov     rax, [rdi]
0x14001b450  test    byte ptr [rax+2E8h], 2
0x14001b457  jz      loc_14001B5A9
0x14001b45d  lea     r8, [rsp+88h+Interval]; Interval
0x14001b465  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFFFD8F0h
0x14001b471  xor     edx, edx; Alertable
0x14001b473  xor     ecx, ecx; WaitMode
0x14001b475  call    cs:__imp_KeDelayExecutionThread
0x14001b47c  nop     dword ptr [rax+rax+00h]
0x14001b481  mov     ebp, ebx
0x14001b483  mov     r14d, 2
0x14001b489  mov     ebx, ebp
0x14001b48b  mov     rdx, r15
0x14001b48e  mov     rcx, rsi
0x14001b491  call    XilRegister_ReadUlong
0x14001b496  test    al, 2
0x14001b498  jz      short loc_14001B4D7
0x14001b49a  cmp     ebp, 64h ; 'd'
0x14001b49d  jnz     loc_14001B559
0x14001b4a3  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001b4aa  jnz     loc_14001B68B
0x14001b4b0  mov     rcx, [rdi]
0x14001b4b3  mov     r8d, 3
0x14001b4b9  call    Etw_StartDeviceFail
0x14001b4be  mov     ebx, 0C0000001h
0x14001b4c3  mov     eax, ebx
0x14001b4c5  add     rsp, 48h
0x14001b4c9  pop     r15
0x14001b4cb  pop     r14
0x14001b4cd  pop     r13
0x14001b4cf  pop     r12
0x14001b4d1  pop     rdi
0x14001b4d2  pop     rsi
0x14001b4d3  pop     rbp
0x14001b4d4  pop     rbx
0x14001b4d5  retn
0x14001b4d7  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001b4de  lea     rbp, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x14001b4e5  jnz     loc_14001B6B7
0x14001b4eb  cmp     ebx, 32h ; '2'
0x14001b4ee  ja      loc_14001B6DC
0x14001b4f4  mov     rcx, rsi
0x14001b4f7  call    Register_WaitForControllerReady
0x14001b4fc  mov     ebx, eax
0x14001b4fe  test    eax, eax
0x14001b500  js      loc_14001B70E
0x14001b506  mov     rax, [rdi]
0x14001b509  test    byte ptr [rax+2F0h], 10h
0x14001b510  jnz     loc_14001B720
0x14001b516  mov     rax, [rdi]
0x14001b519  mov     ecx, [rax+2E8h]
0x14001b51f  bt      rcx, 19h
0x14001b524  jb      loc_14001B749
0x14001b52a  mov     rax, [rdi]
0x14001b52d  mov     rcx, [rax+0A8h]
0x14001b534  test    rcx, rcx
0x14001b537  jnz     loc_14001B772
0x14001b53d  mov     rcx, rsi
0x14001b540  call    Register_RestoreRyzenFeatureBitsPostReset
0x14001b545  mov     rcx, rsi
0x14001b548  call    Register_DisableComplianceModeCapability
0x14001b54d  jmp     loc_14001B4C3
0x14001b552  xor     ebx, ebx
0x14001b554  jmp     loc_14001B4C3
0x14001b559  mov     eax, r14d
0x14001b55c  lea     r8, [rsp+88h+Interval]; Interval
0x14001b564  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x14001b56b  xor     edx, edx; Alertable
0x14001b56d  mov     qword ptr [rsp+88h+Interval], rcx
0x14001b575  xor     ecx, ecx; WaitMode
0x14001b577  call    cs:__imp_KeDelayExecutionThread
0x14001b57e  nop     dword ptr [rax+rax+00h]
0x14001b583  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001b58a  jnz     loc_14001B659
0x14001b590  add     ebx, r14d
0x14001b593  lea     eax, [r14+r14]
0x14001b597  inc     ebp
0x14001b599  cmp     r14d, 10h
0x14001b59d  cmovz   eax, r14d
0x14001b5a1  mov     r14d, eax
0x14001b5a4  jmp     loc_14001B48B
0x14001b5a9  xor     ebp, ebp
0x14001b5ab  mov     r14d, ebx
0x14001b5ae  jmp     loc_14001B489
0x14001b5b3  mov     rcx, [rdi]
0x14001b5b6  mov     r9d, 3Fh ; '?'
0x14001b5bc  mov     r8d, r13d
0x14001b5bf  mov     [rsp+88h+var_68], r14
0x14001b5c4  mov     dl, 4
0x14001b5c6  mov     rcx, [rcx+48h]
0x14001b5ca  call    WPP_RECORDER_SF_
0x14001b5cf  jmp     loc_14001B3FE
0x14001b5d4  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001b5db  jz      loc_14001B4C3
0x14001b5e1  mov     dword ptr [rsp+88h+var_60], eax
0x14001b5e5  mov     r9d, 40h ; '@'
0x14001b5eb  mov     [rsp+88h+var_68], r14
0x14001b5f0  jmp     short loc_14001B601
0x14001b5f2  mov     dword ptr [rsp+88h+var_60], eax
0x14001b5f6  mov     r9d, 46h ; 'F'
0x14001b5fc  mov     [rsp+88h+var_68], rbp
0x14001b601  mov     rcx, [rdi]
0x14001b604  mov     r8d, r13d
0x14001b607  mov     dl, 2
0x14001b609  mov     rcx, [rcx+48h]
0x14001b60d  call    WPP_RECORDER_SF_d
0x14001b612  jmp     loc_14001B4C3
0x14001b617  lea     rdx, [r15+4]
0x14001b61b  mov     rcx, rsi
0x14001b61e  call    XilRegister_ReadUlong
0x14001b623  test    bl, al
0x14001b625  jnz     loc_14001B432
0x14001b62b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001b632  jz      loc_14001B4BE
0x14001b638  mov     rcx, [rdi]
0x14001b63b  mov     r9d, 41h ; 'A'
0x14001b641  mov     r8d, r13d
0x14001b644  mov     [rsp+88h+var_68], r14
0x14001b649  mov     dl, 2
0x14001b64b  mov     rcx, [rcx+48h]
0x14001b64f  call    WPP_RECORDER_SF_
0x14001b654  jmp     loc_14001B4BE
0x14001b659  mov     rcx, [rsi+8]
0x14001b65d  lea     rax, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x14001b664  mov     [rsp+88h+var_58], r14d
0x14001b669  mov     r9d, 45h ; 'E'
0x14001b66f  mov     dword ptr [rsp+88h+var_60], ebp
0x14001b673  mov     r8d, r13d
0x14001b676  mov     dl, 4
0x14001b678  mov     [rsp+88h+var_68], rax
0x14001b67d  mov     rcx, [rcx+48h]
0x14001b681  call    WPP_RECORDER_SF_DD
0x14001b686  jmp     loc_14001B590
0x14001b68b  mov     rcx, [rdi]
0x14001b68e  lea     rax, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x14001b695  mov     r9d, 44h ; 'D'
0x14001b69b  mov     dword ptr [rsp+88h+var_60], ebx
0x14001b69f  mov     r8d, r13d
0x14001b6a2  mov     [rsp+88h+var_68], rax
0x14001b6a7  mov     dl, 1
0x14001b6a9  mov     rcx, [rcx+48h]
0x14001b6ad  call    WPP_RECORDER_SF_D
0x14001b6b2  jmp     loc_14001B4B0
0x14001b6b7  mov     rcx, [rdi]
0x14001b6ba  mov     r9d, 42h ; 'B'
0x14001b6c0  mov     dword ptr [rsp+88h+var_60], ebx
0x14001b6c4  mov     r8d, r13d
0x14001b6c7  mov     dl, 4
0x14001b6c9  mov     [rsp+88h+var_68], rbp
0x14001b6ce  mov     rcx, [rcx+48h]
0x14001b6d2  call    WPP_RECORDER_SF_D
0x14001b6d7  jmp     loc_14001B4EB
0x14001b6dc  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001b6e3  jz      loc_14001B4F4
0x14001b6e9  mov     rcx, [rdi]
0x14001b6ec  mov     r9d, 43h ; 'C'
0x14001b6f2  mov     dword ptr [rsp+88h+var_60], ebx
0x14001b6f6  mov     r8d, r13d
0x14001b6f9  mov     dl, 2
0x14001b6fb  mov     [rsp+88h+var_68], rbp
0x14001b700  mov     rcx, [rcx+48h]
0x14001b704  call    WPP_RECORDER_SF_D
0x14001b709  jmp     loc_14001B4F4
0x14001b70e  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001b715  jz      loc_14001B4C3
0x14001b71b  jmp     loc_14001B5F2
0x14001b720  lea     r8, [rsp+88h+Interval]; Interval
0x14001b728  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFF0BDC0h
0x14001b734  xor     edx, edx; Alertable
0x14001b736  xor     ecx, ecx; WaitMode
0x14001b738  call    cs:__imp_KeDelayExecutionThread
0x14001b73f  nop     dword ptr [rax+rax+00h]
0x14001b744  jmp     loc_14001B516
0x14001b749  lea     r8, [rsp+88h+Interval]; Interval
0x14001b751  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFE488C0h
0x14001b75d  xor     edx, edx; Alertable
0x14001b75f  xor     ecx, ecx; WaitMode
0x14001b761  call    cs:__imp_KeDelayExecutionThread
0x14001b768  nop     dword ptr [rax+rax+00h]
0x14001b76d  jmp     loc_14001B52A
0x14001b772  mov     rax, [rcx+20h]
0x14001b776  test    rax, rax
0x14001b779  jz      loc_14001B53D
0x14001b77f  call    _guard_dispatch_icall
0x14001b784  jmp     loc_14001B53D
```
