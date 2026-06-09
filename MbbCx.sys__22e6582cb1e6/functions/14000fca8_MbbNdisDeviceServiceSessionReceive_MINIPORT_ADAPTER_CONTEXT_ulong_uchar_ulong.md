# MbbNdisDeviceServiceSessionReceive(_MINIPORT_ADAPTER_CONTEXT *,ulong,uchar *,ulong)

- ea: `0x14000fca8`
- end: `0x14000fe85`
- name: `?MbbNdisDeviceServiceSessionReceive@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@KPEAEK@Z`
- size: `477`
- prototype: `__int64 __fastcall(struct _MINIPORT_ADAPTER_CONTEXT *, int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000eac0`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x14000fca8`
- `0x14003f994`
- `0x140047e50`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000fd49`
- `ntoskrnl!ExAllocatePool2` at `0x14000fd49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fe4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fe4f`

## pseudocode

```c
__int64 __fastcall MbbNdisDeviceServiceSessionReceive(
        struct _MINIPORT_ADAPTER_CONTEXT *a1,
        int a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  size_t v5; // rsi
  int v8; // edx
  _DWORD *Pool2; // rax
  int v11; // edx
  void *v12; // rbx
  int v13; // edx
  __int64 v14; // rax
  struct _NDIS_STATUS_INDICATION v15; // [rsp+30h] [rbp-59h] BYREF

  v5 = a4;
  memset(&v15, 0, sizeof(v15));
  if ( (int)v5 + 12 >= (unsigned int)v5 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(64, (unsigned int)(v5 + 12), 1683505741);
    v12 = Pool2;
    if ( Pool2 )
    {
      *Pool2 = 786816;
      Pool2[2] = v5;
      Pool2[1] = a2;
      memmove(Pool2 + 3, a3, v5);
      v14 = *((_QWORD *)a1 + 143);
      v15.Header = (NDIS_OBJECT_HEADER)7340440;
      v15.SourceHandle = *(NDIS_HANDLE *)(*(_QWORD *)v14 + 16LL);
      v15.PortNumber = 0;
      *(_QWORD *)&v15.StatusCode = 1074008100;
      *(_OWORD *)&v15.DestinationHandle = 0;
      v15.Guid = 0;
      v15.StatusBuffer = v12;
      v15.StatusBufferSize = v5 + 12;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          7,
          156,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
      }
      MbbUtilNdisMiniportIndicateStatusEx(**((NDIS_HANDLE ***)a1 + 143), &v15);
      ExFreePoolWithTag(v12, 0);
      return 0;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          7,
          155,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          v5 + 12);
      }
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        7,
        154,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        v5);
    }
    return 3221291028LL;
  }
}

```

## disassembly

