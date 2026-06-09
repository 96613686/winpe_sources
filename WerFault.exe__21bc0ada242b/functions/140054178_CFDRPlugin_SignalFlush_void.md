# CFDRPlugin::SignalFlush(void)

- ea: `0x140054178`
- end: `0x14005431f`
- name: `?SignalFlush@CFDRPlugin@@AEAAJXZ`
- size: `423`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x140053830`

## callees

- `0x140002728`
- `0x14000b540`
- `0x14000e3c4`
- `0x14001444c`
- `0x140054178`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140054244`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140054244`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400542c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400542c0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14005428e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14005428e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005430c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005430c`

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
0x140054178  mov     [rsp+arg_0], rbx
0x14005417d  push    rdi
0x14005417e  sub     rsp, 30h
0x140054182  mov     rdi, rcx
0x140054185  mov     edx, 104h
0x14005418a  lea     rcx, [rsp+38h+lpName]
0x14005418f  xor     ebx, ebx
0x140054191  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140054196  cmp     [rsp+38h+lpName], rbx
0x14005419b  jnz     short loc_1400541D3
0x14005419d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400541a4  lea     rax, WPP_GLOBAL_Control
0x1400541ab  cmp     rcx, rax
0x1400541ae  jz      short loc_1400541C9
0x1400541b0  test    byte ptr [rcx+1Ch], 1
0x1400541b4  jz      short loc_1400541C9
0x1400541b6  mov     rcx, [rcx+10h]
0x1400541ba  lea     edx, [rbx+44h]
0x1400541bd  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1400541c4  call    WPP_SF_
0x1400541c9  mov     edi, 8007000Eh
0x1400541ce  jmp     loc_1400542ED
0x1400541d3  mov     eax, [rdi+30h]
0x1400541d6  lea     r9, aFdrFlushMessag; "FDR_FLUSH_MESSAGE"
0x1400541dd  mov     rcx, [rsp+38h+lpName]; wchar_t *
0x1400541e2  lea     r8, aSD; "%s-%d"
0x1400541e9  mov     edx, 104h; unsigned __int64
0x1400541ee  mov     [rsp+38h+var_18], eax
0x1400541f2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400541f7  mov     edi, eax
0x1400541f9  test    eax, eax
0x1400541fb  jns     short loc_140054238
0x1400541fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140054204  lea     rax, WPP_GLOBAL_Control
0x14005420b  cmp     rcx, rax
0x14005420e  jz      loc_1400542ED
0x140054214  test    byte ptr [rcx+1Ch], 1
0x140054218  jz      loc_1400542ED
0x14005421e  mov     rcx, [rcx+10h]
0x140054222  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140054229  mov     edx, 45h ; 'E'
0x14005422e  call    WPP_SF_
0x140054233  jmp     loc_1400542ED
0x140054238  mov     r8, [rsp+38h+lpName]; lpName
0x14005423d  xor     edx, edx; bInheritHandle
0x14005423f  mov     ecx, 100002h; dwDesiredAccess
0x140054244  call    cs:__imp_OpenEventW
0x14005424a  mov     rbx, rax
0x14005424d  inc     rax
0x140054250  cmp     rax, 1
0x140054254  ja      short loc_14005428B
0x140054256  mov     rcx, cs:WPP_GLOBAL_Control
0x14005425d  lea     rax, WPP_GLOBAL_Control
0x140054264  cmp     rcx, rax
0x140054267  jz      short loc_140054284
0x140054269  test    byte ptr [rcx+1Ch], 1
0x14005426d  jz      short loc_140054284
0x14005426f  mov     edx, 46h ; 'F'
0x140054274  mov     rcx, [rcx+10h]
0x140054278  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x14005427f  call    WPP_SF_
0x140054284  mov     edi, 80004005h
0x140054289  jmp     short loc_1400542ED
0x14005428b  mov     rcx, rbx; hEvent
0x14005428e  call    cs:__imp_SetEvent
0x140054294  test    eax, eax
0x140054296  jnz     short loc_1400542B8
0x140054298  mov     rcx, cs:WPP_GLOBAL_Control
0x14005429f  lea     rax, WPP_GLOBAL_Control
0x1400542a6  cmp     rcx, rax
0x1400542a9  jz      short loc_140054284
0x1400542ab  test    byte ptr [rcx+1Ch], 1
0x1400542af  jz      short loc_140054284
0x1400542b1  mov     edx, 47h ; 'G'
0x1400542b6  jmp     short loc_140054274
0x1400542b8  mov     edx, 1388h; dwMilliseconds
0x1400542bd  mov     rcx, rbx; hHandle
0x1400542c0  call    cs:__imp_WaitForSingleObject
0x1400542c6  cmp     eax, 0FFFFFFFFh
0x1400542c9  jnz     short loc_1400542EB
0x1400542cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400542d2  lea     rax, WPP_GLOBAL_Control
0x1400542d9  cmp     rcx, rax
0x1400542dc  jz      short loc_140054284
0x1400542de  test    byte ptr [rcx+1Ch], 1
0x1400542e2  jz      short loc_140054284
0x1400542e4  mov     edx, 48h ; 'H'
0x1400542e9  jmp     short loc_140054274
0x1400542eb  xor     edi, edi
0x1400542ed  cmp     [rsp+38h+lpName], 0
0x1400542f3  jz      short loc_1400542FF
0x1400542f5  mov     rcx, [rsp+38h+lpName]; void *
0x1400542fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400542ff  lea     rax, [rbx+1]
0x140054303  cmp     rax, 1
0x140054307  jbe     short loc_140054312
0x140054309  mov     rcx, rbx; hObject
0x14005430c  call    cs:__imp_CloseHandle
0x140054312  mov     rbx, [rsp+38h+arg_0]
0x140054317  mov     eax, edi
0x140054319  add     rsp, 30h
0x14005431d  pop     rdi
0x14005431e  retn
```
