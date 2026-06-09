# BfGetPreCreateFileName

- ea: `0x140017360`
- end: `0x14001790e`
- name: `BfGetPreCreateFileName`
- size: `1454`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, PFLT_CONTEXT Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1400157a0`

## callees

- `0x140001348`
- `0x140001dd0`
- `0x140017360`
- `0x14001d130`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140017873`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140017873`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017454`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001748c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400178fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017454`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001748c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400178fd`
- `ntoskrnl!ExAllocatePool2` at `0x140017750`
- `ntoskrnl!ExAllocatePool2` at `0x140017750`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400176ff`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140017726`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400176ff`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140017726`
- `FLTMGR!FltGetFileNameInformation` at `0x1400173e0`
- `FLTMGR!FltGetFileNameInformation` at `0x1400173e0`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140017777`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140017777`
- `FLTMGR!FltParseFileNameInformation` at `0x1400177de`
- `FLTMGR!FltParseFileNameInformation` at `0x1400177de`
- `FLTMGR!FltGetStreamHandleContext` at `0x14001751e`
- `FLTMGR!FltGetStreamHandleContext` at `0x14001751e`
- `FLTMGR!FltReleaseContext` at `0x140017546`
- `FLTMGR!FltReleaseContext` at `0x140017562`
- `FLTMGR!FltReleaseContext` at `0x140017615`
- `FLTMGR!FltReleaseContext` at `0x140017546`
- `FLTMGR!FltReleaseContext` at `0x140017562`
- `FLTMGR!FltReleaseContext` at `0x140017615`
- `FLTMGR!FltObjectDereference` at `0x1400175bd`
- `FLTMGR!FltObjectDereference` at `0x1400175bd`
- `FLTMGR!FltGetVolumeName` at `0x140017797`
- `FLTMGR!FltGetVolumeName` at `0x140017797`

## string_xrefs

- `0x1400174d9`: `onecore\base\fs\wci\bindflt\filter\create.c`

## pseudocode

