# GetReaderIcon(CSCardUserContext *,ushort const *,uchar *,ulong *)

- ea: `0x180002a30`
- end: `0x180002d39`
- name: `?GetReaderIcon@@YAJPEAVCSCardUserContext@@PEBGPEAEPEAK@Z`
- size: `777`
- prototype: `__int64 __fastcall(struct CSCardUserContext *, const unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x180012e40`
- `0x180025980`

## callees

- `0x180002854`
- `0x180002a30`
- `0x180003de0`
- `0x180003fc0`
- `0x180014a30`
- `0x180014b00`
- `0x1800196cc`
- `0x18001a538`
- `0x18001b9b8`
- `0x18001be10`
- `0x18001c7a8`
- `0x18002484c`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c09`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002bfd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002bfd`

## string_xrefs

- `0x180002b5c`: `%systemroot%\System32\SmartcardCredentialProvider.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetReaderIcon(
        struct CSCardUserContext *a1,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int16 v5; // r14
  int ReaderDeviceInstanceId; // eax
  const struct _DEVPROPKEY *v7; // rdx
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // rcx
  ulong ReaderDeviceProperty; // eax
  unsigned __int64 v12; // rdx
  int v13; // r15d
  WCHAR *v14; // rdi
  ulong v15; // eax
  ulong v16; // eax
  unsigned __int64 v17; // rdx
  int v19[2]; // [rsp+20h] [rbp-4E8h] BYREF
  const int *v20; // [rsp+28h] [rbp-4E0h] BYREF
  LPCWSTR lpSrc; // [rsp+30h] [rbp-4D8h]
  int v22; // [rsp+38h] [rbp-4D0h]
  int v23; // [rsp+3Ch] [rbp-4CCh]
  unsigned __int16 *v24; // [rsp+40h] [rbp-4C8h] BYREF
  const int *v25; // [rsp+48h] [rbp-4C0h] BYREF
  unsigned __int16 *v26; // [rsp+50h] [rbp-4B8h]
  int v27; // [rsp+58h] [rbp-4B0h]
  int v28; // [rsp+5Ch] [rbp-4ACh]
  int pExceptionObject; // [rsp+60h] [rbp-4A8h] BYREF
  ulong v30; // [rsp+64h] [rbp-4A4h] BYREF
  int v31; // [rsp+68h] [rbp-4A0h]
  ulong LastError; // [rsp+6Ch] [rbp-49Ch] BYREF
  ulong v33; // [rsp+70h] [rbp-498h] BYREF
  ulong v34; // [rsp+74h] [rbp-494h] BYREF
  const int *v35; // [rsp+78h] [rbp-490h] BYREF
  void *v36; // [rsp+80h] [rbp-488h]
  int v37; // [rsp+88h] [rbp-480h]
  int v38; // [rsp+8Ch] [rbp-47Ch]
  ulong v39; // [rsp+90h] [rbp-478h] BYREF
  unsigned int *v40; // [rsp+98h] [rbp-470h]
  unsigned __int8 *v41; // [rsp+A0h] [rbp-468h]
  WCHAR Dst[520]; // [rsp+B0h] [rbp-458h] BYREF

  v40 = a4;
  v41 = a3;
  try
  {
    v25 = &CBuffer::`vftable';
    v5 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    ReaderDeviceInstanceId = CSCardUserContext::GetReaderDeviceInstanceId(a1, a2, (struct CBuffer *)&v25);
    v8 = ReaderDeviceInstanceId;
    v19[1] = ReaderDeviceInstanceId;
    if ( ReaderDeviceInstanceId )
    {
      pExceptionObject = ReaderDeviceInstanceId;
      throw (ulong *)&pExceptionObject;
    }
    v20 = &CBuffer::`vftable';
    lpSrc = 0;
    v22 = 0;
    v23 = 0;
    v9 = (unsigned __int16 *)&WideCharStr;
    v10 = (unsigned __int16 *)&WideCharStr;
    if ( v28 )
      v10 = v26;
    ReaderDeviceProperty = GetReaderDeviceProperty(v10, v7, (struct CBuffer *)&v20);
    if ( ReaderDeviceProperty && ReaderDeviceProperty != 1168 )
    {
      v30 = ReaderDeviceProperty;
      throw &v30;
    }
    v24 = 0;
    v19[0] = 0;
    v35 = &CBuffer::`vftable';
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v13 = 1;
    v31 = 1;
    if ( ReaderDeviceProperty == 1168 )
    {
      if ( lpSrc )
        operator delete((void *)lpSrc, v12);
      lpSrc = 0;
      v22 = 0;
      v23 = 0;
      CBuffer::Append((CBuffer *)&v20, L"%systemroot%\\System32\\SmartcardCredentialProvider.dll", 0x6Cu);
      v5 = 901;
      v19[0] = 901;
      v14 = (WCHAR *)lpSrc;
      if ( v23 )
        v9 = (unsigned __int16 *)lpSrc;
      v24 = v9;
    }
    else
    {
      if ( (unsigned int)GetResourcePathAndId((struct CBuffer *)&v20, &v24, v19) == 1168 )
      {
        v9 = (unsigned __int16 *)CBuffer::Access((CBuffer *)&v20, 0);
        v24 = v9;
        v19[0] = 0;
        v13 = 0;
        v31 = 0;
      }
      else
      {
        v9 = v24;
        v5 = v19[0];
      }
      v14 = (WCHAR *)lpSrc;
    }
    memset_0(Dst, 0, sizeof(Dst));
    if ( !ExpandEnvironmentStringsW(v9, Dst, 0x103u) )
    {
      LastError = GetLastError();
      throw &LastError;
    }
    if ( v13 )
    {
      v15 = CopyResourceToBuffer(Dst, v5, (struct CBuffer *)&v35);
      if ( v15 )
      {
        v33 = v15;
        throw &v33;
      }
    }
    else
    {
      v16 = CopyFileToBuffer(Dst, (DWORD *)&v35);
      if ( v16 )
      {
        v34 = v16;
        throw &v34;
      }
    }
    PlaceResult(a1, (struct CBuffer *)&v35, v41, v40);
    v35 = &CBuffer::`vftable';
    if ( v36 )
      operator delete(v36, v17);
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v20 = &CBuffer::`vftable';
    if ( v14 )
      operator delete(v14, v17);
    lpSrc = 0;
    v22 = 0;
    v23 = 0;
    v25 = &CBuffer::`vftable';
    if ( v26 )
      operator delete(v26, v17);
    v26 = 0;
    v27 = 0;
    v28 = 0;
  }
  catch ( ulong v39 )
  {
    return v39;
  }
  catch ( ... )
  {
    return (unsigned int)-2146435068;
  }
  return v8;
}

```

