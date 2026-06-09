# CStringRuleReader::ConvertDiskFormatOnRead(DiskFormats,tagPROPVARIANT *)

- ea: `0x180006ca0`
- end: `0x180006e88`
- name: `?ConvertDiskFormatOnRead@CStringRuleReader@@UEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `488`
- prototype: `int __high(enum DiskFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180006ca0`
- `0x180006fc0`
- `0x180007390`
- `0x1800076f0`
- `0x1800132dc`
- `0x18001f970`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006d11`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006dc4`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006d11`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006dc4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006d55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006d83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006e36`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006e64`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006d55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006d83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006e36`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006e64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  v7 = SniffAndConvertToWideString(*pData, a2, (LPVOID *)&pvarDest.puuid);
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
0x180006ca0  mov     [rsp-8+arg_0], rbx
0x180006ca5  mov     [rsp-8+arg_8], rdi
0x180006caa  push    rbp
0x180006cab  mov     rbp, rsp
0x180006cae  sub     rsp, 40h
0x180006cb2  mov     rdi, r8
0x180006cb5  mov     ecx, 101Eh
0x180006cba  cmp     edx, 3
0x180006cbd  jnz     short loc_180006CEF
0x180006cbf  cmp     cx, [r8]
0x180006cc3  jz      loc_180006DE6
0x180006cc9  mov     eax, 1Eh
0x180006cce  cmp     ax, [r8]
0x180006cd2  jz      short loc_180006D33
0x180006cd4  xor     ebx, ebx
0x180006cd6  cmp     cx, [r8]
0x180006cda  jz      short loc_180006D33
0x180006cdc  mov     eax, ebx
0x180006cde  mov     rbx, [rsp+40h+arg_0]
0x180006ce3  mov     rdi, [rsp+40h+arg_8]
0x180006ce8  add     rsp, 40h
0x180006cec  pop     rbp
0x180006ced  retn
0x180006cef  cmp     edx, 4
0x180006cf2  jz      loc_180006DB0
0x180006cf8  cmp     edx, 2
0x180006cfb  jnz     short loc_180006CC9
0x180006cfd  xorps   xmm0, xmm0
0x180006d00  xor     eax, eax
0x180006d02  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180006d06  mov     qword ptr [rbp+pvarDest+10h], rax
0x180006d0a  mov     rdx, rdi; pvarSrc
0x180006d0d  lea     rcx, [rbp+pvarDest]; pvarDest
0x180006d11  call    cs:__imp_PropVariantCopy
0x180006d18  nop     dword ptr [rax+rax+00h]
0x180006d1d  mov     ebx, eax
0x180006d1f  test    eax, eax
0x180006d21  js      short loc_180006D7F
0x180006d23  mov     rdx, rdi; struct tagPROPVARIANT *
0x180006d26  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180006d2a  call    ?ConvertBytesToLPWSTROnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertBytesToLPWSTROnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006d2f  mov     ebx, eax
0x180006d31  jmp     short loc_180006D7F
0x180006d33  xorps   xmm0, xmm0
0x180006d36  xor     eax, eax
0x180006d38  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180006d3c  mov     qword ptr [rbp+pvarDest+10h], rax
0x180006d40  lea     rdx, [rbp+pvarDest]; pvarDest
0x180006d44  mov     rcx, rdi; pvarSrc
0x180006d47  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006d4c  mov     ebx, eax
0x180006d4e  test    eax, eax
0x180006d50  js      short loc_180006D7F
0x180006d52  mov     rcx, rdi; pvar
0x180006d55  call    cs:__imp_PropVariantClear
0x180006d5c  nop     dword ptr [rax+rax+00h]
0x180006d61  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x180006d65  movups  xmmword ptr [rdi], xmm0
0x180006d68  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x180006d6d  movsd   qword ptr [rdi+10h], xmm1
0x180006d72  xorps   xmm0, xmm0
0x180006d75  xor     eax, eax
0x180006d77  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180006d7b  mov     qword ptr [rbp+pvarDest+10h], rax
0x180006d7f  lea     rcx, [rbp+pvarDest]; pvar
0x180006d83  call    cs:__imp_PropVariantClear
0x180006d8a  nop     dword ptr [rax+rax+00h]
0x180006d8f  test    ebx, ebx
0x180006d91  jns     loc_180006CDC
0x180006d97  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006d9e  jz      loc_180006CDC
0x180006da4  mov     ecx, ebx; int
0x180006da6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006dab  jmp     loc_180006CDC
0x180006db0  xorps   xmm0, xmm0
0x180006db3  xor     eax, eax
0x180006db5  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180006db9  mov     qword ptr [rbp+pvarDest+10h], rax
0x180006dbd  mov     rdx, rdi; pvarSrc
0x180006dc0  lea     rcx, [rbp+pvarDest]; pvarDest
0x180006dc4  call    cs:__imp_PropVariantCopy
0x180006dcb  nop     dword ptr [rax+rax+00h]
0x180006dd0  mov     ebx, eax
0x180006dd2  test    eax, eax
0x180006dd4  js      short loc_180006DE4
0x180006dd6  mov     rdx, rdi; pvarDest
0x180006dd9  lea     rcx, [rbp+pvarDest]; pvarSrc
0x180006ddd  call    ?ConvertExifVersionOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertExifVersionOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006de2  mov     ebx, eax
0x180006de4  jmp     short loc_180006D7F
0x180006de6  cmp     dword ptr [r8+8], 0
0x180006deb  jz      loc_180006E7E
0x180006df1  mov     rcx, [r8+10h]
0x180006df5  test    rcx, rcx
0x180006df8  jz      loc_180006E7E
0x180006dfe  xorps   xmm0, xmm0
0x180006e01  xor     eax, eax
0x180006e03  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180006e07  mov     qword ptr [rbp+pvarDest+10h], rax
0x180006e0b  mov     eax, 1Fh
0x180006e10  mov     word ptr [rbp+pvarDest], ax
0x180006e14  lea     r8, [rbp+pvarDest+8]; unsigned __int16 **
0x180006e18  mov     rcx, [rcx]; lpMultiByteStr
0x180006e1b  call    ?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z; SniffAndConvertToWideString(char const *,int *,ushort * *)
0x180006e20  mov     ebx, eax
0x180006e22  test    eax, eax
0x180006e24  jns     short loc_180006E33
0x180006e26  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006e2d  jnz     short loc_180006E75
0x180006e2f  test    eax, eax
0x180006e31  js      short loc_180006E60
0x180006e33  mov     rcx, rdi; pvar
0x180006e36  call    cs:__imp_PropVariantClear
0x180006e3d  nop     dword ptr [rax+rax+00h]
0x180006e42  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x180006e46  movups  xmmword ptr [rdi], xmm0
0x180006e49  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x180006e4e  movsd   qword ptr [rdi+10h], xmm1
0x180006e53  xorps   xmm0, xmm0
0x180006e56  xor     eax, eax
0x180006e58  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180006e5c  mov     qword ptr [rbp+pvarDest+10h], rax
0x180006e60  lea     rcx, [rbp+pvarDest]; pvar
0x180006e64  call    cs:__imp_PropVariantClear
0x180006e6b  nop     dword ptr [rax+rax+00h]
0x180006e70  jmp     loc_180006CDC
0x180006e75  mov     ecx, eax; int
0x180006e77  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006e7c  jmp     short loc_180006E60
0x180006e7e  mov     ebx, 88982F91h
0x180006e83  jmp     loc_180006D97
```
