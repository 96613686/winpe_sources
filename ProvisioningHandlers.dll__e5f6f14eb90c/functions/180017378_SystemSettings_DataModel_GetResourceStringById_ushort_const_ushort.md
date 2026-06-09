# SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)

- ea: `0x180017378`
- end: `0x180017412`
- name: `?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z`
- size: `154`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180020d70`

## callees

- `0x18000dd3c`
- `0x180017378`
- `0x180017418`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017396`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800173f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017396`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800173f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800173c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800173c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::GetResourceStringById(
        SystemSettings::DataModel *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HSTRING *v3; // r8
  int ResourceStringById; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r9
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF

  string = (HSTRING)this;
  *(_QWORD *)a2 = 0;
  WindowsDeleteString(0);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                         (SystemSettings::DataModel *)L"SystemSettings_DateTime_TimeDateStatusFormat",
                         &string,
                         v3);
  if ( ResourceStringById >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = -1;
    do
      ++v8;
    while ( StringRawBuffer[v8] );
    ResourceStringById = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, StringRawBuffer);
  }
  WindowsDeleteString(string);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x180017378  mov     [rsp+arg_8], rbx
0x18001737d  mov     [rsp+arg_10], rsi
0x180017382  mov     [rsp+string], rcx
0x180017387  push    rdi
0x180017388  sub     rsp, 30h
0x18001738c  mov     rdi, rdx
0x18001738f  xor     esi, esi
0x180017391  mov     [rdx], rsi
0x180017394  xor     ecx, ecx; string
0x180017396  call    cs:__imp_WindowsDeleteString
0x18001739d  nop     dword ptr [rax+rax+00h]
0x1800173a2  mov     [rsp+38h+string], rsi
0x1800173a7  lea     rdx, [rsp+38h+string]; HSTRING *
0x1800173ac  lea     rcx, aSystemsettings_24; "SystemSettings_DateTime_TimeDateStatusF"...
0x1800173b3  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800173b8  mov     ebx, eax
0x1800173ba  test    eax, eax
0x1800173bc  js      short loc_1800173EE
0x1800173be  xor     edx, edx; length
0x1800173c0  mov     rcx, [rsp+38h+string]; string
0x1800173c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800173cc  nop     dword ptr [rax+rax+00h]
0x1800173d1  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800173d5  inc     r9
0x1800173d8  cmp     [rax+r9*2], si
0x1800173dd  jnz     short loc_1800173D5
0x1800173df  mov     [rsp+38h+var_10], rdi
0x1800173e4  mov     r8, rax
0x1800173e7  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800173ec  mov     ebx, eax
0x1800173ee  mov     rcx, [rsp+38h+string]; string
0x1800173f3  call    cs:__imp_WindowsDeleteString
0x1800173fa  nop     dword ptr [rax+rax+00h]
0x1800173ff  mov     eax, ebx
0x180017401  mov     rbx, [rsp+38h+arg_8]
0x180017406  mov     rsi, [rsp+38h+arg_10]
0x18001740b  add     rsp, 30h
0x18001740f  pop     rdi
0x180017410  retn
```
