# CStowedExceptionPlugin::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x1400533b0`
- end: `0x14005389f`
- name: `?Initialize@CStowedExceptionPlugin@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `1263`
- prototype: `__int64 __fastcall(CStowedExceptionPlugin *__hidden this, struct WER_PLUGIN_INIT_IN *, unsigned int, HINSTANCE)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400054e4`
- `0x14000ca20`
- `0x140014a88`
- `0x1400166ec`
- `0x14005238c`
- `0x140052568`
- `0x1400525c4`
- `0x1400529b0`
- `0x140052cdc`
- `0x140052f18`
- `0x140053158`
- `0x1400533b0`
- `0x140053d88`
- `0x14005f564`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400534dd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140053556`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140053592`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14005381e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400534dd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140053556`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140053592`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14005381e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1400537ec`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1400537ec`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x140053877`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x140053877`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStowedExceptionPlugin::Initialize(
        CStowedExceptionPlugin *this,
        struct WER_PLUGIN_INIT_IN *a2,
        __int64 a3,
        HINSTANCE a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rax
  char *v11; // r15
  unsigned int v12; // edi
  unsigned int i; // r14d
  int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // r9d
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // edi
  unsigned int v22; // ecx
  void ***j; // rax
  void **v24; // rdi
  void ***k; // rax
  int v26; // eax
  _WORD *v27; // rdx
  __int64 v28; // r8
  int v29; // eax
  unsigned int v30; // r12d
  void *v31; // rdi
  SIZE_T *lpNumberOfBytesRead; // [rsp+20h] [rbp-58h]
  unsigned int v34[2]; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-40h] BYREF
  void *Buffer; // [rsp+40h] [rbp-38h] BYREF
  void *v37[6]; // [rsp+48h] [rbp-30h] BYREF
  unsigned int v38; // [rsp+C8h] [rbp+50h] BYREF

  NumberOfBytesRead = 0;
  memset(v37, 0, 40);
  Buffer = 0;
  v38 = 0;
  v34[0] = 0;
  if ( wcscmp_0(*(const wchar_t **)a2, L"APPCRASH") && wcscmp_0(*(const wchar_t **)a2, L"MoAppCrash") )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8, v9);
  if ( *((_DWORD *)a2 + 63) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8, v9);
  if ( !*((_QWORD *)a2 + 38) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8, v9);
  if ( !*((_DWORD *)a2 + 70) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8, v9);
  if ( !*((_QWORD *)a2 + 36) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8, v9);
  v10 = *((_QWORD *)a2 + 36);
  if ( *(_DWORD *)v10 == -1073741189 && *(_DWORD *)(v10 + 24) == 2 )
  {
    v11 = *(char **)(v10 + 32);
    if ( v11 )
    {
      v12 = *(_DWORD *)(v10 + 40);
      if ( v12 )
      {
        *((_DWORD *)this + 68) = *((_DWORD *)a2 + 70);
        if ( v12 >= 0x100 )
          v12 = 256;
        CStowedExceptionPlugin::AddMemoryBlock(this, v11, 8 * v12, v9);
        for ( i = 0; i < v12; ++i )
        {
          if ( ReadProcessMemory(*((HANDLE *)a2 + 38), &v11[8 * i], &Buffer, 8u, &NumberOfBytesRead) )
          {
            if ( NumberOfBytesRead == 8 )
            {
              v14 = CStowedExceptionPlugin::AddBlocksForStructure(this, *((void **)a2 + 38), Buffer);
              if ( v14 < 0
                && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v15, Buffer, v14);
              }
            }
          }
        }
        if ( ReadProcessMemory(*((HANDLE *)a2 + 38), v11, &Buffer, 8u, &NumberOfBytesRead)
          && NumberOfBytesRead == 8
          && ReadProcessMemory(*((HANDLE *)a2 + 38), Buffer, v37, 0x28u, &NumberOfBytesRead)
          && NumberOfBytesRead == 40
          && LODWORD(v37[0]) >= 0x28
          && (unsigned int)(HIDWORD(v37[0]) - 1397043249) <= 1 )
        {
          tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            (char *)this + 136,
            L"%08x",
            LODWORD(v37[1]));
          if ( (BYTE4(v37[1]) & 3) == 1 )
          {
            CStowedExceptionPlugin::BuildLoadedModuleList(
              (char *)this + 224,
              *((_QWORD *)a2 + 38),
              *((unsigned int *)a2 + 70));
            CStowedExceptionPlugin::BuildUnloadedModuleList((char *)this + 248, *((_QWORD *)a2 + 38));
            if ( v37[2] )
            {
              for ( j = (void ***)*((_QWORD *)this + 28); j != *((void ****)this + 29); ++j )
              {
                v24 = *j;
                if ( **j <= v37[2] && v37[2] < (char *)*v24 + *((unsigned int *)v24 + 2) )
                  goto LABEL_57;
              }
              for ( k = (void ***)*((_QWORD *)this + 31); k != *((void ****)this + 32); ++k )
              {
                v24 = *k;
                if ( **k <= v37[2] && v37[2] < (char *)*v24 + *((unsigned int *)v24 + 2) )
                {
                  v26 = 0;
                  goto LABEL_56;
                }
              }
              v24 = 0;
              v26 = -2147023728;
LABEL_56:
              if ( v26 >= 0 )
              {
LABEL_57:
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (char *)this + 8,
                  L"%016I64x",
                  (char *)v37[2] - (char *)*v24);
                v27 = v24[3];
                if ( v27 )
                {
                  v28 = -1;
                  do
                    ++v28;
                  while ( v27[v28] );
                }
                utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                  (char *)this + 40,
                  v27);
                if ( ((_BYTE)v24[4] & 1) != 0 )
                  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                    (char *)this + 40,
                    L"_unloaded",
                    9);
                LODWORD(lpNumberOfBytesRead) = *((unsigned __int16 *)v24 + 10);
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (char *)this + 72,
                  L"%u.%u.%u.%u",
                  *((unsigned __int16 *)v24 + 8),
                  *((unsigned __int16 *)v24 + 9),
                  lpNumberOfBytesRead,
                  *((unsigned __int16 *)v24 + 11));
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (char *)this + 104,
                  L"%08x",
                  *((unsigned int *)v24 + 3));
                return 0;
              }
            }
            if ( LODWORD(v37[3]) == 8 )
            {
              v29 = HIDWORD(v37[3]);
              if ( HIDWORD(v37[3]) )
              {
                if ( v37[4] )
                {
                  if ( HIDWORD(v37[3]) > 0xFFFF )
                    v29 = 0xFFFF;
                  v30 = 8 * v29;
                  v31 = VirtualAlloc(0, (unsigned int)(8 * v29), 0x1000u, 4u);
                  *(_QWORD *)v34 = v31;
                  if ( v31
                    && ReadProcessMemory(*((HANDLE *)a2 + 38), v37[4], v31, v30, &NumberOfBytesRead)
                    && NumberOfBytesRead )
                  {
                    CStowedExceptionPlugin::HashStackTrace(&v38, (__int64)this + 248);
                    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                      (char *)this + 168,
                      L"StackHash12_%03x",
                      v38);
                  }
                  if ( v31 )
                    VirtualFree(v31, 0, 0x8000u);
                }
              }
            }
            return 0;
          }
          if ( (BYTE4(v37[1]) & 3) == 2 )
          {
            v17 = CStowedExceptionPlugin::CalculateRemoteStringLength(v34, *((void **)a2 + 38), v37[2], v16);
            if ( v17 >= 0 )
            {
              v21 = v34[0];
              if ( 2 * (unsigned __int64)v34[0] > 0xFFFF )
                MicrosoftTelemetryAssertTriggeredNoArgs(0xFFFF, v18, v19, v20);
              v22 = 2 * v21;
              if ( !(2 * v21) )
                return 0;
              goto LABEL_41;
            }
            if ( v17 == -805306106 )
            {
              v22 = 0xFFFF;
LABEL_41:
              if ( (int)CStowedExceptionPlugin::HashRemoteMemory(&v38, *((HANDLE *)a2 + 38), v37[2], v22) >= 0 )
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (char *)this + 168,
                  L"TextHash12_%03x",
                  v38);
            }
          }
        }
        return 0;
      }
    }
  }
  return 2147942450LL;
}

```

