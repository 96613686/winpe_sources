# WriteHeaderToFile(void * const,ushort)

- ea: `0x1800fa808`
- end: `0x1800faa98`
- name: `?WriteHeaderToFile@@YAJQEAXG@Z`
- size: `656`
- prototype: `__int64 __fastcall(HANDLE hFile, unsigned __int16)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800fa1fc`

## callees

- `0x18000c840`
- `0x18001a57c`
- `0x18001a64c`
- `0x1800234f8`
- `0x18002373c`
- `0x18002395c`
- `0x18002b9f0`
- `0x1800c5674`
- `0x1800fa740`
- `0x1800fa808`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa9da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa9da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800faa55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800faa55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fa8d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fa8d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800fa9ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800fa9ca`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800fa913`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800fa956`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800fa913`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800fa956`

## string_xrefs

- `0x1800faa46`: `WriteHeaderToFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteHeaderToFile(HANDLE hFile, unsigned __int16 a2)
{
  unsigned int v2; // ebx
  _WORD *v4; // rdi
  int v5; // edx
  int v6; // ecx
  signed int v7; // ebx
  int v8; // eax
  int v9; // edx
  int v10; // ecx
  DWORD v11; // ebp
  unsigned int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  const unsigned __int16 *v16; // rax
  int v17; // eax
  int v18; // ebx
  int v19; // eax
  int v20; // edx
  int v21; // ecx
  __int64 v22; // rax
  int v23; // r9d
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v27[16]; // [rsp+38h] [rbp-70h] BYREF
  int v28; // [rsp+48h] [rbp-60h]
  unsigned __int16 v29[12]; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int64 retaddr; // [rsp+A8h] [rbp+0h]

  v2 = a2;
  NumberOfBytesWritten = 0;
  v4 = 0;
  std::wstring::wstring(v27);
  if ( !(_WORD)v2 )
  {
    v7 = -2147467259;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(v6, v5, (unsigned int)"WriteHeaderToFile", 290, 5);
    goto LABEL_32;
  }
  v8 = StringCchPrintfW(v29, 0xBu, L"#LID %d", v2);
  v7 = v8;
  if ( v8 < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(v10, v9, (unsigned int)"WriteHeaderToFile", 291, v8);
    goto LABEL_32;
  }
  std::wstring::assign(v27, v29);
  v11 = 2 * v28 + 6;
  v12 = 2 * v28 + 8;
  v4 = CoTaskMemAlloc(v12);
  *v4 = -257;
  v16 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27, v13, v14, v15);
  v17 = StringCchPrintfW(v4 + 1, (unsigned __int64)v11 >> 1, v16);
  v18 = v17;
  if ( v17 )
  {
    if ( v17 == -2147024882 )
      TerminateProcessOnMemoryExhaustion(0);
    FailFastWithHR(v18, retaddr, 0x137u);
  }
  v19 = StringCchCatW(v4 + 1, (unsigned __int64)v11 >> 1, L"\r\n");
  v7 = v19;
  if ( v19 )
  {
    if ( v19 == -2147024882 )
      TerminateProcessOnMemoryExhaustion(0);
    FailFastWithHR(v7, retaddr, 0x138u);
  }
  v22 = (unsigned int)(2 * v28 + 6);
  if ( v12 - (_DWORD)v22 != 2 )
  {
    v7 = -2147418113;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_32;
    v23 = 319;
    goto LABEL_31;
  }
  if ( *((_BYTE *)v4 + v22) || *((_BYTE *)v4 + v22 + 1) )
  {
    v7 = -2147418113;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_32;
    v23 = 320;
    goto LABEL_31;
  }
  if ( WriteFile(hFile, v4, v11, &NumberOfBytesWritten, 0) )
    goto LABEL_35;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_35:
    if ( NumberOfBytesWritten == v11 )
      goto LABEL_32;
    v7 = -2147418113;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_32;
    v23 = 332;
LABEL_31:
    McTemplateU0sqq_EventWriteTransfer(v21, v20, (unsigned int)"WriteHeaderToFile", v23, 255);
    goto LABEL_32;
  }
  if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    McTemplateU0sqq_EventWriteTransfer(v21, v20, (unsigned int)"WriteHeaderToFile", 329, v7);
LABEL_32:
  CoTaskMemFree(v4);
  std::wstring::_Tidy_deallocate(v27);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800fa808  mov     [rsp+arg_10], rbx
