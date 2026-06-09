# SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)

- ea: `0x1800284f8`
- end: `0x180028579`
- name: `?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z`
- size: `129`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001b9c0`
- `0x18001ba80`
- `0x180027350`
- `0x180027b20`
- `0x18002faf0`

## callees

- `0x1800146a8`
- `0x18001cee0`
- `0x1800284f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028561`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028561`

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
0x1800284f8  mov     [rsp+arg_0], rbx
0x1800284fd  mov     [rsp+arg_10], rsi
0x180028502  push    rdi
0x180028503  sub     rsp, 30h
0x180028507  mov     rdi, rdx
0x18002850a  mov     rbx, rcx
0x18002850d  xor     esi, esi
0x18002850f  mov     [rdx], rsi
0x180028512  xor     ecx, ecx; string
0x180028514  call    cs:__imp_WindowsDeleteString
0x18002851a  mov     [rsp+38h+string], rsi
0x18002851f  lea     rdx, [rsp+38h+string]; HSTRING *
0x180028524  mov     rcx, rbx; this
0x180028527  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18002852c  mov     ebx, eax
0x18002852e  test    eax, eax
0x180028530  js      short loc_18002855C
0x180028532  xor     edx, edx; length
0x180028534  mov     rcx, [rsp+38h+string]; string
0x180028539  call    cs:__imp_WindowsGetStringRawBuffer
0x18002853f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180028543  inc     r9
0x180028546  cmp     [rax+r9*2], si
0x18002854b  jnz     short loc_180028543
0x18002854d  mov     [rsp+38h+var_10], rdi
0x180028552  mov     r8, rax
0x180028555  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002855a  mov     ebx, eax
0x18002855c  mov     rcx, [rsp+38h+string]; string
0x180028561  call    cs:__imp_WindowsDeleteString
0x180028567  mov     eax, ebx
0x180028569  mov     rbx, [rsp+38h+arg_0]
0x18002856e  mov     rsi, [rsp+38h+arg_10]
0x180028573  add     rsp, 30h
0x180028577  pop     rdi
0x180028578  retn
```
