# CFDRPlugin::SignalFlush(void)

- ea: `0x140057b3c`
- end: `0x140057cff`
- name: `?SignalFlush@CFDRPlugin@@AEAAJXZ`
- size: `451`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1400571c0`

## callees

- `0x140002748`
- `0x14000b580`
- `0x14000e658`
- `0x140014ee4`
- `0x140057b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140057c08`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140057c08`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140057c90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140057c90`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140057c58`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140057c58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057ce5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057ce5`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::SignalFlush(CFDRPlugin *this)
{
  char *v2; // rbx
  const struct std::nothrow_t *v3; // rdx
  int v4; // edi
  CUserModeHangReport *v5; // rcx
  __int64 v6; // rdx
  LPCWSTR lpName; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  utl::make_unique_for_overwrite<wchar_t [0],0>(&lpName, 260);
  if ( !lpName )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
    }
    v4 = -2147024882;
    goto LABEL_25;
  }
  v4 = StringCchPrintfW((wchar_t *)lpName, 0x104u, L"%s-%d", L"FDR_FLUSH_MESSAGE", *((_DWORD *)this + 12));
  if ( v4 >= 0 )
  {
    v2 = (char *)OpenEventW(0x100002u, 0, lpName);
    if ( v2 == (char *)-1LL || v2 + 1 == (char *)1 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_15;
      }
      v6 = 70;
    }
    else if ( SetEvent(v2) )
    {
      if ( WaitForSingleObject(v2, 0x1388u) != -1 )
      {
        v4 = 0;
        goto LABEL_25;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_15:
        v4 = -2147467259;
        goto LABEL_25;
      }
      v6 = 72;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_15;
      }
      v6 = 71;
    }
    WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
  }
LABEL_25:
  if ( lpName )
    operator delete((void *)lpName, v3);
  if ( (unsigned __int64)(v2 + 1) > 1 )
    CloseHandle(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140057b3c  mov     [rsp+arg_0], rbx
0x140057b41  push    rdi
0x140057b42  sub     rsp, 30h
0x140057b46  mov     rdi, rcx
0x140057b49  mov     edx, 104h
0x140057b4e  lea     rcx, [rsp+38h+lpName]
0x140057b53  xor     ebx, ebx
0x140057b55  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140057b5a  cmp     [rsp+38h+lpName], rbx
0x140057b5f  jnz     short loc_140057B97
0x140057b61  mov     rcx, cs:WPP_GLOBAL_Control
0x140057b68  lea     rax, WPP_GLOBAL_Control
0x140057b6f  cmp     rcx, rax
0x140057b72  jz      short loc_140057B8D
0x140057b74  test    byte ptr [rcx+1Ch], 1
0x140057b78  jz      short loc_140057B8D
0x140057b7a  mov     rcx, [rcx+10h]
0x140057b7e  lea     edx, [rbx+44h]
0x140057b81  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140057b88  call    WPP_SF_
0x140057b8d  mov     edi, 8007000Eh
0x140057b92  jmp     loc_140057CC6
0x140057b97  mov     eax, [rdi+30h]
0x140057b9a  lea     r9, aFdrFlushMessag; "FDR_FLUSH_MESSAGE"
0x140057ba1  mov     rcx, [rsp+38h+lpName]; wchar_t *
0x140057ba6  lea     r8, aSD; "%s-%d"
0x140057bad  mov     edx, 104h; unsigned __int64
0x140057bb2  mov     [rsp+38h+var_18], eax
0x140057bb6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140057bbb  mov     edi, eax
0x140057bbd  test    eax, eax
0x140057bbf  jns     short loc_140057BFC
0x140057bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140057bc8  lea     rax, WPP_GLOBAL_Control
0x140057bcf  cmp     rcx, rax
0x140057bd2  jz      loc_140057CC6
0x140057bd8  test    byte ptr [rcx+1Ch], 1
0x140057bdc  jz      loc_140057CC6
0x140057be2  mov     rcx, [rcx+10h]
0x140057be6  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140057bed  mov     edx, 45h ; 'E'
0x140057bf2  call    WPP_SF_
0x140057bf7  jmp     loc_140057CC6
0x140057bfc  mov     r8, [rsp+38h+lpName]; lpName
0x140057c01  xor     edx, edx; bInheritHandle
0x140057c03  mov     ecx, 100002h; dwDesiredAccess
0x140057c08  call    cs:__imp_OpenEventW
0x140057c0f  nop     dword ptr [rax+rax+00h]
0x140057c14  mov     rbx, rax
0x140057c17  inc     rax
0x140057c1a  cmp     rax, 1
0x140057c1e  ja      short loc_140057C55
0x140057c20  mov     rcx, cs:WPP_GLOBAL_Control
0x140057c27  lea     rax, WPP_GLOBAL_Control
0x140057c2e  cmp     rcx, rax
0x140057c31  jz      short loc_140057C4E
0x140057c33  test    byte ptr [rcx+1Ch], 1
0x140057c37  jz      short loc_140057C4E
0x140057c39  mov     edx, 46h ; 'F'
0x140057c3e  mov     rcx, [rcx+10h]
0x140057c42  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140057c49  call    WPP_SF_
0x140057c4e  mov     edi, 80004005h
0x140057c53  jmp     short loc_140057CC6
0x140057c55  mov     rcx, rbx; hEvent
0x140057c58  call    cs:__imp_SetEvent
0x140057c5f  nop     dword ptr [rax+rax+00h]
0x140057c64  test    eax, eax
0x140057c66  jnz     short loc_140057C88
0x140057c68  mov     rcx, cs:WPP_GLOBAL_Control
0x140057c6f  lea     rax, WPP_GLOBAL_Control
0x140057c76  cmp     rcx, rax
0x140057c79  jz      short loc_140057C4E
0x140057c7b  test    byte ptr [rcx+1Ch], 1
0x140057c7f  jz      short loc_140057C4E
0x140057c81  mov     edx, 47h ; 'G'
0x140057c86  jmp     short loc_140057C3E
0x140057c88  mov     edx, 1388h; dwMilliseconds
0x140057c8d  mov     rcx, rbx; hHandle
0x140057c90  call    cs:__imp_WaitForSingleObject
0x140057c97  nop     dword ptr [rax+rax+00h]
0x140057c9c  cmp     eax, 0FFFFFFFFh
0x140057c9f  jnz     short loc_140057CC4
0x140057ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x140057ca8  lea     rax, WPP_GLOBAL_Control
0x140057caf  cmp     rcx, rax
0x140057cb2  jz      short loc_140057C4E
0x140057cb4  test    byte ptr [rcx+1Ch], 1
0x140057cb8  jz      short loc_140057C4E
0x140057cba  mov     edx, 48h ; 'H'
0x140057cbf  jmp     loc_140057C3E
0x140057cc4  xor     edi, edi
0x140057cc6  cmp     [rsp+38h+lpName], 0
0x140057ccc  jz      short loc_140057CD8
0x140057cce  mov     rcx, [rsp+38h+lpName]; void *
0x140057cd3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140057cd8  lea     rax, [rbx+1]
0x140057cdc  cmp     rax, 1
0x140057ce0  jbe     short loc_140057CF1
0x140057ce2  mov     rcx, rbx; hObject
0x140057ce5  call    cs:__imp_CloseHandle
0x140057cec  nop     dword ptr [rax+rax+00h]
0x140057cf1  mov     rbx, [rsp+38h+arg_0]
0x140057cf6  mov     eax, edi
0x140057cf8  add     rsp, 30h
0x140057cfc  pop     rdi
0x140057cfd  retn
```
