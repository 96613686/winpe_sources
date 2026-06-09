# DisplayMessageBox(HWND__ *,uint,ulong,uint,...)

- ea: `0x1800086d4`
- end: `0x1800088ff`
- name: `?DisplayMessageBox@@YAHPEAUHWND__@@IKIZZ`
- size: `555`
- prototype: `__int64(HWND, unsigned int, unsigned int, unsigned int, ...)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180008d48`
- `0x180009388`

## callees

- `0x180007b10`
- `0x1800086d4`
- `0x180008920`
- `0x18000a9d0`
- `0x18000aa90`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180008870`
- `KERNEL32!LocalFree` at `0x18000887b`
- `KERNEL32!LocalFree` at `0x180008870`
- `KERNEL32!LocalFree` at `0x18000887b`
- `KERNEL32!FormatMessageW` at `0x1800087cc`
- `KERNEL32!FormatMessageW` at `0x180008848`
- `KERNEL32!FormatMessageW` at `0x1800087cc`
- `KERNEL32!FormatMessageW` at `0x180008848`
- `KERNEL32!GetLastError` at `0x180008885`
- `KERNEL32!GetLastError` at `0x180008885`
- `USER32!MessageBoxW` at `0x18000876d`
- `USER32!MessageBoxW` at `0x180008863`
- `USER32!MessageBoxW` at `0x1800088c3`
- `USER32!MessageBoxW` at `0x18000876d`
- `USER32!MessageBoxW` at `0x180008863`
- `USER32!MessageBoxW` at `0x1800088c3`
- `USER32!LoadStringW` at `0x180008731`
- `USER32!LoadStringW` at `0x18000878b`
- `USER32!LoadStringW` at `0x1800087f8`
- `USER32!LoadStringW` at `0x180008731`
- `USER32!LoadStringW` at `0x18000878b`
- `USER32!LoadStringW` at `0x1800087f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800088cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800088d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800088cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800088d6`

## pseudocode

```c
__int64 DisplayMessageBox(HWND a1, UINT a2, DWORD a3, UINT a4, ...)
{
  unsigned int v7; // edi
  WCHAR *v8; // rbx
  int ErrorMessage; // eax
  DWORD v10; // eax
  DWORD v11; // esi
  int *v12; // rax
  signed int LastError; // eax
  bool v14; // sf
  va_list Arguments; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v17[4]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR lpBuffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  va_list v19[3]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Text[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[1024]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Source[1024]; // [rsp+8B0h] [rbp+7B0h] BYREF
  va_list va; // [rsp+1120h] [rbp+1020h] BYREF

  va_start(va, a4);
  v7 = 0;
  v8 = 0;
  Arguments = 0;
  LoadStringW(hInstance, 0x66u, Buffer, 1024);
  if ( a3 )
  {
    ErrorMessage = GetErrorMessage(a3, (unsigned __int16 **)&Arguments);
    va_copy((va_list)v8, Arguments);
    if ( ErrorMessage < 0 )
      goto LABEL_11;
  }
  if ( !a4 )
  {
    v7 = MessageBoxW(a1, v8, Buffer, a2);
LABEL_11:
    LastError = GetLastError();
    v14 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = LastError < 0;
    }
    if ( v14 )
    {
      StringCchPrintfW(Text, 0x20u, L"0x%x", (unsigned int)LastError);
      v7 = MessageBoxW(a1, Text, Buffer, a2);
    }
    goto LABEL_15;
  }
  LoadStringW(hInstance, a4, Source, 1024);
  *(_QWORD *)lpBuffer = 0;
  va_copy(Arguments, va);
  v10 = FormatMessageW(0x500u, Source, 0, 0, lpBuffer, 0, &Arguments);
  Arguments = 0;
  v11 = v10;
  if ( v10 )
  {
    LoadStringW(hInstance, 0x12Du, Text, 32);
    v19[0] = *(va_list *)lpBuffer;
    v12 = &dword_18000F72C;
    *(_QWORD *)v17 = 0;
    if ( a3 )
      v12 = (int *)v8;
    v19[1] = (va_list)v12;
    v11 = FormatMessageW(0x2500u, Text, 0, 0, v17, 0, v19);
    if ( v11 )
    {
      v7 = MessageBoxW(a1, *(LPCWSTR *)v17, Buffer, a2);
      LocalFree(*(HLOCAL *)v17);
    }
  }
  LocalFree(*(HLOCAL *)lpBuffer);
  if ( !v11 )
    goto LABEL_11;
LABEL_15:
  SysFreeString(0);
  SysFreeString(v8);
  return v7;
}

