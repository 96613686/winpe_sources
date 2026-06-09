# CheckIfDeviceHasRadioFeature

- ea: `0x180003920`
- end: `0x180003c5b`
- name: `CheckIfDeviceHasRadioFeature`
- size: `827`
- prototype: `char __fastcall(const WCHAR *, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x1800035b0`

## callees

- `0x180002ec0`
- `0x180003920`
- `0x180003c70`
- `0x180003d50`
- `0x180007720`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003b92`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003b92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a6f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000398e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000398e`
- `HID!HidD_FreePreparsedData` at `0x1800039fd`
- `HID!HidD_FreePreparsedData` at `0x1800039fd`
- `HID!HidD_GetPreparsedData` at `0x1800039a8`
- `HID!HidD_GetPreparsedData` at `0x1800039a8`
- `HID!HidP_GetCaps` at `0x1800039be`
- `HID!HidP_GetCaps` at `0x1800039be`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CheckIfDeviceHasRadioFeature(const WCHAR *a1, int a2, __int64 a3)
{
  unsigned int v3; // esi
  char *FileW; // rax
  char *v8; // rbx
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // r12d
  int v13; // r12d
  int v14; // r12d
  __int128 v15; // xmm1
  PHIDP_PREPARSED_DATA v16; // rcx
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int64 NumberOutputButtonCaps; // rdx
  PHIDP_PREPARSED_DATA PreparsedData; // [rsp+40h] [rbp-39h] BYREF
  _HIDP_CAPS Capabilities; // [rsp+50h] [rbp-29h] BYREF

  v3 = 3;
  PreparsedData = 0;
  memset(&Capabilities, 0, sizeof(Capabilities));
  FileW = (char *)CreateFileW(a1, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  v8 = FileW;
  if ( FileW == (char *)-1LL )
  {
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_7;
    }
    v11 = 75;
LABEL_16:
    WPP_SF_(*(_QWORD *)(v10 + 16), v11, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
    goto LABEL_7;
  }
  if ( !HidD_GetPreparsedData(FileW, &PreparsedData) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_7;
    }
    v11 = 74;
    goto LABEL_16;
  }
  if ( !HidP_GetCaps(PreparsedData, &Capabilities) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_7;
    }
    v11 = 73;
    goto LABEL_16;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    WPP_SF_Dd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      69,
      &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids,
      Capabilities.UsagePage,
      Capabilities.Usage);
  }
  if ( Capabilities.UsagePage != 1 || Capabilities.Usage != 12 )
    goto LABEL_7;
  v12 = a2 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( !v13 )
    {
      v3 = 2;
      goto LABEL_36;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      NumberOutputButtonCaps = Capabilities.NumberOutputButtonCaps;
      goto LABEL_29;
    }
    if ( v14 == 1 )
    {
      v3 = 4;
LABEL_36:
      NumberOutputButtonCaps = Capabilities.NumberInputButtonCaps;
LABEL_29:
      if ( !(unsigned __int16)CheckForButton(v3, NumberOutputButtonCaps, PreparsedData) )
        v3 = 0;
      if ( v3 )
        goto LABEL_32;
      goto LABEL_7;
    }
  }
  v3 = 2;
  if ( (unsigned __int16)CheckForButton(2u, Capabilities.NumberInputButtonCaps, PreparsedData)
    || (v3 = 4, (unsigned __int16)CheckForButton(4u, Capabilities.NumberInputButtonCaps, PreparsedData)) )
  {
LABEL_32:
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 76, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids, v3);
    }
    v15 = *(_OWORD *)&Capabilities.Reserved[3];
    v16 = PreparsedData;
    *(_OWORD *)(a3 + 536) = *(_OWORD *)&Capabilities.Usage;
    *(_QWORD *)(a3 + 528) = v16;
    v17 = *(_OWORD *)&Capabilities.Reserved[11];
    *(_OWORD *)(a3 + 552) = v15;
    *(_DWORD *)(a3 + 600) = v3;
    v18 = *(_OWORD *)&Capabilities.NumberInputValueCaps;
    *(_OWORD *)(a3 + 568) = v17;
    *(_QWORD *)a3 = v8;
    *(_OWORD *)(a3 + 584) = v18;
    _o_wcscpy_s(a3 + 8, 260, a1);
    return 1;
  }
