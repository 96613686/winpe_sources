# HttpExtensionProc

- ea: `0x18000d3e0`
- end: `0x18000d8a7`
- name: `HttpExtensionProc`
- size: `1223`
- prototype: `DWORD __stdcall(EXTENSION_CONTROL_BLOCK *pECB)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c0c`
- `0x1800039fc`
- `0x180004c7c`
- `0x180004df0`
- `0x180004f68`
- `0x1800071c4`
- `0x18000aa08`
- `0x18000b104`
- `0x18000bce4`
- `0x18000d3e0`
- `0x18000db84`
- `0x18000dbb4`
- `0x18000ddd4`
- `0x18000e61c`
- `0x18000eeb0`
- `0x18000f5c2`
- `0x18000f5f0`
- `0x180011010`

## import_xrefs

- `msvcrt!free` at `0x18000d73b`
- `msvcrt!free` at `0x18000d752`
- `msvcrt!free` at `0x18000d73b`
- `msvcrt!free` at `0x18000d752`
- `msvcrt!_stricmp` at `0x18000d494`
- `msvcrt!_stricmp` at `0x18000d494`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000d7c0`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000d80d`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000d7c0`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000d80d`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18000d84b`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18000d88b`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18000d84b`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18000d88b`
- `KERNEL32!GetLastError` at `0x18000d437`
- `KERNEL32!GetLastError` at `0x18000d437`

## pseudocode

```c
DWORD __stdcall HttpExtensionProc(EXTENSION_CONTROL_BLOCK *pECB)
{
  DWORD LastError; // eax
  _QWORD *v3; // rcx
  DWORD v4; // edi
  const char *v5; // rax
  Context *v6; // rbx
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  char v13; // al
  int v14; // edx
  int v15; // r8d
  DWORD v16; // [rsp+30h] [rbp-908h] BYREF
  const char *v17; // [rsp+38h] [rbp-900h] BYREF
  EXTENSION_CONTROL_BLOCK *v18; // [rsp+40h] [rbp-8F8h]
  Context *v19; // [rsp+48h] [rbp-8F0h]
  const bad_win32_error *v20; // [rsp+50h] [rbp-8E8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-8E0h] BYREF
  _BYTE v22[24]; // [rsp+70h] [rbp-8C8h] BYREF
  _BYTE v23[24]; // [rsp+88h] [rbp-8B0h] BYREF
  char v24[32]; // [rsp+A0h] [rbp-898h] BYREF
  char String1[112]; // [rsp+C0h] [rbp-878h] BYREF
  WCHAR v26[1000]; // [rsp+130h] [rbp-808h] BYREF

  v18 = pECB;
  v16 = 100;
  if ( ((unsigned int (__fastcall *)(HCONN, const char *, char *, DWORD *))pECB->GetServerVariable)(
         pECB->ConnID,
         "HTTPS",
         String1,
         &v16) )
  {
    if ( !_stricmp(String1, "on") )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 47);
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        CheckAccessAllowed((__int64)pECB);
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 57);
          v3 = WPP_GLOBAL_Control;
        }
        v4 = 1;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &bad_win32_error `RTTI Type Descriptor', &v20) )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            v16 = 1000;
            if ( GetUserNameW(v26, &v16) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                v13 = (*(__int64 (__fastcall **)(const bad_win32_error *))(*(_QWORD *)v20 + 16LL))(v20);
                WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 12), v14, v15, (int)v26, v13);
              }
            }
          }
          if ( (unsigned int)SendResponse((__int64)v18, (__int64)"401 Unauthorized", 0) )
          {
            v4 = 1;
            __eh34_try_continuation(0, &bad_win32_error `RTTI Type Descriptor', &loc_18000D504);
          }
          else
          {
            v4 = 4;
            __eh34_try_continuation(0, &bad_win32_error `RTTI Type Descriptor', &loc_18000D4FA);
          }
          return v4;
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 48);
        v3 = WPP_GLOBAL_Control;
      }
      v4 = 1;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    v4 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 46, &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids, LastError);
      v3 = WPP_GLOBAL_Control;
    }
  }
  if ( pECB->cbTotalBytes > 0xA00000 )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 108) & 1) != 0 )
      WPP_SF_dd(v3[12], 59, &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids);
    v17 = "Requested HTTP Body is greater than xHTTPBodySizeMaxValue";
    exception::exception((exception *)pExceptionObject, &v17);
    throw (exception *)pExceptionObject;
  }
  if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD *))ValidateMemoryLimit)(v3) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 60);
    v17 = "Memory consumption has crossed the maximum allowance";
    exception::exception((exception *)v22, &v17);
    throw (exception *)v22;
  }
  v16 = 0;
  v5 = (const char *)MmAllocate(0x2828u);
  v6 = (Context *)v5;
  v17 = v5;
  if ( v5 )
  {
    memset_0((void *)(v5 + 16), 0, 0x2818u);
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    std::vector<char>::_Construct_n((char *)v6 + 16);
    *((_QWORD *)v6 + 6) = (char *)v6 + 64;
    *((_QWORD *)v6 + 7) = 2048;
    *((_QWORD *)v6 + 264) = 0;
    *((_QWORD *)v6 + 265) = 0;
    std::vector<char>::_Construct_n((char *)v6 + 2128);
    *(_QWORD *)(v7 + 48) = v7 + 64;
    *(_QWORD *)(v7 + 56) = 8096;
  }
  v19 = v6;
  UtlSprintfAppend<CPreAllocatedResizeBuffer<char>,char>(v6, "%s ", pECB->lpszMethod);
  AppendVariable((__int64)pECB, (__int64)"URL", (__int64 *)v6);
  UtlSprintfAppend<CPreAllocatedResizeBuffer<char>,char>(v6, " HTTP/1.1\r\n");
  AppendVariable((__int64)pECB, (__int64)"ALL_RAW", (__int64 *)v6);
  UtlSprintfAppend<CPreAllocatedResizeBuffer<char>,char>(v6, "\r\n");
  *((_QWORD *)v6 + 1284) = (char *)v6 + 2112;
  CPreAllocatedResizeBuffer<unsigned char>::append((__int64 *)v6 + 264, pECB->lpbData, pECB->cbAvailable);
  v8 = (_QWORD *)*((_QWORD *)v6 + 1284);
  if ( !v8[6] )
    ++v8;
  if ( *v8 >= (unsigned __int64)pECB->cbTotalBytes )
  {
    if ( !(unsigned int)HandleEndOfRead(v6, (__int64)pECB) )
    {
      Context::~Context(v6);
      free(v6);
      return 4;
    }
    Context::~Context(v6);
    free(v6);
    return v4;
  }
  if ( !((unsigned int (__fastcall *)(HCONN, __int64, void (__fastcall *)(struct _EXTENSION_CONTROL_BLOCK *, Context *, unsigned int, DWORD), _QWORD, Context *))pECB->ServerSupportFunction)(
          pECB->ConnID,
          1005,
          GetHttpBody,
          0,
          v6) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 61);
    exception::exception((exception *)v23);
    throw (exception *)v23;
  }
  LODWORD(v17) = AdjustBuffer((__int64)v6, (__int64)pECB);
  v16 = 2;
  v9 = (_QWORD *)*((_QWORD *)v6 + 1284);
  v10 = v9[6];
  if ( v10 )
    v11 = v10 + *v9;
  else
    v11 = v9[1] + v9[3];
  if ( !((unsigned int (__fastcall *)(HCONN, __int64, __int64, const char **, DWORD *))pECB->ServerSupportFunction)(
          pECB->ConnID,
          1010,
          v11,
          &v17,
          &v16) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 62);
    exception::exception((exception *)v24);
    throw (exception *)v24;
  }
  return 3;
}

