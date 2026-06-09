# FileReader::Read7BitEncodedInt(int *)

- ea: `0x18000d64c`
- end: `0x18000d6bd`
- name: `?Read7BitEncodedInt@FileReader@@QEAAJPEAH@Z`
- size: `113`
- prototype: `int __fastcall(HANDLE *this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5a4`

## callees

- `0x18000d458`
- `0x18000d64c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d6ad`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d6ad`

## string_xrefs

- `0x18000d69e`: `FileReader::Read7BitEncodedInt`

## pseudocode

```c
int __fastcall FileReader::Read7BitEncodedInt(HANDLE *this, int *a2)
{
  int v2; // edi
  char v4; // bl
  int v6; // eax
  int result; // eax
  char v8; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  v4 = 0;
  v8 = 0;
  while ( 1 )
  {
    v6 = FileReader::ReadBytes<unsigned char>(this, 1u, &v8);
    if ( v6 < 0 )
      break;
    v2 |= (v8 & 0x7F) << v4;
    if ( v8 >= 0 )
    {
      result = 0;
      *a2 = v2;
      return result;
    }
    v4 += 7;
  }
  return ZTraceReportPropagation(v6, "FileReader::Read7BitEncodedInt", 39, this);
}

```

## disassembly

```asm
0x18000d64c  push    rbx
0x18000d64e  push    rsi
0x18000d64f  push    rdi
0x18000d650  push    r14
0x18000d652  sub     rsp, 28h
0x18000d656  xor     edi, edi
0x18000d658  mov     r14, rdx
0x18000d65b  xor     ebx, ebx
0x18000d65d  mov     rsi, rcx
0x18000d660  mov     [rsp+48h+arg_10], bl
0x18000d664  lea     r8, [rsp+48h+arg_10]
0x18000d669  mov     edx, 1
0x18000d66e  mov     rcx, rsi
0x18000d671  call    ??$ReadBytes@E@FileReader@@QEAAJKPEAE@Z; FileReader::ReadBytes<uchar>(ulong,uchar *)
0x18000d676  test    eax, eax
0x18000d678  js      short loc_18000D69B
0x18000d67a  movzx   eax, [rsp+48h+arg_10]
0x18000d67f  mov     ecx, ebx
0x18000d681  and     eax, 7Fh
0x18000d684  shl     eax, cl
0x18000d686  or      edi, eax
0x18000d688  test    [rsp+48h+arg_10], 80h
0x18000d68d  jz      short loc_18000D694
0x18000d68f  add     ebx, 7
0x18000d692  jmp     short loc_18000D664
0x18000d694  xor     eax, eax
0x18000d696  mov     [r14], edi
0x18000d699  jmp     short loc_18000D6B3
0x18000d69b  mov     r9, rsi
0x18000d69e  lea     rdx, aFilereaderRead_0; "FileReader::Read7BitEncodedInt"
0x18000d6a5  mov     r8d, 27h ; '''
0x18000d6ab  mov     ecx, eax
0x18000d6ad  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000d6b3  add     rsp, 28h
0x18000d6b7  pop     r14
0x18000d6b9  pop     rdi
0x18000d6ba  pop     rsi
0x18000d6bb  pop     rbx
0x18000d6bc  retn
```