## disassembly

```asm
0x1400533b0  push    rbp
0x1400533b2  push    rbx
0x1400533b3  push    rsi
0x1400533b4  push    rdi
0x1400533b5  push    r12
0x1400533b7  push    r13
0x1400533b9  push    r14
0x1400533bb  push    r15
0x1400533bd  mov     rbp, rsp
0x1400533c0  sub     rsp, 78h
0x1400533c4  mov     rbx, rdx
0x1400533c7  mov     rsi, rcx
0x1400533ca  xor     r13d, r13d
0x1400533cd  mov     [rbp+NumberOfBytesRead], r13
0x1400533d1  mov     [rbp+var_30], r13d
0x1400533d5  xorps   xmm0, xmm0
0x1400533d8  xor     eax, eax
0x1400533da  movups  xmmword ptr [rbp+var_2C], xmm0
0x1400533de  movups  xmmword ptr [rbp+lpBaseAddress], xmm0
0x1400533e2  mov     [rbp+var_C], eax
0x1400533e5  mov     [rbp+Buffer], r13
0x1400533e9  mov     [rbp+arg_8], r13d
0x1400533ed  mov     [rbp+var_48], r13d
0x1400533f1  lea     rdx, aAppcrash; "APPCRASH"
0x1400533f8  mov     rcx, [rbx]; String1
0x1400533fb  call    wcscmp_0
0x140053400  test    eax, eax
0x140053402  jz      short loc_14005341C
0x140053404  lea     rdx, aMoappcrash; "MoAppCrash"
0x14005340b  mov     rcx, [rbx]; String1
0x14005340e  call    wcscmp_0
0x140053413  test    eax, eax
0x140053415  jz      short loc_14005341C
0x140053417  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14005341c  cmp     dword ptr [rbx+0FCh], 1
0x140053423  jz      short loc_14005342A
0x140053425  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14005342a  cmp     [rbx+130h], r13
0x140053431  jnz     short loc_140053438
0x140053433  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140053438  cmp     [rbx+118h], r13d
0x14005343f  jnz     short loc_140053446
0x140053441  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140053446  cmp     [rbx+120h], r13
0x14005344d  jnz     short loc_140053454
0x14005344f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140053454  mov     rax, [rbx+120h]
0x14005345b  cmp     dword ptr [rax], 0C000027Bh
0x140053461  jnz     loc_140053888
0x140053467  cmp     dword ptr [rax+18h], 2
0x14005346b  jnz     loc_140053888
0x140053471  mov     r15, [rax+20h]
0x140053475  test    r15, r15
0x140053478  jz      loc_140053888
0x14005347e  mov     edi, [rax+28h]
0x140053481  test    edi, edi
0x140053483  jz      loc_140053888
0x140053489  mov     eax, [rbx+118h]
0x14005348f  mov     [rsi+110h], eax
0x140053495  mov     eax, 100h
0x14005349a  cmp     edi, eax
0x14005349c  cmovnb  edi, eax
0x14005349f  lea     r8d, ds:0[rdi*8]; unsigned int
0x1400534a7  mov     rdx, r15; void *
0x1400534aa  mov     rcx, rsi; this
0x1400534ad  call    ?AddMemoryBlock@CStowedExceptionPlugin@@AEAAJPEAXKK@Z; CStowedExceptionPlugin::AddMemoryBlock(void *,ulong,ulong)
0x1400534b2  mov     r14d, r13d
0x1400534b5  mov     r12d, 8
0x1400534bb  test    edi, edi
0x1400534bd  jz      short loc_14005353C
0x1400534bf  mov     eax, r14d
0x1400534c2  lea     rdx, [r15+rax*8]; lpBaseAddress
0x1400534c6  lea     rax, [rbp+NumberOfBytesRead]
0x1400534ca  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1400534cf  mov     r9, r12; nSize
0x1400534d2  lea     r8, [rbp+Buffer]; lpBuffer
0x1400534d6  mov     rcx, [rbx+130h]; hProcess
0x1400534dd  call    cs:__imp_ReadProcessMemory
0x1400534e4  nop     dword ptr [rax+rax+00h]
0x1400534e9  test    eax, eax
0x1400534eb  jz      short loc_140053534
0x1400534ed  cmp     [rbp+NumberOfBytesRead], r12
0x1400534f1  jnz     short loc_140053534
0x1400534f3  mov     r8, [rbp+Buffer]; void *
0x1400534f7  mov     rdx, [rbx+130h]; void *
0x1400534fe  mov     rcx, rsi; this
0x140053501  call    ?AddBlocksForStructure@CStowedExceptionPlugin@@AEAAJPEAX0@Z; CStowedExceptionPlugin::AddBlocksForStructure(void *,void *)
0x140053506  test    eax, eax
0x140053508  jns     short loc_140053534
0x14005350a  lea     rdx, WPP_GLOBAL_Control
0x140053511  mov     rcx, cs:WPP_GLOBAL_Control
0x140053518  cmp     rcx, rdx
0x14005351b  jz      short loc_140053534
0x14005351d  test    byte ptr [rcx+1Ch], 2
0x140053521  jz      short loc_140053534
0x140053523  mov     dword ptr [rsp+78h+lpNumberOfBytesRead], eax
0x140053527  mov     r9, [rbp+Buffer]
0x14005352b  mov     rcx, [rcx+10h]
0x14005352f  call    WPP_SF_qD
0x140053534  inc     r14d
0x140053537  cmp     r14d, edi
0x14005353a  jb      short loc_1400534BF
0x14005353c  lea     rax, [rbp+NumberOfBytesRead]
0x140053540  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140053545  mov     r9, r12; nSize
0x140053548  lea     r8, [rbp+Buffer]; lpBuffer
0x14005354c  mov     rdx, r15; lpBaseAddress
0x14005354f  mov     rcx, [rbx+130h]; hProcess
0x140053556  call    cs:__imp_ReadProcessMemory
0x14005355d  nop     dword ptr [rax+rax+00h]
0x140053562  test    eax, eax
0x140053564  jz      loc_140053884
0x14005356a  cmp     [rbp+NumberOfBytesRead], r12
0x14005356e  jnz     loc_140053884
0x140053574  lea     rax, [rbp+NumberOfBytesRead]
0x140053578  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14005357d  mov     r9d, 28h ; '('; nSize
0x140053583  lea     r8, [rbp+var_30]; lpBuffer
0x140053587  mov     rdx, [rbp+Buffer]; lpBaseAddress
0x14005358b  mov     rcx, [rbx+130h]; hProcess
0x140053592  call    cs:__imp_ReadProcessMemory
0x140053599  nop     dword ptr [rax+rax+00h]
0x14005359e  test    eax, eax
0x1400535a0  jz      loc_140053884
0x1400535a6  cmp     [rbp+NumberOfBytesRead], 28h ; '('
0x1400535ab  jnz     loc_140053884
0x1400535b1  cmp     [rbp+var_30], 28h ; '('
0x1400535b5  jb      loc_140053884
0x1400535bb  mov     eax, dword ptr [rbp+var_2C]
0x1400535be  add     eax, 0ACBACFCFh
0x1400535c3  cmp     eax, 1
0x1400535c6  ja      loc_140053884
0x1400535cc  lea     rcx, [rsi+88h]
0x1400535d3  mov     r8d, dword ptr [rbp+var_2C+4]
0x1400535d7  lea     rdx, a08x_0; "%08x"
0x1400535de  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400535e3  mov     eax, dword ptr [rbp+var_2C+8]
0x1400535e6  and     eax, 3
0x1400535e9  sub     eax, 1
0x1400535ec  jz      loc_14005367D
0x1400535f2  cmp     eax, 1
0x1400535f5  jnz     loc_140053884
0x1400535fb  mov     r8, [rbp+var_2C+0Ch]; void *
0x1400535ff  mov     rdx, [rbx+130h]; void *
0x140053606  lea     rcx, [rbp+var_48]; unsigned int *
0x14005360a  call    ?CalculateRemoteStringLength@CStowedExceptionPlugin@@CAJPEAKPEAX1K@Z; CStowedExceptionPlugin::CalculateRemoteStringLength(ulong *,void *,void *,ulong)
0x14005360f  test    eax, eax
0x140053611  js      short loc_140053637
0x140053613  mov     edi, [rbp+var_48]
0x140053616  mov     eax, edi
0x140053618  add     rax, rax
0x14005361b  mov     ecx, 0FFFFh
0x140053620  cmp     rax, rcx
0x140053623  jbe     short loc_14005362A
0x140053625  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14005362a  lea     ecx, [rdi+rdi]
0x14005362d  test    ecx, ecx
0x14005362f  jz      loc_140053884
0x140053635  jmp     short loc_140053647
0x140053637  cmp     eax, 0D0000106h
0x14005363c  jnz     loc_140053884
0x140053642  mov     ecx, 0FFFFh
0x140053647  mov     r9d, ecx; unsigned __int64
0x14005364a  mov     r8, [rbp+var_2C+0Ch]; void *
0x14005364e  mov     rdx, [rbx+130h]; hProcess
0x140053655  lea     rcx, [rbp+arg_8]; unsigned int *
0x140053659  call    ?HashRemoteMemory@CStowedExceptionPlugin@@CAJPEAKPEAX1_K@Z; CStowedExceptionPlugin::HashRemoteMemory(ulong *,void *,void *,unsigned __int64)
0x14005365e  test    eax, eax
0x140053660  js      loc_140053884
0x140053666  lea     rcx, [rsi+0A8h]
0x14005366d  mov     r8d, [rbp+arg_8]
0x140053671  lea     rdx, aTexthash1203x; "TextHash12_%03x"
0x140053678  jmp     loc_1400537A3
0x14005367d  lea     r14, [rsi+0E0h]
0x140053684  mov     r8d, [rbx+118h]
0x14005368b  mov     rdx, [rbx+130h]
0x140053692  mov     rcx, r14
0x140053695  call    ?BuildLoadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAXK@Z; CStowedExceptionPlugin::BuildLoadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *,ulong)
0x14005369a  lea     r15, [rsi+0F8h]
0x1400536a1  mov     rdx, [rbx+130h]
0x1400536a8  mov     rcx, r15
0x1400536ab  call    ?BuildUnloadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAX@Z; CStowedExceptionPlugin::BuildUnloadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *)
0x1400536b0  mov     r8, [rbp+var_2C+0Ch]
0x1400536b4  test    r8, r8
0x1400536b7  jz      loc_1400537AD
0x1400536bd  mov     rax, [r14]
0x1400536c0  cmp     rax, [r14+8]
0x1400536c4  jz      short loc_1400536DE
0x1400536c6  mov     rdi, [rax]
0x1400536c9  cmp     [rdi], r8
0x1400536cc  ja      short loc_1400536D9
0x1400536ce  mov     ecx, [rdi+8]
0x1400536d1  add     rcx, [rdi]
0x1400536d4  cmp     r8, rcx
0x1400536d7  jb      short loc_140053714
0x1400536d9  add     rax, r12
0x1400536dc  jmp     short loc_1400536C0
0x1400536de  mov     rax, [r15]
0x1400536e1  cmp     rax, [r15+8]
0x1400536e5  jz      short loc_140053704
0x1400536e7  mov     rdi, [rax]
0x1400536ea  cmp     [rdi], r8
0x1400536ed  ja      short loc_1400536FA
0x1400536ef  mov     ecx, [rdi+8]
0x1400536f2  add     rcx, [rdi]
0x1400536f5  cmp     r8, rcx
0x1400536f8  jb      short loc_1400536FF
0x1400536fa  add     rax, r12
0x1400536fd  jmp     short loc_1400536E1
0x1400536ff  mov     eax, r13d
0x140053702  jmp     short loc_14005370C
0x140053704  mov     rdi, r13
0x140053707  mov     eax, 80070490h
0x14005370c  test    eax, eax
0x14005370e  js      loc_1400537AD
0x140053714  sub     r8, [rdi]
0x140053717  lea     rcx, [rsi+8]
0x14005371b  lea     rdx, a016i64x; "%016I64x"
0x140053722  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140053727  mov     rdx, [rdi+18h]
0x14005372b  test    rdx, rdx
0x14005372e  jz      short loc_140053740
0x140053730  or      r8, 0FFFFFFFFFFFFFFFFh
0x140053734  inc     r8
0x140053737  cmp     [rdx+r8*2], r13w
0x14005373c  jnz     short loc_140053734
0x14005373e  jmp     short loc_140053743
0x140053740  mov     r8, r13
0x140053743  lea     rcx, [rsi+28h]
0x140053747  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14005374c  test    byte ptr [rdi+20h], 1
0x140053750  jz      short loc_140053768
0x140053752  mov     r8d, 9
0x140053758  lea     rdx, SubStr; "_unloaded"
0x14005375f  lea     rcx, [rsi+28h]
0x140053763  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140053768  movzx   eax, word ptr [rdi+16h]
0x14005376c  movzx   r10d, word ptr [rdi+14h]
0x140053771  movzx   r9d, word ptr [rdi+12h]
0x140053776  movzx   r8d, word ptr [rdi+10h]
0x14005377b  lea     rcx, [rsi+48h]
0x14005377f  mov     [rsp+78h+var_50], eax
0x140053783  mov     dword ptr [rsp+78h+lpNumberOfBytesRead], r10d
0x140053788  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x14005378f  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140053794  lea     rcx, [rsi+68h]
0x140053798  mov     r8d, [rdi+0Ch]
0x14005379c  lea     rdx, a08x_0; "%08x"
0x1400537a3  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400537a8  jmp     loc_140053884
0x1400537ad  cmp     dword ptr [rbp+lpBaseAddress+4], r12d
0x1400537b1  jnz     loc_140053884
0x1400537b7  mov     eax, dword ptr [rbp+lpBaseAddress+8]
0x1400537ba  test    eax, eax
0x1400537bc  jz      loc_140053884
0x1400537c2  cmp     [rbp+lpBaseAddress+0Ch], r13
0x1400537c6  jz      loc_140053884
0x1400537cc  mov     ecx, 0FFFFh
0x1400537d1  cmp     eax, ecx
0x1400537d3  cmova   eax, ecx
0x1400537d6  shl     eax, 3
0x1400537d9  mov     r12d, eax
0x1400537dc  mov     r9d, 4; flProtect
0x1400537e2  mov     r8d, 1000h; flAllocationType
0x1400537e8  mov     edx, eax; dwSize
0x1400537ea  xor     ecx, ecx; lpAddress
0x1400537ec  call    cs:__imp_VirtualAlloc
0x1400537f3  nop     dword ptr [rax+rax+00h]
0x1400537f8  mov     rdi, rax
0x1400537fb  mov     qword ptr [rbp+var_48], rax
0x1400537ff  test    rax, rax
0x140053802  jz      short loc_140053867
0x140053804  lea     rax, [rbp+NumberOfBytesRead]
0x140053808  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14005380d  mov     r9d, r12d; nSize
0x140053810  mov     r8, rdi; lpBuffer
0x140053813  mov     rdx, [rbp+lpBaseAddress+0Ch]; lpBaseAddress
0x140053817  mov     rcx, [rbx+130h]; hProcess
0x14005381e  call    cs:__imp_ReadProcessMemory
0x140053825  nop     dword ptr [rax+rax+00h]
0x14005382a  test    eax, eax
0x14005382c  jz      short loc_140053867
0x14005382e  mov     rdx, [rbp+NumberOfBytesRead]
0x140053832  test    rdx, rdx
0x140053835  jz      short loc_140053867
0x140053837  shr     rdx, 3
0x14005383b  mov     [rsp+78h+lpNumberOfBytesRead], r15; __int64
0x140053840  mov     r9, r14
0x140053843  mov     r8, rdi
0x140053846  lea     rcx, [rbp+arg_8]; unsigned int *
0x14005384a  call    ?HashStackTrace@CStowedExceptionPlugin@@CAJPEAKKPEAPEAXPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@2@Z; CStowedExceptionPlugin::HashStackTrace(ulong *,ulong,void * *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *)
0x14005384f  lea     rcx, [rsi+0A8h]
0x140053856  mov     r8d, [rbp+arg_8]
0x14005385a  lea     rdx, aStackhash1203x; "StackHash12_%03x"
0x140053861  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140053866  nop
0x140053867  test    rdi, rdi
0x14005386a  jz      short loc_140053884
0x14005386c  xor     edx, edx; dwSize
0x14005386e  mov     r8d, 8000h; dwFreeType
  ... truncated ...
```
