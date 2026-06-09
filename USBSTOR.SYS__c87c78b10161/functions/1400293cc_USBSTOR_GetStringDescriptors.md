# USBSTOR_GetStringDescriptors

- ea: `0x1400293cc`
- end: `0x1400297a9`
- name: `USBSTOR_GetStringDescriptors`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140029134`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x140010cb4`
- `0x140026cec`
- `0x1400293cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400294b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029543`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400295b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029632`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400296c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400294b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029543`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400295b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029632`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400296c0`

## pseudocode

```c
__int64 __fastcall USBSTOR_GetStringDescriptors(__int64 a1)
{
  __int64 v2; // r14
  int v3; // r8d
  int v4; // edx
  __int64 v5; // rdx
  int Descriptor; // ebx
  __int64 v7; // r8
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int16 v11; // bp
  unsigned int v12; // edx
  unsigned __int64 v13; // rcx
  __int64 v14; // r9
  int v15; // r8d
  int v16; // edx
  unsigned int v17; // edi
  __int64 v18; // r9

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1128551239, a1, 0, 0);
  v2 = *(_QWORD *)(a1 + 64);
  LOBYTE(v3) = 3;
  Descriptor = USBSTOR_GetDescriptor(a1, v4, v3, 0, 0);
  if ( Descriptor >= 0 )
  {
    v10 = MEMORY[0];
    ExFreePoolWithTag(0, 0);
    if ( (unsigned int)v10 < 4 || (v10 & 1) != 0 )
    {
      Descriptor = -1073741668;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_54;
      }
      v9 = 72;
      goto LABEL_53;
    }
    LOBYTE(v7) = 3;
    Descriptor = USBSTOR_GetDescriptor(a1, v5, v7, 0, 0);
    if ( Descriptor < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_54;
      }
      v9 = 73;
      goto LABEL_53;
    }
    if ( (_DWORD)v10 != MEMORY[0] )
    {
      ExFreePoolWithTag(0, 0);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_54;
      }
      v9 = 74;
      goto LABEL_53;
    }
    v11 = MEMORY[2];
    v12 = 2;
    v13 = (unsigned __int64)(v10 - 2) >> 1;
    if ( (unsigned int)v13 >= 2 )
    {
      while ( *(_WORD *)(2LL * v12) != 1033 )
      {
        if ( ++v12 > (unsigned int)v13 )
          goto LABEL_27;
      }
      v11 = 1033;
    }
LABEL_27:
    ExFreePoolWithTag(0, 0);
    v14 = *(_QWORD *)(v2 + 48);
    LOBYTE(v15) = 3;
    LOBYTE(v14) = *(_BYTE *)(v14 + 16);
    Descriptor = USBSTOR_GetDescriptor(a1, v16, v15, v14, v11);
    if ( Descriptor < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_54;
      }
      v9 = 75;
      goto LABEL_53;
    }
    v17 = MEMORY[0];
    ExFreePoolWithTag(0, 0);
    if ( v17 < 4 || (v17 & 1) != 0 )
    {
      Descriptor = -1073741668;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_54;
      }
      v9 = 76;
      goto LABEL_53;
    }
    v18 = *(_QWORD *)(v2 + 48);
    LOBYTE(v7) = 3;
    LOBYTE(v18) = *(_BYTE *)(v18 + 16);
    Descriptor = USBSTOR_GetDescriptor(a1, v5, v7, v18, v11);
    if ( Descriptor < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_54;
      }
      v9 = 77;
      goto LABEL_53;
    }
    if ( v17 != MEMORY[0] )
    {
      ExFreePoolWithTag(0, 0);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_54;
      }
      v9 = 78;
      goto LABEL_53;
    }
    *(_QWORD *)(v2 + 72) = 0;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_58;
    if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u) && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 71;
LABEL_53:
      WPP_SF_d(v8->AttachedDevice, v9, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
  }
LABEL_54:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, v5, v7, (unsigned int)Descriptor, *(_QWORD *)(v2 + 72));
  }
LABEL_58:
  USBSTOR_LogEntry(1668506727, Descriptor, 0, 0);
  return (unsigned int)Descriptor;
}

```

