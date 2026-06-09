# AppMon::MonitorInterface::AppMonWritePort(void *,uchar *,ulong,ulong *)

- ea: `0x1800072d0`
- end: `0x1800073c7`
- name: `?AppMonWritePort@MonitorInterface@AppMon@@SAHPEAXPEAEKPEAK@Z`
- size: `247`
- prototype: `_BOOL8 __fastcall(void *, unsigned __int8 *, int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005b34`
- `0x180005e78`
- `0x1800072d0`
- `0x18000798c`
- `0x180007a78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007394`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007394`

## pseudocode

```c
_BOOL8 __fastcall AppMon::MonitorInterface::AppMonWritePort(void *a1, unsigned __int8 *a2, int a3, unsigned int *a4)
{
  int v4; // eax
  int v5; // ebx
  BOOL v6; // ebx
  std::_Ref_count_base *v8[2]; // [rsp+20h] [rbp-50h] BYREF
  std::_Ref_count_base *v9[2]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v10[6]; // [rsp+40h] [rbp-30h] BYREF
  void *v11; // [rsp+90h] [rbp+20h] BYREF
  unsigned __int8 *v12; // [rsp+98h] [rbp+28h] BYREF
  int v13; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int *v14; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a4;
  v13 = a3;
  v12 = a2;
  v11 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_97cdaf78371d36d9099fba1de28de0ee_Traceguids);
  *(_OWORD *)v9 = 0;
  *(_OWORD *)v8 = 0;
  v10[0] = &v11;
  v10[1] = &v12;
  v10[2] = &v14;
  v10[3] = v9;
  v10[4] = v8;
  v10[5] = &v13;
  v4 = AppMon::CaptureAndConvertExceptionToHR__lambda_fc74db3ed9fe3084f3f78e646fe91a0e___(v10);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_97cdaf78371d36d9099fba1de28de0ee_Traceguids,
        (unsigned int)v4);
    SetLastError((unsigned __int16)v5);
  }
  v6 = v5 >= 0;
  if ( v8[1] )
    std::_Ref_count_base::_Decref(v8[1]);
  if ( v9[1] )
    std::_Ref_count_base::_Decref(v9[1]);
  return v6;
}

```

## disassembly

```asm
0x1800072d0  mov     rax, rsp
0x1800072d3  mov     [rax+20h], r9
0x1800072d7  mov     [rax+18h], r8d
0x1800072db  mov     [rax+10h], rdx
0x1800072df  mov     [rax+8], rcx
0x1800072e3  push    rbp
0x1800072e4  push    rbx
0x1800072e5  push    rdi
0x1800072e6  mov     rbp, rsp
0x1800072e9  sub     rsp, 70h
0x1800072ed  lea     rdi, WPP_GLOBAL_Control
0x1800072f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072fb  cmp     rcx, rdi
0x1800072fe  jz      short loc_18000731B
0x180007300  test    byte ptr [rcx+1Ch], 1
0x180007304  jz      short loc_18000731B
0x180007306  mov     edx, 19h
0x18000730b  lea     r8, WPP_97cdaf78371d36d9099fba1de28de0ee_Traceguids
0x180007312  mov     rcx, [rcx+10h]
0x180007316  call    WPP_SF_
0x18000731b  xorps   xmm0, xmm0
0x18000731e  movdqu  xmmword ptr [rbp+var_40], xmm0
0x180007323  movdqu  xmmword ptr [rbp+var_50], xmm0
0x180007328  lea     rax, [rbp+arg_0]
0x18000732c  mov     [rbp+var_30], rax
0x180007330  lea     rax, [rbp+arg_8]
0x180007334  mov     [rbp+var_28], rax
0x180007338  lea     rax, [rbp+arg_18]
0x18000733c  mov     [rbp+var_20], rax
0x180007340  lea     rax, [rbp+var_40]
0x180007344  mov     [rbp+var_18], rax
0x180007348  lea     rax, [rbp+var_50]
0x18000734c  mov     [rbp+var_10], rax
0x180007350  lea     rax, [rbp+arg_10]
0x180007354  mov     [rbp+var_8], rax
0x180007358  lea     rcx, [rbp+var_30]
0x18000735c  call    AppMon__CaptureAndConvertExceptionToHR__lambda_fc74db3ed9fe3084f3f78e646fe91a0e___
0x180007361  mov     ebx, eax
0x180007363  test    eax, eax
0x180007365  jns     short loc_18000739B
0x180007367  mov     rcx, cs:WPP_GLOBAL_Control
0x18000736e  cmp     rcx, rdi
0x180007371  jz      short loc_180007391
0x180007373  test    byte ptr [rcx+1Ch], 8
0x180007377  jz      short loc_180007391
0x180007379  mov     edx, 1Ah
0x18000737e  mov     r9d, eax
0x180007381  lea     r8, WPP_97cdaf78371d36d9099fba1de28de0ee_Traceguids
0x180007388  mov     rcx, [rcx+10h]
0x18000738c  call    WPP_SF_d
0x180007391  movzx   ecx, bx; dwErrCode
0x180007394  call    cs:__imp_SetLastError
0x18000739a  nop
0x18000739b  not     ebx
0x18000739d  shr     ebx, 1Fh
0x1800073a0  mov     rcx, [rbp+var_50+8]; this
0x1800073a4  test    rcx, rcx
0x1800073a7  jz      short loc_1800073AF
0x1800073a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800073ae  nop
0x1800073af  mov     rcx, [rbp+var_40+8]; this
0x1800073b3  test    rcx, rcx
0x1800073b6  jz      short loc_1800073BD
0x1800073b8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800073bd  mov     eax, ebx
0x1800073bf  add     rsp, 70h
0x1800073c3  pop     rdi
0x1800073c4  pop     rbx
0x1800073c5  pop     rbp
0x1800073c6  retn
```
