# SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)

- ea: `0x18002ee18`
- end: `0x18002ee99`
- name: `?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z`
- size: `129`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `21`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002b110`
- `0x18003c43c`
- `0x18003c5c4`
- `0x180040800`
- `0x180080878`
- `0x1800898d0`
- `0x18008ac00`
- `0x18008cc00`
- `0x18008e1d0`
- `0x18008f150`
- `0x180096fb0`
- `0x180097e90`
- `0x180097f90`
- `0x18009ba98`
- `0x18009c080`
- `0x1800b3ca4`
- `0x1800b4114`
- `0x1800cabc0`
- `0x1800caca0`
- `0x1800caf00`
- `0x1800cb520`

## callees

- `0x18001dfe8`
- `0x180026670`
- `0x18002ee18`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ee34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ee81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ee34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ee81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ee59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ee59`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::GetResourceStringById(
        SystemSettings::DataModel *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HSTRING *v4; // r8
  int ResourceStringById; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r9
  HSTRING string; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)a2 = 0;
  WindowsDeleteString(0);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(this, &string, v4);
  if ( ResourceStringById >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v9 = -1;
    do
      ++v9;
    while ( StringRawBuffer[v9] );
    ResourceStringById = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, StringRawBuffer, v9);
  }
  WindowsDeleteString(string);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x18002ee18  mov     [rsp+arg_0], rbx
0x18002ee1d  mov     [rsp+arg_10], rsi
0x18002ee22  push    rdi
0x18002ee23  sub     rsp, 30h
0x18002ee27  mov     rdi, rdx
0x18002ee2a  mov     rbx, rcx
0x18002ee2d  xor     esi, esi
0x18002ee2f  mov     [rdx], rsi
0x18002ee32  xor     ecx, ecx; string
0x18002ee34  call    cs:__imp_WindowsDeleteString
0x18002ee3a  mov     [rsp+38h+string], rsi
0x18002ee3f  lea     rdx, [rsp+38h+string]; HSTRING *
0x18002ee44  mov     rcx, rbx; this
0x18002ee47  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18002ee4c  mov     ebx, eax
0x18002ee4e  test    eax, eax
0x18002ee50  js      short loc_18002EE7C
0x18002ee52  xor     edx, edx; length
0x18002ee54  mov     rcx, [rsp+38h+string]; string
0x18002ee59  call    cs:__imp_WindowsGetStringRawBuffer
0x18002ee5f  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002ee63  inc     r9
0x18002ee66  cmp     [rax+r9*2], si
0x18002ee6b  jnz     short loc_18002EE63
0x18002ee6d  mov     [rsp+38h+var_10], rdi
0x18002ee72  mov     r8, rax
0x18002ee75  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002ee7a  mov     ebx, eax
0x18002ee7c  mov     rcx, [rsp+38h+string]; string
0x18002ee81  call    cs:__imp_WindowsDeleteString
0x18002ee87  mov     eax, ebx
0x18002ee89  mov     rbx, [rsp+38h+arg_0]
0x18002ee8e  mov     rsi, [rsp+38h+arg_10]
0x18002ee93  add     rsp, 30h
0x18002ee97  pop     rdi
0x18002ee98  retn
```
