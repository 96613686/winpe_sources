# MbbNdisSetModemLoggingConfig(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140014d50`
- end: `0x140014e96`
- name: `?MbbNdisSetModemLoggingConfig@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `326`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x140014d50`
- `0x1400208bc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140014de9`
- `ntoskrnl!ExAllocatePool2` at `0x140014de9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e7b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014d83`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014d83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014d69`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014d69`

## pseudocode

```c
__int64 __fastcall MbbNdisSetModemLoggingConfig(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  __int64 v5; // rdi
  KIRQL v6; // al
  int v7; // ebx
  int v8; // edx
  __int64 Pool2; // rax
  int v11; // edx
  void *v12; // rbx
  unsigned int v13; // ecx

  v5 = **((_QWORD **)a1 + 6);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5);
  v7 = *(_DWORD *)(v5 + 1088);
  *(_BYTE *)(v5 + 8) = v6;
  KeReleaseSpinLock((PKSPIN_LOCK)v5, v6);
  if ( (v7 & 0x40000) != 0 )
  {
    Pool2 = ExAllocatePool2(64, 16, 1683505741);
    v12 = (void *)Pool2;
    if ( Pool2 )
    {
      v13 = *((_DWORD *)a2 + 4);
      *(_DWORD *)Pool2 = *((_DWORD *)a2 + 1);
      *(_DWORD *)(Pool2 + 4) = *((_DWORD *)a2 + 2);
      *(_DWORD *)(Pool2 + 8) = *((_DWORD *)a2 + 3);
      if ( v13 > 4 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            9,
            72,
            (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
            v13);
        }
        ExFreePoolWithTag(v12, 0);
        return 3221291029LL;
      }
      else
      {
        *(_DWORD *)(Pool2 + 12) = v13;
        *((_QWORD *)a1 + 70) = Pool2;
        return MbbUtilSetAttributeWithParameter(a1, (unsigned __int8 *)Pool2, 0x10u);
      }
    }
    else
    {
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        1,
        151,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
    }
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x140014d50  push    rbx
0x140014d52  push    rbp
0x140014d53  push    rsi
0x140014d54  push    rdi
0x140014d55  sub     rsp, 38h
0x140014d59  mov     rax, [rcx+30h]
0x140014d5d  mov     rbp, rcx
0x140014d60  mov     rsi, rdx
0x140014d63  mov     rdi, [rax]
0x140014d66  mov     rcx, rdi; SpinLock
0x140014d69  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014d70  nop     dword ptr [rax+rax+00h]
0x140014d75  mov     ebx, [rdi+440h]
0x140014d7b  mov     rcx, rdi; SpinLock
0x140014d7e  mov     dl, al; NewIrql
0x140014d80  mov     [rdi+8], al
0x140014d83  call    cs:__imp_KeReleaseSpinLock
0x140014d8a  nop     dword ptr [rax+rax+00h]
0x140014d8f  bt      ebx, 12h
0x140014d93  jb      short loc_140014DD9
0x140014d95  lea     rax, WPP_RECORDER_INITIALIZED
0x140014d9c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014da3  jz      short loc_140014DCF
0x140014da5  mov     rcx, cs:WPP_GLOBAL_Control
0x140014dac  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140014db3  mov     r9d, 97h
0x140014db9  mov     [rsp+58h+var_38], rax
0x140014dbe  mov     r8d, 1
0x140014dc4  mov     dl, 4
0x140014dc6  mov     rcx, [rcx+40h]
0x140014dca  call    WPP_RECORDER_SF_
0x140014dcf  mov     eax, 0C00000BBh
0x140014dd4  jmp     loc_140014E8C
0x140014dd9  mov     edi, 10h
0x140014dde  mov     r8d, 6458424Dh
0x140014de4  mov     edx, edi
0x140014de6  lea     ecx, [rdi+30h]
0x140014de9  call    cs:__imp_ExAllocatePool2
0x140014df0  nop     dword ptr [rax+rax+00h]
0x140014df5  mov     rbx, rax
0x140014df8  test    rax, rax
0x140014dfb  jnz     short loc_140014E07
0x140014dfd  mov     eax, 0C000009Ah
0x140014e02  jmp     loc_140014E8C
0x140014e07  mov     eax, [rsi+4]
0x140014e0a  mov     ecx, [rsi+10h]
0x140014e0d  mov     [rbx], eax
0x140014e0f  mov     eax, [rsi+8]
0x140014e12  mov     [rbx+4], eax
0x140014e15  mov     eax, [rsi+0Ch]
0x140014e18  mov     [rbx+8], eax
0x140014e1b  cmp     ecx, 4
0x140014e1e  ja      short loc_140014E3A
0x140014e20  mov     [rbx+0Ch], ecx
0x140014e23  mov     r8d, edi; unsigned int
0x140014e26  mov     rcx, rbp; struct _MBB_REQUEST_CONTEXT *
0x140014e29  mov     [rbp+230h], rbx
0x140014e30  mov     rdx, rbx; unsigned __int8 *
0x140014e33  call    ?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140014e38  jmp     short loc_140014E8C
0x140014e3a  lea     rax, WPP_RECORDER_INITIALIZED
0x140014e41  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014e48  jz      short loc_140014E76
0x140014e4a  mov     [rsp+58h+var_30], ecx
0x140014e4e  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140014e55  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e5c  mov     r9d, 48h ; 'H'
0x140014e62  mov     dl, 2
0x140014e64  mov     [rsp+58h+var_38], rax
0x140014e69  mov     rcx, [rcx+40h]
0x140014e6d  lea     r8d, [r9-3Fh]
0x140014e71  call    WPP_RECORDER_SF_d
0x140014e76  xor     edx, edx; Tag
0x140014e78  mov     rcx, rbx; P
0x140014e7b  call    cs:__imp_ExFreePoolWithTag
0x140014e82  nop     dword ptr [rax+rax+00h]
0x140014e87  mov     eax, 0C0010015h
0x140014e8c  add     rsp, 38h
0x140014e90  pop     rdi
0x140014e91  pop     rsi
0x140014e92  pop     rbp
0x140014e93  pop     rbx
0x140014e94  retn
```
