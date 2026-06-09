# SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)

- ea: `0x180026380`
- end: `0x180026414`
- name: `?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z`
- size: `148`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180025cf0`
- `0x180025e30`

## callees

- `0x1800136e8`
- `0x1800224e8`
- `0x180026380`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800263c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800263c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002639c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800263f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002639c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800263f5`

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
    ResourceStringById = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, StringRawBuffer);
  }
  WindowsDeleteString(string);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x180026380  mov     [rsp+arg_0], rbx
0x180026385  mov     [rsp+arg_10], rsi
0x18002638a  push    rdi
0x18002638b  sub     rsp, 30h
0x18002638f  mov     rdi, rdx
0x180026392  mov     rbx, rcx
0x180026395  xor     esi, esi
0x180026397  mov     [rdx], rsi
0x18002639a  xor     ecx, ecx; string
0x18002639c  call    cs:__imp_WindowsDeleteString
0x1800263a3  nop     dword ptr [rax+rax+00h]
0x1800263a8  mov     [rsp+38h+string], rsi
0x1800263ad  lea     rdx, [rsp+38h+string]; HSTRING *
0x1800263b2  mov     rcx, rbx; this
0x1800263b5  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800263ba  mov     ebx, eax
0x1800263bc  test    eax, eax
0x1800263be  js      short loc_1800263F0
0x1800263c0  xor     edx, edx; length
0x1800263c2  mov     rcx, [rsp+38h+string]; string
0x1800263c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800263ce  nop     dword ptr [rax+rax+00h]
0x1800263d3  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800263d7  inc     r9
0x1800263da  cmp     [rax+r9*2], si
0x1800263df  jnz     short loc_1800263D7
0x1800263e1  mov     [rsp+38h+var_10], rdi
0x1800263e6  mov     r8, rax
0x1800263e9  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800263ee  mov     ebx, eax
0x1800263f0  mov     rcx, [rsp+38h+string]; string
0x1800263f5  call    cs:__imp_WindowsDeleteString
0x1800263fc  nop     dword ptr [rax+rax+00h]
0x180026401  mov     eax, ebx
0x180026403  mov     rbx, [rsp+38h+arg_0]
0x180026408  mov     rsi, [rsp+38h+arg_10]
0x18002640d  add     rsp, 30h
0x180026411  pop     rdi
0x180026412  retn
```
