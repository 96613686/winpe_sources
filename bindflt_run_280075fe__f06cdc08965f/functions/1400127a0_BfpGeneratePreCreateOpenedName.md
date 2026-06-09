# BfpGeneratePreCreateOpenedName

- ea: `0x1400127a0`
- end: `0x140012c54`
- name: `BfpGeneratePreCreateOpenedName`
- size: `1204`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140012c60`

## callees

- `0x140001348`
- `0x1400127a0`
- `0x140013610`
- `0x140013780`
- `0x140014178`
- `0x140020f10`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140012869`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012869`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140012bf8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140012bf8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140012c11`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140012c11`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140012844`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140012ba7`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140012844`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140012ba7`
- `FLTMGR!FltGetFileNameInformation` at `0x14001280e`
- `FLTMGR!FltGetFileNameInformation` at `0x14001280e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012882`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012882`
- `FLTMGR!FltReleaseContext` at `0x1400128ac`
- `FLTMGR!FltReleaseContext` at `0x140012c43`
- `FLTMGR!FltReleaseContext` at `0x1400128ac`
- `FLTMGR!FltReleaseContext` at `0x140012c43`

## pseudocode

```c
__int64 __fastcall BfpGeneratePreCreateOpenedName(
        struct _FLT_INSTANCE *a1,
        __int64 a2,
        struct _FLT_CALLBACK_DATA *a3,
        int a4,
        PFLT_NAME_CONTROL NameCtrl)
{
  struct _FILE_OBJECT *v6; // rcx
  __int64 v9; // r14
  PFLT_FILE_NAME_INFORMATION v10; // rbp
  NTSTATUS appended; // ebx
  PFLT_NAME_CONTROL v12; // rdi
  NTSTATUS v13; // eax
  int v15; // r9d
  int ContextsForFileObject; // eax
  int v17; // edx
  int v18; // eax
  int v19; // edx
  struct _FILE_OBJECT *v20; // rdx
  PFLT_FILE_NAME_INFORMATION v21; // r8
  __int64 v22; // rcx
  struct _FLT_NAME_CONTROL *v23; // rsi
  int Name; // eax
  int v25; // edx
  int v26; // r9d
  unsigned __int16 v27; // dx
  NTSTATUS v28; // eax
  char v29; // [rsp+30h] [rbp-68h]
  char v30; // [rsp+30h] [rbp-68h]
  __int64 v31; // [rsp+38h] [rbp-60h]
  NTSTATUS v32; // [rsp+38h] [rbp-60h]
  int v33; // [rsp+38h] [rbp-60h]
  __int64 v34; // [rsp+40h] [rbp-58h] BYREF
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-50h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+A8h] [rbp+10h] BYREF

  v6 = *(struct _FILE_OBJECT **)(a2 + 64);
  Context = 0;
  FileNameInformation = 0;
  v9 = a2;
  v10 = 0;
  if ( v6 )
  {
    ContextsForFileObject = BfGetContextsForFileObject(v6, a1);
    appended = ContextsForFileObject;
    if ( ContextsForFileObject < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          9,
          11,
          (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
          155,
          ContextsForFileObject);
      }
      v10 = FileNameInformation;
      goto LABEL_11;
    }
    v10 = FileNameInformation;
    if ( !FileNameInformation )
    {
      v18 = BfpPassthroughNameQuery(a3, 0, 0, a4 & 0xFF00FF00 | 2, NameCtrl);
      appended = v18;
      if ( v18 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v19) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v19,
            9,
            12,
            (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
            185,
            v18);
        }
        goto LABEL_13;
      }
      goto LABEL_10;
    }
    v20 = *(struct _FILE_OBJECT **)(v9 + 64);
    v21 = FileNameInformation;
    FileNameInformation = 0;
    v34 = 0;
    if ( (unsigned __int8)BfMapShadowFileObjectToReal(a1, v20, v21, (__int64)&v34, 0) )
    {
      a1 = (struct _FLT_INSTANCE *)FileNameInformation;
      LODWORD(v22) = v34;
    }
    else
    {
      v22 = *(_QWORD *)(v9 + 64);
    }
    v23 = NameCtrl;
    Name = BfpGeneratePostCreateName(v22, (int)a1, a4 & 0xFF00FF00 | 2, (int)v10, (__int64)a1, NameCtrl);
    appended = Name;
    if ( Name < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_11;
      v33 = Name;
      v26 = 13;
      v30 = -36;
      goto LABEL_40;
    }
    v27 = *(_WORD *)(v9 + 88);
    if ( v27 >= 2u )
    {
      v28 = FltCheckAndGrowNameControl(v23, v23->Name.Length + v27 + 2);
      appended = v28;
      if ( v28 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v33 = v28;
          v26 = 14;
          v30 = -16;
LABEL_40:
          LOBYTE(v25) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v25,
            9,
            v26,
            (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
            v30,
            v33);
          goto LABEL_11;
        }
        goto LABEL_11;
      }
      if ( **(_WORD **)(v9 + 96) != 92 && (appended = RtlAppendUnicodeToString(&v23->Name, L"\\"), appended < 0)
        || (appended = RtlAppendUnicodeStringToString(&v23->Name, (PCUNICODE_STRING)(v9 + 88)), appended < 0) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v33 = appended;
          v26 = 15;
          v30 = 0;
          goto LABEL_40;
        }
LABEL_11:
        if ( v10 )
          FltReleaseContext(v10);
LABEL_13:
        if ( Context )
          FltReleaseContext(Context);
        return (unsigned int)appended;
      }
    }
LABEL_10:
    appended = 0;
    goto LABEL_11;
  }
  FileNameInformation = 0;
  if ( !a3 )
    goto LABEL_16;
  appended = FltGetFileNameInformation(a3, a4 & 0xFF00FF00 | 2, &FileNameInformation);
  if ( appended < 0 )
  {
LABEL_17:
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_7;
    v32 = appended;
    v15 = 36;
    v29 = -77;
    goto LABEL_19;
  }
  LODWORD(a2) = FileNameInformation->Name.Length;
  if ( !(_WORD)a2 )
  {
    if ( FileNameInformation->Volume.Length )
    {
LABEL_16:
      appended = -1073741811;
      goto LABEL_17;
    }
  }
  v12 = NameCtrl;
  v13 = FltCheckAndGrowNameControl(NameCtrl, a2);
  appended = v13;
  if ( v13 >= 0 )
  {
    RtlCopyUnicodeString(&v12->Name, &FileNameInformation->Name);
    goto LABEL_7;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v32 = v13;
    v15 = 37;
    v29 = -69;
LABEL_19:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      9,
      v15,
      (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
      v29,
      v32);
  }
LABEL_7:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( appended >= 0 )
    goto LABEL_10;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v31) = appended;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      9,
      10,
      (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
      139,
      v31);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400127a0  mov     rax, rsp
0x1400127a3  push    rbx
0x1400127a4  push    rbp
0x1400127a5  push    rsi
0x1400127a6  push    rdi
0x1400127a7  push    r12
0x1400127a9  push    r13
0x1400127ab  push    r14
0x1400127ad  push    r15
0x1400127af  sub     rsp, 58h
0x1400127b3  xor     r13d, r13d
0x1400127b6  mov     r15, rcx
0x1400127b9  mov     rcx, [rdx+40h]; FileObject
0x1400127bd  mov     edi, r9d
0x1400127c0  mov     [rax-50h], r13
0x1400127c4  mov     rsi, r8
0x1400127c7  mov     [rax+10h], r13
0x1400127cb  mov     r14, rdx
0x1400127ce  mov     ebp, r13d
0x1400127d1  test    rcx, rcx
0x1400127d4  jnz     loc_140012913
0x1400127da  mov     [rax+10h], r13
0x1400127de  lea     r15, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400127e5  lea     r12, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x1400127ec  lea     r14, WPP_RECORDER_INITIALIZED
0x1400127f3  test    r8, r8
0x1400127f6  jz      loc_1400128CC
0x1400127fc  and     edi, 0FF00FF02h
0x140012802  lea     r8, [rax+10h]; FileNameInformation
0x140012806  or      edi, 2
0x140012809  mov     rcx, rsi; CallbackData
0x14001280c  mov     edx, edi; NameOptions
0x14001280e  call    cs:__imp_FltGetFileNameInformation
0x140012815  nop     dword ptr [rax+rax+00h]
0x14001281a  mov     ebx, eax
0x14001281c  test    eax, eax
0x14001281e  js      loc_1400128D1
0x140012824  mov     rcx, [rsp+98h+FileNameInformation]
0x14001282c  movzx   edx, word ptr [rcx+8]; NewSize
0x140012830  test    dx, dx
0x140012833  jz      loc_1400129F2
0x140012839  mov     rdi, [rsp+98h+NameCtrl]
0x140012841  mov     rcx, rdi; NameCtrl
0x140012844  call    cs:__imp_FltCheckAndGrowNameControl
0x14001284b  nop     dword ptr [rax+rax+00h]
0x140012850  mov     ebx, eax
0x140012852  test    eax, eax
0x140012854  js      loc_1400129CE
0x14001285a  mov     rdx, [rsp+98h+FileNameInformation]
0x140012862  mov     rcx, rdi; DestinationString
0x140012865  add     rdx, 8; SourceString
0x140012869  call    cs:__imp_RtlCopyUnicodeString
0x140012870  nop     dword ptr [rax+rax+00h]
0x140012875  mov     rcx, [rsp+98h+FileNameInformation]; FileNameInformation
0x14001287d  test    rcx, rcx
0x140012880  jz      short loc_14001288E
0x140012882  call    cs:__imp_FltReleaseFileNameInformation
0x140012889  nop     dword ptr [rax+rax+00h]
0x14001288e  test    ebx, ebx
0x140012890  js      loc_140012A01
0x140012896  mov     ebx, r13d
0x140012899  test    rbp, rbp
0x14001289c  jnz     loc_140012C40
0x1400128a2  mov     rcx, [rsp+98h+Context]; Context
0x1400128a7  test    rcx, rcx
0x1400128aa  jz      short loc_1400128B8
0x1400128ac  call    cs:__imp_FltReleaseContext
0x1400128b3  nop     dword ptr [rax+rax+00h]
0x1400128b8  mov     eax, ebx
0x1400128ba  add     rsp, 58h
0x1400128be  pop     r15
0x1400128c0  pop     r14
0x1400128c2  pop     r13
0x1400128c4  pop     r12
0x1400128c6  pop     rdi
0x1400128c7  pop     rsi
0x1400128c8  pop     rbp
0x1400128c9  pop     rbx
0x1400128ca  retn
0x1400128cc  mov     ebx, 0C000000Dh
0x1400128d1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400128d8  jz      short loc_140012875
0x1400128da  mov     dword ptr [rsp+98h+var_60], ebx
0x1400128de  mov     r9d, 24h ; '$'
0x1400128e4  mov     dword ptr [rsp+98h+var_68], 3B3h
0x1400128ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400128f3  mov     r8d, 9
0x1400128f9  mov     [rsp+98h+var_70], r15
0x1400128fe  mov     dl, 2
0x140012900  mov     [rsp+98h+var_78], r12
0x140012905  mov     rcx, [rcx+40h]
0x140012909  call    WPP_RECORDER_SF_sDd
0x14001290e  jmp     loc_140012875
0x140012913  lea     r9, [rsp+98h+FileNameInformation]
0x14001291b  mov     rdx, r15; Instance
0x14001291e  lea     r8, [rsp+98h+Context]
0x140012923  call    BfGetContextsForFileObject
0x140012928  mov     ebx, eax
0x14001292a  test    eax, eax
0x14001292c  js      loc_140012A47
0x140012932  mov     rbp, [rsp+98h+FileNameInformation]
0x14001293a  test    rbp, rbp
0x14001293d  jnz     loc_140012AA6
0x140012943  mov     rax, [rsp+98h+NameCtrl]
0x14001294b  and     edi, 0FF00FF02h
0x140012951  or      edi, 2
0x140012954  mov     [rsp+98h+var_78], rax
0x140012959  mov     r9d, edi
0x14001295c  xor     r8d, r8d
0x14001295f  xor     edx, edx
0x140012961  mov     rcx, rsi
0x140012964  call    BfpPassthroughNameQuery
0x140012969  mov     ebx, eax
0x14001296b  test    eax, eax
0x14001296d  jns     loc_140012896
0x140012973  lea     r14, WPP_RECORDER_INITIALIZED
0x14001297a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140012981  jz      loc_1400128A2
0x140012987  mov     rcx, cs:WPP_GLOBAL_Control
0x14001298e  lea     r15, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140012995  mov     dword ptr [rsp+98h+var_60], eax
0x140012999  lea     r12, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x1400129a0  mov     dword ptr [rsp+98h+var_68], 0B9h
0x1400129a8  mov     r9d, 0Ch
0x1400129ae  mov     [rsp+98h+var_70], r15
0x1400129b3  mov     r8d, 9
0x1400129b9  mov     rcx, [rcx+40h]
0x1400129bd  mov     dl, 2
0x1400129bf  mov     [rsp+98h+var_78], r12
0x1400129c4  call    WPP_RECORDER_SF_sDd
0x1400129c9  jmp     loc_1400128A2
0x1400129ce  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400129d5  jz      loc_140012875
0x1400129db  mov     dword ptr [rsp+98h+var_60], eax
0x1400129df  mov     r9d, 25h ; '%'
0x1400129e5  mov     dword ptr [rsp+98h+var_68], 3BBh
0x1400129ed  jmp     loc_1400128EC
0x1400129f2  cmp     [rcx+18h], bp
0x1400129f6  ja      loc_1400128CC
0x1400129fc  jmp     loc_140012839
0x140012a01  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140012a08  jz      loc_1400128B8
0x140012a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a15  mov     r9d, 0Ah
0x140012a1b  mov     dword ptr [rsp+98h+var_60], ebx
0x140012a1f  mov     r8d, 9
0x140012a25  mov     dword ptr [rsp+98h+var_68], 8Bh
0x140012a2d  mov     dl, 2
0x140012a2f  mov     [rsp+98h+var_70], r15
0x140012a34  mov     rcx, [rcx+40h]
0x140012a38  mov     [rsp+98h+var_78], r12
0x140012a3d  call    WPP_RECORDER_SF_sDd
0x140012a42  jmp     loc_1400128B8
0x140012a47  lea     r14, WPP_RECORDER_INITIALIZED
0x140012a4e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140012a55  jz      short loc_140012A99
0x140012a57  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a5e  lea     r15, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140012a65  mov     dword ptr [rsp+98h+var_60], eax
0x140012a69  lea     r12, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x140012a70  mov     dword ptr [rsp+98h+var_68], 9Bh
0x140012a78  mov     r9d, 0Bh
0x140012a7e  mov     [rsp+98h+var_70], r15
0x140012a83  mov     r8d, 9
0x140012a89  mov     rcx, [rcx+40h]
0x140012a8d  mov     dl, 2
0x140012a8f  mov     [rsp+98h+var_78], r12
0x140012a94  call    WPP_RECORDER_SF_sDd
0x140012a99  mov     rbp, [rsp+98h+FileNameInformation]
0x140012aa1  jmp     loc_140012899
0x140012aa6  mov     rdx, [r14+40h]; FileObject
0x140012aaa  lea     rax, [rsp+98h+var_58]
0x140012aaf  mov     [rsp+98h+var_70], r13; __int64
0x140012ab4  lea     r9, [rsp+98h+FileNameInformation]
0x140012abc  mov     r8, rbp; Context
0x140012abf  mov     [rsp+98h+var_78], rax; __int64
0x140012ac4  mov     rcx, r15; Instance
0x140012ac7  mov     [rsp+98h+FileNameInformation], r13
0x140012acf  mov     [rsp+98h+var_58], r13
0x140012ad4  call    BfMapShadowFileObjectToReal
0x140012ad9  test    al, al
0x140012adb  jnz     short loc_140012AE3
0x140012add  mov     rcx, [r14+40h]
0x140012ae1  jmp     short loc_140012AF0
0x140012ae3  mov     r15, [rsp+98h+FileNameInformation]
0x140012aeb  mov     rcx, [rsp+98h+var_58]; int
0x140012af0  mov     rsi, [rsp+98h+NameCtrl]
0x140012af8  and     edi, 0FF00FF02h
0x140012afe  or      edi, 2
0x140012b01  mov     [rsp+98h+var_70], rsi; NameCtrl
0x140012b06  mov     r8d, edi; int
0x140012b09  mov     [rsp+98h+var_78], r15; __int64
0x140012b0e  mov     r9, rbp; int
0x140012b11  mov     rdx, r15; int
0x140012b14  call    BfpGeneratePostCreateName
0x140012b19  mov     ebx, eax
0x140012b1b  test    eax, eax
0x140012b1d  jns     short loc_140012B8E
0x140012b1f  lea     r14, WPP_RECORDER_INITIALIZED
0x140012b26  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140012b2d  jz      loc_140012899
0x140012b33  mov     dword ptr [rsp+98h+var_60], eax
0x140012b37  mov     r9d, 0Dh
0x140012b3d  mov     dword ptr [rsp+98h+var_68], 0DCh
0x140012b45  jmp     short loc_140012B59
0x140012b47  mov     dword ptr [rsp+98h+var_60], ebx
0x140012b4b  mov     r9d, 0Fh
0x140012b51  mov     dword ptr [rsp+98h+var_68], 100h
0x140012b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b60  lea     r15, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140012b67  lea     r12, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x140012b6e  mov     [rsp+98h+var_70], r15
0x140012b73  mov     r8d, 9
0x140012b79  mov     [rsp+98h+var_78], r12
0x140012b7e  mov     dl, 2
0x140012b80  mov     rcx, [rcx+40h]
0x140012b84  call    WPP_RECORDER_SF_sDd
0x140012b89  jmp     loc_140012899
0x140012b8e  movzx   edx, word ptr [r14+58h]
0x140012b93  cmp     dx, 2
0x140012b97  jb      loc_140012896
0x140012b9d  add     dx, 2
0x140012ba1  mov     rcx, rsi; NameCtrl
0x140012ba4  add     dx, [rsi]; NewSize
0x140012ba7  call    cs:__imp_FltCheckAndGrowNameControl
0x140012bae  nop     dword ptr [rax+rax+00h]
0x140012bb3  mov     ebx, eax
0x140012bb5  test    eax, eax
0x140012bb7  jns     short loc_140012BE4
0x140012bb9  lea     r14, WPP_RECORDER_INITIALIZED
0x140012bc0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140012bc7  jz      loc_140012899
0x140012bcd  mov     dword ptr [rsp+98h+var_60], eax
0x140012bd1  mov     r9d, 0Eh
0x140012bd7  mov     dword ptr [rsp+98h+var_68], 0F0h
0x140012bdf  jmp     loc_140012B59
0x140012be4  mov     rax, [r14+60h]
0x140012be8  cmp     word ptr [rax], 5Ch ; '\'
0x140012bec  jz      short loc_140012C0A
0x140012bee  lea     rdx, Source; "\\"
0x140012bf5  mov     rcx, rsi; Destination
0x140012bf8  call    cs:__imp_RtlAppendUnicodeToString
0x140012bff  nop     dword ptr [rax+rax+00h]
0x140012c04  mov     ebx, eax
0x140012c06  test    eax, eax
0x140012c08  js      short loc_140012C27
0x140012c0a  lea     rdx, [r14+58h]; Source
0x140012c0e  mov     rcx, rsi; Destination
0x140012c11  call    cs:__imp_RtlAppendUnicodeStringToString
0x140012c18  nop     dword ptr [rax+rax+00h]
0x140012c1d  mov     ebx, eax
0x140012c1f  test    eax, eax
0x140012c21  jns     loc_140012896
0x140012c27  lea     r14, WPP_RECORDER_INITIALIZED
0x140012c2e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140012c35  jz      loc_140012899
0x140012c3b  jmp     loc_140012B47
0x140012c40  mov     rcx, rbp; Context
0x140012c43  call    cs:__imp_FltReleaseContext
0x140012c4a  nop     dword ptr [rax+rax+00h]
0x140012c4f  jmp     loc_1400128A2
```
