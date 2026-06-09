# BfConvertWalkContextToDirectoryEnumeration

- ea: `0x14001ad80`
- end: `0x14001b277`
- name: `BfConvertWalkContextToDirectoryEnumeration`
- size: `1271`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140024e50`

## callees

- `0x140001348`
- `0x140019c20`
- `0x14001ad80`
- `0x14001bbb4`
- `0x140020d60`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14001aec9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001aec9`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14001ae8d`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14001ae8d`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14001ae4a`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14001ae4a`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14001aeb5`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14001aeb5`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14001ade3`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14001afcf`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14001b067`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14001b13b`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14001ade3`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14001afcf`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14001b067`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14001b13b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001ae67`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001ae67`

## pseudocode

```c
__int64 __fastcall BfConvertWalkContextToDirectoryEnumeration(
        UNICODE_STRING **a1,
        int a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6)
{
  __int64 result; // rax
  unsigned int v7; // edx
  unsigned __int8 v8; // bl
  _DWORD *v9; // rsi
  struct _UNICODE_STRING *v11; // r12
  UNICODE_STRING *v13; // r15
  UNICODE_STRING *v14; // rax
  UNICODE_STRING *v15; // rdi
  NTSTATUS v16; // ebx
  BOOLEAN IsNameInExpression; // bl
  _QWORD *v18; // rbx
  _QWORD *v19; // rax
  __int64 v20; // r14
  int DirectoryEntry; // eax
  int v22; // edx
  __int64 v23; // r8
  _QWORD *v24; // rbx
  _QWORD *v25; // rax
  __int64 v26; // rcx
  bool v27; // zf
  _QWORD *v28; // rax
  _QWORD *v29; // rbx
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // [rsp+38h] [rbp-60h]
  unsigned int v33; // [rsp+40h] [rbp-58h]
  _DWORD v34[3]; // [rsp+44h] [rbp-54h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-48h] BYREF
  char v36; // [rsp+A0h] [rbp+8h]

  result = (__int64)a6;
  v7 = 0;
  v8 = 1;
  v33 = 0;
  v9 = 0;
  v36 = 1;
  *a6 = 0;
  v11 = a3;
  memset(v34, 0, sizeof(v34));
LABEL_6:
  while ( 2 )
  {
    v13 = *a1;
    if ( *a1 == (UNICODE_STRING *)a1 )
      goto LABEL_47;
    if ( (UNICODE_STRING **)v13->Buffer != a1
      || (v14 = *(UNICODE_STRING **)&v13->Length, *(UNICODE_STRING **)(*(_QWORD *)&v13->Length + 8LL) != v13) )
    {
LABEL_72:
      __fastfail(3u);
    }
    *a1 = v14;
    v14->Buffer = (PWSTR)a1;
    if ( !LOBYTE(v13[6].Length) )
    {
      v18 = *(_QWORD **)(a4 + 88);
      LOBYTE(a3) = 0;
      if ( !v18 )
        goto LABEL_3;
      while ( 1 )
      {
        if ( (int)BfReturnedWalkContextAvlCompareRoutine(&v13[5], v18) < 0 )
        {
          v28 = (_QWORD *)*v18;
          if ( !*v18 )
          {
            LOBYTE(a3) = 0;
            goto LABEL_3;
          }
        }
        else
        {
          v28 = (_QWORD *)v18[1];
          if ( !v28 )
          {
            LOBYTE(a3) = 1;
LABEL_3:
            result = RtlAvlInsertNodeEx(a4 + 88, v18, a3, &v13[1]);
            v9 = *(_DWORD **)&v34[1];
LABEL_4:
            v7 = v33;
LABEL_5:
            v8 = v36;
            goto LABEL_6;
          }
        }
        v18 = v28;
      }
    }
    if ( v11 )
    {
      if ( FsRtlDoesNameContainWildCards(v11) )
      {
        DestinationString = 0;
        v16 = RtlUpcaseUnicodeString(&DestinationString, v11, 1u);
        if ( v16 < 0 )
        {
          result = BfDereferenceMappingListEntry(v13);
          v7 = v33;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v32) = v16;
            LOBYTE(v7) = 3;
            result = WPP_RECORDER_SF_sDd(
                       WPP_GLOBAL_Control->DeviceExtension,
                       v7,
                       12,
                       27,
                       (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
                       (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
                       231,
                       v32);
            goto LABEL_4;
          }
          goto LABEL_5;
        }
        v15 = v13 + 5;
        IsNameInExpression = FsRtlIsNameInExpression(&DestinationString, v13 + 5, 1u, 0);
        RtlFreeUnicodeString(&DestinationString);
        if ( !IsNameInExpression )
        {
LABEL_16:
          v18 = *(_QWORD **)(a4 + 88);
          LOBYTE(a3) = 0;
          if ( !v18 )
            goto LABEL_3;
          while ( 1 )
          {
            if ( (int)BfReturnedWalkContextAvlCompareRoutine(v15, v18) < 0 )
            {
              v19 = (_QWORD *)*v18;
              if ( !*v18 )
              {
                LOBYTE(a3) = 0;
                goto LABEL_3;
              }
            }
            else
            {
              v19 = (_QWORD *)v18[1];
              if ( !v19 )
              {
                LOBYTE(a3) = 1;
                goto LABEL_3;
              }
            }
            v18 = v19;
          }
        }
        v8 = v36;
      }
      else
      {
        v15 = v13 + 5;
        if ( RtlCompareUnicodeString(v11, v13 + 5, 1u) )
          goto LABEL_16;
      }
      v7 = v33;
    }
    else
    {
      v15 = v13 + 5;
    }
    v20 = v7;
    v34[0] = 0;
    DirectoryEntry = BfGenerateDirectoryEntry(
                       (int)v13,
                       v8,
                       a2,
                       *(_DWORD *)(a5 + 56) - v7,
                       (void *)(v7 + *(_QWORD *)(a5 + 64)),
                       (__int64)v34);
    if ( !v8 || DirectoryEntry != -2147483643 )
    {
      if ( DirectoryEntry != -1073741820 && DirectoryEntry != -2147483643 )
      {
        if ( DirectoryEntry >= 0 )
        {
          v24 = *(_QWORD **)(a4 + 88);
          LOBYTE(v23) = 0;
          if ( v24 )
          {
            while ( 1 )
            {
              if ( (int)BfReturnedWalkContextAvlCompareRoutine(v15, v24) < 0 )
              {
                v25 = (_QWORD *)*v24;
                if ( !*v24 )
                  goto LABEL_42;
              }
              else
              {
                v25 = (_QWORD *)v24[1];
                if ( !v25 )
                  goto LABEL_31;
              }
              v24 = v25;
            }
          }
LABEL_32:
          RtlAvlInsertNodeEx(a4 + 88, v24, v23, &v13[1]);
          goto LABEL_33;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v32) = DirectoryEntry;
          LOBYTE(v22) = 3;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v22,
            12,
            28,
            (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
            60,
            v32);
        }
        v24 = *(_QWORD **)(a4 + 88);
        LOBYTE(v23) = 0;
        v34[0] = 0;
        if ( !v24 )
          goto LABEL_32;
        while ( 1 )
        {
          if ( (int)BfReturnedWalkContextAvlCompareRoutine(v15, v24) < 0 )
          {
            v31 = (_QWORD *)*v24;
            if ( !*v24 )
            {
LABEL_42:
              LOBYTE(v23) = 0;
              goto LABEL_32;
            }
          }
          else
          {
            v31 = (_QWORD *)v24[1];
            if ( !v31 )
            {
LABEL_31:
              LOBYTE(v23) = 1;
              goto LABEL_32;
            }
          }
          v24 = v31;
        }
      }
      result = (__int64)*a1;
      if ( (UNICODE_STRING **)(*a1)->Buffer == a1 )
      {
        v7 = v33;
        *(_QWORD *)&v13->Length = result;
        v13->Buffer = (PWSTR)a1;
        *(_QWORD *)(result + 8) = v13;
        *a1 = v13;
LABEL_47:
        v26 = a5;
        break;
      }
      goto LABEL_72;
    }
    v29 = *(_QWORD **)(a4 + 88);
    LOBYTE(v23) = 0;
    if ( !v29 )
      goto LABEL_57;
    while ( (int)BfReturnedWalkContextAvlCompareRoutine(v15, v29) >= 0 )
    {
      v30 = (_QWORD *)v29[1];
      if ( !v30 )
      {
        LOBYTE(v23) = 1;
        goto LABEL_57;
      }
LABEL_55:
      v29 = v30;
    }
    v30 = (_QWORD *)*v29;
    if ( *v29 )
      goto LABEL_55;
    LOBYTE(v23) = 0;
LABEL_57:
    RtlAvlInsertNodeEx(a4 + 88, v29, v23, &v13[1]);
    *a6 = 1;
LABEL_33:
    v7 = v34[0] + v33;
    v26 = a5;
    result = (__int64)a6;
    v33 += v34[0];
    v9 = (_DWORD *)(v20 + *(_QWORD *)(a5 + 64));
    v27 = *a6 == 0;
    *(_QWORD *)&v34[1] = v9;
    if ( v27 )
    {
      v8 = 0;
      v36 = 0;
      continue;
    }
    break;
  }
  if ( v9 )
    *v9 = 0;
  *(_DWORD *)(v26 + 52) = 0;
  *(_DWORD *)(v26 + 48) = v7;
  return result;
}

