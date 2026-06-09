# CPubCacheBackingStore::CreateHashStore(ushort *)

- ea: `0x180056148`
- end: `0x1800562a9`
- name: `?CreateHashStore@CPubCacheBackingStore@@AEAAKPEAG@Z`
- size: `353`
- prototype: `unsigned int(CPubCacheBackingStore *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800556f0`

## callees

- `0x180004374`
- `0x18000cf48`
- `0x180056148`
- `0x180062688`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800561ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005621d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800561ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005621d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800561a3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180056213`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800561a3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180056213`

## pseudocode

```c
__int64 __fastcall CPubCacheBackingStore::CreateHashStore(CPubCacheBackingStore *this, unsigned __int16 *a2)
{
  DWORD HashSubStorePath; // eax
  DWORD v4; // ebx
  CHostedCacheMsgEncoding *v5; // rcx
  int v6; // edx
  unsigned int v7; // edi
  WCHAR *v8; // r9
  WCHAR PathName[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 102, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  if ( CreateDirectoryW(a2, 0) || (HashSubStorePath = GetLastError(), v4 = HashSubStorePath, HashSubStorePath == 183) )
  {
    v7 = 0;
    v4 = 0;
    while ( v7 < 0x10 )
    {
      HashSubStorePath = GenerateHashSubStorePath(a2, v7, PathName);
      v4 = HashSubStorePath;
      if ( HashSubStorePath )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v6 = 104;
          goto LABEL_26;
        }
        return v4;
      }
      if ( !CreateDirectoryW(PathName, 0) )
      {
        HashSubStorePath = GetLastError();
        v4 = HashSubStorePath;
        if ( HashSubStorePath != 183 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v6 = 105;
            v8 = PathName;
            goto LABEL_27;
          }
          return v4;
        }
        v4 = 0;
      }
      ++v7;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v6 = 103;
LABEL_26:
      LODWORD(v8) = (_DWORD)a2;
LABEL_27:
      WPP_SF_Sd(
        *((_QWORD *)v5 + 12),
        v6,
        (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
        (_DWORD)v8,
        HashSubStorePath);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180056148  push    rbx
0x18005614a  push    rsi
0x18005614b  push    rdi
0x18005614c  push    r14
0x18005614e  sub     rsp, 258h
0x180056155  mov     rax, cs:__security_cookie
0x18005615c  xor     rax, rsp
0x18005615f  mov     [rsp+278h+var_38], rax
0x180056167  mov     rsi, rdx
0x18005616a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056171  lea     r14, WPP_GLOBAL_Control
0x180056178  cmp     rcx, r14
0x18005617b  jz      short loc_18005619E
0x18005617d  test    byte ptr [rcx+6Ch], 4
0x180056181  jz      short loc_18005619E
0x180056183  cmp     byte ptr [rcx+69h], 4
0x180056187  jb      short loc_18005619E
0x180056189  mov     rcx, [rcx+60h]
0x18005618d  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180056194  mov     edx, 66h ; 'f'
0x180056199  call    WPP_SF_
0x18005619e  xor     edx, edx; lpSecurityAttributes
0x1800561a0  mov     rcx, rsi; lpPathName
0x1800561a3  call    cs:__imp_CreateDirectoryW
0x1800561a9  test    eax, eax
0x1800561ab  jnz     short loc_1800561EA
0x1800561ad  call    cs:__imp_GetLastError
0x1800561b3  mov     ebx, eax
0x1800561b5  cmp     eax, 0B7h
0x1800561ba  jz      short loc_1800561EA
0x1800561bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800561c3  cmp     rcx, r14
0x1800561c6  jz      loc_18005628A
0x1800561cc  test    byte ptr [rcx+6Ch], 4
0x1800561d0  jz      loc_18005628A
0x1800561d6  cmp     byte ptr [rcx+69h], 1
0x1800561da  jb      loc_18005628A
0x1800561e0  mov     edx, 67h ; 'g'
0x1800561e5  jmp     loc_180056273
0x1800561ea  xor     edi, edi
0x1800561ec  xor     ebx, ebx
0x1800561ee  cmp     edi, 10h
0x1800561f1  jnb     loc_18005628A
0x1800561f7  lea     r8, [rsp+278h+PathName]; unsigned __int16 *
0x1800561fc  mov     edx, edi; unsigned int
0x1800561fe  mov     rcx, rsi; unsigned __int16 *
0x180056201  call    ?GenerateHashSubStorePath@@YAKPEAGK0@Z; GenerateHashSubStorePath(ushort *,ulong,ushort *)
0x180056206  mov     ebx, eax
0x180056208  test    eax, eax
0x18005620a  jnz     short loc_180056256
0x18005620c  xor     edx, edx; lpSecurityAttributes
0x18005620e  lea     rcx, [rsp+278h+PathName]; lpPathName
0x180056213  call    cs:__imp_CreateDirectoryW
0x180056219  test    eax, eax
0x18005621b  jnz     short loc_18005622E
0x18005621d  call    cs:__imp_GetLastError
0x180056223  mov     ebx, eax
0x180056225  cmp     eax, 0B7h
0x18005622a  jnz     short loc_180056232
0x18005622c  xor     ebx, ebx
0x18005622e  inc     edi
0x180056230  jmp     short loc_1800561EE
0x180056232  mov     rcx, cs:WPP_GLOBAL_Control
0x180056239  cmp     rcx, r14
0x18005623c  jz      short loc_18005628A
0x18005623e  test    byte ptr [rcx+6Ch], 4
0x180056242  jz      short loc_18005628A
0x180056244  cmp     byte ptr [rcx+69h], 1
0x180056248  jb      short loc_18005628A
0x18005624a  mov     edx, 69h ; 'i'
0x18005624f  lea     r9, [rsp+278h+PathName]
0x180056254  jmp     short loc_180056276
0x180056256  mov     rcx, cs:WPP_GLOBAL_Control
0x18005625d  cmp     rcx, r14
0x180056260  jz      short loc_18005628A
0x180056262  test    byte ptr [rcx+6Ch], 4
0x180056266  jz      short loc_18005628A
0x180056268  cmp     byte ptr [rcx+69h], 1
0x18005626c  jb      short loc_18005628A
0x18005626e  mov     edx, 68h ; 'h'
0x180056273  mov     r9, rsi
0x180056276  mov     rcx, [rcx+60h]
0x18005627a  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180056281  mov     [rsp+278h+var_258], eax
0x180056285  call    WPP_SF_Sd
0x18005628a  mov     eax, ebx
0x18005628c  mov     rcx, [rsp+278h+var_38]
0x180056294  xor     rcx, rsp; StackCookie
0x180056297  call    __security_check_cookie
0x18005629c  add     rsp, 258h
0x1800562a3  pop     r14
0x1800562a5  pop     rdi
0x1800562a6  pop     rsi
0x1800562a7  pop     rbx
0x1800562a8  retn
```