## disassembly

```asm
0x180002a30  push    rbx
0x180002a32  push    rsi
0x180002a33  push    rdi
0x180002a34  push    r13
0x180002a36  push    r14
0x180002a38  push    r15
0x180002a3a  sub     rsp, 4D8h
0x180002a41  mov     rax, cs:__security_cookie
0x180002a48  xor     rax, rsp
0x180002a4b  mov     [rsp+508h+var_48], rax
0x180002a53  mov     [rsp+508h+var_470], r9
0x180002a5b  mov     [rsp+508h+var_468], r8
0x180002a63  mov     r13, rcx
0x180002a66  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180002a6d  mov     [rsp+508h+var_4C0], r15
0x180002a72  xor     r14d, r14d
0x180002a75  mov     [rsp+508h+var_4B8], r14
0x180002a7a  mov     [rsp+508h+var_4B0], r14d
0x180002a7f  mov     [rsp+508h+var_4AC], r14d
0x180002a84  lea     r8, [rsp+508h+var_4C0]; struct CBuffer *
0x180002a89  call    ?GetReaderDeviceInstanceId@CSCardUserContext@@QEAAJPEBGAEAVCBuffer@@@Z; CSCardUserContext::GetReaderDeviceInstanceId(ushort const *,CBuffer &)
0x180002a8e  mov     ebx, eax
0x180002a90  mov     [rsp+508h+var_4E4], eax
0x180002a94  test    eax, eax
0x180002a96  jz      short loc_180002AAD
0x180002a98  mov     [rsp+508h+pExceptionObject], eax
0x180002a9c  lea     rdx, _TI1K; pThrowInfo
0x180002aa3  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180002aa8  call    _CxxThrowException_0
0x180002aad  mov     [rsp+508h+var_4E0], r15
0x180002ab2  mov     [rsp+508h+lpSrc], r14
0x180002ab7  mov     [rsp+508h+var_4D0], r14d
0x180002abc  mov     [rsp+508h+var_4CC], r14d
0x180002ac1  lea     rsi, WideCharStr
0x180002ac8  mov     rcx, rsi
0x180002acb  cmp     [rsp+508h+var_4AC], r14d
0x180002ad0  cmova   rcx, [rsp+508h+var_4B8]; unsigned __int16 *
0x180002ad6  lea     r8, [rsp+508h+var_4E0]; struct CBuffer *
0x180002adb  call    ?GetReaderDeviceProperty@@YAJPEBGPEBU_DEVPROPKEY@@AEAVCBuffer@@@Z; GetReaderDeviceProperty(ushort const *,_DEVPROPKEY const *,CBuffer &)
0x180002ae0  mov     edi, 490h
0x180002ae5  test    eax, eax
0x180002ae7  jz      short loc_180002B02
0x180002ae9  cmp     eax, edi
0x180002aeb  jz      short loc_180002B02
0x180002aed  mov     [rsp+508h+var_4A4], eax
0x180002af1  lea     rdx, _TI1K; pThrowInfo
0x180002af8  lea     rcx, [rsp+508h+var_4A4]; pExceptionObject
0x180002afd  call    _CxxThrowException_0
0x180002b02  mov     [rsp+508h+var_4C8], r14
0x180002b07  mov     [rsp+508h+var_4E8], r14d
0x180002b0c  mov     [rsp+508h+var_490], r15
0x180002b11  mov     [rsp+508h+var_488], r14
0x180002b19  mov     [rsp+508h+var_480], r14d
0x180002b21  mov     [rsp+508h+var_47C], r14d
0x180002b29  mov     r15d, 1
0x180002b2f  mov     [rsp+508h+var_4A0], r15d
0x180002b34  cmp     eax, edi
0x180002b36  jnz     short loc_180002B8D
0x180002b38  mov     rcx, [rsp+508h+lpSrc]; void *
0x180002b3d  test    rcx, rcx
0x180002b40  jz      short loc_180002B47
0x180002b42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002b47  mov     [rsp+508h+lpSrc], r14
0x180002b4c  mov     [rsp+508h+var_4D0], r14d
0x180002b51  mov     [rsp+508h+var_4CC], r14d
0x180002b56  mov     r8d, 6Ch ; 'l'; unsigned int
0x180002b5c  lea     rdx, aSystemrootSyst; "%systemroot%\\System32\\SmartcardCreden"...
0x180002b63  lea     rcx, [rsp+508h+var_4E0]; this
0x180002b68  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x180002b6d  mov     r14d, 385h
0x180002b73  mov     [rsp+508h+var_4E8], r14d
0x180002b78  mov     rdi, [rsp+508h+lpSrc]
0x180002b7d  cmp     [rsp+508h+var_4CC], 0
0x180002b82  cmova   rsi, rdi
0x180002b86  mov     [rsp+508h+var_4C8], rsi
0x180002b8b  jmp     short loc_180002BD7
0x180002b8d  lea     r8, [rsp+508h+var_4E8]; int *
0x180002b92  lea     rdx, [rsp+508h+var_4C8]; unsigned __int16 **
0x180002b97  lea     rcx, [rsp+508h+var_4E0]; this
0x180002b9c  call    ?GetResourcePathAndId@@YAJAEAVCBuffer@@PEAPEAGPEAH@Z; GetResourcePathAndId(CBuffer &,ushort * *,int *)
0x180002ba1  cmp     eax, edi
0x180002ba3  jnz     short loc_180002BC8
0x180002ba5  xor     edx, edx; unsigned int
0x180002ba7  lea     rcx, [rsp+508h+var_4E0]; this
0x180002bac  call    ?Access@CBuffer@@QEBAPEAEK@Z; CBuffer::Access(ulong)
0x180002bb1  mov     rsi, rax
0x180002bb4  mov     [rsp+508h+var_4C8], rax
0x180002bb9  mov     [rsp+508h+var_4E8], r14d
0x180002bbe  xor     r15d, r15d
0x180002bc1  mov     [rsp+508h+var_4A0], r15d
0x180002bc6  jmp     short loc_180002BD2
0x180002bc8  mov     rsi, [rsp+508h+var_4C8]
0x180002bcd  mov     r14d, [rsp+508h+var_4E8]
0x180002bd2  mov     rdi, [rsp+508h+lpSrc]
0x180002bd7  xor     edx, edx; Val
0x180002bd9  mov     r8d, 410h; Size
0x180002bdf  lea     rcx, [rsp+508h+Dst]; void *
0x180002be7  call    memset_0
0x180002bec  mov     r8d, 103h; nSize
0x180002bf2  lea     rdx, [rsp+508h+Dst]; lpDst
0x180002bfa  mov     rcx, rsi; lpSrc
0x180002bfd  call    cs:__imp_ExpandEnvironmentStringsW
0x180002c03  xor     esi, esi
0x180002c05  test    eax, eax
0x180002c07  jnz     short loc_180002C24
0x180002c09  call    cs:__imp_GetLastError
0x180002c0f  mov     [rsp+508h+var_49C], eax
0x180002c13  lea     rdx, _TI1K; pThrowInfo
0x180002c1a  lea     rcx, [rsp+508h+var_49C]; pExceptionObject
0x180002c1f  call    _CxxThrowException_0
0x180002c24  lea     rcx, [rsp+508h+Dst]; unsigned __int16 *
0x180002c2c  test    r15d, r15d
0x180002c2f  jz      short loc_180002C57
0x180002c31  lea     r8, [rsp+508h+var_490]; struct CBuffer *
0x180002c36  mov     edx, r14d; int
0x180002c39  call    ?CopyResourceToBuffer@@YAJPEBGHAEAVCBuffer@@@Z; CopyResourceToBuffer(ushort const *,int,CBuffer &)
0x180002c3e  test    eax, eax
0x180002c40  jz      short loc_180002C7A
0x180002c42  mov     [rsp+508h+var_498], eax
0x180002c46  lea     rdx, _TI1K; pThrowInfo
0x180002c4d  lea     rcx, [rsp+508h+var_498]; pExceptionObject
0x180002c52  call    _CxxThrowException_0
0x180002c57  lea     rdx, [rsp+508h+var_490]; struct CBuffer *
0x180002c5c  call    ?CopyFileToBuffer@@YAJPEBGAEAVCBuffer@@@Z; CopyFileToBuffer(ushort const *,CBuffer &)
0x180002c61  test    eax, eax
0x180002c63  jz      short loc_180002C7A
0x180002c65  mov     [rsp+508h+var_494], eax
0x180002c69  lea     rdx, _TI1K; pThrowInfo
0x180002c70  lea     rcx, [rsp+508h+var_494]; pExceptionObject
0x180002c75  call    _CxxThrowException_0
0x180002c7a  mov     r9, [rsp+508h+var_470]; unsigned int *
0x180002c82  mov     r8, [rsp+508h+var_468]; unsigned __int8 *
0x180002c8a  lea     rdx, [rsp+508h+var_490]; struct CBuffer *
0x180002c8f  mov     rcx, r13; struct CSCardUserContext *
0x180002c92  call    ?PlaceResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAEPEAK@Z; PlaceResult(CSCardUserContext *,CBuffer &,uchar *,ulong *)
0x180002c97  nop
0x180002c98  lea     r14, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180002c9f  mov     [rsp+508h+var_490], r14
0x180002ca4  mov     rcx, [rsp+508h+var_488]; void *
0x180002cac  test    rcx, rcx
0x180002caf  jz      short loc_180002CB6
0x180002cb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002cb6  mov     [rsp+508h+var_488], rsi
0x180002cbe  mov     [rsp+508h+var_480], esi
0x180002cc5  mov     [rsp+508h+var_47C], esi
0x180002ccc  mov     [rsp+508h+var_4E0], r14
0x180002cd1  test    rdi, rdi
0x180002cd4  jz      short loc_180002CDE
0x180002cd6  mov     rcx, rdi; void *
0x180002cd9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002cde  mov     [rsp+508h+lpSrc], rsi
0x180002ce3  mov     [rsp+508h+var_4D0], esi
0x180002ce7  mov     [rsp+508h+var_4CC], esi
0x180002ceb  mov     [rsp+508h+var_4C0], r14
0x180002cf0  cmp     [rsp+508h+var_4B8], rsi
0x180002cf5  jz      short loc_180002D01
0x180002cf7  mov     rcx, [rsp+508h+var_4B8]; void *
0x180002cfc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002d01  mov     [rsp+508h+var_4B8], rsi
0x180002d06  mov     [rsp+508h+var_4B0], esi
0x180002d0a  mov     [rsp+508h+var_4AC], esi
0x180002d0e  jmp     short loc_180002D16
0x180002d10  jmp     short $+2
0x180002d12  mov     ebx, [rsp+508h+var_4E4]
0x180002d16  mov     eax, ebx
0x180002d18  mov     rcx, [rsp+508h+var_48]
0x180002d20  xor     rcx, rsp; StackCookie
0x180002d23  call    __security_check_cookie
0x180002d28  add     rsp, 4D8h
0x180002d2f  pop     r15
0x180002d31  pop     r14
0x180002d33  pop     r13
0x180002d35  pop     rdi
0x180002d36  pop     rsi
0x180002d37  pop     rbx
0x180002d38  retn
```
