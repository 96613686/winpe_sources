# ConvertCommentToBlob(tagPROPVARIANT *)

- ea: `0x1800caea4`
- end: `0x1800caf6a`
- name: `?ConvertCommentToBlob@@YAJPEAUtagPROPVARIANT@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180055aa4`

## callees

- `0x1800bb784`
- `0x1800caea4`
- `0x1800caf70`
- `0x1800cb038`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800caf23`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800caf23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800caf52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800caf52`

## pseudocode

```c
__int64 __fastcall ConvertCommentToBlob(PROPVARIANT *pvar)
{
  int v1; // edx
  unsigned __int16 *v2; // rsi
  int v4; // edx
  int v5; // edx
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // eax
  int v9; // eax
  unsigned __int16 *v11; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(unsigned __int16 *)pvar;
  v2 = 0;
  v11 = 0;
  v4 = v1 - 30;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 == 34 )
      {
        v6 = 0;
      }
      else
      {
        v6 = -2147024809;
        if ( (_DWORD)g_doStackCaptures )
        {
          v7 = -2147024809;
LABEL_16:
          DoStackCapture(v7);
          goto LABEL_17;
        }
      }
      goto LABEL_17;
    }
    v2 = (unsigned __int16 *)pvar[1];
    *(_OWORD *)pvar = 0;
    pvar[2] = 0;
  }
  else
  {
    v8 = ConvertToWideString((LPCCH)pvar[1], &v11);
    v6 = v8;
    if ( v8 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v8);
      v2 = v11;
      goto LABEL_17;
    }
    PropVariantClear(pvar);
    v2 = v11;
  }
  v9 = ConvertCommentOnWrite(v2, pvar);
  v6 = v9;
  if ( v9 < 0 && (_DWORD)g_doStackCaptures )
  {
    v7 = v9;
    goto LABEL_16;
  }
LABEL_17:
  CoTaskMemFree(v2);
  return v6;
}

```

## disassembly

```asm
0x1800caea4  mov     [rsp+arg_8], rbx
0x1800caea9  mov     [rsp+arg_10], rsi
0x1800caeae  push    rdi
0x1800caeaf  sub     rsp, 20h
0x1800caeb3  movzx   edx, word ptr [rcx]
0x1800caeb6  xor     esi, esi
0x1800caeb8  mov     [rsp+28h+arg_0], rsi
0x1800caebd  mov     rdi, rcx
0x1800caec0  sub     edx, 1Eh
0x1800caec3  jz      short loc_1800CAEF6
0x1800caec5  sub     edx, 1
0x1800caec8  jz      short loc_1800CAEE4
0x1800caeca  cmp     edx, 22h ; '"'
0x1800caecd  jz      short loc_1800CAEE0
0x1800caecf  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800caed5  mov     ebx, 80070057h
0x1800caeda  jz      short loc_1800CAF4F
0x1800caedc  mov     ecx, ebx
0x1800caede  jmp     short loc_1800CAF4A
0x1800caee0  xor     ebx, ebx
0x1800caee2  jmp     short loc_1800CAF4F
0x1800caee4  mov     rsi, [rcx+8]
0x1800caee8  xorps   xmm0, xmm0
0x1800caeeb  xor     eax, eax
0x1800caeed  movups  xmmword ptr [rcx], xmm0
0x1800caef0  mov     [rcx+10h], rax
0x1800caef4  jmp     short loc_1800CAF2E
0x1800caef6  mov     rcx, [rcx+8]; lpMultiByteStr
0x1800caefa  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 **
0x1800caeff  call    ?ConvertToWideString@@YAJPEBDPEAPEAG@Z; ConvertToWideString(char const *,ushort * *)
0x1800caf04  mov     ebx, eax
0x1800caf06  test    eax, eax
0x1800caf08  jns     short loc_1800CAF20
0x1800caf0a  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800caf10  jz      short loc_1800CAF19
0x1800caf12  mov     ecx, eax; int
0x1800caf14  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800caf19  mov     rsi, [rsp+28h+arg_0]
0x1800caf1e  jmp     short loc_1800CAF4F
0x1800caf20  mov     rcx, rdi; pvar
0x1800caf23  call    cs:__imp_PropVariantClear
0x1800caf29  mov     rsi, [rsp+28h+arg_0]
0x1800caf2e  mov     rdx, rdi; pvar
0x1800caf31  mov     rcx, rsi; Src
0x1800caf34  call    ?ConvertCommentOnWrite@@YAJPEAGPEAUtagPROPVARIANT@@@Z; ConvertCommentOnWrite(ushort *,tagPROPVARIANT *)
0x1800caf39  mov     ebx, eax
0x1800caf3b  test    eax, eax
0x1800caf3d  jns     short loc_1800CAF4F
0x1800caf3f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800caf46  jz      short loc_1800CAF4F
0x1800caf48  mov     ecx, eax; int
0x1800caf4a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800caf4f  mov     rcx, rsi; pv
0x1800caf52  call    cs:__imp_CoTaskMemFree
0x1800caf58  mov     rsi, [rsp+28h+arg_10]
0x1800caf5d  mov     eax, ebx
0x1800caf5f  mov     rbx, [rsp+28h+arg_8]
0x1800caf64  add     rsp, 20h
0x1800caf68  pop     rdi
0x1800caf69  retn
```
