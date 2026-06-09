# FltReleaseFileNameInformation

- ea: `0x1800629c0`
- end: `0x180062b69`
- name: `FltReleaseFileNameInformation`
- size: `425`
- prototype: `void __stdcall(PFLT_FILE_NAME_INFORMATION FileNameInformation)`
- caller_count: `13`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000eb80`
- `0x180022e0c`
- `0x180058640`
- `0x180059a00`
- `0x18005b4b0`
- `0x18005e410`
- `0x180061760`
- `0x180061e00`
- `0x180062050`
- `0x180062510`
- `0x180062db0`
- `0x1800761f0`
- `0x180087810`

## callees

- `0x1800148b0`
- `0x180014cf0`
- `0x1800228fc`
- `0x1800629c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180062a98`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062a98`
- `ntoskrnl!KeBugCheckEx` at `0x180062ad9`
- `ntoskrnl!KeBugCheckEx` at `0x180062ad9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180062a70`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180062b4e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180062a70`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180062b4e`

## pseudocode

```c
void __stdcall FltReleaseFileNameInformation(PFLT_FILE_NAME_INFORMATION FileNameInformation)
{
  int v1; // r8d
  int Buffer; // ecx
  __int64 MaximumLength; // rax
  unsigned __int64 v5; // rax
  _UNICODE_STRING *p_Share; // rdx
  unsigned __int64 v7; // rax
  ULONG v8; // edx

  if ( (byte_180040A43 & 8) != 0 )
    McTemplateU0sp_EtwWriteTransfer(
      FileNameInformation,
      NameCacheSup_c6404,
      "FltReleaseFileNameInformation",
      FileNameInformation);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&FileNameInformation[1], 0xFFFFFFFF) <= 1 )
  {
    if ( ((__int64)FileNameInformation[-1].ParentDir.Buffer & 0x1E000) != 0 )
      KeBugCheckEx(0xF5u, 0x68u, (ULONG_PTR)&FileNameInformation[-1].Share, (ULONG_PTR)FileNameInformation, 0);
    if ( (byte_180040A43 & 8) != 0 )
      McTemplateU0s_EtwWriteTransfer(FileNameInformation, NameCacheSup_c6433, "FltReleaseFileNameInformation");
    if ( (byte_180040A43 & 2) != 0 )
      McTemplateU0spdw_EtwWriteTransfer(
        (unsigned __int16)LODWORD(FileNameInformation[-1].ParentDir.Buffer),
        FileNameInformation->Name.Length >> 1,
        v1,
        (_DWORD)FileNameInformation - 80,
        (char)FileNameInformation[-1].ParentDir.Buffer,
        FileNameInformation->Name.Length >> 1,
        (__int64)FileNameInformation->Name.Buffer);
    Buffer = (int)FileNameInformation[-1].ParentDir.Buffer;
    if ( (Buffer & 0x1000) != 0 )
    {
      MaximumLength = FileNameInformation[-1].Share.MaximumLength;
      if ( (unsigned __int16)MaximumLength <= 0x150u )
        LOWORD(v5) = 0;
      else
        v5 = (unsigned __int64)(MaximumLength - 273) >> 6;
      p_Share = &FileNameInformation[-1].Share;
      v7 = (unsigned __int64)(unsigned __int16)v5 << 7;
      if ( (Buffer & 0x800) != 0 )
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)qword_18003FDC0 + v7), p_Share);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)qword_18003FA40 + v7), p_Share);
    }
    else
    {
      if ( (Buffer & 0x800) != 0 )
        v8 = 946752838;
      else
        v8 = 846089542;
      ExFreePoolWithTag(&FileNameInformation[-1].Share, v8);
    }
  }
  if ( (byte_180040A43 & 8) != 0 )
    McTemplateU0s_EtwWriteTransfer(FileNameInformation, NameCacheSup_c6442, "FltReleaseFileNameInformation");
}

```

## disassembly

