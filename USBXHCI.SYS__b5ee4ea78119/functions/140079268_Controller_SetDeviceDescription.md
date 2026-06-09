# Controller_SetDeviceDescription

- ea: `0x140079268`
- end: `0x140079889`
- name: `Controller_SetDeviceDescription`
- size: `1569`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400444c0`

## callees

- `0x14001ac48`
- `0x14001ad0c`
- `0x140045064`
- `0x140045178`
- `0x14004a204`
- `0x140059970`
- `0x1400599b0`
- `0x140077290`
- `0x140079268`

## import_xrefs

- `ntoskrnl!RtlFindMessage` at `0x14007938c`
- `ntoskrnl!RtlFindMessage` at `0x140079606`
- `ntoskrnl!RtlFindMessage` at `0x14007938c`
- `ntoskrnl!RtlFindMessage` at `0x140079606`
- `ntoskrnl!wcsncpy_s` at `0x1400794b8`
- `ntoskrnl!wcsncpy_s` at `0x14007977f`
- `ntoskrnl!wcsncpy_s` at `0x1400794b8`
- `ntoskrnl!wcsncpy_s` at `0x14007977f`
- `ntoskrnl!IoSetDevicePropertyData` at `0x140079846`
- `ntoskrnl!IoSetDevicePropertyData` at `0x140079846`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079560`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007973c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079759`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079560`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007973c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079759`
- `ntoskrnl!ExAllocatePool2` at `0x14007946e`
- `ntoskrnl!ExAllocatePool2` at `0x14007950b`
- `ntoskrnl!ExAllocatePool2` at `0x140079680`
- `ntoskrnl!ExAllocatePool2` at `0x1400796fa`
- `ntoskrnl!ExAllocatePool2` at `0x14007946e`
- `ntoskrnl!ExAllocatePool2` at `0x14007950b`
- `ntoskrnl!ExAllocatePool2` at `0x140079680`
- `ntoskrnl!ExAllocatePool2` at `0x1400796fa`
- `ntoskrnl!_stricmp` at `0x14007934a`
- `ntoskrnl!_stricmp` at `0x14007934a`

## string_xrefs

- `0x14007928f`: `@System32\drivers\usbxhci.sys`

## pseudocode

```c
void __fastcall Controller_SetDeviceDescription(__int64 a1)
{
  __int64 v2; // rcx
  wchar_t *v3; // r13
  __int16 HighestUsbVersionSupported; // ax
  unsigned __int8 v5; // bl
  unsigned int i; // ecx
  unsigned int j; // r14d
  size_t v8; // rdx
  int v9; // r9d
  int v10; // edx
  size_t v11; // rcx
  BYTE *Text; // r12
  size_t v13; // rax
  rsize_t v14; // r14
  size_t v15; // rdi
  wchar_t *Pool2; // rax
  BYTE *v17; // r12
  __int64 v18; // rax
  size_t v19; // rdx
  void *v20; // r13
  int v21; // r9d
  BYTE *v22; // rbx
  wchar_t *v23; // rax
  int v24; // edx
  struct _DEVICE_OBJECT *v25; // rax
  NTSTATUS v26; // eax
  int v27; // edx
  PMESSAGE_RESOURCE_ENTRY *MessageResourceEntry; // [rsp+20h] [rbp-A9h]
  PVOID Data; // [rsp+30h] [rbp-99h]
  int v30; // [rsp+38h] [rbp-91h]
  int v31; // [rsp+40h] [rbp-89h]
  int v32; // [rsp+48h] [rbp-81h]
  int v33; // [rsp+50h] [rbp-79h]
  BYTE *P; // [rsp+60h] [rbp-69h]
  unsigned __int8 v35; // [rsp+69h] [rbp-60h]
  size_t pcbLength; // [rsp+70h] [rbp-59h] BYREF
  size_t v37; // [rsp+78h] [rbp-51h] BYREF
  PMESSAGE_RESOURCE_ENTRY v38; // [rsp+80h] [rbp-49h] BYREF
  PMESSAGE_RESOURCE_ENTRY v39; // [rsp+88h] [rbp-41h] BYREF
  rsize_t MaxCount; // [rsp+90h] [rbp-39h]
  _OWORD v41[2]; // [rsp+98h] [rbp-31h] BYREF
  _OWORD v42[2]; // [rsp+B8h] [rbp-11h]

  v38 = 0;
  v41[0] = *(_OWORD *)L"@System32\\drivers\\usbxhci.sys";
  v39 = 0;
  v41[1] = *(_OWORD *)L"2\\drivers\\usbxhci.sys";
  v42[0] = *(_OWORD *)L"s\\usbxhci.sys";
  *(_OWORD *)((char *)v42 + 12) = *(_OWORD *)L"hci.sys";
  if ( !(unsigned __int8)Controller_DriverInstalledDueToCompatibleIdMatch() )
    return;
  v2 = *(_QWORD *)(a1 + 152);
  v3 = 0;
  v37 = 0;
  HighestUsbVersionSupported = RootHub_GetHighestUsbVersionSupported(v2);
  v5 = HighestUsbVersionSupported;
  v35 = HIBYTE(HighestUsbVersionSupported);
  if ( *(_DWORD *)(a1 + 644) == 1 )
  {
    for ( i = 0; i < 0xB; ++i )
    {
      if ( PciVendorIdTable[8 * i] == *(_WORD *)(a1 + 648) )
      {
        v3 = (&off_14006C448)[2 * i];
        goto LABEL_13;
      }
    }
  }
  else
  {
    for ( j = 0; j < 5; ++j )
    {
      if ( !_stricmp((&AcpiVendorIdTable)[2 * j], (const char *)(a1 + 704)) )
      {
        v3 = (&off_14006C3F8)[2 * j];
LABEL_13:
        v37 = (size_t)v3;
        break;
      }
    }
  }
  if ( RtlFindMessage(
         *(PVOID *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 24LL),
         0xBu,
         0,
         0x40010001u,
         &v38) < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 150;
LABEL_17:
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), v8, 4, v9, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
      return;
    }
    return;
  }
  v8 = v38->Length - 4LL;
  pcbLength = v8;
  if ( v8 <= 0xFFFFFFFE )
  {
    if ( RtlUnalignedStringCbLengthW((STRSAFE_PCUNZWCH)v38->Text, v8, &pcbLength) < 0 )
      return;
    v11 = pcbLength;
    Text = v38->Text;
    P = v38->Text;
    if ( pcbLength >= 4 )
    {
      v13 = pcbLength >> 1;
      if ( *(_WORD *)&Text[2 * (pcbLength >> 1) - 2] == 10 )
      {
        v14 = v13 - 2;
        if ( *(_WORD *)&Text[2 * v13 - 4] == 13 )
        {
          v15 = pcbLength - 2;
          Pool2 = (wchar_t *)ExAllocatePool2(256, pcbLength - 2, 1229146200);
          P = (BYTE *)Pool2;
          if ( !Pool2 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v9 = 152;
              goto LABEL_17;
            }
            return;
          }
          wcsncpy_s(Pool2, v15 >> 1, (const wchar_t *)v38->Text, v14);
          v11 = pcbLength;
        }
      }
    }
    v17 = 0;
    if ( v3 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v3[v18] );
      pcbLength = v11 + 112 + 2 * v18;
      v20 = (void *)ExAllocatePool2(256, pcbLength, 1229146200);
      if ( !v20 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_36:
          v22 = P;
LABEL_37:
          if ( v22 )
            ExFreePoolWithTag(v22, 0x49434858u);
          return;
        }
        v21 = 153;
