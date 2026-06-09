# GetCommonHttpRequestHeaders(ushort * *,unsigned __int64 *)

- ea: `0x18009da38`
- end: `0x18009e04f`
- name: `?GetCommonHttpRequestHeaders@@YAJPEAPEAGPEA_K@Z`
- size: `1559`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009c1a0`

## callees

- `0x180003c20`
- `0x180005f24`
- `0x180006c40`
- `0x180086678`
- `0x1800871b4`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x18008aad8`
- `0x18008aecc`
- `0x18009c460`
- `0x18009da38`
- `0x18009e058`
- `0x18009e2e0`
- `0x18009ec70`
- `0x1800a3068`

## string_xrefs

- `0x18009db29`: `GetCommonHttpRequestHeaders`
- `0x18009db43`: `GetCommonHttpRequestHeaders`
- `0x18009db92`: `GetCommonHttpRequestHeaders`
- `0x18009dbdc`: `GetCommonHttpRequestHeaders`
- `0x18009dc29`: `GetCommonHttpRequestHeaders`
- `0x18009dc61`: `GetCommonHttpRequestHeaders`
- `0x18009dcdb`: `GetCommonHttpRequestHeaders`
- `0x18009dcfb`: `GetCommonHttpRequestHeaders`
- `0x18009dd1e`: `GetCommonHttpRequestHeaders`
- `0x18009de73`: `GetCommonHttpRequestHeaders`
- `0x18009df11`: `GetCommonHttpRequestHeaders`
- `0x18009df8c`: `GetCommonHttpRequestHeaders`
- `0x18009e01f`: `GetCommonHttpRequestHeaders`
- `0x18009dd02`: `%s: %d disallowed character(s) were removed from target server value.`
- `0x18009dbd5`: `GetDllVersionInfo`
- `0x18009dc22`: `GetDllVersionInfo`
- `0x18009decc`: `User-Agent: Dsreg/%s (Windows %s)\nocp-adrs-client-name: Dsreg\nocp-adrs-client-version: %s\n`

## pseudocode