```

## disassembly

```asm
0x1800086d4  mov     [rsp-8+uID], r9d
0x1800086d9  push    rbp
0x1800086da  push    rbx
0x1800086db  push    rsi
0x1800086dc  push    rdi
0x1800086dd  push    r12
0x1800086df  push    r14
0x1800086e1  push    r15
0x1800086e3  lea     rbp, [rsp-0FC0h]
0x1800086eb  mov     eax, 10C0h
0x1800086f0  call    _alloca_probe
0x1800086f5  sub     rsp, rax
0x1800086f8  mov     rax, cs:__security_cookie
0x1800086ff  xor     rax, rsp
0x180008702  mov     [rbp+0FF0h+var_40], rax
0x180008709  mov     r12d, r8d
0x18000870c  mov     r15d, edx
0x18000870f  mov     r14, rcx
0x180008712  lea     r8, [rbp+0FF0h+Buffer]; lpBuffer
0x180008716  mov     rcx, cs:hInstance; hInstance
0x18000871d  xor     edi, edi
0x18000871f  mov     esi, 400h
0x180008724  xor     ebx, ebx
0x180008726  mov     r9d, esi; cchBufferMax
0x180008729  mov     [rsp+10F0h+var_10B0], rbx
0x18000872e  lea     edx, [rdi+66h]; uID
0x180008731  call    cs:__imp_LoadStringW
0x180008737  test    r12d, r12d
0x18000873a  jz      short loc_180008756
0x18000873c  lea     rdx, [rsp+10F0h+var_10B0]; unsigned __int16 **
0x180008741  mov     ecx, r12d; dwMessageId
0x180008744  call    ?GetErrorMessage@@YAJKPEAPEAG@Z; GetErrorMessage(ulong,ushort * *)
0x180008749  mov     rbx, [rsp+10F0h+var_10B0]
0x18000874e  test    eax, eax
0x180008750  js      loc_180008885
0x180008756  mov     edx, [rbp+0FF0h+uID]; uID
0x18000875c  test    edx, edx
0x18000875e  jnz     short loc_18000877A
0x180008760  mov     r9d, r15d; uType
0x180008763  lea     r8, [rbp+0FF0h+Buffer]; lpCaption
0x180008767  mov     rdx, rbx; lpText
0x18000876a  mov     rcx, r14; hWnd
0x18000876d  call    cs:__imp_MessageBoxW
0x180008773  mov     edi, eax
0x180008775  jmp     loc_180008885
0x18000877a  mov     rcx, cs:hInstance; hInstance
0x180008781  lea     r8, [rbp+0FF0h+Source]; lpBuffer
0x180008788  mov     r9d, esi; cchBufferMax
0x18000878b  call    cs:__imp_LoadStringW
0x180008791  lea     rax, [rbp+0FF0h+arg_20]
0x180008798  mov     qword ptr [rsp+10F0h+var_10A0], rdi
0x18000879d  mov     [rsp+10F0h+var_10B0], rax
0x1800087a2  lea     rdx, [rbp+0FF0h+Source]; lpSource
0x1800087a9  lea     rax, [rsp+10F0h+var_10B0]
0x1800087ae  xor     r9d, r9d; dwLanguageId
0x1800087b1  mov     [rsp+10F0h+Arguments], rax; Arguments
0x1800087b6  xor     r8d, r8d; dwMessageId
0x1800087b9  lea     rax, [rsp+10F0h+var_10A0]
0x1800087be  mov     [rsp+10F0h+nSize], edi; nSize
0x1800087c2  mov     ecx, 500h; dwFlags
0x1800087c7  mov     [rsp+10F0h+lpBuffer], rax; lpBuffer
0x1800087cc  call    cs:__imp_FormatMessageW
0x1800087d2  mov     [rsp+10F0h+var_10B0], rdi
0x1800087d7  mov     esi, eax
0x1800087d9  test    eax, eax
0x1800087db  jz      loc_180008876
0x1800087e1  mov     rcx, cs:hInstance; hInstance
0x1800087e8  lea     r8, [rsp+10F0h+Text]; lpBuffer
0x1800087ed  mov     r9d, 20h ; ' '; cchBufferMax
0x1800087f3  mov     edx, 12Dh; uID
0x1800087f8  call    cs:__imp_LoadStringW
0x1800087fe  mov     rax, qword ptr [rsp+10F0h+var_10A0]
0x180008803  lea     rdx, [rsp+10F0h+Text]; lpSource
0x180008808  mov     [rsp+10F0h+var_1098], rax
0x18000880d  test    r12d, r12d
0x180008810  lea     rax, dword_18000F72C
0x180008817  mov     qword ptr [rsp+10F0h+var_10A8], rdi
0x18000881c  cmovnz  rax, rbx
0x180008820  mov     ecx, 2500h; dwFlags
0x180008825  mov     [rsp+10F0h+var_1090], rax
0x18000882a  xor     r9d, r9d; dwLanguageId
0x18000882d  lea     rax, [rsp+10F0h+var_1098]
0x180008832  xor     r8d, r8d; dwMessageId
0x180008835  mov     [rsp+10F0h+Arguments], rax; Arguments
0x18000883a  lea     rax, [rsp+10F0h+var_10A8]
0x18000883f  mov     [rsp+10F0h+nSize], edi; nSize
0x180008843  mov     [rsp+10F0h+lpBuffer], rax; lpBuffer
0x180008848  call    cs:__imp_FormatMessageW
0x18000884e  mov     esi, eax
0x180008850  test    eax, eax
0x180008852  jz      short loc_180008876
0x180008854  mov     rdx, qword ptr [rsp+10F0h+var_10A8]; lpText
0x180008859  lea     r8, [rbp+0FF0h+Buffer]; lpCaption
0x18000885d  mov     r9d, r15d; uType
0x180008860  mov     rcx, r14; hWnd
0x180008863  call    cs:__imp_MessageBoxW
0x180008869  mov     rcx, qword ptr [rsp+10F0h+var_10A8]; hMem
0x18000886e  mov     edi, eax
0x180008870  call    cs:__imp_LocalFree
0x180008876  mov     rcx, qword ptr [rsp+10F0h+var_10A0]; hMem
0x18000887b  call    cs:__imp_LocalFree
0x180008881  test    esi, esi
0x180008883  jnz     short loc_1800088CB
0x180008885  call    cs:__imp_GetLastError
0x18000888b  test    eax, eax
0x18000888d  jle     short loc_180008899
0x18000888f  movzx   eax, ax
0x180008892  or      eax, 80070000h
0x180008897  test    eax, eax
0x180008899  jns     short loc_1800088CB
0x18000889b  mov     r9d, eax
0x18000889e  lea     r8, a0xX; "0x%x"
0x1800088a5  mov     edx, 20h ; ' '; unsigned __int64
0x1800088aa  lea     rcx, [rsp+10F0h+Text]; unsigned __int16 *
0x1800088af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800088b4  mov     r9d, r15d; uType
0x1800088b7  lea     r8, [rbp+0FF0h+Buffer]; lpCaption
0x1800088bb  lea     rdx, [rsp+10F0h+Text]; lpText
0x1800088c0  mov     rcx, r14; hWnd
0x1800088c3  call    cs:__imp_MessageBoxW
0x1800088c9  mov     edi, eax
0x1800088cb  xor     ecx, ecx; bstrString
0x1800088cd  call    cs:__imp_SysFreeString
0x1800088d3  mov     rcx, rbx; bstrString
0x1800088d6  call    cs:__imp_SysFreeString
0x1800088dc  mov     eax, edi
0x1800088de  mov     rcx, [rbp+0FF0h+var_40]
0x1800088e5  xor     rcx, rsp; StackCookie
0x1800088e8  call    __security_check_cookie
0x1800088ed  add     rsp, 10C0h
0x1800088f4  pop     r15
0x1800088f6  pop     r14
0x1800088f8  pop     r12
0x1800088fa  pop     rdi
0x1800088fb  pop     rsi
0x1800088fc  pop     rbx
0x1800088fd  pop     rbp
0x1800088fe  retn
```