```asm
0x1800629c0  mov     [rsp+arg_0], rbx
0x1800629c5  push    rdi
0x1800629c6  sub     rsp, 40h
0x1800629ca  test    cs:byte_180040A43, 8
0x1800629d1  mov     rdi, rcx
0x1800629d4  jnz     loc_180062AFE
0x1800629da  mov     eax, 0FFFFFFFFh
0x1800629df  lock xadd [rdi+78h], eax
0x1800629e4  sub     eax, 1
0x1800629e7  jle     short loc_180062A02
0x1800629e9  test    cs:byte_180040A43, 8
0x1800629f0  jnz     loc_180062AA9
0x1800629f6  mov     rbx, [rsp+48h+arg_0]
0x1800629fb  add     rsp, 40h
0x1800629ff  pop     rdi
0x180062a00  retn
0x180062a02  test    dword ptr [rdi-8], 1E000h
0x180062a09  jnz     loc_180062AC1
0x180062a0f  test    cs:byte_180040A43, 8
0x180062a16  jnz     loc_180062AE6
0x180062a1c  test    cs:byte_180040A43, 2
0x180062a23  jnz     loc_180062B19
0x180062a29  mov     ecx, [rdi-8]
0x180062a2c  bt      ecx, 0Ch
0x180062a30  jnb     short loc_180062A85
0x180062a32  movzx   eax, word ptr [rdi-4Eh]
0x180062a36  mov     edx, 150h
0x180062a3b  cmp     ax, dx
0x180062a3e  jbe     short loc_180062A81
0x180062a40  sub     rax, 111h
0x180062a46  shr     rax, 6
0x180062a4a  movzx   eax, ax
0x180062a4d  lea     rdx, [rdi-50h]; Entry
0x180062a51  shl     rax, 7
0x180062a55  bt      ecx, 0Bh
0x180062a59  lea     rcx, FltGlobals
0x180062a60  jb      loc_180062B44
0x180062a66  add     rcx, 0D80h
0x180062a6d  add     rcx, rax; Lookaside
0x180062a70  call    cs:__imp_ExFreeToPagedLookasideList
0x180062a77  nop     dword ptr [rax+rax+00h]
0x180062a7c  jmp     loc_1800629E9
0x180062a81  xor     eax, eax
0x180062a83  jmp     short loc_180062A4A
0x180062a85  bt      ecx, 0Bh
0x180062a89  lea     rcx, [rdi-50h]; P
0x180062a8d  jb      loc_180062B5F
0x180062a93  mov     edx, 326E4D46h; Tag
0x180062a98  call    cs:__imp_ExFreePoolWithTag
0x180062a9f  nop     dword ptr [rax+rax+00h]
0x180062aa4  jmp     loc_1800629E9
0x180062aa9  lea     r8, aFltreleasefile; "FltReleaseFileNameInformation"
0x180062ab0  lea     rdx, NameCacheSup_c6442
0x180062ab7  call    McTemplateU0s_EtwWriteTransfer
0x180062abc  jmp     loc_1800629F6
0x180062ac1  xor     eax, eax
0x180062ac3  lea     r8, [rdi-50h]; BugCheckParameter2
0x180062ac7  mov     r9, rdi; BugCheckParameter3
0x180062aca  mov     [rsp+48h+BugCheckParameter4], rax; BugCheckParameter4
0x180062acf  mov     edx, 68h ; 'h'; BugCheckParameter1
0x180062ad4  mov     ecx, 0F5h; BugCheckCode
0x180062ad9  call    cs:__imp_KeBugCheckEx
0x180062ae6  lea     r8, aFltreleasefile; "FltReleaseFileNameInformation"
0x180062aed  lea     rdx, NameCacheSup_c6433
0x180062af4  call    McTemplateU0s_EtwWriteTransfer
0x180062af9  jmp     loc_180062A1C
0x180062afe  mov     r9, rdi
0x180062b01  lea     r8, aFltreleasefile; "FltReleaseFileNameInformation"
0x180062b08  lea     rdx, NameCacheSup_c6404
0x180062b0f  call    McTemplateU0sp_EtwWriteTransfer
0x180062b14  jmp     loc_1800629DA
0x180062b19  mov     eax, [rdi-8]
0x180062b1c  lea     r9, [rdi-50h]
0x180062b20  movzx   edx, word ptr [rdi+8]
0x180062b24  movzx   ecx, ax
0x180062b27  mov     rax, [rdi+10h]
0x180062b2b  mov     [rsp+48h+var_18], rax
0x180062b30  shr     edx, 1
0x180062b32  mov     [rsp+48h+var_20], edx
0x180062b36  mov     dword ptr [rsp+48h+BugCheckParameter4], ecx
0x180062b3a  call    McTemplateU0spdw_EtwWriteTransfer
0x180062b3f  jmp     loc_180062A29
0x180062b44  add     rcx, 1100h
0x180062b4b  add     rcx, rax; Lookaside
0x180062b4e  call    cs:__imp_ExFreeToPagedLookasideList
0x180062b55  nop     dword ptr [rax+rax+00h]
0x180062b5a  jmp     loc_1800629E9
0x180062b5f  mov     edx, 386E4D46h
0x180062b64  jmp     loc_180062A98
```
