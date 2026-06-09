# MbbNdisSetUiccOpenChannel(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x1400168f0`
- end: `0x1400169da`
- name: `?MbbNdisSetUiccOpenChannel@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140001cf8`
- `0x1400168f0`
- `0x14001d530`
- `0x14001d5f8`
- `0x1400208bc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001692e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001692e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016914`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016914`

## pseudocode

```c
__int64 __fastcall MbbNdisSetUiccOpenChannel(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  PKSPIN_LOCK *v3; // rax
  PKSPIN_LOCK v6; // rsi
  KIRQL v7; // al
  int v8; // ebx
  int v9; // edx
  __int64 result; // rax
  unsigned __int8 *v11; // rcx
  unsigned __int8 *v12; // rdx
  unsigned int v13; // r8d
  unsigned int v14; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int8 *v15; // [rsp+58h] [rbp+10h] BYREF

  v3 = (PKSPIN_LOCK *)*((_QWORD *)a1 + 6);
  v14 = 0;
  v6 = *v3;
  v7 = KeAcquireSpinLockRaiseToDpc(*v3);
  v8 = *((_DWORD *)v6 + 272);
  *((_BYTE *)v6 + 8) = v7;
  KeReleaseSpinLock(v6, v7);
  if ( (v8 & 0x2000) != 0 )
  {
    v15 = 0;
    v11 = a2 + 4;
    if ( *((_WORD *)v6 + 41) < 0x400u )
      result = MbbUtilWwanToMbbSetUiccOpenChannel<_MBB_SET_UICC_OPEN_CHANNEL>((__int64)v11, (__int64 *)&v15, &v14);
    else
      result = MbbUtilWwanToMbbSetUiccOpenChannel<_MBB_SET_UICC_OPEN_CHANNEL_EX4>((__int64)v11, (__int64 *)&v15, &v14);
    if ( !(_DWORD)result )
    {
      v12 = v15;
      v13 = v14;
      *((_QWORD *)a1 + 70) = v15;
      return MbbUtilSetAttributeWithParameter(a1, v12, v13);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        139,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
    }
    return 3221225659LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400168f0  mov     [rsp+arg_10], rbx
0x1400168f5  push    rbp
0x1400168f6  push    rsi
0x1400168f7  push    rdi
0x1400168f8  sub     rsp, 30h
0x1400168fc  mov     rax, [rcx+30h]
0x140016900  mov     rdi, rcx
0x140016903  mov     rbp, rdx
0x140016906  mov     [rsp+48h+arg_0], 0
0x14001690e  mov     rsi, [rax]
0x140016911  mov     rcx, rsi; SpinLock
0x140016914  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001691b  nop     dword ptr [rax+rax+00h]
0x140016920  mov     ebx, [rsi+440h]
0x140016926  mov     rcx, rsi; SpinLock
0x140016929  mov     dl, al; NewIrql
0x14001692b  mov     [rsi+8], al
0x14001692e  call    cs:__imp_KeReleaseSpinLock
0x140016935  nop     dword ptr [rax+rax+00h]
0x14001693a  bt      ebx, 0Dh
0x14001693e  jb      short loc_140016981
0x140016940  lea     rax, WPP_RECORDER_INITIALIZED
0x140016947  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001694e  jz      short loc_14001697A
0x140016950  mov     rcx, cs:WPP_GLOBAL_Control
0x140016957  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001695e  mov     r9d, 8Bh
0x140016964  mov     [rsp+48h+var_28], rax
0x140016969  mov     r8d, 3
0x14001696f  mov     dl, 4
0x140016971  mov     rcx, [rcx+40h]
0x140016975  call    WPP_RECORDER_SF_
0x14001697a  mov     eax, 0C00000BBh
0x14001697f  jmp     short loc_1400169CC
0x140016981  mov     eax, 400h
0x140016986  mov     [rsp+48h+arg_8], 0
0x14001698f  lea     rcx, [rbp+4]
0x140016993  lea     r8, [rsp+48h+arg_0]
0x140016998  lea     rdx, [rsp+48h+arg_8]
0x14001699d  cmp     [rsi+52h], ax
0x1400169a1  jb      short loc_1400169AA
0x1400169a3  call    ??$MbbUtilWwanToMbbSetUiccOpenChannel@U_MBB_SET_UICC_OPEN_CHANNEL_EX4@@@@YAHPEAU_WWAN_SET_UICC_OPEN_CHANNEL@@PEAPEAU_MBB_SET_UICC_OPEN_CHANNEL_EX4@@PEAK@Z; MbbUtilWwanToMbbSetUiccOpenChannel<_MBB_SET_UICC_OPEN_CHANNEL_EX4>(_WWAN_SET_UICC_OPEN_CHANNEL *,_MBB_SET_UICC_OPEN_CHANNEL_EX4 * *,ulong *)
0x1400169a8  jmp     short loc_1400169AF
0x1400169aa  call    ??$MbbUtilWwanToMbbSetUiccOpenChannel@U_MBB_SET_UICC_OPEN_CHANNEL@@@@YAHPEAU_WWAN_SET_UICC_OPEN_CHANNEL@@PEAPEAU_MBB_SET_UICC_OPEN_CHANNEL@@PEAK@Z; MbbUtilWwanToMbbSetUiccOpenChannel<_MBB_SET_UICC_OPEN_CHANNEL>(_WWAN_SET_UICC_OPEN_CHANNEL *,_MBB_SET_UICC_OPEN_CHANNEL * *,ulong *)
0x1400169af  test    eax, eax
0x1400169b1  jnz     short loc_1400169CC
0x1400169b3  mov     rdx, [rsp+48h+arg_8]; unsigned __int8 *
0x1400169b8  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x1400169bb  mov     r8d, [rsp+48h+arg_0]; unsigned int
0x1400169c0  mov     [rdi+230h], rdx
0x1400169c7  call    ?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x1400169cc  mov     rbx, [rsp+48h+arg_10]
0x1400169d1  add     rsp, 30h
0x1400169d5  pop     rdi
0x1400169d6  pop     rsi
0x1400169d7  pop     rbp
0x1400169d8  retn
```
