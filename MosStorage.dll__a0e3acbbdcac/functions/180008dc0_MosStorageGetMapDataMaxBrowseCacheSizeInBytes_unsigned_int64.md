# MosStorageGetMapDataMaxBrowseCacheSizeInBytes(unsigned __int64 *)

- ea: `0x180008dc0`
- end: `0x180008e63`
- name: `?MosStorageGetMapDataMaxBrowseCacheSizeInBytes@@YAJPEA_K@Z`
- size: `163`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009cc0`

## callees

- `0x180008dc0`
- `0x18000d8b8`
- `0x180010010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008dfb`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008dfb`

## string_xrefs

- `0x180008df2`: `MosStorageGetMapDataMaxBrowseCacheSizeInBytes`

## pseudocode

```c
__int64 __fastcall MosStorageGetMapDataMaxBrowseCacheSizeInBytes(unsigned __int64 *a1)
{
  int LocaleMapConfiguration; // eax
  int v3; // r8d
  unsigned int v4; // ebx
  struct ILocaleMapConfiguration *v5; // rcx
  struct ILocaleMapConfiguration *v7; // [rsp+38h] [rbp+10h] BYREF
  unsigned __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 0;
  LocaleMapConfiguration = MapPlatformConfig::GetLocaleMapConfiguration(&v7);
  if ( LocaleMapConfiguration < 0 )
  {
    v3 = 1020;
LABEL_3:
    v4 = ZTraceReportOriginationNoThis(LocaleMapConfiguration, "MosStorageGetMapDataMaxBrowseCacheSizeInBytes", v3);
    goto LABEL_7;
  }
  LocaleMapConfiguration = (*(__int64 (__fastcall **)(struct ILocaleMapConfiguration *, __int64, unsigned __int64 *))(*(_QWORD *)v7 + 56LL))(
                             v7,
                             259,
                             &v8);
  if ( LocaleMapConfiguration < 0 )
  {
    v3 = 1021;
    goto LABEL_3;
  }
  v4 = 0;
  *a1 = v8;
LABEL_7:
  v5 = v7;
  if ( v7 )
  {
    v7 = 0;
    (*(void (__fastcall **)(struct ILocaleMapConfiguration *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180008dc0  mov     rax, rsp
0x180008dc3  mov     [rax+8], rbx
0x180008dc7  push    rdi
0x180008dc8  sub     rsp, 20h
0x180008dcc  mov     rdi, rcx
0x180008dcf  mov     qword ptr [rax+10h], 0
0x180008dd7  mov     qword ptr [rax+18h], 0
0x180008ddf  lea     rcx, [rax+10h]; struct ILocaleMapConfiguration **
0x180008de3  call    ?GetLocaleMapConfiguration@MapPlatformConfig@@SAJPEAPEAUILocaleMapConfiguration@@@Z; MapPlatformConfig::GetLocaleMapConfiguration(ILocaleMapConfiguration * *)
0x180008de8  test    eax, eax
0x180008dea  jns     short loc_180008E05
0x180008dec  mov     r8d, 3FCh
0x180008df2  lea     rdx, aMosstoragegetm_2; "MosStorageGetMapDataMaxBrowseCacheSizeI"...
0x180008df9  mov     ecx, eax
0x180008dfb  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008e01  mov     ebx, eax
0x180008e03  jmp     short loc_180008E36
0x180008e05  mov     rcx, [rsp+28h+arg_8]
0x180008e0a  mov     rax, [rcx]
0x180008e0d  lea     r8, [rsp+28h+arg_10]
0x180008e12  mov     edx, 103h
0x180008e17  mov     rax, [rax+38h]
0x180008e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e20  test    eax, eax
0x180008e22  jns     short loc_180008E2C
0x180008e24  mov     r8d, 3FDh
0x180008e2a  jmp     short loc_180008DF2
0x180008e2c  xor     ebx, ebx
0x180008e2e  mov     rax, [rsp+28h+arg_10]
0x180008e33  mov     [rdi], rax
0x180008e36  mov     rcx, [rsp+28h+arg_8]
0x180008e3b  test    rcx, rcx
0x180008e3e  jz      short loc_180008E56
0x180008e40  mov     [rsp+28h+arg_8], 0
0x180008e49  mov     rax, [rcx]
0x180008e4c  mov     rax, [rax+10h]
0x180008e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e55  nop
0x180008e56  mov     eax, ebx
0x180008e58  mov     rbx, [rsp+28h+arg_0]
0x180008e5d  add     rsp, 20h
0x180008e61  pop     rdi
0x180008e62  retn
```
