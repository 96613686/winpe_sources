# USBSTOR_1667SendSecurityProtocolIn

- ea: `0x140021e34`
- end: `0x140021feb`
- name: `USBSTOR_1667SendSecurityProtocolIn`
- size: `439`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400220e4`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x140021e34`
- `0x140022098`
- `0x1400266ac`

## pseudocode

```c
__int64 __fastcall USBSTOR_1667SendSecurityProtocolIn(
        PDEVICE_OBJECT DeviceObject,
        __int64 a2,
        char a3,
        __int64 a4,
        int a5,
        unsigned int *a6)
{
  PDEVICE_OBJECT v8; // rcx
  unsigned int *v9; // rsi
  unsigned int v10; // edi
  unsigned int v11; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int128 Src; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+98h] [rbp+48h] BYREF

  LODWORD(v16) = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids);
  }
  v9 = a6;
  v10 = *a6;
  *a6 = 0;
  if ( !a3 || (v10 & 0x1FF) == 0 )
  {
    Src = 0;
    LOBYTE(v8) = a3;
    BYTE4(Src) = a3 << 7;
    LODWORD(Src) = 162;
    USBSTOR_1667SetAllocationLength(v8, v10, &v16, (char *)&Src + 6);
    if ( (unsigned int)v16 <= v10 )
    {
      v11 = USBSTOR_IssueInternalCdbToLun(DeviceObject, (__int64)&v16, &Src, 12, 10);
      if ( (v11 & 0x80000000) == 0 )
      {
        *v9 = v10;
        goto LABEL_23;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v11;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_23;
      v13 = 13;
    }
    else
    {
      v11 = -1073741789;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v11;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_23;
      v13 = 12;
    }
    goto LABEL_11;
  }
  v11 = -1073741789;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v11;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v13 = 11;
LABEL_11:
    WPP_SF_(v12->AttachedDevice, v13, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids);
  }
LABEL_23:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids);
  }
  return v11;
}

```

## disassembly

