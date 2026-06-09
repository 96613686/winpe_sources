# TraceLoggingManager::InitializeSessionSettings(void)

- ea: `0x180026114`
- end: `0x180026244`
- name: `?InitializeSessionSettings@TraceLoggingManager@@AEAAJXZ`
- size: `304`
- prototype: `__int64 __fastcall(const WCHAR *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180025efc`

## callees

- `0x180017820`
- `0x180023278`
- `0x180026114`
- `0x18002d518`
- `0x18003c4a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180026218`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180026218`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800261c8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800261c8`

## string_xrefs

- `0x1800261e4`: `onecore\ds\security\ngc\ctnrsvc\service\traceloggingmanager.cpp`

## pseudocode

```c
__int64 __fastcall TraceLoggingManager::InitializeSessionSettings(const WCHAR *this)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // rdx
  const WCHAR *v4; // r9
  LPCWSTR *v5; // r8
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PCWSTR pszPathIn; // [rsp+30h] [rbp+8h] BYREF

  pszPathIn = this;
  memset_0(&Properties, 0, 0x978u);
  Properties.Wnode.BufferSize = 2424;
  Properties.Wnode.Flags = 0x20000;
  Properties.Wnode.ClientContext = 2;
  Properties.LogFileMode = 4;
  Properties.MaximumFileSize = 150;
  Properties.FlushTimer = 10;
  Properties.LoggerNameOffset = 120;
  Properties.LogFileNameOffset = 376;
  pszPathIn = 0;
  v1 = wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(&pszPathIn);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 98;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\traceloggingmanager.cpp",
      (const char *)(unsigned int)v1,
      v7);
    goto LABEL_13;
  }
  v4 = (const WCHAR *)&pszMore;
  if ( (unsigned __int64)qword_1800C0D68 > 7 )
    v4 = pszMore;
  v1 = PathCchCombine(&FileName, 0x400u, pszPathIn, v4);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 99;
    goto LABEL_7;
  }
  v5 = &g_NgcTraceLoggingManager;
  if ( (unsigned __int64)qword_1800C0D48 > 7 )
    v5 = (LPCWSTR *)g_NgcTraceLoggingManager;
  if ( (unsigned int)_o_wcscpy_s(qword_1800C0E10, 128, v5) )
    v2 = -2147024630;
  else
    v2 = 0;
LABEL_13:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPathIn);
  return v2;
}

```

## disassembly

```asm
0x180026114  mov     [rsp+pszPathIn], rcx
0x180026119  push    rbx; int
0x18002611a  sub     rsp, 20h
0x18002611e  mov     ebx, 978h
0x180026123  lea     rcx, Properties; void *
0x18002612a  mov     r8d, ebx; Size
0x18002612d  xor     edx, edx; Val
0x18002612f  call    memset_0
0x180026134  lea     rcx, [rsp+28h+pszPathIn]
0x180026139  mov     cs:Properties.Wnode.BufferSize, ebx
0x18002613f  mov     cs:Properties.Wnode.Flags, 20000h
0x180026149  mov     cs:Properties.Wnode.ClientContext, 2
0x180026153  mov     cs:Properties.LogFileMode, 4
0x18002615d  mov     cs:Properties.MaximumFileSize, 96h
0x180026167  mov     cs:Properties.FlushTimer, 0Ah
0x180026171  mov     cs:Properties.LoggerNameOffset, 78h ; 'x'
0x18002617b  mov     cs:Properties.LogFileNameOffset, 178h
0x180026185  mov     [rsp+28h+pszPathIn], 0
0x18002618e  call    ??$GetSystemDirectoryW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180026193  mov     ebx, eax
0x180026195  test    eax, eax
0x180026197  jns     short loc_1800261A0
0x180026199  mov     edx, 62h ; 'b'
0x18002619e  jmp     short loc_1800261DF
0x1800261a0  cmp     cs:qword_1800C0D68, 7
0x1800261a8  lea     r9, pszMore
0x1800261af  mov     r8, [rsp+28h+pszPathIn]; pszPathIn
0x1800261b4  lea     rcx, FileName; pszPathOut
0x1800261bb  cmova   r9, cs:pszMore; pszMore
0x1800261c3  mov     edx, 400h; cchPathOut
0x1800261c8  call    cs:__imp_PathCchCombine
0x1800261cf  nop     dword ptr [rax+rax+00h]
0x1800261d4  mov     ebx, eax
0x1800261d6  test    eax, eax
0x1800261d8  jns     short loc_1800261F5
0x1800261da  mov     edx, 63h ; 'c'; void *
0x1800261df  mov     rcx, [rsp+28h]; this
0x1800261e4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x1800261eb  mov     r9d, eax; char *
0x1800261ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800261f3  jmp     short loc_180026231
0x1800261f5  cmp     cs:qword_1800C0D48, 7
0x1800261fd  lea     r8, ?g_NgcTraceLoggingManager@@3VTraceLoggingManager@@A; TraceLoggingManager g_NgcTraceLoggingManager
0x180026204  mov     edx, 80h
0x180026209  lea     rcx, qword_1800C0E10
0x180026210  cmova   r8, cs:?g_NgcTraceLoggingManager@@3VTraceLoggingManager@@A; TraceLoggingManager g_NgcTraceLoggingManager
0x180026218  call    cs:__imp__o_wcscpy_s
0x18002621f  nop     dword ptr [rax+rax+00h]
0x180026224  test    eax, eax
0x180026226  jz      short loc_18002622F
0x180026228  mov     ebx, 8007010Ah
0x18002622d  jmp     short loc_180026231
0x18002622f  xor     ebx, ebx
0x180026231  lea     rcx, [rsp+28h+pszPathIn]
0x180026236  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002623b  mov     eax, ebx
0x18002623d  add     rsp, 20h
0x180026241  pop     rbx
0x180026242  retn
```
