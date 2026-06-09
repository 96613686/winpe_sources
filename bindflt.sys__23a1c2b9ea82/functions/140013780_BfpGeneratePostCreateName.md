# BfpGeneratePostCreateName

- ea: `0x140013780`
- end: `0x14001385e`
- name: `BfpGeneratePostCreateName`
- size: `222`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400127a0`
- `0x140012c60`

## callees

- `0x140001348`
- `0x140001dd0`
- `0x140013780`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400137dc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400137dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137f7`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x1400137bd`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x1400137bd`

## pseudocode

```c
__int64 __fastcall BfpGeneratePostCreateName(int a1, int a2, int a3, int a4, __int64 a5, PFLT_NAME_CONTROL NameCtrl)
{
  NTSTATUS Name; // ebx
  int v7; // edx
  NTSTATUS v9; // [rsp+38h] [rbp-20h]
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-18h] BYREF

  SourceString = 0;
  Name = BfGeneratePostCreateName(a1, a2, a3, a4, a5, (__int64)&SourceString);
  if ( Name >= 0 )
  {
    Name = FltCheckAndGrowNameControl(NameCtrl, SourceString.Length);
    if ( Name < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = Name;
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          9,
          35,
          (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
          111,
          v9);
      }
    }
    else
    {
      RtlCopyUnicodeString(&NameCtrl->Name, &SourceString);
    }
  }
  if ( SourceString.Buffer )
    ExFreePoolWithTag(SourceString.Buffer, 0x74734642u);
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x140013780  push    rbx
0x140013782  sub     rsp, 50h
0x140013786  lea     rax, [rsp+58h+SourceString]
0x14001378b  xorps   xmm0, xmm0
0x14001378e  mov     [rsp+58h+var_30], rax
0x140013793  mov     rax, [rsp+58h+arg_20]
0x14001379b  mov     [rsp+58h+var_38], rax
0x1400137a0  movups  xmmword ptr [rsp+58h+SourceString.Length], xmm0
0x1400137a5  call    BfGeneratePostCreateName
0x1400137aa  mov     ebx, eax
0x1400137ac  test    eax, eax
0x1400137ae  js      short loc_1400137E8
0x1400137b0  movzx   edx, [rsp+58h+SourceString.Length]; NewSize
0x1400137b5  mov     rcx, [rsp+58h+NameCtrl]; NameCtrl
0x1400137bd  call    cs:__imp_FltCheckAndGrowNameControl
0x1400137c4  nop     dword ptr [rax+rax+00h]
0x1400137c9  mov     ebx, eax
0x1400137cb  test    eax, eax
0x1400137cd  js      short loc_14001380C
0x1400137cf  mov     rcx, [rsp+58h+NameCtrl]; DestinationString
0x1400137d7  lea     rdx, [rsp+58h+SourceString]; SourceString
0x1400137dc  call    cs:__imp_RtlCopyUnicodeString
0x1400137e3  nop     dword ptr [rax+rax+00h]
0x1400137e8  mov     rcx, [rsp+58h+SourceString.Buffer]; P
0x1400137ed  test    rcx, rcx
0x1400137f0  jz      short loc_140013803
0x1400137f2  mov     edx, 74734642h; Tag
0x1400137f7  call    cs:__imp_ExFreePoolWithTag
0x1400137fe  nop     dword ptr [rax+rax+00h]
0x140013803  mov     eax, ebx
0x140013805  add     rsp, 50h
0x140013809  pop     rbx
0x14001380a  retn
0x14001380c  lea     rax, WPP_RECORDER_INITIALIZED
0x140013813  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001381a  jz      short loc_1400137E8
0x14001381c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013823  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001382a  mov     [rsp+58h+var_20], ebx
0x14001382e  mov     r9d, 23h ; '#'
0x140013834  mov     [rsp+58h+var_28], 36Fh
0x14001383c  mov     dl, 2
0x14001383e  mov     [rsp+58h+var_30], rax
0x140013843  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x14001384a  mov     rcx, [rcx+40h]
0x14001384e  lea     r8d, [r9-1Ah]
0x140013852  mov     [rsp+58h+var_38], rax
0x140013857  call    WPP_RECORDER_SF_sDd
0x14001385c  jmp     short loc_1400137E8
```
