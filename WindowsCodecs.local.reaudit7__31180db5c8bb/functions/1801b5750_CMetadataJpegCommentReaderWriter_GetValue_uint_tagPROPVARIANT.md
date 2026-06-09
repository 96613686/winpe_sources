# CMetadataJpegCommentReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x1801b5750`
- end: `0x1801b5818`
- name: `?GetValue@CMetadataJpegCommentReaderWriter@@EEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(CMetadataJpegCommentReaderWriter *this, int, PROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004f894`
- `0x1800bd9d4`
- `0x1801b5750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b577d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b57c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b577d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b57c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b57f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b57f8`

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
0x1801b5750  mov     [rsp+arg_0], rbx
0x1801b5755  push    rsi
0x1801b5756  sub     rsp, 20h
0x1801b575a  mov     rsi, r8
0x1801b575d  mov     rbx, rcx
0x1801b5760  cmp     edx, 1
0x1801b5763  jz      short loc_1801B576C
0x1801b5765  mov     ebx, 80070057h
0x1801b576a  jmp     short loc_1801B57E0
0x1801b576c  cmp     qword ptr [rcx+98h], 0
0x1801b5774  jz      short loc_1801B57C1
0x1801b5776  movzx   ecx, word ptr [rcx+0A0h]; cb
0x1801b577d  call    cs:__imp_CoTaskMemAlloc
0x1801b5784  nop     dword ptr [rax+rax+00h]
0x1801b5789  mov     [rsi+8], rax
0x1801b578d  test    rax, rax
0x1801b5790  jz      short loc_1801B57DB
0x1801b5792  movzx   edx, word ptr [rbx+0A0h]; unsigned __int64
0x1801b5799  mov     rcx, rax; char *
0x1801b579c  mov     r8, [rbx+98h]; char *
0x1801b57a3  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1801b57a8  mov     ebx, eax
0x1801b57aa  test    eax, eax
0x1801b57ac  jns     short loc_1801B580A
0x1801b57ae  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b57b5  jz      short loc_1801B57BB
0x1801b57b7  mov     ecx, eax
0x1801b57b9  jmp     short loc_1801B57EB
0x1801b57bb  test    eax, eax
0x1801b57bd  js      short loc_1801B57F0
0x1801b57bf  jmp     short loc_1801B580A
0x1801b57c1  mov     ecx, 1; cb
0x1801b57c6  call    cs:__imp_CoTaskMemAlloc
0x1801b57cd  nop     dword ptr [rax+rax+00h]
0x1801b57d2  mov     [rsi+8], rax
0x1801b57d6  test    rax, rax
0x1801b57d9  jnz     short loc_1801B5806
0x1801b57db  mov     ebx, 8007000Eh
0x1801b57e0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b57e7  jz      short loc_1801B57F0
0x1801b57e9  mov     ecx, ebx; int
0x1801b57eb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b57f0  test    rsi, rsi
0x1801b57f3  jz      short loc_1801B580A
0x1801b57f5  mov     rcx, rsi; pvar
0x1801b57f8  call    cs:__imp_PropVariantClear
0x1801b57ff  nop     dword ptr [rax+rax+00h]
0x1801b5804  jmp     short loc_1801B580A
0x1801b5806  xor     ebx, ebx
0x1801b5808  mov     [rax], bl
0x1801b580a  mov     eax, ebx
0x1801b580c  mov     rbx, [rsp+28h+arg_0]
0x1801b5811  add     rsp, 20h
0x1801b5815  pop     rsi
0x1801b5816  retn
```
