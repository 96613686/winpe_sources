# CheckForButton(RADIO_FEATURE_TYPE,ushort,_HIDP_PREPARSED_DATA *)

- ea: `0x180007720`
- end: `0x1800078fb`
- name: `?CheckForButton@@YAGW4RADIO_FEATURE_TYPE@@GPEAU_HIDP_PREPARSED_DATA@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(unsigned int, __int64, struct _HIDP_PREPARSED_DATA *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180003920`

## callees

- `0x180003d50`
- `0x180004910`
- `0x180007720`
- `0x1800089f4`
- `0x18000d2a0`
- `0x18000df4c`
- `0x180024fdc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800077bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800077bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078cd`
- `HID!HidP_GetSpecificButtonCaps` at `0x18000783f`
- `HID!HidP_GetSpecificButtonCaps` at `0x18000783f`

## pseudocode

```c
__int64 __fastcall CheckForButton(unsigned int a1, __int64 a2, struct _HIDP_PREPARSED_DATA *a3)
{
  __int64 v3; // rbp
  struct _HIDP_BUTTON_CAPS *ButtonCaps; // rbx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  USAGE v9; // di
  HIDP_REPORT_TYPE v10; // esi
  struct _HIDP_BUTTON_CAPS *v11; // rax
  __int64 v12; // r8
  NTSTATUS SpecificButtonCaps; // eax
  __int64 v14; // rcx
  USHORT v15; // di
  SIZE_T cb; // [rsp+40h] [rbp-58h] BYREF
  USHORT ButtonCapsLength; // [rsp+48h] [rbp-50h] BYREF

  v3 = (unsigned __int16)a2;
  ButtonCapsLength = a2;
  ButtonCaps = 0;
  if ( !(_WORD)a2 )
    goto LABEL_22;
  v7 = a1 - 2;
  if ( !v7 )
    goto LABEL_7;
  v8 = v7 - 1;
  if ( v8 )
  {
    if ( v8 == 1 )
    {
      v9 = 200;
LABEL_8:
      v10 = HidP_Input;
      goto LABEL_9;
    }
LABEL_7:
    v9 = 198;
    goto LABEL_8;
  }
  v9 = 199;
  v10 = HidP_Output;
LABEL_9:
  cb = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(&cb, (unsigned __int16)a2, 72) >= 0 && cb <= 0x7FFFFFFF )
  {
    v11 = (struct _HIDP_BUTTON_CAPS *)CoTaskMemAlloc((unsigned int)cb);
    ButtonCaps = v11;
    if ( v11 )
    {
      memset_0(v11, 0, 72 * v3);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
      {
        WPP_SF_DDDd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), WPP_GLOBAL_Control, v12, (unsigned int)v10);
      }
      SpecificButtonCaps = HidP_GetSpecificButtonCaps(v10, 1u, 0, v9, ButtonCaps, &ButtonCapsLength, a3);
      v14 = WPP_GLOBAL_Control;
      if ( SpecificButtonCaps != 1114112 )
        ButtonCapsLength = 0;
      goto LABEL_23;
    }
  }
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_27;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 67, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
LABEL_22:
    v14 = WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 && *(_BYTE *)(v14 + 25) >= 4u )
    WPP_SF_dd(*(_QWORD *)(v14 + 16), a2, a3, a1, ButtonCapsLength);
LABEL_27:
  v15 = ButtonCapsLength;
  CoTaskMemFree(ButtonCaps);
  return v15;
}

```

## disassembly

