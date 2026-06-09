# USBSTOR_GetStateSeparationLocation

- ea: `0x14002239c`
- end: `0x140022618`
- name: `USBSTOR_GetStateSeparationLocation`
- size: `636`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001fca8`
- `0x140026f6c`

## callees

- `0x140010664`
- `0x14002239c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002244f`
- `ntoskrnl!ExAllocatePool2` at `0x140022528`
- `ntoskrnl!ExAllocatePool2` at `0x14002244f`
- `ntoskrnl!ExAllocatePool2` at `0x140022528`
- `ntoskrnl!swprintf_s` at `0x14002258f`
- `ntoskrnl!swprintf_s` at `0x14002258f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400225ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022600`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400225ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022600`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400223e4`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400224c9`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400223e4`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400224c9`

## string_xrefs

- `0x1400223db`: `\Registry\Machine\System\CurrentControlSet\Control\usbstor`
- `0x1400224a4`: `\Registry\Machine\System\CurrentControlSet\Control\usbstor`

## pseudocode

```c
__int64 __fastcall USBSTOR_GetStateSeparationLocation(__int64 a1, __int64 a2, __int64 a3, int a4, wchar_t **a5)
{
  int PersistedStateLocation; // eax
  int v8; // ebx
  void *Pool2; // rsi
  wchar_t *v10; // rdi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  unsigned __int64 v13; // rbx
  wchar_t *v14; // rax
  unsigned int v16; // [rsp+78h] [rbp+10h] BYREF
  int v17; // [rsp+7Ch] [rbp+14h]

  v17 = HIDWORD(a2);
  v16 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"USBStor",
                             0,
                             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\usbstor",
                             0,
                             0,
                             0,
                             &v16);
  v8 = PersistedStateLocation;
  if ( PersistedStateLocation >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_8c8e2bcf66043dde3d33f256d9bd74b7_Traceguids);
    }
    return (unsigned int)-1073741823;
  }
  if ( PersistedStateLocation != -2147483643 )
    return (unsigned int)v8;
  Pool2 = (void *)ExAllocatePool2(256, v16, 1396788565);
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_8c8e2bcf66043dde3d33f256d9bd74b7_Traceguids);
    }
    return (unsigned int)-1073741670;
  }
  v8 = RtlGetPersistedStateLocation(
         L"USBStor",
         0,
         L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\usbstor",
         0,
         Pool2,
         v16,
         0);
  if ( v8 >= 0 )
  {
    v13 = a4 + v16 + 2;
    v14 = (wchar_t *)ExAllocatePool2(256, v13, 1396788565);
    v10 = v14;
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_8c8e2bcf66043dde3d33f256d9bd74b7_Traceguids);
      }
      v8 = -1073741670;
      goto LABEL_32;
    }
    v8 = swprintf_s(v14, v13 >> 1, L"%s\\%s", Pool2, a3);
    if ( v8 >= 0 )
    {
      *a5 = v10;
      v10 = 0;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v12 = 14;
        goto LABEL_30;
      }
    }
  }
  else
  {
    v10 = 0;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v12 = 12;
LABEL_30:
      WPP_SF_(v11->AttachedDevice, v12, WPP_8c8e2bcf66043dde3d33f256d9bd74b7_Traceguids);
    }
  }
LABEL_32:
  ExFreePoolWithTag(Pool2, 0);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002239c  mov     r11, rsp
0x14002239f  mov     [r11+10h], rdx
0x1400223a3  push    rbx
0x1400223a4  push    rbp
0x1400223a5  push    rsi
0x1400223a6  push    rdi
0x1400223a7  sub     rsp, 48h
0x1400223ab  lea     rax, [r11+10h]
0x1400223af  mov     [rsp+68h+arg_8], 0
0x1400223b7  mov     [r11-38h], rax
0x1400223bb  lea     rcx, aUsbstor_1; "USBStor"
0x1400223c2  mov     edi, r9d
0x1400223c5  mov     [rsp+68h+var_40], 0
0x1400223cd  mov     rbp, r8
0x1400223d0  mov     qword ptr [r11-48h], 0
0x1400223d8  xor     r9d, r9d
0x1400223db  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400223e2  xor     edx, edx
0x1400223e4  call    cs:__imp_RtlGetPersistedStateLocation
0x1400223eb  nop     dword ptr [rax+rax+00h]
0x1400223f0  mov     ebx, eax
0x1400223f2  test    eax, eax
0x1400223f4  js      short loc_140022435
0x1400223f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400223fd  lea     rax, WPP_GLOBAL_Control
0x140022404  cmp     rcx, rax
0x140022407  jz      short loc_14002242B
0x140022409  mov     eax, [rcx+2Ch]
0x14002240c  test    al, 2
0x14002240e  jz      short loc_14002242B
0x140022410  cmp     byte ptr [rcx+29h], 2
0x140022414  jb      short loc_14002242B
0x140022416  mov     rcx, [rcx+18h]
0x14002241a  lea     r8, WPP_8c8e2bcf66043dde3d33f256d9bd74b7_Traceguids
0x140022421  mov     edx, 0Ah
0x140022426  call    WPP_SF_
0x14002242b  mov     ebx, 0C0000001h
0x140022430  jmp     loc_14002260C
0x140022435  cmp     eax, 80000005h
0x14002243a  jnz     loc_14002260C
0x140022440  mov     edx, [rsp+68h+arg_8]
0x140022444  mov     ecx, 100h
0x140022449  mov     r8d, 53414D55h
0x14002244f  call    cs:__imp_ExAllocatePool2
0x140022456  nop     dword ptr [rax+rax+00h]
0x14002245b  mov     rsi, rax
0x14002245e  test    rax, rax
0x140022461  jnz     short loc_1400224A0
0x140022463  mov     rcx, cs:WPP_GLOBAL_Control
0x14002246a  lea     rax, WPP_GLOBAL_Control
0x140022471  cmp     rcx, rax
0x140022474  jz      short loc_140022496
0x140022476  mov     eax, [rcx+2Ch]
0x140022479  test    al, 1
0x14002247b  jz      short loc_140022496
0x14002247d  cmp     byte ptr [rcx+29h], 2
0x140022481  jb      short loc_140022496
0x140022483  mov     rcx, [rcx+18h]
0x140022487  lea     edx, [rsi+0Bh]
0x14002248a  lea     r8, WPP_8c8e2bcf66043dde3d33f256d9bd74b7_Traceguids
0x140022491  call    WPP_SF_
0x140022496  mov     ebx, 0C000009Ah
0x14002249b  jmp     loc_14002260C
0x1400224a0  mov     eax, [rsp+68h+arg_8]
0x1400224a4  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400224ab  mov     [rsp+68h+var_38], 0
0x1400224b4  lea     rcx, aUsbstor_1; "USBStor"
0x1400224bb  mov     [rsp+68h+var_40], eax
0x1400224bf  xor     r9d, r9d
0x1400224c2  xor     edx, edx
0x1400224c4  mov     [rsp+68h+var_48], rsi
0x1400224c9  call    cs:__imp_RtlGetPersistedStateLocation
0x1400224d0  nop     dword ptr [rax+rax+00h]
0x1400224d5  mov     ebx, eax
0x1400224d7  test    eax, eax
0x1400224d9  jns     short loc_140022512
0x1400224db  xor     edi, edi
0x1400224dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400224e4  lea     rax, WPP_GLOBAL_Control
0x1400224eb  cmp     rcx, rax
0x1400224ee  jz      loc_1400225E5
0x1400224f4  mov     edx, [rcx+2Ch]
0x1400224f7  test    dl, 1
0x1400224fa  jz      loc_1400225E5
0x140022500  cmp     byte ptr [rcx+29h], 2
0x140022504  jb      loc_1400225E5
0x14002250a  lea     edx, [rdi+0Ch]
0x14002250d  jmp     loc_1400225C6
0x140022512  mov     edx, [rsp+68h+arg_8]
0x140022516  mov     ecx, 100h
0x14002251b  add     edx, 2
0x14002251e  mov     r8d, 53414D55h
0x140022524  add     edx, edi
0x140022526  mov     ebx, edx
0x140022528  call    cs:__imp_ExAllocatePool2
0x14002252f  nop     dword ptr [rax+rax+00h]
0x140022534  mov     rdi, rax
0x140022537  test    rax, rax
0x14002253a  jnz     short loc_140022577
0x14002253c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022543  lea     rax, WPP_GLOBAL_Control
0x14002254a  cmp     rcx, rax
0x14002254d  jz      short loc_140022570
0x14002254f  mov     edx, [rcx+2Ch]
0x140022552  test    dl, 1
0x140022555  jz      short loc_140022570
0x140022557  cmp     byte ptr [rcx+29h], 2
0x14002255b  jb      short loc_140022570
0x14002255d  mov     rcx, [rcx+18h]
0x140022561  lea     edx, [rdi+0Dh]
0x140022564  lea     r8, WPP_8c8e2bcf66043dde3d33f256d9bd74b7_Traceguids
0x14002256b  call    WPP_SF_
0x140022570  mov     ebx, 0C000009Ah
0x140022575  jmp     short loc_1400225E5
0x140022577  shr     rbx, 1
0x14002257a  lea     r8, aSS; "%s\\%s"
0x140022581  mov     rdx, rbx; SizeInWords
0x140022584  mov     [rsp+68h+var_48], rbp
0x140022589  mov     r9, rsi
0x14002258c  mov     rcx, rdi; Dst
0x14002258f  call    cs:__imp_swprintf_s
0x140022596  nop     dword ptr [rax+rax+00h]
0x14002259b  mov     ebx, eax
0x14002259d  test    eax, eax
0x14002259f  jns     short loc_1400225D8
0x1400225a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400225a8  lea     rax, WPP_GLOBAL_Control
0x1400225af  cmp     rcx, rax
0x1400225b2  jz      short loc_1400225E5
0x1400225b4  mov     eax, [rcx+2Ch]
0x1400225b7  test    al, 1
0x1400225b9  jz      short loc_1400225E5
0x1400225bb  cmp     byte ptr [rcx+29h], 2
0x1400225bf  jb      short loc_1400225E5
0x1400225c1  mov     edx, 0Eh
0x1400225c6  mov     rcx, [rcx+18h]
0x1400225ca  lea     r8, WPP_8c8e2bcf66043dde3d33f256d9bd74b7_Traceguids
0x1400225d1  call    WPP_SF_
0x1400225d6  jmp     short loc_1400225E5
0x1400225d8  mov     rax, [rsp+68h+arg_20]
0x1400225e0  mov     [rax], rdi
0x1400225e3  xor     edi, edi
0x1400225e5  xor     edx, edx; Tag
0x1400225e7  mov     rcx, rsi; P
0x1400225ea  call    cs:__imp_ExFreePoolWithTag
0x1400225f1  nop     dword ptr [rax+rax+00h]
0x1400225f6  test    rdi, rdi
0x1400225f9  jz      short loc_14002260C
0x1400225fb  xor     edx, edx; Tag
0x1400225fd  mov     rcx, rdi; P
0x140022600  call    cs:__imp_ExFreePoolWithTag
0x140022607  nop     dword ptr [rax+rax+00h]
0x14002260c  mov     eax, ebx
0x14002260e  add     rsp, 48h
0x140022612  pop     rdi
0x140022613  pop     rsi
0x140022614  pop     rbp
0x140022615  pop     rbx
0x140022616  retn
```
