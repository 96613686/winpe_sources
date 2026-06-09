# BfFormatPathFromFileNameInfo

- ea: `0x140017bf0`
- end: `0x140017ef8`
- name: `BfFormatPathFromFileNameInfo`
- size: `776`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001dd0`
- `0x140012c60`
- `0x1400152f0`
- `0x1400157a0`
- `0x140017f00`
- `0x1400194b0`

## callees

- `0x140001348`
- `0x140003304`
- `0x140017bf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140017dcf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017dcf`
- `ntoskrnl!ExAllocatePool2` at `0x140017ca6`
- `ntoskrnl!ExAllocatePool2` at `0x140017ca6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140017cd3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140017cf0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140017df5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140017cd3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140017cf0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140017df5`
- `FLTMGR!FltParseFileNameInformation` at `0x140017d1e`
- `FLTMGR!FltParseFileNameInformation` at `0x140017d1e`

## pseudocode

```c
NTSTATUS __fastcall BfFormatPathFromFileNameInfo(__int64 a1, char a2, struct _UNICODE_STRING *a3, __int64 a4)
{
  unsigned __int16 v7; // ax
  unsigned __int16 v8; // cx
  unsigned __int16 v9; // di
  NTSTATUS appended; // edi
  __int64 Pool2; // rax
  int v12; // edx
  NTSTATUS result; // eax
  unsigned __int16 v14; // ax
  PWSTR Buffer; // rcx
  int v16; // r9d
  char v17; // [rsp+30h] [rbp-48h]
  int v18; // [rsp+38h] [rbp-40h]

  if ( (*(_BYTE *)(a1 + 2) & 9) != 9 )
  {
    appended = FltParseFileNameInformation((PFLT_FILE_NAME_INFORMATION)a1);
    if ( appended < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v18 = appended;
        v16 = 37;
        v17 = 31;
        goto LABEL_34;
      }
      goto LABEL_25;
    }
    if ( (*(_BYTE *)(a1 + 2) & 9) != 9 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sD(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          8,
          38,
          (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
          38);
      appended = -1073741811;
      goto LABEL_25;
    }
  }
  v7 = *(_WORD *)(a1 + 104);
  v8 = *(_WORD *)(a1 + 88) + v7;
  if ( v8 < v7 )
    goto LABEL_5;
  if ( !a2 )
  {
    v9 = *(_WORD *)(a1 + 88) + v7;
    goto LABEL_10;
  }
  v14 = *(_WORD *)(a1 + 40) + v8;
  v9 = v14 >= v8 ? *(_WORD *)(a1 + 40) + v8 : -1;
  if ( v14 < v8 )
  {
LABEL_5:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        8,
        39,
        (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
        62);
    appended = -1073741562;
    goto LABEL_25;
  }
LABEL_10:
  *(_DWORD *)&a3->Length = 0;
  if ( !v9 )
    v9 = 1;
  Pool2 = ExAllocatePool2(256, v9, 1953711682, a4);
  a3->Buffer = (PWSTR)Pool2;
  if ( Pool2 )
  {
    a3->MaximumLength = v9;
    if ( a2 && (appended = RtlAppendUnicodeStringToString(a3, (PCUNICODE_STRING)(a1 + 40)), appended < 0) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v18 = appended;
        v16 = 41;
        v17 = 81;
LABEL_34:
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          8,
          v16,
          (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
          v17,
          v18);
      }
    }
    else
    {
      appended = RtlAppendUnicodeStringToString(a3, (PCUNICODE_STRING)(a1 + 104));
      if ( appended < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_25;
        v18 = appended;
        v16 = 42;
        v17 = 90;
        goto LABEL_34;
      }
      result = RtlAppendUnicodeStringToString(a3, (PCUNICODE_STRING)(a1 + 88));
      appended = result;
      if ( result >= 0 )
        return result;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v18 = result;
        v16 = 43;
        v17 = 98;
        goto LABEL_34;
      }
    }
  }
  else
  {
    appended = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v18 = -1073741670;
      v16 = 40;
      v17 = 71;
      goto LABEL_34;
    }
  }
LABEL_25:
  Buffer = a3->Buffer;
  if ( Buffer )
  {
    ExFreePoolWithTag(Buffer, 0x74734642u);
    a3->Buffer = 0;
  }
  *(_DWORD *)&a3->Length = 0;
  return appended;
}

