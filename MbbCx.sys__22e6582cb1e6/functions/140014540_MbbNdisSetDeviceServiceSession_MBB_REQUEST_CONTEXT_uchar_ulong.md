# MbbNdisSetDeviceServiceSession(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140014540`
- end: `0x140014726`
- name: `?MbbNdisSetDeviceServiceSession@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `486`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x140001cf8`
- `0x1400051ac`
- `0x140014540`
- `0x140018610`
- `0x14001f5b8`
- `0x1400208bc`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140014596`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014596`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001457c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001457c`

## pseudocode

```c
__int64 __fastcall MbbNdisSetDeviceServiceSession(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3)
{
  PKSPIN_LOCK *v4; // rax
  PKSPIN_LOCK v7; // rdi
  KIRQL v8; // al
  int v9; // ebx
  int v10; // edx
  unsigned int *v12; // rbx
  int v13; // edx
  int v14; // r8d
  int v15; // ecx
  unsigned __int8 v16[16]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v17; // [rsp+50h] [rbp-38h]

  v17 = 0;
  v4 = (PKSPIN_LOCK *)*((_QWORD *)a1 + 6);
  *(_OWORD *)v16 = 0;
  v7 = *v4;
  v8 = KeAcquireSpinLockRaiseToDpc(*v4);
  v9 = *((_DWORD *)v7 + 272);
  *((_BYTE *)v7 + 8) = v8;
  KeReleaseSpinLock(v7, v8);
  if ( (v9 & 0x200000) != 0 )
  {
    v12 = (unsigned int *)(a2 + 4);
    *a3 = 28;
    if ( MbbUtilIsNativeMbnService((struct _GUID *)(a2 + 4)) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_D_guid_(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          v14,
          132,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          *((_DWORD *)a1 + 4),
          (__int64)(a2 + 4));
      }
      return 3221291029LL;
    }
    else
    {
      *(_OWORD *)((char *)a1 + 728) = *(_OWORD *)v12;
      *((_DWORD *)a1 + 186) = *((_DWORD *)a2 + 6);
      v15 = *((_DWORD *)a2 + 5);
      if ( (unsigned int)(v15 - 1) <= 1 )
      {
        *(_DWORD *)v16 = _byteswap_ulong(*v12);
        *(_WORD *)&v16[4] = __ROR2__(*((_WORD *)a2 + 4), 8);
        *(_WORD *)&v16[6] = __ROR2__(*((_WORD *)a2 + 5), 8);
        *(_QWORD *)&v16[8] = *(_QWORD *)(a2 + 12);
        LODWORD(v17) = *((_DWORD *)a2 + 6);
        HIDWORD(v17) = v15 == 1;
        *((_DWORD *)a1 + 187) = HIDWORD(v17);
        return MbbUtilSetAttributeWithParameter(a1, v16, 0x18u);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_DD(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            3,
            133,
            (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
            *((_DWORD *)a1 + 4),
            v15);
        }
        return 3221225485LL;
      }
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        131,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
    }
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x140014540  push    rbx
0x140014542  push    rbp
0x140014543  push    rsi
0x140014544  push    rdi
0x140014545  push    r14
0x140014547  sub     rsp, 60h
0x14001454b  mov     rax, cs:__security_cookie
0x140014552  xor     rax, rsp
0x140014555  mov     [rsp+88h+var_30], rax
0x14001455a  xor     eax, eax
0x14001455c  xorps   xmm0, xmm0
0x14001455f  mov     [rsp+88h+var_38], rax
0x140014564  mov     rsi, rcx
0x140014567  mov     rax, [rcx+30h]
0x14001456b  mov     r14, r8
0x14001456e  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x140014573  mov     rbp, rdx
0x140014576  mov     rdi, [rax]
0x140014579  mov     rcx, rdi; SpinLock
0x14001457c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014583  nop     dword ptr [rax+rax+00h]
0x140014588  mov     ebx, [rdi+440h]
0x14001458e  mov     rcx, rdi; SpinLock
0x140014591  mov     dl, al; NewIrql
0x140014593  mov     [rdi+8], al
0x140014596  call    cs:__imp_KeReleaseSpinLock
0x14001459d  nop     dword ptr [rax+rax+00h]
0x1400145a2  bt      ebx, 15h
0x1400145a6  jb      short loc_1400145EA
0x1400145a8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400145af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400145b6  jz      short loc_1400145E0
0x1400145b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400145bf  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400145c6  mov     r9d, 83h
0x1400145cc  mov     [rsp+88h+var_68], rax
0x1400145d1  mov     dl, 4
0x1400145d3  mov     rcx, [rcx+40h]
0x1400145d7  lea     r8d, [r9-80h]
0x1400145db  call    WPP_RECORDER_SF_
0x1400145e0  mov     eax, 0C00000BBh
0x1400145e5  jmp     loc_14001470D
0x1400145ea  lea     rbx, [rbp+4]
0x1400145ee  mov     dword ptr [r14], 1Ch
0x1400145f5  mov     rcx, rbx; Source2
0x1400145f8  call    ?MbbUtilIsNativeMbnService@@YAEPEAU_GUID@@@Z; MbbUtilIsNativeMbnService(_GUID *)
0x1400145fd  test    al, al
0x1400145ff  jz      short loc_14001464B
0x140014601  lea     rax, WPP_RECORDER_INITIALIZED
0x140014608  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001460f  jz      short loc_140014641
0x140014611  mov     eax, [rsi+10h]
0x140014614  mov     r9d, 84h
0x14001461a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014621  mov     dl, 2
0x140014623  mov     [rsp+88h+var_58], rbx
0x140014628  mov     [rsp+88h+var_60], eax
0x14001462c  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140014633  mov     [rsp+88h+var_68], rax
0x140014638  mov     rcx, [rcx+40h]
0x14001463c  call    WPP_RECORDER_SF_D_guid_
0x140014641  mov     eax, 0C0010015h
0x140014646  jmp     loc_14001470D
0x14001464b  movups  xmm0, xmmword ptr [rbx]
0x14001464e  movdqu  xmmword ptr [rsi+2D8h], xmm0
0x140014656  mov     eax, [rbp+18h]
0x140014659  mov     [rsi+2E8h], eax
0x14001465f  mov     ecx, [rbp+14h]
0x140014662  lea     eax, [rcx-1]
0x140014665  cmp     eax, 1
0x140014668  jbe     short loc_1400146B6
0x14001466a  lea     rax, WPP_RECORDER_INITIALIZED
0x140014671  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014678  jz      short loc_1400146AF
0x14001467a  mov     eax, [rsi+10h]
0x14001467d  mov     r9d, 85h
0x140014683  mov     dword ptr [rsp+88h+var_58], ecx
0x140014687  mov     r8d, 3
0x14001468d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014694  mov     dl, 2
0x140014696  mov     [rsp+88h+var_60], eax
0x14001469a  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400146a1  mov     [rsp+88h+var_68], rax
0x1400146a6  mov     rcx, [rcx+40h]
0x1400146aa  call    WPP_RECORDER_SF_DD
0x1400146af  mov     eax, 0C000000Dh
0x1400146b4  jmp     short loc_14001470D
0x1400146b6  mov     eax, [rbx]
0x1400146b8  lea     rdx, [rsp+88h+var_48]; unsigned __int8 *
0x1400146bd  bswap   eax
0x1400146bf  mov     dword ptr [rsp+88h+var_48], eax
0x1400146c3  mov     r8d, 18h; unsigned int
0x1400146c9  movzx   eax, word ptr [rbp+8]
0x1400146cd  ror     ax, 8
0x1400146d1  mov     word ptr [rsp+88h+var_48+4], ax
0x1400146d6  movzx   eax, word ptr [rbp+0Ah]
0x1400146da  ror     ax, 8
0x1400146de  mov     word ptr [rsp+88h+var_48+6], ax
0x1400146e3  mov     rax, [rbp+0Ch]
0x1400146e7  mov     qword ptr [rsp+88h+var_48+8], rax
0x1400146ec  mov     eax, [rbp+18h]
0x1400146ef  mov     dword ptr [rsp+88h+var_38], eax
0x1400146f3  xor     eax, eax
0x1400146f5  cmp     ecx, 1
0x1400146f8  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x1400146fb  setz    al
0x1400146fe  mov     dword ptr [rsp+88h+var_38+4], eax
0x140014702  mov     [rsi+2ECh], eax
0x140014708  call    ?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x14001470d  mov     rcx, [rsp+88h+var_30]
0x140014712  xor     rcx, rsp; StackCookie
0x140014715  call    __security_check_cookie
0x14001471a  add     rsp, 60h
0x14001471e  pop     r14
0x140014720  pop     rdi
0x140014721  pop     rsi
0x140014722  pop     rbp
0x140014723  pop     rbx
0x140014724  retn
```
