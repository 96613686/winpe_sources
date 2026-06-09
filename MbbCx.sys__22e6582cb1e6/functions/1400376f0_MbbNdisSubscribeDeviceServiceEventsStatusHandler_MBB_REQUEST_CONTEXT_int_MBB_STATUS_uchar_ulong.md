# MbbNdisSubscribeDeviceServiceEventsStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x1400376f0`
- end: `0x14003797c`
- name: `?MbbNdisSubscribeDeviceServiceEventsStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `652`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x1400051ac`
- `0x1400376f0`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400377f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400377f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003782d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003782d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400377d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400377d9`

## pseudocode

```c
__int64 __fastcall MbbNdisSubscribeDeviceServiceEventsStatusHandler(__int64 a1, unsigned int a2, unsigned int a3)
{
  int v6; // edx
  int v7; // esi
  PVOID *v8; // r14
  int v9; // eax
  __int64 v10; // rdi
  KIRQL v11; // al
  void *v12; // rcx
  KIRQL v13; // dl
  __int64 v14; // rax
  __int64 v15; // rdx
  NDIS_HANDLE *v16; // rax
  struct _NDIS_STATUS_INDICATION v18; // [rsp+40h] [rbp-61h] BYREF
  __int128 v19; // [rsp+B0h] [rbp+Fh] BYREF

  memset(&v18, 0, sizeof(v18));
  v19 = 0;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        194,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
    v7 = -1073479677;
    v8 = (PVOID *)(a1 + 432);
  }
  else
  {
    v9 = MbbUtilMbbToWwanStatus(a3);
    v8 = (PVOID *)(a1 + 432);
    v7 = v9;
    if ( *(_QWORD *)(a1 + 432) && (*(_QWORD *)(a1 + 424) || *(_BYTE *)(a1 + 576)) && *(_BYTE *)(a1 + 452) && !v9 )
    {
      v10 = **(_QWORD **)(a1 + 48);
      v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v10);
      v12 = *(void **)(v10 + 1128);
      *(_BYTE *)(v10 + 8) = v11;
      if ( v12 )
      {
        ExFreePoolWithTag(v12, 0);
        *(_QWORD *)(v10 + 1128) = 0;
      }
      v13 = *(_BYTE *)(v10 + 8);
      *(_QWORD *)(v10 + 1128) = *(_QWORD *)(a1 + 728);
      *(_DWORD *)(v10 + 1124) = *(_DWORD *)(a1 + 736);
      KeReleaseSpinLock((PKSPIN_LOCK)v10, v13);
      *(_QWORD *)(a1 + 568) = 0;
    }
  }
  if ( *(_QWORD *)(a1 + 424) || *(_BYTE *)(a1 + 576) )
  {
    v14 = *(_QWORD *)(a1 + 48);
    v18.Header = (NDIS_OBJECT_HEADER)7340440;
    v18.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v14 + 1144LL) + 16LL);
    v18.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
    v18.RequestId = *v8;
    v18.StatusBuffer = &v19;
    v18.PortNumber = 0;
    *(_QWORD *)&v18.StatusCode = 1074008087;
    v18.Guid = 0;
    LODWORD(v19) = 1048960;
    *((_QWORD *)&v19 + 1) = 11;
    DWORD1(v19) = v7;
    v18.StatusBufferSize = 16;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        195,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v7);
    }
    v15 = *(_QWORD *)(a1 + 104);
    if ( v15 )
      v16 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031
                                                                                               + 1616))(
                              WdfDriverGlobals,
                              v15,
                              off_14005DF38)
                          + 24);
    else
      v16 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
    MbbUtilNdisMiniportIndicateStatusEx(v16, &v18);
  }
  return a2;
}

