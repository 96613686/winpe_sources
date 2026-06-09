# AppMon::PortManager::DeleteRegAppEndPointEntry(ushort const *)

- ea: `0x18000cec8`
- end: `0x18000cf59`
- name: `?DeleteRegAppEndPointEntry@PortManager@AppMon@@CAJPEBG@Z`
- size: `145`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ca20`

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000a0c0`
- `0x18000b03c`
- `0x18000cec8`

## pseudocode

```c
__int64 __fastcall AppMon::PortManager::DeleteRegAppEndPointEntry(const unsigned __int16 *a1)
{
  __int64 v1; // rax
  int v2; // eax
  unsigned int v3; // ebx
  const unsigned __int16 *v5; // [rsp+30h] [rbp+8h] BYREF
  char v6; // [rsp+38h] [rbp+10h] BYREF

  v5 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids);
  v1 = lambda_948a67701d3f0c2931e33beed91a0c98_::_lambda_948a67701d3f0c2931e33beed91a0c98_(&v6, &v5);
  v2 = AppMon::CaptureAndConvertExceptionToHR__lambda_0aa2d63311eaf491c50ddef0a1197475___(v1);
  v3 = v2;
  if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids, (unsigned int)v2);
  return v3;
}

```

## disassembly

```asm
0x18000cec8  mov     [rsp+arg_10], rbx
0x18000cecd  mov     [rsp+arg_0], rcx
0x18000ced2  push    rdi
0x18000ced3  sub     rsp, 20h
0x18000ced7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cede  lea     rdi, WPP_GLOBAL_Control
0x18000cee5  cmp     rcx, rdi
0x18000cee8  jz      short loc_18000CF05
0x18000ceea  test    byte ptr [rcx+1Ch], 1
0x18000ceee  jz      short loc_18000CF05
0x18000cef0  mov     rcx, [rcx+10h]
0x18000cef4  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000cefb  mov     edx, 20h ; ' '
0x18000cf00  call    WPP_SF_
0x18000cf05  lea     rdx, [rsp+28h+arg_0]
0x18000cf0a  lea     rcx, [rsp+28h+arg_8]
0x18000cf0f  call    _lambda_948a67701d3f0c2931e33beed91a0c98____lambda_948a67701d3f0c2931e33beed91a0c98_
0x18000cf14  mov     rcx, rax
0x18000cf17  call    AppMon__CaptureAndConvertExceptionToHR__lambda_0aa2d63311eaf491c50ddef0a1197475___
0x18000cf1c  mov     ebx, eax
0x18000cf1e  test    eax, eax
0x18000cf20  jns     short loc_18000CF4C
0x18000cf22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf29  cmp     rcx, rdi
0x18000cf2c  jz      short loc_18000CF4C
0x18000cf2e  test    byte ptr [rcx+1Ch], 8
0x18000cf32  jz      short loc_18000CF4C
0x18000cf34  mov     rcx, [rcx+10h]
0x18000cf38  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000cf3f  mov     edx, 21h ; '!'
0x18000cf44  mov     r9d, eax
0x18000cf47  call    WPP_SF_d
0x18000cf4c  mov     eax, ebx
0x18000cf4e  mov     rbx, [rsp+28h+arg_10]
0x18000cf53  add     rsp, 20h
0x18000cf57  pop     rdi
0x18000cf58  retn
```
