# SZtoWSZ(uint,char const *,ushort * *)

- ea: `0x406b37`
- end: `0x406bd4`
- name: `?SZtoWSZ@@YGJIPBDPAPAG@Z`
- size: `157`
- prototype: `int __userpurge@<eax>(const CHAR *@<edx>, WCHAR **, const char *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x40304d`
- `0x405628`
- `0x407142`
- `0x407561`

## callees

- `0x406b37`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x406b5a`
- `KERNEL32!MultiByteToWideChar` at `0x406b8e`
- `KERNEL32!MultiByteToWideChar` at `0x406b5a`
- `KERNEL32!MultiByteToWideChar` at `0x406b8e`
- `KERNEL32!GetLastError` at `0x406bac`
- `KERNEL32!GetLastError` at `0x406bac`
- `ole32!CoTaskMemAlloc` at `0x406b72`
- `ole32!CoTaskMemAlloc` at `0x406b72`
- `ole32!CoTaskMemFree` at `0x406bc5`
- `ole32!CoTaskMemFree` at `0x406bc5`

## pseudocode

```c
int __userpurge SZtoWSZ@<eax>(const CHAR *a1@<edx>, WCHAR **a2, const char *a3, unsigned __int16 **a4)
{
  unsigned int v5; // esi
  WCHAR *v6; // edi
  unsigned int v7; // eax
  unsigned int v8; // esi
  WCHAR *v9; // eax
  unsigned int v10; // eax
  signed int LastError; // eax

  v5 = -2147024809;
  v6 = 0;
  if ( a1 && a2 )
  {
    v7 = MultiByteToWideChar(0, 0, a1, -1, 0, 0);
    v8 = v7;
    if ( v7 && v7 <= 0x400 )
    {
      v9 = (WCHAR *)CoTaskMemAlloc(2 * v7);
      v6 = v9;
      if ( !v9 )
        return -2147024882;
      v10 = MultiByteToWideChar(0, 0, a1, -1, v9, v8);
      if ( v10 && v10 <= v8 && !v6[v10 - 1] )
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
0x406b37  mov     edi, edi
0x406b39  push    ebp
0x406b3a  mov     ebp, esp
0x406b3c  push    ebx
0x406b3d  push    esi
0x406b3e  mov     ebx, edx
0x406b40  xor     eax, eax
0x406b42  mov     esi, 80070057h
0x406b47  push    edi
0x406b48  mov     edi, eax
0x406b4a  test    ebx, ebx
0x406b4c  jz      short loc_406BCB
0x406b4e  cmp     [ebp+arg_0], eax
0x406b51  jz      short loc_406BCB
0x406b53  push    eax; cchWideChar
0x406b54  push    eax; lpWideCharStr
0x406b55  push    0FFFFFFFFh; cbMultiByte
0x406b57  push    ebx; lpMultiByteStr
0x406b58  push    eax; dwFlags
0x406b59  push    eax; CodePage
0x406b5a  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x406b60  mov     esi, eax
0x406b62  test    esi, esi
0x406b64  jz      short loc_406BAC
0x406b66  cmp     esi, 400h
0x406b6c  ja      short loc_406BAC
0x406b6e  lea     eax, [esi+esi]
0x406b71  push    eax; cb
0x406b72  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x406b78  mov     edi, eax
0x406b7a  test    edi, edi
0x406b7c  jnz     short loc_406B85
0x406b7e  mov     esi, 8007000Eh
0x406b83  jmp     short loc_406BCB
0x406b85  push    esi; cchWideChar
0x406b86  push    edi; lpWideCharStr
0x406b87  push    0FFFFFFFFh; cbMultiByte
0x406b89  push    ebx; lpMultiByteStr
0x406b8a  xor     ebx, ebx
0x406b8c  push    ebx; dwFlags
0x406b8d  push    ebx; CodePage
0x406b8e  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x406b94  test    eax, eax
0x406b96  jz      short loc_406BAC
0x406b98  cmp     eax, esi
0x406b9a  ja      short loc_406BAC
0x406b9c  cmp     [edi+eax*2-2], bx
0x406ba1  jnz     short loc_406BAC
0x406ba3  mov     eax, [ebp+arg_0]
0x406ba6  mov     esi, ebx
0x406ba8  mov     [eax], edi
0x406baa  jmp     short loc_406BCB
0x406bac  call    ds:__imp__GetLastError@0; GetLastError()
0x406bb2  movzx   esi, ax
0x406bb5  or      esi, 80070000h
0x406bbb  test    eax, eax
0x406bbd  cmovle  esi, eax
0x406bc0  test    edi, edi
0x406bc2  jz      short loc_406BCB
0x406bc4  push    edi; pv
0x406bc5  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x406bcb  pop     edi
0x406bcc  mov     eax, esi
0x406bce  pop     esi
0x406bcf  pop     ebx
0x406bd0  pop     ebp
0x406bd1  retn    4
```