```c
__int64 __fastcall GetCommonHttpRequestHeaders(unsigned __int16 **a1, unsigned __int64 *a2)
{
  size_t v2; // rax
  int OSVersionInfo; // [rsp+50h] [rbp-3F8h]
  int TargetServer; // [rsp+50h] [rbp-3F8h]
  int v6; // [rsp+54h] [rbp-3F4h] BYREF
  unsigned __int16 *v7; // [rsp+58h] [rbp-3F0h] BYREF
  wchar_t *v8; // [rsp+60h] [rbp-3E8h]
  unsigned __int64 v9; // [rsp+68h] [rbp-3E0h] BYREF
  unsigned __int64 v10; // [rsp+70h] [rbp-3D8h]
  wchar_t *Buffer; // [rsp+78h] [rbp-3D0h] BYREF
  __int64 v12; // [rsp+80h] [rbp-3C8h]
  __int64 v13; // [rsp+88h] [rbp-3C0h]
  __int64 v14; // [rsp+90h] [rbp-3B8h]
  unsigned __int64 v15; // [rsp+98h] [rbp-3B0h] BYREF
  unsigned __int16 *v16; // [rsp+A0h] [rbp-3A8h]
  wchar_t *v17; // [rsp+A8h] [rbp-3A0h]
  unsigned __int16 *v18; // [rsp+B0h] [rbp-398h]
  wchar_t *v19; // [rsp+B8h] [rbp-390h]
  void *Block; // [rsp+C0h] [rbp-388h]
  unsigned __int16 v21[56]; // [rsp+D0h] [rbp-378h] BYREF
  wchar_t v22[56]; // [rsp+140h] [rbp-308h] BYREF
  unsigned __int16 v23[56]; // [rsp+1B0h] [rbp-298h] BYREF
  unsigned __int16 v24[264]; // [rsp+220h] [rbp-228h] BYREF

  memset(v22, 0, 0x64u);
  memset(v23, 0, 0x64u);
  memset(v21, 0, 0x64u);
  memset(v24, 0, 0x20Au);
  v7 = 0;
  v6 = 0;
  v8 = 0;
  Buffer = 0;
  v10 = 0;
  v9 = 0;
  v15 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a1 )
  {
    *a1 = 0;
    OSVersionInfo = GetOSVersionInfo(v22, 0x32u);
    if ( OSVersionInfo >= 0 )
    {
      OSVersionInfo = GetDllVersionInfo(v23, 0x32u, 0);
      if ( OSVersionInfo < 0 || (OSVersionInfo = GetDllVersionInfo(v21, 0x32u, 1), OSVersionInfo < 0) )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"GetCommonHttpRequestHeaders",
          L"GetDllVersionInfo",
          (unsigned int)OSVersionInfo);
      }
      else
      {
        TargetServer = GetTargetServer(&v7);
        if ( TargetServer >= 0 )
        {
          if ( !(unsigned int)IsEmptyString(v7) )
          {
            if ( !(unsigned int)SanitizeHttpHeaderValue(v7, v24, 0x105u, &v15, &v6) )
              Logger::TraceWarning(
                L"%s: Target server value is truncated to %zu characters.",
                L"GetCommonHttpRequestHeaders",
                260);
            if ( v6 > 0 )
              Logger::TraceWarning(
                L"%s: %d disallowed character(s) were removed from target server value.",
                L"GetCommonHttpRequestHeaders",
                (unsigned int)v6);
            Logger::TraceInformation(
              L"%s: Header value for \"%s\" is \"%s\"",
              L"GetCommonHttpRequestHeaders",
              L"x-ms-target-dc",
              v24);
          }
        }
        else
        {
          Logger::TraceWarning(
            L"%s: GetTargetServer failed with error code %08x.",
            L"GetCommonHttpRequestHeaders",
            (unsigned int)TargetServer);
          SafeFree(v7);
          v7 = 0;
        }
        v16 = v23;
        v12 = -1;
        do
          ++v12;
        while ( v16[v12] );
        v17 = v22;
        v13 = -1;
        do
          ++v13;
        while ( v17[v13] );
        v18 = v21;
        v14 = -1;
        do
          ++v14;
        while ( v18[v14] );
        v10 = v14 + v12 + v13 + 93;
        if ( v15 )
          v10 += v15 + 20;
        v2 = 2 * v10;
        if ( !is_mul_ok(v10, 2u) )
          v2 = -1;
        v19 = (wchar_t *)operator new[](v2, (const struct std::nothrow_t *)std::nothrow);
        v8 = v19;
        if ( v19 )
        {
          v9 = v10;
          Buffer = v8;
          OSVersionInfo = StringCchPrintfExW(
                            v8,
                            v10,
                            &Buffer,
                            &v9,
                            0,
                            L"User-Agent: Dsreg/%s (Windows %s)\r\n"
                             "ocp-adrs-client-name: Dsreg\r\n"
                             "ocp-adrs-client-version: %s\r\n",
                            v23,
                            v22,
                            v21);
          if ( OSVersionInfo < 0
            || v15
            && (OSVersionInfo = StringCchPrintfExW(Buffer, v9, &Buffer, &v9, 0, L"x-ms-target-dc: %s\r\n", v24),
                OSVersionInfo < 0) )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"GetCommonHttpRequestHeaders",
              L"StringCchPrintfExW",
              (unsigned int)OSVersionInfo);
          }
          else
          {
            *a1 = v8;
            v8 = 0;
            if ( a2 )
              *a2 = v10 - v9;
          }
        }
        else
        {
          OSVersionInfo = -2147024882;
          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"GetCommonHttpRequestHeaders");
        }
      }
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"GetCommonHttpRequestHeaders",
        L"GetOSVersionInfo",
        (unsigned int)OSVersionInfo);
    }
  }
  else
  {
    OSVersionInfo = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetCommonHttpRequestHeaders", L"pBuffer");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetCommonHttpRequestHeaders", L"pBuffer");
  }
  SafeFree(v7);
  v7 = 0;
  Block = v8;
  operator delete(v8);
  v8 = 0;
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"GetCommonHttpRequestHeaders", (unsigned int)OSVersionInfo);
  return (unsigned int)OSVersionInfo;
}

```

## disassembly

