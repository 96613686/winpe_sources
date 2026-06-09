# CBrowserBrokerInstance::CopyFavoritesToRedirectedPath(ushort const *,ushort * *)

- ea: `0x180007c50`
- end: `0x180007ce9`
- name: `?CopyFavoritesToRedirectedPath@CBrowserBrokerInstance@@UEAAJPEBGPEAPEAG@Z`
- size: `153`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006c90`
- `0x180007c50`
- `0x18000e428`
- `0x18001baa0`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180007cb2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180007cb2`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180007c9e`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180007c9e`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::CopyFavoritesToRedirectedPath(
        CBrowserBrokerInstance *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int PIC; // ebx
  PWSTR ppszPath; // [rsp+48h] [rbp+20h] BYREF

  LODWORD(ppszPath) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&ppszPath);
  if ( PIC >= 0 )
  {
    ppszPath = 0;
    PIC = SHGetKnownFolderPath(&FOLDERID_Favorites, 0x11000u, 0, &ppszPath);
    if ( PIC >= 0 )
    {
      PIC = SHStrDupW(ppszPath, a3);
      if ( PIC >= 0 )
        PIC = CopyFolderContents(ppszPath, a2);
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&ppszPath);
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180007c50  mov     rax, rsp
0x180007c53  mov     [rax+8], rbx
0x180007c57  mov     [rax+10h], rsi
0x180007c5b  push    rdi
0x180007c5c  sub     rsp, 20h
0x180007c60  mov     rsi, r8
0x180007c63  mov     rdi, rdx
0x180007c66  mov     dword ptr [rax+20h], 0
0x180007c6d  lea     rdx, [rax+20h]; unsigned int *
0x180007c71  mov     ecx, 1; unsigned int
0x180007c76  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180007c7b  mov     ebx, eax
0x180007c7d  test    eax, eax
0x180007c7f  js      short loc_180007CD7
0x180007c81  mov     [rsp+28h+ppszPath], 0
0x180007c8a  lea     r9, [rsp+28h+ppszPath]; ppszPath
0x180007c8f  xor     r8d, r8d; hToken
0x180007c92  mov     edx, 11000h; dwFlags
0x180007c97  lea     rcx, FOLDERID_Favorites; rfid
0x180007c9e  call    cs:__imp_SHGetKnownFolderPath
0x180007ca4  mov     ebx, eax
0x180007ca6  test    eax, eax
0x180007ca8  js      short loc_180007CCD
0x180007caa  mov     rdx, rsi; ppwsz
0x180007cad  mov     rcx, [rsp+28h+ppszPath]; psz
0x180007cb2  call    cs:__imp_SHStrDupW
0x180007cb8  mov     ebx, eax
0x180007cba  test    eax, eax
0x180007cbc  js      short loc_180007CCD
0x180007cbe  mov     rdx, rdi; unsigned __int16 *
0x180007cc1  mov     rcx, [rsp+28h+ppszPath]; unsigned __int16 *
0x180007cc6  call    ?CopyFolderContents@@YAJPEBG0@Z; CopyFolderContents(ushort const *,ushort const *)
0x180007ccb  mov     ebx, eax
0x180007ccd  lea     rcx, [rsp+28h+ppszPath]
0x180007cd2  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180007cd7  mov     eax, ebx
0x180007cd9  mov     rbx, [rsp+28h+arg_0]
0x180007cde  mov     rsi, [rsp+28h+arg_8]
0x180007ce3  add     rsp, 20h
0x180007ce7  pop     rdi
0x180007ce8  retn
```
