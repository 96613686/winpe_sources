# FwCopyHyperVVMCreator

- ea: `0x180022690`
- end: `0x180022785`
- name: `FwCopyHyperVVMCreator`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001cdc`
- `0x1800042c4`
- `0x180019be0`
- `0x180022690`

## import_xrefs

- `fwbase!FwAlloc` at `0x1800226b1`
- `fwbase!FwAlloc` at `0x1800226b1`
- `fwbase!FwStringCopy` at `0x180022718`
- `fwbase!FwStringCopy` at `0x180022718`

## string_xrefs

- `0x180022741`: `FwStringCopy:friendlyName`

## pseudocode

```c
__int64 __fastcall FwCopyHyperVVMCreator(__int64 a1, __int64 *a2)
{
  __int64 v4; // rbx
  int v5; // edi

  *a2 = 0;
  v4 = FwAlloc(40);
  if ( v4 )
  {
    *(_WORD *)(v4 + 8) = *(_WORD *)(a1 + 8);
    *(_OWORD *)(v4 + 12) = *(_OWORD *)(a1 + 12);
    v5 = FwStringCopy(*(_QWORD *)(a1 + 32), v4 + 32);
    if ( v5 >= 0 )
    {
      *a2 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          209,
          (unsigned int)WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids,
          v5,
          (__int64)"FwStringCopy:friendlyName");
      FwFreeHyperVVMCreatorsBySchemaVersion(v4, 545);
    }
  }
  else
  {
    v5 = -2147024882;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, 2147942414LL);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022690  mov     [rsp+arg_0], rbx
0x180022695  mov     [rsp+arg_8], rsi
0x18002269a  push    rdi
0x18002269b  sub     rsp, 30h
0x18002269f  mov     rdi, rcx
0x1800226a2  mov     qword ptr [rdx], 0
0x1800226a9  mov     ecx, 28h ; '('
0x1800226ae  mov     rsi, rdx
0x1800226b1  call    cs:__imp_FwAlloc
0x1800226b7  mov     rbx, rax
0x1800226ba  test    rax, rax
0x1800226bd  jnz     short loc_1800226FF
0x1800226bf  mov     edi, 8007000Eh
0x1800226c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226cb  lea     rax, WPP_GLOBAL_Control
0x1800226d2  cmp     rcx, rax
0x1800226d5  jz      loc_180022773
0x1800226db  test    byte ptr [rcx+1Ch], 1
0x1800226df  jz      loc_180022773
0x1800226e5  mov     rcx, [rcx+10h]
0x1800226e9  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x1800226f0  mov     edx, 0D0h
0x1800226f5  mov     r9d, edi
0x1800226f8  call    WPP_SF_d
0x1800226fd  jmp     short loc_180022773
0x1800226ff  movzx   eax, word ptr [rdi+8]
0x180022703  lea     rdx, [rbx+20h]
0x180022707  mov     [rbx+8], ax
0x18002270b  movups  xmm0, xmmword ptr [rdi+0Ch]
0x18002270f  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180022714  mov     rcx, [rdi+20h]
0x180022718  call    cs:__imp_FwStringCopy
0x18002271e  mov     edi, eax
0x180022720  test    eax, eax
0x180022722  jns     short loc_180022770
0x180022724  mov     rcx, cs:WPP_GLOBAL_Control
0x18002272b  lea     rax, WPP_GLOBAL_Control
0x180022732  cmp     rcx, rax
0x180022735  jz      short loc_180022761
0x180022737  test    byte ptr [rcx+1Ch], 1
0x18002273b  jz      short loc_180022761
0x18002273d  mov     rcx, [rcx+10h]
0x180022741  lea     rax, aFwstringcopyFr; "FwStringCopy:friendlyName"
0x180022748  mov     edx, 0D1h
0x18002274d  mov     [rsp+38h+var_18], rax
0x180022752  mov     r9d, edi
0x180022755  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x18002275c  call    WPP_SF_ds
0x180022761  mov     edx, 221h
0x180022766  mov     rcx, rbx
0x180022769  call    FwFreeHyperVVMCreatorsBySchemaVersion
0x18002276e  jmp     short loc_180022773
0x180022770  mov     [rsi], rbx
0x180022773  mov     rbx, [rsp+38h+arg_0]
0x180022778  mov     eax, edi
0x18002277a  mov     rsi, [rsp+38h+arg_8]
0x18002277f  add     rsp, 30h
0x180022783  pop     rdi
0x180022784  retn
```
