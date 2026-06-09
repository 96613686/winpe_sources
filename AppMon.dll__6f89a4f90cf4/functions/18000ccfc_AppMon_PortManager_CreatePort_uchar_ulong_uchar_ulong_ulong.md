# AppMon::PortManager::CreatePort(uchar *,ulong,uchar *,ulong,ulong *)

- ea: `0x18000ccfc`
- end: `0x18000cd98`
- name: `?CreatePort@PortManager@AppMon@@SAJPEAEK0KPEAK@Z`
- size: `156`
- prototype: `__int64 __fastcall(unsigned __int8 *, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800065a8`

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000a11c`
- `0x18000ccfc`

## pseudocode

```c
__int64 __fastcall AppMon::PortManager::CreatePort(unsigned __int8 *a1, __int64 a2, unsigned __int8 *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int8 *v7; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = a2;
  v7 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids);
  v6[0] = &v7;
  v6[1] = &v8;
  v3 = AppMon::CaptureAndConvertExceptionToHR__lambda_2637e2e6f36ee0e4e7329debb16589bd___(v6, a2, a3);
  v4 = v3;
  if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids, (unsigned int)v3);
  return v4;
}

```

## disassembly

```asm
0x18000ccfc  mov     [rsp+arg_10], rbx
0x18000cd01  mov     [rsp+arg_8], edx
0x18000cd05  mov     [rsp+arg_0], rcx
0x18000cd0a  push    rdi
0x18000cd0b  sub     rsp, 30h
0x18000cd0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd16  lea     rdi, WPP_GLOBAL_Control
0x18000cd1d  cmp     rcx, rdi
0x18000cd20  jz      short loc_18000CD3D
0x18000cd22  test    byte ptr [rcx+1Ch], 1
0x18000cd26  jz      short loc_18000CD3D
0x18000cd28  mov     rcx, [rcx+10h]
0x18000cd2c  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000cd33  mov     edx, 0Ah
0x18000cd38  call    WPP_SF_
0x18000cd3d  lea     rax, [rsp+38h+arg_0]
0x18000cd42  mov     [rsp+38h+var_18], rax
0x18000cd47  lea     rcx, [rsp+38h+var_18]
0x18000cd4c  lea     rax, [rsp+38h+arg_8]
0x18000cd51  mov     [rsp+38h+var_10], rax
0x18000cd56  call    AppMon__CaptureAndConvertExceptionToHR__lambda_2637e2e6f36ee0e4e7329debb16589bd___
0x18000cd5b  mov     ebx, eax
0x18000cd5d  test    eax, eax
0x18000cd5f  jns     short loc_18000CD8B
0x18000cd61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd68  cmp     rcx, rdi
0x18000cd6b  jz      short loc_18000CD8B
0x18000cd6d  test    byte ptr [rcx+1Ch], 8
0x18000cd71  jz      short loc_18000CD8B
0x18000cd73  mov     rcx, [rcx+10h]
0x18000cd77  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000cd7e  mov     edx, 0Bh
0x18000cd83  mov     r9d, eax
0x18000cd86  call    WPP_SF_d
0x18000cd8b  mov     eax, ebx
0x18000cd8d  mov     rbx, [rsp+38h+arg_10]
0x18000cd92  add     rsp, 30h
0x18000cd96  pop     rdi
0x18000cd97  retn
```
