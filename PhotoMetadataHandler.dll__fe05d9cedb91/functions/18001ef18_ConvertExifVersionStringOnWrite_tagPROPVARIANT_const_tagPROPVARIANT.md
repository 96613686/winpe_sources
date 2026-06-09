# ConvertExifVersionStringOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001ef18`
- end: `0x18001f06d`
- name: `?ConvertExifVersionStringOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `341`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c4c0`

## callees

- `0x180007d90`
- `0x18000bff0`
- `0x18001ef18`
- `0x18002005c`
- `0x180026498`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001effa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001effa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f058`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efde`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001efd4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001efd4`

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
0x18001ef18  mov     rax, rsp
0x18001ef1b  push    rbx
0x18001ef1c  push    rbp
0x18001ef1d  push    rsi
0x18001ef1e  push    rdi
0x18001ef1f  push    r14
0x18001ef21  push    r15
0x18001ef23  sub     rsp, 48h
0x18001ef27  cmp     word ptr [rcx], 1Fh
0x18001ef2b  mov     r10d, 80070057h
0x18001ef31  mov     ebx, r10d
0x18001ef34  mov     r14, rdx
0x18001ef37  mov     rbp, rcx
0x18001ef3a  jnz     loc_18001F05E
0x18001ef40  mov     rcx, [rcx+8]; unsigned __int16 *
0x18001ef44  lea     r8, [rax+8]; unsigned __int64 *
0x18001ef48  mov     r11d, 7FFFFFFFh
0x18001ef4e  mov     qword ptr [rax+8], 0
0x18001ef56  mov     edx, r11d; unsigned __int64
0x18001ef59  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001ef5e  mov     ebx, eax
0x18001ef60  test    eax, eax
0x18001ef62  js      loc_18001F05E
0x18001ef68  mov     edi, dword ptr [rsp+78h+arg_0]
0x18001ef6f  inc     edi
0x18001ef71  cmp     edi, r11d
0x18001ef74  jbe     short loc_18001EF7E
0x18001ef76  mov     ebx, r10d
0x18001ef79  jmp     loc_18001F05E
0x18001ef7e  mov     ecx, edi; Size
0x18001ef80  lea     rdx, [rsp+78h+arg_0]; void **
0x18001ef88  mov     [rsp+78h+arg_0], 0
0x18001ef94  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001ef99  mov     ebx, eax
0x18001ef9b  test    eax, eax
0x18001ef9d  js      loc_18001F05E
0x18001efa3  mov     rsi, [rsp+78h+arg_0]
0x18001efab  mov     r9d, edi; cchWideChar
0x18001efae  mov     r8, [rbp+8]; lpWideCharStr
0x18001efb2  xor     edx, edx; dwFlags
0x18001efb4  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001efbd  mov     ecx, 4E9Fh; CodePage
0x18001efc2  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18001efcb  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x18001efcf  mov     [rsp+78h+lpMultiByteStr], rsi; lpMultiByteStr
0x18001efd4  call    cs:__imp_WideCharToMultiByte
0x18001efda  test    eax, eax
0x18001efdc  jnz     short loc_18001EFF7
0x18001efde  call    cs:__imp_GetLastError
0x18001efe4  mov     ebx, eax
0x18001efe6  test    eax, eax
0x18001efe8  jle     short loc_18001EFF3
0x18001efea  movzx   ebx, ax
0x18001efed  or      ebx, 80070000h
0x18001eff3  test    ebx, ebx
0x18001eff5  js      short loc_18001F055
0x18001eff7  mov     rcx, r14; pvar
0x18001effa  call    cs:__imp_PropVariantClear
0x18001f000  lea     r8, [rsp+78h+arg_0]; unsigned __int64 *
0x18001f008  mov     [rsp+78h+arg_0], 0
0x18001f014  mov     rcx, rsi; char *
0x18001f017  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18001f01c  mov     ebx, eax
0x18001f01e  test    eax, eax
0x18001f020  js      short loc_18001F055
0x18001f022  mov     rdi, [rsp+78h+arg_0]
0x18001f02a  lea     rdx, [r14+10h]; void **
0x18001f02e  mov     rcx, rdi; Size
0x18001f031  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001f036  mov     ebx, eax
0x18001f038  test    eax, eax
0x18001f03a  js      short loc_18001F055
0x18001f03c  mov     rcx, [r14+10h]; void *
0x18001f040  mov     r8, rdi; Size
0x18001f043  mov     rdx, rsi; Src
0x18001f046  mov     word ptr [r14], 41h ; 'A'
0x18001f04c  mov     [r14+8], edi
0x18001f050  call    memcpy_0
0x18001f055  mov     rcx, rsi; pv
0x18001f058  call    cs:__imp_CoTaskMemFree
0x18001f05e  mov     eax, ebx
0x18001f060  add     rsp, 48h
0x18001f064  pop     r15
0x18001f066  pop     r14
0x18001f068  pop     rdi
0x18001f069  pop     rsi
0x18001f06a  pop     rbp
0x18001f06b  pop     rbx
0x18001f06c  retn
```