LABEL_35:
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), v19, 4, v21, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
        goto LABEL_36;
      }
      v33 = *(unsigned __int8 *)(a1 + 721);
      v32 = *(unsigned __int8 *)(a1 + 720);
      v31 = v35;
      v30 = v5;
      Data = (PVOID)v37;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), v10, 4, 154, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
      }
      if ( RtlFindMessage(
             *(PVOID *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 24LL),
             0xBu,
             0,
             0x40010002u,
             &v39) < 0 )
        goto LABEL_36;
      v19 = v39->Length - 4LL;
      v37 = v19;
      if ( v19 > 0xFFFFFFFE )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_36;
        v21 = 155;
        goto LABEL_35;
      }
      if ( RtlUnalignedStringCbLengthW((STRSAFE_PCUNZWCH)v39->Text, v19, &v37) < 0 )
        goto LABEL_36;
      pcbLength += 108 + v37;
      v20 = (void *)ExAllocatePool2(256, pcbLength, 1229146200);
      if ( !v20 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_36;
        v21 = 156;
        goto LABEL_35;
      }
      v17 = v39->Text;
      if ( v37 >= 4 && *(_WORD *)&v17[2 * (v37 >> 1) - 2] == 10 )
      {
        MaxCount = (v37 >> 1) - 2;
        if ( *(_WORD *)&v17[2 * MaxCount] == 13 )
        {
          v37 -= 2LL;
          v23 = (wchar_t *)ExAllocatePool2(256, v37, 1229146200);
          v17 = (BYTE *)v23;
          if ( !v23 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v24) = 2;
              WPP_RECORDER_SF_(
                *(_QWORD *)(a1 + 72),
                v24,
                4,
                157,
                (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
            }
            v22 = P;
            goto LABEL_58;
          }
          wcsncpy_s(v23, v37 >> 1, (const wchar_t *)v39->Text, MaxCount);
        }
      }
      v33 = *(unsigned __int8 *)(a1 + 721);
      v32 = *(unsigned __int8 *)(a1 + 720);
      v31 = v35;
      v30 = v5;
      Data = v17;
    }
    v22 = P;
    LODWORD(MessageResourceEntry) = 1073807361;
    if ( RtlStringCbPrintfW(
           (NTSTRSAFE_PWSTR)v20,
           pcbLength,
           L"%s,#%d;%s;(%s,%X.%X,%X.%X)",
           v41,
           MessageResourceEntry,
           P,
           Data,
           v30,
           v31,
           v32,
           v33) >= 0
      && RtlUnalignedStringCbLengthW((STRSAFE_PCUNZWCH)v20, pcbLength, &pcbLength) >= 0 )
    {
      v25 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 264))(
                                       WdfDriverGlobals,
                                       *(_QWORD *)a1);
      v26 = IoSetDevicePropertyData(v25, &DEVPKEY_Device_FriendlyName, 0, 1u, 0x19u, pcbLength + 2, v20);
      if ( v26 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 3;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 72),
          v27,
          4,
          158,
          (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
          v26);
      }
    }
