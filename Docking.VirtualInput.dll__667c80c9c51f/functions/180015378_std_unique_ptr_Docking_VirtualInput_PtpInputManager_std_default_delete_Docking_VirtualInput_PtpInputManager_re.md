# std::unique_ptr<Docking::VirtualInput::PtpInputManager,std::default_delete<Docking::VirtualInput::PtpInputManager>>::reset(Docking::VirtualInput::PtpInputManager *)

- ea: `0x180015378`
- end: `0x1800153cc`
- name: `?reset@?$unique_ptr@VPtpInputManager@VirtualInput@Docking@@U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@@std@@QEAAXPEAVPtpInputManager@VirtualInput@Docking@@@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014650`

## callees

- `0x18000b810`
- `0x18000ce24`
- `0x180014740`
- `0x180015378`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<Docking::VirtualInput::PtpInputManager>::reset(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // [rsp+20h] [rbp-18h]
  __int64 v4; // [rsp+28h] [rbp-10h]
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  result = std::exchange<Docking::VirtualInput::PtpInputManager *,std::nullptr_t>(a1, &v6);
  v3 = result;
  if ( result )
  {
    v4 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a1);
    return std::default_delete<Docking::VirtualInput::PtpInputManager>::operator()(v4, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180015378  mov     [rsp+arg_8], rdx
0x18001537d  mov     [rsp+arg_0], rcx
0x180015382  sub     rsp, 38h
0x180015386  mov     rax, [rsp+38h+arg_0]
0x18001538b  lea     rdx, [rsp+38h+arg_8]
0x180015390  mov     rcx, rax
0x180015393  call    ??$exchange@PEAVPtpInputManager@VirtualInput@Docking@@$$T@std@@YAPEAVPtpInputManager@VirtualInput@Docking@@AEAPEAV123@$$QEA$$T@Z
0x180015398  mov     [rsp+38h+var_18], rax
0x18001539d  cmp     [rsp+38h+var_18], 0
0x1800153a3  jz      short loc_1800153C7
0x1800153a5  mov     rax, [rsp+38h+arg_0]
0x1800153aa  mov     rcx, rax
0x1800153ad  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x1800153b2  mov     [rsp+38h+var_10], rax
0x1800153b7  mov     rdx, [rsp+38h+var_18]
0x1800153bc  mov     rcx, [rsp+38h+var_10]
0x1800153c1  call    ??R?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@QEBAXPEAVPtpInputManager@VirtualInput@Docking@@@Z; std::default_delete<Docking::VirtualInput::PtpInputManager>::operator()(Docking::VirtualInput::PtpInputManager *)
0x1800153c6  nop
0x1800153c7  add     rsp, 38h
0x1800153cb  retn
```
