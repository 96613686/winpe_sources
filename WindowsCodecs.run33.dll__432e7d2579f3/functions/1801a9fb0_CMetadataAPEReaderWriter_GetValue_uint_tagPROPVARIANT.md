# CMetadataAPEReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x1801a9fb0`
- end: `0x1801aa07a`
- name: `?GetValue@CMetadataAPEReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(CMetadataAPEReaderWriter *this, int, PROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bb784`
- `0x18017b528`
- `0x1801a9fb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801a9fec`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801a9fec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801aa024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801aa024`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa062`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa062`

## pseudocode

```c
__int64 __fastcall CMetadataAPEReaderWriter::GetValue(CMetadataAPEReaderWriter *this, int a2, PROPVARIANT *a3)
{
  unsigned int v3; // ebx
  int v6; // edx
  HRESULT v7; // eax
  int v8; // ecx
  void *v9; // rax

  v3 = 0;
  v6 = a2 - 1;
  if ( !v6 )
  {
    if ( !*((_DWORD *)this + 41) )
    {
      PropVariantClear(a3);
      return v3;
    }
    *((_DWORD *)a3 + 2) = 11;
    v9 = CoTaskMemAlloc(0xBu);
    a3[2] = v9;
    if ( v9 )
    {
      memcpy_0(v9, (char *)this + 152, *((unsigned int *)a3 + 2));
      return v3;
    }
    v3 = -2147024882;
LABEL_12:
    if ( (_DWORD)g_doStackCaptures )
    {
      v8 = v3;
      goto LABEL_14;
    }
    return v3;
  }
  if ( v6 != 1 )
  {
    v3 = -2147024809;
    goto LABEL_12;
  }
  if ( *((_WORD *)this + 84) == 4113 )
  {
    v7 = PropVariantCopy(a3, (const PROPVARIANT *)this + 21);
    v3 = v7;
    if ( v7 < 0 && (_DWORD)g_doStackCaptures )
    {
      v8 = v7;
LABEL_14:
      DoStackCapture(v8);
    }
  }
  else
  {
    *(_WORD *)a3 = 4113;
    *((_DWORD *)a3 + 2) = 0;
    a3[2] = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1801a9fb0  mov     [rsp+arg_0], rbx
0x1801a9fb5  mov     [rsp+arg_8], rsi
0x1801a9fba  push    rdi
0x1801a9fbb  sub     rsp, 20h
0x1801a9fbf  xor     ebx, ebx
0x1801a9fc1  mov     rdi, r8
0x1801a9fc4  mov     rsi, rcx
0x1801a9fc7  sub     edx, 1
0x1801a9fca  jz      short loc_1801AA013
0x1801a9fcc  cmp     edx, 1
0x1801a9fcf  jz      short loc_1801A9FD8
0x1801a9fd1  mov     ebx, 80070057h
0x1801a9fd6  jmp     short loc_1801AA038
0x1801a9fd8  lea     rdx, [rcx+0A8h]; pvarSrc
0x1801a9fdf  mov     eax, 1011h
0x1801a9fe4  cmp     [rdx], ax
0x1801a9fe7  jnz     short loc_1801AA005
0x1801a9fe9  mov     rcx, rdi; pvarDest
0x1801a9fec  call    cs:__imp_PropVariantCopy
0x1801a9ff2  mov     ebx, eax
0x1801a9ff4  test    eax, eax
0x1801a9ff6  jns     short loc_1801AA068
0x1801a9ff8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a9fff  jz      short loc_1801AA068
0x1801aa001  mov     ecx, eax
0x1801aa003  jmp     short loc_1801AA043
0x1801aa005  mov     [r8], ax
0x1801aa009  mov     [r8+8], ebx
0x1801aa00d  mov     [r8+10h], rbx
0x1801aa011  jmp     short loc_1801AA068
0x1801aa013  cmp     [rcx+0A4h], ebx
0x1801aa019  jz      short loc_1801AA05F
0x1801aa01b  mov     ecx, 0Bh; cb
0x1801aa020  mov     [r8+8], ecx
0x1801aa024  call    cs:__imp_CoTaskMemAlloc
0x1801aa02a  mov     [rdi+10h], rax
0x1801aa02e  test    rax, rax
0x1801aa031  jnz     short loc_1801AA04A
0x1801aa033  mov     ebx, 8007000Eh
0x1801aa038  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801aa03f  jz      short loc_1801AA068
0x1801aa041  mov     ecx, ebx; int
0x1801aa043  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801aa048  jmp     short loc_1801AA068
0x1801aa04a  mov     r8d, [rdi+8]; Size
0x1801aa04e  lea     rdx, [rsi+98h]; Src
0x1801aa055  mov     rcx, rax; void *
0x1801aa058  call    memcpy_0
0x1801aa05d  jmp     short loc_1801AA068
0x1801aa05f  mov     rcx, rdi; pvar
0x1801aa062  call    cs:__imp_PropVariantClear
0x1801aa068  mov     rsi, [rsp+28h+arg_8]
0x1801aa06d  mov     eax, ebx
0x1801aa06f  mov     rbx, [rsp+28h+arg_0]
0x1801aa074  add     rsp, 20h
0x1801aa078  pop     rdi
0x1801aa079  retn
```
