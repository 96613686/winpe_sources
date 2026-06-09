# AppMon::PortManager::QueryUpdatePerUserPrinter(ulong,uchar *)

- ea: `0x18000d394`
- end: `0x18000d430`
- name: `?QueryUpdatePerUserPrinter@PortManager@AppMon@@SAJKPEAE@Z`
- size: `156`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800065a8`

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000a3a0`
- `0x18000d394`

## pseudocode

```c
__int64 __fastcall AppMon::PortManager::QueryUpdatePerUserPrinter(int a1, unsigned __int8 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int8 *v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = a2;
  v6 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids);
  v5[0] = &v7;
  v5[1] = &v6;
  v2 = AppMon::CaptureAndConvertExceptionToHR__lambda_b732d421b79af9831b8171cb846b06bc___(v5);
  v3 = v2;
  if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids, (unsigned int)v2);
  return v3;
}

```

## disassembly

```asm
0x18000d394  mov     [rsp+arg_10], rbx
0x18000d399  mov     [rsp+arg_8], rdx
0x18000d39e  mov     [rsp+arg_0], ecx
0x18000d3a2  push    rdi
0x18000d3a3  sub     rsp, 30h
0x18000d3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3ae  lea     rdi, WPP_GLOBAL_Control
0x18000d3b5  cmp     rcx, rdi
0x18000d3b8  jz      short loc_18000D3D5
0x18000d3ba  test    byte ptr [rcx+1Ch], 1
0x18000d3be  jz      short loc_18000D3D5
0x18000d3c0  mov     rcx, [rcx+10h]
0x18000d3c4  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000d3cb  mov     edx, 0Ch
0x18000d3d0  call    WPP_SF_
0x18000d3d5  lea     rax, [rsp+38h+arg_8]
0x18000d3da  mov     [rsp+38h+var_18], rax
0x18000d3df  lea     rcx, [rsp+38h+var_18]
0x18000d3e4  lea     rax, [rsp+38h+arg_0]
0x18000d3e9  mov     [rsp+38h+var_10], rax
0x18000d3ee  call    AppMon__CaptureAndConvertExceptionToHR__lambda_b732d421b79af9831b8171cb846b06bc___
0x18000d3f3  mov     ebx, eax
0x18000d3f5  test    eax, eax
0x18000d3f7  jns     short loc_18000D423
0x18000d3f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d400  cmp     rcx, rdi
0x18000d403  jz      short loc_18000D423
0x18000d405  test    byte ptr [rcx+1Ch], 8
0x18000d409  jz      short loc_18000D423
0x18000d40b  mov     rcx, [rcx+10h]
0x18000d40f  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000d416  mov     edx, 0Dh
0x18000d41b  mov     r9d, eax
0x18000d41e  call    WPP_SF_d
0x18000d423  mov     eax, ebx
0x18000d425  mov     rbx, [rsp+38h+arg_10]
0x18000d42a  add     rsp, 30h
0x18000d42e  pop     rdi
0x18000d42f  retn
```
