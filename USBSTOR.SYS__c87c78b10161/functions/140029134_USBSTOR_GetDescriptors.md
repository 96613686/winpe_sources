# USBSTOR_GetDescriptors

- ea: `0x140029134`
- end: `0x1400293c6`
- name: `USBSTOR_GetDescriptors`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140008590`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x140026cec`
- `0x140029134`
- `0x1400293cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002927c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029324`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002927c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029324`

## pseudocode

```c
__int64 __fastcall USBSTOR_GetDescriptors(__int64 a1)
{
  __int64 v2; // r14
  int v3; // r8d
  int v4; // edx
  int v5; // edx
  int Descriptor; // edi
  int v7; // r8d
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned __int16 v10; // bp
  int v11; // r8d
  PVOID P; // [rsp+70h] [rbp+8h] BYREF

  P = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1129530439, a1, 0, 0);
  v2 = *(_QWORD *)(a1 + 64);
  LOBYTE(v3) = 1;
  Descriptor = USBSTOR_GetDescriptor(a1, v4, v3, 0, 0);
  if ( Descriptor >= 0 )
  {
    *(_QWORD *)(v2 + 48) = P;
    LOBYTE(v7) = 2;
    Descriptor = USBSTOR_GetDescriptor(a1, v5, v7, 0, 0);
    if ( Descriptor >= 0 )
    {
      v10 = *((_WORD *)P + 1);
      ExFreePoolWithTag(P, 0);
      if ( v10 >= 9u )
      {
        LOBYTE(v11) = 2;
        Descriptor = USBSTOR_GetDescriptor(a1, (unsigned int)&P, v11, 0, 0);
        if ( Descriptor >= 0 )
        {
          if ( v10 == *((_WORD *)P + 1) )
          {
            *(_QWORD *)(v2 + 56) = P;
            if ( *(_BYTE *)(*(_QWORD *)(v2 + 48) + 16LL) )
              USBSTOR_GetStringDescriptors(a1);
            goto LABEL_33;
          }
          ExFreePoolWithTag(P, 0);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_37;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_33;
          v9 = 68;
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_37;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_33;
          v9 = 67;
        }
      }
      else
      {
        Descriptor = -1073741668;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_37;
        if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_33;
        }
        v9 = 66;
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_37;
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_33;
      }
      v9 = 65;
    }
    goto LABEL_10;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_37;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v9 = 64;
LABEL_10:
    WPP_SF_(v8->AttachedDevice, v9, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
LABEL_33:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
LABEL_37:
  USBSTOR_LogEntry(1668506727, Descriptor, 0, 0);
  return (unsigned int)Descriptor;
}