```asm
0x140021e34  mov     [rsp-28h+arg_0], rbx
0x140021e39  mov     [rsp-28h+arg_8], rsi
0x140021e3e  mov     byte ptr [rsp-28h+arg_18], r9b
0x140021e43  push    rbp
0x140021e44  push    rdi
0x140021e45  push    r13
0x140021e47  push    r14
0x140021e49  push    r15
0x140021e4b  mov     rbp, rsp
0x140021e4e  sub     rsp, 50h
0x140021e52  mov     r14b, dl
0x140021e55  mov     bl, r8b
0x140021e58  xor     edx, edx
0x140021e5a  mov     r15, rcx
0x140021e5d  mov     dword ptr [rbp+arg_18], edx
0x140021e60  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e67  lea     r13, WPP_GLOBAL_Control
0x140021e6e  cmp     rcx, r13
0x140021e71  jz      short loc_140021E97
0x140021e73  mov     eax, [rcx+2Ch]
0x140021e76  test    al, 1
0x140021e78  jz      short loc_140021E97
0x140021e7a  cmp     byte ptr [rcx+29h], 4
0x140021e7e  jb      short loc_140021E97
0x140021e80  mov     rcx, [rcx+18h]
0x140021e84  lea     r8, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids
0x140021e8b  mov     edx, 0Ah
0x140021e90  call    WPP_SF_
0x140021e95  xor     edx, edx
0x140021e97  mov     rsi, [rbp+arg_28]
0x140021e9b  mov     edi, [rsi]
0x140021e9d  mov     [rsi], edx
0x140021e9f  test    bl, bl
0x140021ea1  jz      short loc_140021EEF
0x140021ea3  test    edi, 1FFh
0x140021ea9  jz      short loc_140021EEF
0x140021eab  mov     ebx, 0C0000023h
0x140021eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140021eb7  cmp     rcx, r13
0x140021eba  jz      loc_140021FCF
0x140021ec0  mov     eax, [rcx+2Ch]
0x140021ec3  test    al, 1
0x140021ec5  jz      loc_140021F9E
0x140021ecb  cmp     byte ptr [rcx+29h], 2
0x140021ecf  jb      loc_140021F9E
0x140021ed5  mov     edx, 0Bh
0x140021eda  mov     rcx, [rcx+18h]
0x140021ede  lea     r8, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids
0x140021ee5  call    WPP_SF_
0x140021eea  jmp     loc_140021F9E
0x140021eef  mov     al, bl
0x140021ef1  lea     r9, [rbp+var_10+6]
0x140021ef5  shl     al, 7
0x140021ef8  lea     r8, [rbp+arg_18]
0x140021efc  xorps   xmm0, xmm0
0x140021eff  mov     edx, edi
0x140021f01  movups  [rbp+var_10], xmm0
0x140021f05  mov     cl, bl
0x140021f07  mov     byte ptr [rbp+var_10+4], al
0x140021f0a  mov     dword ptr [rbp+var_10], 0A2h
0x140021f11  call    USBSTOR_1667SetAllocationLength
0x140021f16  cmp     dword ptr [rbp+arg_18], edi
0x140021f19  jbe     short loc_140021F44
0x140021f1b  mov     ebx, 0C0000023h
0x140021f20  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f27  cmp     rcx, r13
0x140021f2a  jz      loc_140021FCF
0x140021f30  mov     eax, [rcx+2Ch]
0x140021f33  test    al, 1
0x140021f35  jz      short loc_140021F9E
0x140021f37  cmp     byte ptr [rcx+29h], 2
0x140021f3b  jb      short loc_140021F9E
0x140021f3d  mov     edx, 0Ch
0x140021f42  jmp     short loc_140021EDA
0x140021f44  mov     r9, [rbp+arg_30]
0x140021f48  lea     rax, [rbp+var_10]
0x140021f4c  mov     [rsp+50h+var_18], 0Ah; int
0x140021f54  mov     dl, r14b
0x140021f57  mov     [rsp+50h+var_20], 0Ch; char
0x140021f5c  mov     rcx, r15; DeviceObject
0x140021f5f  mov     [rsp+50h+Src], rax; Src
0x140021f64  lea     rax, [rbp+arg_18]
0x140021f68  mov     [rsp+50h+var_30], rax; __int64
0x140021f6d  call    USBSTOR_IssueInternalCdbToLun
0x140021f72  mov     ebx, eax
0x140021f74  test    eax, eax
0x140021f76  jns     short loc_140021F9C
0x140021f78  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f7f  cmp     rcx, r13
0x140021f82  jz      short loc_140021FCF
0x140021f84  mov     edx, [rcx+2Ch]
0x140021f87  test    dl, 1
0x140021f8a  jz      short loc_140021F9E
0x140021f8c  cmp     byte ptr [rcx+29h], 2
0x140021f90  jb      short loc_140021F9E
0x140021f92  mov     edx, 0Dh
0x140021f97  jmp     loc_140021EDA
0x140021f9c  mov     [rsi], edi
0x140021f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021fa5  cmp     rcx, r13
0x140021fa8  jz      short loc_140021FCF
0x140021faa  mov     eax, [rcx+2Ch]
0x140021fad  test    al, 1
0x140021faf  jz      short loc_140021FCF
0x140021fb1  cmp     byte ptr [rcx+29h], 4
0x140021fb5  jb      short loc_140021FCF
0x140021fb7  mov     rcx, [rcx+18h]
0x140021fbb  lea     r8, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids
0x140021fc2  mov     edx, 0Eh
0x140021fc7  mov     r9d, ebx
0x140021fca  call    WPP_SF_d
0x140021fcf  lea     r11, [rsp+50h+var_s0]
0x140021fd4  mov     eax, ebx
0x140021fd6  mov     rbx, [r11+30h]
0x140021fda  mov     rsi, [r11+38h]
0x140021fde  mov     rsp, r11
0x140021fe1  pop     r15
0x140021fe3  pop     r14
0x140021fe5  pop     r13
0x140021fe7  pop     rdi
0x140021fe8  pop     rbp
0x140021fe9  retn
```
