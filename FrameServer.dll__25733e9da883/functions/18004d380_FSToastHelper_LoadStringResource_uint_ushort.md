# FSToastHelper::LoadStringResource(uint,ushort * *)

- ea: `0x18004d380`
- end: `0x18004d494`
- name: `?LoadStringResource@FSToastHelper@@CAJIPEAPEAG@Z`
- size: `276`
- prototype: `__int64 __fastcall(UINT uID, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004d564`

## callees

- `0x180009608`
- `0x18004d380`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004d3c9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004d43a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004d3c9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004d43a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d3d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d3d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d444`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d40a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d40a`

## pseudocode

```c
__int64 __fastcall FSToastHelper::LoadStringResource(UINT uID, unsigned __int16 **a2)
{
  signed int v4; // ebx
  __int64 v5; // rdx
  int StringW; // ebp
  signed int LastError; // eax
  int v8; // ebp
  unsigned __int16 *v9; // rax
  signed int v10; // eax
  __int64 Buffer; // [rsp+68h] [rbp+10h] BYREF

  Buffer = 0;
  if ( a2 )
  {
    v4 = 0;
    StringW = LoadStringW(&_ImageBase, uID, (LPWSTR)&Buffer, 0);
    if ( StringW > 0 )
      goto LABEL_10;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_10:
      v8 = StringW + 1;
      v9 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v8);
      *a2 = v9;
      if ( v9 )
      {
        if ( LoadStringW(&_ImageBase, uID, v9, v8) <= 0 )
        {
          v10 = GetLastError();
          v4 = v10;
          if ( v10 > 0 )
            v4 = (unsigned __int16)v10 | 0x80070000;
          if ( v4 < 0 && g_wppLevels )
          {
            v5 = 13;
            goto LABEL_19;
          }
        }
      }
      else
      {
        v4 = -2147024882;
        if ( g_wppLevels )
        {
          v5 = 12;
          goto LABEL_19;
        }
      }
    }
    else if ( g_wppLevels )
    {
      v5 = 11;
      goto LABEL_19;
    }
  }
  else
  {
    v4 = -2147024809;
    if ( g_wppLevels )
    {
      v5 = 10;
LABEL_19:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_95fbd6b376ad3cce955e1a6deddee8d6_Traceguids, 0, v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004d380  push    rbx
0x18004d382  push    rbp
0x18004d383  push    rsi
0x18004d384  push    rdi
0x18004d385  sub     rsp, 38h
0x18004d389  mov     [rsp+58h+Buffer], 0
0x18004d392  mov     rdi, rdx
0x18004d395  mov     esi, ecx
0x18004d397  test    rdx, rdx
0x18004d39a  jnz     short loc_18004D3B6
0x18004d39c  mov     ebx, 80070057h
0x18004d3a1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d3a8  jb      loc_18004D489
0x18004d3ae  lea     edx, [rdi+0Ah]
0x18004d3b1  jmp     loc_18004D46B
0x18004d3b6  xor     r9d, r9d; cchBufferMax
0x18004d3b9  lea     r8, [rsp+58h+Buffer]; lpBuffer
0x18004d3be  mov     edx, esi; uID
0x18004d3c0  lea     rcx, __ImageBase; hInstance
0x18004d3c7  xor     ebx, ebx
0x18004d3c9  call    cs:__imp_LoadStringW
0x18004d3cf  mov     ebp, eax
0x18004d3d1  test    eax, eax
0x18004d3d3  jg      short loc_18004D402
0x18004d3d5  call    cs:__imp_GetLastError
0x18004d3db  mov     ebx, eax
0x18004d3dd  test    eax, eax
0x18004d3df  jle     short loc_18004D3EA
0x18004d3e1  movzx   ebx, ax
0x18004d3e4  or      ebx, 80070000h
0x18004d3ea  test    ebx, ebx
0x18004d3ec  jns     short loc_18004D402
0x18004d3ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d3f5  jb      loc_18004D489
0x18004d3fb  mov     edx, 0Bh
0x18004d400  jmp     short loc_18004D46B
0x18004d402  inc     ebp
0x18004d404  movsxd  rcx, ebp
0x18004d407  add     rcx, rcx; cb
0x18004d40a  call    cs:__imp_CoTaskMemAlloc
0x18004d410  mov     [rdi], rax
0x18004d413  test    rax, rax
0x18004d416  jnz     short loc_18004D42B
0x18004d418  mov     ebx, 8007000Eh
0x18004d41d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d424  jb      short loc_18004D489
0x18004d426  lea     edx, [rax+0Ch]
0x18004d429  jmp     short loc_18004D46B
0x18004d42b  mov     r9d, ebp; cchBufferMax
0x18004d42e  lea     rcx, __ImageBase; hInstance
0x18004d435  mov     r8, rax; lpBuffer
0x18004d438  mov     edx, esi; uID
0x18004d43a  call    cs:__imp_LoadStringW
0x18004d440  test    eax, eax
0x18004d442  jg      short loc_18004D489
0x18004d444  call    cs:__imp_GetLastError
0x18004d44a  mov     ebx, eax
0x18004d44c  test    eax, eax
0x18004d44e  jle     short loc_18004D459
0x18004d450  movzx   ebx, ax
0x18004d453  or      ebx, 80070000h
0x18004d459  test    ebx, ebx
0x18004d45b  jns     short loc_18004D489
0x18004d45d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d464  jb      short loc_18004D489
0x18004d466  mov     edx, 0Dh
0x18004d46b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d472  lea     r8, WPP_95fbd6b376ad3cce955e1a6deddee8d6_Traceguids
0x18004d479  xor     r9d, r9d
0x18004d47c  mov     [rsp+58h+var_38], ebx
0x18004d480  mov     rcx, [rcx+10h]
0x18004d484  call    WPP_SF_qD
0x18004d489  mov     eax, ebx
0x18004d48b  add     rsp, 38h
0x18004d48f  pop     rdi
0x18004d490  pop     rsi
0x18004d491  pop     rbp
0x18004d492  pop     rbx
0x18004d493  retn
```
