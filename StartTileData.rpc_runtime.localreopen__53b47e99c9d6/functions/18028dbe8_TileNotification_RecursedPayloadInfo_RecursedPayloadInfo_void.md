# TileNotification::RecursedPayloadInfo::~RecursedPayloadInfo(void)

- ea: `0x18028dbe8`
- end: `0x18028dcd1`
- name: `??1RecursedPayloadInfo@TileNotification@@QEAA@XZ`
- size: `233`
- prototype: `void __fastcall(TileNotification::RecursedPayloadInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18028df7c`

## callees

- `0x18028db1c`
- `0x18028dbe8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dcb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dc9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028dcb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18028dc14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18028dc44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18028dc14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18028dc44`

## pseudocode

```c
void __fastcall TileNotification::RecursedPayloadInfo::~RecursedPayloadInfo(
        TileNotification::RecursedPayloadInfo *this)
{
  void *v2; // rcx
  void *v3; // rcx

  CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>((char *)this + 192);
  v2 = (void *)*((_QWORD *)this + 20);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 20) = 0;
  }
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 23) = 0;
  CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>((char *)this + 128);
  v3 = (void *)*((_QWORD *)this + 12);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 12) = 0;
  }
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 15) = 0;
  CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>((char *)this + 64);
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
  WindowsDeleteString(*((HSTRING *)this + 3));
  *((_QWORD *)this + 3) = 0;
  WindowsDeleteString(*((HSTRING *)this + 2));
  *((_QWORD *)this + 2) = 0;
  WindowsDeleteString(*((HSTRING *)this + 1));
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18028dbe8  mov     [rsp+arg_0], rbx
0x18028dbed  mov     [rsp+arg_8], rsi
0x18028dbf2  push    rdi
0x18028dbf3  sub     rsp, 20h
0x18028dbf7  mov     rbx, rcx
0x18028dbfa  add     rcx, 0C0h
0x18028dc01  call    ??1?$CSimplePointerArray@GV?$CTPolicyCoTaskMem@G@@VCSimpleArrayCaseInsensitiveOrdinalStringCompareHelper@@@@QEAA@XZ; CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(void)
0x18028dc06  mov     rcx, [rbx+0A0h]; pv
0x18028dc0d  xor     esi, esi
0x18028dc0f  test    rcx, rcx
0x18028dc12  jz      short loc_18028DC21
0x18028dc14  call    cs:__imp_CoTaskMemFree
0x18028dc1a  mov     [rbx+0A0h], rsi
0x18028dc21  lea     rcx, [rbx+80h]
0x18028dc28  mov     [rbx+0A8h], rsi
0x18028dc2f  mov     [rbx+0B8h], rsi
0x18028dc36  call    ??1?$CSimplePointerArray@GV?$CTPolicyCoTaskMem@G@@VCSimpleArrayCaseInsensitiveOrdinalStringCompareHelper@@@@QEAA@XZ; CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(void)
0x18028dc3b  mov     rcx, [rbx+60h]; pv
0x18028dc3f  test    rcx, rcx
0x18028dc42  jz      short loc_18028DC4E
0x18028dc44  call    cs:__imp_CoTaskMemFree
0x18028dc4a  mov     [rbx+60h], rsi
0x18028dc4e  lea     rcx, [rbx+40h]
0x18028dc52  mov     [rbx+68h], rsi
0x18028dc56  mov     [rbx+78h], rsi
0x18028dc5a  call    ??1?$CSimplePointerArray@GV?$CTPolicyCoTaskMem@G@@VCSimpleArrayCaseInsensitiveOrdinalStringCompareHelper@@@@QEAA@XZ; CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(void)
0x18028dc5f  mov     rcx, [rbx+38h]; string
0x18028dc63  call    cs:__imp_WindowsDeleteString
0x18028dc69  mov     [rbx+38h], rsi
0x18028dc6d  mov     rcx, [rbx+30h]; string
0x18028dc71  call    cs:__imp_WindowsDeleteString
0x18028dc77  mov     [rbx+30h], rsi
0x18028dc7b  mov     rcx, [rbx+28h]; string
0x18028dc7f  call    cs:__imp_WindowsDeleteString
0x18028dc85  mov     [rbx+28h], rsi
0x18028dc89  mov     rcx, [rbx+20h]; string
0x18028dc8d  call    cs:__imp_WindowsDeleteString
0x18028dc93  mov     [rbx+20h], rsi
0x18028dc97  mov     rcx, [rbx+18h]; string
0x18028dc9b  call    cs:__imp_WindowsDeleteString
0x18028dca1  mov     [rbx+18h], rsi
0x18028dca5  mov     rcx, [rbx+10h]; string
0x18028dca9  call    cs:__imp_WindowsDeleteString
0x18028dcaf  mov     [rbx+10h], rsi
0x18028dcb3  mov     rcx, [rbx+8]; string
0x18028dcb7  call    cs:__imp_WindowsDeleteString
0x18028dcbd  mov     [rbx+8], rsi
0x18028dcc1  mov     rbx, [rsp+28h+arg_0]
0x18028dcc6  mov     rsi, [rsp+28h+arg_8]
0x18028dccb  add     rsp, 20h
0x18028dccf  pop     rdi
0x18028dcd0  retn
```
