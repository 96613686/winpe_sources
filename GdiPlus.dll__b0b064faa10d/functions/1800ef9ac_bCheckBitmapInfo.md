# bCheckBitmapInfo

- ea: `0x1800ef9ac`
- end: `0x1800efac5`
- name: `bCheckBitmapInfo`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800ef8c0`

## callees

- `0x1800ef9ac`
- `0x1800efacc`
- `0x1800fe680`
- `0x18013ee60`

## import_xrefs

- `ntdll!RtlLogUnexpectedCodepath` at `0x1800efa92`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800efa92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800efa5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800efab5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800efa5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800efab5`
- `GDI32!IsValidEnhMetaRecordOffExt` at `0x1800ef9e6`
- `GDI32!IsValidEnhMetaRecordOffExt` at `0x1800efa70`
- `GDI32!IsValidEnhMetaRecordOffExt` at `0x1800ef9e6`
- `GDI32!IsValidEnhMetaRecordOffExt` at `0x1800efa70`

## pseudocode

```c
__int64 __fastcall bCheckBitmapInfo(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  HLOCAL v10; // rcx
  HLOCAL v12; // rbx
  __int64 v13; // r8
  HLOCAL hMem; // [rsp+30h] [rbp-38h] BYREF
  char v15; // [rsp+38h] [rbp-30h]
  int v16; // [rsp+40h] [rbp-28h] BYREF
  __int64 v17; // [rsp+44h] [rbp-24h]

  hMem = 0;
  v15 = 0;
  if ( !(unsigned int)((__int64 (*)(void))IsValidEnhMetaRecordOffExt)() )
    return 0;
  if ( !(unsigned int)bCheckBitmapInfoHeader(a2, a3, a4, a5, &hMem) )
  {
    v10 = hMem;
    if ( !hMem || !v15 )
      return 0;
    goto LABEL_11;
  }
  v12 = hMem;
  if ( *(_DWORD *)hMem == 124 && *((_DWORD *)hMem + 14) == 1296188740 )
  {
    v13 = a3 + *((_DWORD *)hMem + 28);
    if ( (unsigned int)v13 < a3 )
    {
LABEL_9:
      if ( !v15 )
        return 0;
      v10 = v12;
LABEL_11:
      LocalFree(v10);
      return 0;
    }
    if ( !(unsigned int)IsValidEnhMetaRecordOffExt(a1, a2, v13, *((unsigned int *)hMem + 29)) )
    {
      if ( !*((_DWORD *)v12 + 28) )
      {
        v16 = 60430534;
        v17 = 2;
        RtlLogUnexpectedCodepath(&v16);
      }
      goto LABEL_9;
    }
  }
  BitmapInfoPtr::operator=(a6, &hMem);
  if ( hMem && v15 )
    LocalFree(hMem);
  return 1;
}

```

## disassembly

```asm
0x1800ef9ac  push    rbp
0x1800ef9ae  push    rbx
0x1800ef9af  push    rsi
0x1800ef9b0  push    rdi
0x1800ef9b1  push    r14
0x1800ef9b3  push    r15
0x1800ef9b5  mov     rbp, rsp
0x1800ef9b8  sub     rsp, 68h
0x1800ef9bc  mov     rax, cs:__security_cookie
0x1800ef9c3  xor     rax, rsp
0x1800ef9c6  mov     [rbp+var_18], rax
0x1800ef9ca  mov     r14, [rbp+arg_28]
0x1800ef9ce  mov     ebx, r9d
0x1800ef9d1  mov     edi, r8d
0x1800ef9d4  mov     [rbp+hMem], 0
0x1800ef9dc  mov     rsi, rdx
0x1800ef9df  mov     [rbp+var_30], 0
0x1800ef9e3  mov     r15, rcx
0x1800ef9e6  call    cs:__imp_IsValidEnhMetaRecordOffExt
0x1800ef9ec  test    eax, eax
0x1800ef9ee  jz      short loc_1800EFA1C
0x1800ef9f0  mov     r9d, [rbp+arg_20]
0x1800ef9f4  lea     rax, [rbp+hMem]
0x1800ef9f8  mov     r8d, ebx
0x1800ef9fb  mov     [rsp+68h+var_48], rax
0x1800efa00  mov     edx, edi
0x1800efa02  mov     rcx, rsi
0x1800efa05  call    bCheckBitmapInfoHeader
0x1800efa0a  test    eax, eax
0x1800efa0c  jnz     short loc_1800EFA37
0x1800efa0e  mov     rcx, [rbp+hMem]
0x1800efa12  test    rcx, rcx
0x1800efa15  jz      short loc_1800EFA1C
0x1800efa17  cmp     [rbp+var_30], al
0x1800efa1a  jnz     short loc_1800EFA5E
0x1800efa1c  xor     eax, eax
0x1800efa1e  mov     rcx, [rbp+var_18]
0x1800efa22  xor     rcx, rsp; StackCookie
0x1800efa25  call    __security_check_cookie
0x1800efa2a  add     rsp, 68h
0x1800efa2e  pop     r15
0x1800efa30  pop     r14
0x1800efa32  pop     rdi
0x1800efa33  pop     rsi
0x1800efa34  pop     rbx
0x1800efa35  pop     rbp
0x1800efa36  retn
0x1800efa37  mov     rbx, [rbp+hMem]
0x1800efa3b  cmp     dword ptr [rbx], 7Ch ; '|'
0x1800efa3e  jnz     short loc_1800EFA9A
0x1800efa40  cmp     dword ptr [rbx+38h], 4D424544h
0x1800efa47  jnz     short loc_1800EFA9A
0x1800efa49  mov     r8d, [rbx+70h]
0x1800efa4d  add     r8d, edi
0x1800efa50  cmp     r8d, edi
0x1800efa53  jnb     short loc_1800EFA66
0x1800efa55  cmp     [rbp+var_30], 0
0x1800efa59  jz      short loc_1800EFA1C
0x1800efa5b  mov     rcx, rbx; hMem
0x1800efa5e  call    cs:__imp_LocalFree
0x1800efa64  jmp     short loc_1800EFA1C
0x1800efa66  mov     r9d, [rbx+74h]
0x1800efa6a  mov     rdx, rsi
0x1800efa6d  mov     rcx, r15
0x1800efa70  call    cs:__imp_IsValidEnhMetaRecordOffExt
0x1800efa76  test    eax, eax
0x1800efa78  jnz     short loc_1800EFA9A
0x1800efa7a  cmp     [rbx+70h], eax
0x1800efa7d  jnz     short loc_1800EFA55
0x1800efa7f  lea     rcx, [rbp+var_28]
0x1800efa83  mov     [rbp+var_28], 39A18C6h
0x1800efa8a  mov     [rbp+var_24], 2
0x1800efa92  call    cs:__imp_RtlLogUnexpectedCodepath
0x1800efa98  jmp     short loc_1800EFA55
0x1800efa9a  lea     rdx, [rbp+hMem]
0x1800efa9e  mov     rcx, r14
0x1800efaa1  call    ??4BitmapInfoPtr@@QEAAAEAV0@AEAV0@@Z; BitmapInfoPtr::operator=(BitmapInfoPtr &)
0x1800efaa6  mov     rcx, [rbp+hMem]; hMem
0x1800efaaa  test    rcx, rcx
0x1800efaad  jz      short loc_1800EFABB
0x1800efaaf  cmp     [rbp+var_30], 0
0x1800efab3  jz      short loc_1800EFABB
0x1800efab5  call    cs:__imp_LocalFree
0x1800efabb  mov     eax, 1
0x1800efac0  jmp     loc_1800EFA1E
```
