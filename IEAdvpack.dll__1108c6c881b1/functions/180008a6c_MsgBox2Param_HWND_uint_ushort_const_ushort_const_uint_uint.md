# MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)

- ea: `0x180008a6c`
- end: `0x180008c7f`
- name: `?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z`
- size: `531`
- prototype: `__int64 __fastcall(HWND hWnd, UINT uID, const unsigned __int16 *, const unsigned __int16 *, UINT uType, unsigned int)`
- caller_count: `40`
- callee_count: `6`
- tags: ``

## callers

- `0x180002450`
- `0x180003fb8`
- `0x1800040e0`
- `0x1800042f8`
- `0x1800045e8`
- `0x180004754`
- `0x180004880`
- `0x1800053f0`
- `0x1800056d0`
- `0x180005f80`
- `0x18000616c`
- `0x1800063c4`
- `0x180006e54`
- `0x1800071c0`
- `0x1800076a8`
- `0x180007968`
- `0x1800079c0`
- `0x180008138`
- `0x180008330`
- `0x180009004`
- `0x1800096f0`
- `0x180009890`
- `0x180009928`
- `0x180009c14`
- `0x18000a428`
- `0x18000a61c`
- `0x18000b8f0`
- `0x18000cc80`
- `0x18000d6cc`
- `0x1800104c0`
- `0x1800115b0`
- `0x180011940`
- `0x1800121d8`
- `0x180012f48`
- `0x180013280`
- `0x1800135d8`
- `0x180013fa4`
- `0x180014440`
- `0x1800152d8`
- `0x180016268`

## callees

- `0x1800022bc`
- `0x180008a34`
- `0x180008a6c`
- `0x1800178f4`
- `0x1800179dc`
- `0x18001b980`

## import_xrefs

- `USER32!MessageBeep` at `0x180008b88`
- `USER32!MessageBeep` at `0x180008b88`
- `USER32!MessageBoxW` at `0x180008c44`
- `USER32!MessageBoxW` at `0x180008c44`
- `KERNEL32!LocalFree` at `0x180008c51`
- `KERNEL32!LocalFree` at `0x180008c51`
- `KERNEL32!FormatMessageW` at `0x180008b72`
- `KERNEL32!FormatMessageW` at `0x180008b72`

## pseudocode

```c
__int64 __fastcall MsgBox2Param(
        HWND hWnd,
        UINT uID,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        UINT uType,
        unsigned int a6)
{
  unsigned int v8; // ebx
  WCHAR *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  HINSTANCE v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // r8
  bool v16; // zf
  int v17; // eax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  va_list Arguments[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v20[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v21; // [rsp+70h] [rbp-90h]
  __int128 v22; // [rsp+80h] [rbp-80h]
  __int128 v23; // [rsp+90h] [rbp-70h]
  __int128 v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+B0h] [rbp-50h]
  WCHAR v26[264]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 Source[512]; // [rsp+2D0h] [rbp+1D0h] BYREF

  *(_OWORD *)v20 = *(_OWORD *)L"Unexpected Error.  Could not load resource.";
  v21 = *(_OWORD *)L"ed Error.  Could not load resource.";
  v22 = *(_OWORD *)L".  Could not load resource.";
  v23 = *(_OWORD *)L" not load resource.";
  v24 = *(_OWORD *)L"d resource.";
  v25 = *(_QWORD *)L"ce.";
  *(_QWORD *)Buffer = 0;
  if ( (word_1800257D2 & 2) == 0 && (word_1800257D2 & 1) != 0 )
    return 1;
  Arguments[0] = (va_list)a3;
  Arguments[1] = (va_list)a4;
  v8 = -1;
  LoadSz(uID, Source, 0x200u);
  if ( !Source[0] )
    StringCchCopyW(Source, 0x200u, v20);
  if ( FormatMessageW(0x2500u, Source, 0, 0, Buffer, 0, Arguments) )
  {
    MessageBeep(uType);
    v9 = (WCHAR *)pszTitleString;
    if ( !pszTitleString )
    {
      LoadSz(0x48Fu, v26, 0x104u);
      if ( !v26[0] )
        StringCchCopyW(v26, 0x104u, v20);
      v9 = v26;
    }
    if ( !(unsigned int)RunningOnWin95BiDiLoc() )
      goto LABEL_18;
    v12 = dword_1800251B4;
    if ( dword_1800251B4 == -2 )
    {
      v13 = g_hinstMUI;
      dword_1800251B4 = 0;
      if ( (unsigned int)GetResourceLanguage(g_hinstMUI, v10, v11, 1)
        || (unsigned int)GetResourceLanguage(v13, v14, v15, 13) )
      {
        v12 = 1;
        dword_1800251B4 = 1;
      }
      else
      {
        v12 = dword_1800251B4;
      }
    }
    v16 = v12 == 0;
    v17 = 1638400;
    if ( v16 )
LABEL_18:
      v17 = 0x10000;
    v8 = MessageBoxW(hWnd, *(LPCWSTR *)Buffer, v9, v17 | a6 | uType);
    LocalFree(*(HLOCAL *)Buffer);
  }
  return v8;
}

```

