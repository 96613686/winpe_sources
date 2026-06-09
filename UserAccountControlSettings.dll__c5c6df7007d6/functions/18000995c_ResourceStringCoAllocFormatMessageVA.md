# ResourceStringCoAllocFormatMessageVA

- ea: `0x18000995c`
- end: `0x180009a40`
- name: `ResourceStringCoAllocFormatMessageVA`
- size: `228`
- prototype: `__int64(HMODULE, __int64, _QWORD *, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009930`

## callees

- `0x180006af0`
- `0x180009800`
- `0x1800098d0`
- `0x18000995c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800099e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800099e4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800099bb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800099bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a2f`

## pseudocode

```c
__int64 ResourceStringCoAllocFormatMessageVA(HMODULE a1, __int64 a2, _QWORD *a3, ...)
{
  int ErrorError; // ebx
  __int64 v5; // rax
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  void *v8; // r11
  int lpBuffer; // [rsp+20h] [rbp-58h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-38h] BYREF
  LPCVOID lpSource; // [rsp+48h] [rbp-30h] BYREF
  va_list Arguments; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  va_list va1; // [rsp+A0h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  Arguments = va_arg(va1, va_list);
  lpSource = 0;
  ErrorError = TResourceStringAllocCopyEx<unsigned short *>(
                 a1,
                 a2,
                 (__int64)a3,
                 Arguments,
                 lpBuffer,
                 (void **)&lpSource);
  if ( ErrorError >= 0 )
  {
    *(_QWORD *)Buffer = 0;
    if ( FormatMessageW(0x500u, lpSource, 0, 0, Buffer, 0, (va_list *)va) )
    {
      ErrorError = -2147024882;
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v5) );
      v6 = (unsigned int)(v5 + 1);
      v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
      if ( v7 )
      {
        ErrorError = StringCchCopyW(v7, (unsigned int)v6, *(const unsigned __int16 **)Buffer);
        if ( ErrorError >= 0 )
        {
          *a3 = v8;
          v8 = 0;
        }
        CoTaskMemFree(v8);
      }
      LocalFree(*(HLOCAL *)Buffer);
    }
    else
    {
      ErrorError = HRESULTFromLastErrorError();
    }
    LocalFree((HLOCAL)lpSource);
  }
  return (unsigned int)ErrorError;
}

```

## disassembly

```asm
0x18000995c  mov     r11, rsp
0x18000995f  mov     [r11+20h], r9
0x180009963  push    rbx
0x180009964  push    rbp
0x180009965  push    rsi
0x180009966  push    rdi
0x180009967  sub     rsp, 58h
0x18000996b  lea     rax, [r11-30h]
0x18000996f  xor     ebp, ebp
0x180009971  mov     [r11-30h], rbp
0x180009975  mov     rsi, r8
0x180009978  mov     [r11-50h], rax
0x18000997c  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180009981  mov     ebx, eax
0x180009983  test    eax, eax
0x180009985  js      loc_180009A35
0x18000998b  mov     rdx, [rsp+78h+lpSource]; lpSource
0x180009990  lea     rax, [rsp+78h+arg_18]
0x180009998  mov     [rsp+78h+Arguments], rax; Arguments
0x18000999d  xor     r9d, r9d; dwLanguageId
0x1800099a0  lea     rax, [rsp+78h+Buffer]
0x1800099a5  mov     [rsp+78h+nSize], ebp; nSize
0x1800099a9  xor     r8d, r8d; dwMessageId
0x1800099ac  mov     [rsp+78h+lpBuffer], rax; lpBuffer
0x1800099b1  mov     ecx, 500h; dwFlags
0x1800099b6  mov     qword ptr [rsp+78h+Buffer], rbp
0x1800099bb  call    cs:__imp_FormatMessageW
0x1800099c1  test    eax, eax
0x1800099c3  jz      short loc_180009A23
0x1800099c5  mov     rcx, qword ptr [rsp+78h+Buffer]
0x1800099ca  mov     ebx, 8007000Eh
0x1800099cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800099d3  inc     rax
0x1800099d6  cmp     [rcx+rax*2], bp
0x1800099da  jnz     short loc_1800099D3
0x1800099dc  inc     eax
0x1800099de  mov     edi, eax
0x1800099e0  lea     rcx, [rax+rax]; cb
0x1800099e4  call    cs:__imp_CoTaskMemAlloc
0x1800099ea  mov     r11, rax
0x1800099ed  test    rax, rax
0x1800099f0  jz      short loc_180009A16
0x1800099f2  mov     r8, qword ptr [rsp+78h+Buffer]; unsigned __int16 *
0x1800099f7  mov     edx, edi; unsigned __int64
0x1800099f9  mov     rcx, rax; unsigned __int16 *
0x1800099fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009a01  mov     ebx, eax
0x180009a03  test    eax, eax
0x180009a05  js      short loc_180009A0D
0x180009a07  mov     [rsi], r11
0x180009a0a  mov     r11, rbp
0x180009a0d  mov     rcx, r11; pv
0x180009a10  call    cs:__imp_CoTaskMemFree
0x180009a16  mov     rcx, qword ptr [rsp+78h+Buffer]; hMem
0x180009a1b  call    cs:__imp_LocalFree
0x180009a21  jmp     short loc_180009A2A
0x180009a23  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180009a28  mov     ebx, eax
0x180009a2a  mov     rcx, [rsp+78h+lpSource]; hMem
0x180009a2f  call    cs:__imp_LocalFree
0x180009a35  mov     eax, ebx
0x180009a37  add     rsp, 58h
0x180009a3b  pop     rdi
0x180009a3c  pop     rsi
0x180009a3d  pop     rbp
0x180009a3e  pop     rbx
0x180009a3f  retn
```