LABEL_7:
  if ( PreparsedData )
    HidD_FreePreparsedData(PreparsedData);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return 0;
}

```

## disassembly

```asm
0x180003920  mov     [rsp-8+arg_8], rbx
0x180003925  push    rbp
0x180003926  push    rsi
0x180003927  push    rdi
0x180003928  push    r12
0x18000392a  push    r13
0x18000392c  push    r14
0x18000392e  push    r15
0x180003930  lea     rbp, [rsp-27h]
0x180003935  sub     rsp, 0A0h
0x18000393c  mov     rax, cs:__security_cookie
0x180003943  xor     rax, rsp
0x180003946  mov     [rbp+57h+var_40], rax
0x18000394a  xorps   xmm0, xmm0
0x18000394d  xor     r13d, r13d
0x180003950  mov     esi, 3
0x180003955  mov     [rsp+0D0h+hTemplateFile], r13; hTemplateFile
0x18000395a  mov     r15, r8
0x18000395d  mov     [rsp+0D0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180003965  mov     r12d, edx
0x180003968  mov     [rsp+0D0h+dwCreationDisposition], esi; dwCreationDisposition
0x18000396c  xor     r9d, r9d; lpSecurityAttributes
0x18000396f  mov     [rbp+57h+PreparsedData], r13
0x180003973  mov     r8d, esi; dwShareMode
0x180003976  mov     edx, 0C0000000h; dwDesiredAccess
0x18000397b  mov     r14, rcx
0x18000397e  movups  xmmword ptr [rbp+57h+Capabilities.Usage], xmm0
0x180003982  movups  xmmword ptr [rbp+57h+Capabilities.Reserved+6], xmm0
0x180003986  movups  xmmword ptr [rbp+57h+Capabilities.Reserved+16h], xmm0
0x18000398a  movups  xmmword ptr [rbp+57h+Capabilities.NumberInputValueCaps], xmm0
0x18000398e  call    cs:__imp_CreateFileW
0x180003994  mov     rbx, rax
0x180003997  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000399b  jz      loc_180003A36
0x1800039a1  lea     rdx, [rbp+57h+PreparsedData]; PreparsedData
0x1800039a5  mov     rcx, rax; HidDeviceObject
0x1800039a8  call    cs:__imp_HidD_GetPreparsedData
0x1800039ae  test    al, al
0x1800039b0  jz      loc_180003AA8
0x1800039b6  mov     rcx, [rbp+57h+PreparsedData]; PreparsedData
0x1800039ba  lea     rdx, [rbp+57h+Capabilities]; Capabilities
0x1800039be  call    cs:__imp_HidP_GetCaps
0x1800039c4  test    eax, eax
0x1800039c6  jz      loc_180003C26
0x1800039cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039d3  lea     rdi, WPP_GLOBAL_Control
0x1800039da  cmp     rcx, rdi
0x1800039dd  jz      short loc_1800039E9
0x1800039df  test    byte ptr [rcx+1Ch], 1
0x1800039e3  jnz     loc_180003A77
0x1800039e9  cmp     [rbp+57h+Capabilities.UsagePage], 1
0x1800039ee  jz      loc_180003ADA
0x1800039f4  mov     rcx, [rbp+57h+PreparsedData]; PreparsedData
0x1800039f8  test    rcx, rcx
0x1800039fb  jz      short loc_180003A03
0x1800039fd  call    cs:__imp_HidD_FreePreparsedData
0x180003a03  lea     rcx, [rbx-1]
0x180003a07  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180003a0b  jbe     short loc_180003A6C
0x180003a0d  xor     al, al
0x180003a0f  mov     rcx, [rbp+57h+var_40]
0x180003a13  xor     rcx, rsp; StackCookie
0x180003a16  call    __security_check_cookie
0x180003a1b  mov     rbx, [rsp+0D0h+arg_8]
0x180003a23  add     rsp, 0A0h
0x180003a2a  pop     r15
0x180003a2c  pop     r14
0x180003a2e  pop     r13
0x180003a30  pop     r12
0x180003a32  pop     rdi
0x180003a33  pop     rsi
0x180003a34  pop     rbp
0x180003a35  retn
0x180003a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a3d  lea     rdi, WPP_GLOBAL_Control
0x180003a44  cmp     rcx, rdi
0x180003a47  jz      short loc_1800039F4
0x180003a49  test    byte ptr [rcx+1Ch], 1
0x180003a4d  jz      short loc_1800039F4
0x180003a4f  cmp     byte ptr [rcx+19h], 2
0x180003a53  jb      short loc_1800039F4
0x180003a55  mov     edx, 4Bh ; 'K'
0x180003a5a  mov     rcx, [rcx+10h]
0x180003a5e  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180003a65  call    WPP_SF_
0x180003a6a  jmp     short loc_1800039F4
0x180003a6c  mov     rcx, rbx; hObject
0x180003a6f  call    cs:__imp_CloseHandle
0x180003a75  jmp     short loc_180003A0D
0x180003a77  cmp     byte ptr [rcx+19h], 4
0x180003a7b  jb      loc_1800039E9
0x180003a81  movzx   eax, [rbp+57h+Capabilities.Usage]
0x180003a85  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180003a8c  movzx   r9d, [rbp+57h+Capabilities.UsagePage]
0x180003a91  mov     edx, 45h ; 'E'
0x180003a96  mov     rcx, [rcx+10h]
0x180003a9a  mov     [rsp+0D0h+dwCreationDisposition], eax
0x180003a9e  call    WPP_SF_Dd
0x180003aa3  jmp     loc_1800039E9
0x180003aa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003aaf  lea     rdi, WPP_GLOBAL_Control
0x180003ab6  cmp     rcx, rdi
0x180003ab9  jz      loc_1800039F4
0x180003abf  test    byte ptr [rcx+1Ch], 1
0x180003ac3  jz      loc_1800039F4
0x180003ac9  cmp     byte ptr [rcx+19h], 2
0x180003acd  jb      loc_1800039F4
0x180003ad3  mov     edx, 4Ah ; 'J'
0x180003ad8  jmp     short loc_180003A5A
0x180003ada  cmp     [rbp+57h+Capabilities.Usage], 0Ch
0x180003adf  jnz     loc_1800039F4
0x180003ae5  sub     r12d, 1
0x180003ae9  jz      loc_180003BB6
0x180003aef  sub     r12d, 1
0x180003af3  jz      loc_180003BA8
0x180003af9  sub     r12d, 1
0x180003afd  jz      loc_180003B9F
0x180003b03  cmp     r12d, 1
0x180003b07  jnz     loc_180003BB6
0x180003b0d  mov     esi, 4
0x180003b12  jmp     loc_180003BAD
0x180003b17  mov     r8, [rbp+57h+PreparsedData]
0x180003b1b  mov     ecx, esi
0x180003b1d  call    ?CheckForButton@@YAGW4RADIO_FEATURE_TYPE@@GPEAU_HIDP_PREPARSED_DATA@@@Z; CheckForButton(RADIO_FEATURE_TYPE,ushort,_HIDP_PREPARSED_DATA *)
0x180003b22  test    ax, ax
0x180003b25  cmovz   esi, r13d
0x180003b29  test    esi, esi
0x180003b2b  jz      loc_1800039F4
0x180003b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b38  cmp     rcx, rdi
0x180003b3b  jnz     loc_180003BF5
0x180003b41  movaps  xmm0, xmmword ptr [rbp+57h+Capabilities.Usage]
0x180003b45  mov     r8, r14
0x180003b48  movaps  xmm1, xmmword ptr [rbp+57h+Capabilities.Reserved+6]
0x180003b4c  mov     edx, 104h
0x180003b51  mov     rcx, [rbp+57h+PreparsedData]
0x180003b55  movups  xmmword ptr [r15+218h], xmm0
0x180003b5d  mov     [r15+210h], rcx
0x180003b64  lea     rcx, [r15+8]
0x180003b68  movaps  xmm0, xmmword ptr [rbp+57h+Capabilities.Reserved+16h]
0x180003b6c  movups  xmmword ptr [r15+228h], xmm1
0x180003b74  mov     [r15+258h], esi
0x180003b7b  movaps  xmm1, xmmword ptr [rbp+57h+Capabilities.NumberInputValueCaps]
0x180003b7f  movups  xmmword ptr [r15+238h], xmm0
0x180003b87  mov     [r15], rbx
0x180003b8a  movups  xmmword ptr [r15+248h], xmm1
0x180003b92  call    cs:__imp__o_wcscpy_s
0x180003b98  mov     al, 1
0x180003b9a  jmp     loc_180003A0F
0x180003b9f  movzx   edx, [rbp+57h+Capabilities.NumberOutputButtonCaps]
0x180003ba3  jmp     loc_180003B17
0x180003ba8  mov     esi, 2
0x180003bad  movzx   edx, [rbp+57h+Capabilities.NumberInputButtonCaps]
0x180003bb1  jmp     loc_180003B17
0x180003bb6  mov     r8, [rbp+57h+PreparsedData]
0x180003bba  mov     esi, 2
0x180003bbf  movzx   edx, [rbp+57h+Capabilities.NumberInputButtonCaps]
0x180003bc3  mov     ecx, esi
0x180003bc5  call    ?CheckForButton@@YAGW4RADIO_FEATURE_TYPE@@GPEAU_HIDP_PREPARSED_DATA@@@Z; CheckForButton(RADIO_FEATURE_TYPE,ushort,_HIDP_PREPARSED_DATA *)
0x180003bca  test    ax, ax
0x180003bcd  jnz     loc_180003B31
0x180003bd3  mov     r8, [rbp+57h+PreparsedData]
0x180003bd7  mov     esi, 4
0x180003bdc  movzx   edx, [rbp+57h+Capabilities.NumberInputButtonCaps]
0x180003be0  mov     ecx, esi
0x180003be2  call    ?CheckForButton@@YAGW4RADIO_FEATURE_TYPE@@GPEAU_HIDP_PREPARSED_DATA@@@Z; CheckForButton(RADIO_FEATURE_TYPE,ushort,_HIDP_PREPARSED_DATA *)
0x180003be7  test    ax, ax
0x180003bea  jz      loc_1800039F4
0x180003bf0  jmp     loc_180003B31
0x180003bf5  test    byte ptr [rcx+1Ch], 1
0x180003bf9  jz      loc_180003B41
0x180003bff  cmp     byte ptr [rcx+19h], 4
0x180003c03  jb      loc_180003B41
0x180003c09  mov     rcx, [rcx+10h]
0x180003c0d  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180003c14  mov     edx, 4Ch ; 'L'
0x180003c19  mov     r9d, esi
0x180003c1c  call    WPP_SF_d
0x180003c21  jmp     loc_180003B41
0x180003c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c2d  lea     rdi, WPP_GLOBAL_Control
0x180003c34  cmp     rcx, rdi
0x180003c37  jz      loc_1800039F4
0x180003c3d  test    byte ptr [rcx+1Ch], 1
0x180003c41  jz      loc_1800039F4
0x180003c47  cmp     byte ptr [rcx+19h], 2
0x180003c4b  jb      loc_1800039F4
0x180003c51  mov     edx, 49h ; 'I'
0x180003c56  jmp     loc_180003A5A
```
