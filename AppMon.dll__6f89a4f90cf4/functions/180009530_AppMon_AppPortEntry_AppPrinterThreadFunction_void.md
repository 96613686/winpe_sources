# AppMon::AppPortEntry::AppPrinterThreadFunction(void *)

- ea: `0x180009530`
- end: `0x1800095bf`
- name: `?AppPrinterThreadFunction@AppPortEntry@AppMon@@CAKPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005b34`
- `0x180007a78`
- `0x180007c6c`
- `0x180009530`

## pseudocode

```c
__int64 __fastcall AppMon::AppPortEntry::AppPrinterThreadFunction(LPVOID lpThreadParameter)
{
  int v1; // eax
  unsigned __int16 v2; // bx
  LPVOID v4; // [rsp+30h] [rbp+8h] BYREF
  LPVOID *v5; // [rsp+38h] [rbp+10h] BYREF

  v4 = lpThreadParameter;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_50fef123aed832f4ff66a3d97e48546f_Traceguids);
  v5 = &v4;
  v1 = AppMon::CaptureAndConvertExceptionToHR__lambda_b3125c57f832666c07a653ed576da69f___(&v5);
  v2 = v1;
  if ( v1 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_50fef123aed832f4ff66a3d97e48546f_Traceguids, (unsigned int)v1);
  return v2;
}

```

## disassembly

```asm
0x180009530  mov     [rsp+arg_10], rbx
0x180009535  mov     [rsp+arg_0], rcx
0x18000953a  push    rdi
0x18000953b  sub     rsp, 20h
0x18000953f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009546  lea     rdi, WPP_GLOBAL_Control
0x18000954d  cmp     rcx, rdi
0x180009550  jz      short loc_18000956D
0x180009552  test    byte ptr [rcx+1Ch], 1
0x180009556  jz      short loc_18000956D
0x180009558  mov     rcx, [rcx+10h]
0x18000955c  lea     r8, WPP_50fef123aed832f4ff66a3d97e48546f_Traceguids
0x180009563  mov     edx, 13h
0x180009568  call    WPP_SF_
0x18000956d  lea     rax, [rsp+28h+arg_0]
0x180009572  lea     rcx, [rsp+28h+arg_8]
0x180009577  mov     [rsp+28h+arg_8], rax
0x18000957c  call    AppMon__CaptureAndConvertExceptionToHR__lambda_b3125c57f832666c07a653ed576da69f___
0x180009581  mov     ebx, eax
0x180009583  test    eax, eax
0x180009585  jns     short loc_1800095B1
0x180009587  mov     rcx, cs:WPP_GLOBAL_Control
0x18000958e  cmp     rcx, rdi
0x180009591  jz      short loc_1800095B1
0x180009593  test    byte ptr [rcx+1Ch], 8
0x180009597  jz      short loc_1800095B1
0x180009599  mov     rcx, [rcx+10h]
0x18000959d  lea     r8, WPP_50fef123aed832f4ff66a3d97e48546f_Traceguids
0x1800095a4  mov     edx, 14h
0x1800095a9  mov     r9d, eax
0x1800095ac  call    WPP_SF_d
0x1800095b1  movzx   eax, bx
0x1800095b4  mov     rbx, [rsp+28h+arg_10]
0x1800095b9  add     rsp, 20h
0x1800095bd  pop     rdi
0x1800095be  retn
```
