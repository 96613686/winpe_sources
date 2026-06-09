# GenInstall(ushort const *,ushort const *,ushort const *)

- ea: `0x18000616c`
- end: `0x180006313`
- name: `?GenInstall@@YAJPEBG00@Z`
- size: `423`
- prototype: `__int64 __fastcall(LPCWSTR lpszLongPath, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180004880`

## callees

- `0x1800017a8`
- `0x180001c48`
- `0x1800022bc`
- `0x18000616c`
- `0x180008a34`
- `0x180008a6c`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000625f`
- `KERNEL32!GetLastError` at `0x18000625f`
- `KERNEL32!FormatMessageW` at `0x18000628c`
- `KERNEL32!FormatMessageW` at `0x18000628c`
- `KERNEL32!GetShortPathNameW` at `0x18000621c`
- `KERNEL32!GetShortPathNameW` at `0x180006232`
- `KERNEL32!GetShortPathNameW` at `0x18000621c`
- `KERNEL32!GetShortPathNameW` at `0x180006232`

## pseudocode

```c
__int64 __fastcall GenInstall(LPCWSTR lpszLongPath, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v4; // ebx
  const WCHAR *v5; // r11
  __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  DWORD LastError; // eax
  WCHAR szLongPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[512]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR szShortPath[264]; // [rsp+650h] [rbp+550h] BYREF

  v4 = StringCchCopyW(szLongPath, 0x104u, a3);
  if ( v4 >= 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( szLongPath[v6] );
    if ( (unsigned int)v6 >= 2 && szLongPath[(unsigned int)(v6 - 2)] != 58 )
    {
      v7 = (unsigned int)(v6 - 1);
      if ( szLongPath[v7] == 92 )
      {
        if ( v7 >= 260 )
          _report_rangecheckfailure(v7 * 2, v6, 520);
        szLongPath[(unsigned int)(v6 - 1)] = 0;
      }
    }
    if ( dword_1800257F8 == 1 )
    {
      memset_0(szShortPath, 0, 0x208u);
      GetShortPathNameW(lpszLongPath, szShortPath, 0x104u);
      GetShortPathNameW(szLongPath, szLongPath, 0x104u);
      return (unsigned int)-2147467259;
    }
    else
    {
      v4 = InstallOnNT(v5, szLongPath);
      if ( v4 < 0 )
      {
        LastError = GetLastError();
        if ( !FormatMessageW(0x1000u, 0, LastError, 0, Buffer, 0x200u, 0) )
        {
          LoadSz(0x490u, Buffer, 0x200u);
          if ( !Buffer[0] )
            StringCchCopyW(Buffer, 0x200u, L"Could not get the system message. You may run out of the resource.");
        }
        MsgBox2Param(hWnd, 0x45Bu, Buffer, 0, 0x10u, 0);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000616c  mov     [rsp-8+arg_18], rbx
0x180006171  push    rbp
0x180006172  push    rsi
0x180006173  push    rdi
0x180006174  lea     rbp, [rsp-770h]
0x18000617c  sub     rsp, 870h
0x180006183  mov     rax, cs:__security_cookie
0x18000618a  xor     rax, rsp
0x18000618d  mov     [rbp+780h+var_20], rax
0x180006194  mov     r11, rdx
0x180006197  mov     rdi, rcx
0x18000619a  mov     edx, 104h; unsigned __int64
0x18000619f  lea     rcx, [rsp+880h+szLongPath]; unsigned __int16 *
0x1800061a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800061a9  xor     esi, esi
0x1800061ab  mov     ebx, eax
0x1800061ad  test    eax, eax
0x1800061af  js      loc_1800062EF
0x1800061b5  lea     rax, [rsp+880h+szLongPath]
0x1800061ba  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800061be  inc     rdx
0x1800061c1  cmp     [rax+rdx*2], si
0x1800061c5  jnz     short loc_1800061BE
0x1800061c7  mov     r8d, 208h; Size
0x1800061cd  cmp     edx, 2
0x1800061d0  jb      short loc_1800061F5
0x1800061d2  lea     eax, [rdx-2]
0x1800061d5  cmp     [rsp+rax*2+880h+szLongPath], 3Ah ; ':'
0x1800061db  jz      short loc_1800061F5
0x1800061dd  lea     ecx, [rdx-1]
0x1800061e0  add     rcx, rcx
0x1800061e3  cmp     [rsp+rcx+880h+szLongPath], 5Ch ; '\'
0x1800061e9  jnz     short loc_1800061F5
0x1800061eb  cmp     rcx, r8
0x1800061ee  jnb     short loc_180006242
0x1800061f0  mov     [rsp+rcx+880h+szLongPath], si
0x1800061f5  cmp     cs:dword_1800257F8, 1
0x1800061fc  jnz     short loc_180006248
0x1800061fe  xor     edx, edx; Val
0x180006200  lea     rcx, [rbp+780h+szShortPath]; void *
0x180006207  call    memset_0
0x18000620c  mov     r8d, 104h; cchBuffer
0x180006212  lea     rdx, [rbp+780h+szShortPath]; lpszShortPath
0x180006219  mov     rcx, rdi; lpszLongPath
0x18000621c  call    cs:__imp_GetShortPathNameW
0x180006222  mov     r8d, 104h; cchBuffer
0x180006228  lea     rdx, [rsp+880h+szLongPath]; lpszShortPath
0x18000622d  lea     rcx, [rsp+880h+szLongPath]; lpszLongPath
0x180006232  call    cs:__imp_GetShortPathNameW
0x180006238  mov     ebx, 80004005h
0x18000623d  jmp     loc_1800062EF
0x180006242  call    __report_rangecheckfailure
0x180006248  lea     rdx, [rsp+880h+szLongPath]; SourceRootPath
0x18000624d  mov     rcx, r11; SectionName
0x180006250  call    ?InstallOnNT@@YAJPEBG0@Z; InstallOnNT(ushort const *,ushort const *)
0x180006255  mov     ebx, eax
0x180006257  test    eax, eax
0x180006259  jns     loc_1800062EF
0x18000625f  call    cs:__imp_GetLastError
0x180006265  mov     [rsp+880h+Arguments], rsi; Arguments
0x18000626a  mov     edi, 200h
0x18000626f  mov     r8d, eax; dwMessageId
0x180006272  mov     [rsp+880h+nSize], edi; nSize
0x180006276  lea     rax, [rbp+780h+Buffer]
0x18000627d  xor     r9d, r9d; dwLanguageId
0x180006280  xor     edx, edx; lpSource
0x180006282  mov     [rsp+880h+lpBuffer], rax; lpBuffer
0x180006287  mov     ecx, 1000h; dwFlags
0x18000628c  call    cs:__imp_FormatMessageW
0x180006292  test    eax, eax
0x180006294  jnz     short loc_1800062C8
0x180006296  mov     r8d, edi; cchBufferMax
0x180006299  lea     rdx, [rbp+780h+Buffer]; lpBuffer
0x1800062a0  mov     ecx, 490h; uID
0x1800062a5  call    ?LoadSz@@YAPEAGIPEAGI@Z; LoadSz(uint,ushort *,uint)
0x1800062aa  cmp     [rbp+780h+Buffer], si
0x1800062b1  jnz     short loc_1800062C8
0x1800062b3  lea     r8, aCouldNotGetThe; "Could not get the system message. You m"...
0x1800062ba  mov     edx, edi; unsigned __int64
0x1800062bc  lea     rcx, [rbp+780h+Buffer]; unsigned __int16 *
0x1800062c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800062c8  mov     rcx, cs:hWnd; hWnd
0x1800062cf  lea     r8, [rbp+780h+Buffer]; unsigned __int16 *
0x1800062d6  mov     [rsp+880h+nSize], esi; unsigned int
0x1800062da  xor     r9d, r9d; unsigned __int16 *
0x1800062dd  mov     edx, 45Bh; uID
0x1800062e2  mov     dword ptr [rsp+880h+lpBuffer], 10h; unsigned int
0x1800062ea  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800062ef  mov     eax, ebx
0x1800062f1  mov     rcx, [rbp+780h+var_20]
0x1800062f8  xor     rcx, rsp; StackCookie
0x1800062fb  call    __security_check_cookie
0x180006300  mov     rbx, [rsp+880h+arg_18]
0x180006308  add     rsp, 870h
0x18000630f  pop     rdi
0x180006310  pop     rsi
0x180006311  pop     rbp
0x180006312  retn
```
