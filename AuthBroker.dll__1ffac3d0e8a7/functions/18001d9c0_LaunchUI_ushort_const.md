# LaunchUI(ushort const *)

- ea: `0x18001d9c0`
- end: `0x18001db4c`
- name: `?LaunchUI@@YAXPEBG@Z`
- size: `396`
- prototype: `void __fastcall(const wchar_t *url)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800130f0`

## callees

- `0x18000737c`
- `0x180011b30`
- `0x18001d9c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001daac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001daac`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001daa1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001daa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db05`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18001da0e`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18001da0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dafa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dafa`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001da36`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001da36`

## pseudocode

```c
void __fastcall LaunchUI(const wchar_t *url)
{
  unsigned __int64 v2; // rax
  HRESULT v3; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  PARSEDURLW ppu; // [rsp+30h] [rbp-38h] BYREF
  wchar_t *threadUrl; // [rsp+78h] [rbp+10h] BYREF

  threadUrl = 0;
  v2 = -1;
  do
    ++v2;
  while ( url[v2] );
  if ( v2 <= 0x4000
    && (memset(&ppu, 0, sizeof(ppu)), ppu.cbSize = 40, ParseURLW(url, &ppu) >= 0)
    && (ppu.nScheme == 2 || ppu.nScheme == 11) )
  {
    v3 = SHStrDupW(url, &threadUrl);
    if ( v3 >= 0 )
    {
      Thread = CreateThread(0, 0, LaunchUIThreadProc, threadUrl, 0, 0);
      if ( Thread )
      {
        CloseHandle(Thread);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 2) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Control.Logger,
            0x11u,
            WPP_5c25b29c16823e432c896bdd05006b28_Traceguids,
            LastError);
        }
        CoTaskMemFree(threadUrl);
      }
    }
    else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
           && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 2) != 0
           && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x10u, WPP_5c25b29c16823e432c896bdd05006b28_Traceguids, v3);
    }
  }
  else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
         && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 2) != 0
         && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0xFu, WPP_5c25b29c16823e432c896bdd05006b28_Traceguids);
  }
}

```

## disassembly

```asm
0x18001d9c0  mov     [rsp+arg_0], rbx
0x18001d9c5  push    rsi
0x18001d9c6  sub     rsp, 60h
0x18001d9ca  xor     esi, esi
0x18001d9cc  mov     rbx, url
0x18001d9cf  mov     [rsp+68h+threadUrl], rsi
0x18001d9d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d9d8  inc     rax
0x18001d9db  cmp     [url+rax*2], si
0x18001d9df  jnz     short loc_18001D9D8
0x18001d9e1  cmp     rax, 4000h
0x18001d9e7  ja      loc_18001DB0D
0x18001d9ed  xorps   xmm0, xmm0
0x18001d9f0  lea     rdx, [rsp+68h+ppu]; ppu
0x18001d9f5  xor     eax, eax
0x18001d9f7  movups  xmmword ptr [rsp+68h+ppu.cbSize], xmm0
0x18001d9fc  mov     [rsp+68h+ppu.cbSize], 28h ; '('
0x18001da04  movups  xmmword ptr [rsp+68h+ppu.cchProtocol], xmm0
0x18001da09  mov     qword ptr [rsp+68h+ppu.cchSuffix], rax
0x18001da0e  call    cs:__imp_ParseURLW
0x18001da14  test    eax, eax
0x18001da16  js      loc_18001DB0D
0x18001da1c  cmp     [rsp+68h+ppu.nScheme], 2
0x18001da21  jz      short loc_18001DA2E
0x18001da23  cmp     [rsp+68h+ppu.nScheme], 0Bh
0x18001da28  jnz     loc_18001DB0D
0x18001da2e  lea     rdx, [rsp+68h+threadUrl]; ppwsz
0x18001da33  mov     url, rbx; psz
0x18001da36  call    cs:__imp_SHStrDupW
0x18001da3c  test    eax, eax
0x18001da3e  jns     short loc_18001DA88
0x18001da40  mov     url, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001da47  lea     rdx, WPP_GLOBAL_Control
0x18001da4e  cmp     url, rdx
0x18001da51  jz      loc_18001DB41
0x18001da57  test    byte ptr [url+44h], 2
0x18001da5b  jz      loc_18001DB41
0x18001da61  cmp     byte ptr [url+41h], 2
0x18001da65  jb      loc_18001DB41
0x18001da6b  mov     url, [url+38h]; Logger
0x18001da6f  lea     r8, WPP_5c25b29c16823e432c896bdd05006b28_Traceguids; TraceGuid
0x18001da76  mov     edx, 10h; id
0x18001da7b  mov     r9d, eax; _a1
0x18001da7e  call    WPP_SF_d
0x18001da83  jmp     loc_18001DB41
0x18001da88  mov     r9, [rsp+68h+threadUrl]; lpParameter
0x18001da8d  lea     r8, _LaunchUIThreadProc; lpStartAddress
0x18001da94  mov     [rsp+68h+lpThreadId], rsi; lpThreadId
0x18001da99  xor     edx, edx; dwStackSize
0x18001da9b  xor     ecx, ecx; lpThreadAttributes
0x18001da9d  mov     [rsp+68h+dwCreationFlags], esi; dwCreationFlags
0x18001daa1  call    cs:__imp_CreateThread
0x18001daa7  test    rax, rax
0x18001daaa  jnz     short loc_18001DB02
0x18001daac  call    cs:__imp_GetLastError
0x18001dab2  test    eax, eax
0x18001dab4  jle     short loc_18001DABE
0x18001dab6  movzx   eax, ax
0x18001dab9  or      eax, 80070000h
0x18001dabe  mov     url, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001dac5  lea     rdx, WPP_GLOBAL_Control
0x18001dacc  cmp     url, rdx
0x18001dacf  jz      short loc_18001DAF5
0x18001dad1  test    byte ptr [url+44h], 2
0x18001dad5  jz      short loc_18001DAF5
0x18001dad7  cmp     byte ptr [url+41h], 2
0x18001dadb  jb      short loc_18001DAF5
0x18001dadd  mov     url, [url+38h]; Logger
0x18001dae1  lea     r8, WPP_5c25b29c16823e432c896bdd05006b28_Traceguids; TraceGuid
0x18001dae8  mov     edx, 11h; id
0x18001daed  mov     r9d, eax; _a1
0x18001daf0  call    WPP_SF_d
0x18001daf5  mov     url, [rsp+68h+threadUrl]; pv
0x18001dafa  call    cs:__imp_CoTaskMemFree
0x18001db00  jmp     short loc_18001DB41
0x18001db02  mov     url, rax; hObject
0x18001db05  call    cs:__imp_CloseHandle
0x18001db0b  jmp     short loc_18001DB41
0x18001db0d  mov     url, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001db14  lea     rdx, WPP_GLOBAL_Control
0x18001db1b  cmp     url, rdx
0x18001db1e  jz      short loc_18001DB41
0x18001db20  test    byte ptr [url+44h], 2
0x18001db24  jz      short loc_18001DB41
0x18001db26  cmp     byte ptr [url+41h], 2
0x18001db2a  jb      short loc_18001DB41
0x18001db2c  mov     url, [url+38h]; Logger
0x18001db30  lea     r8, WPP_5c25b29c16823e432c896bdd05006b28_Traceguids; TraceGuid
0x18001db37  mov     edx, 0Fh; id
0x18001db3c  call    WPP_SF_
0x18001db41  mov     rbx, [rsp+68h+arg_0]
0x18001db46  add     rsp, 60h
0x18001db4a  pop     rsi
0x18001db4b  retn
```
