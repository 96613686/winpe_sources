# ConvertCommentToBlob(tagPROPVARIANT *)

- ea: `0x1800cd3a0`
- end: `0x1800cd473`
- name: `?ConvertCommentToBlob@@YAJPEAUtagPROPVARIANT@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048d3c`

## callees

- `0x1800bd9d4`
- `0x1800cd3a0`
- `0x1800cd47c`
- `0x1800cd54c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cd41f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cd41f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd454`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd454`

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
0x1800cd3a0  mov     [rsp+arg_8], rbx
0x1800cd3a5  mov     [rsp+arg_10], rsi
0x1800cd3aa  push    rdi
0x1800cd3ab  sub     rsp, 20h
0x1800cd3af  movzx   edx, word ptr [rcx]
0x1800cd3b2  xor     esi, esi
0x1800cd3b4  mov     [rsp+28h+arg_0], rsi
0x1800cd3b9  mov     rdi, rcx
0x1800cd3bc  sub     edx, 1Eh
0x1800cd3bf  jz      short loc_1800CD3F2
0x1800cd3c1  sub     edx, 1
0x1800cd3c4  jz      short loc_1800CD3E0
0x1800cd3c6  cmp     edx, 22h ; '"'
0x1800cd3c9  jz      short loc_1800CD3DC
0x1800cd3cb  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800cd3d1  mov     ebx, 80070057h
0x1800cd3d6  jz      short loc_1800CD451
0x1800cd3d8  mov     ecx, ebx
0x1800cd3da  jmp     short loc_1800CD44C
0x1800cd3dc  xor     ebx, ebx
0x1800cd3de  jmp     short loc_1800CD451
0x1800cd3e0  mov     rsi, [rcx+8]
0x1800cd3e4  xorps   xmm0, xmm0
0x1800cd3e7  xor     eax, eax
0x1800cd3e9  movups  xmmword ptr [rcx], xmm0
0x1800cd3ec  mov     [rcx+10h], rax
0x1800cd3f0  jmp     short loc_1800CD430
0x1800cd3f2  mov     rcx, [rcx+8]; lpMultiByteStr
0x1800cd3f6  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 **
0x1800cd3fb  call    ?ConvertToWideString@@YAJPEBDPEAPEAG@Z; ConvertToWideString(char const *,ushort * *)
0x1800cd400  mov     ebx, eax
0x1800cd402  test    eax, eax
0x1800cd404  jns     short loc_1800CD41C
0x1800cd406  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800cd40c  jz      short loc_1800CD415
0x1800cd40e  mov     ecx, eax; int
0x1800cd410  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cd415  mov     rsi, [rsp+28h+arg_0]
0x1800cd41a  jmp     short loc_1800CD451
0x1800cd41c  mov     rcx, rdi; pvar
0x1800cd41f  call    cs:__imp_PropVariantClear
0x1800cd426  nop     dword ptr [rax+rax+00h]
0x1800cd42b  mov     rsi, [rsp+28h+arg_0]
0x1800cd430  mov     rdx, rdi; pvar
0x1800cd433  mov     rcx, rsi; Src
0x1800cd436  call    ?ConvertCommentOnWrite@@YAJPEAGPEAUtagPROPVARIANT@@@Z; ConvertCommentOnWrite(ushort *,tagPROPVARIANT *)
0x1800cd43b  mov     ebx, eax
0x1800cd43d  test    eax, eax
0x1800cd43f  jns     short loc_1800CD451
0x1800cd441  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800cd448  jz      short loc_1800CD451
0x1800cd44a  mov     ecx, eax; int
0x1800cd44c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cd451  mov     rcx, rsi; pv
0x1800cd454  call    cs:__imp_CoTaskMemFree
0x1800cd45b  nop     dword ptr [rax+rax+00h]
0x1800cd460  mov     rsi, [rsp+28h+arg_10]
0x1800cd465  mov     eax, ebx
0x1800cd467  mov     rbx, [rsp+28h+arg_8]
0x1800cd46c  add     rsp, 20h
0x1800cd470  pop     rdi
0x1800cd471  retn
```
