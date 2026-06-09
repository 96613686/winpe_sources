# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180006eec`
- end: `0x1800070b2`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U2@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@464@Z`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016940`

## callees

- `0x180006eec`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007097`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007097`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        const wchar_t **a6,
        __int64 **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        const wchar_t **a11)
{
  __int64 v11; // rcx
  const wchar_t *v13; // r8
  __int64 v14; // rax
  int v15; // eax
  const wchar_t *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  __int64 *v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  const wchar_t *v22; // rdx
  int v23; // ecx
  __int64 v24; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-99h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int8 *v28; // [rsp+60h] [rbp-71h]
  int v29; // [rsp+68h] [rbp-69h]
  int v30; // [rsp+6Ch] [rbp-65h]
  __int64 v31; // [rsp+70h] [rbp-61h]
  __int64 v32; // [rsp+78h] [rbp-59h]
  const wchar_t *v33; // [rsp+80h] [rbp-51h]
  int v34; // [rsp+88h] [rbp-49h]
  int v35; // [rsp+8Ch] [rbp-45h]
  __int64 *v36; // [rsp+90h] [rbp-41h]
  int v37; // [rsp+98h] [rbp-39h]
  int v38; // [rsp+9Ch] [rbp-35h]
  __int64 v39; // [rsp+A0h] [rbp-31h]
  __int64 v40; // [rsp+A8h] [rbp-29h]
  const wchar_t *v41; // [rsp+B0h] [rbp-21h]
  int v42; // [rsp+B8h] [rbp-19h]
  int v43; // [rsp+BCh] [rbp-15h]
  __int64 v44; // [rsp+C0h] [rbp-11h]
  __int64 v45; // [rsp+C8h] [rbp-9h]
  const wchar_t *v46; // [rsp+D0h] [rbp-1h]
  int v47; // [rsp+D8h] [rbp+7h]
  int v48; // [rsp+DCh] [rbp+Bh]

  v11 = -1;
  v13 = *a11;
  if ( *a11 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &byte_18002AE5D;
    v15 = 1;
  }
  v47 = v15;
  v44 = a10;
  v46 = v13;
  v48 = 0;
  v45 = 4;
  v16 = *a9;
  if ( *a9 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_BYTE *)v16 + v17) );
    v18 = v17 + 1;
  }
  else
  {
    v16 = &byte_18002AE5D;
    v18 = 1;
  }
  v42 = v18;
  v39 = a8;
  v41 = v16;
  v43 = 0;
  v40 = 4;
  v19 = *a7;
  if ( *a7 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v19 + v20) );
    v21 = 2 * v20 + 2;
  }
  else
  {
    v19 = &qword_18002AF20;
    v21 = 2;
  }
  v37 = v21;
  v36 = v19;
  v38 = 0;
  v22 = *a6;
  if ( *a6 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v22 + v11) );
    v23 = v11 + 1;
  }
  else
  {
    v22 = &byte_18002AE5D;
    v23 = 1;
  }
  v34 = v23;
  v33 = v22;
  v35 = 0;
  v24 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180037058;
  v31 = v24;
  v32 = 16;
  UserData.Size = (unsigned __int16)*off_180037058;
  v29 = *(unsigned __int16 *)(a2 + 11);
  v28 = a2 + 11;
  UserData.Reserved = 2;
  v30 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 9u, &UserData);
}

