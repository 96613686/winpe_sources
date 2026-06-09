# PrjfPopulateDestinationForRenameOrLink

- ea: `0x140007694`
- end: `0x140007988`
- name: `PrjfPopulateDestinationForRenameOrLink`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14002c98c`

## callees

- `0x140007694`
- `0x140007990`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000bb00`
- `0x14000be80`
- `0x14000d128`
- `0x140012d68`
- `0x14002aecc`
- `0x14003d2c8`
- `0x140042658`

## import_xrefs

- `FLTMGR!FltParseFileNameInformation` at `0x140007749`
- `FLTMGR!FltParseFileNameInformation` at `0x140007749`
- `FLTMGR!FltClose` at `0x1400078d0`
- `FLTMGR!FltClose` at `0x1400078d0`

## pseudocode

```c
__int64 __fastcall PrjfPopulateDestinationForRenameOrLink(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFLT_FILE_NAME_INFORMATION FileNameInformation,
        __int64 a4)
{
  int v8; // edx
  int v9; // ecx
  int v10; // ebx
  int v11; // r8d
  UNICODE_STRING *p_FinalComponent; // rdi
  int v13; // eax
  int v14; // edx
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // eax
  int v19; // edx
  int v20; // r8d
  int v21; // [rsp+20h] [rbp-E0h]
  HANDLE FileHandle; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v23[4]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v24; // [rsp+98h] [rbp-68h]
  __int128 v25; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v26[80]; // [rsp+C0h] [rbp-40h] BYREF

  FileHandle = 0;
  v10 = PrjfReopenFile(Instance, *(PFILE_OBJECT *)(a4 + 80), 0x80000000, &FileHandle, 0);
  if ( v10 < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x20;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDqqqd(v9, v8, v11, *((_QWORD *)WPP_GLOBAL_Control + 8), v21);
    }
    goto LABEL_19;
  }
  v10 = FltParseFileNameInformation(FileNameInformation);
  if ( v10 < 0 )
    goto LABEL_19;
  if ( PrjfFltQueryInformationByName )
  {
    v23[0] = 48;
    v23[3] = 512;
    v25 = 0;
    memset(v26, 0, 0x48u);
    p_FinalComponent = &FileNameInformation->FinalComponent;
    v23[1] = FileHandle;
    v23[2] = &FileNameInformation->FinalComponent;
    v24 = 0;
    v13 = ((__int64 (__fastcall *)(PFLT_FILTER, PFLT_INSTANCE, _QWORD *, __int128 *, _BYTE *, int, int, _QWORD))PrjfFltQueryInformationByName)(
            Globals,
            Instance,
            v23,
            &v25,
            v26,
            72,
            68,
            0);
    v10 = v13;
    if ( v13 >= 0 )
      goto LABEL_16;
    if ( v13 != -1073741772 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
        LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          525,
          v14,
          v16,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          13,
          124,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          209,
          v13);
      }
      goto LABEL_19;
    }
  }
  p_FinalComponent = &FileNameInformation->FinalComponent;
  v17 = PrjfPartiallyExpandDirectory(
          CallbackData,
          Instance,
          *(PFILE_OBJECT *)(a4 + 80),
          &FileNameInformation->FinalComponent);
  v10 = v17;
  if ( v17 < 0 && v17 != -1073741772 && v17 != -1073741267 )
    goto LABEL_19;
LABEL_16:
  if ( PrjfFltQueryInformationByName )
  {
    v10 = PrjfPrepareDestinationForRenameOrLink(CallbackData, Instance, FileHandle, p_FinalComponent, a4);
    if ( v10 < 0 )
      goto LABEL_19;
    goto LABEL_18;
  }
  if ( !byte_14001ABCD )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v15);
  v10 = PrjfDeleteTombstoneIfExists(Instance, *(PFILE_OBJECT *)(a4 + 80), (__int64)FileHandle, p_FinalComponent);
  if ( v10 >= 0 )
  {
LABEL_18:
    v10 = 0;
    goto LABEL_19;
  }
  if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = BYTE2(xmmword_14001A3D0) & 8;
    LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      531,
      v19,
      v20,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      19,
      125,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      36,
      v10);
  }
LABEL_19:
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140007694  push    rbp
0x140007696  push    rbx
0x140007697  push    rsi
0x140007698  push    rdi
0x140007699  push    r13
0x14000769b  push    r14
0x14000769d  push    r15
0x14000769f  lea     rbp, [rsp-20h]
0x1400076a4  sub     rsp, 120h
0x1400076ab  mov     rax, cs:__security_cookie
0x1400076b2  xor     rax, rsp
0x1400076b5  mov     [rbp+50h+var_40], rax
0x1400076b9  mov     r14, r9
0x1400076bc  mov     [rsp+150h+FileHandle], 0
0x1400076c5  mov     rsi, rdx
0x1400076c8  mov     [rsp+150h+var_130], 0; PFILE_OBJECT *
0x1400076d1  mov     r13, r8
0x1400076d4  lea     r9, [rsp+150h+FileHandle]; FileHandle
0x1400076d9  mov     r15, rcx
0x1400076dc  mov     r8d, 80000000h; DesiredAccess
0x1400076e2  mov     rdx, [r14+50h]; FileObject
0x1400076e6  mov     rcx, rsi; Instance
0x1400076e9  call    PrjfReopenFile
0x1400076ee  mov     ebx, eax
0x1400076f0  test    eax, eax
0x1400076f2  jns     short loc_140007746
0x1400076f4  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400076fa  lea     rax, WPP_RECORDER_INITIALIZED
0x140007701  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007708  setnz   r8b
0x14000770c  and     dl, 20h
0x14000770f  jnz     short loc_14000771A
0x140007711  test    r8b, r8b
0x140007714  jz      loc_1400078C6
0x14000771a  mov     r9, cs:WPP_GLOBAL_Control
0x140007721  mov     rax, [r14+50h]
0x140007725  mov     [rsp+150h+var_E8], ebx
0x140007729  mov     [rsp+150h+var_F0], rax
0x14000772e  mov     r9, [r9+40h]
0x140007732  mov     [rsp+150h+var_F8], rsi
0x140007737  mov     [rsp+150h+var_100], r15
0x14000773c  call    WPP_RECORDER_AND_TRACE_SF_sDqqqd
0x140007741  jmp     loc_1400078C6
0x140007746  mov     rcx, r13; FileNameInformation
0x140007749  call    cs:__imp_FltParseFileNameInformation
0x140007750  nop     dword ptr [rax+rax+00h]
0x140007755  mov     ebx, eax
0x140007757  test    eax, eax
0x140007759  js      loc_1400078C6
0x14000775f  mov     rbx, cs:PrjfFltQueryInformationByName
0x140007766  test    rbx, rbx
0x140007769  jz      loc_140007872
0x14000776f  xor     edx, edx; Val
0x140007771  mov     [rsp+150h+var_D8], 30h ; '0'
0x14000777a  xorps   xmm0, xmm0
0x14000777d  mov     [rbp+50h+var_C0], 200h
0x140007785  lea     rcx, [rbp+50h+var_90]; void *
0x140007789  movups  [rbp+50h+var_A8], xmm0
0x14000778d  lea     r8d, [rdx+48h]; Size
0x140007791  call    memset
0x140007796  mov     rax, [rsp+150h+FileHandle]
0x14000779b  lea     rdi, [r13+58h]
0x14000779f  mov     rcx, cs:Globals
0x1400077a6  lea     r9, [rbp+50h+var_A8]
0x1400077aa  mov     [rbp+50h+var_D0], rax
0x1400077ae  lea     r8, [rsp+150h+var_D8]
0x1400077b3  mov     [rsp+150h+var_118], 0
0x1400077bc  lea     rax, [rbp+50h+var_90]
0x1400077c0  mov     [rsp+150h+var_120], 44h ; 'D'
0x1400077c8  xorps   xmm0, xmm0
0x1400077cb  mov     [rsp+150h+var_128], 48h ; 'H'
0x1400077d3  mov     rdx, rsi
0x1400077d6  mov     [rsp+150h+var_130], rax
0x1400077db  mov     rax, rbx
0x1400077de  mov     [rbp+50h+var_C8], rdi
0x1400077e2  movdqu  [rbp+50h+var_B8], xmm0
0x1400077e7  call    _guard_dispatch_icall
0x1400077ec  mov     ebx, eax
0x1400077ee  test    eax, eax
0x1400077f0  jns     loc_14000789C
0x1400077f6  cmp     eax, 0C0000034h
0x1400077fb  jz      short loc_140007872
0x1400077fd  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140007803  lea     rax, WPP_RECORDER_INITIALIZED
0x14000780a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007811  setnz   r8b
0x140007815  and     dl, 20h
0x140007818  jnz     short loc_140007823
0x14000781a  test    r8b, r8b
0x14000781d  jz      loc_1400078C6
0x140007823  mov     dword ptr [rsp+150h+var_100], ebx
0x140007827  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000782e  mov     [rsp+150h+var_108], 15D1h
0x140007836  mov     ecx, 20Dh
0x14000783b  mov     [rsp+150h+var_110], rax
0x140007840  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140007847  mov     [rsp+150h+var_118], rax
0x14000784c  mov     word ptr [rsp+150h+var_120], 7Ch ; '|'
0x140007853  mov     [rsp+150h+var_128], 0Dh
0x14000785b  mov     r9, cs:WPP_GLOBAL_Control
0x140007862  mov     byte ptr [rsp+150h+var_130], 2
0x140007867  mov     r9, [r9+40h]
0x14000786b  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140007870  jmp     short loc_1400078C6
0x140007872  mov     r8, [r14+50h]; FileObject
0x140007876  lea     rdi, [r13+58h]
0x14000787a  mov     r9, rdi; FileName
0x14000787d  mov     rdx, rsi; Instance
0x140007880  mov     rcx, r15; CallbackData
0x140007883  call    PrjfPartiallyExpandDirectory
0x140007888  mov     ebx, eax
0x14000788a  test    eax, eax
0x14000788c  jns     short loc_14000789C
0x14000788e  cmp     eax, 0C0000034h
0x140007893  jz      short loc_14000789C
0x140007895  cmp     eax, 0C000022Dh
0x14000789a  jnz     short loc_1400078C6
0x14000789c  cmp     cs:PrjfFltQueryInformationByName, 0
0x1400078a4  jz      short loc_1400078FD
0x1400078a6  mov     r8, [rsp+150h+FileHandle]
0x1400078ab  mov     r9, rdi
0x1400078ae  mov     rdx, rsi
0x1400078b1  mov     [rsp+150h+var_130], r14
0x1400078b6  mov     rcx, r15
0x1400078b9  call    PrjfPrepareDestinationForRenameOrLink
0x1400078be  mov     ebx, eax
0x1400078c0  test    eax, eax
0x1400078c2  js      short loc_1400078C6
0x1400078c4  xor     ebx, ebx
0x1400078c6  mov     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400078cb  test    rcx, rcx
0x1400078ce  jz      short loc_1400078DC
0x1400078d0  call    cs:__imp_FltClose
0x1400078d7  nop     dword ptr [rax+rax+00h]
0x1400078dc  mov     eax, ebx
0x1400078de  mov     rcx, [rbp+50h+var_40]
0x1400078e2  xor     rcx, rsp; StackCookie
0x1400078e5  call    __security_check_cookie
0x1400078ea  add     rsp, 120h
0x1400078f1  pop     r15
0x1400078f3  pop     r14
0x1400078f5  pop     r13
0x1400078f7  pop     rdi
0x1400078f8  pop     rsi
0x1400078f9  pop     rbx
0x1400078fa  pop     rbp
0x1400078fb  retn
0x1400078fd  cmp     cs:byte_14001ABCD, 0
0x140007904  jnz     short loc_14000790B
0x140007906  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000790b  mov     r8, [rsp+150h+FileHandle]
0x140007910  mov     r9, rdi
0x140007913  mov     rdx, [r14+50h]; FileObject
0x140007917  mov     rcx, rsi; Instance
0x14000791a  call    PrjfDeleteTombstoneIfExists
0x14000791f  mov     ebx, eax
0x140007921  test    eax, eax
0x140007923  jns     short loc_1400078C4
0x140007925  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14000792b  lea     rax, WPP_RECORDER_INITIALIZED
0x140007932  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007939  setnz   r8b
0x14000793d  and     dl, 8
0x140007940  jnz     short loc_14000794B
0x140007942  test    r8b, r8b
0x140007945  jz      loc_1400078C6
0x14000794b  mov     dword ptr [rsp+150h+var_100], ebx
0x14000794f  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140007956  mov     [rsp+150h+var_108], 1624h
0x14000795e  mov     ecx, 213h
0x140007963  mov     [rsp+150h+var_110], rax
0x140007968  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14000796f  mov     [rsp+150h+var_118], rax
0x140007974  mov     word ptr [rsp+150h+var_120], 7Dh ; '}'
0x14000797b  mov     [rsp+150h+var_128], 13h
0x140007983  jmp     loc_14000785B
```