```

## disassembly

```asm
0x14001ad80  mov     [rsp+arg_10], rbx
0x14001ad85  mov     [rsp+arg_8], edx
0x14001ad89  push    rbp
0x14001ad8a  push    rsi
0x14001ad8b  push    rdi
0x14001ad8c  push    r12
0x14001ad8e  push    r13
0x14001ad90  push    r14
0x14001ad92  push    r15
0x14001ad94  sub     rsp, 60h
0x14001ad98  mov     rax, [rsp+98h+arg_28]
0x14001ada0  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001ada7  xor     edx, edx
0x14001ada9  lea     r14, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001adb0  mov     bl, 1
0x14001adb2  mov     [rsp+98h+var_58], edx
0x14001adb6  xor     esi, esi
0x14001adb8  mov     [rsp+98h+arg_0], bl
0x14001adbf  mov     [rax], dl
0x14001adc1  mov     r13, r9
0x14001adc4  mov     r12, r8
0x14001adc7  mov     qword ptr [rsp+98h+var_54+4], rsi
0x14001adcc  mov     rbp, rcx
0x14001adcf  mov     dword ptr [rsp+98h+var_54], edx
0x14001add3  jmp     short loc_14001AE07
0x14001add5  mov     r8b, 1
0x14001add8  lea     r9, [r15+10h]
0x14001addc  mov     rdx, rbx
0x14001addf  lea     rcx, [r13+58h]
0x14001ade3  call    cs:__imp_RtlAvlInsertNodeEx
0x14001adea  nop     dword ptr [rax+rax+00h]
0x14001adef  mov     rsi, qword ptr [rsp+98h+var_54+4]
0x14001adf4  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001adfb  mov     edx, [rsp+98h+var_58]
0x14001adff  movzx   ebx, [rsp+98h+arg_0]
0x14001ae07  mov     r15, [rbp+0]
0x14001ae0b  cmp     r15, rbp
0x14001ae0e  jz      loc_14001B0BF
0x14001ae14  cmp     [r15+8], rbp
0x14001ae18  jnz     loc_14001B270
0x14001ae1e  mov     rax, [r15]
0x14001ae21  cmp     [rax+8], r15
0x14001ae25  jnz     loc_14001B270
0x14001ae2b  mov     [rbp+0], rax
0x14001ae2f  mov     [rax+8], rbp
0x14001ae33  cmp     byte ptr [r15+60h], 0
0x14001ae38  jz      loc_14001B028
0x14001ae3e  test    r12, r12
0x14001ae41  jz      loc_14001AF21
0x14001ae47  mov     rcx, r12; Name
0x14001ae4a  call    cs:__imp_FsRtlDoesNameContainWildCards
0x14001ae51  nop     dword ptr [rax+rax+00h]
0x14001ae56  mov     r8b, 1; AllocateDestinationString
0x14001ae59  test    al, al
0x14001ae5b  jnz     short loc_14001AE7D
0x14001ae5d  lea     rdi, [r15+50h]
0x14001ae61  mov     rcx, r12; String1
0x14001ae64  mov     rdx, rdi; String2
0x14001ae67  call    cs:__imp_RtlCompareUnicodeString
0x14001ae6e  nop     dword ptr [rax+rax+00h]
0x14001ae73  test    eax, eax
0x14001ae75  jz      loc_14001B20C
0x14001ae7b  jmp     short loc_14001AEDD
0x14001ae7d  xorps   xmm0, xmm0
0x14001ae80  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14001ae85  mov     rdx, r12; SourceString
0x14001ae88  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x14001ae8d  call    cs:__imp_RtlUpcaseUnicodeString
0x14001ae94  nop     dword ptr [rax+rax+00h]
0x14001ae99  mov     ebx, eax
0x14001ae9b  test    eax, eax
0x14001ae9d  js      loc_14001B1AB
0x14001aea3  lea     rdi, [r15+50h]
0x14001aea7  xor     r9d, r9d; UpcaseTable
0x14001aeaa  mov     rdx, rdi; Name
0x14001aead  lea     rcx, [rsp+98h+DestinationString]; Expression
0x14001aeb2  mov     r8b, 1; IgnoreCase
0x14001aeb5  call    cs:__imp_FsRtlIsNameInExpression
0x14001aebc  nop     dword ptr [rax+rax+00h]
0x14001aec1  lea     rcx, [rsp+98h+DestinationString]; UnicodeString
0x14001aec6  movzx   ebx, al
0x14001aec9  call    cs:__imp_RtlFreeUnicodeString
0x14001aed0  nop     dword ptr [rax+rax+00h]
0x14001aed5  test    bl, bl
0x14001aed7  jnz     loc_14001B204
0x14001aedd  mov     rbx, [r13+58h]
0x14001aee1  xor     r8b, r8b
0x14001aee4  test    rbx, rbx
0x14001aee7  jz      loc_14001ADD8
0x14001aeed  nop     dword ptr [rax]
0x14001aef0  mov     rdx, rbx
0x14001aef3  mov     rcx, rdi
0x14001aef6  call    BfReturnedWalkContextAvlCompareRoutine
0x14001aefb  test    eax, eax
0x14001aefd  js      short loc_14001AF11
0x14001aeff  mov     rax, [rbx+8]
0x14001af03  test    rax, rax
0x14001af06  jz      loc_14001ADD5
0x14001af0c  mov     rbx, rax
0x14001af0f  jmp     short loc_14001AEF0
0x14001af11  mov     rax, [rbx]
0x14001af14  test    rax, rax
0x14001af17  jnz     short loc_14001AF0C
0x14001af19  xor     r8b, r8b
0x14001af1c  jmp     loc_14001ADD8
0x14001af21  lea     rdi, [r15+50h]
0x14001af25  mov     r8, [rsp+98h+arg_20]
0x14001af2d  lea     rax, [rsp+98h+var_54]
0x14001af32  mov     r14d, edx
0x14001af35  mov     [rsp+98h+var_70], rax; __int64
0x14001af3a  mov     dword ptr [rsp+98h+var_54], 0
0x14001af42  mov     rcx, [r8+40h]
0x14001af46  mov     r9d, [r8+38h]
0x14001af4a  add     rcx, r14
0x14001af4d  mov     r8d, [rsp+98h+arg_8]; int
0x14001af55  sub     r9d, edx; int
0x14001af58  mov     [rsp+98h+var_78], rcx; void *
0x14001af5d  movzx   edx, bl; int
0x14001af60  mov     rcx, r15; int
0x14001af63  call    BfGenerateDirectoryEntry
0x14001af68  test    bl, bl
0x14001af6a  jnz     loc_14001B0F5
0x14001af70  cmp     eax, 0C0000004h
0x14001af75  jz      loc_14001B09E
0x14001af7b  cmp     eax, 80000005h
0x14001af80  jz      loc_14001B09E
0x14001af86  test    eax, eax
0x14001af88  js      loc_14001B215
0x14001af8e  mov     rbx, [r13+58h]
0x14001af92  xor     r8b, r8b
0x14001af95  test    rbx, rbx
0x14001af98  jz      short loc_14001AFC4
0x14001af9a  nop     word ptr [rax+rax+00h]
0x14001afa0  mov     rdx, rbx
0x14001afa3  mov     rcx, rdi
0x14001afa6  call    BfReturnedWalkContextAvlCompareRoutine
0x14001afab  test    eax, eax
0x14001afad  js      loc_14001B07D
0x14001afb3  mov     rax, [rbx+8]
0x14001afb7  test    rax, rax
0x14001afba  jz      short loc_14001AFC1
0x14001afbc  mov     rbx, rax
0x14001afbf  jmp     short loc_14001AFA0
0x14001afc1  mov     r8b, 1
0x14001afc4  lea     r9, [r15+10h]
0x14001afc8  mov     rdx, rbx
0x14001afcb  lea     rcx, [r13+58h]
0x14001afcf  call    cs:__imp_RtlAvlInsertNodeEx
0x14001afd6  nop     dword ptr [rax+rax+00h]
0x14001afdb  mov     edx, [rsp+98h+var_58]
0x14001afdf  add     edx, dword ptr [rsp+98h+var_54]
0x14001afe3  mov     rcx, [rsp+98h+arg_20]
0x14001afeb  mov     rax, [rsp+98h+arg_28]
0x14001aff3  mov     [rsp+98h+var_58], edx
0x14001aff7  mov     rsi, [rcx+40h]
0x14001affb  add     rsi, r14
0x14001affe  cmp     byte ptr [rax], 0
0x14001b001  mov     qword ptr [rsp+98h+var_54+4], rsi
0x14001b006  jnz     loc_14001B0C7
0x14001b00c  xor     bl, bl
0x14001b00e  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001b015  mov     [rsp+98h+arg_0], bl
0x14001b01c  lea     r14, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001b023  jmp     loc_14001AE07
0x14001b028  mov     rbx, [r13+58h]
0x14001b02c  xor     r8b, r8b
0x14001b02f  test    rbx, rbx
0x14001b032  jz      short loc_14001B05C
0x14001b034  mov     rdx, rbx
0x14001b037  lea     rcx, [r15+50h]
0x14001b03b  call    BfReturnedWalkContextAvlCompareRoutine
0x14001b040  test    eax, eax
0x14001b042  js      short loc_14001B091
0x14001b044  mov     rax, [rbx+8]
0x14001b048  test    rax, rax
0x14001b04b  jz      short loc_14001B052
0x14001b04d  mov     rbx, rax
0x14001b050  jmp     short loc_14001B034
0x14001b052  mov     r8b, 1
0x14001b055  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001b05c  lea     r9, [r15+10h]
0x14001b060  mov     rdx, rbx
0x14001b063  lea     rcx, [r13+58h]
0x14001b067  call    cs:__imp_RtlAvlInsertNodeEx
0x14001b06e  nop     dword ptr [rax+rax+00h]
0x14001b073  mov     rsi, qword ptr [rsp+98h+var_54+4]
0x14001b078  jmp     loc_14001ADFB
0x14001b07d  mov     rax, [rbx]
0x14001b080  test    rax, rax
0x14001b083  jnz     loc_14001AFBC
0x14001b089  xor     r8b, r8b
0x14001b08c  jmp     loc_14001AFC4
0x14001b091  mov     rax, [rbx]
0x14001b094  test    rax, rax
0x14001b097  jnz     short loc_14001B04D
0x14001b099  xor     r8b, r8b
0x14001b09c  jmp     short loc_14001B055
0x14001b09e  mov     rax, [rbp+0]
0x14001b0a2  cmp     [rax+8], rbp
0x14001b0a6  jnz     loc_14001B270
0x14001b0ac  mov     edx, [rsp+98h+var_58]
0x14001b0b0  mov     [r15], rax
0x14001b0b3  mov     [r15+8], rbp
0x14001b0b7  mov     [rax+8], r15
0x14001b0bb  mov     [rbp+0], r15
0x14001b0bf  mov     rcx, [rsp+98h+arg_20]
0x14001b0c7  test    rsi, rsi
0x14001b0ca  jz      short loc_14001B0D2
0x14001b0cc  mov     dword ptr [rsi], 0
0x14001b0d2  mov     rbx, [rsp+98h+arg_10]
0x14001b0da  mov     dword ptr [rcx+34h], 0
0x14001b0e1  mov     [rcx+30h], edx
0x14001b0e4  add     rsp, 60h
0x14001b0e8  pop     r15
0x14001b0ea  pop     r14
0x14001b0ec  pop     r13
0x14001b0ee  pop     r12
0x14001b0f0  pop     rdi
0x14001b0f1  pop     rsi
0x14001b0f2  pop     rbp
0x14001b0f3  retn
0x14001b0f5  cmp     eax, 80000005h
0x14001b0fa  jnz     loc_14001AF70
0x14001b100  mov     rbx, [r13+58h]
0x14001b104  xor     r8b, r8b
0x14001b107  test    rbx, rbx
0x14001b10a  jz      short loc_14001B130
0x14001b10c  nop     dword ptr [rax+00h]
0x14001b110  mov     rdx, rbx
0x14001b113  mov     rcx, rdi
0x14001b116  call    BfReturnedWalkContextAvlCompareRoutine
0x14001b11b  test    eax, eax
0x14001b11d  js      short loc_14001B157
0x14001b11f  mov     rax, [rbx+8]
0x14001b123  test    rax, rax
0x14001b126  jz      short loc_14001B12D
0x14001b128  mov     rbx, rax
0x14001b12b  jmp     short loc_14001B110
0x14001b12d  mov     r8b, 1
0x14001b130  lea     r9, [r15+10h]
0x14001b134  mov     rdx, rbx
0x14001b137  lea     rcx, [r13+58h]
0x14001b13b  call    cs:__imp_RtlAvlInsertNodeEx
0x14001b142  nop     dword ptr [rax+rax+00h]
0x14001b147  mov     rax, [rsp+98h+arg_28]
0x14001b14f  mov     byte ptr [rax], 1
0x14001b152  jmp     loc_14001AFDB
0x14001b157  mov     rax, [rbx]
0x14001b15a  test    rax, rax
0x14001b15d  jnz     short loc_14001B128
0x14001b15f  xor     r8b, r8b
0x14001b162  jmp     short loc_14001B130
0x14001b164  mov     rbx, [r13+58h]
0x14001b168  xor     r8b, r8b
0x14001b16b  mov     dword ptr [rsp+98h+var_54], 0
0x14001b173  test    rbx, rbx
0x14001b176  jz      loc_14001AFC4
0x14001b17c  mov     rdx, rbx
0x14001b17f  mov     rcx, rdi
0x14001b182  call    BfReturnedWalkContextAvlCompareRoutine
0x14001b187  test    eax, eax
0x14001b189  js      short loc_14001B19D
0x14001b18b  mov     rax, [rbx+8]
0x14001b18f  test    rax, rax
0x14001b192  jz      loc_14001AFC1
0x14001b198  mov     rbx, rax
0x14001b19b  jmp     short loc_14001B17C
0x14001b19d  mov     rax, [rbx]
0x14001b1a0  test    rax, rax
0x14001b1a3  jz      loc_14001B089
0x14001b1a9  jmp     short loc_14001B198
0x14001b1ab  mov     rcx, r15; Entry
0x14001b1ae  call    BfDereferenceMappingListEntry
0x14001b1b3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001b1ba  mov     edx, [rsp+98h+var_58]
0x14001b1be  jz      loc_14001ADFF
0x14001b1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b1cb  lea     rax, WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids
0x14001b1d2  mov     dword ptr [rsp+98h+var_60], ebx
0x14001b1d6  mov     r9d, 1Bh
0x14001b1dc  mov     [rsp+98h+var_68], 6E7h
0x14001b1e4  mov     r8d, 0Ch
0x14001b1ea  mov     [rsp+98h+var_70], r14
0x14001b1ef  mov     dl, 3
0x14001b1f1  mov     rcx, [rcx+40h]
0x14001b1f5  mov     [rsp+98h+var_78], rax
0x14001b1fa  call    WPP_RECORDER_SF_sDd
0x14001b1ff  jmp     loc_14001ADFB
0x14001b204  movzx   ebx, [rsp+98h+arg_0]
0x14001b20c  mov     edx, [rsp+98h+var_58]
0x14001b210  jmp     loc_14001AF25
0x14001b215  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001b21c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001b223  jz      loc_14001B164
0x14001b229  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b230  mov     r9d, 1Ch
0x14001b236  mov     dword ptr [rsp+98h+var_60], eax
0x14001b23a  mov     r8d, 0Ch
0x14001b240  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001b247  mov     [rsp+98h+var_68], 73Ch
  ... truncated ...
```
