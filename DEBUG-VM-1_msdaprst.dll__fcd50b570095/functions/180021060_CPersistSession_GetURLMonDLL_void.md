# CPersistSession::GetURLMonDLL(void)

- ea: `0x180021060`
- end: `0x180021108`
- name: `?GetURLMonDLL@CPersistSession@@AEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(CPersistSession *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021680`
- `0x180022108`

## callees

- `0x180021060`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800210af`
- `KERNEL32!GetProcAddress` at `0x1800210cb`
- `KERNEL32!GetProcAddress` at `0x1800210e7`
- `KERNEL32!GetProcAddress` at `0x1800210af`
- `KERNEL32!GetProcAddress` at `0x1800210cb`
- `KERNEL32!GetProcAddress` at `0x1800210e7`
- `KERNEL32!GetLastError` at `0x180021091`
- `KERNEL32!GetLastError` at `0x180021091`
- `KERNEL32!LoadLibraryExW` at `0x180021083`
- `KERNEL32!LoadLibraryExW` at `0x180021083`

## string_xrefs

- `0x180021076`: `urlmon.dll`
- `0x1800210c1`: `CreateURLMoniker`
- `0x1800210dd`: `CreateAsyncBindCtx`

## pseudocode

```c
signed int __fastcall CPersistSession::GetURLMonDLL(CPersistSession *this)
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed int result; // eax

  if ( CPersistSession::m_hURLMON )
    return 0;
  Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    CPersistSession::m_pIsValidURL = (int (*)(struct IBindCtx *, const unsigned __int16 *, unsigned int))GetProcAddress(Library, "IsValidURL");
    if ( CPersistSession::m_pIsValidURL )
    {
      CPersistSession::m_pCreateURLMoniker = (int (*)(struct IMoniker *, unsigned __int16 *, struct IMoniker **))GetProcAddress(v2, "CreateURLMoniker");
      if ( CPersistSession::m_pCreateURLMoniker )
      {
        CPersistSession::m_pCreateAsyncBindCtx = (int (*)(unsigned int, struct IBindStatusCallback *, struct IEnumFORMATETC *, struct IBindCtx **))GetProcAddress(v2, "CreateAsyncBindCtx");
        if ( CPersistSession::m_pCreateAsyncBindCtx )
        {
          CPersistSession::m_hURLMON = v2;
          return 0;
        }
      }
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180021060  push    rbx
0x180021062  sub     rsp, 20h
0x180021066  cmp     cs:?m_hURLMON@CPersistSession@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CPersistSession::m_hURLMON
0x18002106e  jnz     loc_180021100
0x180021074  xor     edx, edx; hFile
0x180021076  lea     rcx, aUrlmonDll; "urlmon.dll"
0x18002107d  mov     r8d, 800h; dwFlags
0x180021083  call    cs:__imp_LoadLibraryExW
0x180021089  mov     rbx, rax
0x18002108c  test    rax, rax
0x18002108f  jnz     short loc_1800210A5
0x180021091  call    cs:__imp_GetLastError
0x180021097  test    eax, eax
0x180021099  jle     short loc_180021102
0x18002109b  movzx   eax, ax
0x18002109e  or      eax, 80070000h
0x1800210a3  jmp     short loc_180021102
0x1800210a5  lea     rdx, aIsvalidurl; "IsValidURL"
0x1800210ac  mov     rcx, rbx; hModule
0x1800210af  call    cs:__imp_GetProcAddress
0x1800210b5  mov     cs:?m_pIsValidURL@CPersistSession@@0P6AJPEAUIBindCtx@@PEBGK@ZEA, rax; long (*CPersistSession::m_pIsValidURL)(IBindCtx *,ushort const *,ulong)
0x1800210bc  test    rax, rax
0x1800210bf  jz      short loc_180021091
0x1800210c1  lea     rdx, aCreateurlmonik; "CreateURLMoniker"
0x1800210c8  mov     rcx, rbx; hModule
0x1800210cb  call    cs:__imp_GetProcAddress
0x1800210d1  mov     cs:?m_pCreateURLMoniker@CPersistSession@@0P6AJPEAUIMoniker@@PEAGPEAPEAU2@@ZEA, rax; long (*CPersistSession::m_pCreateURLMoniker)(IMoniker *,ushort *,IMoniker * *)
0x1800210d8  test    rax, rax
0x1800210db  jz      short loc_180021091
0x1800210dd  lea     rdx, aCreateasyncbin; "CreateAsyncBindCtx"
0x1800210e4  mov     rcx, rbx; hModule
0x1800210e7  call    cs:__imp_GetProcAddress
0x1800210ed  mov     cs:?m_pCreateAsyncBindCtx@CPersistSession@@0P6AJKPEAUIBindStatusCallback@@PEAUIEnumFORMATETC@@PEAPEAUIBindCtx@@@ZEA, rax; long (*CPersistSession::m_pCreateAsyncBindCtx)(ulong,IBindStatusCallback *,IEnumFORMATETC *,IBindCtx * *)
0x1800210f4  test    rax, rax
0x1800210f7  jz      short loc_180021091
0x1800210f9  mov     cs:?m_hURLMON@CPersistSession@@0PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * CPersistSession::m_hURLMON
0x180021100  xor     eax, eax
0x180021102  add     rsp, 20h
0x180021106  pop     rbx
0x180021107  retn
```
