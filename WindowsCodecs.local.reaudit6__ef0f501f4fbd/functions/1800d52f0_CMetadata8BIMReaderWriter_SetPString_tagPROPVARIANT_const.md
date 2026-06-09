# CMetadata8BIMReaderWriter::SetPString(tagPROPVARIANT const *)

- ea: `0x1800d52f0`
- end: `0x1800d549a`
- name: `?SetPString@CMetadata8BIMReaderWriter@@MEAAJPEBUtagPROPVARIANT@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(CMetadata8BIMReaderWriter *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d4fe0`
- `0x1800d50f0`
- `0x1800d5260`

## callees

- `0x180042ae8`
- `0x18004ecd4`
- `0x180064b00`
- `0x180093040`
- `0x1800a5864`
- `0x1800bd9d4`
- `0x1800d52f0`
- `0x18017e438`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d5427`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d5427`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d547e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d547e`

## pseudocode

```c
__int64 __fastcall CMetadata8BIMReaderWriter::SetPString(
        CMetadata8BIMReaderWriter *this,
        const struct tagPROPVARIANT *a2)
{
  void *puuid; // rdi
  unsigned int v5; // ebx
  HRESULT v6; // eax
  int v7; // ecx
  int v8; // eax
  unsigned int v9; // eax
  int v10; // r9d
  void *v11; // rax
  bool v12; // zf
  ULONGLONG pullResult; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 v15; // [rsp+50h] [rbp+18h] BYREF

  puuid = 0;
  pullResult = 0;
  v15 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024809);
    return v5;
  }
  if ( a2->vt == 30 )
  {
    v6 = StringCchLengthA(a2->pszVal, 0xFFu, &v15);
    v5 = v6;
    if ( v6 < 0 )
      goto LABEL_6;
    puuid = a2->puuid;
  }
  else
  {
    if ( a2->vt != 31 )
    {
      v12 = (_DWORD)g_doStackCaptures == 0;
      v5 = -2147024809;
LABEL_27:
      if ( v12 )
        goto LABEL_30;
      v7 = v5;
      goto LABEL_29;
    }
    v6 = StringCchLengthW(a2->bstrVal, 0xFFu, &v15);
    v5 = v6;
    if ( v6 < 0 )
    {
LABEL_6:
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_30;
      goto LABEL_7;
    }
    v8 = CoerceWideStrToAnsiStrCodepage(a2->bstrVal, (char **)&pullResult, 0);
    v5 = v8;
    if ( v8 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v8);
      puuid = (void *)pullResult;
      goto LABEL_30;
    }
    puuid = (void *)pullResult;
  }
  v6 = CMetadata8BIMReaderWriter::ClearPString(this);
  v5 = v6;
  if ( v6 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_30;
LABEL_7:
    v7 = v6;
LABEL_29:
    DoStackCapture(v7);
    goto LABEL_30;
  }
  v9 = (unsigned __int8)v15;
  *((_BYTE *)this + 152) = v15;
  if ( !(_BYTE)v9 )
    goto LABEL_30;
  pullResult = 0;
  v6 = ULongLongMult(v9, 1u, &pullResult);
  v5 = v6;
  if ( v6 >= 0 )
  {
    v11 = malloc(pullResult);
    *((_QWORD *)this + 20) = v11;
    if ( v11 )
    {
      memcpy_0(v11, puuid, *((unsigned __int8 *)this + 152));
      goto LABEL_30;
    }
    v12 = (_DWORD)g_doStackCaptures == 0;
    v5 = -2147024882;
    goto LABEL_27;
  }
  if ( v10 )
    goto LABEL_7;
LABEL_30:
  if ( a2->vt == 31 )
    CoTaskMemFree(puuid);
  return v5;
}

