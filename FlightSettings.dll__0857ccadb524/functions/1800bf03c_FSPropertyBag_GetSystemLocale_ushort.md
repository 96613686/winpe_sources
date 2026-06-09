# FSPropertyBag::GetSystemLocale(ushort * *)

- ea: `0x1800bf03c`
- end: `0x1800bf0fe`
- name: `?GetSystemLocale@FSPropertyBag@@AEAAJPEAPEAG@Z`
- size: `194`
- prototype: `__int64 __fastcall(FSPropertyBag *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ba770`

## callees

- `0x1800254ac`
- `0x1800bf03c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf07e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf0d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf07e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf0d2`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800bf074`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800bf0b8`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800bf074`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800bf0b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf09b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf09b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf090`

## pseudocode

```c
__int64 __fastcall FSPropertyBag::GetSystemLocale(FSPropertyBag *this, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rbx
  unsigned int v4; // ebx
  signed int LastError; // eax
  ULONG pcchLanguagesBuffer; // [rsp+30h] [rbp+8h] BYREF
  int v8; // [rsp+34h] [rbp+Ch]
  ULONG pulNumLanguages; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int16 *v10; // [rsp+48h] [rbp+20h] BYREF

  v8 = HIDWORD(this);
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  v10 = 0;
  if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer)
    && GetLastError() != 122
    && (v3 = (unsigned __int16 *)CoTaskMemAlloc(2LL * pcchLanguagesBuffer),
        CoTaskMemFree(0),
        v10 = v3,
        GetSystemPreferredUILanguages(8u, &pulNumLanguages, v3, &pcchLanguagesBuffer)) )
  {
    *a2 = v3;
    v4 = 0;
    v10 = 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v10);
  return v4;
}

```

## disassembly

```asm
0x1800bf03c  mov     rax, rsp
0x1800bf03f  mov     [rax+10h], rbx
0x1800bf043  mov     [rax+8], rcx
0x1800bf047  push    rdi
0x1800bf048  sub     rsp, 20h
0x1800bf04c  xor     r8d, r8d; pwszLanguagesBuffer
0x1800bf04f  mov     dword ptr [rax+18h], 0
0x1800bf056  mov     rdi, rdx
0x1800bf059  mov     dword ptr [rax+8], 0
0x1800bf060  lea     r9, [rax+8]; pcchLanguagesBuffer
0x1800bf064  mov     qword ptr [rax+20h], 0
0x1800bf06c  lea     rdx, [rax+18h]; pulNumLanguages
0x1800bf070  lea     ecx, [r8+8]; dwFlags
0x1800bf074  call    cs:__imp_GetSystemPreferredUILanguages
0x1800bf07a  test    eax, eax
0x1800bf07c  jz      short loc_1800BF0D2
0x1800bf07e  call    cs:__imp_GetLastError
0x1800bf084  cmp     eax, 7Ah ; 'z'
0x1800bf087  jz      short loc_1800BF0D2
0x1800bf089  mov     ecx, [rsp+28h+pcchLanguagesBuffer]
0x1800bf08d  add     rcx, rcx; cb
0x1800bf090  call    cs:__imp_CoTaskMemAlloc
0x1800bf096  xor     ecx, ecx; pv
0x1800bf098  mov     rbx, rax
0x1800bf09b  call    cs:__imp_CoTaskMemFree
0x1800bf0a1  lea     r9, [rsp+28h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800bf0a6  mov     [rsp+28h+arg_18], rbx
0x1800bf0ab  mov     r8, rbx; pwszLanguagesBuffer
0x1800bf0ae  lea     rdx, [rsp+28h+pulNumLanguages]; pulNumLanguages
0x1800bf0b3  mov     ecx, 8; dwFlags
0x1800bf0b8  call    cs:__imp_GetSystemPreferredUILanguages
0x1800bf0be  test    eax, eax
0x1800bf0c0  jz      short loc_1800BF0D2
0x1800bf0c2  mov     [rdi], rbx
0x1800bf0c5  xor     ebx, ebx
0x1800bf0c7  mov     [rsp+28h+arg_18], 0
0x1800bf0d0  jmp     short loc_1800BF0E7
0x1800bf0d2  call    cs:__imp_GetLastError
0x1800bf0d8  mov     ebx, eax
0x1800bf0da  test    eax, eax
0x1800bf0dc  jle     short loc_1800BF0E7
0x1800bf0de  movzx   ebx, ax
0x1800bf0e1  or      ebx, 80070000h
0x1800bf0e7  lea     rcx, [rsp+28h+arg_18]
0x1800bf0ec  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800bf0f1  mov     eax, ebx
0x1800bf0f3  mov     rbx, [rsp+28h+arg_8]
0x1800bf0f8  add     rsp, 20h
0x1800bf0fc  pop     rdi
0x1800bf0fd  retn
```
