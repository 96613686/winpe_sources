# BfGeneratePostCreateName

- ea: `0x140001dd0`
- end: `0x140001fc1`
- name: `BfGeneratePostCreateName`
- size: `497`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140013780`
- `0x140017360`
- `0x1400202f0`
- `0x1400225f4`

## callees

- `0x140001348`
- `0x140001dd0`
- `0x140001fd0`
- `0x140004438`
- `0x1400154b0`
- `0x1400172f0`
- `0x140017bf0`
- `0x140020a10`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x140001e9e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140001e9e`

## string_xrefs

- `0x140001ee0`: `opened`

## pseudocode

```c
__int64 __fastcall BfGeneratePostCreateName(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        struct _FLT_INSTANCE *a5,
        UNICODE_STRING *a6)
{
  int v7; // esi
  __int64 v8; // rdx
  int v9; // ebx
  int v10; // r8d
  int v11; // r9d
  int v12; // eax
  int v13; // edx
  __int64 v14; // r8
  int v15; // eax
  int v16; // eax
  int v18; // r9d
  char v19; // [rsp+30h] [rbp-48h]
  int v20; // [rsp+38h] [rbp-40h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-28h] BYREF
  __int128 v22; // [rsp+58h] [rbp-20h] BYREF

  v7 = (unsigned __int8)a3;
  FileNameInformation = 0;
  v22 = 0;
  v9 = BfGetFileNameInformation(0, a1, a2, a3);
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDsd(WPP_GLOBAL_Control->DeviceExtension, v8, v10, v11, (unsigned int)&FileNameInformation);
  }
  else
  {
    LOBYTE(v8) = 1;
    FileNameInformation->NamesParsed = 0;
    v12 = BfFormatPathFromFileNameInfo(FileNameInformation, v8, &v22);
    v9 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_8;
      v20 = v12;
      v18 = 32;
      v19 = 20;
      goto LABEL_20;
    }
    if ( v7 == 1 )
      v14 = *(_QWORD *)(a4 + 40) + 16LL;
    else
      v14 = a4 + 64;
    v15 = BfReplaceFirstSubstring(&v22, *(_QWORD *)(a4 + 48) + 40LL, v14, a6);
    v9 = v15;
    if ( v15 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_8;
      v20 = v15;
      v18 = 33;
      v19 = 48;
      goto LABEL_20;
    }
    if ( a5 )
    {
      v16 = BfPrependVolumeNameFromInstance(a5, a6);
      v9 = v16;
      if ( v16 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = v16;
        v18 = 34;
        v19 = 61;
LABEL_20:
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          9,
          v18,
          (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
          v19,
          v20);
      }
    }
  }
LABEL_8:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  BfFreeUnicodeString(&v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140001dd0  mov     rax, rsp
0x140001dd3  mov     [rax+8], rbx
0x140001dd7  mov     [rax+10h], rsi
0x140001ddb  push    rdi
0x140001ddc  sub     rsp, 70h
0x140001de0  mov     rdi, r9
0x140001de3  movzx   esi, r8b
0x140001de7  xorps   xmm0, xmm0
0x140001dea  mov     qword ptr [rax-28h], 0
0x140001df2  mov     r9d, r8d
0x140001df5  mov     r8, rdx
0x140001df8  mov     rdx, rcx
0x140001dfb  xor     ecx, ecx
0x140001dfd  movups  xmmword ptr [rax-20h], xmm0
0x140001e01  lea     rax, [rax-28h]
0x140001e05  mov     [rsp+78h+var_58], rax
0x140001e0a  call    BfGetFileNameInformation
0x140001e0f  mov     ebx, eax
0x140001e11  test    eax, eax
0x140001e13  js      loc_140001EC9
0x140001e19  mov     rax, [rsp+78h+FileNameInformation]
0x140001e1e  lea     r8, [rsp+78h+var_20]
0x140001e23  xor     ecx, ecx
0x140001e25  mov     dl, 1
0x140001e27  mov     [rax+2], cx
0x140001e2b  mov     rcx, [rsp+78h+FileNameInformation]
0x140001e30  call    BfFormatPathFromFileNameInfo
0x140001e35  mov     ebx, eax
0x140001e37  test    eax, eax
0x140001e39  js      loc_140001F09
0x140001e3f  cmp     esi, 1
0x140001e42  jz      loc_140001F31
0x140001e48  lea     r8, [rdi+40h]
0x140001e4c  mov     rdx, [rdi+30h]
0x140001e50  lea     rcx, [rsp+78h+var_20]
0x140001e55  mov     r9, [rsp+78h+arg_28]
0x140001e5d  add     rdx, 28h ; '('
0x140001e61  call    BfReplaceFirstSubstring
0x140001e66  mov     ebx, eax
0x140001e68  test    eax, eax
0x140001e6a  js      loc_140001F3E
0x140001e70  mov     rcx, [rsp+78h+arg_20]
0x140001e78  test    rcx, rcx
0x140001e7b  jz      short loc_140001E94
0x140001e7d  mov     rdx, [rsp+78h+arg_28]
0x140001e85  call    BfPrependVolumeNameFromInstance
0x140001e8a  mov     ebx, eax
0x140001e8c  test    eax, eax
0x140001e8e  js      loc_140001F66
0x140001e94  mov     rcx, [rsp+78h+FileNameInformation]; FileNameInformation
0x140001e99  test    rcx, rcx
0x140001e9c  jz      short loc_140001EAA
0x140001e9e  call    cs:__imp_FltReleaseFileNameInformation
0x140001ea5  nop     dword ptr [rax+rax+00h]
0x140001eaa  lea     rcx, [rsp+78h+var_20]
0x140001eaf  call    BfFreeUnicodeString
0x140001eb4  lea     r11, [rsp+78h+var_8]
0x140001eb9  mov     eax, ebx
0x140001ebb  mov     rbx, [r11+10h]
0x140001ebf  mov     rsi, [r11+18h]
0x140001ec3  mov     rsp, r11
0x140001ec6  pop     rdi
0x140001ec7  retn
0x140001ec9  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001ed0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001ed7  jz      short loc_140001E94
0x140001ed9  cmp     esi, 1
0x140001edc  mov     [rsp+78h+var_38], ebx
0x140001ee0  lea     rax, aOpened; "opened"
0x140001ee7  lea     rcx, aNormalized; "normalized"
0x140001eee  cmovnz  rcx, rax
0x140001ef2  mov     [rsp+78h+var_40], rcx
0x140001ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x140001efe  mov     rcx, [rcx+40h]
0x140001f02  call    WPP_RECORDER_SF_sDsd
0x140001f07  jmp     short loc_140001E94
0x140001f09  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001f10  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001f17  jz      loc_140001E94
0x140001f1d  mov     dword ptr [rsp+78h+var_40], eax
0x140001f21  mov     r9d, 20h ; ' '
0x140001f27  mov     dword ptr [rsp+78h+var_48], 314h
0x140001f2f  jmp     short loc_140001F8C
0x140001f31  mov     r8, [rdi+28h]
0x140001f35  add     r8, 10h
0x140001f39  jmp     loc_140001E4C
0x140001f3e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001f45  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001f4c  jz      loc_140001E94
0x140001f52  mov     dword ptr [rsp+78h+var_40], eax
0x140001f56  mov     r9d, 21h ; '!'
0x140001f5c  mov     dword ptr [rsp+78h+var_48], 330h
0x140001f64  jmp     short loc_140001F8C
0x140001f66  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001f6d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001f74  jz      loc_140001E94
0x140001f7a  mov     dword ptr [rsp+78h+var_40], eax
0x140001f7e  mov     r9d, 22h ; '"'
0x140001f84  mov     dword ptr [rsp+78h+var_48], 33Dh
0x140001f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f93  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140001f9a  mov     [rsp+78h+var_50], rax
0x140001f9f  mov     r8d, 9
0x140001fa5  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x140001fac  mov     dl, 2
0x140001fae  mov     [rsp+78h+var_58], rax
0x140001fb3  mov     rcx, [rcx+40h]
0x140001fb7  call    WPP_RECORDER_SF_sDd
0x140001fbc  jmp     loc_140001E94
```
