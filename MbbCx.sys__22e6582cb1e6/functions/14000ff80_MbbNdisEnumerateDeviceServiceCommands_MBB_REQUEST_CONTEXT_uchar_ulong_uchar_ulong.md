# MbbNdisEnumerateDeviceServiceCommands(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x14000ff80`
- end: `0x1400101c4`
- name: `?MbbNdisEnumerateDeviceServiceCommands@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `580`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140005644`
- `0x14000ff80`
- `0x14001eca4`
- `0x14003f994`
- `0x140047e50`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140010039`
- `ntoskrnl!ExAllocatePool2` at `0x140010039`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001018a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001018a`

## pseudocode

```c
__int64 __fastcall MbbNdisEnumerateDeviceServiceCommands(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  struct _MBB_DS *DeviceService; // rax
  int v7; // edx
  struct _MBB_DS *v8; // rsi
  unsigned int v10; // r14d
  __int64 Pool2; // rax
  int v12; // edx
  _DWORD *v13; // rbx
  __int128 v14; // xmm0
  __int64 v15; // r8
  const void *v16; // rdx
  int v17; // edx
  __int64 v18; // rax
  struct _NDIS_STATUS_INDICATION v19; // [rsp+40h] [rbp-51h] BYREF

  memset(&v19, 0, sizeof(v19));
  DeviceService = MbbUtilFindDeviceService(**((struct _MINIPORT_ADAPTER_CONTEXT ***)a1 + 6), (struct _GUID *)(a4 + 4));
  v8 = DeviceService;
  if ( DeviceService )
  {
    v10 = 4 * *((_DWORD *)DeviceService + 6) + 32;
    Pool2 = ExAllocatePool2(64, v10, 1683505741);
    v13 = (_DWORD *)Pool2;
    if ( Pool2 )
    {
      v14 = *(_OWORD *)(a4 + 4);
      v15 = *((unsigned int *)v8 + 6);
      v16 = (const void *)*((_QWORD *)v8 + 4);
      *(_DWORD *)(Pool2 + 28) = v15;
      *(_OWORD *)(Pool2 + 8) = v14;
      *(_QWORD *)Pool2 = 2097536;
      *(_DWORD *)(Pool2 + 24) = 12;
      memmove((void *)(Pool2 + 32), v16, 4 * v15);
      v18 = *((_QWORD *)a1 + 6);
      v19.Header = (NDIS_OBJECT_HEADER)7340440;
      v19.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v18 + 1144LL) + 16LL);
      v19.DestinationHandle = (NDIS_HANDLE)*((_QWORD *)a1 + 55);
      v19.RequestId = (PVOID)*((_QWORD *)a1 + 54);
      v19.PortNumber = 0;
      *(_QWORD *)&v19.StatusCode = 1074008097;
      v19.Guid = 0;
      v19.StatusBuffer = v13;
      v19.StatusBufferSize = v10;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 4;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          3,
          58,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          *((_DWORD *)a1 + 4),
          v13[7]);
      }
      MbbUtilNdisMiniportIndicateStatusEx(**(NDIS_HANDLE ***)(**((_QWORD **)a1 + 6) + 1144LL), &v19);
      ExFreePoolWithTag(v13, 0);
      return 65537;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_Ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          3,
          57,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          *((_DWORD *)a1 + 4),
          v10,
          *((_DWORD *)v8 + 6));
      }
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        3,
        56,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        *((_DWORD *)a1 + 4));
    }
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x14000ff80  mov     [rsp-8+arg_8], rbx
0x14000ff85  mov     [rsp-8+arg_10], rsi
0x14000ff8a  push    rbp
0x14000ff8b  push    rdi
0x14000ff8c  push    r13
0x14000ff8e  push    r14
0x14000ff90  push    r15
0x14000ff92  lea     rbp, [rsp-2Fh]
0x14000ff97  sub     rsp, 0C0h
0x14000ff9e  mov     rax, cs:__security_cookie
0x14000ffa5  xor     rax, rsp
0x14000ffa8  mov     [rbp+4Fh+var_30], rax
0x14000ffac  xor     edx, edx; Val
0x14000ffae  mov     rdi, rcx
0x14000ffb1  lea     rcx, [rbp+4Fh+var_A0]; void *
0x14000ffb5  mov     r15, r9
0x14000ffb8  lea     r8d, [rdx+70h]; Size
0x14000ffbc  call    memset
0x14000ffc1  mov     rcx, [rdi+30h]
0x14000ffc5  lea     rdx, [r15+4]; struct _GUID *
0x14000ffc9  mov     rcx, [rcx]; struct _MINIPORT_ADAPTER_CONTEXT *
0x14000ffcc  call    ?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z; MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)
0x14000ffd1  mov     rsi, rax
0x14000ffd4  test    rax, rax
0x14000ffd7  jnz     short loc_140010020
0x14000ffd9  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ffe0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ffe7  jz      short loc_140010016
0x14000ffe9  mov     eax, [rdi+10h]
0x14000ffec  lea     r9d, [rsi+38h]
0x14000fff0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fff7  lea     r8d, [rsi+3]
0x14000fffb  mov     [rsp+0E0h+var_B8], eax
0x14000ffff  mov     dl, 2
0x140010001  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140010008  mov     [rsp+0E0h+var_C0], rax
0x14001000d  mov     rcx, [rcx+40h]
0x140010011  call    WPP_RECORDER_SF_d
0x140010016  mov     eax, 0C00000BBh
0x14001001b  jmp     loc_14001019B
0x140010020  mov     eax, [rax+18h]
0x140010023  mov     ecx, 40h ; '@'
0x140010028  mov     r8d, 6458424Dh
0x14001002e  lea     r14d, ds:20h[rax*4]
0x140010036  mov     edx, r14d
0x140010039  call    cs:__imp_ExAllocatePool2
0x140010040  nop     dword ptr [rax+rax+00h]
0x140010045  mov     rbx, rax
0x140010048  test    rax, rax
0x14001004b  jnz     short loc_1400100A0
0x14001004d  lea     rax, WPP_RECORDER_INITIALIZED
0x140010054  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001005b  jz      short loc_140010096
0x14001005d  mov     eax, [rsi+18h]
0x140010060  lea     r9d, [rbx+39h]
0x140010064  mov     rcx, cs:WPP_GLOBAL_Control
0x14001006b  lea     r8d, [rbx+3]
0x14001006f  mov     [rsp+0E0h+var_A8], eax
0x140010073  mov     dl, 2
0x140010075  mov     eax, [rdi+10h]
0x140010078  mov     [rsp+0E0h+var_B0], r14d
0x14001007d  mov     rcx, [rcx+40h]
0x140010081  mov     [rsp+0E0h+var_B8], eax
0x140010085  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001008c  mov     [rsp+0E0h+var_C0], rax
0x140010091  call    WPP_RECORDER_SF_Ddd
0x140010096  mov     eax, 0C000009Ah
0x14001009b  jmp     loc_14001019B
0x1400100a0  movups  xmm0, xmmword ptr [r15+4]
0x1400100a5  mov     r8d, [rsi+18h]
0x1400100a9  lea     rcx, [rax+20h]; void *
0x1400100ad  mov     rdx, [rsi+20h]; Src
0x1400100b1  mov     [rax+1Ch], r8d
0x1400100b5  shl     r8, 2; Size
0x1400100b9  movdqu  xmmword ptr [rax+8], xmm0
0x1400100be  mov     qword ptr [rax], 200180h
0x1400100c5  mov     dword ptr [rax+18h], 0Ch
0x1400100cc  call    memmove
0x1400100d1  mov     rax, [rdi+30h]
0x1400100d5  xorps   xmm0, xmm0
0x1400100d8  mov     dword ptr [rbp+4Fh+var_A0.Header.Type], 700198h
0x1400100df  mov     rcx, [rax]
0x1400100e2  mov     rax, [rcx+478h]
0x1400100e9  mov     rcx, [rax]
0x1400100ec  mov     rax, [rcx+10h]
0x1400100f0  mov     [rbp+4Fh+var_A0.SourceHandle], rax
0x1400100f4  mov     rax, [rdi+1B8h]
0x1400100fb  mov     [rbp+4Fh+var_A0.DestinationHandle], rax
0x1400100ff  mov     rax, [rdi+1B0h]
0x140010106  mov     [rbp+4Fh+var_A0.RequestId], rax
0x14001010a  mov     [rbp+4Fh+var_A0.PortNumber], 0
0x140010111  mov     qword ptr [rbp+4Fh+var_A0.StatusCode], 40041021h
0x140010119  movups  xmmword ptr [rbp+4Fh+var_A0.Guid.Data1], xmm0
0x14001011d  mov     [rbp+4Fh+var_A0.StatusBuffer], rbx
0x140010121  mov     [rbp+4Fh+var_A0.StatusBufferSize], r14d
0x140010125  lea     rax, WPP_RECORDER_INITIALIZED
0x14001012c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010133  jz      short loc_14001016B
0x140010135  mov     eax, [rbx+1Ch]
0x140010138  mov     r9d, 3Ah ; ':'
0x14001013e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010145  mov     dl, 4
0x140010147  mov     [rsp+0E0h+var_B0], eax
0x14001014b  mov     eax, [rdi+10h]
0x14001014e  mov     [rsp+0E0h+var_B8], eax
0x140010152  lea     r8d, [r9-37h]
0x140010156  mov     rcx, [rcx+40h]
0x14001015a  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140010161  mov     [rsp+0E0h+var_C0], rax
0x140010166  call    WPP_RECORDER_SF_DD
0x14001016b  mov     rax, [rdi+30h]
0x14001016f  lea     rdx, [rbp+4Fh+var_A0]; struct _NDIS_STATUS_INDICATION *
0x140010173  mov     rcx, [rax]
0x140010176  mov     rcx, [rcx+478h]
0x14001017d  mov     rcx, [rcx]; struct _MINIPORT_INTERFACE_CONTEXT *
0x140010180  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x140010185  xor     edx, edx; Tag
0x140010187  mov     rcx, rbx; P
0x14001018a  call    cs:__imp_ExFreePoolWithTag
0x140010191  nop     dword ptr [rax+rax+00h]
0x140010196  mov     eax, 10001h
0x14001019b  mov     rcx, [rbp+4Fh+var_30]
0x14001019f  xor     rcx, rsp; StackCookie
0x1400101a2  call    __security_check_cookie
0x1400101a7  lea     r11, [rsp+0E0h+var_20]
0x1400101af  mov     rbx, [r11+38h]
0x1400101b3  mov     rsi, [r11+40h]
0x1400101b7  mov     rsp, r11
0x1400101ba  pop     r15
0x1400101bc  pop     r14
0x1400101be  pop     r13
0x1400101c0  pop     rdi
0x1400101c1  pop     rbp
0x1400101c2  retn
```