```

## disassembly

```asm
0x140029134  mov     [rsp+arg_8], rbp
0x140029139  mov     [rsp+arg_10], rsi
0x14002913e  push    rdi
0x14002913f  push    r12
0x140029141  push    r13
0x140029143  push    r14
0x140029145  push    r15
0x140029147  sub     rsp, 40h
0x14002914b  mov     rsi, rcx
0x14002914e  mov     [rsp+68h+P], 0
0x140029157  mov     rcx, cs:WPP_GLOBAL_Control
0x14002915e  lea     r15, WPP_GLOBAL_Control
0x140029165  lea     r12, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14002916c  cmp     rcx, r15
0x14002916f  jz      short loc_14002918F
0x140029171  bt      dword ptr [rcx+2Ch], 8
0x140029176  jnb     short loc_14002918F
0x140029178  cmp     byte ptr [rcx+29h], 4
0x14002917c  jb      short loc_14002918F
0x14002917e  mov     rcx, [rcx+18h]
0x140029182  mov     edx, 3Fh ; '?'
0x140029187  mov     r8, r12
0x14002918a  call    WPP_SF_
0x14002918f  xor     r9d, r9d
0x140029192  xor     r8d, r8d
0x140029195  mov     rdx, rsi
0x140029198  mov     ecx, 43534447h
0x14002919d  call    USBSTOR_LogEntry
0x1400291a2  mov     r14, [rsi+40h]
0x1400291a6  lea     rcx, [rsp+68h+P]
0x1400291ab  mov     [rsp+68h+var_30], rcx
0x1400291b0  xor     eax, eax
0x1400291b2  mov     [rsp+68h+var_38], 12h
0x1400291ba  mov     rcx, rsi
0x1400291bd  xor     r9d, r9d
0x1400291c0  mov     [rsp+68h+var_48], ax
0x1400291c5  mov     r8b, 1
0x1400291c8  call    USBSTOR_GetDescriptor
0x1400291cd  mov     edi, eax
0x1400291cf  test    eax, eax
0x1400291d1  jns     short loc_14002920F
0x1400291d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400291da  cmp     rcx, r15
0x1400291dd  jz      loc_140029396
0x1400291e3  mov     edx, [rcx+2Ch]
0x1400291e6  test    dl, 2
0x1400291e9  jz      loc_140029369
0x1400291ef  cmp     byte ptr [rcx+29h], 2
0x1400291f3  jb      loc_140029369
0x1400291f9  mov     edx, 40h ; '@'
0x1400291fe  mov     rcx, [rcx+18h]
0x140029202  mov     r8, r12
0x140029205  call    WPP_SF_
0x14002920a  jmp     loc_140029369
0x14002920f  mov     rax, [rsp+68h+P]
0x140029214  lea     rcx, [rsp+68h+P]
0x140029219  mov     [rsp+68h+var_30], rcx
0x14002921e  xor     r9d, r9d
0x140029221  mov     [r14+30h], rax
0x140029225  mov     r8b, 2
0x140029228  xor     eax, eax
0x14002922a  mov     [rsp+68h+var_38], 9
0x140029232  mov     rcx, rsi
0x140029235  mov     [rsp+68h+var_48], ax
0x14002923a  call    USBSTOR_GetDescriptor
0x14002923f  mov     edi, eax
0x140029241  test    eax, eax
0x140029243  jns     short loc_140029271
0x140029245  mov     rcx, cs:WPP_GLOBAL_Control
0x14002924c  cmp     rcx, r15
0x14002924f  jz      loc_140029396
0x140029255  bt      dword ptr [rcx+2Ch], 8
0x14002925a  jnb     loc_140029369
0x140029260  cmp     byte ptr [rcx+29h], 2
0x140029264  jb      loc_140029369
0x14002926a  mov     edx, 41h ; 'A'
0x14002926f  jmp     short loc_1400291FE
0x140029271  mov     rcx, [rsp+68h+P]; P
0x140029276  xor     edx, edx; Tag
0x140029278  movzx   ebp, word ptr [rcx+2]
0x14002927c  call    cs:__imp_ExFreePoolWithTag
0x140029283  nop     dword ptr [rax+rax+00h]
0x140029288  mov     eax, 9
0x14002928d  cmp     bp, ax
0x140029290  jnb     short loc_1400292C4
0x140029292  mov     edi, 0C000009Ch
0x140029297  mov     rcx, cs:WPP_GLOBAL_Control
0x14002929e  cmp     rcx, r15
0x1400292a1  jz      loc_140029396
0x1400292a7  bt      dword ptr [rcx+2Ch], 8
0x1400292ac  jnb     loc_140029369
0x1400292b2  cmp     byte ptr [rcx+29h], 2
0x1400292b6  jb      loc_140029369
0x1400292bc  lea     edx, [rax+39h]
0x1400292bf  jmp     loc_1400291FE
0x1400292c4  xor     ecx, ecx
0x1400292c6  lea     rdx, [rsp+68h+P]
0x1400292cb  mov     [rsp+68h+var_30], rdx
0x1400292d0  xor     r9d, r9d
0x1400292d3  mov     [rsp+68h+var_38], ebp
0x1400292d7  mov     r8b, 2
0x1400292da  mov     [rsp+68h+var_48], cx
0x1400292df  mov     rcx, rsi
0x1400292e2  call    USBSTOR_GetDescriptor
0x1400292e7  mov     edi, eax
0x1400292e9  test    eax, eax
0x1400292eb  jns     short loc_140029314
0x1400292ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400292f4  cmp     rcx, r15
0x1400292f7  jz      loc_140029396
0x1400292fd  mov     eax, [rcx+2Ch]
0x140029300  test    al, 2
0x140029302  jz      short loc_140029369
0x140029304  cmp     byte ptr [rcx+29h], 2
0x140029308  jb      short loc_140029369
0x14002930a  mov     edx, 43h ; 'C'
0x14002930f  jmp     loc_1400291FE
0x140029314  mov     rax, [rsp+68h+P]
0x140029319  cmp     bp, [rax+2]
0x14002931d  jz      short loc_140029353
0x14002931f  xor     edx, edx; Tag
0x140029321  mov     rcx, rax; P
0x140029324  call    cs:__imp_ExFreePoolWithTag
0x14002932b  nop     dword ptr [rax+rax+00h]
0x140029330  mov     rcx, cs:WPP_GLOBAL_Control
0x140029337  cmp     rcx, r15
0x14002933a  jz      short loc_140029396
0x14002933c  mov     eax, [rcx+2Ch]
0x14002933f  test    al, 2
0x140029341  jz      short loc_140029369
0x140029343  cmp     byte ptr [rcx+29h], 2
0x140029347  jb      short loc_140029369
0x140029349  mov     edx, 44h ; 'D'
0x14002934e  jmp     loc_1400291FE
0x140029353  mov     [r14+38h], rax
0x140029357  mov     rax, [r14+30h]
0x14002935b  cmp     byte ptr [rax+10h], 0
0x14002935f  jz      short loc_140029369
0x140029361  mov     rcx, rsi
0x140029364  call    USBSTOR_GetStringDescriptors
0x140029369  mov     rcx, cs:WPP_GLOBAL_Control
0x140029370  cmp     rcx, r15
0x140029373  jz      short loc_140029396
0x140029375  bt      dword ptr [rcx+2Ch], 8
0x14002937a  jnb     short loc_140029396
0x14002937c  cmp     byte ptr [rcx+29h], 4
0x140029380  jb      short loc_140029396
0x140029382  mov     rcx, [rcx+18h]
0x140029386  mov     edx, 45h ; 'E'
0x14002938b  mov     r9d, edi
0x14002938e  mov     r8, r12
0x140029391  call    WPP_SF_d
0x140029396  movsxd  rdx, edi
0x140029399  xor     r9d, r9d
0x14002939c  xor     r8d, r8d
0x14002939f  mov     ecx, 63736467h
0x1400293a4  call    USBSTOR_LogEntry
0x1400293a9  lea     r11, [rsp+68h+var_28]
0x1400293ae  mov     eax, edi
0x1400293b0  mov     rbp, [r11+38h]
0x1400293b4  mov     rsi, [r11+40h]
0x1400293b8  mov     rsp, r11
0x1400293bb  pop     r15
0x1400293bd  pop     r14
0x1400293bf  pop     r13
0x1400293c1  pop     r12
0x1400293c3  pop     rdi
0x1400293c4  retn
```
