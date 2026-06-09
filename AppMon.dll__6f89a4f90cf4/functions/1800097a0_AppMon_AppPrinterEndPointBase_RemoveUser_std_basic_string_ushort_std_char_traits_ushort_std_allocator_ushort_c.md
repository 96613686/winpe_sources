# AppMon::AppPrinterEndPointBase::RemoveUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800097a0`
- end: `0x1800097fd`
- name: `?RemoveUser@AppPrinterEndPointBase@AppMon@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005b34`
- `0x180007be0`
- `0x1800097a0`

## pseudocode

```c
__int64 __fastcall AppMon::AppPrinterEndPointBase::RemoveUser(__int64 a1, __int64 a2)
{
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_50fef123aed832f4ff66a3d97e48546f_Traceguids);
  v5[0] = a1;
  v5[1] = a2;
  return AppMon::CaptureAndConvertExceptionToHR__lambda_9127c3a32082dec1804f2631bbb1f063___(v5);
}

```

## disassembly

```asm
0x1800097a0  mov     [rsp+arg_0], rbx
0x1800097a5  push    rdi
0x1800097a6  sub     rsp, 30h
0x1800097aa  mov     rbx, rdx
0x1800097ad  mov     rdi, rcx
0x1800097b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097b7  lea     rax, WPP_GLOBAL_Control
0x1800097be  cmp     rcx, rax
0x1800097c1  jz      short loc_1800097DE
0x1800097c3  test    byte ptr [rcx+1Ch], 1
0x1800097c7  jz      short loc_1800097DE
0x1800097c9  mov     rcx, [rcx+10h]
0x1800097cd  lea     r8, WPP_50fef123aed832f4ff66a3d97e48546f_Traceguids
0x1800097d4  mov     edx, 0Ch
0x1800097d9  call    WPP_SF_
0x1800097de  lea     rcx, [rsp+38h+var_18]
0x1800097e3  mov     [rsp+38h+var_18], rdi
0x1800097e8  mov     [rsp+38h+var_10], rbx
0x1800097ed  call    AppMon__CaptureAndConvertExceptionToHR__lambda_9127c3a32082dec1804f2631bbb1f063___
0x1800097f2  mov     rbx, [rsp+38h+arg_0]
0x1800097f7  add     rsp, 30h
0x1800097fb  pop     rdi
0x1800097fc  retn
```
