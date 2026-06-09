# CNetworkItemFactory::s_FDBackgroundCOMParkingThread(void *)

- ea: `0x1800055e0`
- end: `0x180005684`
- name: `?s_FDBackgroundCOMParkingThread@CNetworkItemFactory@@CAKPEAX@Z`
- size: `164`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800055e0`
- `0x18000589c`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180005635`
- `KERNEL32!WaitForSingleObject` at `0x180005635`
- `KERNEL32!CloseHandle` at `0x180005671`
- `KERNEL32!CloseHandle` at `0x180005671`
- `ole32!CoUninitialize` at `0x180005668`
- `ole32!CoUninitialize` at `0x180005668`
- `ole32!CoInitializeEx` at `0x1800055f1`
- `ole32!CoInitializeEx` at `0x1800055f1`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::s_FDBackgroundCOMParkingThread(PVOID Parameter)
{
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_182dd27e7f09338048566614cf2976f3_Traceguids);
    }
    WaitForSingleObject(Parameter, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_182dd27e7f09338048566614cf2976f3_Traceguids);
    }
    CoUninitialize();
  }
  CloseHandle(Parameter);
  return 0;
}

```

## disassembly

```asm
0x1800055e0  mov     [rsp+arg_0], rbx
0x1800055e5  push    rdi
0x1800055e6  sub     rsp, 20h
0x1800055ea  mov     rbx, rcx
0x1800055ed  xor     edx, edx; dwCoInit
0x1800055ef  xor     ecx, ecx; pvReserved
0x1800055f1  call    cs:__imp_CoInitializeEx
0x1800055f7  test    eax, eax
0x1800055f9  js      short loc_18000566E
0x1800055fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005602  lea     rdi, WPP_GLOBAL_Control
0x180005609  cmp     rcx, rdi
0x18000560c  jz      short loc_18000562F
0x18000560e  cmp     byte ptr [rcx+19h], 4
0x180005612  jb      short loc_18000562F
0x180005614  test    byte ptr [rcx+1Ch], 2
0x180005618  jz      short loc_18000562F
0x18000561a  mov     rcx, [rcx+10h]
0x18000561e  lea     r8, WPP_182dd27e7f09338048566614cf2976f3_Traceguids
0x180005625  mov     edx, 15h
0x18000562a  call    WPP_SF_
0x18000562f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005632  mov     rcx, rbx; hHandle
0x180005635  call    cs:__imp_WaitForSingleObject
0x18000563b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005642  cmp     rcx, rdi
0x180005645  jz      short loc_180005668
0x180005647  cmp     byte ptr [rcx+19h], 4
0x18000564b  jb      short loc_180005668
0x18000564d  test    byte ptr [rcx+1Ch], 2
0x180005651  jz      short loc_180005668
0x180005653  mov     rcx, [rcx+10h]
0x180005657  lea     r8, WPP_182dd27e7f09338048566614cf2976f3_Traceguids
0x18000565e  mov     edx, 16h
0x180005663  call    WPP_SF_
0x180005668  call    cs:__imp_CoUninitialize
0x18000566e  mov     rcx, rbx; hObject
0x180005671  call    cs:__imp_CloseHandle
0x180005677  mov     rbx, [rsp+28h+arg_0]
0x18000567c  xor     eax, eax
0x18000567e  add     rsp, 20h
0x180005682  pop     rdi
0x180005683  retn
```