```

## disassembly

```asm
0x1800d52f0  mov     [rsp+arg_0], rbx
0x1800d52f5  push    rbp
0x1800d52f6  push    rsi
0x1800d52f7  push    rdi
0x1800d52f8  sub     rsp, 20h
0x1800d52fc  xor     edi, edi
0x1800d52fe  mov     rsi, rdx
0x1800d5301  mov     [rsp+38h+pullResult], rdi
0x1800d5306  mov     rbp, rcx
0x1800d5309  mov     [rsp+38h+arg_10], rdi
0x1800d530e  test    rdx, rdx
0x1800d5311  jnz     short loc_1800D5330
0x1800d5313  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d5319  mov     ebx, 80070057h
0x1800d531e  jz      loc_1800D548A
0x1800d5324  mov     ecx, ebx; int
0x1800d5326  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d532b  jmp     loc_1800D548A
0x1800d5330  cmp     word ptr [rdx], 1Eh
0x1800d5334  jnz     short loc_1800D5368
0x1800d5336  mov     rcx, [rsi+8]; char *
0x1800d533a  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x1800d533f  mov     edx, 0FFh; unsigned __int64
0x1800d5344  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800d5349  mov     ebx, eax
0x1800d534b  test    eax, eax
0x1800d534d  jns     short loc_1800D5362
0x1800d534f  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d5355  jz      loc_1800D5475
0x1800d535b  mov     ecx, eax
0x1800d535d  jmp     loc_1800D5470
0x1800d5362  mov     rdi, [rsi+8]
0x1800d5366  jmp     short loc_1800D53C0
0x1800d5368  cmp     word ptr [rdx], 1Fh
0x1800d536c  jnz     loc_1800D5461
0x1800d5372  mov     rcx, [rsi+8]; unsigned __int16 *
0x1800d5376  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x1800d537b  mov     edx, 0FFh; unsigned __int64
0x1800d5380  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d5385  mov     ebx, eax
0x1800d5387  test    eax, eax
0x1800d5389  js      short loc_1800D534F
0x1800d538b  mov     rcx, [rsi+8]; lpWideCharStr
0x1800d538f  lea     rdx, [rsp+38h+pullResult]; char **
0x1800d5394  xor     r8d, r8d; unsigned int
0x1800d5397  call    ?CoerceWideStrToAnsiStrCodepage@@YAJPEBGPEAPEADI@Z; CoerceWideStrToAnsiStrCodepage(ushort const *,char * *,uint)
0x1800d539c  mov     ebx, eax
0x1800d539e  test    eax, eax
0x1800d53a0  jns     short loc_1800D53BB
0x1800d53a2  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d53a8  jz      short loc_1800D53B1
0x1800d53aa  mov     ecx, eax; int
0x1800d53ac  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d53b1  mov     rdi, [rsp+38h+pullResult]
0x1800d53b6  jmp     loc_1800D5475
0x1800d53bb  mov     rdi, [rsp+38h+pullResult]
0x1800d53c0  mov     rcx, rbp; this
0x1800d53c3  call    ?ClearPString@CMetadata8BIMReaderWriter@@MEAAJXZ; CMetadata8BIMReaderWriter::ClearPString(void)
0x1800d53c8  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800d53cf  mov     ebx, eax
0x1800d53d1  test    eax, eax
0x1800d53d3  jns     short loc_1800D53E2
0x1800d53d5  test    r9d, r9d
0x1800d53d8  jnz     short loc_1800D535B
0x1800d53da  test    eax, eax
0x1800d53dc  js      loc_1800D5475
0x1800d53e2  movzx   eax, byte ptr [rsp+38h+arg_10]
0x1800d53e7  mov     [rbp+98h], al
0x1800d53ed  test    al, al
0x1800d53ef  jz      loc_1800D5475
0x1800d53f5  mov     ecx, eax; ullMultiplicand
0x1800d53f7  mov     [rsp+38h+pullResult], 0
0x1800d5400  lea     r8, [rsp+38h+pullResult]; pullResult
0x1800d5405  mov     edx, 1; ullMultiplier
0x1800d540a  call    ULongLongMult
0x1800d540f  mov     ebx, eax
0x1800d5411  test    eax, eax
0x1800d5413  jns     short loc_1800D5422
0x1800d5415  test    r9d, r9d
0x1800d5418  jnz     loc_1800D535B
0x1800d541e  test    eax, eax
0x1800d5420  js      short loc_1800D5475
0x1800d5422  mov     rcx, [rsp+38h+pullResult]; Size
0x1800d5427  call    cs:__imp_malloc
0x1800d542e  nop     dword ptr [rax+rax+00h]
0x1800d5433  mov     [rbp+0A0h], rax
0x1800d543a  test    rax, rax
0x1800d543d  jnz     short loc_1800D544C
0x1800d543f  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d5445  mov     ebx, 8007000Eh
0x1800d544a  jmp     short loc_1800D546C
0x1800d544c  movzx   r8d, byte ptr [rbp+98h]; Size
0x1800d5454  mov     rdx, rdi; Src
0x1800d5457  mov     rcx, rax; void *
0x1800d545a  call    memcpy_0
0x1800d545f  jmp     short loc_1800D5475
0x1800d5461  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d5467  mov     ebx, 80070057h
0x1800d546c  jz      short loc_1800D5475
0x1800d546e  mov     ecx, ebx; int
0x1800d5470  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d5475  cmp     word ptr [rsi], 1Fh
0x1800d5479  jnz     short loc_1800D548A
0x1800d547b  mov     rcx, rdi; pv
0x1800d547e  call    cs:__imp_CoTaskMemFree
0x1800d5485  nop     dword ptr [rax+rax+00h]
0x1800d548a  mov     eax, ebx
0x1800d548c  mov     rbx, [rsp+38h+arg_0]
0x1800d5491  add     rsp, 20h
0x1800d5495  pop     rdi
0x1800d5496  pop     rsi
0x1800d5497  pop     rbp
0x1800d5498  retn
```
