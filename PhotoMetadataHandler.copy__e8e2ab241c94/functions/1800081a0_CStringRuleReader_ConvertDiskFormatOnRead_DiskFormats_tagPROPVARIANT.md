# CStringRuleReader::ConvertDiskFormatOnRead(DiskFormats,tagPROPVARIANT *)

- ea: `0x1800081a0`
- end: `0x18000835b`
- name: `?ConvertDiskFormatOnRead@CStringRuleReader@@UEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(__int64, int *, PROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800081a0`
- `0x1800084a0`
- `0x180008840`
- `0x180008b60`
- `0x1800129d8`
- `0x18001eaec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008210`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800082b1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008210`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800082b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000824e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008276`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008315`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000833d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000824e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008276`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008315`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000833d`

## pseudocode

```c
__int64 __fastcall CStringRuleReader::ConvertDiskFormatOnRead(__int64 a1, int *a2, PROPVARIANT *a3)
{
  int v4; // ebx
  LPCCH *pData; // rcx
  int v7; // eax
  PROPVARIANT pvarDest; // [rsp+20h] [rbp-20h] BYREF

  if ( (_DWORD)a2 != 3 )
  {
    if ( (_DWORD)a2 == 4 )
    {
      memset(&pvarDest, 0, sizeof(pvarDest));
      v4 = PropVariantCopy(&pvarDest, a3);
      if ( v4 >= 0 )
        v4 = ConvertExifVersionOnRead(&pvarDest, a3);
    }
    else
    {
      if ( (_DWORD)a2 != 2 )
      {
LABEL_3:
        if ( a3->vt != 30 )
        {
          v4 = 0;
          if ( a3->vt != 4126 )
            return (unsigned int)v4;
        }
        memset(&pvarDest, 0, sizeof(pvarDest));
        v4 = SniffAndConvertToWideString(a3, &pvarDest);
        if ( v4 >= 0 )
        {
          PropVariantClear(a3);
          *a3 = pvarDest;
          memset(&pvarDest, 0, sizeof(pvarDest));
        }
        goto LABEL_12;
      }
      memset(&pvarDest, 0, sizeof(pvarDest));
      v4 = PropVariantCopy(&pvarDest, a3);
      if ( v4 >= 0 )
        v4 = ConvertBytesToLPWSTROnRead(&pvarDest, a3);
    }
LABEL_12:
    PropVariantClear(&pvarDest);
    if ( v4 >= 0 )
      return (unsigned int)v4;
    goto LABEL_13;
  }
  if ( a3->vt != 4126 )
    goto LABEL_3;
  if ( !a3->lVal || (pData = (LPCCH *)a3->bstrblobVal.pData) == 0 )
  {
    v4 = -2003292271;
LABEL_13:
    if ( g_doStackCaptures )
      DoStackCapture(v4);
    return (unsigned int)v4;
  }
  memset(&pvarDest, 0, sizeof(pvarDest));
  pvarDest.vt = 31;
  v7 = SniffAndConvertToWideString(*pData, a2, &pvarDest.bstrVal);
  v4 = v7;
  if ( v7 >= 0 )
  {
    PropVariantClear(a3);
    *a3 = pvarDest;
    memset(&pvarDest, 0, sizeof(pvarDest));
  }
  else if ( g_doStackCaptures )
  {
    DoStackCapture(v7);
  }
  PropVariantClear(&pvarDest);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800081a0  mov     [rsp-8+arg_0], rbx
0x1800081a5  mov     [rsp-8+arg_8], rdi
0x1800081aa  push    rbp
0x1800081ab  mov     rbp, rsp
0x1800081ae  sub     rsp, 40h
0x1800081b2  mov     rdi, r8
0x1800081b5  mov     ecx, 101Eh
0x1800081ba  cmp     edx, 3
0x1800081bd  jnz     short loc_1800081EE
0x1800081bf  cmp     cx, [r8]
0x1800081c3  jz      loc_1800082CD
0x1800081c9  mov     eax, 1Eh
0x1800081ce  cmp     ax, [r8]
0x1800081d2  jz      short loc_18000822C
0x1800081d4  xor     ebx, ebx
0x1800081d6  cmp     cx, [r8]
0x1800081da  jz      short loc_18000822C
0x1800081dc  mov     eax, ebx
0x1800081de  mov     rbx, [rsp+40h+arg_0]
0x1800081e3  mov     rdi, [rsp+40h+arg_8]
0x1800081e8  add     rsp, 40h
0x1800081ec  pop     rbp
0x1800081ed  retn
0x1800081ee  cmp     edx, 4
0x1800081f1  jz      loc_18000829D
0x1800081f7  cmp     edx, 2
0x1800081fa  jnz     short loc_1800081C9
0x1800081fc  xorps   xmm0, xmm0
0x1800081ff  xor     eax, eax
0x180008201  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180008205  mov     qword ptr [rbp+pvarDest+10h], rax
0x180008209  mov     rdx, rdi; pvarSrc
0x18000820c  lea     rcx, [rbp+pvarDest]; pvarDest
0x180008210  call    cs:__imp_PropVariantCopy
0x180008216  mov     ebx, eax
0x180008218  test    eax, eax
0x18000821a  js      short loc_180008272
0x18000821c  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000821f  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180008223  call    ?ConvertBytesToLPWSTROnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertBytesToLPWSTROnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180008228  mov     ebx, eax
0x18000822a  jmp     short loc_180008272
0x18000822c  xorps   xmm0, xmm0
0x18000822f  xor     eax, eax
0x180008231  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180008235  mov     qword ptr [rbp+pvarDest+10h], rax
0x180008239  lea     rdx, [rbp+pvarDest]; pvarDest
0x18000823d  mov     rcx, rdi; pvarSrc
0x180008240  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180008245  mov     ebx, eax
0x180008247  test    eax, eax
0x180008249  js      short loc_180008272
0x18000824b  mov     rcx, rdi; pvar
0x18000824e  call    cs:__imp_PropVariantClear
0x180008254  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x180008258  movups  xmmword ptr [rdi], xmm0
0x18000825b  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x180008260  movsd   qword ptr [rdi+10h], xmm1
0x180008265  xorps   xmm0, xmm0
0x180008268  xor     eax, eax
0x18000826a  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000826e  mov     qword ptr [rbp+pvarDest+10h], rax
0x180008272  lea     rcx, [rbp+pvarDest]; pvar
0x180008276  call    cs:__imp_PropVariantClear
0x18000827c  test    ebx, ebx
0x18000827e  jns     loc_1800081DC
0x180008284  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000828b  jz      loc_1800081DC
0x180008291  mov     ecx, ebx; int
0x180008293  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008298  jmp     loc_1800081DC
0x18000829d  xorps   xmm0, xmm0
0x1800082a0  xor     eax, eax
0x1800082a2  movups  xmmword ptr [rbp+pvarDest], xmm0
0x1800082a6  mov     qword ptr [rbp+pvarDest+10h], rax
0x1800082aa  mov     rdx, rdi; pvarSrc
0x1800082ad  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800082b1  call    cs:__imp_PropVariantCopy
0x1800082b7  mov     ebx, eax
0x1800082b9  test    eax, eax
0x1800082bb  js      short loc_1800082CB
0x1800082bd  mov     rdx, rdi; pvarDest
0x1800082c0  lea     rcx, [rbp+pvarDest]; pvarSrc
0x1800082c4  call    ?ConvertExifVersionOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertExifVersionOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800082c9  mov     ebx, eax
0x1800082cb  jmp     short loc_180008272
0x1800082cd  cmp     dword ptr [r8+8], 0
0x1800082d2  jz      short loc_180008351
0x1800082d4  mov     rcx, [r8+10h]
0x1800082d8  test    rcx, rcx
0x1800082db  jz      short loc_180008351
0x1800082dd  xorps   xmm0, xmm0
0x1800082e0  xor     eax, eax
0x1800082e2  movups  xmmword ptr [rbp+pvarDest], xmm0
0x1800082e6  mov     qword ptr [rbp+pvarDest+10h], rax
0x1800082ea  mov     eax, 1Fh
0x1800082ef  mov     word ptr [rbp+pvarDest], ax
0x1800082f3  lea     r8, [rbp+pvarDest+8]; unsigned __int16 **
0x1800082f7  mov     rcx, [rcx]; lpMultiByteStr
0x1800082fa  call    ?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z; SniffAndConvertToWideString(char const *,int *,ushort * *)
0x1800082ff  mov     ebx, eax
0x180008301  test    eax, eax
0x180008303  jns     short loc_180008312
0x180008305  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000830c  jnz     short loc_180008348
0x18000830e  test    eax, eax
0x180008310  js      short loc_180008339
0x180008312  mov     rcx, rdi; pvar
0x180008315  call    cs:__imp_PropVariantClear
0x18000831b  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x18000831f  movups  xmmword ptr [rdi], xmm0
0x180008322  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x180008327  movsd   qword ptr [rdi+10h], xmm1
0x18000832c  xorps   xmm0, xmm0
0x18000832f  xor     eax, eax
0x180008331  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180008335  mov     qword ptr [rbp+pvarDest+10h], rax
0x180008339  lea     rcx, [rbp+pvarDest]; pvar
0x18000833d  call    cs:__imp_PropVariantClear
0x180008343  jmp     loc_1800081DC
0x180008348  mov     ecx, eax; int
0x18000834a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000834f  jmp     short loc_180008339
0x180008351  mov     ebx, 88982F91h
0x180008356  jmp     loc_180008284
```
