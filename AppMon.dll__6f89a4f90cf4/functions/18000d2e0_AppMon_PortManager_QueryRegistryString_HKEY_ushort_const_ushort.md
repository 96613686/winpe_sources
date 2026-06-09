# AppMon::PortManager::QueryRegistryString(HKEY__ *,ushort const *,ushort * *)

- ea: `0x18000d2e0`
- end: `0x18000d38b`
- name: `?QueryRegistryString@PortManager@AppMon@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `171`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bafc`

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000a408`
- `0x18000d2e0`

## pseudocode

```c
__int64 __fastcall AppMon::PortManager::QueryRegistryString(HKEY a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  _QWORD v6[5]; // [rsp+20h] [rbp-28h] BYREF
  HKEY v7; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *v8; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 **v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = a3;
  v8 = a2;
  v7 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids);
  v6[0] = &v7;
  v6[1] = &v8;
  v6[2] = &v9;
  v3 = AppMon::CaptureAndConvertExceptionToHR__lambda_d125e79bece40f49aceb176120309ade___(v6);
  v4 = v3;
  if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids, (unsigned int)v3);
  return v4;
}

```

## disassembly

```asm
0x18000d2e0  mov     rax, rsp
0x18000d2e3  mov     [rax+20h], rbx
0x18000d2e7  mov     [rax+18h], r8
0x18000d2eb  mov     [rax+10h], rdx
0x18000d2ef  mov     [rax+8], rcx
0x18000d2f3  push    rdi
0x18000d2f4  sub     rsp, 40h
0x18000d2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2ff  lea     rdi, WPP_GLOBAL_Control
0x18000d306  cmp     rcx, rdi
0x18000d309  jz      short loc_18000D326
0x18000d30b  test    byte ptr [rcx+1Ch], 1
0x18000d30f  jz      short loc_18000D326
0x18000d311  mov     rcx, [rcx+10h]
0x18000d315  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000d31c  mov     edx, 16h
0x18000d321  call    WPP_SF_
0x18000d326  lea     rax, [rsp+48h+arg_0]
0x18000d32b  mov     [rsp+48h+var_28], rax
0x18000d330  lea     rcx, [rsp+48h+var_28]
0x18000d335  lea     rax, [rsp+48h+arg_8]
0x18000d33a  mov     [rsp+48h+var_20], rax
0x18000d33f  lea     rax, [rsp+48h+arg_10]
0x18000d344  mov     [rsp+48h+var_18], rax
0x18000d349  call    AppMon__CaptureAndConvertExceptionToHR__lambda_d125e79bece40f49aceb176120309ade___
0x18000d34e  mov     ebx, eax
0x18000d350  test    eax, eax
0x18000d352  jns     short loc_18000D37E
0x18000d354  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d35b  cmp     rcx, rdi
0x18000d35e  jz      short loc_18000D37E
0x18000d360  test    byte ptr [rcx+1Ch], 8
0x18000d364  jz      short loc_18000D37E
0x18000d366  mov     rcx, [rcx+10h]
0x18000d36a  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000d371  mov     edx, 17h
0x18000d376  mov     r9d, eax
0x18000d379  call    WPP_SF_d
0x18000d37e  mov     eax, ebx
0x18000d380  mov     rbx, [rsp+48h+arg_18]
0x18000d385  add     rsp, 40h
0x18000d389  pop     rdi
0x18000d38a  retn
```
