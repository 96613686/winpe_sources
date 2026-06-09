# CMetadataIPTCReaderWriter::SniffAndConvertToWideString(tagPROPVARIANT *)

- ea: `0x1800aec68`
- end: `0x1800aecf1`
- name: `?SniffAndConvertToWideString@CMetadataIPTCReaderWriter@@AEAAJPEAUtagPROPVARIANT@@@Z`
- size: `137`
- prototype: `int(CMetadataIPTCReaderWriter *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023648`

## callees

- `0x180055704`
- `0x1800aec68`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aec93`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aec93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aeca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aeca4`

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
0x1800aec68  mov     rax, rsp
0x1800aec6b  mov     [rax+10h], rbx
0x1800aec6f  mov     [rax+18h], rsi
0x1800aec73  mov     [rax+8], rcx
0x1800aec77  push    rdi
0x1800aec78  sub     rsp, 20h
0x1800aec7c  mov     rcx, [rdx+8]; lpMultiByteStr
0x1800aec80  xor     edi, edi
0x1800aec82  xor     ebx, ebx
0x1800aec84  mov     [rax+8], rdi
0x1800aec88  mov     rsi, rdx
0x1800aec8b  test    rcx, rcx
0x1800aec8e  jnz     short loc_1800AECBC
0x1800aec90  mov     rcx, rsi; pvar
0x1800aec93  call    cs:__imp_PropVariantClear
0x1800aec99  xor     ecx, ecx; pv
0x1800aec9b  mov     word ptr [rsi], 1Fh
0x1800aeca0  mov     [rsi+8], rdi
0x1800aeca4  call    cs:__imp_CoTaskMemFree
0x1800aecaa  mov     rsi, [rsp+28h+arg_10]
0x1800aecaf  mov     eax, ebx
0x1800aecb1  mov     rbx, [rsp+28h+arg_8]
0x1800aecb6  add     rsp, 20h
0x1800aecba  pop     rdi
0x1800aecbb  retn
0x1800aecbc  lea     r8, [rsp+28h+arg_0]; unsigned __int16 **
0x1800aecc1  xor     edx, edx; int *
0x1800aecc3  call    ?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z; SniffAndConvertToWideString(char const *,int *,ushort * *)
0x1800aecc8  mov     ebx, eax
0x1800aecca  test    eax, eax
0x1800aeccc  js      short loc_1800AECD5
0x1800aecce  mov     rdi, [rsp+28h+arg_0]
0x1800aecd3  jmp     short loc_1800AEC90
0x1800aecd5  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800aecdb  jz      short loc_1800AECE6
0x1800aecdd  mov     ecx, eax; int
0x1800aecdf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800aece4  jmp     short loc_1800AECEA
0x1800aece6  test    eax, eax
0x1800aece8  jns     short loc_1800AECCE
0x1800aecea  mov     rcx, [rsp+28h+arg_0]
0x1800aecef  jmp     short loc_1800AECA4
```