0x1800fa80d  mov     [rsp+arg_18], rbp
0x1800fa812  push    rsi
0x1800fa813  push    rdi
0x1800fa814  push    r12
0x1800fa816  push    r14
0x1800fa818  push    r15
0x1800fa81a  sub     rsp, 80h
0x1800fa821  mov     rax, cs:__security_cookie
0x1800fa828  xor     rax, rsp
0x1800fa82b  mov     [rsp+0A8h+var_38], rax
0x1800fa830  movzx   ebx, dx
0x1800fa833  mov     r12, rcx
0x1800fa836  mov     [rsp+0A8h+NumberOfBytesWritten], 0
0x1800fa83e  xor     edi, edi
0x1800fa840  lea     rcx, [rsp+0A8h+var_70]; void *
0x1800fa845  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800fa84a  nop
0x1800fa84b  xor     eax, eax
0x1800fa84d  cmp     ax, bx
0x1800fa850  jnz     short loc_1800FA877
0x1800fa852  mov     ebx, 80004005h
0x1800fa857  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800fa85e  jz      loc_1800FAA52
0x1800fa864  mov     dword ptr [rsp+0A8h+lpOverlapped], 80004005h
0x1800fa86c  mov     r9d, 122h
0x1800fa872  jmp     loc_1800FAA46
0x1800fa877  mov     r9d, ebx
0x1800fa87a  lea     r8, aLidD; "#LID %d"
0x1800fa881  mov     edx, 0Bh; unsigned __int64
0x1800fa886  lea     rcx, [rsp+0A8h+var_50]; unsigned __int16 *
0x1800fa88b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fa890  mov     ebx, eax
0x1800fa892  test    eax, eax
0x1800fa894  jns     short loc_1800FA8B2
0x1800fa896  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800fa89d  jz      loc_1800FAA52
0x1800fa8a3  mov     dword ptr [rsp+0A8h+lpOverlapped], eax
0x1800fa8a7  mov     r9d, 123h
0x1800fa8ad  jmp     loc_1800FAA46
0x1800fa8b2  lea     rdx, [rsp+0A8h+var_50]
0x1800fa8b7  lea     rcx, [rsp+0A8h+var_70]
0x1800fa8bc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800fa8c1  mov     eax, [rsp+0A8h+var_60]
0x1800fa8c5  lea     ebp, ds:6[rax*2]
0x1800fa8cc  lea     esi, [rbp+2]
0x1800fa8cf  mov     ecx, esi; cb
0x1800fa8d1  call    cs:__imp_CoTaskMemAlloc
0x1800fa8d8  nop     dword ptr [rax+rax+00h]
0x1800fa8dd  mov     rdi, rax
0x1800fa8e0  mov     word ptr [rax], 0FEFFh
0x1800fa8e5  mov     r14d, ebp
0x1800fa8e8  shr     r14, 1
0x1800fa8eb  lea     rcx, [rsp+0A8h+var_70]
0x1800fa8f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800fa8f5  mov     r8, rax; unsigned __int16 *
0x1800fa8f8  mov     rdx, r14; unsigned __int64
0x1800fa8fb  lea     rcx, [rdi+2]; unsigned __int16 *
0x1800fa8ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fa904  mov     ebx, eax
0x1800fa906  test    eax, eax
0x1800fa908  jz      short loc_1800FA934
0x1800fa90a  cmp     eax, 8007000Eh
0x1800fa90f  jnz     short loc_1800FA91F
0x1800fa911  xor     ecx, ecx; FailedAllocationSize
0x1800fa913  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x1800fa91a  nop     dword ptr [rax+rax+00h]
0x1800fa91f  mov     rdx, [rsp+0A8h]; unsigned __int64
0x1800fa927  mov     r8d, 137h; unsigned __int64
0x1800fa92d  mov     ecx, ebx; int
0x1800fa92f  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x1800fa934  lea     r8, asc_1803036D8; "\r\n"
0x1800fa93b  mov     rdx, r14; unsigned __int64
0x1800fa93e  lea     rcx, [rdi+2]; unsigned __int16 *
0x1800fa942  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800fa947  mov     ebx, eax
0x1800fa949  test    eax, eax
0x1800fa94b  jz      short loc_1800FA977
0x1800fa94d  cmp     eax, 8007000Eh
0x1800fa952  jnz     short loc_1800FA962
0x1800fa954  xor     ecx, ecx; FailedAllocationSize
0x1800fa956  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x1800fa95d  nop     dword ptr [rax+rax+00h]
0x1800fa962  mov     rdx, [rsp+0A8h]; unsigned __int64
0x1800fa96a  mov     r8d, 138h; unsigned __int64
0x1800fa970  mov     ecx, ebx; int
0x1800fa972  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x1800fa977  mov     eax, [rsp+0A8h+var_60]
0x1800fa97b  lea     eax, ds:6[rax*2]
0x1800fa982  sub     esi, eax
0x1800fa984  cmp     esi, 2
0x1800fa987  jz      short loc_1800FA9A6
0x1800fa989  mov     ebx, 8000FFFFh
0x1800fa98e  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800fa995  jz      loc_1800FAA52
0x1800fa99b  mov     r9d, 13Fh
0x1800fa9a1  jmp     loc_1800FAA3E
0x1800fa9a6  cmp     byte ptr [rax+rdi], 0
0x1800fa9aa  jnz     short loc_1800FAA2A
0x1800fa9ac  cmp     byte ptr [rax+rdi+1], 0
0x1800fa9b1  jnz     short loc_1800FAA2A
0x1800fa9b3  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x1800fa9bc  lea     r9, [rsp+0A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800fa9c1  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800fa9c4  mov     rdx, rdi; lpBuffer
0x1800fa9c7  mov     rcx, r12; hFile
0x1800fa9ca  call    cs:__imp_WriteFile
0x1800fa9d1  nop     dword ptr [rax+rax+00h]
0x1800fa9d6  test    eax, eax
0x1800fa9d8  jnz     short loc_1800FAA0E
0x1800fa9da  call    cs:__imp_GetLastError
0x1800fa9e1  nop     dword ptr [rax+rax+00h]
0x1800fa9e6  mov     ebx, eax
0x1800fa9e8  test    eax, eax
0x1800fa9ea  jle     short loc_1800FA9F5
0x1800fa9ec  movzx   ebx, ax
0x1800fa9ef  or      ebx, 80070000h
0x1800fa9f5  test    ebx, ebx
0x1800fa9f7  jns     short loc_1800FAA0E
0x1800fa9f9  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800faa00  jz      short loc_1800FAA52
0x1800faa02  mov     dword ptr [rsp+0A8h+lpOverlapped], ebx
0x1800faa06  mov     r9d, 149h
0x1800faa0c  jmp     short loc_1800FAA46
0x1800faa0e  cmp     [rsp+0A8h+NumberOfBytesWritten], ebp
0x1800faa12  jz      short loc_1800FAA52
0x1800faa14  mov     ebx, 8000FFFFh
0x1800faa19  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800faa20  jz      short loc_1800FAA52
0x1800faa22  mov     r9d, 14Ch
0x1800faa28  jmp     short loc_1800FAA3E
0x1800faa2a  mov     ebx, 8000FFFFh
0x1800faa2f  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800faa36  jz      short loc_1800FAA52
0x1800faa38  mov     r9d, 140h
0x1800faa3e  mov     dword ptr [rsp+0A8h+lpOverlapped], 8000FFFFh
0x1800faa46  lea     r8, aWriteheadertof; "WriteHeaderToFile"
0x1800faa4d  call    McTemplateU0sqq_EventWriteTransfer
0x1800faa52  mov     rcx, rdi; pv
0x1800faa55  call    cs:__imp_CoTaskMemFree
0x1800faa5c  nop     dword ptr [rax+rax+00h]
0x1800faa61  nop
0x1800faa62  lea     rcx, [rsp+0A8h+var_70]
0x1800faa67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800faa6c  mov     eax, ebx
0x1800faa6e  mov     rcx, [rsp+0A8h+var_38]
0x1800faa73  xor     rcx, rsp; StackCookie
0x1800faa76  call    __security_check_cookie
0x1800faa7b  lea     r11, [rsp+0A8h+var_28]
0x1800faa83  mov     rbx, [r11+40h]
0x1800faa87  mov     rbp, [r11+48h]
0x1800faa8b  mov     rsp, r11
0x1800faa8e  pop     r15
0x1800faa90  pop     r14
0x1800faa92  pop     r12
0x1800faa94  pop     rdi
0x1800faa95  pop     rsi
0x1800faa96  retn
```
