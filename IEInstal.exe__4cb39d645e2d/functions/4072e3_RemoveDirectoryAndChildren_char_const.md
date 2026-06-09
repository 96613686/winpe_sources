# RemoveDirectoryAndChildren(char const *)

- ea: `0x4072e3`
- end: `0x4074c9`
- name: `?RemoveDirectoryAndChildren@@YGJPBD@Z`
- size: `486`
- prototype: `int __thiscall(const char *this)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x402f16`
- `0x40373b`
- `0x405849`
- `0x4072e3`
- `0x407fd4`

## callees

- `0x406224`
- `0x40646b`
- `0x4064be`
- `0x4072e3`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `KERNEL32!SetFileAttributesA` at `0x407418`
- `KERNEL32!SetFileAttributesA` at `0x407438`
- `KERNEL32!SetFileAttributesA` at `0x407418`
- `KERNEL32!SetFileAttributesA` at `0x407438`
- `KERNEL32!FindFirstFileA` at `0x4073a1`
- `KERNEL32!FindFirstFileA` at `0x4073a1`
- `KERNEL32!FindNextFileA` at `0x407456`
- `KERNEL32!FindNextFileA` at `0x407456`
- `KERNEL32!FindClose` at `0x407484`
- `KERNEL32!FindClose` at `0x40748d`
- `KERNEL32!FindClose` at `0x407484`
- `KERNEL32!FindClose` at `0x40748d`
- `KERNEL32!lstrcmpA` at `0x4073bc`
- `KERNEL32!lstrcmpA` at `0x4073d4`
- `KERNEL32!lstrcmpA` at `0x4073bc`
- `KERNEL32!lstrcmpA` at `0x4073d4`
- `KERNEL32!RemoveDirectoryA` at `0x407336`
- `KERNEL32!RemoveDirectoryA` at `0x407494`
- `KERNEL32!RemoveDirectoryA` at `0x407336`
- `KERNEL32!RemoveDirectoryA` at `0x407494`
- `KERNEL32!DeleteFileA` at `0x407446`
- `KERNEL32!DeleteFileA` at `0x407446`
- `KERNEL32!GetLastError` at `0x407464`
- `KERNEL32!GetLastError` at `0x40746f`
- `KERNEL32!GetLastError` at `0x40749e`
- `KERNEL32!GetLastError` at `0x407464`
- `KERNEL32!GetLastError` at `0x40746f`
- `KERNEL32!GetLastError` at `0x40749e`

## pseudocode

