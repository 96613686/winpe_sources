# AppMon::MonitorInterface::AppMonOpenPort(void *,ushort *,void * *)

- ea: `0x1800070f0`
- end: `0x1800071bf`
- name: `?AppMonOpenPort@MonitorInterface@AppMon@@SAHPEAXPEAGPEAPEAX@Z`
- size: `207`
- prototype: `_BOOL8 __fastcall(void *, unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005b34`
- `0x180005e48`
- `0x1800070f0`
- `0x18000798c`
- `0x180007a78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000719b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000719b`

## pseudocode

```c
_BOOL8 __fastcall AppMon::MonitorInterface::AppMonOpenPort(void *a1, unsigned __int16 *a2, void **a3)
{
  int v3; // eax
  int v4; // ebx
  BOOL v5; // ebx
  std::_Ref_count_base *v7[2]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v8[4]; // [rsp+30h] [rbp-20h] BYREF
  void *v9; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int16 *v10; // [rsp+78h] [rbp+28h] BYREF
  void **v11; // [rsp+80h] [rbp+30h] BYREF

  v11 = a3;
  v10 = a2;
  v9 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_97cdaf78371d36d9099fba1de28de0ee_Traceguids);
  *(_OWORD *)v7 = 0;
  v8[0] = &v9;
  v8[1] = &v10;
  v8[2] = &v11;
  v8[3] = v7;
  v3 = AppMon::CaptureAndConvertExceptionToHR__lambda_efcf23d17e2e36bb8836d653a6951244___(v8);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_97cdaf78371d36d9099fba1de28de0ee_Traceguids,
        (unsigned int)v3);
    SetLastError((unsigned __int16)v4);
  }
  v5 = v4 >= 0;
  if ( v7[1] )
    std::_Ref_count_base::_Decref(v7[1]);
  return v5;
}

```

## disassembly

```asm
0x1800070f0  mov     [rsp-18h+arg_10], r8
0x1800070f5  mov     [rsp-18h+arg_8], rdx
0x1800070fa  mov     [rsp-18h+arg_0], rcx
0x1800070ff  push    rbp
0x180007100  push    rbx
0x180007101  push    rdi
0x180007102  mov     rbp, rsp
0x180007105  sub     rsp, 50h
0x180007109  lea     rdi, WPP_GLOBAL_Control
0x180007110  mov     rcx, cs:WPP_GLOBAL_Control
0x180007117  cmp     rcx, rdi
0x18000711a  jz      short loc_180007137
0x18000711c  test    byte ptr [rcx+1Ch], 1
0x180007120  jz      short loc_180007137
0x180007122  mov     edx, 15h
0x180007127  lea     r8, WPP_97cdaf78371d36d9099fba1de28de0ee_Traceguids
0x18000712e  mov     rcx, [rcx+10h]
0x180007132  call    WPP_SF_
0x180007137  xorps   xmm0, xmm0
0x18000713a  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18000713f  lea     rax, [rbp+arg_0]
0x180007143  mov     [rbp+var_20], rax
0x180007147  lea     rax, [rbp+arg_8]
0x18000714b  mov     [rbp+var_18], rax
0x18000714f  lea     rax, [rbp+arg_10]
0x180007153  mov     [rbp+var_10], rax
0x180007157  lea     rax, [rbp+var_30]
0x18000715b  mov     [rbp+var_8], rax
0x18000715f  lea     rcx, [rbp+var_20]
0x180007163  call    AppMon__CaptureAndConvertExceptionToHR__lambda_efcf23d17e2e36bb8836d653a6951244___
0x180007168  mov     ebx, eax
0x18000716a  test    eax, eax
0x18000716c  jns     short loc_1800071A2
0x18000716e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007175  cmp     rcx, rdi
0x180007178  jz      short loc_180007198
0x18000717a  test    byte ptr [rcx+1Ch], 8
0x18000717e  jz      short loc_180007198
0x180007180  mov     edx, 16h
0x180007185  mov     r9d, eax
0x180007188  lea     r8, WPP_97cdaf78371d36d9099fba1de28de0ee_Traceguids
0x18000718f  mov     rcx, [rcx+10h]
0x180007193  call    WPP_SF_d
0x180007198  movzx   ecx, bx; dwErrCode
0x18000719b  call    cs:__imp_SetLastError
0x1800071a1  nop
0x1800071a2  not     ebx
0x1800071a4  shr     ebx, 1Fh
0x1800071a7  mov     rcx, [rbp+var_30+8]; this
0x1800071ab  test    rcx, rcx
0x1800071ae  jz      short loc_1800071B5
0x1800071b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800071b5  mov     eax, ebx
0x1800071b7  add     rsp, 50h
0x1800071bb  pop     rdi
0x1800071bc  pop     rbx
0x1800071bd  pop     rbp
0x1800071be  retn
```