```

## disassembly

```asm
0x18000d3e0  push    rbx
0x18000d3e2  push    rsi
0x18000d3e3  push    rdi
0x18000d3e4  push    r14
0x18000d3e6  sub     rsp, 918h
0x18000d3ed  mov     rax, cs:__security_cookie
0x18000d3f4  xor     rax, rsp
0x18000d3f7  mov     [rsp+938h+var_38], rax
0x18000d3ff  mov     r14, rcx
0x18000d402  mov     [rsp+938h+var_8F8], rcx
0x18000d407  mov     [rsp+938h+var_908], 64h ; 'd'
0x18000d40f  lea     r9, [rsp+938h+var_908]
0x18000d414  lea     r8, [rsp+938h+String1]
0x18000d41c  lea     rdx, aHttps; "HTTPS"
0x18000d423  mov     rcx, [rcx+8]
0x18000d427  mov     rax, [r14+0A0h]
0x18000d42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d433  test    eax, eax
0x18000d435  jnz     short loc_18000D485
0x18000d437  call    cs:__imp_GetLastError
0x18000d43d  lea     rsi, WPP_GLOBAL_Control
0x18000d444  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d44b  mov     edi, 1
0x18000d450  cmp     rcx, rsi
0x18000d453  jz      loc_18000D541
0x18000d459  test    [rcx+6Ch], dil
0x18000d45d  jz      loc_18000D541
0x18000d463  lea     edx, [rdi+2Dh]
0x18000d466  mov     r9d, eax
0x18000d469  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x18000d470  mov     rcx, [rcx+60h]
0x18000d474  call    WPP_SF_d
0x18000d479  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d480  jmp     loc_18000D541
0x18000d485  lea     rdx, String2; "on"
0x18000d48c  lea     rcx, [rsp+938h+String1]; String1
0x18000d494  call    cs:__imp__stricmp
0x18000d49a  test    eax, eax
0x18000d49c  jnz     short loc_18000D50E
0x18000d49e  lea     rsi, WPP_GLOBAL_Control
0x18000d4a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4ac  cmp     rcx, rsi
0x18000d4af  jz      short loc_18000D4C4
0x18000d4b1  test    byte ptr [rcx+6Ch], 4
0x18000d4b5  jz      short loc_18000D4C4
0x18000d4b7  lea     edx, [rax+2Fh]
0x18000d4ba  mov     rcx, [rcx+60h]
0x18000d4be  call    WPP_SF_
0x18000d4c3  nop
0x18000d4c4  mov     rcx, r14
0x18000d4c7  call    CheckAccessAllowed
0x18000d4cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4d3  cmp     rcx, rsi
0x18000d4d6  jz      short loc_18000D4F3
0x18000d4d8  test    byte ptr [rcx+6Ch], 4
0x18000d4dc  jz      short loc_18000D4F3
0x18000d4de  mov     edx, 39h ; '9'
0x18000d4e3  mov     rcx, [rcx+60h]
0x18000d4e7  call    WPP_SF_
0x18000d4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4f3  mov     edi, 1
0x18000d4f8  jmp     short loc_18000D541
0x18000d4fa  mov     edi, 4
0x18000d4ff  jmp     loc_18000D759
0x18000d504  mov     edi, 1
0x18000d509  jmp     loc_18000D759
0x18000d50e  lea     rsi, WPP_GLOBAL_Control
0x18000d515  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d51c  cmp     rcx, rsi
0x18000d51f  jz      short loc_18000D53C
0x18000d521  test    byte ptr [rcx+6Ch], 4
0x18000d525  jz      short loc_18000D53C
0x18000d527  mov     edx, 30h ; '0'
0x18000d52c  mov     rcx, [rcx+60h]
0x18000d530  call    WPP_SF_
0x18000d535  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d53c  mov     edi, 1
0x18000d541  mov     r9d, [r14+88h]
0x18000d548  mov     eax, 0A00000h
0x18000d54d  cmp     r9d, eax
0x18000d550  ja      loc_18000D786
0x18000d556  call    ValidateMemoryLimit
0x18000d55b  test    al, al
0x18000d55d  jz      loc_18000D7D7
0x18000d563  mov     [rsp+938h+var_908], 0
0x18000d56b  mov     ecx, 2828h; unsigned __int64
0x18000d570  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000d575  mov     rbx, rax
0x18000d578  mov     [rsp+938h+var_900], rax
0x18000d57d  test    rbx, rbx
0x18000d580  jz      short loc_18000D5EA
0x18000d582  lea     rcx, [rax+10h]; void *
0x18000d586  xor     edx, edx; Val
0x18000d588  mov     r8d, 2818h; Size
0x18000d58e  call    memset_0
0x18000d593  mov     qword ptr [rbx], 0
0x18000d59a  mov     qword ptr [rbx+8], 0
0x18000d5a2  lea     rcx, [rbx+10h]
0x18000d5a6  call    ?_Construct_n@?$vector@DV?$allocator@D@std@@@std@@QEAAX_KAEBD@Z; std::vector<char>::_Construct_n(unsigned __int64,char const &)
0x18000d5ab  lea     rax, [rbx+40h]
0x18000d5af  mov     [rbx+30h], rax
0x18000d5b3  mov     qword ptr [rbx+38h], 800h
0x18000d5bb  lea     rdx, [rbx+840h]
0x18000d5c2  mov     qword ptr [rdx], 0
0x18000d5c9  mov     qword ptr [rdx+8], 0
0x18000d5d1  lea     rcx, [rdx+10h]
0x18000d5d5  call    ?_Construct_n@?$vector@DV?$allocator@D@std@@@std@@QEAAX_KAEBD@Z; std::vector<char>::_Construct_n(unsigned __int64,char const &)
0x18000d5da  lea     rax, [rdx+40h]
0x18000d5de  mov     [rdx+30h], rax
0x18000d5e2  mov     qword ptr [rdx+38h], 1FA0h
0x18000d5ea  mov     [rsp+938h+var_8F0], rbx
0x18000d5ef  mov     r8, [r14+68h]
0x18000d5f3  lea     rdx, aS; "%s "
0x18000d5fa  mov     rcx, rbx
0x18000d5fd  call    ??$UtlSprintfAppend@V?$CPreAllocatedResizeBuffer@D@@D@@YA_KPEAV?$CPreAllocatedResizeBuffer@D@@PEBDZZ; UtlSprintfAppend<CPreAllocatedResizeBuffer<char>,char>(CPreAllocatedResizeBuffer<char> *,char const *,...)
0x18000d602  mov     r8, rbx
0x18000d605  lea     rdx, aUrl; "URL"
0x18000d60c  mov     rcx, r14
0x18000d60f  call    AppendVariable
0x18000d614  lea     rdx, aHttp11; " HTTP/1.1\r\n"
0x18000d61b  mov     rcx, rbx
0x18000d61e  call    ??$UtlSprintfAppend@V?$CPreAllocatedResizeBuffer@D@@D@@YA_KPEAV?$CPreAllocatedResizeBuffer@D@@PEBDZZ; UtlSprintfAppend<CPreAllocatedResizeBuffer<char>,char>(CPreAllocatedResizeBuffer<char> *,char const *,...)
0x18000d623  mov     r8, rbx
0x18000d626  lea     rdx, aAllRaw; "ALL_RAW"
0x18000d62d  mov     rcx, r14
0x18000d630  call    AppendVariable
0x18000d635  lea     rdx, asc_1800131E8; "\r\n"
0x18000d63c  mov     rcx, rbx
0x18000d63f  call    ??$UtlSprintfAppend@V?$CPreAllocatedResizeBuffer@D@@D@@YA_KPEAV?$CPreAllocatedResizeBuffer@D@@PEBDZZ; UtlSprintfAppend<CPreAllocatedResizeBuffer<char>,char>(CPreAllocatedResizeBuffer<char> *,char const *,...)
0x18000d644  lea     rcx, [rbx+840h]
0x18000d64b  mov     [rbx+2820h], rcx
0x18000d652  mov     r8d, [r14+8Ch]
0x18000d659  mov     rdx, [r14+90h]
0x18000d660  call    ?append@?$CPreAllocatedResizeBuffer@E@@QEAAXPEBE_K@Z; CPreAllocatedResizeBuffer<uchar>::append(uchar const *,unsigned __int64)
0x18000d665  mov     rcx, [rbx+2820h]
0x18000d66c  lea     rax, [rcx+8]
0x18000d670  cmp     qword ptr [rcx+30h], 0
0x18000d675  cmovz   rcx, rax
0x18000d679  mov     eax, [r14+88h]
0x18000d680  cmp     [rcx], rax
0x18000d683  jnb     loc_18000D71F
0x18000d689  mov     [rsp+938h+var_918], rbx
0x18000d68e  xor     r9d, r9d
0x18000d691  lea     r8, ?GetHttpBody@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z; GetHttpBody(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong)
0x18000d698  mov     edx, 3EDh
0x18000d69d  mov     rcx, [r14+8]
0x18000d6a1  mov     rax, [r14+0B8h]
0x18000d6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ad  test    eax, eax
0x18000d6af  jz      loc_18000D825
0x18000d6b5  mov     rdx, r14
0x18000d6b8  mov     rcx, rbx
0x18000d6bb  call    AdjustBuffer
0x18000d6c0  mov     dword ptr [rsp+938h+var_900], eax
0x18000d6c4  mov     [rsp+938h+var_908], 2
0x18000d6cc  mov     rax, [rbx+2820h]
0x18000d6d3  mov     rcx, [rax+30h]
0x18000d6d7  test    rcx, rcx
0x18000d6da  jz      short loc_18000D6E4
0x18000d6dc  mov     r8, [rax]
0x18000d6df  add     r8, rcx
0x18000d6e2  jmp     short loc_18000D6EC
0x18000d6e4  mov     r8, [rax+18h]
0x18000d6e8  add     r8, [rax+8]
0x18000d6ec  lea     rax, [rsp+938h+var_908]
0x18000d6f1  mov     [rsp+938h+var_918], rax
0x18000d6f6  lea     r9, [rsp+938h+var_900]
0x18000d6fb  mov     edx, 3F2h
0x18000d700  mov     rcx, [r14+8]
0x18000d704  mov     rax, [r14+0B8h]
0x18000d70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d710  test    eax, eax
0x18000d712  jz      loc_18000D865
0x18000d718  mov     eax, 3
0x18000d71d  jmp     short loc_18000D769
0x18000d71f  mov     rdx, r14
0x18000d722  mov     rcx, rbx
0x18000d725  call    HandleEndOfRead
0x18000d72a  nop
0x18000d72b  mov     rcx, rbx; this
0x18000d72e  test    eax, eax
0x18000d730  jnz     short loc_18000D749
0x18000d732  call    ??1Context@@QEAA@XZ; Context::~Context(void)
0x18000d737  nop
0x18000d738  mov     rcx, rbx; Block
0x18000d73b  call    cs:__imp_free
0x18000d741  nop
0x18000d742  mov     eax, 4
0x18000d747  jmp     short loc_18000D769
0x18000d749  call    ??1Context@@QEAA@XZ; Context::~Context(void)
0x18000d74e  nop
0x18000d74f  mov     rcx, rbx; Block
0x18000d752  call    cs:__imp_free
0x18000d758  nop
0x18000d759  jmp     short loc_18000D767
0x18000d75b  mov     eax, 4
0x18000d760  jmp     short loc_18000D769
0x18000d762  mov     edi, 1
0x18000d767  mov     eax, edi
0x18000d769  mov     rcx, [rsp+938h+var_38]
0x18000d771  xor     rcx, rsp; StackCookie
0x18000d774  call    __security_check_cookie
0x18000d779  add     rsp, 918h
0x18000d780  pop     r14
0x18000d782  pop     rdi
0x18000d783  pop     rsi
0x18000d784  pop     rbx
0x18000d785  retn
0x18000d786  cmp     rcx, rsi
0x18000d789  jz      short loc_18000D7AA
0x18000d78b  test    [rcx+6Ch], dil
0x18000d78f  jz      short loc_18000D7AA
0x18000d791  mov     edx, 3Bh ; ';'
0x18000d796  mov     dword ptr [rsp+938h+var_918], eax
0x18000d79a  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x18000d7a1  mov     rcx, [rcx+60h]
0x18000d7a5  call    WPP_SF_dd
0x18000d7aa  lea     rax, aRequestedHttpB; "Requested HTTP Body is greater than xHT"...
0x18000d7b1  mov     [rsp+938h+var_900], rax
0x18000d7b6  lea     rdx, [rsp+938h+var_900]
0x18000d7bb  lea     rcx, [rsp+938h+pExceptionObject]
0x18000d7c0  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18000d7c6  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18000d7cd  lea     rcx, [rsp+938h+pExceptionObject]; pExceptionObject
0x18000d7d2  call    _CxxThrowException_0
0x18000d7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7de  cmp     rcx, rsi
0x18000d7e1  jz      short loc_18000D7F7
0x18000d7e3  test    [rcx+6Ch], dil
0x18000d7e7  jz      short loc_18000D7F7
0x18000d7e9  mov     edx, 3Ch ; '<'
0x18000d7ee  mov     rcx, [rcx+60h]
0x18000d7f2  call    WPP_SF_
0x18000d7f7  lea     rax, aMemoryConsumpt; "Memory consumption has crossed the maxi"...
0x18000d7fe  mov     [rsp+938h+var_900], rax
0x18000d803  lea     rdx, [rsp+938h+var_900]
0x18000d808  lea     rcx, [rsp+938h+var_8C8]
0x18000d80d  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18000d813  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18000d81a  lea     rcx, [rsp+938h+var_8C8]; pExceptionObject
0x18000d81f  call    _CxxThrowException_0
0x18000d825  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d82c  cmp     rcx, rsi
0x18000d82f  jz      short loc_18000D843
0x18000d831  test    [rcx+6Ch], dil
0x18000d835  jz      short loc_18000D843
0x18000d837  lea     edx, [rax+3Dh]
0x18000d83a  mov     rcx, [rcx+60h]
0x18000d83e  call    WPP_SF_
0x18000d843  lea     rcx, [rsp+938h+var_8B0]
0x18000d84b  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x18000d851  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18000d858  lea     rcx, [rsp+938h+var_8B0]; pExceptionObject
0x18000d860  call    _CxxThrowException_0
0x18000d865  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d86c  cmp     rcx, rsi
0x18000d86f  jz      short loc_18000D883
0x18000d871  test    [rcx+6Ch], dil
0x18000d875  jz      short loc_18000D883
0x18000d877  lea     edx, [rax+3Eh]
0x18000d87a  mov     rcx, [rcx+60h]
0x18000d87e  call    WPP_SF_
0x18000d883  lea     rcx, [rsp+938h+var_898]
0x18000d88b  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x18000d891  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18000d898  lea     rcx, [rsp+938h+var_898]; pExceptionObject
0x18000d8a0  call    _CxxThrowException_0
```
