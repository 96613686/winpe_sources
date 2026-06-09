# ConvertExifVersionStringOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001fe04`
- end: `0x18001ff72`
- name: `?ConvertExifVersionStringOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `366`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d1f0`

## callees

- `0x1800096a0`
- `0x18000c5a0`
- `0x18001fe04`
- `0x180021034`
- `0x180027748`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fef2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fed0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001fec0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001fec0`

## pseudocode

```c
__int64 __fastcall ConvertExifVersionStringOnWrite(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  signed int v2; // ebx
  const unsigned __int16 *bstrVal; // rcx
  unsigned int v6; // r10d
  unsigned int v7; // r11d
  unsigned int cbMultiByte; // edi
  char *v9; // rsi
  signed int LastError; // eax
  unsigned __int64 v11; // rdx
  LPSTR v12; // rdi
  BYTE *pData; // rcx
  LPSTR lpMultiByteStr; // [rsp+80h] [rbp+8h] BYREF

  v2 = -2147024809;
  if ( a1->vt == 31 )
  {
    bstrVal = a1->bstrVal;
    lpMultiByteStr = 0;
    v2 = StringCchLengthW(bstrVal, 0x7FFFFFFFu, (unsigned __int64 *)&lpMultiByteStr);
    if ( v2 >= 0 )
    {
      cbMultiByte = (_DWORD)lpMultiByteStr + 1;
      if ( (int)lpMultiByteStr + 1 <= v7 )
      {
        lpMultiByteStr = 0;
        v2 = CoTaskMemAllocWithInit(cbMultiByte, (void **)&lpMultiByteStr);
        if ( v2 >= 0 )
        {
          v9 = lpMultiByteStr;
          if ( WideCharToMultiByte(0x4E9Fu, 0, a1->bstrVal, cbMultiByte, lpMultiByteStr, cbMultiByte, 0, 0) )
            goto LABEL_10;
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
          if ( v2 >= 0 )
          {
LABEL_10:
            PropVariantClear(a2);
            lpMultiByteStr = 0;
            v2 = StringCchLengthA(v9, v11, (unsigned __int64 *)&lpMultiByteStr);
            if ( v2 >= 0 )
            {
              v12 = lpMultiByteStr;
              v2 = CoTaskMemAllocWithInit((size_t)lpMultiByteStr, (void **)&a2->bstrblobVal.pData);
              if ( v2 >= 0 )
              {
                pData = a2->bstrblobVal.pData;
                a2->vt = 65;
                a2->lVal = (int)v12;
                memcpy_0(pData, v9, (size_t)v12);
              }
            }
          }
          CoTaskMemFree(v9);
        }
      }
      else
      {
        return v6;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001fe04  mov     rax, rsp
0x18001fe07  push    rbx
0x18001fe08  push    rbp
0x18001fe09  push    rsi
0x18001fe0a  push    rdi
0x18001fe0b  push    r14
0x18001fe0d  push    r15
0x18001fe0f  sub     rsp, 48h
0x18001fe13  cmp     word ptr [rcx], 1Fh
0x18001fe17  mov     r10d, 80070057h
0x18001fe1d  mov     ebx, r10d
0x18001fe20  mov     r14, rdx
0x18001fe23  mov     rbp, rcx
0x18001fe26  jnz     loc_18001FF62
0x18001fe2c  mov     rcx, [rcx+8]; unsigned __int16 *
0x18001fe30  lea     r8, [rax+8]; unsigned __int64 *
0x18001fe34  mov     r11d, 7FFFFFFFh
0x18001fe3a  mov     qword ptr [rax+8], 0
0x18001fe42  mov     edx, r11d; unsigned __int64
0x18001fe45  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001fe4a  mov     ebx, eax
0x18001fe4c  test    eax, eax
0x18001fe4e  js      loc_18001FF62
0x18001fe54  mov     edi, dword ptr [rsp+78h+arg_0]
0x18001fe5b  inc     edi
0x18001fe5d  cmp     edi, r11d
0x18001fe60  jbe     short loc_18001FE6A
0x18001fe62  mov     ebx, r10d
0x18001fe65  jmp     loc_18001FF62
0x18001fe6a  mov     ecx, edi; Size
0x18001fe6c  lea     rdx, [rsp+78h+arg_0]; void **
0x18001fe74  mov     [rsp+78h+arg_0], 0
0x18001fe80  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001fe85  mov     ebx, eax
0x18001fe87  test    eax, eax
0x18001fe89  js      loc_18001FF62
0x18001fe8f  mov     rsi, [rsp+78h+arg_0]
0x18001fe97  mov     r9d, edi; cchWideChar
0x18001fe9a  mov     r8, [rbp+8]; lpWideCharStr
0x18001fe9e  xor     edx, edx; dwFlags
0x18001fea0  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001fea9  mov     ecx, 4E9Fh; CodePage
0x18001feae  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18001feb7  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x18001febb  mov     [rsp+78h+lpMultiByteStr], rsi; lpMultiByteStr
0x18001fec0  call    cs:__imp_WideCharToMultiByte
0x18001fec7  nop     dword ptr [rax+rax+00h]
0x18001fecc  test    eax, eax
0x18001fece  jnz     short loc_18001FEEF
0x18001fed0  call    cs:__imp_GetLastError
0x18001fed7  nop     dword ptr [rax+rax+00h]
0x18001fedc  mov     ebx, eax
0x18001fede  test    eax, eax
0x18001fee0  jle     short loc_18001FEEB
0x18001fee2  movzx   ebx, ax
0x18001fee5  or      ebx, 80070000h
0x18001feeb  test    ebx, ebx
0x18001feed  js      short loc_18001FF53
0x18001feef  mov     rcx, r14; pvar
0x18001fef2  call    cs:__imp_PropVariantClear
0x18001fef9  nop     dword ptr [rax+rax+00h]
0x18001fefe  lea     r8, [rsp+78h+arg_0]; unsigned __int64 *
0x18001ff06  mov     [rsp+78h+arg_0], 0
0x18001ff12  mov     rcx, rsi; char *
0x18001ff15  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18001ff1a  mov     ebx, eax
0x18001ff1c  test    eax, eax
0x18001ff1e  js      short loc_18001FF53
0x18001ff20  mov     rdi, [rsp+78h+arg_0]
0x18001ff28  lea     rdx, [r14+10h]; void **
0x18001ff2c  mov     rcx, rdi; Size
0x18001ff2f  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001ff34  mov     ebx, eax
0x18001ff36  test    eax, eax
0x18001ff38  js      short loc_18001FF53
0x18001ff3a  mov     rcx, [r14+10h]; void *
0x18001ff3e  mov     r8, rdi; Size
0x18001ff41  mov     rdx, rsi; Src
0x18001ff44  mov     word ptr [r14], 41h ; 'A'
0x18001ff4a  mov     [r14+8], edi
0x18001ff4e  call    memcpy_0
0x18001ff53  mov     rcx, rsi; pv
0x18001ff56  call    cs:__imp_CoTaskMemFree
0x18001ff5d  nop     dword ptr [rax+rax+00h]
0x18001ff62  mov     eax, ebx
0x18001ff64  add     rsp, 48h
0x18001ff68  pop     r15
0x18001ff6a  pop     r14
0x18001ff6c  pop     rdi
0x18001ff6d  pop     rsi
0x18001ff6e  pop     rbp
0x18001ff6f  pop     rbx
0x18001ff70  retn
```
