# VassertFun(char const *,char const *,int)

- ea: `0x1800fb110`
- end: `0x1800fb40d`
- name: `?VassertFun@@YAXPEBD0H@Z`
- size: `765`
- prototype: `void __fastcall(const char *, const char *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800fb550`

## callees

- `0x180040988`
- `0x18004236c`
- `0x180083790`
- `0x1800fb110`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x1800fb2b6`
- `KERNEL32!RtlCaptureContext` at `0x1800fb3ae`
- `KERNEL32!RtlCaptureContext` at `0x1800fb2b6`
- `KERNEL32!RtlCaptureContext` at `0x1800fb3ae`
- `KERNEL32!DebugBreak` at `0x1800fb3e8`
- `KERNEL32!DebugBreak` at `0x1800fb3e8`
- `KERNEL32!TlsGetValue` at `0x1800fb149`
- `KERNEL32!TlsGetValue` at `0x1800fb3c0`
- `KERNEL32!TlsGetValue` at `0x1800fb149`
- `KERNEL32!TlsGetValue` at `0x1800fb3c0`
- `KERNEL32!GetCurrentThreadId` at `0x1800fb182`
- `KERNEL32!GetCurrentThreadId` at `0x1800fb182`
- `ADVAPI32!RegOpenKeyExA` at `0x1800fb258`
- `ADVAPI32!RegOpenKeyExA` at `0x1800fb314`
- `ADVAPI32!RegOpenKeyExA` at `0x1800fb258`
- `ADVAPI32!RegOpenKeyExA` at `0x1800fb314`
- `ADVAPI32!RegCloseKey` at `0x1800fb267`
- `ADVAPI32!RegCloseKey` at `0x1800fb323`
- `ADVAPI32!RegCloseKey` at `0x1800fb267`
- `ADVAPI32!RegCloseKey` at `0x1800fb323`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1800fb17a`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1800fb17a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fb28b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fb383`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fb28b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fb383`
- `USER32!MessageBoxA` at `0x1800fb35a`
- `USER32!MessageBoxA` at `0x1800fb35a`

## string_xrefs

