# CMetadataIPTCReaderWriter::SniffAndConvertToWideString(tagPROPVARIANT *)

- ea: `0x18004ff44`
- end: `0x18004ffda`
- name: `?SniffAndConvertToWideString@CMetadataIPTCReaderWriter@@AEAAJPEAUtagPROPVARIANT@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(CMetadataIPTCReaderWriter *this, PROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f390`

## callees

- `0x18004a994`
- `0x18004ff44`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ff6f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ff6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ff86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ff86`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::SniffAndConvertToWideString(
        CMetadataIPTCReaderWriter *this,
        PROPVARIANT *a2)
{
  const CHAR *v2; // rcx
  unsigned __int16 *v3; // rdi
  unsigned int v4; // ebx
  unsigned __int16 *v6; // rcx
  int v8; // eax
  unsigned __int16 *v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = (unsigned __int16 *)this;
  v2 = (const CHAR *)a2[1];
  v3 = 0;
  v4 = 0;
  v9 = 0;
  if ( !v2 )
    goto LABEL_2;
  v8 = SniffAndConvertToWideString(v2, 0, &v9);
  v4 = v8;
  if ( v8 >= 0 )
  {
    v3 = v9;
LABEL_2:
    PropVariantClear(a2);
    v6 = 0;
    *(_WORD *)a2 = 31;
    a2[1] = v3;
    goto LABEL_3;
  }
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(v8);
  v6 = v9;
LABEL_3:
  CoTaskMemFree(v6);
  return v4;
}

```

## disassembly

```asm
0x18004ff44  mov     rax, rsp
0x18004ff47  mov     [rax+10h], rbx
0x18004ff4b  mov     [rax+18h], rsi
0x18004ff4f  mov     [rax+8], rcx
0x18004ff53  push    rdi
0x18004ff54  sub     rsp, 20h
0x18004ff58  mov     rcx, [rdx+8]; lpMultiByteStr
0x18004ff5c  xor     edi, edi
0x18004ff5e  xor     ebx, ebx
0x18004ff60  mov     [rax+8], rdi
0x18004ff64  mov     rsi, rdx
0x18004ff67  test    rcx, rcx
0x18004ff6a  jnz     short loc_18004FFA5
0x18004ff6c  mov     rcx, rsi; pvar
0x18004ff6f  call    cs:__imp_PropVariantClear
0x18004ff76  nop     dword ptr [rax+rax+00h]
0x18004ff7b  xor     ecx, ecx; pv
0x18004ff7d  mov     word ptr [rsi], 1Fh
0x18004ff82  mov     [rsi+8], rdi
0x18004ff86  call    cs:__imp_CoTaskMemFree
0x18004ff8d  nop     dword ptr [rax+rax+00h]
0x18004ff92  mov     rsi, [rsp+28h+arg_10]
0x18004ff97  mov     eax, ebx
0x18004ff99  mov     rbx, [rsp+28h+arg_8]
0x18004ff9e  add     rsp, 20h
0x18004ffa2  pop     rdi
0x18004ffa3  retn
0x18004ffa5  lea     r8, [rsp+28h+arg_0]; unsigned __int16 **
0x18004ffaa  xor     edx, edx; int *
0x18004ffac  call    ?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z; SniffAndConvertToWideString(char const *,int *,ushort * *)
0x18004ffb1  mov     ebx, eax
0x18004ffb3  test    eax, eax
0x18004ffb5  js      short loc_18004FFBE
0x18004ffb7  mov     rdi, [rsp+28h+arg_0]
0x18004ffbc  jmp     short loc_18004FF6C
0x18004ffbe  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18004ffc4  jz      short loc_18004FFCF
0x18004ffc6  mov     ecx, eax; int
0x18004ffc8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004ffcd  jmp     short loc_18004FFD3
0x18004ffcf  test    eax, eax
0x18004ffd1  jns     short loc_18004FFB7
0x18004ffd3  mov     rcx, [rsp+28h+arg_0]
0x18004ffd8  jmp     short loc_18004FF86
```