```c
__int64 __fastcall BfGetPreCreateFileName(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        struct _FLT_INSTANCE *a3,
        PFLT_FILE_NAME_INFORMATION *a4,
        _BYTE *Context)
{
  _BYTE *v7; // r14
  struct _FILE_OBJECT *v9; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v10; // r12
  _BYTE *v11; // r15
  NTSTATUS FileNameInformation; // eax
  NTSTATUS Name; // edi
  int v15; // r9d
  NTSTATUS StreamHandleContext; // eax
  PFLT_CONTEXT v17; // rcx
  __int64 v18; // rcx
  _WORD *v19; // rax
  struct _FLT_INSTANCE *v20; // rsi
  __int64 v21; // rdx
  __int64 v22; // rax
  __int16 v23; // r8
  const UNICODE_STRING *v24; // r13
  __int64 v25; // r9
  __int64 Pool2; // rax
  char v27; // [rsp+38h] [rbp-21h]
  __int64 v28; // [rsp+40h] [rbp-19h]
  PVOID FltObject; // [rsp+48h] [rbp-11h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-9h] BYREF
  PVOID v31[2]; // [rsp+60h] [rbp+7h] BYREF
  ULONG BufferSizeNeeded; // [rsp+C0h] [rbp+67h] BYREF
  PFLT_INSTANCE Instance; // [rsp+C8h] [rbp+6Fh]

  Instance = a3;
  v7 = Context;
  v9 = *(struct _FILE_OBJECT **)(a2 + 64);
  v10 = 0;
  FltObject = 0;
  v11 = 0;
  *Context = 0;
  BufferSizeNeeded = 0;
  *(_OWORD *)v31 = 0;
  *(_OWORD *)P = 0;
  if ( !v9 )
  {
LABEL_2:
    *a4 = 0;
    if ( CallbackData
      && ((FileNameInformation = FltGetFileNameInformation(CallbackData, 0x102u, a4), FileNameInformation < 0)
       || (*a4)->Name.Length
       || !(*a4)->Volume.Length) )
    {
      Name = FileNameInformation;
      if ( FileNameInformation >= 0 )
        goto LABEL_6;
    }
    else
    {
      Name = -1073741811;
      FileNameInformation = -1073741811;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v28) = FileNameInformation;
      v15 = 11;
      v27 = -67;
LABEL_22:
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        5,
        v15,
        (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
        v27,
        v28);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  Context = 0;
  StreamHandleContext = FltGetStreamHandleContext(a3, v9, (PFLT_CONTEXT *)&Context);
  Name = StreamHandleContext;
  if ( StreamHandleContext == -1073741275 )
  {
    v11 = Context;
LABEL_29:
    v17 = 0;
    Context = 0;
    Name = 0;
    goto LABEL_30;
  }
  if ( StreamHandleContext >= 0 )
  {
    v11 = Context;
    if ( (*((_DWORD *)Context + 20) & 1) == 0 )
    {
      FltReleaseContext(Context);
      v11 = 0;
    }
    goto LABEL_29;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      7,
      25,
      (__int64)WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\context.c",
      173,
      StreamHandleContext);
  }
  v17 = Context;
LABEL_30:
  if ( v17 )
    FltReleaseContext(v17);
  if ( Name >= 0 )
  {
    if ( v11 )
    {
      v18 = *(_QWORD *)(a2 + 64);
      v19 = *(_WORD **)(v18 + 24);
      if ( v19 && *v19 == 25649 && (v11[80] & 1) != 0 )
      {
        v22 = *(_QWORD *)(v18 + 32);
        v20 = Instance;
        v18 = *(_QWORD *)(v22 + 8);
        v21 = *(_QWORD *)(v22 + 16);
      }
      else
      {
        v20 = Instance;
        LODWORD(v21) = (_DWORD)Instance;
      }
      Name = BfGeneratePostCreateName(v18, v21, 16777474, (_DWORD)v11, (__int64)v20, (__int64)v31);
      if ( Name >= 0 )
      {
        v23 = (__int16)v31[0];
        if ( *((_WORD *)v31[1] + ((unsigned __int64)LOWORD(v31[0]) >> 1) - 1) == 92
          || (Context = (_BYTE *)(a2 + 88), !*(_WORD *)(a2 + 88))
          || **(_WORD **)(a2 + 96) == 58 )
        {
          LOBYTE(Context) = 0;
          v24 = (const UNICODE_STRING *)(a2 + 88);
        }
        else
        {
          v24 = (const UNICODE_STRING *)Context;
          v23 = LOWORD(v31[0]) + 2;
          LOBYTE(Context) = 1;
        }
        WORD1(P[0]) = v24->Length + v23;
        Name = BfAllocateUnicodeString(WORD1(P[0]), P);
        if ( Name >= 0 )
        {
          Name = RtlAppendUnicodeStringToString((PUNICODE_STRING)P, (PCUNICODE_STRING)v31);
          if ( Name >= 0 )
          {
            if ( !(_BYTE)Context || (Name = RtlAppendUnicodeToString((PUNICODE_STRING)P, L"\\"), Name >= 0) )
            {
              Name = RtlAppendUnicodeStringToString((PUNICODE_STRING)P, v24);
              if ( Name >= 0 )
              {
                Pool2 = ExAllocatePool2(256, 120, 1835943490, v25);
                v10 = (struct _FLT_FILE_NAME_INFORMATION *)Pool2;
                if ( Pool2 )
                {
                  *(_OWORD *)(Pool2 + 8) = *(_OWORD *)P;
                  Name = FltGetVolumeFromInstance(v20, (PFLT_VOLUME *)&FltObject);
                  if ( Name < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LODWORD(v28) = Name;
                      v15 = 13;
                      v27 = 28;
                      goto LABEL_22;
                    }
                  }
                  else
                  {
                    Name = FltGetVolumeName((PFLT_VOLUME)FltObject, 0, &BufferSizeNeeded);
                    if ( (int)(Name + 0x80000000) < 0 || Name == -1073741789 )
                    {
                      v10->Volume.Buffer = v10->Name.Buffer;
                      v10->Volume.Length = BufferSizeNeeded;
                      v10->Volume.MaximumLength = BufferSizeNeeded;
                      *(_DWORD *)&v10->Size = 120;
                      v10->Format = 2;
                      Name = FltParseFileNameInformation(v10);
                      if ( Name < 0 )
                      {
                        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          LODWORD(v28) = Name;
                          v15 = 15;
                          v27 = 50;
                          goto LABEL_22;
                        }
                      }
                      else
                      {
                        *a4 = v10;
                        v10 = 0;
                        *v7 = 1;
                      }
                    }
                    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LODWORD(v28) = Name;
                      v15 = 14;
                      v27 = 35;
                      goto LABEL_22;
                    }
                  }
                }
                else
                {
                  Name = -1073741670;
                }
              }
            }
          }
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v28) = Name;
        v15 = 12;
        v27 = -36;
        goto LABEL_22;
      }
      goto LABEL_6;
    }
    goto LABEL_2;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v28) = Name;
    v15 = 10;
    v27 = -88;
    goto LABEL_22;
  }
LABEL_6:
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( v11 )
    FltReleaseContext(v11);
  if ( !*v7 )
  {
    if ( P[1] )
    {
      ExFreePoolWithTag(P[1], 0x74734642u);
      P[1] = 0;
    }
    LODWORD(P[0]) = 0;
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0x6D6E4642u);
  if ( v31[1] )
    ExFreePoolWithTag(v31[1], 0x74734642u);
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x140017360  mov     rax, rsp
0x140017363  mov     [rax+18h], r8
0x140017367  push    rbp
0x140017368  push    rdi
0x140017369  lea     rbp, [rax-57h]
0x14001736d  sub     rsp, 98h
0x140017374  mov     [rax+8], rbx
0x140017378  xorps   xmm0, xmm0
0x14001737b  mov     [rax-18h], rsi
0x14001737f  xorps   xmm1, xmm1
0x140017382  mov     [rax-20h], r12
0x140017386  mov     rsi, rcx
0x140017389  xor     ecx, ecx
0x14001738b  mov     [rax-28h], r13
0x14001738f  mov     [rax-30h], r14
0x140017393  mov     r13, rdx
0x140017396  mov     r14, [rbp+4Fh+Context]
0x14001739a  mov     rbx, r9
0x14001739d  mov     rdx, [rdx+40h]; FileObject
0x1400173a1  mov     r12d, ecx
0x1400173a4  mov     [rax-38h], r15
0x1400173a8  mov     rax, r8
0x1400173ab  mov     [rbp+4Fh+FltObject], rcx
0x1400173af  mov     r15d, ecx
0x1400173b2  mov     [r14], cl
0x1400173b5  mov     [rbp+4Fh+BufferSizeNeeded], ecx
0x1400173b8  movups  xmmword ptr [rbp+4Fh+var_48], xmm0
0x1400173bc  movups  xmmword ptr [rbp+4Fh+P], xmm1
0x1400173c0  test    rdx, rdx
0x1400173c3  jnz     loc_140017513
0x1400173c9  mov     [rbx], rcx
0x1400173cc  test    rsi, rsi
0x1400173cf  jz      loc_1400174A5
0x1400173d5  mov     r8, rbx; FileNameInformation
0x1400173d8  mov     edx, 102h; NameOptions
0x1400173dd  mov     rcx, rsi; CallbackData
0x1400173e0  call    cs:__imp_FltGetFileNameInformation
0x1400173e7  nop     dword ptr [rax+rax+00h]
0x1400173ec  test    eax, eax
0x1400173ee  js      short loc_1400173FE
0x1400173f0  mov     rcx, [rbx]
0x1400173f3  cmp     [rcx+8], r12w
0x1400173f8  jz      loc_140017507
0x1400173fe  mov     edi, eax
0x140017400  test    eax, eax
0x140017402  js      loc_1400174AC
0x140017408  mov     rcx, [rbp+4Fh+FltObject]; FltObject
0x14001740c  mov     r13, [rsp+0A0h+var_20]
0x140017414  mov     rsi, [rsp+90h]
0x14001741c  mov     rbx, [rsp+0A0h+arg_0]
0x140017424  test    rcx, rcx
0x140017427  jnz     loc_1400175BD
0x14001742d  test    r15, r15
0x140017430  jnz     loc_140017612
0x140017436  cmp     byte ptr [r14], 0
0x14001743a  mov     r14, [rsp+0A0h+var_28]
0x14001743f  mov     r15, [rsp+0A0h+var_30]
0x140017444  jnz     short loc_14001746D
0x140017446  mov     rcx, [rbp+4Fh+P+8]; P
0x14001744a  test    rcx, rcx
0x14001744d  jz      short loc_140017468
0x14001744f  mov     edx, 74734642h; Tag
0x140017454  call    cs:__imp_ExFreePoolWithTag
0x14001745b  nop     dword ptr [rax+rax+00h]
0x140017460  mov     [rbp+4Fh+P+8], 0
0x140017468  xor     eax, eax
0x14001746a  mov     dword ptr [rbp+4Fh+P], eax
0x14001746d  test    r12, r12
0x140017470  jnz     loc_1400178F5
0x140017476  mov     rcx, [rbp+4Fh+var_48+8]; P
0x14001747a  mov     r12, [rsp+0A0h+var_18]
0x140017482  test    rcx, rcx
0x140017485  jz      short loc_140017498
0x140017487  mov     edx, 74734642h; Tag
0x14001748c  call    cs:__imp_ExFreePoolWithTag
0x140017493  nop     dword ptr [rax+rax+00h]
0x140017498  mov     eax, edi
0x14001749a  add     rsp, 98h
0x1400174a1  pop     rdi
0x1400174a2  pop     rbp
0x1400174a3  retn
0x1400174a5  mov     edi, 0C000000Dh
0x1400174aa  mov     eax, edi
0x1400174ac  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400174b3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400174ba  jz      loc_140017408
0x1400174c0  mov     [rsp+38h], eax
0x1400174c4  mov     r9d, 0Bh
0x1400174ca  mov     dword ptr [rsp+0A0h+var_70], 0BDh
0x1400174d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400174d9  lea     rax, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400174e0  mov     qword ptr [rsp+0A0h+var_78], rax
0x1400174e5  mov     r8d, 5
0x1400174eb  lea     rax, WPP_48a527b79fd4344d8b4157379f595642_Traceguids
0x1400174f2  mov     dl, 2
0x1400174f4  mov     [rsp+0A0h+var_80], rax
0x1400174f9  mov     rcx, [rcx+40h]
0x1400174fd  call    WPP_RECORDER_SF_sDd
0x140017502  jmp     loc_140017408
0x140017507  cmp     [rcx+18h], r12w
0x14001750c  ja      short loc_1400174A5
0x14001750e  jmp     loc_1400173FE
0x140017513  mov     [rbp+4Fh+Context], rcx
0x140017517  lea     r8, [rbp+4Fh+Context]; Context
0x14001751b  mov     rcx, rax; Instance
0x14001751e  call    cs:__imp_FltGetStreamHandleContext
0x140017525  nop     dword ptr [rax+rax+00h]
0x14001752a  mov     edi, eax
0x14001752c  cmp     eax, 0C0000225h
0x140017531  jz      short loc_1400175A1
0x140017533  test    eax, eax
0x140017535  js      short loc_1400175A7
0x140017537  mov     r15, [rbp+4Fh+Context]
0x14001753b  mov     eax, [r15+50h]
0x14001753f  test    al, 1
0x140017541  jnz     short loc_140017555
0x140017543  mov     rcx, r15; Context
0x140017546  call    cs:__imp_FltReleaseContext
0x14001754d  nop     dword ptr [rax+rax+00h]
0x140017552  xor     r15d, r15d
0x140017555  xor     ecx, ecx; Context
0x140017557  mov     [rbp+4Fh+Context], rcx
0x14001755b  xor     edi, edi
0x14001755d  test    rcx, rcx
0x140017560  jz      short loc_14001756E
0x140017562  call    cs:__imp_FltReleaseContext
0x140017569  nop     dword ptr [rax+rax+00h]
0x14001756e  test    edi, edi
0x140017570  jns     loc_140017626
0x140017576  lea     rax, WPP_RECORDER_INITIALIZED
0x14001757d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017584  jz      loc_140017408
0x14001758a  mov     [rsp+38h], edi
0x14001758e  mov     r9d, 0Ah
0x140017594  mov     dword ptr [rsp+0A0h+var_70], 0A8h
0x14001759c  jmp     loc_1400174D2
0x1400175a1  mov     r15, [rbp+4Fh+Context]
0x1400175a5  jmp     short loc_140017555
0x1400175a7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400175ae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400175b5  jnz     short loc_1400175CE
0x1400175b7  mov     rcx, [rbp+4Fh+Context]
0x1400175bb  jmp     short loc_14001755D
0x1400175bd  call    cs:__imp_FltObjectDereference
0x1400175c4  nop     dword ptr [rax+rax+00h]
0x1400175c9  jmp     loc_14001742D
0x1400175ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175d5  lea     rax, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400175dc  mov     [rsp+38h], edi
0x1400175e0  mov     r9d, 19h
0x1400175e6  mov     dword ptr [rsp+0A0h+var_70], 4ADh
0x1400175ee  mov     r8d, 7
0x1400175f4  mov     qword ptr [rsp+0A0h+var_78], rax
0x1400175f9  mov     dl, 2
0x1400175fb  mov     rcx, [rcx+40h]
0x1400175ff  lea     rax, WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids
0x140017606  mov     [rsp+0A0h+var_80], rax
0x14001760b  call    WPP_RECORDER_SF_sDd
0x140017610  jmp     short loc_1400175B7
0x140017612  mov     rcx, r15; Context
0x140017615  call    cs:__imp_FltReleaseContext
0x14001761c  nop     dword ptr [rax+rax+00h]
0x140017621  jmp     loc_140017436
0x140017626  test    r15, r15
0x140017629  jz      loc_1400178EE
0x14001762f  mov     rcx, [r13+40h]
0x140017633  mov     rax, [rcx+18h]
0x140017637  test    rax, rax
0x14001763a  jz      short loc_140017646
0x14001763c  mov     edx, 6431h
0x140017641  cmp     [rax], dx
0x140017644  jz      short loc_14001764F
0x140017646  mov     rsi, [rbp+4Fh+Instance]
0x14001764a  mov     rdx, rsi
0x14001764d  jmp     short loc_140017666
0x14001764f  test    byte ptr [r15+50h], 1
0x140017654  jz      short loc_140017646
0x140017656  mov     rax, [rcx+20h]
0x14001765a  mov     rsi, [rbp+4Fh+Instance]
0x14001765e  mov     rcx, [rax+8]
0x140017662  mov     rdx, [rax+10h]
0x140017666  lea     rax, [rbp+4Fh+var_48]
0x14001766a  mov     r9, r15
0x14001766d  mov     qword ptr [rsp+0A0h+var_78], rax
0x140017672  mov     r8d, 1000102h
0x140017678  mov     [rsp+0A0h+var_80], rsi
0x14001767d  call    BfGeneratePostCreateName
0x140017682  mov     edi, eax
0x140017684  test    eax, eax
0x140017686  jns     short loc_1400176B3
0x140017688  lea     rax, WPP_RECORDER_INITIALIZED
0x14001768f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017696  jz      loc_140017408
0x14001769c  mov     [rsp+38h], edi
0x1400176a0  mov     r9d, 0Ch
0x1400176a6  mov     dword ptr [rsp+0A0h+var_70], 0DCh
0x1400176ae  jmp     loc_1400174D2
0x1400176b3  movzx   r8d, word ptr [rbp+4Fh+var_48]
0x1400176b8  mov     rax, [rbp+4Fh+var_48+8]
0x1400176bc  mov     ecx, r8d
0x1400176bf  shr     rcx, 1
0x1400176c2  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400176c8  jnz     loc_140017836
0x1400176ce  mov     byte ptr [rbp+4Fh+Context], r12b
0x1400176d2  add     r13, 58h ; 'X'
0x1400176d6  add     r8w, [r13+0]
0x1400176db  lea     rdx, [rbp+4Fh+P]
0x1400176df  movzx   ecx, r8w
0x1400176e3  mov     word ptr [rbp+4Fh+P+2], r8w
0x1400176e8  call    BfAllocateUnicodeString
0x1400176ed  mov     edi, eax
0x1400176ef  test    eax, eax
0x1400176f1  js      loc_140017408
0x1400176f7  lea     rdx, [rbp+4Fh+var_48]; Source
0x1400176fb  lea     rcx, [rbp+4Fh+P]; Destination
0x1400176ff  call    cs:__imp_RtlAppendUnicodeStringToString
0x140017706  nop     dword ptr [rax+rax+00h]
0x14001770b  mov     edi, eax
0x14001770d  test    eax, eax
0x14001770f  js      loc_140017408
0x140017715  cmp     byte ptr [rbp+4Fh+Context], r12b
0x140017719  jnz     loc_140017868
0x14001771f  mov     rdx, r13; Source
0x140017722  lea     rcx, [rbp+4Fh+P]; Destination
0x140017726  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001772d  nop     dword ptr [rax+rax+00h]
0x140017732  mov     edi, eax
0x140017734  test    eax, eax
0x140017736  js      loc_140017408
0x14001773c  mov     r13d, 78h ; 'x'
0x140017742  mov     r8d, 6D6E4642h
0x140017748  mov     edx, r13d
0x14001774b  mov     ecx, 100h
0x140017750  call    cs:__imp_ExAllocatePool2
0x140017757  nop     dword ptr [rax+rax+00h]
0x14001775c  mov     r12, rax
0x14001775f  test    rax, rax
0x140017762  jz      loc_14001788E
0x140017768  movups  xmm0, xmmword ptr [rbp+4Fh+P]
0x14001776c  lea     rdx, [rbp+4Fh+FltObject]; RetVolume
0x140017770  mov     rcx, rsi; Instance
0x140017773  movups  xmmword ptr [rax+8], xmm0
0x140017777  call    cs:__imp_FltGetVolumeFromInstance
0x14001777e  nop     dword ptr [rax+rax+00h]
0x140017783  mov     edi, eax
0x140017785  test    eax, eax
0x140017787  js      loc_140017898
0x14001778d  mov     rcx, [rbp+4Fh+FltObject]; Volume
0x140017791  lea     r8, [rbp+4Fh+BufferSizeNeeded]; BufferSizeNeeded
0x140017795  xor     edx, edx; VolumeName
0x140017797  call    cs:__imp_FltGetVolumeName
0x14001779e  nop     dword ptr [rax+rax+00h]
0x1400177a3  mov     ecx, 80000000h
0x1400177a8  mov     edi, eax
0x1400177aa  add     eax, ecx
0x1400177ac  test    ecx, eax
0x1400177ae  jz      short loc_140017803
0x1400177b0  mov     rax, [r12+10h]
0x1400177b5  mov     rcx, r12; FileNameInformation
0x1400177b8  mov     [r12+20h], rax
0x1400177bd  movzx   eax, word ptr [rbp+4Fh+BufferSizeNeeded]
0x1400177c1  mov     [r12+18h], ax
0x1400177c7  movzx   eax, word ptr [rbp+4Fh+BufferSizeNeeded]
0x1400177cb  mov     [r12+1Ah], ax
0x1400177d1  mov     [r12], r13d
0x1400177d5  mov     dword ptr [r12+4], 2
0x1400177de  call    cs:__imp_FltParseFileNameInformation
0x1400177e5  nop     dword ptr [rax+rax+00h]
0x1400177ea  mov     edi, eax
0x1400177ec  test    eax, eax
0x1400177ee  js      loc_1400178C3
0x1400177f4  mov     [rbx], r12
0x1400177f7  xor     r12d, r12d
0x1400177fa  mov     byte ptr [r14], 1
0x1400177fe  jmp     loc_140017408
0x140017803  cmp     edi, 0C0000023h
0x140017809  jz      short loc_1400177B0
0x14001780b  lea     rax, WPP_RECORDER_INITIALIZED
0x140017812  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017819  jz      loc_140017408
0x14001781f  mov     [rsp+38h], edi
0x140017823  mov     r9d, 0Eh
0x140017829  mov     dword ptr [rsp+0A0h+var_70], 123h
0x140017831  jmp     loc_1400174D2
0x140017836  lea     rax, [r13+58h]
0x14001783a  mov     [rbp+4Fh+Context], rax
0x14001783e  cmp     [rax], r12w
0x140017842  jz      loc_1400176CE
0x140017848  mov     rax, [r13+60h]
0x14001784c  cmp     word ptr [rax], 3Ah ; ':'
0x140017850  jz      loc_1400176CE
0x140017856  mov     r13, [rbp+4Fh+Context]
0x14001785a  add     r8w, 2
0x14001785f  mov     byte ptr [rbp+4Fh+Context], 1
0x140017863  jmp     loc_1400176D6
0x140017868  lea     rdx, Source; "\\"
0x14001786f  lea     rcx, [rbp+4Fh+P]; Destination
0x140017873  call    cs:__imp_RtlAppendUnicodeToString
0x14001787a  nop     dword ptr [rax+rax+00h]
0x14001787f  mov     edi, eax
  ... truncated ...
```
