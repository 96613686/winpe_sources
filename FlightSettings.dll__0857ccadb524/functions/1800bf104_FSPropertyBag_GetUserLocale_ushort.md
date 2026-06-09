# FSPropertyBag::GetUserLocale(ushort * *)

- ea: `0x1800bf104`
- end: `0x1800bf1bb`
- name: `?GetUserLocale@FSPropertyBag@@AEAAJPEAPEAG@Z`
- size: `183`
- prototype: `__int64 __fastcall(FSPropertyBag *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ba770`

## callees

- `0x1800254ac`
- `0x1800bf104`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf18f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf18f`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1800bf13c`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1800bf175`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1800bf13c`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1800bf175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf14d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf14d`

## pseudocode

```c
__int64 __fastcall FSPropertyBag::GetUserLocale(FSPropertyBag *this, unsigned __int16 **a2)
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
  if ( GetUserPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer)
    && (v3 = (unsigned __int16 *)CoTaskMemAlloc(2LL * pcchLanguagesBuffer),
        CoTaskMemFree(0),
        v10 = v3,
        GetUserPreferredUILanguages(8u, &pulNumLanguages, v3, &pcchLanguagesBuffer)) )
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
0x1800bf104  mov     rax, rsp
0x1800bf107  mov     [rax+10h], rbx
0x1800bf10b  mov     [rax+8], rcx
0x1800bf10f  push    rdi
0x1800bf110  sub     rsp, 20h
0x1800bf114  xor     r8d, r8d; pwszLanguagesBuffer
0x1800bf117  mov     dword ptr [rax+18h], 0
0x1800bf11e  mov     rdi, rdx
0x1800bf121  mov     dword ptr [rax+8], 0
0x1800bf128  lea     r9, [rax+8]; pcchLanguagesBuffer
0x1800bf12c  mov     qword ptr [rax+20h], 0
0x1800bf134  lea     rdx, [rax+18h]; pulNumLanguages
0x1800bf138  lea     ecx, [r8+8]; dwFlags
0x1800bf13c  call    cs:__imp_GetUserPreferredUILanguages
0x1800bf142  test    eax, eax
0x1800bf144  jz      short loc_1800BF18F
0x1800bf146  mov     ecx, [rsp+28h+pcchLanguagesBuffer]
0x1800bf14a  add     rcx, rcx; cb
0x1800bf14d  call    cs:__imp_CoTaskMemAlloc
0x1800bf153  xor     ecx, ecx; pv
0x1800bf155  mov     rbx, rax
0x1800bf158  call    cs:__imp_CoTaskMemFree
0x1800bf15e  lea     r9, [rsp+28h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800bf163  mov     [rsp+28h+arg_18], rbx
0x1800bf168  mov     r8, rbx; pwszLanguagesBuffer
0x1800bf16b  lea     rdx, [rsp+28h+pulNumLanguages]; pulNumLanguages
0x1800bf170  mov     ecx, 8; dwFlags
0x1800bf175  call    cs:__imp_GetUserPreferredUILanguages
0x1800bf17b  test    eax, eax
0x1800bf17d  jz      short loc_1800BF18F
0x1800bf17f  mov     [rdi], rbx
0x1800bf182  xor     ebx, ebx
0x1800bf184  mov     [rsp+28h+arg_18], 0
0x1800bf18d  jmp     short loc_1800BF1A4
0x1800bf18f  call    cs:__imp_GetLastError
0x1800bf195  mov     ebx, eax
0x1800bf197  test    eax, eax
0x1800bf199  jle     short loc_1800BF1A4
0x1800bf19b  movzx   ebx, ax
0x1800bf19e  or      ebx, 80070000h
0x1800bf1a4  lea     rcx, [rsp+28h+arg_18]
0x1800bf1a9  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800bf1ae  mov     eax, ebx
0x1800bf1b0  mov     rbx, [rsp+28h+arg_8]
0x1800bf1b5  add     rsp, 20h
0x1800bf1b9  pop     rdi
0x1800bf1ba  retn
```
