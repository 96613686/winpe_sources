# SoftwareBitmapFactory::ConvertWithAlpha(Windows::Graphics::Imaging::ISoftwareBitmap *,Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Graphics::Imaging::BitmapAlphaMode,Windows::Graphics::Imaging::ISoftwareBitmap * *)

- ea: `0x180007b50`
- end: `0x180007d32`
- name: `?ConvertWithAlpha@SoftwareBitmapFactory@@UEAAJPEAUISoftwareBitmap@Imaging@Graphics@Windows@@W4BitmapPixelFormat@345@W4BitmapAlphaMode@345@PEAPEAU2345@@Z`
- size: `482`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800076d0`
- `0x18000eef4`
- `0x180022c1c`

## callees

- `0x18000290c`
- `0x180007b50`
- `0x180026920`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007c31`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007d0a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007c31`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007d0a`

## pseudocode

```c
__int64 __fastcall SoftwareBitmapFactory::ConvertWithAlpha(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        ULONGLONG a5)
{
  __int64 result; // rax
  unsigned int v10; // ebx
  unsigned int v11; // [rsp+30h] [rbp-91h] BYREF
  __int64 v12; // [rsp+38h] [rbp-89h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-71h] BYREF
  char *v15; // [rsp+60h] [rbp-61h]
  __int64 v16; // [rsp+68h] [rbp-59h]
  __int64 *v17; // [rsp+70h] [rbp-51h]
  __int64 v18; // [rsp+78h] [rbp-49h]
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+80h] [rbp-41h] BYREF
  int *v20; // [rsp+90h] [rbp-31h]
  int v21; // [rsp+98h] [rbp-29h]
  int v22; // [rsp+9Ch] [rbp-25h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+A0h] [rbp-21h]
  __int64 v24; // [rsp+A8h] [rbp-19h]
  unsigned int *v25; // [rsp+B0h] [rbp-11h]
  __int64 v26; // [rsp+B8h] [rbp-9h]

  if ( (unsigned int)dword_1800710A0 > 5 )
  {
    v12 = a2;
    v17 = &v12;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_1800710A8;
    v18 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_1800710A8;
    v15 = byte_1800657FD;
    UserData.Reserved = 2;
    v16 = 0x10000002BLL;
    v11 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  UserData.Ptr = a5;
  v16 = a1 - 48;
  *(_QWORD *)&UserData.Size = a2;
  v15 = (char *)__PAIR64__(a4, a3);
  result = MF::ExceptionBoundary__lambda_224091afc8216c96659666e5ca450a42___(&UserData);
  v10 = result;
  if ( (unsigned int)dword_1800710A0 > 5 )
  {
    v11 = result;
    *(_QWORD *)&EventDescriptor.Id = a2;
    v25 = &v11;
    v26 = 4;
    p_EventDescriptor = &EventDescriptor;
    v19.Ptr = (ULONGLONG)off_1800710A8;
    v24 = 8;
    UserData.Ptr = 0x2050B000000LL;
    *(_QWORD *)&UserData.Size = 0;
    v19.Size = *(unsigned __int16 *)off_1800710A8;
    v20 = &dword_1800657BC;
    v19.Reserved = 2;
    v21 = 53;
    v22 = 1;
    LODWORD(v12) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 4u, &v19);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180007b50  push    rbp
0x180007b52  push    rbx
0x180007b53  push    rsi
0x180007b54  push    rdi
0x180007b55  push    r12
0x180007b57  push    r13
0x180007b59  push    r14
0x180007b5b  push    r15
0x180007b5d  lea     rbp, [rsp-17h]
0x180007b62  sub     rsp, 0D8h
0x180007b69  mov     rax, cs:__security_cookie
0x180007b70  xor     rax, rsp
0x180007b73  mov     [rbp+4Fh+var_50], rax
0x180007b77  mov     eax, cs:dword_1800710A0
0x180007b7d  lea     rsi, _TraceLoggingMetadataEnd
0x180007b84  xor     r12d, r12d
0x180007b87  lea     r13, _TraceLoggingMetadata
0x180007b8e  mov     ebx, r9d
0x180007b91  mov     r14d, r8d
0x180007b94  mov     rdi, rdx
0x180007b97  mov     r15, rcx
0x180007b9a  cmp     eax, 5
0x180007b9d  jbe     loc_180007C37
0x180007ba3  mov     [rsp+110h+var_D8], rdx
0x180007ba8  lea     rax, [rsp+110h+var_D8]
0x180007bad  mov     [rbp+4Fh+var_A0], rax
0x180007bb1  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x180007bb6  movzx   eax, cs:word_1800657F3
0x180007bbd  xor     r9d, r9d; RelatedActivityId
0x180007bc0  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x180007bc3  xor     r8d, r8d; ActivityId
0x180007bc6  mov     rax, cs:off_1800710A8
0x180007bcd  mov     [rbp+4Fh+var_C0.Ptr], rax
0x180007bd1  mov     [rbp+4Fh+var_98], 8
0x180007bd9  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x180007be1  mov     [rbp+4Fh+EventDescriptor.Keyword], r12
0x180007be5  movzx   eax, word ptr [rax]
0x180007be8  mov     [rbp+4Fh+var_C0.Size], eax
0x180007beb  lea     rax, byte_1800657FD
0x180007bf2  mov     [rbp+4Fh+var_B0], rax
0x180007bf6  mov     rax, rsi
0x180007bf9  sub     eax, r13d
0x180007bfc  mov     dword ptr [rbp+4Fh+var_C0.0Ch], 2
0x180007c03  mov     dword ptr [rbp+4Fh+var_A8], 2Bh ; '+'
0x180007c0a  mov     dword ptr [rbp+4Fh+var_A8+4], 1
0x180007c11  mov     [rsp+110h+var_E0], eax
0x180007c15  mov     eax, [rsp+110h+var_E0]
0x180007c19  mov     rcx, cs:RegHandle; RegHandle
0x180007c20  lea     rax, [rbp+4Fh+var_C0]
0x180007c24  mov     [rsp+110h+UserData], rax; UserData
0x180007c29  mov     [rsp+110h+UserDataCount], 3; UserDataCount
0x180007c31  call    cs:__imp_EventWriteTransfer
0x180007c37  mov     rax, [rbp+4Fh+arg_20]
0x180007c3b  lea     rcx, [rbp+4Fh+var_C0]
0x180007c3f  mov     [rbp+4Fh+var_C0.Ptr], rax
0x180007c43  lea     rax, [r15-30h]
0x180007c47  mov     [rbp+4Fh+var_A8], rax
0x180007c4b  mov     qword ptr [rbp+4Fh+var_C0.Size], rdi
0x180007c4f  mov     dword ptr [rbp+4Fh+var_B0], r14d
0x180007c53  mov     dword ptr [rbp+4Fh+var_B0+4], ebx
0x180007c56  call    MF__ExceptionBoundary__lambda_224091afc8216c96659666e5ca450a42___
0x180007c5b  mov     ecx, cs:dword_1800710A0
0x180007c61  mov     ebx, eax
0x180007c63  cmp     ecx, 5
0x180007c66  jbe     loc_180007D12
0x180007c6c  mov     [rsp+110h+var_E0], eax
0x180007c70  lea     rdx, [rbp+4Fh+var_C0]; EventDescriptor
0x180007c74  mov     qword ptr [rsp+110h+EventDescriptor.Id], rdi
0x180007c79  lea     rax, [rsp+110h+var_E0]
0x180007c7e  mov     [rbp+4Fh+var_60], rax
0x180007c82  sub     esi, r13d
0x180007c85  lea     rax, [rsp+110h+EventDescriptor]
0x180007c8a  mov     [rbp+4Fh+var_58], 4
0x180007c92  mov     [rbp+4Fh+var_70], rax
0x180007c96  xor     r9d, r9d; RelatedActivityId
0x180007c99  movzx   eax, cs:word_1800657B2
0x180007ca0  xor     r8d, r8d; ActivityId
0x180007ca3  mov     dword ptr [rbp+4Fh+var_C0.Ptr+4], eax
0x180007ca6  mov     rax, cs:off_1800710A8
0x180007cad  mov     [rbp+4Fh+var_90.Ptr], rax
0x180007cb1  mov     [rbp+4Fh+var_68], 8
0x180007cb9  mov     dword ptr [rbp+4Fh+var_C0.Ptr], 0B000000h
0x180007cc0  mov     qword ptr [rbp+4Fh+var_C0.Size], r12
0x180007cc4  movzx   eax, word ptr [rax]
0x180007cc7  mov     [rbp+4Fh+var_90.Size], eax
0x180007cca  lea     rax, dword_1800657BC
0x180007cd1  mov     [rbp+4Fh+var_80], rax
0x180007cd5  mov     dword ptr [rbp+4Fh+var_90.0Ch], 2
0x180007cdc  mov     [rbp+4Fh+var_78], 35h ; '5'
0x180007ce3  mov     [rbp+4Fh+var_74], 1
0x180007cea  mov     dword ptr [rsp+110h+var_D8], esi
0x180007cee  mov     eax, dword ptr [rsp+110h+var_D8]
0x180007cf2  mov     rcx, cs:RegHandle; RegHandle
0x180007cf9  lea     rax, [rbp+4Fh+var_90]
0x180007cfd  mov     [rsp+110h+UserData], rax; UserData
0x180007d02  mov     [rsp+110h+UserDataCount], 4; UserDataCount
0x180007d0a  call    cs:__imp_EventWriteTransfer
0x180007d10  mov     eax, ebx
0x180007d12  mov     rcx, [rbp+4Fh+var_50]
0x180007d16  xor     rcx, rsp; StackCookie
0x180007d19  call    __security_check_cookie
0x180007d1e  add     rsp, 0D8h
0x180007d25  pop     r15
0x180007d27  pop     r14
0x180007d29  pop     r13
0x180007d2b  pop     r12
0x180007d2d  pop     rdi
0x180007d2e  pop     rsi
0x180007d2f  pop     rbx
0x180007d30  pop     rbp
0x180007d31  retn
```