```asm
0x180007720  mov     [rsp+arg_18], rbx
0x180007725  push    rbp
0x180007726  push    rsi
0x180007727  push    rdi
0x180007728  push    r12
0x18000772a  push    r13
0x18000772c  push    r14
0x18000772e  push    r15
0x180007730  sub     rsp, 60h
0x180007734  mov     rax, cs:__security_cookie
0x18000773b  xor     rax, rsp
0x18000773e  mov     [rsp+98h+var_48], rax
0x180007743  movzx   ebp, dx
0x180007746  xor     r13d, r13d
0x180007749  mov     [rsp+98h+var_50], bp
0x18000774e  mov     r12, r8
0x180007751  mov     r14d, ecx
0x180007754  mov     ebx, r13d
0x180007757  test    bp, bp
0x18000775a  jz      loc_180007891
0x180007760  sub     ecx, 2
0x180007763  jz      short loc_180007782
0x180007765  sub     ecx, 1
0x180007768  jz      short loc_180007776
0x18000776a  cmp     ecx, 1
0x18000776d  jnz     short loc_180007782
0x18000776f  mov     edi, 0C8h
0x180007774  jmp     short loc_180007787
0x180007776  mov     edi, 0C7h
0x18000777b  mov     esi, 1
0x180007780  jmp     short loc_18000778A
0x180007782  mov     edi, 0C6h
0x180007787  mov     esi, r13d
0x18000778a  mov     r8d, 48h ; 'H'
0x180007790  mov     [rsp+98h+cb], r13
0x180007795  mov     rdx, rbp
0x180007798  lea     rcx, [rsp+98h+cb]
0x18000779d  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x1800077a2  test    eax, eax
0x1800077a4  js      loc_18000785B
0x1800077aa  cmp     [rsp+98h+cb], 7FFFFFFFh
0x1800077b3  ja      loc_18000785B
0x1800077b9  mov     ecx, dword ptr [rsp+98h+cb]; cb
0x1800077bd  call    cs:__imp_CoTaskMemAlloc
0x1800077c3  mov     rbx, rax
0x1800077c6  test    rax, rax
0x1800077c9  jz      loc_18000785B
0x1800077cf  lea     r8, ds:0[rbp*8]
0x1800077d7  xor     edx, edx; Val
0x1800077d9  add     r8, rbp
0x1800077dc  mov     rcx, rax; void *
0x1800077df  shl     r8, 3; Size
0x1800077e3  call    memset_0
0x1800077e8  mov     rdx, cs:WPP_GLOBAL_Control
0x1800077ef  lea     r15, WPP_GLOBAL_Control
0x1800077f6  cmp     rdx, r15
0x1800077f9  jz      short loc_18000781E
0x1800077fb  test    byte ptr [rdx+1Ch], 1
0x1800077ff  jz      short loc_18000781E
0x180007801  cmp     byte ptr [rdx+19h], 4
0x180007805  jb      short loc_18000781E
0x180007807  movzx   ecx, di
0x18000780a  mov     r9d, esi
0x18000780d  mov     dword ptr [rsp+98h+PreparsedData], ebp
0x180007811  mov     dword ptr [rsp+98h+ButtonCapsLength], ecx
0x180007815  mov     rcx, [rdx+10h]
0x180007819  call    WPP_SF_DDDd
0x18000781e  xor     r8d, r8d; LinkCollection
0x180007821  mov     [rsp+98h+PreparsedData], r12; PreparsedData
0x180007826  lea     rax, [rsp+98h+var_50]
0x18000782b  movzx   r9d, di; Usage
0x18000782f  mov     [rsp+98h+ButtonCapsLength], rax; ButtonCapsLength
0x180007834  mov     ecx, esi; ReportType
0x180007836  mov     [rsp+98h+ButtonCaps], rbx; ButtonCaps
0x18000783b  lea     edx, [r8+1]; UsagePage
0x18000783f  call    cs:__imp_HidP_GetSpecificButtonCaps
0x180007845  mov     rcx, cs:WPP_GLOBAL_Control
0x18000784c  cmp     eax, 110000h
0x180007851  jz      short loc_18000789F
0x180007853  mov     [rsp+98h+var_50], r13w
0x180007859  jmp     short loc_18000789F
0x18000785b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007862  lea     r15, WPP_GLOBAL_Control
0x180007869  cmp     rcx, r15
0x18000786c  jz      short loc_1800078C5
0x18000786e  test    byte ptr [rcx+1Ch], 1
0x180007872  jz      short loc_18000789F
0x180007874  cmp     byte ptr [rcx+19h], 2
0x180007878  jb      short loc_18000789F
0x18000787a  mov     rcx, [rcx+10h]
0x18000787e  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180007885  mov     edx, 43h ; 'C'
0x18000788a  call    WPP_SF_
0x18000788f  jmp     short loc_180007898
0x180007891  lea     r15, WPP_GLOBAL_Control
0x180007898  mov     rcx, cs:WPP_GLOBAL_Control
0x18000789f  cmp     rcx, r15
0x1800078a2  jz      short loc_1800078C5
0x1800078a4  test    byte ptr [rcx+1Ch], 1
0x1800078a8  jz      short loc_1800078C5
0x1800078aa  cmp     byte ptr [rcx+19h], 4
0x1800078ae  jb      short loc_1800078C5
0x1800078b0  movzx   eax, [rsp+98h+var_50]
0x1800078b5  mov     r9d, r14d
0x1800078b8  mov     rcx, [rcx+10h]
0x1800078bc  mov     dword ptr [rsp+98h+ButtonCaps], eax
0x1800078c0  call    WPP_SF_dd
0x1800078c5  movzx   edi, [rsp+98h+var_50]
0x1800078ca  mov     rcx, rbx; pv
0x1800078cd  call    cs:__imp_CoTaskMemFree
0x1800078d3  movzx   eax, di
0x1800078d6  mov     rcx, [rsp+98h+var_48]
0x1800078db  xor     rcx, rsp; StackCookie
0x1800078de  call    __security_check_cookie
0x1800078e3  mov     rbx, [rsp+98h+arg_18]
0x1800078eb  add     rsp, 60h
0x1800078ef  pop     r15
0x1800078f1  pop     r14
0x1800078f3  pop     r13
0x1800078f5  pop     r12
0x1800078f7  pop     rdi
0x1800078f8  pop     rsi
0x1800078f9  pop     rbp
0x1800078fa  retn
```