```asm
0x18009da38  mov     [rsp+arg_8], rdx
0x18009da3d  mov     [rsp+arg_0], rcx
0x18009da42  push    rdi
0x18009da43  sub     rsp, 440h
0x18009da4a  mov     rax, cs:__security_cookie
0x18009da51  xor     rax, rsp
0x18009da54  mov     [rsp+448h+var_18], rax
0x18009da5c  mov     [rsp+448h+var_3F8], 0
0x18009da64  lea     rax, [rsp+448h+var_308]
0x18009da6c  mov     rdi, rax
0x18009da6f  xor     eax, eax
0x18009da71  mov     ecx, 64h ; 'd'
0x18009da76  rep stosb
0x18009da78  lea     rax, [rsp+448h+var_298]
0x18009da80  mov     rdi, rax
0x18009da83  xor     eax, eax
0x18009da85  mov     ecx, 64h ; 'd'
0x18009da8a  rep stosb
0x18009da8c  lea     rax, [rsp+448h+var_378]
0x18009da94  mov     rdi, rax
0x18009da97  xor     eax, eax
0x18009da99  mov     ecx, 64h ; 'd'
0x18009da9e  rep stosb
0x18009daa0  lea     rax, [rsp+448h+var_228]
0x18009daa8  mov     rdi, rax
0x18009daab  xor     eax, eax
0x18009daad  mov     ecx, 20Ah
0x18009dab2  rep stosb
0x18009dab4  mov     [rsp+448h+var_3F0], 0
0x18009dabd  mov     [rsp+448h+var_3F4], 0
0x18009dac5  mov     [rsp+448h+var_3E8], 0
0x18009dace  mov     [rsp+448h+Buffer], 0
0x18009dad7  mov     [rsp+448h+var_3D8], 0
0x18009dae0  mov     [rsp+448h+var_3E0], 0
0x18009dae9  mov     [rsp+448h+var_3B0], 0
0x18009daf5  cmp     [rsp+448h+arg_8], 0
0x18009dafe  jz      short loc_18009DB0F
0x18009db00  mov     rax, [rsp+448h+arg_8]
0x18009db08  mov     qword ptr [rax], 0
0x18009db0f  cmp     [rsp+448h+arg_0], 0
0x18009db18  jnz     short loc_18009DB5A
0x18009db1a  mov     [rsp+448h+var_3F8], 80070057h
0x18009db22  lea     r8, aPbuffer; "pBuffer"
0x18009db29  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009db30  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18009db37  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009db3c  lea     rdx, aPbuffer; "pBuffer"
0x18009db43  lea     rcx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009db4a  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18009db4f  nop
0x18009db50  jmp     loc_18009DFE3
0x18009db55  jmp     loc_18009DFE3
0x18009db5a  mov     rax, [rsp+448h+arg_0]
0x18009db62  mov     qword ptr [rax], 0
0x18009db69  mov     edx, 32h ; '2'; BufferCount
0x18009db6e  lea     rcx, [rsp+448h+var_308]; Buffer
0x18009db76  call    ?GetOSVersionInfo@@YAJPEAG_K@Z; GetOSVersionInfo(ushort *,unsigned __int64)
0x18009db7b  mov     [rsp+448h+var_3F8], eax
0x18009db7f  cmp     [rsp+448h+var_3F8], 0
0x18009db84  jge     short loc_18009DBB0
0x18009db86  mov     r9d, [rsp+448h+var_3F8]
0x18009db8b  lea     r8, aGetosversionin; "GetOSVersionInfo"
0x18009db92  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009db99  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009dba0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009dba5  nop
0x18009dba6  jmp     loc_18009DFE3
0x18009dbab  jmp     loc_18009DFE3
0x18009dbb0  xor     r8d, r8d; int
0x18009dbb3  mov     edx, 32h ; '2'; unsigned __int64
0x18009dbb8  lea     rcx, [rsp+448h+var_298]; unsigned __int16 *
0x18009dbc0  call    ?GetDllVersionInfo@@YAJPEAG_KH@Z; GetDllVersionInfo(ushort *,unsigned __int64,int)
0x18009dbc5  mov     [rsp+448h+var_3F8], eax
0x18009dbc9  cmp     [rsp+448h+var_3F8], 0
0x18009dbce  jge     short loc_18009DBFA
0x18009dbd0  mov     r9d, [rsp+448h+var_3F8]
0x18009dbd5  lea     r8, aGetdllversioni; "GetDllVersionInfo"
0x18009dbdc  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009dbe3  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009dbea  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009dbef  nop
0x18009dbf0  jmp     loc_18009DFE3
0x18009dbf5  jmp     loc_18009DFE3
0x18009dbfa  mov     r8d, 1; int
0x18009dc00  mov     edx, 32h ; '2'; unsigned __int64
0x18009dc05  lea     rcx, [rsp+448h+var_378]; unsigned __int16 *
0x18009dc0d  call    ?GetDllVersionInfo@@YAJPEAG_KH@Z; GetDllVersionInfo(ushort *,unsigned __int64,int)
0x18009dc12  mov     [rsp+448h+var_3F8], eax
0x18009dc16  cmp     [rsp+448h+var_3F8], 0
0x18009dc1b  jge     short loc_18009DC47
0x18009dc1d  mov     r9d, [rsp+448h+var_3F8]
0x18009dc22  lea     r8, aGetdllversioni; "GetDllVersionInfo"
0x18009dc29  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009dc30  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009dc37  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009dc3c  nop
0x18009dc3d  jmp     loc_18009DFE3
0x18009dc42  jmp     loc_18009DFE3
0x18009dc47  lea     rcx, [rsp+448h+var_3F0]; unsigned __int16 **
0x18009dc4c  call    ?GetTargetServer@@YAJPEAPEAG@Z; GetTargetServer(ushort * *)
0x18009dc51  mov     [rsp+448h+var_3F8], eax
0x18009dc55  cmp     [rsp+448h+var_3F8], 0
0x18009dc5a  jge     short loc_18009DC95
0x18009dc5c  mov     r8d, [rsp+448h+var_3F8]
0x18009dc61  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009dc68  lea     rcx, aSGettargetserv; "%s: GetTargetServer failed with error c"...
0x18009dc6f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18009dc74  nop
0x18009dc75  mov     rcx, [rsp+448h+var_3F0]; void *
0x18009dc7a  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009dc7f  mov     [rsp+448h+var_3F0], 0
0x18009dc88  mov     [rsp+448h+var_3F8], 0
0x18009dc90  jmp     loc_18009DD32
0x18009dc95  mov     rcx, [rsp+448h+var_3F0]; unsigned __int16 *
0x18009dc9a  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18009dc9f  test    eax, eax
0x18009dca1  jnz     loc_18009DD32
0x18009dca7  lea     rax, [rsp+448h+var_3F4]
0x18009dcac  mov     [rsp+448h+var_428], rax; int *
0x18009dcb1  lea     r9, [rsp+448h+var_3B0]; unsigned __int64 *
0x18009dcb9  mov     r8d, 105h; unsigned __int64
0x18009dcbf  lea     rdx, [rsp+448h+var_228]; unsigned __int16 *
0x18009dcc7  mov     rcx, [rsp+448h+var_3F0]; unsigned __int16 *
0x18009dccc  call    ?SanitizeHttpHeaderValue@@YAHPEBGPEAG_KPEA_KPEAH@Z; SanitizeHttpHeaderValue(ushort const *,ushort *,unsigned __int64,unsigned __int64 *,int *)
0x18009dcd1  test    eax, eax
0x18009dcd3  jnz     short loc_18009DCEF
0x18009dcd5  mov     r8d, 104h
0x18009dcdb  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009dce2  lea     rcx, aSTargetServerV; "%s: Target server value is truncated to"...
0x18009dce9  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18009dcee  nop
0x18009dcef  cmp     [rsp+448h+var_3F4], 0
0x18009dcf4  jle     short loc_18009DD0F
0x18009dcf6  mov     r8d, [rsp+448h+var_3F4]
0x18009dcfb  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009dd02  lea     rcx, aSDDisallowedCh; "%s: %d disallowed character(s) were rem"...
0x18009dd09  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18009dd0e  nop
0x18009dd0f  lea     r9, [rsp+448h+var_228]
0x18009dd17  lea     r8, aXMsTargetDc; "x-ms-target-dc"
0x18009dd1e  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009dd25  lea     rcx, aSHeaderValueFo; "%s: Header value for \"%s\" is \"%s\""
0x18009dd2c  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009dd31  nop
0x18009dd32  lea     rax, [rsp+448h+var_298]
0x18009dd3a  mov     [rsp+448h+var_3A8], rax
0x18009dd42  mov     [rsp+448h+var_3C8], 0FFFFFFFFFFFFFFFFh
0x18009dd4e  inc     [rsp+448h+var_3C8]
0x18009dd56  mov     rax, [rsp+448h+var_3A8]
0x18009dd5e  mov     rcx, [rsp+448h+var_3C8]
0x18009dd66  cmp     word ptr [rax+rcx*2], 0
0x18009dd6b  jnz     short loc_18009DD4E
0x18009dd6d  mov     rax, [rsp+448h+var_3C8]
0x18009dd75  lea     rcx, [rsp+448h+var_308]
0x18009dd7d  mov     [rsp+448h+var_3A0], rcx
0x18009dd85  mov     [rsp+448h+var_3C0], 0FFFFFFFFFFFFFFFFh
0x18009dd91  inc     [rsp+448h+var_3C0]
0x18009dd99  mov     rcx, [rsp+448h+var_3A0]
0x18009dda1  mov     rdx, [rsp+448h+var_3C0]
0x18009dda9  cmp     word ptr [rcx+rdx*2], 0
0x18009ddae  jnz     short loc_18009DD91
0x18009ddb0  mov     rcx, [rsp+448h+var_3C0]
0x18009ddb8  lea     rax, [rax+rcx+5Dh]
0x18009ddbd  lea     rcx, [rsp+448h+var_378]
0x18009ddc5  mov     [rsp+448h+var_398], rcx
0x18009ddcd  mov     [rsp+448h+var_3B8], 0FFFFFFFFFFFFFFFFh
0x18009ddd9  inc     [rsp+448h+var_3B8]
0x18009dde1  mov     rcx, [rsp+448h+var_398]
0x18009dde9  mov     rdx, [rsp+448h+var_3B8]
0x18009ddf1  cmp     word ptr [rcx+rdx*2], 0
0x18009ddf6  jnz     short loc_18009DDD9
0x18009ddf8  mov     rcx, [rsp+448h+var_3B8]
0x18009de00  add     rax, rcx
0x18009de03  mov     [rsp+448h+var_3D8], rax
0x18009de08  cmp     [rsp+448h+var_3B0], 0
0x18009de11  jbe     short loc_18009DE2A
0x18009de13  mov     rax, [rsp+448h+var_3D8]
0x18009de18  mov     rcx, [rsp+448h+var_3B0]
0x18009de20  lea     rax, [rax+rcx+14h]
0x18009de25  mov     [rsp+448h+var_3D8], rax
0x18009de2a  mov     eax, 2
0x18009de2f  mul     [rsp+448h+var_3D8]
0x18009de34  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009de3b  cmovb   rax, rcx
0x18009de3f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009de46  mov     rcx, rax; unsigned __int64
0x18009de49  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009de4e  mov     [rsp+448h+var_390], rax
0x18009de56  mov     rax, [rsp+448h+var_390]
0x18009de5e  mov     [rsp+448h+var_3E8], rax
0x18009de63  cmp     [rsp+448h+var_3E8], 0
0x18009de69  jnz     short loc_18009DE91
0x18009de6b  mov     [rsp+448h+var_3F8], 8007000Eh
0x18009de73  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009de7a  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18009de81  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18009de86  nop
0x18009de87  jmp     loc_18009DFE3
0x18009de8c  jmp     loc_18009DFE3
0x18009de91  mov     rax, [rsp+448h+var_3D8]
0x18009de96  mov     [rsp+448h+var_3E0], rax
0x18009de9b  mov     rax, [rsp+448h+var_3E8]
0x18009dea0  mov     [rsp+448h+Buffer], rax
0x18009dea5  lea     rax, [rsp+448h+var_378]
0x18009dead  mov     [rsp+448h+var_408], rax
0x18009deb2  lea     rax, [rsp+448h+var_308]
0x18009deba  mov     [rsp+448h+var_410], rax
0x18009debf  lea     rax, [rsp+448h+var_298]
0x18009dec7  mov     [rsp+448h+var_418], rax
0x18009decc  lea     rax, aUserAgentDsreg; "User-Agent: Dsreg/%s (Windows %s)\r\noc"...
0x18009ded3  mov     [rsp+448h+var_420], rax; unsigned __int16 *
0x18009ded8  mov     [rsp+448h+var_428], 0; unsigned int
0x18009dee1  lea     r9, [rsp+448h+var_3E0]; unsigned __int64 *
0x18009dee6  lea     r8, [rsp+448h+Buffer]; unsigned __int16 **
0x18009deeb  mov     rdx, [rsp+448h+var_3E0]; unsigned __int64
0x18009def0  mov     rcx, [rsp+448h+Buffer]; Buffer
0x18009def5  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18009defa  mov     [rsp+448h+var_3F8], eax
0x18009defe  cmp     [rsp+448h+var_3F8], 0
0x18009df03  jge     short loc_18009DF2F
0x18009df05  mov     r9d, [rsp+448h+var_3F8]
0x18009df0a  lea     r8, aStringcchprint_0; "StringCchPrintfExW"
0x18009df11  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009df18  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009df1f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009df24  nop
0x18009df25  jmp     loc_18009DFE3
0x18009df2a  jmp     loc_18009DFE3
0x18009df2f  cmp     [rsp+448h+var_3B0], 0
0x18009df38  jbe     short loc_18009DFA4
0x18009df3a  lea     rax, [rsp+448h+var_228]
0x18009df42  mov     [rsp+448h+var_418], rax
0x18009df47  lea     rax, aXMsTargetDcS; "x-ms-target-dc: %s\r\n"
0x18009df4e  mov     [rsp+448h+var_420], rax; unsigned __int16 *
0x18009df53  mov     [rsp+448h+var_428], 0; unsigned int
0x18009df5c  lea     r9, [rsp+448h+var_3E0]; unsigned __int64 *
0x18009df61  lea     r8, [rsp+448h+Buffer]; unsigned __int16 **
0x18009df66  mov     rdx, [rsp+448h+var_3E0]; unsigned __int64
0x18009df6b  mov     rcx, [rsp+448h+Buffer]; Buffer
0x18009df70  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18009df75  mov     [rsp+448h+var_3F8], eax
0x18009df79  cmp     [rsp+448h+var_3F8], 0
0x18009df7e  jge     short loc_18009DFA4
0x18009df80  mov     r9d, [rsp+448h+var_3F8]
0x18009df85  lea     r8, aStringcchprint_0; "StringCchPrintfExW"
0x18009df8c  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009df93  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009df9a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009df9f  nop
0x18009dfa0  jmp     short loc_18009DFE3
0x18009dfa2  jmp     short loc_18009DFE3
0x18009dfa4  mov     rax, [rsp+448h+arg_0]
0x18009dfac  mov     rcx, [rsp+448h+var_3E8]
0x18009dfb1  mov     [rax], rcx
0x18009dfb4  mov     [rsp+448h+var_3E8], 0
0x18009dfbd  cmp     [rsp+448h+arg_8], 0
0x18009dfc6  jz      short loc_18009DFE3
0x18009dfc8  mov     rax, [rsp+448h+var_3E0]
0x18009dfcd  mov     rcx, [rsp+448h+var_3D8]
0x18009dfd2  sub     rcx, rax
0x18009dfd5  mov     rax, rcx
0x18009dfd8  mov     rcx, [rsp+448h+arg_8]
0x18009dfe0  mov     [rcx], rax
0x18009dfe3  mov     rcx, [rsp+448h+var_3F0]; void *
0x18009dfe8  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009dfed  mov     [rsp+448h+var_3F0], 0
0x18009dff6  mov     rax, [rsp+448h+var_3E8]
0x18009dffb  mov     [rsp+448h+Block], rax
0x18009e003  mov     rcx, [rsp+448h+Block]; Block
0x18009e00b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009e010  nop
0x18009e011  mov     [rsp+448h+var_3E8], 0
0x18009e01a  mov     r8d, [rsp+448h+var_3F8]
0x18009e01f  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18009e026  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18009e02d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009e032  mov     eax, [rsp+448h+var_3F8]
0x18009e036  mov     rcx, [rsp+448h+var_18]
0x18009e03e  xor     rcx, rsp; StackCookie
0x18009e041  call    __security_check_cookie
0x18009e046  add     rsp, 440h
0x18009e04d  pop     rdi
0x18009e04e  retn
```