```

## disassembly

```asm
0x180006eec  push    rbp
0x180006eee  lea     rbp, [rsp-1Fh]
0x180006ef3  sub     rsp, 0F0h
0x180006efa  mov     rax, cs:__security_cookie
0x180006f01  xor     rax, rsp
0x180006f04  mov     [rbp+1Fh+var_10], rax
0x180006f08  mov     rax, [rbp+1Fh+arg_50]
0x180006f0c  lea     r11, byte_18002AE5D
0x180006f13  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006f17  xor     r10d, r10d
0x180006f1a  mov     r9, rdx
0x180006f1d  mov     r8, [rax]
0x180006f20  test    r8, r8
0x180006f23  jz      short loc_180006F35
0x180006f25  mov     rax, rcx
0x180006f28  inc     rax
0x180006f2b  cmp     [r8+rax], r10b
0x180006f2f  jnz     short loc_180006F28
0x180006f31  inc     eax
0x180006f33  jmp     short loc_180006F3D
0x180006f35  mov     r8, r11
0x180006f38  mov     eax, 1
0x180006f3d  mov     [rbp+1Fh+var_18], eax
0x180006f40  mov     rax, [rbp+1Fh+arg_48]
0x180006f44  mov     [rbp+1Fh+var_30], rax
0x180006f48  mov     rax, [rbp+1Fh+arg_40]
0x180006f4c  mov     [rbp+1Fh+var_20], r8
0x180006f50  mov     [rbp+1Fh+var_14], r10d
0x180006f54  mov     [rbp+1Fh+var_28], 4
0x180006f5c  mov     rdx, [rax]
0x180006f5f  test    rdx, rdx
0x180006f62  jz      short loc_180006F74
0x180006f64  mov     rax, rcx
0x180006f67  inc     rax
0x180006f6a  cmp     [rdx+rax], r10b
0x180006f6e  jnz     short loc_180006F67
0x180006f70  inc     eax
0x180006f72  jmp     short loc_180006F7C
0x180006f74  mov     rdx, r11
0x180006f77  mov     eax, 1
0x180006f7c  mov     [rbp+1Fh+var_38], eax
0x180006f7f  mov     r8d, 2
0x180006f85  mov     rax, [rbp+1Fh+arg_38]
0x180006f89  mov     [rbp+1Fh+var_50], rax
0x180006f8d  mov     rax, [rbp+1Fh+arg_30]
0x180006f91  mov     [rbp+1Fh+var_40], rdx
0x180006f95  mov     [rbp+1Fh+var_34], r10d
0x180006f99  mov     [rbp+1Fh+var_48], 4
0x180006fa1  mov     rdx, [rax]
0x180006fa4  test    rdx, rdx
0x180006fa7  jz      short loc_180006FBF
0x180006fa9  mov     rax, rcx
0x180006fac  inc     rax
0x180006faf  cmp     [rdx+rax*2], r10w
0x180006fb4  jnz     short loc_180006FAC
0x180006fb6  lea     eax, ds:2[rax*2]
0x180006fbd  jmp     short loc_180006FC9
0x180006fbf  lea     rdx, qword_18002AF20
0x180006fc6  mov     eax, r8d
0x180006fc9  mov     [rbp+1Fh+var_58], eax
0x180006fcc  mov     rax, [rbp+1Fh+arg_28]
0x180006fd0  mov     [rbp+1Fh+var_60], rdx
0x180006fd4  mov     [rbp+1Fh+var_54], r10d
0x180006fd8  mov     rdx, [rax]
0x180006fdb  test    rdx, rdx
0x180006fde  jz      short loc_180006FED
0x180006fe0  inc     rcx
0x180006fe3  cmp     [rdx+rcx], r10b
0x180006fe7  jnz     short loc_180006FE0
0x180006fe9  inc     ecx
0x180006feb  jmp     short loc_180006FF5
0x180006fed  mov     rdx, r11
0x180006ff0  mov     ecx, 1
0x180006ff5  mov     rax, [rbp+1Fh+arg_20]
0x180006ff9  mov     [rbp+1Fh+var_68], ecx
0x180006ffc  mov     [rbp+1Fh+var_70], rdx
0x180007000  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x180007005  mov     [rbp+1Fh+var_64], r10d
0x180007009  mov     rcx, [rax]
0x18000700c  movzx   eax, byte ptr [r9]
0x180007010  shl     eax, 18h
0x180007013  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x180007017  movzx   eax, word ptr [r9+1]
0x18000701c  mov     dword ptr [rsp+0F0h+EventDescriptor.Level], eax
0x180007020  mov     rax, [r9+3]
0x180007024  mov     [rsp+0F0h+EventDescriptor.Keyword], rax
0x180007029  mov     rax, cs:off_180037058
0x180007030  mov     [rsp+0F0h+var_A0.Ptr], rax
0x180007035  mov     [rbp+1Fh+var_80], rcx
0x180007039  lea     rcx, [r9+0Bh]
0x18000703d  mov     [rbp+1Fh+var_78], 10h
0x180007045  xor     r9d, r9d; RelatedActivityId
0x180007048  movzx   eax, word ptr [rax]
0x18000704b  mov     [rbp+1Fh+var_A0.Size], eax
0x18000704e  movzx   eax, word ptr [rcx]
0x180007051  mov     [rbp+1Fh+var_88], eax
0x180007054  lea     rax, _TraceLoggingMetadataEnd
0x18000705b  mov     [rbp+1Fh+var_90], rcx
0x18000705f  lea     rcx, _TraceLoggingMetadata
0x180007066  sub     eax, ecx
0x180007068  mov     dword ptr [rbp+1Fh+var_A0.0Ch], r8d
0x18000706c  mov     [rbp+1Fh+var_84], 1
0x180007073  xor     r8d, r8d; ActivityId
0x180007076  mov     [rsp+0F0h+var_C0], eax
0x18000707a  mov     eax, [rsp+0F0h+var_C0]
0x18000707e  mov     rcx, cs:RegHandle; RegHandle
0x180007085  lea     rax, [rsp+0F0h+var_A0]
0x18000708a  mov     [rsp+0F0h+UserData], rax; UserData
0x18000708f  mov     [rsp+0F0h+UserDataCount], 9; UserDataCount
0x180007097  call    cs:__imp_EventWriteTransfer
0x18000709d  mov     rcx, [rbp+1Fh+var_10]
0x1800070a1  xor     rcx, rsp; StackCookie
0x1800070a4  call    __security_check_cookie
0x1800070a9  add     rsp, 0F0h
0x1800070b0  pop     rbp
0x1800070b1  retn
```
