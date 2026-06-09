# CMetadata8BIMReaderWriter::SetPString(tagPROPVARIANT const *)

- ea: `0x1800d2960`
- end: `0x1800d2af9`
- name: `?SetPString@CMetadata8BIMReaderWriter@@MEAAJPEBUtagPROPVARIANT@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(CMetadata8BIMReaderWriter *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d2650`
- `0x1800d2760`
- `0x1800d28d0`

## callees

- `0x18001dd10`
- `0x180022d44`
- `0x180045650`
- `0x180067e88`
- `0x1800a5ec0`
- `0x1800bb784`
- `0x1800d2960`
- `0x18017b528`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d2a93`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d2a93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d2ae4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d2ae4`

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
0x1800d2960  mov     [rsp+arg_0], rbx
0x1800d2965  push    rbp
0x1800d2966  push    rsi
0x1800d2967  push    rdi
0x1800d2968  sub     rsp, 20h
0x1800d296c  xor     edi, edi
0x1800d296e  mov     rsi, rdx
0x1800d2971  mov     [rsp+38h+pullResult], rdi
0x1800d2976  mov     rbp, rcx
0x1800d2979  mov     [rsp+38h+arg_10], rdi
0x1800d297e  test    rdx, rdx
0x1800d2981  jnz     short loc_1800D29A0
0x1800d2983  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d2989  mov     ebx, 80070057h
0x1800d298e  jz      loc_1800D2AEA
0x1800d2994  mov     ecx, ebx; int
0x1800d2996  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d299b  jmp     loc_1800D2AEA
0x1800d29a0  cmp     word ptr [rdx], 1Eh
0x1800d29a4  jnz     short loc_1800D29D8
0x1800d29a6  mov     rcx, [rsi+8]; char *
0x1800d29aa  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x1800d29af  mov     edx, 0FFh; unsigned __int64
0x1800d29b4  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800d29b9  mov     ebx, eax
0x1800d29bb  test    eax, eax
0x1800d29bd  jns     short loc_1800D29D2
0x1800d29bf  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d29c5  jz      loc_1800D2ADB
0x1800d29cb  mov     ecx, eax
0x1800d29cd  jmp     loc_1800D2AD6
0x1800d29d2  mov     rdi, [rsi+8]
0x1800d29d6  jmp     short loc_1800D2A30
0x1800d29d8  cmp     word ptr [rdx], 1Fh
0x1800d29dc  jnz     loc_1800D2AC7
0x1800d29e2  mov     rcx, [rsi+8]; unsigned __int16 *
0x1800d29e6  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x1800d29eb  mov     edx, 0FFh; unsigned __int64
0x1800d29f0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d29f5  mov     ebx, eax
0x1800d29f7  test    eax, eax
0x1800d29f9  js      short loc_1800D29BF
0x1800d29fb  mov     rcx, [rsi+8]; lpWideCharStr
0x1800d29ff  lea     rdx, [rsp+38h+pullResult]; char **
0x1800d2a04  xor     r8d, r8d; unsigned int
0x1800d2a07  call    ?CoerceWideStrToAnsiStrCodepage@@YAJPEBGPEAPEADI@Z; CoerceWideStrToAnsiStrCodepage(ushort const *,char * *,uint)
0x1800d2a0c  mov     ebx, eax
0x1800d2a0e  test    eax, eax
0x1800d2a10  jns     short loc_1800D2A2B
0x1800d2a12  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d2a18  jz      short loc_1800D2A21
0x1800d2a1a  mov     ecx, eax; int
0x1800d2a1c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2a21  mov     rdi, [rsp+38h+pullResult]
0x1800d2a26  jmp     loc_1800D2ADB
0x1800d2a2b  mov     rdi, [rsp+38h+pullResult]
0x1800d2a30  mov     rcx, rbp; this
0x1800d2a33  call    ?ClearPString@CMetadata8BIMReaderWriter@@MEAAJXZ; CMetadata8BIMReaderWriter::ClearPString(void)
0x1800d2a38  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800d2a3f  mov     ebx, eax
0x1800d2a41  test    eax, eax
0x1800d2a43  jns     short loc_1800D2A52
0x1800d2a45  test    r9d, r9d
0x1800d2a48  jnz     short loc_1800D29CB
0x1800d2a4a  test    eax, eax
0x1800d2a4c  js      loc_1800D2ADB
0x1800d2a52  movzx   eax, byte ptr [rsp+38h+arg_10]
0x1800d2a57  mov     [rbp+98h], al
0x1800d2a5d  test    al, al
0x1800d2a5f  jz      short loc_1800D2ADB
0x1800d2a61  mov     ecx, eax; ullMultiplicand
0x1800d2a63  mov     [rsp+38h+pullResult], 0
0x1800d2a6c  lea     r8, [rsp+38h+pullResult]; pullResult
0x1800d2a71  mov     edx, 1; ullMultiplier
0x1800d2a76  call    ULongLongMult
0x1800d2a7b  mov     ebx, eax
0x1800d2a7d  test    eax, eax
0x1800d2a7f  jns     short loc_1800D2A8E
0x1800d2a81  test    r9d, r9d
0x1800d2a84  jnz     loc_1800D29CB
0x1800d2a8a  test    eax, eax
0x1800d2a8c  js      short loc_1800D2ADB
0x1800d2a8e  mov     rcx, [rsp+38h+pullResult]; Size
0x1800d2a93  call    cs:__imp_malloc
0x1800d2a99  mov     [rbp+0A0h], rax
0x1800d2aa0  test    rax, rax
0x1800d2aa3  jnz     short loc_1800D2AB2
0x1800d2aa5  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d2aab  mov     ebx, 8007000Eh
0x1800d2ab0  jmp     short loc_1800D2AD2
0x1800d2ab2  movzx   r8d, byte ptr [rbp+98h]; Size
0x1800d2aba  mov     rdx, rdi; Src
0x1800d2abd  mov     rcx, rax; void *
0x1800d2ac0  call    memcpy_0
0x1800d2ac5  jmp     short loc_1800D2ADB
0x1800d2ac7  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d2acd  mov     ebx, 80070057h
0x1800d2ad2  jz      short loc_1800D2ADB
0x1800d2ad4  mov     ecx, ebx; int
0x1800d2ad6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2adb  cmp     word ptr [rsi], 1Fh
0x1800d2adf  jnz     short loc_1800D2AEA
0x1800d2ae1  mov     rcx, rdi; pv
0x1800d2ae4  call    cs:__imp_CoTaskMemFree
0x1800d2aea  mov     eax, ebx
0x1800d2aec  mov     rbx, [rsp+38h+arg_0]
0x1800d2af1  add     rsp, 20h
0x1800d2af5  pop     rdi
0x1800d2af6  pop     rsi
0x1800d2af7  pop     rbp
0x1800d2af8  retn
```
