# UsbRemoveIrp

- ea: `0x14000f9f0`
- end: `0x14000fac6`
- name: `UsbRemoveIrp`
- size: `214`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140006040`
- `0x140013154`

## callees

- `0x14000ae80`
- `0x14000af70`
- `0x14000f9f0`
- `0x14000facc`
- `0x1400105e8`
- `0x140010664`

## pseudocode

```c
char __fastcall UsbRemoveIrp(__int64 a1, __int64 a2)
{
  unsigned int IrpPriority; // ebp
  __int64 v5; // rdx
  char v6; // bl
  __int64 v7; // r10
  __int64 v8; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  IrpPriority = UsbGetIrpPriority(a1, a2);
  UsbGetStreamSubQueue(a1, a2);
  v6 = PortListSearchAndRemoveRequest(a1 + 32, a2 + 120);
  if ( !v6 )
  {
    if ( IrpPriority <= 5 )
      v8 = a1 + 56LL * (IrpPriority - 1) + 88;
    else
      v8 = v7;
    v6 = PortListSearchAndRemoveRequest(v8, v5);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x14000f9f0  push    rbx
0x14000f9f2  push    rbp
0x14000f9f3  push    rsi
0x14000f9f4  push    rdi
0x14000f9f5  push    r14
0x14000f9f7  sub     rsp, 20h
0x14000f9fb  mov     rbx, rdx
0x14000f9fe  mov     rdi, rcx
0x14000fa01  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa08  lea     r14, WPP_GLOBAL_Control
0x14000fa0f  cmp     rcx, r14
0x14000fa12  jz      short loc_14000FA36
0x14000fa14  mov     eax, [rcx+2Ch]
0x14000fa17  test    al, 20h
0x14000fa19  jz      short loc_14000FA36
0x14000fa1b  cmp     byte ptr [rcx+29h], 4
0x14000fa1f  jb      short loc_14000FA36
0x14000fa21  mov     rcx, [rcx+18h]
0x14000fa25  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000fa2c  mov     edx, 26h ; '&'
0x14000fa31  call    WPP_SF_
0x14000fa36  mov     rdx, rbx
0x14000fa39  lea     rsi, [rbx+78h]
0x14000fa3d  mov     rcx, rdi
0x14000fa40  call    UsbGetIrpPriority
0x14000fa45  mov     rdx, rbx
0x14000fa48  mov     rcx, rdi
0x14000fa4b  mov     ebp, eax
0x14000fa4d  call    UsbGetStreamSubQueue
0x14000fa52  lea     rcx, [rdi+20h]
0x14000fa56  mov     rdx, rsi
0x14000fa59  mov     r10, rax
0x14000fa5c  call    PortListSearchAndRemoveRequest
0x14000fa61  mov     bl, al
0x14000fa63  test    al, al
0x14000fa65  jnz     short loc_14000FA86
0x14000fa67  cmp     ebp, 5
0x14000fa6a  jbe     short loc_14000FA71
0x14000fa6c  mov     rcx, r10
0x14000fa6f  jmp     short loc_14000FA7F
0x14000fa71  lea     ecx, [rbp-1]
0x14000fa74  imul    rcx, 38h ; '8'
0x14000fa78  add     rcx, 58h ; 'X'
0x14000fa7c  add     rcx, rdi
0x14000fa7f  call    PortListSearchAndRemoveRequest
0x14000fa84  mov     bl, al
0x14000fa86  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa8d  cmp     rcx, r14
0x14000fa90  jz      short loc_14000FAB8
0x14000fa92  mov     eax, [rcx+2Ch]
0x14000fa95  test    al, 20h
0x14000fa97  jz      short loc_14000FAB8
0x14000fa99  cmp     byte ptr [rcx+29h], 4
0x14000fa9d  jb      short loc_14000FAB8
0x14000fa9f  mov     rcx, [rcx+18h]
0x14000faa3  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000faaa  movzx   r9d, bl
0x14000faae  mov     edx, 27h ; '''
0x14000fab3  call    WPP_SF_d
0x14000fab8  mov     al, bl
0x14000faba  add     rsp, 20h
0x14000fabe  pop     r14
0x14000fac0  pop     rdi
0x14000fac1  pop     rsi
0x14000fac2  pop     rbp
0x14000fac3  pop     rbx
0x14000fac4  retn
```
