# MbbNdisSetSarConfig(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140015fc0`
- end: `0x140016135`
- name: `?MbbNdisSetSarConfig@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `373`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x140015fc0`
- `0x1400208bc`
- `0x140022d98`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001600f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001600f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015ff5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015ff5`

## pseudocode

```c
__int64 __fastcall MbbNdisSetSarConfig(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  __int64 v6; // rdi
  KIRQL v7; // al
  int v8; // ebx
  unsigned __int64 v9; // rdx
  __int64 result; // rax
  unsigned int v11; // eax
  unsigned __int8 *v12; // rdx
  unsigned int v13; // r8d
  unsigned int v14; // [rsp+50h] [rbp+8h] BYREF
  struct _MBB_SET_SAR_CONFIG *v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  v14 = 0;
  v6 = **((_QWORD **)a1 + 6);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6);
  v8 = *(_DWORD *)(v6 + 1088);
  *(_BYTE *)(v6 + 8) = v7;
  KeReleaseSpinLock((PKSPIN_LOCK)v6, v7);
  if ( (v8 & 0x400) != 0 )
  {
    if ( a2
      && a3
      && *a3 >= 0x14
      && (v9 = 8LL * *((unsigned int *)a2 + 4), v9 <= 0xFFFFFFFF)
      && (v11 = (v9 + 3) & 0xFFFFFFFC, v11 + 12 >= v11)
      && (LODWORD(v9) = (v9 + 3) & 0xFFFFFFFC, v11 + 12 + (unsigned int)v9 >= (unsigned int)v9) )
    {
      result = MbbUtilWwanToMbbSetSarConfig((struct _WWAN_SET_SAR_CONFIG *)(a2 + 4), &v15, &v14);
      if ( !(_DWORD)result )
      {
        v12 = (unsigned __int8 *)v15;
        v13 = v14;
        *((_QWORD *)a1 + 70) = v15;
        return MbbUtilSetAttributeWithParameter(a1, v12, v13);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          1,
          147,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          *((_DWORD *)a1 + 4));
      }
      return 3221291029LL;
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
        1,
        146,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
    }
    return 3221225659LL;
  }
  return result;
}

```

## disassembly

```asm
0x140015fc0  mov     rax, rsp
0x140015fc3  mov     [rax+18h], rbx
0x140015fc7  mov     [rax+20h], rbp
0x140015fcb  push    rsi
0x140015fcc  push    rdi
0x140015fcd  push    r14
0x140015fcf  sub     rsp, 30h
0x140015fd3  mov     qword ptr [rax+10h], 0
0x140015fdb  mov     rsi, rcx
0x140015fde  mov     dword ptr [rax+8], 0
0x140015fe5  mov     rbp, r8
0x140015fe8  mov     rax, [rcx+30h]
0x140015fec  mov     r14, rdx
0x140015fef  mov     rdi, [rax]
0x140015ff2  mov     rcx, rdi; SpinLock
0x140015ff5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015ffc  nop     dword ptr [rax+rax+00h]
0x140016001  mov     ebx, [rdi+440h]
0x140016007  mov     rcx, rdi; SpinLock
0x14001600a  mov     dl, al; NewIrql
0x14001600c  mov     [rdi+8], al
0x14001600f  call    cs:__imp_KeReleaseSpinLock
0x140016016  nop     dword ptr [rax+rax+00h]
0x14001601b  bt      ebx, 0Ah
0x14001601f  jb      short loc_140016065
0x140016021  lea     rax, WPP_RECORDER_INITIALIZED
0x140016028  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001602f  jz      short loc_14001605B
0x140016031  mov     rcx, cs:WPP_GLOBAL_Control
0x140016038  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001603f  mov     r9d, 92h
0x140016045  mov     [rsp+48h+var_28], rax
0x14001604a  mov     r8d, 1
0x140016050  mov     dl, 4
0x140016052  mov     rcx, [rcx+40h]
0x140016056  call    WPP_RECORDER_SF_
0x14001605b  mov     eax, 0C00000BBh
0x140016060  jmp     loc_140016121
0x140016065  test    r14, r14
0x140016068  jz      short loc_1400160DB
0x14001606a  test    rbp, rbp
0x14001606d  jz      short loc_1400160DB
0x14001606f  cmp     dword ptr [rbp+0], 14h
0x140016073  jb      short loc_1400160DB
0x140016075  lea     rcx, [r14+4]; struct _WWAN_SET_SAR_CONFIG *
0x140016079  mov     eax, 0FFFFFFFFh
0x14001607e  mov     edx, [rcx+0Ch]
0x140016081  shl     rdx, 3
0x140016085  cmp     rdx, rax
0x140016088  ja      short loc_1400160DB
0x14001608a  lea     eax, [rdx+3]
0x14001608d  mov     r9d, 0FFFFFFFCh
0x140016093  and     eax, r9d
0x140016096  lea     r8d, [rax+0Ch]
0x14001609a  cmp     r8d, eax
0x14001609d  jb      short loc_1400160DB
0x14001609f  add     edx, 3
0x1400160a2  and     edx, r9d
0x1400160a5  lea     eax, [r8+rdx]
0x1400160a9  cmp     eax, edx
0x1400160ab  jb      short loc_1400160DB
0x1400160ad  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x1400160b2  lea     rdx, [rsp+48h+arg_8]; struct _MBB_SET_SAR_CONFIG **
0x1400160b7  call    ?MbbUtilWwanToMbbSetSarConfig@@YAHPEAU_WWAN_SET_SAR_CONFIG@@PEAPEAU_MBB_SET_SAR_CONFIG@@PEAK@Z; MbbUtilWwanToMbbSetSarConfig(_WWAN_SET_SAR_CONFIG *,_MBB_SET_SAR_CONFIG * *,ulong *)
0x1400160bc  test    eax, eax
0x1400160be  jnz     short loc_140016121
0x1400160c0  mov     rdx, [rsp+48h+arg_8]; unsigned __int8 *
0x1400160c5  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x1400160c8  mov     r8d, [rsp+48h+arg_0]; unsigned int
0x1400160cd  mov     [rsi+230h], rdx
0x1400160d4  call    ?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x1400160d9  jmp     short loc_140016121
0x1400160db  lea     rax, WPP_RECORDER_INITIALIZED
0x1400160e2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400160e9  jz      short loc_14001611C
0x1400160eb  mov     eax, [rsi+10h]
0x1400160ee  mov     r9d, 93h
0x1400160f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400160fb  mov     r8d, 1
0x140016101  mov     [rsp+48h+var_20], eax
0x140016105  mov     dl, 2
0x140016107  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001610e  mov     [rsp+48h+var_28], rax
0x140016113  mov     rcx, [rcx+40h]
0x140016117  call    WPP_RECORDER_SF_d
0x14001611c  mov     eax, 0C0010015h
0x140016121  mov     rbx, [rsp+48h+arg_10]
0x140016126  mov     rbp, [rsp+48h+arg_18]
0x14001612b  add     rsp, 30h
0x14001612f  pop     r14
0x140016131  pop     rdi
0x140016132  pop     rsi
0x140016133  retn
```
