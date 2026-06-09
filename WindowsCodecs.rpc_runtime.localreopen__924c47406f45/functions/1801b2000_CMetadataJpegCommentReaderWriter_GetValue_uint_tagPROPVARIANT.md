# CMetadataJpegCommentReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x1801b2000`
- end: `0x1801b20b5`
- name: `?GetValue@CMetadataJpegCommentReaderWriter@@EEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `181`
- prototype: `int(CMetadataJpegCommentReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020e14`
- `0x1800bb784`
- `0x1801b2000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b202d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b2070`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b202d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b2070`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b209c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b209c`

## pseudocode

```c
__int64 __fastcall CMetadataJpegCommentReaderWriter::GetValue(
        CMetadataJpegCommentReaderWriter *this,
        int a2,
        PROPVARIANT *a3)
{
  unsigned int v5; // ebx
  char *v6; // rax
  int v7; // eax
  int v8; // ecx
  _BYTE *v9; // rax

  if ( a2 != 1 )
  {
    v5 = -2147024809;
LABEL_11:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_14;
    v8 = v5;
    goto LABEL_13;
  }
  if ( !*((_QWORD *)this + 19) )
  {
    v9 = CoTaskMemAlloc(1u);
    a3[1] = v9;
    if ( v9 )
    {
      v5 = 0;
      *v9 = 0;
      return v5;
    }
    goto LABEL_10;
  }
  v6 = (char *)CoTaskMemAlloc(*((unsigned __int16 *)this + 80));
  a3[1] = v6;
  if ( !v6 )
  {
LABEL_10:
    v5 = -2147024882;
    goto LABEL_11;
  }
  v7 = StringCchCopyA(v6, *((unsigned __int16 *)this + 80), *((const char **)this + 19));
  v5 = v7;
  if ( v7 >= 0 )
    return v5;
  if ( (_DWORD)g_doStackCaptures )
  {
    v8 = v7;
LABEL_13:
    DoStackCapture(v8);
  }
LABEL_14:
  if ( a3 )
    PropVariantClear(a3);
  return v5;
}

```

## disassembly

```asm
0x1801b2000  mov     [rsp+arg_0], rbx
0x1801b2005  push    rsi
0x1801b2006  sub     rsp, 20h
0x1801b200a  mov     rsi, r8
0x1801b200d  mov     rbx, rcx
0x1801b2010  cmp     edx, 1
0x1801b2013  jz      short loc_1801B201C
0x1801b2015  mov     ebx, 80070057h
0x1801b201a  jmp     short loc_1801B2084
0x1801b201c  cmp     qword ptr [rcx+98h], 0
0x1801b2024  jz      short loc_1801B206B
0x1801b2026  movzx   ecx, word ptr [rcx+0A0h]; cb
0x1801b202d  call    cs:__imp_CoTaskMemAlloc
0x1801b2033  mov     [rsi+8], rax
0x1801b2037  test    rax, rax
0x1801b203a  jz      short loc_1801B207F
0x1801b203c  movzx   edx, word ptr [rbx+0A0h]; unsigned __int64
0x1801b2043  mov     rcx, rax; char *
0x1801b2046  mov     r8, [rbx+98h]; char *
0x1801b204d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1801b2052  mov     ebx, eax
0x1801b2054  test    eax, eax
0x1801b2056  jns     short loc_1801B20A8
0x1801b2058  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b205f  jz      short loc_1801B2065
0x1801b2061  mov     ecx, eax
0x1801b2063  jmp     short loc_1801B208F
0x1801b2065  test    eax, eax
0x1801b2067  js      short loc_1801B2094
0x1801b2069  jmp     short loc_1801B20A8
0x1801b206b  mov     ecx, 1; cb
0x1801b2070  call    cs:__imp_CoTaskMemAlloc
0x1801b2076  mov     [rsi+8], rax
0x1801b207a  test    rax, rax
0x1801b207d  jnz     short loc_1801B20A4
0x1801b207f  mov     ebx, 8007000Eh
0x1801b2084  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b208b  jz      short loc_1801B2094
0x1801b208d  mov     ecx, ebx; int
0x1801b208f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b2094  test    rsi, rsi
0x1801b2097  jz      short loc_1801B20A8
0x1801b2099  mov     rcx, rsi; pvar
0x1801b209c  call    cs:__imp_PropVariantClear
0x1801b20a2  jmp     short loc_1801B20A8
0x1801b20a4  xor     ebx, ebx
0x1801b20a6  mov     [rax], bl
0x1801b20a8  mov     eax, ebx
0x1801b20aa  mov     rbx, [rsp+28h+arg_0]
0x1801b20af  add     rsp, 20h
0x1801b20b3  pop     rsi
0x1801b20b4  retn
```