```c
int __thiscall RemoveDirectoryAndChildren(const char *this)
{
  signed int v1; // esi
  HANDLE FirstFileA; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  const char *v7; // [esp+0h] [ebp-260h]
  _WIN32_FIND_DATAA FindFileData; // [esp+10h] [ebp-250h] BYREF
  CHAR PathName[268]; // [esp+150h] [ebp-110h] BYREF

  v1 = 0;
  memset(PathName, 0, 260);
  if ( this )
  {
    if ( *this )
    {
      if ( !RemoveDirectoryA(this) )
      {
        v1 = StringCchCopyA(PathName, 0x104u, (size_t)this);
        if ( v1 >= 0 )
        {
          v1 = StringCchCatA(PathName, 260 - strlen(PathName), "\\*");
          if ( v1 >= 0 )
          {
            FirstFileA = FindFirstFileA(PathName, &FindFileData);
            if ( FirstFileA == (HANDLE)-1 )
              goto LABEL_20;
            do
            {
              if ( lstrcmpA(FindFileData.cFileName, ".") && lstrcmpA(FindFileData.cFileName, "..") )
              {
                v1 = StringCchPrintfA(PathName, 0x103u, "%s\\%s", this, FindFileData.cFileName);
                if ( v1 < 0 )
                  goto LABEL_18;
                if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
                  SetFileAttributesA(PathName, 0x90u);
                  v1 = RemoveDirectoryAndChildren(v7);
                  if ( v1 < 0 )
                    goto LABEL_18;
                }
                else
                {
                  SetFileAttributesA(PathName, 0x80u);
                  if ( !DeleteFileA(PathName) )
                    goto LABEL_16;
                }
              }
            }
            while ( FindNextFileA(FirstFileA, &FindFileData) );
            if ( GetLastError() != 18 )
            {
LABEL_16:
              LastError = GetLastError();
              v1 = (unsigned __int16)LastError | 0x80070000;
              if ( LastError <= 0 )
                v1 = LastError;
LABEL_18:
              FindClose(FirstFileA);
              return v1;
            }
            FindClose(FirstFileA);
            if ( !RemoveDirectoryA(this) )
            {
LABEL_20:
              v5 = GetLastError();
              v1 = (unsigned __int16)v5 | 0x80070000;
              if ( v5 <= 0 )
                return v5;
            }
          }
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x4072e3  mov     edi, edi
0x4072e5  push    ebp
0x4072e6  mov     ebp, esp
0x4072e8  and     esp, 0FFFFFFF8h
0x4072eb  sub     esp, 254h
0x4072f1  mov     eax, ___security_cookie
0x4072f6  xor     eax, esp
0x4072f8  mov     [esp+254h+var_4], eax
0x4072ff  push    ebx
0x407300  push    esi
0x407301  push    edi; char *
0x407302  push    103h; Size
0x407307  xor     esi, esi
0x407309  mov     [esp+264h+PathName], 0
0x407311  lea     eax, [esp+264h+var_10F]
0x407318  mov     edi, ecx
0x40731a  push    esi; Val
0x40731b  push    eax; void *
0x40731c  call    _memset
0x407321  add     esp, 0Ch
0x407324  test    edi, edi
0x407326  jz      loc_4074B2
0x40732c  cmp     byte ptr [edi], 0
0x40732f  jz      loc_4074B2
0x407335  push    edi; lpPathName
0x407336  call    ds:__imp__RemoveDirectoryA@4; RemoveDirectoryA(x)
0x40733c  test    eax, eax
0x40733e  jnz     loc_4074B2
0x407344  push    edi; cchDest
0x407345  mov     ebx, 104h
0x40734a  lea     eax, [esp+264h+PathName]
0x407351  push    ebx; unsigned int
0x407352  push    eax; char *
0x407353  call    ?StringCchCopyA@@YGJPADIPBD@Z; StringCchCopyA(char *,uint,char const *)
0x407358  mov     esi, eax
0x40735a  test    esi, esi
0x40735c  js      loc_4074B2
0x407362  lea     ecx, [esp+260h+PathName]
0x407369  lea     edx, [ecx+1]
0x40736c  mov     al, [ecx]
0x40736e  inc     ecx
0x40736f  test    al, al
0x407371  jnz     short loc_40736C
0x407373  sub     ecx, edx
0x407375  lea     eax, [esp+260h+PathName]
0x40737c  push    offset asc_4019EC; "\\*"
0x407381  sub     ebx, ecx
0x407383  push    ebx; unsigned int
0x407384  push    eax; char *
0x407385  call    ?StringCchCatA@@YGJPADIPBD@Z; StringCchCatA(char *,uint,char const *)
0x40738a  mov     esi, eax
0x40738c  test    esi, esi
0x40738e  js      loc_4074B2
0x407394  lea     eax, [esp+260h+FindFileData]
0x407398  push    eax; lpFindFileData
0x407399  lea     eax, [esp+264h+PathName]
0x4073a0  push    eax; lpFileName
0x4073a1  call    ds:__imp__FindFirstFileA@8; FindFirstFileA(x,x)
0x4073a7  mov     ebx, eax
0x4073a9  cmp     ebx, 0FFFFFFFFh
0x4073ac  jz      loc_40749E
0x4073b2  push    offset String2; "."
0x4073b7  lea     eax, [esp+264h+FindFileData.cFileName]
0x4073bb  push    eax; lpString1
0x4073bc  call    ds:__imp__lstrcmpA@8; lstrcmpA(x,x)
0x4073c2  test    eax, eax
0x4073c4  jz      loc_407450
0x4073ca  push    offset asc_4019F4; ".."
0x4073cf  lea     eax, [esp+264h+FindFileData.cFileName]
0x4073d3  push    eax; lpString1
0x4073d4  call    ds:__imp__lstrcmpA@8; lstrcmpA(x,x)
0x4073da  test    eax, eax
0x4073dc  jz      short loc_407450
0x4073de  lea     eax, [esp+260h+FindFileData.cFileName]
0x4073e2  push    eax
0x4073e3  push    edi
0x4073e4  push    offset aSS_1; "%s\\%s"
0x4073e9  lea     eax, [esp+26Ch+PathName]
0x4073f0  push    103h; unsigned int
0x4073f5  push    eax; Buffer
0x4073f6  call    ?StringCchPrintfA@@YAJPADIPBDZZ; StringCchPrintfA(char *,uint,char const *,...)
0x4073fb  mov     esi, eax
0x4073fd  add     esp, 14h
0x407400  test    esi, esi
0x407402  js      short loc_407483
0x407404  test    byte ptr [esp+260h+FindFileData.dwFileAttributes], 10h
0x407409  lea     eax, [esp+260h+PathName]
0x407410  jz      short loc_407432
0x407412  push    90h; dwFileAttributes
0x407417  push    eax; lpFileName
0x407418  call    ds:__imp__SetFileAttributesA@8; SetFileAttributesA(x,x)
0x40741e  lea     ecx, [esp+260h+PathName]
0x407425  call    ?RemoveDirectoryAndChildren@@YGJPBD@Z; RemoveDirectoryAndChildren(char const *)
0x40742a  mov     esi, eax
0x40742c  test    esi, esi
0x40742e  js      short loc_407483
0x407430  jmp     short loc_407450
0x407432  push    80h; dwFileAttributes
0x407437  push    eax; lpFileName
0x407438  call    ds:__imp__SetFileAttributesA@8; SetFileAttributesA(x,x)
0x40743e  lea     eax, [esp+260h+PathName]
0x407445  push    eax; lpFileName
0x407446  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x40744c  test    eax, eax
0x40744e  jz      short loc_40746F
0x407450  lea     eax, [esp+260h+FindFileData]
0x407454  push    eax; lpFindFileData
0x407455  push    ebx; hFindFile
0x407456  call    ds:__imp__FindNextFileA@8; FindNextFileA(x,x)
0x40745c  test    eax, eax
0x40745e  jnz     loc_4073B2
0x407464  call    ds:__imp__GetLastError@0; GetLastError()
0x40746a  cmp     eax, 12h
0x40746d  jz      short loc_40748C
0x40746f  call    ds:__imp__GetLastError@0; GetLastError()
0x407475  movzx   esi, ax
0x407478  or      esi, 80070000h
0x40747e  test    eax, eax
0x407480  cmovle  esi, eax
0x407483  push    ebx; hFindFile
0x407484  call    ds:__imp__FindClose@4; FindClose(x)
0x40748a  jmp     short loc_4074B2
0x40748c  push    ebx; hFindFile
0x40748d  call    ds:__imp__FindClose@4; FindClose(x)
0x407493  push    edi; lpPathName
0x407494  call    ds:__imp__RemoveDirectoryA@4; RemoveDirectoryA(x)
0x40749a  test    eax, eax
0x40749c  jnz     short loc_4074B2
0x40749e  call    ds:__imp__GetLastError@0; GetLastError()
0x4074a4  movzx   esi, ax
0x4074a7  or      esi, 80070000h
0x4074ad  test    eax, eax
0x4074af  cmovle  esi, eax
0x4074b2  mov     ecx, [esp+260h+var_4]
0x4074b9  mov     eax, esi
0x4074bb  pop     edi
0x4074bc  pop     esi
0x4074bd  pop     ebx
0x4074be  xor     ecx, esp; StackCookie
0x4074c0  call    @__security_check_cookie@4; __security_check_cookie(x)
0x4074c5  mov     esp, ebp
0x4074c7  pop     ebp
0x4074c8  retn
```