## disassembly

```asm
0x180008a6c  mov     [rsp-8+arg_10], rbx
0x180008a71  push    rbp
0x180008a72  push    rsi
0x180008a73  push    rdi
0x180008a74  push    r14
0x180008a76  push    r15
0x180008a78  lea     rbp, [rsp-5E0h]
0x180008a80  sub     rsp, 6E0h
0x180008a87  mov     rax, cs:__security_cookie
0x180008a8e  xor     rax, rsp
0x180008a91  mov     [rbp+600h+var_30], rax
0x180008a98  movaps  xmm0, xmmword ptr cs:aUnexpectedErro; "Unexpected Error.  Could not load resou"...
0x180008a9f  xor     r15d, r15d
0x180008aa2  movaps  xmm1, xmmword ptr cs:aUnexpectedErro+10h; "ed Error.  Could not load resource."
0x180008aa9  mov     r14, rcx
0x180008aac  movzx   ecx, cs:word_1800257D2
0x180008ab3  mov     r10d, edx
0x180008ab6  movaps  xmmword ptr [rsp+700h+var_6A0], xmm0
0x180008abb  movaps  xmm0, xmmword ptr cs:aUnexpectedErro+20h; ".  Could not load resource."
0x180008ac2  movaps  [rsp+700h+var_690], xmm1
0x180008ac7  movaps  xmm1, xmmword ptr cs:aUnexpectedErro+30h; " not load resource."
0x180008ace  movaps  [rbp+600h+var_680], xmm0
0x180008ad2  movaps  xmm0, xmmword ptr cs:aUnexpectedErro+40h; "d resource."
0x180008ad9  movaps  [rbp+600h+var_670], xmm1
0x180008add  movsd   xmm1, qword ptr cs:aUnexpectedErro+50h; "ce."
0x180008ae5  movaps  [rbp+600h+var_660], xmm0
0x180008ae9  movsd   [rbp+600h+var_650], xmm1
0x180008aee  mov     qword ptr [rsp+700h+Buffer], r15
0x180008af3  test    cl, 2
0x180008af6  jnz     short loc_180008B06
0x180008af8  test    cl, 1
0x180008afb  jz      short loc_180008B06
0x180008afd  lea     eax, [r15+1]
0x180008b01  jmp     loc_180008C59
0x180008b06  mov     [rsp+700h+var_6B8], r8
0x180008b0b  lea     rdx, [rbp+600h+Source]; lpBuffer
0x180008b12  mov     edi, 200h
0x180008b17  mov     [rsp+700h+var_6B0], r9
0x180008b1c  mov     r8d, edi; cchBufferMax
0x180008b1f  mov     ecx, r10d; uID
0x180008b22  or      ebx, 0FFFFFFFFh
0x180008b25  call    ?LoadSz@@YAPEAGIPEAGI@Z; LoadSz(uint,ushort *,uint)
0x180008b2a  cmp     [rbp+600h+Source], r15w
0x180008b32  jnz     short loc_180008B47
0x180008b34  lea     r8, [rsp+700h+var_6A0]; unsigned __int16 *
0x180008b39  mov     edx, edi; unsigned __int64
0x180008b3b  lea     rcx, [rbp+600h+Source]; unsigned __int16 *
0x180008b42  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008b47  lea     rax, [rsp+700h+var_6B8]
0x180008b4c  xor     r9d, r9d; dwLanguageId
0x180008b4f  mov     [rsp+700h+Arguments], rax; Arguments
0x180008b54  lea     rdx, [rbp+600h+Source]; lpSource
0x180008b5b  lea     rax, [rsp+700h+Buffer]
0x180008b60  mov     [rsp+700h+nSize], r15d; nSize
0x180008b65  xor     r8d, r8d; dwMessageId
0x180008b68  mov     [rsp+700h+lpBuffer], rax; lpBuffer
0x180008b6d  mov     ecx, 2500h; dwFlags
0x180008b72  call    cs:__imp_FormatMessageW
0x180008b78  test    eax, eax
0x180008b7a  jz      loc_180008C57
0x180008b80  mov     ebx, [rbp+600h+uType]
0x180008b86  mov     ecx, ebx; uType
0x180008b88  call    cs:__imp_MessageBeep
0x180008b8e  mov     rdi, cs:pszTitleString
0x180008b95  test    rdi, rdi
0x180008b98  jnz     short loc_180008BCB
0x180008b9a  mov     edi, 104h
0x180008b9f  lea     rdx, [rbp+600h+var_640]; lpBuffer
0x180008ba3  mov     r8d, edi; cchBufferMax
0x180008ba6  mov     ecx, 48Fh; uID
0x180008bab  call    ?LoadSz@@YAPEAGIPEAGI@Z; LoadSz(uint,ushort *,uint)
0x180008bb0  cmp     [rbp+600h+var_640], r15w
0x180008bb5  jnz     short loc_180008BC7
0x180008bb7  lea     r8, [rsp+700h+var_6A0]; unsigned __int16 *
0x180008bbc  mov     edx, edi; unsigned __int64
0x180008bbe  lea     rcx, [rbp+600h+var_640]; unsigned __int16 *
0x180008bc2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008bc7  lea     rdi, [rbp+600h+var_640]
0x180008bcb  or      ebx, [rbp+600h+arg_28]
0x180008bd1  call    RunningOnWin95BiDiLoc
0x180008bd6  test    eax, eax
0x180008bd8  jz      short loc_180008C2F
0x180008bda  mov     eax, cs:dword_1800251B4
0x180008be0  cmp     eax, 0FFFFFFFEh
0x180008be3  jnz     short loc_180008C26
0x180008be5  mov     rsi, cs:g_hinstMUI
0x180008bec  lea     r9d, [rax+3]
0x180008bf0  mov     rcx, rsi
0x180008bf3  mov     cs:dword_1800251B4, r15d
0x180008bfa  call    GetResourceLanguage
0x180008bff  test    eax, eax
0x180008c01  jnz     short loc_180008C1B
0x180008c03  lea     r9d, [rax+0Dh]
0x180008c07  mov     rcx, rsi
0x180008c0a  call    GetResourceLanguage
0x180008c0f  test    eax, eax
0x180008c11  jnz     short loc_180008C1B
0x180008c13  mov     eax, cs:dword_1800251B4
0x180008c19  jmp     short loc_180008C26
0x180008c1b  mov     eax, 1
0x180008c20  mov     cs:dword_1800251B4, eax
0x180008c26  test    eax, eax
0x180008c28  mov     eax, 190000h
0x180008c2d  jnz     short loc_180008C34
0x180008c2f  mov     eax, 10000h
0x180008c34  mov     rdx, qword ptr [rsp+700h+Buffer]; lpText
0x180008c39  or      ebx, eax
0x180008c3b  mov     r9d, ebx; uType
0x180008c3e  mov     r8, rdi; lpCaption
0x180008c41  mov     rcx, r14; hWnd
0x180008c44  call    cs:__imp_MessageBoxW
0x180008c4a  mov     rcx, qword ptr [rsp+700h+Buffer]; hMem
0x180008c4f  mov     ebx, eax
0x180008c51  call    cs:__imp_LocalFree
0x180008c57  mov     eax, ebx
0x180008c59  mov     rcx, [rbp+600h+var_30]
0x180008c60  xor     rcx, rsp; StackCookie
0x180008c63  call    __security_check_cookie
0x180008c68  mov     rbx, [rsp+700h+arg_10]
0x180008c70  add     rsp, 6E0h
0x180008c77  pop     r15
0x180008c79  pop     r14
0x180008c7b  pop     rdi
0x180008c7c  pop     rsi
0x180008c7d  pop     rbp
0x180008c7e  retn
```
