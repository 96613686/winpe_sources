# ConvertToWideString(char const *,ushort * *)

- ea: `0x1800cb038`
- end: `0x1800cb13d`
- name: `?ConvertToWideString@@YAJPEBDPEAPEAG@Z`
- size: `261`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800caea4`

## callees

- `0x18001dd10`
- `0x180055830`
- `0x1800bb784`
- `0x1800cb038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb0c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cb0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb0ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb125`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cb07b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cb0e5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cb07b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cb0e5`

## pseudocode

```c
__int64 __fastcall ConvertToWideString(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  int v4; // ebx
  int v5; // eax
  int cchWideChar; // ebp
  signed int LastError; // eax
  ULONGLONG pullResult; // [rsp+60h] [rbp+8h] BYREF

  *a2 = 0;
  if ( lpMultiByteStr )
  {
    v4 = -2147467259;
    v5 = MultiByteToWideChar(0, 0, lpMultiByteStr, -1, 0, 0);
    cchWideChar = v5;
    if ( v5 )
    {
      pullResult = 0;
      v4 = ULongLongMult(v5, 2u, &pullResult);
      if ( v4 >= 0 )
      {
        v4 = CoTaskMemAllocWithInit(pullResult, (void **)a2);
        if ( v4 >= 0 )
        {
          SetLastError(0);
          v4 = 0;
          if ( !MultiByteToWideChar(0, 0, lpMultiByteStr, -1, *a2, cchWideChar) )
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            if ( v4 >= 0 )
              v4 = -2003292268;
            if ( (_DWORD)g_doStackCaptures )
              DoStackCapture(v4);
          }
          if ( v4 < 0 )
          {
            CoTaskMemFree(*a2);
            *a2 = 0;
          }
        }
      }
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800cb038  push    rbx
0x1800cb03a  push    rbp
0x1800cb03b  push    rsi
0x1800cb03c  push    rdi
0x1800cb03d  sub     rsp, 38h
0x1800cb041  mov     qword ptr [rdx], 0
0x1800cb048  mov     rdi, rdx
0x1800cb04b  mov     rsi, rcx
0x1800cb04e  test    rcx, rcx
0x1800cb051  jnz     short loc_1800CB05A
0x1800cb053  xor     ebx, ebx
0x1800cb055  jmp     loc_1800CB132
0x1800cb05a  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x1800cb062  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800cb066  mov     r8, rsi; lpMultiByteStr
0x1800cb069  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x1800cb072  xor     edx, edx; dwFlags
0x1800cb074  xor     ecx, ecx; CodePage
0x1800cb076  mov     ebx, 80004005h
0x1800cb07b  call    cs:__imp_MultiByteToWideChar
0x1800cb081  movsxd  rbp, eax
0x1800cb084  test    eax, eax
0x1800cb086  jz      loc_1800CB132
0x1800cb08c  mov     rcx, rbp; ullMultiplicand
0x1800cb08f  mov     [rsp+58h+pullResult], 0
0x1800cb098  lea     r8, [rsp+58h+pullResult]; pullResult
0x1800cb09d  mov     edx, 2; ullMultiplier
0x1800cb0a2  call    ULongLongMult
0x1800cb0a7  mov     ebx, eax
0x1800cb0a9  test    eax, eax
0x1800cb0ab  js      loc_1800CB132
0x1800cb0b1  mov     rcx, [rsp+58h+pullResult]; Size
0x1800cb0b6  mov     rdx, rdi; void **
0x1800cb0b9  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x1800cb0be  mov     ebx, eax
0x1800cb0c0  test    eax, eax
0x1800cb0c2  js      short loc_1800CB132
0x1800cb0c4  xor     ecx, ecx; dwErrCode
0x1800cb0c6  call    cs:__imp_SetLastError
0x1800cb0cc  mov     rax, [rdi]
0x1800cb0cf  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800cb0d3  mov     [rsp+58h+cchWideChar], ebp; cchWideChar
0x1800cb0d7  mov     r8, rsi; lpMultiByteStr
0x1800cb0da  xor     edx, edx; dwFlags
0x1800cb0dc  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x1800cb0e1  xor     ecx, ecx; CodePage
0x1800cb0e3  xor     ebx, ebx
0x1800cb0e5  call    cs:__imp_MultiByteToWideChar
0x1800cb0eb  test    eax, eax
0x1800cb0ed  jnz     short loc_1800CB11E
0x1800cb0ef  call    cs:__imp_GetLastError
0x1800cb0f5  mov     ebx, eax
0x1800cb0f7  test    eax, eax
0x1800cb0f9  jle     short loc_1800CB104
0x1800cb0fb  movzx   ebx, ax
0x1800cb0fe  or      ebx, 80070000h
0x1800cb104  test    ebx, ebx
0x1800cb106  mov     eax, 88982F94h
0x1800cb10b  cmovns  ebx, eax
0x1800cb10e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800cb115  jz      short loc_1800CB11E
0x1800cb117  mov     ecx, ebx; int
0x1800cb119  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cb11e  test    ebx, ebx
0x1800cb120  jns     short loc_1800CB132
0x1800cb122  mov     rcx, [rdi]; pv
0x1800cb125  call    cs:__imp_CoTaskMemFree
0x1800cb12b  mov     qword ptr [rdi], 0
0x1800cb132  mov     eax, ebx
0x1800cb134  add     rsp, 38h
0x1800cb138  pop     rdi
0x1800cb139  pop     rsi
0x1800cb13a  pop     rbp
0x1800cb13b  pop     rbx
0x1800cb13c  retn
```
