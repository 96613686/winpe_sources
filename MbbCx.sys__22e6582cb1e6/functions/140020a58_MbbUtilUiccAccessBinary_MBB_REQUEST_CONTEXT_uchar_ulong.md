# MbbUtilUiccAccessBinary(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140020a58`
- end: `0x140020b32`
- name: `?MbbUtilUiccAccessBinary@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400174a0`

## callees

- `0x140001cf8`
- `0x14001fc2c`
- `0x140020a58`
- `0x140023a7c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140020aa3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020aa3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020a89`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020a89`

## pseudocode

```c
__int64 __fastcall MbbUtilUiccAccessBinary(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  __int64 v5; // rdi
  KIRQL v6; // al
  int v7; // ebx
  int v8; // edx
  __int64 result; // rax
  unsigned __int8 *v10; // rdx
  unsigned int v11; // r8d
  struct _MBB_UICC_ACCESS_BINARY *v12; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+60h] [rbp+18h] BYREF
  int v14; // [rsp+64h] [rbp+1Ch]

  v14 = HIDWORD(a3);
  v12 = 0;
  v13 = 0;
  v5 = **((_QWORD **)a1 + 6);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5);
  v7 = *(_DWORD *)(v5 + 1088);
  *(_BYTE *)(v5 + 8) = v6;
  KeReleaseSpinLock((PKSPIN_LOCK)v5, v6);
  if ( (v7 & 0x100000) != 0 )
  {
    result = MbbUtilWwanToMbbUiccAccessBinary((struct _WWAN_UICC_ACCESS_BINARY *)(a2 + 4), &v12, &v13);
    if ( !(_DWORD)result )
    {
      v10 = (unsigned __int8 *)v12;
      v11 = v13;
      *((_QWORD *)a1 + 70) = v12;
      return MbbUtilQueryAttributeWithParameter(a1, v10, v11);
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
        3,
        41,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
    }
    return 3221225659LL;
  }
  return result;
}

```

## disassembly

```asm
0x140020a58  mov     rax, rsp
0x140020a5b  mov     [rax+10h], rbx
0x140020a5f  mov     [rax+18h], r8
0x140020a63  push    rbp
0x140020a64  push    rsi
0x140020a65  push    rdi
0x140020a66  sub     rsp, 30h
0x140020a6a  mov     qword ptr [rax+8], 0
0x140020a72  mov     rsi, rcx
0x140020a75  mov     dword ptr [rax+18h], 0
0x140020a7c  mov     rbp, rdx
0x140020a7f  mov     rax, [rcx+30h]
0x140020a83  mov     rdi, [rax]
0x140020a86  mov     rcx, rdi; SpinLock
0x140020a89  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140020a90  nop     dword ptr [rax+rax+00h]
0x140020a95  mov     ebx, [rdi+440h]
0x140020a9b  mov     rcx, rdi; SpinLock
0x140020a9e  mov     dl, al; NewIrql
0x140020aa0  mov     [rdi+8], al
0x140020aa3  call    cs:__imp_KeReleaseSpinLock
0x140020aaa  nop     dword ptr [rax+rax+00h]
0x140020aaf  bt      ebx, 14h
0x140020ab3  jb      short loc_140020AF4
0x140020ab5  lea     rax, WPP_RECORDER_INITIALIZED
0x140020abc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020ac3  jz      short loc_140020AED
0x140020ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x140020acc  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140020ad3  mov     r9d, 29h ; ')'
0x140020ad9  mov     [rsp+48h+var_28], rax
0x140020ade  mov     dl, 4
0x140020ae0  mov     rcx, [rcx+40h]
0x140020ae4  lea     r8d, [r9-26h]
0x140020ae8  call    WPP_RECORDER_SF_
0x140020aed  mov     eax, 0C00000BBh
0x140020af2  jmp     short loc_140020B24
0x140020af4  lea     rcx, [rbp+4]; struct _WWAN_UICC_ACCESS_BINARY *
0x140020af8  lea     r8, [rsp+48h+arg_10]; unsigned int *
0x140020afd  lea     rdx, [rsp+48h+arg_0]; struct _MBB_UICC_ACCESS_BINARY **
0x140020b02  call    ?MbbUtilWwanToMbbUiccAccessBinary@@YAHPEAU_WWAN_UICC_ACCESS_BINARY@@PEAPEAU_MBB_UICC_ACCESS_BINARY@@PEAK@Z; MbbUtilWwanToMbbUiccAccessBinary(_WWAN_UICC_ACCESS_BINARY *,_MBB_UICC_ACCESS_BINARY * *,ulong *)
0x140020b07  test    eax, eax
0x140020b09  jnz     short loc_140020B24
0x140020b0b  mov     rdx, [rsp+48h+arg_0]; unsigned __int8 *
0x140020b10  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x140020b13  mov     r8d, [rsp+48h+arg_10]; unsigned int
0x140020b18  mov     [rsi+230h], rdx
0x140020b1f  call    ?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140020b24  mov     rbx, [rsp+48h+arg_8]
0x140020b29  add     rsp, 30h
0x140020b2d  pop     rdi
0x140020b2e  pop     rsi
0x140020b2f  pop     rbp
0x140020b30  retn
```
