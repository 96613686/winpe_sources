# WSZtoSZ(uint,ushort const *,char * *)

- ea: `0x406a93`
- end: `0x406b31`
- name: `?WSZtoSZ@@YGJIPBGPAPAD@Z`
- size: `158`
- prototype: `int __userpurge@<eax>(const WCHAR *@<edx>, CHAR **, const unsigned __int16 *, char **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x403094`
- `0x406e47`
- `0x407142`
- `0x407b9f`

## callees

- `0x406a93`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x406ab8`
- `KERNEL32!WideCharToMultiByte` at `0x406aeb`
- `KERNEL32!WideCharToMultiByte` at `0x406ab8`
- `KERNEL32!WideCharToMultiByte` at `0x406aeb`
- `KERNEL32!GetLastError` at `0x406b09`
- `KERNEL32!GetLastError` at `0x406b09`
- `ole32!CoTaskMemAlloc` at `0x406acd`
- `ole32!CoTaskMemAlloc` at `0x406acd`
- `ole32!CoTaskMemFree` at `0x406b22`
- `ole32!CoTaskMemFree` at `0x406b22`

## pseudocode

```c
int __userpurge WSZtoSZ@<eax>(const WCHAR *a1@<edx>, CHAR **a2, const unsigned __int16 *a3, char **a4)
{
  unsigned int v5; // esi
  CHAR *v6; // edi
  SIZE_T v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // eax
  signed int LastError; // eax

  v5 = -2147024809;
  v6 = 0;
  if ( a1 && a2 )
  {
    v7 = WideCharToMultiByte(0, 0, a1, -1, 0, 0, 0, 0);
    v8 = v7;
    if ( v7 && v7 <= 0x400 )
    {
      v6 = (CHAR *)CoTaskMemAlloc(v7);
      if ( !v6 )
        return -2147024882;
      v9 = WideCharToMultiByte(0, 0, a1, -1, v6, v8, 0, 0);
      if ( v9 && v9 <= v8 && !v6[v9 - 1] )
      {
        v5 = 0;
        *a2 = v6;
        return v5;
      }
    }
    LastError = GetLastError();
    v5 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v5 = LastError;
    if ( v6 )
      CoTaskMemFree(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x406a93  mov     edi, edi
0x406a95  push    ebp
0x406a96  mov     ebp, esp
0x406a98  push    ebx
0x406a99  push    esi
0x406a9a  mov     ebx, edx
0x406a9c  xor     eax, eax
0x406a9e  mov     esi, 80070057h
0x406aa3  push    edi
0x406aa4  mov     edi, eax
0x406aa6  test    ebx, ebx
0x406aa8  jz      short loc_406B28
0x406aaa  cmp     [ebp+arg_0], eax
0x406aad  jz      short loc_406B28
0x406aaf  push    eax; lpUsedDefaultChar
0x406ab0  push    eax; lpDefaultChar
0x406ab1  push    eax; cbMultiByte
0x406ab2  push    eax; lpMultiByteStr
0x406ab3  push    0FFFFFFFFh; cchWideChar
0x406ab5  push    ebx; lpWideCharStr
0x406ab6  push    eax; dwFlags
0x406ab7  push    eax; CodePage
0x406ab8  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x406abe  mov     esi, eax
0x406ac0  test    esi, esi
0x406ac2  jz      short loc_406B09
0x406ac4  cmp     esi, 400h
0x406aca  ja      short loc_406B09
0x406acc  push    esi; cb
0x406acd  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x406ad3  mov     edi, eax
0x406ad5  test    edi, edi
0x406ad7  jnz     short loc_406AE0
0x406ad9  mov     esi, 8007000Eh
0x406ade  jmp     short loc_406B28
0x406ae0  xor     eax, eax
0x406ae2  push    eax; lpUsedDefaultChar
0x406ae3  push    eax; lpDefaultChar
0x406ae4  push    esi; cbMultiByte
0x406ae5  push    edi; lpMultiByteStr
0x406ae6  push    0FFFFFFFFh; cchWideChar
0x406ae8  push    ebx; lpWideCharStr
0x406ae9  push    eax; dwFlags
0x406aea  push    eax; CodePage
0x406aeb  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x406af1  test    eax, eax
0x406af3  jz      short loc_406B09
0x406af5  cmp     eax, esi
0x406af7  ja      short loc_406B09
0x406af9  cmp     byte ptr [edi+eax-1], 0
0x406afe  jnz     short loc_406B09
0x406b00  mov     eax, [ebp+arg_0]
0x406b03  xor     esi, esi
0x406b05  mov     [eax], edi
0x406b07  jmp     short loc_406B28
0x406b09  call    ds:__imp__GetLastError@0; GetLastError()
0x406b0f  movzx   esi, ax
0x406b12  or      esi, 80070000h
0x406b18  test    eax, eax
0x406b1a  cmovle  esi, eax
0x406b1d  test    edi, edi
0x406b1f  jz      short loc_406B28
0x406b21  push    edi; pv
0x406b22  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x406b28  pop     edi
0x406b29  mov     eax, esi
0x406b2b  pop     esi
0x406b2c  pop     ebx
0x406b2d  pop     ebp
0x406b2e  retn    4
```