```asm
0x14000fca8  mov     [rsp-8+arg_8], rbx
0x14000fcad  push    rbp
0x14000fcae  push    rsi
0x14000fcaf  push    rdi
0x14000fcb0  push    r12
0x14000fcb2  push    r13
0x14000fcb4  push    r14
0x14000fcb6  push    r15
0x14000fcb8  lea     rbp, [rsp-27h]
0x14000fcbd  sub     rsp, 0B0h
0x14000fcc4  mov     rax, cs:__security_cookie
0x14000fccb  xor     rax, rsp
0x14000fcce  mov     [rbp+57h+var_40], rax
0x14000fcd2  mov     r15d, edx
0x14000fcd5  mov     esi, r9d
0x14000fcd8  xor     edx, edx; Val
0x14000fcda  mov     r12, r8
0x14000fcdd  mov     r14, rcx
0x14000fce0  lea     rcx, [rbp+57h+var_B0]; void *
0x14000fce4  lea     r8d, [rdx+70h]; Size
0x14000fce8  call    memset
0x14000fced  lea     edi, [rsi+0Ch]
0x14000fcf0  cmp     edi, esi
0x14000fcf2  jnb     short loc_14000FD3C
0x14000fcf4  lea     rax, WPP_RECORDER_INITIALIZED
0x14000fcfb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000fd02  jz      short loc_14000FD32
0x14000fd04  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd0b  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14000fd12  mov     r9d, 9Ah
0x14000fd18  mov     [rsp+0E0h+var_B8], esi
0x14000fd1c  mov     r8d, 7
0x14000fd22  mov     [rsp+0E0h+var_C0], rax
0x14000fd27  mov     dl, 2
0x14000fd29  mov     rcx, [rcx+40h]
0x14000fd2d  call    WPP_RECORDER_SF_d
0x14000fd32  mov     eax, 0C0010014h
0x14000fd37  jmp     loc_14000FE5D
0x14000fd3c  mov     edx, edi
0x14000fd3e  mov     ecx, 40h ; '@'
0x14000fd43  mov     r8d, 6458424Dh
0x14000fd49  call    cs:__imp_ExAllocatePool2
0x14000fd50  nop     dword ptr [rax+rax+00h]
0x14000fd55  mov     rbx, rax
0x14000fd58  test    rax, rax
0x14000fd5b  jnz     short loc_14000FDA3
0x14000fd5d  lea     rax, WPP_RECORDER_INITIALIZED
0x14000fd64  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000fd6b  jz      short loc_14000FD99
0x14000fd6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd74  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14000fd7b  mov     r9d, 9Bh
0x14000fd81  mov     [rsp+0E0h+var_B8], edi
0x14000fd85  lea     r8d, [rbx+7]
0x14000fd89  mov     [rsp+0E0h+var_C0], rax
0x14000fd8e  mov     dl, 2
0x14000fd90  mov     rcx, [rcx+40h]
0x14000fd94  call    WPP_RECORDER_SF_d
0x14000fd99  mov     eax, 0C000009Ah
0x14000fd9e  jmp     loc_14000FE5D
0x14000fda3  mov     r8, rsi; Size
0x14000fda6  mov     dword ptr [rax], 0C0180h
0x14000fdac  lea     rcx, [rax+0Ch]; void *
0x14000fdb0  mov     [rax+8], esi
0x14000fdb3  mov     rdx, r12; Src
0x14000fdb6  mov     [rax+4], r15d
0x14000fdba  call    memmove
0x14000fdbf  mov     rax, [r14+478h]
0x14000fdc6  xorps   xmm0, xmm0
0x14000fdc9  mov     dword ptr [rbp+57h+var_B0.Header.Type], 700198h
0x14000fdd0  xorps   xmm1, xmm1
0x14000fdd3  mov     rcx, [rax]
0x14000fdd6  mov     rax, [rcx+10h]
0x14000fdda  mov     [rbp+57h+var_B0.SourceHandle], rax
0x14000fdde  mov     [rbp+57h+var_B0.PortNumber], 0
0x14000fde5  mov     qword ptr [rbp+57h+var_B0.StatusCode], 40041024h
0x14000fded  movdqa  xmmword ptr [rbp+57h+var_B0.DestinationHandle], xmm0
0x14000fdf2  movups  xmmword ptr [rbp+57h+var_B0.Guid.Data1], xmm1
0x14000fdf6  mov     [rbp+57h+var_B0.StatusBuffer], rbx
0x14000fdfa  mov     [rbp+57h+var_B0.StatusBufferSize], edi
0x14000fdfd  lea     rax, WPP_RECORDER_INITIALIZED
0x14000fe04  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000fe0b  jz      short loc_14000FE37
0x14000fe0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe14  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14000fe1b  mov     r9d, 9Ch
0x14000fe21  mov     [rsp+0E0h+var_C0], rax
0x14000fe26  mov     r8d, 7
0x14000fe2c  mov     dl, 4
0x14000fe2e  mov     rcx, [rcx+40h]
0x14000fe32  call    WPP_RECORDER_SF_
0x14000fe37  mov     rcx, [r14+478h]
0x14000fe3e  lea     rdx, [rbp+57h+var_B0]; struct _NDIS_STATUS_INDICATION *
0x14000fe42  mov     rcx, [rcx]; struct _MINIPORT_INTERFACE_CONTEXT *
0x14000fe45  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14000fe4a  xor     edx, edx; Tag
0x14000fe4c  mov     rcx, rbx; P
0x14000fe4f  call    cs:__imp_ExFreePoolWithTag
0x14000fe56  nop     dword ptr [rax+rax+00h]
0x14000fe5b  xor     eax, eax
0x14000fe5d  mov     rcx, [rbp+57h+var_40]
0x14000fe61  xor     rcx, rsp; StackCookie
0x14000fe64  call    __security_check_cookie
0x14000fe69  mov     rbx, [rsp+0E0h+arg_8]
0x14000fe71  add     rsp, 0B0h
0x14000fe78  pop     r15
0x14000fe7a  pop     r14
0x14000fe7c  pop     r13
0x14000fe7e  pop     r12
0x14000fe80  pop     rdi
0x14000fe81  pop     rsi
0x14000fe82  pop     rbp
0x14000fe83  retn
```