```

## disassembly

```asm
0x140017bf0  push    rbx
0x140017bf2  push    rbp
0x140017bf3  push    rsi
0x140017bf4  push    rdi
0x140017bf5  push    r14
0x140017bf7  push    r15
0x140017bf9  sub     rsp, 48h
0x140017bfd  movzx   eax, byte ptr [rcx+2]
0x140017c01  mov     rbx, r8
0x140017c04  and     al, 9
0x140017c06  movzx   ebp, dl
0x140017c09  mov     rsi, rcx
0x140017c0c  cmp     al, 9
0x140017c0e  jnz     loc_140017D1E
0x140017c14  movzx   eax, word ptr [rsi+68h]
0x140017c18  movzx   ecx, ax
0x140017c1b  add     cx, [rsi+58h]
0x140017c1f  cmp     cx, ax
0x140017c22  jb      short loc_140017C32
0x140017c24  test    bpl, bpl
0x140017c27  jnz     loc_140017D93
0x140017c2d  movzx   edi, cx
0x140017c30  jmp     short loc_140017C8F
0x140017c32  lea     rax, WPP_RECORDER_INITIALIZED
0x140017c39  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017c40  jz      short loc_140017C80
0x140017c42  mov     rcx, cs:WPP_GLOBAL_Control
0x140017c49  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140017c50  mov     dword ptr [rsp+78h+var_48], 73Eh
0x140017c58  mov     r9d, 27h ; '''
0x140017c5e  mov     [rsp+78h+var_50], rax
0x140017c63  mov     r8d, 8
0x140017c69  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x140017c70  mov     dl, 2
0x140017c72  mov     rcx, [rcx+40h]
0x140017c76  mov     [rsp+78h+var_58], rax
0x140017c7b  call    WPP_RECORDER_SF_sD
0x140017c80  mov     edi, 0C0000106h
0x140017c85  jmp     loc_140017DC1
0x140017c8a  movzx   edi, ax
0x140017c8d  jb      short loc_140017C32
0x140017c8f  xor     eax, eax
0x140017c91  mov     [rbx], eax
0x140017c93  test    di, di
0x140017c96  jz      short loc_140017D14
0x140017c98  movzx   edx, di
0x140017c9b  mov     ecx, 100h
0x140017ca0  mov     r8d, 74734642h
0x140017ca6  call    cs:__imp_ExAllocatePool2
0x140017cad  nop     dword ptr [rax+rax+00h]
0x140017cb2  mov     [rbx+8], rax
0x140017cb6  test    rax, rax
0x140017cb9  jz      loc_140017E2F
0x140017cbf  mov     [rbx+2], di
0x140017cc3  test    bpl, bpl
0x140017cc6  jnz     loc_140017DEE
0x140017ccc  lea     rdx, [rsi+68h]; Source
0x140017cd0  mov     rcx, rbx; Destination
0x140017cd3  call    cs:__imp_RtlAppendUnicodeStringToString
0x140017cda  nop     dword ptr [rax+rax+00h]
0x140017cdf  mov     edi, eax
0x140017ce1  test    eax, eax
0x140017ce3  js      loc_140017EB7
0x140017ce9  lea     rdx, [rsi+58h]; Source
0x140017ced  mov     rcx, rbx; Destination
0x140017cf0  call    cs:__imp_RtlAppendUnicodeStringToString
0x140017cf7  nop     dword ptr [rax+rax+00h]
0x140017cfc  mov     edi, eax
0x140017cfe  test    eax, eax
0x140017d00  js      loc_140017EDF
0x140017d06  add     rsp, 48h
0x140017d0a  pop     r15
0x140017d0c  pop     r14
0x140017d0e  pop     rdi
0x140017d0f  pop     rsi
0x140017d10  pop     rbp
0x140017d11  pop     rbx
0x140017d12  retn
0x140017d14  mov     edi, 1
0x140017d19  jmp     loc_140017C98
0x140017d1e  call    cs:__imp_FltParseFileNameInformation
0x140017d25  nop     dword ptr [rax+rax+00h]
0x140017d2a  mov     edi, eax
0x140017d2c  test    eax, eax
0x140017d2e  js      short loc_140017DAD
0x140017d30  movzx   eax, byte ptr [rsi+2]
0x140017d34  and     al, 9
0x140017d36  cmp     al, 9
0x140017d38  jz      loc_140017C14
0x140017d3e  lea     rax, WPP_RECORDER_INITIALIZED
0x140017d45  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017d4c  jz      short loc_140017D8C
0x140017d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d55  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140017d5c  mov     dword ptr [rsp+78h+var_48], 726h
0x140017d64  mov     r9d, 26h ; '&'
0x140017d6a  mov     [rsp+78h+var_50], rax
0x140017d6f  mov     r8d, 8
0x140017d75  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x140017d7c  mov     dl, 2
0x140017d7e  mov     rcx, [rcx+40h]
0x140017d82  mov     [rsp+78h+var_58], rax
0x140017d87  call    WPP_RECORDER_SF_sD
0x140017d8c  mov     edi, 0C000000Dh
0x140017d91  jmp     short loc_140017DC1
0x140017d93  movzx   eax, cx
0x140017d96  add     ax, [rsi+28h]
0x140017d9a  cmp     ax, cx
0x140017d9d  jnb     loc_140017C8A
0x140017da3  mov     edi, 0FFFFh
0x140017da8  jmp     loc_140017C8D
0x140017dad  lea     rax, WPP_RECORDER_INITIALIZED
0x140017db4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017dbb  jnz     loc_140017E5C
0x140017dc1  mov     rcx, [rbx+8]; P
0x140017dc5  test    rcx, rcx
0x140017dc8  jz      short loc_140017DE3
0x140017dca  mov     edx, 74734642h; Tag
0x140017dcf  call    cs:__imp_ExFreePoolWithTag
0x140017dd6  nop     dword ptr [rax+rax+00h]
0x140017ddb  mov     qword ptr [rbx+8], 0
0x140017de3  xor     eax, eax
0x140017de5  mov     [rbx], eax
0x140017de7  mov     eax, edi
0x140017de9  jmp     loc_140017D06
0x140017dee  lea     rdx, [rsi+28h]; Source
0x140017df2  mov     rcx, rbx; Destination
0x140017df5  call    cs:__imp_RtlAppendUnicodeStringToString
0x140017dfc  nop     dword ptr [rax+rax+00h]
0x140017e01  mov     edi, eax
0x140017e03  test    eax, eax
0x140017e05  jns     loc_140017CCC
0x140017e0b  lea     rax, WPP_RECORDER_INITIALIZED
0x140017e12  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017e19  jz      short loc_140017DC1
0x140017e1b  mov     [rsp+78h+var_40], edi
0x140017e1f  mov     r9d, 29h ; ')'
0x140017e25  mov     dword ptr [rsp+78h+var_48], 751h
0x140017e2d  jmp     short loc_140017E82
0x140017e2f  mov     edi, 0C000009Ah
0x140017e34  lea     rax, WPP_RECORDER_INITIALIZED
0x140017e3b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017e42  jz      loc_140017DC1
0x140017e48  mov     [rsp+78h+var_40], edi
0x140017e4c  mov     r9d, 28h ; '('
0x140017e52  mov     dword ptr [rsp+78h+var_48], 747h
0x140017e5a  jmp     short loc_140017E82
0x140017e5c  mov     [rsp+78h+var_40], edi
0x140017e60  mov     r9d, 25h ; '%'
0x140017e66  mov     dword ptr [rsp+78h+var_48], 71Fh
0x140017e6e  jmp     short loc_140017E82
0x140017e70  mov     [rsp+78h+var_40], edi
0x140017e74  mov     r9d, 2Bh ; '+'
0x140017e7a  mov     dword ptr [rsp+78h+var_48], 762h
0x140017e82  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e89  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140017e90  mov     [rsp+78h+var_50], rax
0x140017e95  mov     r8d, 8
0x140017e9b  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x140017ea2  mov     dl, 2
0x140017ea4  mov     [rsp+78h+var_58], rax
0x140017ea9  mov     rcx, [rcx+40h]
0x140017ead  call    WPP_RECORDER_SF_sDd
0x140017eb2  jmp     loc_140017DC1
0x140017eb7  lea     rax, WPP_RECORDER_INITIALIZED
0x140017ebe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017ec5  jz      loc_140017DC1
0x140017ecb  mov     [rsp+78h+var_40], edi
0x140017ecf  mov     r9d, 2Ah ; '*'
0x140017ed5  mov     dword ptr [rsp+78h+var_48], 75Ah
0x140017edd  jmp     short loc_140017E82
0x140017edf  lea     rax, WPP_RECORDER_INITIALIZED
0x140017ee6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017eed  jz      loc_140017DC1
0x140017ef3  jmp     loc_140017E70
```