- `0x1800fb18b`: `thread 0x%x`
- `0x1800fb306`: `Software\Microsoft\FrontPage\ServerExtensions\IgnoreAsserts`
- `0x1800fb24a`: `Software\Microsoft\FrontPage\ServerExtensions\NoAssertMsgBox`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall VassertFun(const char *a1, const char *a2, int a3)
{
  const char ***Value; // rax
  const char ***v7; // rbx
  const char **v8; // r8
  void (*v9)(void *, __int64, __int64, __int64, int, const char *, ...); // rax
  HKEY v10; // rax
  HKEY v11; // rbx
  char v12; // al
  int v13; // eax
  HKEY v14; // rax
  LPVOID v15; // rax
  int phkResult; // [rsp+20h] [rbp-4F8h]
  HKEY hKey[2]; // [rsp+50h] [rbp-4C8h] BYREF
  char Destination[128]; // [rsp+60h] [rbp-4B8h] BYREF
  CHAR Text[1024]; // [rsp+E0h] [rbp-438h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  Value = (const char ***)TlsGetValue(dwTlsIndex);
  v7 = Value;
  if ( Value && *((int *)Value + 4) > 0 && (v8 = Value[3], *v8) )
  {
    strncpy_s(Destination, 0x80u, *v8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    GetCurrentThreadId();
    sub_180040988(Destination, 0xFFFFFFFFFFFFFFFFuLL, "thread 0x%x");
  }
  v9 = *(void (**)(void *, __int64, __int64, __int64, int, const char *, ...))(off_1802AB3C8 + 80LL);
  LOWORD(phkResult) = 0;
  if ( byte_1802AF49C )
    v9(&off_1802AB3C8, 946565170, 117141511, 0, phkResult, "**** Assert failure in %s(xx); '%.400s' ***", a2, a1);
  else
    v9(&off_1802AB3C8, 946565171, 117141511, 8, phkResult, "**** Assert failure in %s(%d) '%.400s' ***", a2, a3, a1);
  if ( !byte_1802AF4A0 )
  {
    if ( !RegOpenKeyExA(
            HKEY_LOCAL_MACHINE,
            "Software\\Microsoft\\FrontPage\\ServerExtensions\\NoAssertMsgBox",
            0,
            0x20019u,
            hKey) )
    {
      RegCloseKey(hKey[0]);
      if ( !v7 )
        return;
      if ( dword_1802B0018 )
        v10 = (HKEY)COWSAllocator::AllocCurrentHeap(0x4E0u);
      else
        v10 = (HKEY)malloc(0x4E0u);
      v11 = v10;
      hKey[0] = v10;
      if ( !v10 )
      {
        v11 = 0;
        goto LABEL_30;
      }
      goto LABEL_28;
    }
    sub_18004236C(
      Text,
      0xFFFFFFFFFFFFFFFFuLL,
      "Assert failed (Vframework [%s]) File '%.200s', line %d\nExpression = '%.400s'\n(click Retry to debug)");
    if ( RegOpenKeyExA(
           HKEY_LOCAL_MACHINE,
           "Software\\Microsoft\\FrontPage\\ServerExtensions\\IgnoreAsserts",
           0,
           0x20019u,
           hKey) )
    {
      v12 = 0;
    }
    else
    {
      RegCloseKey(hKey[0]);
      v12 = 1;
    }
    v13 = v12 != 0 ? 5 : 3;
    if ( byte_1802757AC )
      v13 = MessageBoxA(0, Text, "SharePoint", 0x12u);
    if ( v13 == 3 )
    {
      if ( !v7 )
        return;
      if ( dword_1802B0018 )
        v14 = (HKEY)COWSAllocator::AllocCurrentHeap(0x4E0u);
      else
        v14 = (HKEY)malloc(0x4E0u);
      v11 = v14;
      hKey[0] = v14;
      if ( !v14 )
      {
        v11 = 0;
LABEL_30:
        v15 = TlsGetValue(dwTlsIndex);
        if ( v15 )
          (*(void (__fastcall **)(LPVOID, HKEY))(*(_QWORD *)v15 + 40LL))(v15, v11);
        return;
      }
LABEL_28:
      *(_QWORD *)v11 = &Vstatus::`vftable';
      *(_QWORD *)v11 = &VassertContextStatus::`vftable';
      RtlCaptureContext((PCONTEXT)(v11 + 4));
      goto LABEL_30;
    }
    if ( v13 == 4 )
      DebugBreak();
  }
}

```

## disassembly

```asm
0x1800fb110  push    rbx
0x1800fb112  push    rbp
0x1800fb113  push    rsi
0x1800fb114  push    r14
0x1800fb116  push    r15
0x1800fb118  sub     rsp, 4F0h
0x1800fb11f  mov     [rsp+518h+var_4C0], 0FFFFFFFFFFFFFFFEh
0x1800fb128  mov     rax, cs:__security_cookie
0x1800fb12f  xor     rax, rsp
0x1800fb132  mov     [rsp+518h+var_38], rax
0x1800fb13a  mov     r14d, r8d
0x1800fb13d  mov     rbp, rdx
0x1800fb140  mov     rsi, rcx
0x1800fb143  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800fb149  call    cs:TlsGetValue
0x1800fb14f  mov     rbx, rax
0x1800fb152  xor     r15d, r15d
0x1800fb155  test    rax, rax
0x1800fb158  jz      short loc_1800FB182
0x1800fb15a  cmp     [rax+10h], r15d
0x1800fb15e  jle     short loc_1800FB182
0x1800fb160  mov     r8, [rax+18h]
0x1800fb164  cmp     [r8], r15
0x1800fb167  jz      short loc_1800FB182
0x1800fb169  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800fb16d  mov     r8, [r8]; Source
0x1800fb170  mov     edx, 80h; SizeInBytes
0x1800fb175  lea     rcx, [rsp+518h+Destination]; Destination
0x1800fb17a  call    cs:strncpy_s
0x1800fb180  jmp     short loc_1800FB1A0
0x1800fb182  call    cs:GetCurrentThreadId
0x1800fb188  mov     r9d, eax
0x1800fb18b  lea     r8, aThread0xX; "thread 0x%x"
0x1800fb192  or      rdx, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800fb196  lea     rcx, [rsp+518h+Destination]; Buffer
0x1800fb19b  call    sub_180040988
0x1800fb1a0  mov     rax, cs:off_1802AB3C8
0x1800fb1a7  mov     r8d, 6FB7007h
0x1800fb1ad  mov     rax, [rax+50h]
0x1800fb1b1  cmp     cs:byte_1802AF49C, r15b
0x1800fb1b8  jz      short loc_1800FB1EE
0x1800fb1ba  mov     [rsp+518h+var_4E0], rsi
0x1800fb1bf  mov     [rsp+518h+var_4E8], rbp
0x1800fb1c4  lea     rcx, aAssertFailureI; "**** Assert failure in %s(xx); '%.400s'"...
0x1800fb1cb  mov     [rsp+518h+var_4F0], rcx
0x1800fb1d0  mov     word ptr [rsp+518h+phkResult], r15w
0x1800fb1d6  movzx   r9d, r15w
0x1800fb1da  mov     edx, 386B7032h
0x1800fb1df  lea     rcx, off_1802AB3C8
0x1800fb1e6  call    cs:__guard_dispatch_icall_fptr
0x1800fb1ec  jmp     short loc_1800FB22A
0x1800fb1ee  mov     edx, 8
0x1800fb1f3  mov     [rsp+518h+var_4D8], rsi
0x1800fb1f8  mov     dword ptr [rsp+518h+var_4E0], r14d
0x1800fb1fd  mov     [rsp+518h+var_4E8], rbp
0x1800fb202  lea     rcx, aAssertFailureI_0; "**** Assert failure in %s(%d) '%.400s' "...
0x1800fb209  mov     [rsp+518h+var_4F0], rcx
0x1800fb20e  mov     word ptr [rsp+518h+phkResult], r15w
0x1800fb214  movzx   r9d, dx
0x1800fb218  mov     edx, 386B7033h
0x1800fb21d  lea     rcx, off_1802AB3C8
0x1800fb224  call    cs:__guard_dispatch_icall_fptr
0x1800fb22a  cmp     cs:byte_1802AF4A0, r15b
0x1800fb231  jnz     loc_1800FB3EE
0x1800fb237  lea     rax, [rsp+518h+hKey]
0x1800fb23c  mov     [rsp+518h+phkResult], rax; phkResult
0x1800fb241  mov     r9d, 20019h; samDesired
0x1800fb247  xor     r8d, r8d; ulOptions
0x1800fb24a  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\FrontPage\\ServerE"...
0x1800fb251  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800fb258  call    cs:RegOpenKeyExA
0x1800fb25e  test    eax, eax
0x1800fb260  jnz     short loc_1800FB2C7
0x1800fb262  mov     rcx, [rsp+518h+hKey]; hKey
0x1800fb267  call    cs:RegCloseKey
0x1800fb26d  test    rbx, rbx
0x1800fb270  jz      loc_1800FB3EE
0x1800fb276  mov     ecx, 4E0h; unsigned __int64
0x1800fb27b  cmp     cs:dword_1802B0018, r15d
0x1800fb282  jz      short loc_1800FB28B
0x1800fb284  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800fb289  jmp     short loc_1800FB291
0x1800fb28b  call    cs:malloc
0x1800fb291  mov     rbx, rax
0x1800fb294  mov     [rsp+518h+hKey], rax
0x1800fb299  test    rax, rax
0x1800fb29c  jz      short loc_1800FB2BF
0x1800fb29e  lea     rax, ??_7Vstatus@@6B@; const Vstatus::`vftable'
0x1800fb2a5  mov     [rbx], rax
0x1800fb2a8  lea     rax, ??_7VassertContextStatus@@6B@; const VassertContextStatus::`vftable'
0x1800fb2af  mov     [rbx], rax
0x1800fb2b2  lea     rcx, [rbx+10h]; ContextRecord
0x1800fb2b6  call    cs:RtlCaptureContext
0x1800fb2bc  nop
0x1800fb2bd  jmp     short loc_1800FB2C2
0x1800fb2bf  mov     rbx, r15
0x1800fb2c2  jmp     loc_1800FB3BA
0x1800fb2c7  mov     [rsp+518h+var_4E8], rsi
0x1800fb2cc  mov     dword ptr [rsp+518h+var_4F0], r14d
0x1800fb2d1  mov     [rsp+518h+phkResult], rbp
0x1800fb2d6  lea     r9, [rsp+518h+Destination]
0x1800fb2db  lea     r8, aAssertFailedVf; "Assert failed (Vframework [%s]) File '%"...
0x1800fb2e2  or      rdx, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800fb2e6  lea     rcx, [rsp+518h+Text]; Buffer
0x1800fb2ee  call    sub_18004236C
0x1800fb2f3  lea     rax, [rsp+518h+hKey]
0x1800fb2f8  mov     [rsp+518h+phkResult], rax; phkResult
0x1800fb2fd  mov     r9d, 20019h; samDesired
0x1800fb303  xor     r8d, r8d; ulOptions
0x1800fb306  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\FrontPage\\ServerE"...
0x1800fb30d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800fb314  call    cs:RegOpenKeyExA
0x1800fb31a  test    eax, eax
0x1800fb31c  jnz     short loc_1800FB32D
0x1800fb31e  mov     rcx, [rsp+518h+hKey]; hKey
0x1800fb323  call    cs:RegCloseKey
0x1800fb329  mov     al, 1
0x1800fb32b  jmp     short loc_1800FB330
0x1800fb32d  mov     al, r15b
0x1800fb330  neg     al
0x1800fb332  sbb     eax, eax
0x1800fb334  and     eax, 2
0x1800fb337  add     eax, 3
0x1800fb33a  cmp     cs:byte_1802757AC, r15b
0x1800fb341  jz      short loc_1800FB360
0x1800fb343  mov     r9d, 12h; uType
0x1800fb349  lea     r8, Caption; "SharePoint"
0x1800fb350  lea     rdx, [rsp+518h+Text]; lpText
0x1800fb358  xor     ecx, ecx; hWnd
0x1800fb35a  call    cs:MessageBoxA
0x1800fb360  cmp     eax, 3
0x1800fb363  jnz     short loc_1800FB3E3
0x1800fb365  test    rbx, rbx
0x1800fb368  jz      loc_1800FB3EE
0x1800fb36e  mov     ecx, 4E0h; unsigned __int64
0x1800fb373  cmp     cs:dword_1802B0018, r15d
0x1800fb37a  jz      short loc_1800FB383
0x1800fb37c  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800fb381  jmp     short loc_1800FB389
0x1800fb383  call    cs:malloc
0x1800fb389  mov     rbx, rax
0x1800fb38c  mov     [rsp+518h+hKey], rax
0x1800fb391  test    rax, rax
0x1800fb394  jz      short loc_1800FB3B7
0x1800fb396  lea     rax, ??_7Vstatus@@6B@; const Vstatus::`vftable'
0x1800fb39d  mov     [rbx], rax
0x1800fb3a0  lea     rax, ??_7VassertContextStatus@@6B@; const VassertContextStatus::`vftable'
0x1800fb3a7  mov     [rbx], rax
0x1800fb3aa  lea     rcx, [rbx+10h]; ContextRecord
0x1800fb3ae  call    cs:RtlCaptureContext
0x1800fb3b4  nop
0x1800fb3b5  jmp     short loc_1800FB3BA
0x1800fb3b7  mov     rbx, r15
0x1800fb3ba  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800fb3c0  call    cs:TlsGetValue
0x1800fb3c6  mov     r8, rax
0x1800fb3c9  test    rax, rax
0x1800fb3cc  jz      short loc_1800FB3EE
0x1800fb3ce  mov     rcx, [rax]
0x1800fb3d1  mov     rax, [rcx+28h]
0x1800fb3d5  mov     rdx, rbx
0x1800fb3d8  mov     rcx, r8
0x1800fb3db  call    cs:__guard_dispatch_icall_fptr
0x1800fb3e1  jmp     short loc_1800FB3EE
0x1800fb3e3  cmp     eax, 4
0x1800fb3e6  jnz     short loc_1800FB3EE
0x1800fb3e8  call    cs:DebugBreak
0x1800fb3ee  mov     rcx, [rsp+518h+var_38]
0x1800fb3f6  xor     rcx, rsp
0x1800fb3f9  call    sub_1801503E0
0x1800fb3fe  add     rsp, 4F0h
0x1800fb405  pop     r15
0x1800fb407  pop     r14
0x1800fb409  pop     rsi
0x1800fb40a  pop     rbp
0x1800fb40b  pop     rbx
0x1800fb40c  retn
```
