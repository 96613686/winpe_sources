# MbbUtilUiccAccessRecord(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140020b38`
- end: `0x140020c12`
- name: `?MbbUtilUiccAccessRecord@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400174c0`

## callees

- `0x140001cf8`
- `0x14001fc2c`
- `0x140020b38`
- `0x140023bb4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140020b83`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020b83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020b69`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020b69`

## pseudocode

```c
__int64 __fastcall MbbUtilUiccAccessRecord(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  __int64 v5; // rdi
  KIRQL v6; // al
  int v7; // ebx
  int v8; // edx
  __int64 result; // rax
  unsigned __int8 *v10; // rdx
  unsigned int v11; // r8d
  struct _MBB_UICC_ACCESS_RECORD *v12; // [rsp+50h] [rbp+8h] BYREF
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
    result = MbbUtilWwanToMbbUiccAccessRecord((struct _WWAN_UICC_ACCESS_RECORD *)(a2 + 4), &v12, &v13);
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
        42,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
    }
    return 3221225659LL;
  }
  return result;
}

```

## disassembly

```asm
0x140020b38  mov     rax, rsp
0x140020b3b  mov     [rax+10h], rbx
0x140020b3f  mov     [rax+18h], r8
0x140020b43  push    rbp
0x140020b44  push    rsi
0x140020b45  push    rdi
0x140020b46  sub     rsp, 30h
0x140020b4a  mov     qword ptr [rax+8], 0
0x140020b52  mov     rsi, rcx
0x140020b55  mov     dword ptr [rax+18h], 0
0x140020b5c  mov     rbp, rdx
0x140020b5f  mov     rax, [rcx+30h]
0x140020b63  mov     rdi, [rax]
0x140020b66  mov     rcx, rdi; SpinLock
0x140020b69  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140020b70  nop     dword ptr [rax+rax+00h]
0x140020b75  mov     ebx, [rdi+440h]
0x140020b7b  mov     rcx, rdi; SpinLock
0x140020b7e  mov     dl, al; NewIrql
0x140020b80  mov     [rdi+8], al
0x140020b83  call    cs:__imp_KeReleaseSpinLock
0x140020b8a  nop     dword ptr [rax+rax+00h]
0x140020b8f  bt      ebx, 14h
0x140020b93  jb      short loc_140020BD4
0x140020b95  lea     rax, WPP_RECORDER_INITIALIZED
0x140020b9c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020ba3  jz      short loc_140020BCD
0x140020ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x140020bac  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140020bb3  mov     r9d, 2Ah ; '*'
0x140020bb9  mov     [rsp+48h+var_28], rax
0x140020bbe  mov     dl, 4
0x140020bc0  mov     rcx, [rcx+40h]
0x140020bc4  lea     r8d, [r9-27h]
0x140020bc8  call    WPP_RECORDER_SF_
0x140020bcd  mov     eax, 0C00000BBh
0x140020bd2  jmp     short loc_140020C04
0x140020bd4  lea     rcx, [rbp+4]; struct _WWAN_UICC_ACCESS_RECORD *
0x140020bd8  lea     r8, [rsp+48h+arg_10]; unsigned int *
0x140020bdd  lea     rdx, [rsp+48h+arg_0]; struct _MBB_UICC_ACCESS_RECORD **
0x140020be2  call    ?MbbUtilWwanToMbbUiccAccessRecord@@YAHPEAU_WWAN_UICC_ACCESS_RECORD@@PEAPEAU_MBB_UICC_ACCESS_RECORD@@PEAK@Z; MbbUtilWwanToMbbUiccAccessRecord(_WWAN_UICC_ACCESS_RECORD *,_MBB_UICC_ACCESS_RECORD * *,ulong *)
0x140020be7  test    eax, eax
0x140020be9  jnz     short loc_140020C04
0x140020beb  mov     rdx, [rsp+48h+arg_0]; unsigned __int8 *
0x140020bf0  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x140020bf3  mov     r8d, [rsp+48h+arg_10]; unsigned int
0x140020bf8  mov     [rsi+230h], rdx
0x140020bff  call    ?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140020c04  mov     rbx, [rsp+48h+arg_8]
0x140020c09  add     rsp, 30h
0x140020c0d  pop     rdi
0x140020c0e  pop     rsi
0x140020c0f  pop     rbp
0x140020c10  retn
```