```

## disassembly

```asm
0x1400376f0  mov     [rsp-8+arg_8], rbx
0x1400376f5  push    rbp
0x1400376f6  push    rsi
0x1400376f7  push    rdi
0x1400376f8  push    r14
0x1400376fa  push    r15
0x1400376fc  lea     rbp, [rsp-2Fh]
0x140037701  sub     rsp, 0D0h
0x140037708  mov     rax, cs:__security_cookie
0x14003770f  xor     rax, rsp
0x140037712  mov     [rbp+4Fh+var_30], rax
0x140037716  mov     r15d, edx
0x140037719  mov     edi, r8d
0x14003771c  xor     edx, edx; Val
0x14003771e  mov     rbx, rcx
0x140037721  lea     rcx, [rbp+4Fh+var_B0]; void *
0x140037725  lea     r8d, [rdx+70h]; Size
0x140037729  call    memset
0x14003772e  lea     rax, WPP_RECORDER_INITIALIZED
0x140037735  xorps   xmm0, xmm0
0x140037738  lea     rcx, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003773f  movups  [rbp+4Fh+var_40], xmm0
0x140037743  test    r15d, r15d
0x140037746  jz      short loc_140037791
0x140037748  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003774f  jz      short loc_140037780
0x140037751  mov     eax, [rbx+10h]
0x140037754  mov     r9d, 0C2h
0x14003775a  mov     [rsp+0F0h+var_C0], r15d
0x14003775f  mov     r8d, 3
0x140037765  mov     [rsp+0F0h+var_C8], eax
0x140037769  mov     dl, 2
0x14003776b  mov     [rsp+0F0h+var_D0], rcx
0x140037770  mov     rcx, cs:WPP_GLOBAL_Control
0x140037777  mov     rcx, [rcx+40h]
0x14003777b  call    WPP_RECORDER_SF_DD
0x140037780  mov     esi, 0C0040003h
0x140037785  lea     r14, [rbx+1B0h]
0x14003778c  jmp     loc_140037844
0x140037791  mov     ecx, edi
0x140037793  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140037798  lea     r14, [rbx+1B0h]
0x14003779f  mov     esi, eax
0x1400377a1  cmp     qword ptr [r14], 0
0x1400377a5  jz      loc_140037844
0x1400377ab  cmp     qword ptr [rbx+1A8h], 0
0x1400377b3  jnz     short loc_1400377C2
0x1400377b5  cmp     byte ptr [rbx+240h], 0
0x1400377bc  jz      loc_140037844
0x1400377c2  cmp     byte ptr [rbx+1C4h], 0
0x1400377c9  jz      short loc_140037844
0x1400377cb  test    eax, eax
0x1400377cd  jnz     short loc_140037844
0x1400377cf  mov     rax, [rbx+30h]
0x1400377d3  mov     rdi, [rax]
0x1400377d6  mov     rcx, rdi; SpinLock
0x1400377d9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400377e0  nop     dword ptr [rax+rax+00h]
0x1400377e5  mov     rcx, [rdi+468h]; P
0x1400377ec  mov     [rdi+8], al
0x1400377ef  test    rcx, rcx
0x1400377f2  jz      short loc_14003780D
0x1400377f4  xor     edx, edx; Tag
0x1400377f6  call    cs:__imp_ExFreePoolWithTag
0x1400377fd  nop     dword ptr [rax+rax+00h]
0x140037802  mov     qword ptr [rdi+468h], 0
0x14003780d  mov     rax, [rbx+2D8h]
0x140037814  mov     rcx, rdi; SpinLock
0x140037817  mov     dl, [rdi+8]; NewIrql
0x14003781a  mov     [rdi+468h], rax
0x140037821  mov     eax, [rbx+2E0h]
0x140037827  mov     [rdi+464h], eax
0x14003782d  call    cs:__imp_KeReleaseSpinLock
0x140037834  nop     dword ptr [rax+rax+00h]
0x140037839  mov     qword ptr [rbx+238h], 0
0x140037844  cmp     qword ptr [rbx+1A8h], 0
0x14003784c  jnz     short loc_14003785B
0x14003784e  cmp     byte ptr [rbx+240h], 0
0x140037855  jz      loc_140037955
0x14003785b  mov     rax, [rbx+30h]
0x14003785f  xorps   xmm0, xmm0
0x140037862  mov     dword ptr [rbp+4Fh+var_B0.Header.Type], 700198h
0x140037869  mov     rcx, [rax]
0x14003786c  mov     rax, [rcx+478h]
0x140037873  mov     rcx, [rax]
0x140037876  mov     rax, [rcx+10h]
0x14003787a  mov     ecx, 10h
0x14003787f  mov     [rbp+4Fh+var_B0.SourceHandle], rax
0x140037883  mov     rax, [rbx+1B8h]
0x14003788a  mov     [rbp+4Fh+var_B0.DestinationHandle], rax
0x14003788e  mov     rax, [r14]
0x140037891  mov     [rbp+4Fh+var_B0.RequestId], rax
0x140037895  lea     rax, [rbp+4Fh+var_40]
0x140037899  mov     [rbp+4Fh+var_B0.StatusBuffer], rax
0x14003789d  mov     [rbp+4Fh+var_B0.PortNumber], 0
0x1400378a4  mov     qword ptr [rbp+4Fh+var_B0.StatusCode], 40041017h
0x1400378ac  movups  xmmword ptr [rbp+4Fh+var_B0.Guid.Data1], xmm0
0x1400378b0  mov     dword ptr [rbp+4Fh+var_40], 100180h
0x1400378b7  mov     qword ptr [rbp+4Fh+var_40+8], 0Bh
0x1400378bf  mov     dword ptr [rbp+4Fh+var_40+4], esi
0x1400378c2  mov     [rbp+4Fh+var_B0.StatusBufferSize], ecx
0x1400378c5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400378cc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400378d3  jz      short loc_140037908
0x1400378d5  mov     eax, [rbx+10h]
0x1400378d8  lea     r8d, [rcx-0Dh]
0x1400378dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400378e3  mov     r9d, 0C3h
0x1400378e9  mov     [rsp+0F0h+var_C0], esi
0x1400378ed  mov     dl, 4
0x1400378ef  mov     [rsp+0F0h+var_C8], eax
0x1400378f3  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400378fa  mov     [rsp+0F0h+var_D0], rax
0x1400378ff  mov     rcx, [rcx+40h]
0x140037903  call    WPP_RECORDER_SF_DD
0x140037908  mov     rdx, [rbx+68h]
0x14003790c  test    rdx, rdx
0x14003790f  jz      short loc_140037938
0x140037911  mov     rax, cs:WdfFunctions_01031
0x140037918  mov     r8, cs:off_14005DF38
0x14003791f  mov     rcx, cs:WdfDriverGlobals
0x140037926  mov     rax, [rax+650h]
0x14003792d  call    _guard_dispatch_icall
0x140037932  add     rax, 18h
0x140037936  jmp     short loc_140037949
0x140037938  mov     rax, [rbx+30h]
0x14003793c  mov     rcx, [rax]
0x14003793f  mov     rax, [rcx+478h]
0x140037946  mov     rax, [rax]
0x140037949  lea     rdx, [rbp+4Fh+var_B0]; struct _NDIS_STATUS_INDICATION *
0x14003794d  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x140037950  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x140037955  mov     eax, r15d
0x140037958  mov     rcx, [rbp+4Fh+var_30]
0x14003795c  xor     rcx, rsp; StackCookie
0x14003795f  call    __security_check_cookie
0x140037964  mov     rbx, [rsp+0F0h+arg_8]
0x14003796c  add     rsp, 0D0h
0x140037973  pop     r15
0x140037975  pop     r14
0x140037977  pop     rdi
0x140037978  pop     rsi
0x140037979  pop     rbp
0x14003797a  retn
```