## disassembly

```asm
0x1400293cc  mov     rax, rsp
0x1400293cf  push    rbx
0x1400293d0  push    rbp
0x1400293d1  push    rsi
0x1400293d2  push    rdi
0x1400293d3  push    r12
0x1400293d5  push    r13
0x1400293d7  push    r14
0x1400293d9  push    r15
0x1400293db  sub     rsp, 48h
0x1400293df  mov     rsi, rcx
0x1400293e2  mov     qword ptr [rax+8], 0
0x1400293ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400293f1  lea     r13, WPP_GLOBAL_Control
0x1400293f8  lea     rbp, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400293ff  cmp     rcx, r13
0x140029402  jz      short loc_140029422
0x140029404  bt      dword ptr [rcx+2Ch], 8
0x140029409  jnb     short loc_140029422
0x14002940b  cmp     byte ptr [rcx+29h], 4
0x14002940f  jb      short loc_140029422
0x140029411  mov     rcx, [rcx+18h]
0x140029415  mov     edx, 46h ; 'F'
0x14002941a  mov     r8, rbp
0x14002941d  call    WPP_SF_
0x140029422  xor     r9d, r9d
0x140029425  xor     r8d, r8d
0x140029428  mov     rdx, rsi
0x14002942b  mov     ecx, 43445347h
0x140029430  call    USBSTOR_LogEntry
0x140029435  mov     r14, [rsi+40h]
0x140029439  lea     rcx, [rsp+88h+P]
0x140029441  mov     [rsp+88h+var_50], rcx
0x140029446  xor     eax, eax
0x140029448  xor     r9d, r9d
0x14002944b  mov     r8b, 3
0x14002944e  mov     rcx, rsi
0x140029451  lea     r15d, [rax+2]
0x140029455  mov     [rsp+88h+var_58], r15d
0x14002945a  mov     word ptr [rsp+88h+var_68], ax
0x14002945f  call    USBSTOR_GetDescriptor
0x140029464  mov     ebx, eax
0x140029466  test    eax, eax
0x140029468  jns     short loc_1400294A7
0x14002946a  mov     rcx, cs:WPP_GLOBAL_Control
0x140029471  cmp     rcx, r13
0x140029474  jz      loc_140029782
0x14002947a  bt      dword ptr [rcx+2Ch], 8
0x14002947f  jnb     loc_140029754
0x140029485  cmp     [rcx+29h], r15b
0x140029489  jb      loc_140029754
0x14002948f  lea     edx, [r15+45h]
0x140029493  mov     r8, rbp
0x140029496  mov     rcx, [rcx+18h]
0x14002949a  mov     r9d, eax
0x14002949d  call    WPP_SF_d
0x1400294a2  jmp     loc_140029754
0x1400294a7  mov     rcx, [rsp+88h+P]; P
0x1400294af  xor     edx, edx; Tag
0x1400294b1  movzx   edi, byte ptr [rcx]
0x1400294b4  call    cs:__imp_ExFreePoolWithTag
0x1400294bb  nop     dword ptr [rax+rax+00h]
0x1400294c0  cmp     edi, 4
0x1400294c3  jb      loc_140029722
0x1400294c9  test    dil, 1
0x1400294cd  jnz     loc_140029722
0x1400294d3  lea     rcx, [rsp+88h+P]
0x1400294db  xor     eax, eax
0x1400294dd  mov     [rsp+88h+var_50], rcx
0x1400294e2  xor     r9d, r9d
0x1400294e5  mov     [rsp+88h+var_58], edi
0x1400294e9  mov     rcx, rsi
0x1400294ec  mov     r8b, 3
0x1400294ef  mov     word ptr [rsp+88h+var_68], ax
0x1400294f4  call    USBSTOR_GetDescriptor
0x1400294f9  mov     ebx, eax
0x1400294fb  test    eax, eax
0x1400294fd  jns     short loc_14002952E
0x1400294ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140029506  cmp     rcx, r13
0x140029509  jz      loc_140029782
0x14002950f  bt      dword ptr [rcx+2Ch], 8
0x140029514  jnb     loc_140029754
0x14002951a  cmp     [rcx+29h], r15b
0x14002951e  jb      loc_140029754
0x140029524  mov     edx, 49h ; 'I'
0x140029529  jmp     loc_140029493
0x14002952e  mov     r8, [rsp+88h+P]
0x140029536  movzx   eax, byte ptr [r8]
0x14002953a  cmp     edi, eax
0x14002953c  jz      short loc_14002957E
0x14002953e  xor     edx, edx; Tag
0x140029540  mov     rcx, r8; P
0x140029543  call    cs:__imp_ExFreePoolWithTag
0x14002954a  nop     dword ptr [rax+rax+00h]
0x14002954f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029556  cmp     rcx, r13
0x140029559  jz      loc_140029782
0x14002955f  bt      dword ptr [rcx+2Ch], 8
0x140029564  jnb     loc_140029754
0x14002956a  cmp     [rcx+29h], r15b
0x14002956e  jb      loc_140029754
0x140029574  mov     edx, 4Ah ; 'J'
0x140029579  jmp     loc_140029745
0x14002957e  movzx   ebp, word ptr [r8+2]
0x140029583  mov     rcx, rdi
0x140029586  sub     rcx, r15
0x140029589  mov     edx, r15d
0x14002958c  shr     rcx, 1
0x14002958f  cmp     ecx, r15d
0x140029592  jb      short loc_1400295AE
0x140029594  mov     r9d, 409h
0x14002959a  mov     eax, edx
0x14002959c  cmp     [r8+rax*2], r9w
0x1400295a1  jz      short loc_1400295AB
0x1400295a3  inc     edx
0x1400295a5  cmp     edx, ecx
0x1400295a7  jbe     short loc_14002959A
0x1400295a9  jmp     short loc_1400295AE
0x1400295ab  mov     ebp, r9d
0x1400295ae  xor     edx, edx; Tag
0x1400295b0  mov     rcx, r8; P
0x1400295b3  call    cs:__imp_ExFreePoolWithTag
0x1400295ba  nop     dword ptr [rax+rax+00h]
0x1400295bf  mov     r9, [r14+30h]
0x1400295c3  lea     rax, [rsp+88h+P]
0x1400295cb  mov     [rsp+88h+var_50], rax
0x1400295d0  mov     r8b, 3
0x1400295d3  mov     [rsp+88h+var_58], r15d
0x1400295d8  mov     rcx, rsi
0x1400295db  mov     word ptr [rsp+88h+var_68], bp
0x1400295e0  mov     r9b, [r9+10h]
0x1400295e4  call    USBSTOR_GetDescriptor
0x1400295e9  mov     ebx, eax
0x1400295eb  test    eax, eax
0x1400295ed  jns     short loc_140029625
0x1400295ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400295f6  cmp     rcx, r13
0x1400295f9  jz      loc_140029782
0x1400295ff  bt      dword ptr [rcx+2Ch], 8
0x140029604  jnb     loc_140029754
0x14002960a  cmp     [rcx+29h], r15b
0x14002960e  jb      loc_140029754
0x140029614  mov     edx, 4Bh ; 'K'
0x140029619  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140029620  jmp     loc_140029496
0x140029625  mov     rcx, [rsp+88h+P]; P
0x14002962d  xor     edx, edx; Tag
0x14002962f  movzx   edi, byte ptr [rcx]
0x140029632  call    cs:__imp_ExFreePoolWithTag
0x140029639  nop     dword ptr [rax+rax+00h]
0x14002963e  cmp     edi, 4
0x140029641  jb      loc_1400296FD
0x140029647  test    dil, 1
0x14002964b  jnz     loc_1400296FD
0x140029651  mov     r9, [r14+30h]
0x140029655  lea     rax, [rsp+88h+P]
0x14002965d  mov     [rsp+88h+var_50], rax
0x140029662  mov     r8b, 3
0x140029665  mov     [rsp+88h+var_58], edi
0x140029669  mov     rcx, rsi
0x14002966c  mov     word ptr [rsp+88h+var_68], bp
0x140029671  mov     r9b, [r9+10h]
0x140029675  call    USBSTOR_GetDescriptor
0x14002967a  mov     ebx, eax
0x14002967c  test    eax, eax
0x14002967e  jns     short loc_1400296AF
0x140029680  mov     rcx, cs:WPP_GLOBAL_Control
0x140029687  cmp     rcx, r13
0x14002968a  jz      loc_140029782
0x140029690  bt      dword ptr [rcx+2Ch], 8
0x140029695  jnb     loc_140029754
0x14002969b  cmp     [rcx+29h], r15b
0x14002969f  jb      loc_140029754
0x1400296a5  mov     edx, 4Dh ; 'M'
0x1400296aa  jmp     loc_140029619
0x1400296af  mov     rcx, [rsp+88h+P]; P
0x1400296b7  movzx   eax, byte ptr [rcx]
0x1400296ba  cmp     edi, eax
0x1400296bc  jz      short loc_1400296F7
0x1400296be  xor     edx, edx; Tag
0x1400296c0  call    cs:__imp_ExFreePoolWithTag
0x1400296c7  nop     dword ptr [rax+rax+00h]
0x1400296cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400296d3  cmp     rcx, r13
0x1400296d6  jz      loc_140029782
0x1400296dc  bt      dword ptr [rcx+2Ch], 8
0x1400296e1  jnb     short loc_140029754
0x1400296e3  cmp     [rcx+29h], r15b
0x1400296e7  jb      short loc_140029754
0x1400296e9  mov     edx, 4Eh ; 'N'
0x1400296ee  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400296f5  jmp     short loc_140029748
0x1400296f7  mov     [r14+48h], rcx
0x1400296fb  jmp     short loc_140029754
0x1400296fd  mov     ebx, 0C000009Ch
0x140029702  mov     rcx, cs:WPP_GLOBAL_Control
0x140029709  cmp     rcx, r13
0x14002970c  jz      short loc_140029782
0x14002970e  bt      dword ptr [rcx+2Ch], 8
0x140029713  jnb     short loc_140029754
0x140029715  cmp     [rcx+29h], r15b
0x140029719  jb      short loc_140029754
0x14002971b  mov     edx, 4Ch ; 'L'
0x140029720  jmp     short loc_1400296EE
0x140029722  mov     ebx, 0C000009Ch
0x140029727  mov     rcx, cs:WPP_GLOBAL_Control
0x14002972e  cmp     rcx, r13
0x140029731  jz      short loc_140029782
0x140029733  bt      dword ptr [rcx+2Ch], 8
0x140029738  jnb     short loc_140029754
0x14002973a  cmp     [rcx+29h], r15b
0x14002973e  jb      short loc_140029754
0x140029740  mov     edx, 48h ; 'H'
0x140029745  mov     r8, rbp
0x140029748  mov     rcx, [rcx+18h]
0x14002974c  mov     r9d, edi
0x14002974f  call    WPP_SF_d
0x140029754  mov     rcx, cs:WPP_GLOBAL_Control
0x14002975b  cmp     rcx, r13
0x14002975e  jz      short loc_140029782
0x140029760  bt      dword ptr [rcx+2Ch], 8
0x140029765  jnb     short loc_140029782
0x140029767  cmp     byte ptr [rcx+29h], 4
0x14002976b  jb      short loc_140029782
0x14002976d  mov     rax, [r14+48h]
0x140029771  mov     r9d, ebx
0x140029774  mov     rcx, [rcx+18h]
0x140029778  mov     [rsp+88h+var_68], rax
0x14002977d  call    WPP_SF_Dq
0x140029782  movsxd  rdx, ebx
0x140029785  xor     r9d, r9d
0x140029788  xor     r8d, r8d
0x14002978b  mov     ecx, 63736467h
0x140029790  call    USBSTOR_LogEntry
0x140029795  mov     eax, ebx
0x140029797  add     rsp, 48h
0x14002979b  pop     r15
0x14002979d  pop     r14
0x14002979f  pop     r13
0x1400297a1  pop     r12
0x1400297a3  pop     rdi
0x1400297a4  pop     rsi
0x1400297a5  pop     rbp
0x1400297a6  pop     rbx
0x1400297a7  retn
```