LABEL_58:
    ExFreePoolWithTag(v20, 0x49434858u);
    if ( v17 )
      ExFreePoolWithTag(v17, 0x49434858u);
    goto LABEL_37;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = 151;
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x140079268  push    rbp
0x14007926a  push    rbx
0x14007926b  push    rsi
0x14007926c  push    rdi
0x14007926d  push    r12
0x14007926f  push    r13
0x140079271  push    r14
0x140079273  push    r15
0x140079275  lea     rbp, [rsp-1Fh]
0x14007927a  sub     rsp, 0E8h
0x140079281  mov     rax, cs:__security_cookie
0x140079288  xor     rax, rsp
0x14007928b  mov     [rbp+57h+var_48], rax
0x14007928f  movups  xmm0, xmmword ptr cs:aSystem32Driver; "@System32\\drivers\\usbxhci.sys"
0x140079296  xor     r12d, r12d
0x140079299  mov     rsi, rcx
0x14007929c  movups  xmm1, xmmword ptr cs:aSystem32Driver+10h; "2\\drivers\\usbxhci.sys"
0x1400792a3  mov     [rbp+57h+var_A0], r12
0x1400792a7  movups  [rbp+57h+var_88], xmm0
0x1400792ab  mov     [rbp+57h+var_98], r12
0x1400792af  movups  xmm0, xmmword ptr cs:aSystem32Driver+20h; "s\\usbxhci.sys"
0x1400792b6  movups  [rbp+57h+var_78], xmm1
0x1400792ba  movups  xmm1, xmmword ptr cs:aSystem32Driver+2Ch; "hci.sys"
0x1400792c1  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1400792c5  movups  xmmword ptr [rbp+57h+var_68+0Ch], xmm1
0x1400792c9  call    Controller_DriverInstalledDueToCompatibleIdMatch
0x1400792ce  test    al, al
0x1400792d0  jz      loc_14007956C
0x1400792d6  mov     rcx, [rsi+98h]
0x1400792dd  mov     r13d, r12d
0x1400792e0  mov     [rbp+57h+var_A8], r12
0x1400792e4  call    RootHub_GetHighestUsbVersionSupported
0x1400792e9  cmp     dword ptr [rsi+284h], 1
0x1400792f0  lea     rdi, cs:140000000h
0x1400792f7  movzx   ebx, ax
0x1400792fa  mov     word ptr [rbp+57h+var_B8], bx
0x1400792fe  jnz     short loc_14007932C
0x140079300  mov     ecx, r12d
0x140079303  cmp     ecx, 0Bh
0x140079306  jnb     short loc_14007936B
0x140079308  movzx   eax, word ptr [rsi+288h]
0x14007930f  mov     edx, ecx
0x140079311  add     rdx, rdx
0x140079314  cmp     rva PciVendorIdTable[rdi+rdx*8], ax
0x14007931c  jz      short loc_140079322
0x14007931e  inc     ecx
0x140079320  jmp     short loc_140079303
0x140079322  mov     r13, rva off_14006C448[rdi+rdx*8]; "ATI/AMD" ...
0x14007932a  jmp     short loc_140079367
0x14007932c  mov     r14d, r12d
0x14007932f  cmp     r14d, 5
0x140079333  jnb     short loc_14007936B
0x140079335  mov     r15d, r14d
0x140079338  lea     rdx, [rsi+2C0h]; Str2
0x14007933f  add     r15, r15
0x140079342  mov     rcx, rva AcpiVendorIdTable[rdi+r15*8]; Str1
0x14007934a  call    cs:__imp__stricmp
0x140079351  nop     dword ptr [rax+rax+00h]
0x140079356  test    eax, eax
0x140079358  jz      short loc_14007935F
0x14007935a  inc     r14d
0x14007935d  jmp     short loc_14007932F
0x14007935f  mov     r13, rva off_14006C3F8[rdi+r15*8]; "NVIDIA" ...
0x140079367  mov     [rbp+57h+var_A8], r13
0x14007936b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140079372  lea     rax, [rbp+57h+var_A0]
0x140079376  xor     r8d, r8d; Language
0x140079379  mov     [rsp+120h+MessageResourceEntry], rax; MessageResourceEntry
0x14007937e  mov     r9d, 40010001h; MessageId
0x140079384  mov     rcx, [rcx+18h]; BaseAddress
0x140079388  lea     edx, [r8+0Bh]; Type
0x14007938c  call    cs:__imp_RtlFindMessage
0x140079393  nop     dword ptr [rax+rax+00h]
0x140079398  test    eax, eax
0x14007939a  jns     short loc_1400793D8
0x14007939c  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400793a3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400793aa  jz      loc_14007956C
0x1400793b0  mov     r9d, 96h
0x1400793b6  mov     r8d, 4
0x1400793bc  mov     rcx, [rsi+48h]
0x1400793c0  lea     r14, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x1400793c7  mov     dl, 2
0x1400793c9  mov     [rsp+120h+MessageResourceEntry], r14
0x1400793ce  call    WPP_RECORDER_SF_
0x1400793d3  jmp     loc_14007956C
0x1400793d8  mov     rcx, [rbp+57h+var_A0]
0x1400793dc  mov     eax, 0FFFFFFFEh
0x1400793e1  movzx   edx, word ptr [rcx]
0x1400793e4  add     rdx, 0FFFFFFFFFFFFFFFCh; cbMax
0x1400793e8  mov     [rbp+57h+pcbLength], rdx
0x1400793ec  cmp     rdx, rax
0x1400793ef  jbe     short loc_14007940D
0x1400793f1  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400793f8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400793ff  jz      loc_14007956C
0x140079405  mov     r9d, 97h
0x14007940b  jmp     short loc_1400793B6
0x14007940d  add     rcx, 4; psz
0x140079411  lea     r8, [rbp+57h+pcbLength]; pcbLength
0x140079415  call    RtlUnalignedStringCbLengthW
0x14007941a  test    eax, eax
0x14007941c  js      loc_14007956C
0x140079422  mov     r12, [rbp+57h+var_A0]
0x140079426  mov     r15d, 4
0x14007942c  mov     rcx, [rbp+57h+pcbLength]
0x140079430  add     r12, 4
0x140079434  mov     [rbp+57h+P], r12
0x140079438  cmp     rcx, r15
0x14007943b  jb      loc_1400794C8
0x140079441  mov     rax, rcx
0x140079444  shr     rax, 1
0x140079447  cmp     word ptr [r12+rax*2-2], 0Ah
0x14007944e  jnz     short loc_1400794C8
0x140079450  lea     r14, [rax-2]
0x140079454  cmp     word ptr [r12+r14*2], 0Dh
0x14007945a  jnz     short loc_1400794C8
0x14007945c  lea     rdi, [rcx-2]
0x140079460  mov     r8d, 49434858h
0x140079466  mov     rdx, rdi
0x140079469  mov     ecx, 100h
0x14007946e  call    cs:__imp_ExAllocatePool2
0x140079475  nop     dword ptr [rax+rax+00h]
0x14007947a  mov     [rbp+57h+P], rax
0x14007947e  test    rax, rax
0x140079481  jnz     short loc_1400794A5
0x140079483  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007948a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140079491  jz      loc_14007956C
0x140079497  mov     r9d, 98h
0x14007949d  mov     r8d, r15d
0x1400794a0  jmp     loc_1400793BC
0x1400794a5  mov     r8, [rbp+57h+var_A0]
0x1400794a9  mov     r9, r14; MaxCount
0x1400794ac  shr     rdi, 1
0x1400794af  add     r8, r15; Src
0x1400794b2  mov     rdx, rdi; SizeInWords
0x1400794b5  mov     rcx, rax; Dst
0x1400794b8  call    cs:__imp_wcsncpy_s
0x1400794bf  nop     dword ptr [rax+rax+00h]
0x1400794c4  mov     rcx, [rbp+57h+pcbLength]
0x1400794c8  xor     r12d, r12d
0x1400794cb  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400794d2  lea     r14, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x1400794d9  test    r13, r13
0x1400794dc  jz      loc_1400795C2
0x1400794e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400794e6  inc     rax
0x1400794e9  cmp     [r13+rax*2+0], r12w
0x1400794ef  jnz     short loc_1400794E6
0x1400794f1  add     rcx, 70h ; 'p'
0x1400794f5  mov     r8d, 49434858h
0x1400794fb  lea     rax, [rcx+rax*2]
0x1400794ff  mov     ecx, 100h
0x140079504  mov     rdx, rax
0x140079507  mov     [rbp+57h+pcbLength], rax
0x14007950b  call    cs:__imp_ExAllocatePool2
0x140079512  nop     dword ptr [rax+rax+00h]
0x140079517  mov     r13, rax
0x14007951a  test    rax, rax
0x14007951d  jnz     short loc_14007958D
0x14007951f  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140079526  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14007952d  jz      short loc_14007954F
0x14007952f  mov     r9d, 99h
0x140079535  lea     r14, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007953c  mov     rcx, [rsi+48h]
0x140079540  mov     r8d, r15d
0x140079543  mov     dl, 2
0x140079545  mov     [rsp+120h+MessageResourceEntry], r14
0x14007954a  call    WPP_RECORDER_SF_
0x14007954f  mov     rbx, [rbp+57h+P]
0x140079553  test    rbx, rbx
0x140079556  jz      short loc_14007956C
0x140079558  mov     edx, 49434858h; Tag
0x14007955d  mov     rcx, rbx; P
0x140079560  call    cs:__imp_ExFreePoolWithTag
0x140079567  nop     dword ptr [rax+rax+00h]
0x14007956c  mov     rcx, [rbp+57h+var_48]
0x140079570  xor     rcx, rsp; StackCookie
0x140079573  call    __security_check_cookie
0x140079578  add     rsp, 0E8h
0x14007957f  pop     r15
0x140079581  pop     r14
0x140079583  pop     r13
0x140079585  pop     r12
0x140079587  pop     rdi
0x140079588  pop     rsi
0x140079589  pop     rbx
0x14007958a  pop     rbp
0x14007958b  retn
0x14007958d  movzx   eax, byte ptr [rsi+2D1h]
0x140079594  movzx   ecx, byte ptr [rsi+2D0h]
0x14007959b  movzx   edx, [rbp+57h+var_B8+1]
0x14007959f  mov     [rsp+120h+var_D0], eax
0x1400795a3  mov     rax, [rbp+57h+var_A8]
0x1400795a7  mov     [rsp+120h+var_D8], ecx
0x1400795ab  mov     [rsp+120h+var_E0], edx
0x1400795af  movzx   r8d, bl
0x1400795b3  mov     [rsp+120h+var_E8], r8d
0x1400795b8  mov     [rsp+120h+Data], rax
0x1400795bd  jmp     loc_1400797B7
0x1400795c2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400795c9  jz      short loc_1400795E5
0x1400795cb  mov     rcx, [rsi+48h]
0x1400795cf  mov     r9d, 9Ah
0x1400795d5  mov     r8d, r15d
0x1400795d8  mov     [rsp+120h+MessageResourceEntry], r14
0x1400795dd  mov     dl, r15b
0x1400795e0  call    WPP_RECORDER_SF_
0x1400795e5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400795ec  lea     rax, [rbp+57h+var_98]
0x1400795f0  xor     r8d, r8d; Language
0x1400795f3  mov     [rsp+120h+MessageResourceEntry], rax; MessageResourceEntry
0x1400795f8  mov     r9d, 40010002h; MessageId
0x1400795fe  mov     rcx, [rcx+18h]; BaseAddress
0x140079602  lea     edx, [r8+0Bh]; Type
0x140079606  call    cs:__imp_RtlFindMessage
0x14007960d  nop     dword ptr [rax+rax+00h]
0x140079612  test    eax, eax
0x140079614  js      loc_14007954F
0x14007961a  mov     rcx, [rbp+57h+var_98]
0x14007961e  mov     eax, 0FFFFFFFEh
0x140079623  movzx   edx, word ptr [rcx]
0x140079626  add     rdx, 0FFFFFFFFFFFFFFFCh; cbMax
0x14007962a  mov     [rbp+57h+var_A8], rdx
0x14007962e  cmp     rdx, rax
0x140079631  jbe     short loc_14007964B
0x140079633  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007963a  jz      loc_14007954F
0x140079640  mov     r9d, 9Bh
0x140079646  jmp     loc_14007953C
0x14007964b  add     rcx, r15; psz
0x14007964e  lea     r8, [rbp+57h+var_A8]; pcbLength
0x140079652  call    RtlUnalignedStringCbLengthW
0x140079657  test    eax, eax
0x140079659  js      loc_14007954F
0x14007965f  mov     rcx, [rbp+57h+pcbLength]
0x140079663  mov     r8d, 49434858h
0x140079669  mov     rax, [rbp+57h+var_A8]
0x14007966d  add     rcx, 6Ch ; 'l'
0x140079671  add     rax, rcx
0x140079674  mov     ecx, 100h
0x140079679  mov     rdx, rax
0x14007967c  mov     [rbp+57h+pcbLength], rax
0x140079680  call    cs:__imp_ExAllocatePool2
0x140079687  nop     dword ptr [rax+rax+00h]
0x14007968c  mov     r13, rax
0x14007968f  test    rax, rax
0x140079692  jnz     short loc_1400796AC
0x140079694  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007969b  jz      loc_14007954F
0x1400796a1  mov     r9d, 9Ch
0x1400796a7  jmp     loc_14007953C
0x1400796ac  mov     r12, [rbp+57h+var_98]
0x1400796b0  mov     rcx, [rbp+57h+var_A8]
0x1400796b4  add     r12, r15
0x1400796b7  cmp     rcx, r15
0x1400796ba  jb      loc_14007978B
0x1400796c0  mov     rax, rcx
0x1400796c3  shr     rax, 1
0x1400796c6  cmp     word ptr [r12+rax*2-2], 0Ah
0x1400796cd  jnz     loc_14007978B
0x1400796d3  add     rax, 0FFFFFFFFFFFFFFFEh
0x1400796d7  mov     [rbp+57h+MaxCount], rax
0x1400796db  cmp     word ptr [r12+rax*2], 0Dh
0x1400796e1  jnz     loc_14007978B
0x1400796e7  lea     rdx, [rcx-2]
0x1400796eb  mov     r8d, 49434858h
0x1400796f1  mov     ecx, 100h
0x1400796f6  mov     [rbp+57h+var_A8], rdx
0x1400796fa  call    cs:__imp_ExAllocatePool2
0x140079701  nop     dword ptr [rax+rax+00h]
0x140079706  mov     r12, rax
0x140079709  test    rax, rax
0x14007970c  jnz     short loc_14007976A
0x14007970e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140079715  jz      short loc_140079730
0x140079717  mov     rcx, [rsi+48h]
0x14007971b  mov     r9d, 9Dh
0x140079721  mov     r8d, r15d
0x140079724  mov     [rsp+120h+MessageResourceEntry], r14
0x140079729  mov     dl, 2
0x14007972b  call    WPP_RECORDER_SF_
0x140079730  mov     rbx, [rbp+57h+P]
0x140079734  mov     edx, 49434858h; Tag
0x140079739  mov     rcx, r13; P
0x14007973c  call    cs:__imp_ExFreePoolWithTag
0x140079743  nop     dword ptr [rax+rax+00h]
0x140079748  test    r12, r12
0x14007974b  jz      loc_140079553
0x140079751  mov     edx, 49434858h; Tag
0x140079756  mov     rcx, r12; P
0x140079759  call    cs:__imp_ExFreePoolWithTag
0x140079760  nop     dword ptr [rax+rax+00h]
0x140079765  jmp     loc_140079553
0x14007976a  mov     r8, [rbp+57h+var_98]
0x14007976e  mov     rcx, rax; Dst
0x140079771  mov     rdx, [rbp+57h+var_A8]
0x140079775  add     r8, r15; Src
  ... truncated ...
```
