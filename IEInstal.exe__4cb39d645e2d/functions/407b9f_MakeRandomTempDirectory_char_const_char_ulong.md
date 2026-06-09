# MakeRandomTempDirectory(char const *,char *,ulong)

- ea: `0x407b9f`
- end: `0x407c36`
- name: `?MakeRandomTempDirectory@@YGJPBDPADK@Z`
- size: `151`
- prototype: `int __userpurge@<eax>(char *@<edx>, const char *@<ecx>, const char *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x407c3c`

## callees

- `0x4064be`
- `0x406a93`
- `0x406bda`
- `0x407b9f`

## import_xrefs

- `KERNEL32!CreateDirectoryExA` at `0x407c06`
- `KERNEL32!CreateDirectoryExA` at `0x407c06`
- `KERNEL32!GetLastError` at `0x407c10`
- `KERNEL32!GetLastError` at `0x407c10`
- `ole32!CoTaskMemFree` at `0x407bf8`
- `ole32!CoTaskMemFree` at `0x407bf8`
- `OLEAUT32!__imp__SysFreeString@4` at `0x407c27`
- `OLEAUT32!__imp__SysFreeString@4` at `0x407c27`

## pseudocode

```c
int __userpurge MakeRandomTempDirectory@<eax>(
        char *a1@<edx>,
        const char *a2@<ecx>,
        const char *a3,
        char *a4,
        unsigned int a5)
{
  signed int v7; // esi
  signed int LastError; // eax
  const unsigned __int16 *v10; // [esp+0h] [ebp-14h]
  char **v11; // [esp+4h] [ebp-10h]
  BSTR bstrString; // [esp+Ch] [ebp-8h] BYREF
  LPVOID pv; // [esp+10h] [ebp-4h] BYREF

  bstrString = 0;
  v7 = -2147467259;
  if ( CreateUuidString(&bstrString) >= 0 )
  {
    pv = 0;
    if ( WSZtoSZ((unsigned int)&pv, v10, v11) >= 0 )
    {
      v7 = StringCchPrintfA(a1, 0x104u, "%s%s", a2, (const char *)pv);
      CoTaskMemFree(pv);
      if ( v7 >= 0 && !CreateDirectoryExA(a2, a1, 0) )
      {
        LastError = GetLastError();
        v7 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v7 = LastError;
      }
    }
    SysFreeString(bstrString);
  }
  return v7;
}

```

## disassembly

```asm
0x407b9f  mov     edi, edi
0x407ba1  push    ebp
0x407ba2  mov     ebp, esp
0x407ba4  push    ecx
0x407ba5  push    ecx
0x407ba6  push    ebx
0x407ba7  push    esi; char **
0x407ba8  mov     ebx, ecx
0x407baa  mov     [ebp+bstrString], 0
0x407bb1  push    edi; unsigned __int16 *
0x407bb2  lea     ecx, [ebp+bstrString]
0x407bb5  mov     edi, edx
0x407bb7  mov     esi, 80004005h
0x407bbc  call    ?CreateUuidString@@YGJPAPAG@Z; CreateUuidString(ushort * *)
0x407bc1  test    eax, eax
0x407bc3  js      short loc_407C2D
0x407bc5  mov     edx, [ebp+bstrString]
0x407bc8  lea     eax, [ebp+pv]
0x407bcb  push    eax; unsigned int
0x407bcc  mov     [ebp+pv], 0
0x407bd3  call    ?WSZtoSZ@@YGJIPBGPAPAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x407bd8  test    eax, eax
0x407bda  js      short loc_407C24
0x407bdc  push    [ebp+pv]
0x407bdf  push    ebx
0x407be0  push    offset aSS_0; "%s%s"
0x407be5  push    104h; unsigned int
0x407bea  push    edi; Buffer
0x407beb  call    ?StringCchPrintfA@@YAJPADIPBDZZ; StringCchPrintfA(char *,uint,char const *,...)
0x407bf0  add     esp, 14h
0x407bf3  mov     esi, eax
0x407bf5  push    [ebp+pv]; pv
0x407bf8  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x407bfe  test    esi, esi
0x407c00  js      short loc_407C24
0x407c02  push    0; lpSecurityAttributes
0x407c04  push    edi; lpNewDirectory
0x407c05  push    ebx; lpTemplateDirectory
0x407c06  call    ds:__imp__CreateDirectoryExA@12; CreateDirectoryExA(x,x,x)
0x407c0c  test    eax, eax
0x407c0e  jnz     short loc_407C24
0x407c10  call    ds:__imp__GetLastError@0; GetLastError()
0x407c16  movzx   esi, ax
0x407c19  or      esi, 80070000h
0x407c1f  test    eax, eax
0x407c21  cmovle  esi, eax
0x407c24  push    [ebp+bstrString]; bstrString
0x407c27  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x407c2d  pop     edi
0x407c2e  mov     eax, esi
0x407c30  pop     esi
0x407c31  pop     ebx
0x407c32  leave
0x407c33  retn    4
```
