# SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)

- ea: `0x18002bad4`
- end: `0x18002bbe9`
- name: `?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ`
- size: `277`
- prototype: `__int64(SystemSettings::DataModel *__hidden this, const unsigned __int16 *, unsigned __int16 **, ...)`
- caller_count: `25`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002e7c0`
- `0x18002fbd0`
- `0x180040440`
- `0x180040800`
- `0x180045ee0`
- `0x180046e7c`
- `0x180054810`
- `0x1800554d0`
- `0x180055de0`
- `0x180055f20`
- `0x1800641c0`
- `0x18007bd14`
- `0x18007e970`
- `0x18007eea0`
- `0x1800818c0`
- `0x180083bf0`
- `0x1800843f0`
- `0x18008ce20`
- `0x18008d710`
- `0x180096fb0`
- `0x18009b9b0`
- `0x1800b3b88`
- `0x1800b4114`
- `0x1800b56fc`
- `0x1800b58ac`

## callees

- `0x18001dfe8`
- `0x180026670`
- `0x18002bad4`
- `0x1800349f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb7e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bb6e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bb6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bb44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bb44`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 SystemSettings::DataModel::FormatResourceMessageArgAlloc(
        SystemSettings::DataModel *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        ...)
{
  HSTRING *v4; // r8
  signed int ResourceStringById; // ebx
  __int64 v6; // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  signed int LastError; // eax
  const WCHAR *v11; // r8
  va_list Arguments; // [rsp+40h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-30h] BYREF
  WCHAR Buffer[4]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v16; // [rsp+58h] [rbp-20h]
  __int64 v17; // [rsp+60h] [rbp-18h]
  unsigned __int16 **v18; // [rsp+B0h] [rbp+38h] BYREF

  v18 = a3;
  *(_QWORD *)Buffer = 0;
  v16 = 0;
  v17 = 0;
  va_copy(Arguments, (va_list)&v18);
  WindowsDeleteString(0);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(this, &string, v4);
  if ( ResourceStringById < 0 )
    goto LABEL_11;
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(Buffer);
  v6 = -1;
  v16 = -1;
  v17 = -1;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( FormatMessageW(0x500u, StringRawBuffer, 0, 0, Buffer, 0, &Arguments) )
  {
    Arguments = 0;
LABEL_7:
    v11 = &word_180106450;
    if ( *(_QWORD *)Buffer )
      v11 = *(const WCHAR **)Buffer;
    do
      ++v6;
    while ( v11[v6] );
    ResourceStringById = _AllocStringWorker<CTCoAllocPolicy>(v9, v8, v11, v6);
    goto LABEL_11;
  }
  LastError = GetLastError();
  ResourceStringById = LastError;
  if ( LastError > 0 )
    ResourceStringById = (unsigned __int16)LastError | 0x80070000;
  Arguments = 0;
  if ( ResourceStringById >= 0 )
    goto LABEL_7;
LABEL_11:
  WindowsDeleteString(string);
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(Buffer);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x18002bad4  mov     [rsp-20h+arg_8], rdx
0x18002bad9  mov     [rsp-20h+arg_10], r8
0x18002bade  mov     [rsp-20h+arg_18], r9
0x18002bae3  push    rbp
0x18002bae4  push    rbx
0x18002bae5  push    rsi
0x18002bae6  push    rdi
0x18002bae7  mov     rbp, rsp
0x18002baea  sub     rsp, 78h
0x18002baee  mov     rbx, rcx
0x18002baf1  xor     esi, esi
0x18002baf3  mov     qword ptr [rbp+Buffer], rsi
0x18002baf7  mov     [rbp+var_20], rsi
0x18002bafb  mov     [rbp+var_18], rsi
0x18002baff  lea     rax, [rbp+arg_10]
0x18002bb03  mov     [rbp+var_38], rax
0x18002bb07  xor     ecx, ecx; string
0x18002bb09  call    cs:__imp_WindowsDeleteString
0x18002bb0f  mov     [rbp+string], rsi
0x18002bb13  lea     rdx, [rbp+string]; HSTRING *
0x18002bb17  mov     rcx, rbx; this
0x18002bb1a  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18002bb1f  mov     ebx, eax
0x18002bb21  test    eax, eax
0x18002bb23  js      loc_18002BBCA
0x18002bb29  lea     rcx, [rbp+Buffer]
0x18002bb2d  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18002bb32  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002bb36  mov     [rbp+var_20], rdi
0x18002bb3a  mov     [rbp+var_18], rdi
0x18002bb3e  xor     edx, edx; length
0x18002bb40  mov     rcx, [rbp+string]; string
0x18002bb44  call    cs:__imp_WindowsGetStringRawBuffer
0x18002bb4a  lea     rcx, [rbp+var_38]
0x18002bb4e  mov     [rsp+78h+Arguments], rcx; Arguments
0x18002bb53  mov     [rsp+78h+nSize], esi; nSize
0x18002bb57  lea     rcx, [rbp+Buffer]
0x18002bb5b  mov     [rsp+78h+lpBuffer], rcx; lpBuffer
0x18002bb60  xor     r9d, r9d; dwLanguageId
0x18002bb63  xor     r8d, r8d; dwMessageId
0x18002bb66  mov     rdx, rax; lpSource
0x18002bb69  mov     ecx, 500h; dwFlags
0x18002bb6e  call    cs:__imp_FormatMessageW
0x18002bb74  test    eax, eax
0x18002bb76  jz      short loc_18002BB7E
0x18002bb78  mov     [rbp+var_38], rsi
0x18002bb7c  jmp     short loc_18002BB9B
0x18002bb7e  call    cs:__imp_GetLastError
0x18002bb84  mov     ebx, eax
0x18002bb86  test    eax, eax
0x18002bb88  jle     short loc_18002BB93
0x18002bb8a  movzx   ebx, ax
0x18002bb8d  or      ebx, 80070000h
0x18002bb93  mov     [rbp+var_38], rsi
0x18002bb97  test    ebx, ebx
0x18002bb99  js      short loc_18002BBCA
0x18002bb9b  mov     rax, qword ptr [rbp+Buffer]
0x18002bb9f  lea     r8, word_180106450
0x18002bba6  test    rax, rax
0x18002bba9  cmovnz  r8, rax
0x18002bbad  mov     rax, [rbp+arg_8]
0x18002bbb1  inc     rdi
0x18002bbb4  cmp     [r8+rdi*2], si
0x18002bbb9  jnz     short loc_18002BBB1
0x18002bbbb  mov     qword ptr [rsp+78h+nSize], rax
0x18002bbc0  mov     r9, rdi
0x18002bbc3  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002bbc8  mov     ebx, eax
0x18002bbca  mov     rcx, [rbp+string]; string
0x18002bbce  call    cs:__imp_WindowsDeleteString
0x18002bbd4  nop
0x18002bbd5  lea     rcx, [rbp+Buffer]
0x18002bbd9  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18002bbde  mov     eax, ebx
0x18002bbe0  add     rsp, 78h
0x18002bbe4  pop     rdi
0x18002bbe5  pop     rsi
0x18002bbe6  pop     rbx
0x18002bbe7  pop     rbp
0x18002bbe8  retn
```
