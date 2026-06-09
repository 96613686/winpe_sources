# Uev::CreateProcNotificationListener::CreateProcNotificationListener(void)

- ea: `0x1400125ac`
- end: `0x140012a0d`
- name: `??0CreateProcNotificationListener@Uev@@QEAA@XZ`
- size: `1121`
- prototype: `Uev::CreateProcNotificationListener *__fastcall(Uev::CreateProcNotificationListener *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000b2e0`

## callees

- `0x140003e50`
- `0x140004a6c`
- `0x140004a78`
- `0x14000ba60`
- `0x14000c1cc`
- `0x14000c2b8`
- `0x14000c3a4`
- `0x1400125ac`
- `0x14001a8a4`
- `0x14001aff0`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x140012721`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x140012721`

## string_xrefs

- `0x14001263e`: `\UevConnectCreateNotifyPort`
- `0x140012881`: `\system32\mavinject.exe`
- `0x1400127fd`: `\syswow64\Microsoft.Uev.AppAgent.dll`
- `0x140012912`: `\system32\Microsoft.Uev.AppAgent.dll`

## pseudocode

```c
Uev::CreateProcNotificationListener *__fastcall Uev::CreateProcNotificationListener::CreateProcNotificationListener(
        Uev::CreateProcNotificationListener *this)
{
  Uev::CreateProcNotificationListener *v1; // r12
  int v2; // ebx
  char *v3; // rcx
  unsigned __int64 v4; // r13
  __int64 v5; // r8
  unsigned __int64 v6; // rdx
  char *v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r8
  void **v10; // r14
  unsigned __int64 v11; // rdx
  char *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // r8
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rax
  char *v17; // rax
  __int64 v18; // rbx
  __int64 v19; // r8
  char *v20; // rdi
  char *v21; // rax
  char *v22; // rdx
  __int64 ShortPathNameW; // rbx
  char *v24; // rdx
  __int64 v25; // rbx
  char *v27; // [rsp+20h] [rbp-2A8h]
  char *v28; // [rsp+20h] [rbp-2A8h]
  char *Src; // [rsp+30h] [rbp-298h]
  _BYTE v31[32]; // [rsp+38h] [rbp-290h] BYREF
  void *v32; // [rsp+58h] [rbp-270h]
  _QWORD *v33; // [rsp+60h] [rbp-268h]
  Uev::UevException *v34; // [rsp+68h] [rbp-260h] BYREF
  Uev::UevException *v35; // [rsp+70h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-248h] BYREF

  v1 = this;
  v2 = *((_DWORD *)this + 72);
  *(_QWORD *)this = &Uev::NotificationListener::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 20) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 8;
  v3 = (char *)this + 112;
  *(_OWORD *)v3 = 0;
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 3) = 0;
  std::wstring::_Construct<1,wchar_t *>(v3, L"\\UevConnectCreateNotifyPort", 27);
  *((_DWORD *)v1 + 36) = v2 + 500;
  v4 = -1;
  *((_QWORD *)v1 + 19) = -1;
  *(_QWORD *)v1 = &Uev::CreateProcNotificationListener::`vftable';
  *((_OWORD *)v1 + 10) = 0;
  *((_QWORD *)v1 + 22) = 0;
  *((_QWORD *)v1 + 23) = 7;
  *((_WORD *)v1 + 80) = 0;
  *((_OWORD *)v1 + 12) = 0;
  *((_QWORD *)v1 + 26) = 0;
  *((_QWORD *)v1 + 27) = 7;
  *((_WORD *)v1 + 96) = 0;
  *((_OWORD *)v1 + 14) = 0;
  *((_QWORD *)v1 + 30) = 0;
  *((_QWORD *)v1 + 31) = 7;
  *((_WORD *)v1 + 112) = 0;
  v32 = (char *)v1 + 256;
  *((_OWORD *)v1 + 16) = 0;
  *((_QWORD *)v1 + 34) = 0;
  *((_QWORD *)v1 + 35) = 7;
  *((_WORD *)v1 + 128) = 0;
  *((_DWORD *)v1 + 72) = Uev::Util::GetDwordConfigValue(L"FilterSendMsgTimeout", 0x2710u);
  *((_DWORD *)v1 + 73) = Uev::Util::GetDwordConfigValue(L"TimeToWaitBeforeInject", 0);
  memset_0(Buffer, 0, 0x208u);
  GetSystemWindowsDirectoryW(Buffer, 0x104u);
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  if ( v6 > *((_QWORD *)v1 + 23) )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char *)v1 + 160,
      v6,
      v5,
      Buffer);
  }
  else
  {
    if ( *((_QWORD *)v1 + 23) <= 7u )
      v7 = (char *)v1 + 160;
    else
      v7 = (char *)*((_QWORD *)v1 + 20);
    *((_QWORD *)v1 + 22) = v6;
    v8 = 2 * v6;
    memmove_0(v7, Buffer, 2 * v6);
    *(_WORD *)&v7[v8] = 0;
  }
  std::wstring::_Append<wchar_t>((char *)v1 + 160);
  v10 = (void **)((char *)v1 + 192);
  v11 = -1;
  do
    ++v11;
  while ( Buffer[v11] );
  if ( v11 > *((_QWORD *)v1 + 27) )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char *)v1 + 192,
      v11,
      v9,
      Buffer);
  }
  else
  {
    if ( *((_QWORD *)v1 + 27) <= 7u )
      v12 = (char *)v1 + 192;
    else
      v12 = (char *)*v10;
    *((_QWORD *)v1 + 26) = v11;
    v13 = 2 * v11;
    memmove_0(v12, Buffer, 2 * v11);
    *(_WORD *)&v12[v13] = 0;
  }
  std::wstring::_Append<wchar_t>((char *)v1 + 192);
  v15 = -1;
  do
    ++v15;
  while ( Buffer[v15] );
  v16 = *((_QWORD *)v1 + 31);
  if ( v15 > v16 )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char *)v1 + 224,
      v15,
      v14,
      Buffer);
  }
  else
  {
    if ( v16 <= 7 )
      v17 = (char *)v1 + 224;
    else
      v17 = (char *)*((_QWORD *)v1 + 28);
    v27 = v17;
    *((_QWORD *)v1 + 30) = v15;
    v18 = 2 * v15;
    memmove_0(v17, Buffer, 2 * v15);
    *(_WORD *)&v27[v18] = 0;
  }
  std::wstring::_Append<wchar_t>((char *)v1 + 224);
  v20 = (char *)v1 + 256;
  Src = (char *)v1 + 256;
  do
    ++v4;
  while ( Buffer[v4] );
  v33 = (_QWORD *)((char *)v1 + 280);
  if ( v4 > *((_QWORD *)v1 + 35) )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char *)v1 + 256,
      v4,
      v19,
      Buffer);
  }
  else
  {
    if ( *((_QWORD *)v1 + 35) <= 7u )
      v21 = (char *)v1 + 256;
    else
      v21 = *(char **)v20;
    v28 = v21;
    *((_QWORD *)v1 + 34) = v4;
    memmove_0(v21, Buffer, 2 * v4);
    *(_WORD *)&v28[2 * v4] = 0;
  }
  std::wstring::_Append<wchar_t>(v32);
  try
  {
    if ( *((_QWORD *)v1 + 27) <= 7u )
      v22 = (char *)v1 + 192;
    else
      v22 = (char *)*v10;
    ShortPathNameW = Uev::Util::GetShortPathNameW(v31, v22);
    if ( v10 != (void **)ShortPathNameW )
    {
      std::wstring::_Tidy_deallocate((char *)v1 + 192);
      *(_OWORD *)v10 = *(_OWORD *)ShortPathNameW;
      *((_OWORD *)v1 + 13) = *(_OWORD *)(ShortPathNameW + 16);
      *(_QWORD *)(ShortPathNameW + 16) = 0;
      *(_QWORD *)(ShortPathNameW + 24) = 7;
      *(_WORD *)ShortPathNameW = 0;
    }
    std::wstring::_Tidy_deallocate(v31);
  }
  catch ( Uev::UevException *v34 )
  {
    std::wstring::wstring(v31, (char *)v34 + 24);
    DbgTraceFrmtErr<wchar_t const *>((wchar_t *)L"AgentService.CreateProcNotificationListener::Constructor: Error creating"
                                                 " short-form file name for injected DLL (32-bit): %s");
    std::wstring::_Tidy_deallocate(v31);
    v1 = this;
    v20 = Src;
  }
  catch ( ... )
  {
    DbgTrace<2>(
      L"AgentService.CreateProcNotificationListener::Constructor: Error creating short-form file name for injected DLL (32-bit)");
    v1 = this;
    v20 = Src;
  }
  if ( *v33 <= 7u )
    v24 = v20;
  else
    v24 = *(char **)v20;
  try
  {
    v25 = Uev::Util::GetShortPathNameW(v31, v24);
    if ( v20 != (char *)v25 )
    {
      std::wstring::_Tidy_deallocate(v20);
      *(_OWORD *)v20 = *(_OWORD *)v25;
      *((_OWORD *)v20 + 1) = *(_OWORD *)(v25 + 16);
      *(_QWORD *)(v25 + 16) = 0;
      *(_QWORD *)(v25 + 24) = 7;
      *(_WORD *)v25 = 0;
    }
    std::wstring::_Tidy_deallocate(v31);
  }
  catch ( Uev::UevException *v35 )
  {
    std::wstring::wstring(v31, (char *)v35 + 24);
    DbgTraceFrmtErr<wchar_t const *>((wchar_t *)L"AgentService.CreateProcNotificationListener::Constructor: Error creating"
                                                 " short-form file name for injected DLL (64-bit): %s");
    std::wstring::_Tidy_deallocate(v31);
    return this;
  }
  catch ( ... )
  {
    DbgTrace<2>(
      L"AgentService.CreateProcNotificationListener::Constructor: Error creating short-form file name for injected DLL (64-bit)");
    return this;
  }
  return v1;
}

```

## disassembly

```asm
0x1400125ac  mov     [rsp+arg_8], rbx
0x1400125b1  mov     [rsp+arg_10], rsi
0x1400125b6  push    rdi
0x1400125b7  push    r12
0x1400125b9  push    r13
0x1400125bb  push    r14
0x1400125bd  push    r15
0x1400125bf  sub     rsp, 2A0h
0x1400125c6  mov     rax, cs:__security_cookie
0x1400125cd  xor     rax, rsp
0x1400125d0  mov     [rsp+2C8h+var_38], rax
0x1400125d8  mov     r12, rcx
0x1400125db  mov     [rsp+2C8h+var_2A0], rcx
0x1400125e0  xor     esi, esi
0x1400125e2  mov     ebx, [rcx+120h]
0x1400125e8  lea     rax, ??_7NotificationListener@Uev@@6B@; const Uev::NotificationListener::`vftable'
0x1400125ef  mov     [rcx], rax
0x1400125f2  mov     [rcx+8], rsi
0x1400125f6  mov     [rcx+14h], sil
0x1400125fa  mov     [rcx+18h], rsi
0x1400125fe  mov     [rcx+20h], rsi
0x140012602  mov     [rcx+28h], rsi
0x140012606  mov     [rcx+30h], esi
0x140012609  mov     [rcx+38h], rsi
0x14001260d  mov     [rcx+40h], rsi
0x140012611  mov     [rcx+48h], rsi
0x140012615  mov     [rcx+50h], rsi
0x140012619  mov     [rcx+58h], rsi
0x14001261d  mov     [rcx+60h], rsi
0x140012621  mov     dword ptr [rcx+68h], 8
0x140012628  add     rcx, 70h ; 'p'
0x14001262c  xorps   xmm0, xmm0
0x14001262f  movups  xmmword ptr [rcx], xmm0
0x140012632  mov     [rcx+10h], rsi
0x140012636  mov     [rcx+18h], rsi
0x14001263a  lea     r8d, [rsi+1Bh]
0x14001263e  lea     rdx, aUevconnectcrea; "\\UevConnectCreateNotifyPort"
0x140012645  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14001264a  lea     eax, [rbx+1F4h]
0x140012650  mov     [r12+90h], eax
0x140012658  or      r13, 0FFFFFFFFFFFFFFFFh
0x14001265c  mov     [r12+98h], r13
0x140012664  lea     rax, ??_7CreateProcNotificationListener@Uev@@6B@; const Uev::CreateProcNotificationListener::`vftable'
0x14001266b  mov     [r12], rax
0x14001266f  lea     rdi, [r12+0A0h]
0x140012677  xorps   xmm0, xmm0
0x14001267a  movups  xmmword ptr [rdi], xmm0
0x14001267d  mov     [rdi+10h], rsi
0x140012681  lea     r15d, [rsi+7]
0x140012685  mov     [rdi+18h], r15
0x140012689  mov     [rdi], si
0x14001268c  lea     rax, [rdi+20h]
0x140012690  mov     [rsp+2C8h+Src], rax
0x140012695  movups  xmmword ptr [rax], xmm0
0x140012698  mov     [rax+10h], rsi
0x14001269c  mov     [rax+18h], r15
0x1400126a0  mov     [rax], si
0x1400126a3  lea     rax, [r12+0E0h]
0x1400126ab  movups  xmmword ptr [rax], xmm0
0x1400126ae  mov     [rax+10h], rsi
0x1400126b2  mov     [rax+18h], r15
0x1400126b6  mov     [rax], si
0x1400126b9  add     rax, 20h ; ' '
0x1400126bd  mov     [rsp+2C8h+var_270], rax
0x1400126c2  movups  xmmword ptr [rax], xmm0
0x1400126c5  mov     [rax+10h], rsi
0x1400126c9  mov     [rax+18h], r15
0x1400126cd  mov     [rax], si
0x1400126d0  mov     edx, 2710h; unsigned int
0x1400126d5  lea     rcx, aFiltersendmsgt; "FilterSendMsgTimeout"
0x1400126dc  call    ?GetDwordConfigValue@Util@Uev@@SAKPEB_WK@Z; Uev::Util::GetDwordConfigValue(wchar_t const *,ulong)
0x1400126e1  mov     [r12+120h], eax
0x1400126e9  xor     edx, edx; unsigned int
0x1400126eb  lea     rcx, aTimetowaitbefo; "TimeToWaitBeforeInject"
0x1400126f2  call    ?GetDwordConfigValue@Util@Uev@@SAKPEB_WK@Z; Uev::Util::GetDwordConfigValue(wchar_t const *,ulong)
0x1400126f7  mov     [r12+124h], eax
0x1400126ff  xor     edx, edx; Val
0x140012701  mov     r8d, 208h; Size
0x140012707  lea     rcx, [rsp+2C8h+Buffer]; void *
0x14001270f  call    memset_0
0x140012714  mov     edx, 104h; uSize
0x140012719  lea     rcx, [rsp+2C8h+Buffer]; lpBuffer
0x140012721  call    cs:__imp_GetSystemWindowsDirectoryW
0x140012727  lea     rax, [rsp+2C8h+Buffer]
0x14001272f  mov     rdx, r13
0x140012732  inc     rdx
0x140012735  cmp     [rax+rdx*2], si
0x140012739  jnz     short loc_140012732
0x14001273b  cmp     rdx, [rdi+18h]
0x14001273f  ja      short loc_140012771
0x140012741  cmp     [rdi+18h], r15
0x140012745  jbe     short loc_14001274C
0x140012747  mov     r14, [rdi]
0x14001274a  jmp     short loc_14001274F
0x14001274c  mov     r14, rdi
0x14001274f  mov     [rdi+10h], rdx
0x140012753  lea     rbx, [rdx+rdx]
0x140012757  mov     r8, rbx; Size
0x14001275a  lea     rdx, [rsp+2C8h+Buffer]; Src
0x140012762  mov     rcx, r14; void *
0x140012765  call    memmove_0
0x14001276a  mov     [rbx+r14], si
0x14001276f  jmp     short loc_140012781
0x140012771  lea     r9, [rsp+2C8h+Buffer]
0x140012779  mov     rcx, rdi
0x14001277c  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140012781  mov     r8d, 17h
0x140012787  lea     rdx, aSyswow64Mavinj; "\\syswow64\\mavinject.exe"
0x14001278e  mov     rcx, rdi; Src
0x140012791  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140012796  lea     r14, [r12+0C0h]
0x14001279e  lea     rax, [rsp+2C8h+Buffer]
0x1400127a6  mov     rdx, r13
0x1400127a9  inc     rdx
0x1400127ac  cmp     [rax+rdx*2], si
0x1400127b0  jnz     short loc_1400127A9
0x1400127b2  cmp     rdx, [r14+18h]
0x1400127b6  ja      short loc_1400127E7
0x1400127b8  cmp     [r14+18h], r15
0x1400127bc  jbe     short loc_1400127C3
0x1400127be  mov     rdi, [r14]
0x1400127c1  jmp     short loc_1400127C6
0x1400127c3  mov     rdi, r14
0x1400127c6  mov     [r14+10h], rdx
0x1400127ca  lea     rbx, [rdx+rdx]
0x1400127ce  mov     r8, rbx; Size
0x1400127d1  lea     rdx, [rsp+2C8h+Buffer]; Src
0x1400127d9  mov     rcx, rdi; void *
0x1400127dc  call    memmove_0
0x1400127e1  mov     [rdi+rbx], si
0x1400127e5  jmp     short loc_1400127F7
0x1400127e7  lea     r9, [rsp+2C8h+Buffer]
0x1400127ef  mov     rcx, r14
0x1400127f2  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x1400127f7  mov     r8d, 24h ; '$'
0x1400127fd  lea     rdx, aSyswow64Micros; "\\syswow64\\Microsoft.Uev.AppAgent.dll"
0x140012804  mov     rcx, [rsp+2C8h+Src]; Src
0x140012809  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14001280e  lea     rax, [rsp+2C8h+Buffer]
0x140012816  mov     rdx, r13
0x140012819  inc     rdx
0x14001281c  cmp     [rax+rdx*2], si
0x140012820  jnz     short loc_140012819
0x140012822  lea     rdi, [r12+0E0h]
0x14001282a  mov     rax, [rdi+18h]
0x14001282e  cmp     rdx, rax
0x140012831  ja      short loc_14001286B
0x140012833  cmp     rax, r15
0x140012836  jbe     short loc_14001283D
0x140012838  mov     rax, [rdi]
0x14001283b  jmp     short loc_140012840
0x14001283d  mov     rax, rdi
0x140012840  mov     [rsp+2C8h+var_2A8], rax
0x140012845  mov     [rdi+10h], rdx
0x140012849  lea     rbx, [rdx+rdx]
0x14001284d  mov     r8, rbx; Size
0x140012850  lea     rdx, [rsp+2C8h+Buffer]; Src
0x140012858  mov     rcx, rax; void *
0x14001285b  call    memmove_0
0x140012860  mov     rax, [rsp+2C8h+var_2A8]
0x140012865  mov     [rbx+rax], si
0x140012869  jmp     short loc_14001287B
0x14001286b  lea     r9, [rsp+2C8h+Buffer]
0x140012873  mov     rcx, rdi
0x140012876  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14001287b  mov     r8d, 17h
0x140012881  lea     rdx, aSystem32Mavinj; "\\system32\\mavinject.exe"
0x140012888  mov     rcx, rdi; Src
0x14001288b  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140012890  lea     rdi, [r12+100h]
0x140012898  mov     [rsp+2C8h+Src], rdi
0x14001289d  lea     rax, [rsp+2C8h+Buffer]
0x1400128a5  inc     r13
0x1400128a8  cmp     [rax+r13*2], si
0x1400128ad  jnz     short loc_1400128A5
0x1400128af  lea     rax, [rdi+18h]
0x1400128b3  mov     [rsp+2C8h+var_268], rax
0x1400128b8  cmp     r13, [rax]
0x1400128bb  ja      short loc_1400128F9
0x1400128bd  cmp     [rax], r15
0x1400128c0  jbe     short loc_1400128C7
0x1400128c2  mov     rax, [rdi]
0x1400128c5  jmp     short loc_1400128CA
0x1400128c7  mov     rax, rdi
0x1400128ca  mov     [rsp+2C8h+var_2A8], rax
0x1400128cf  mov     [rdi+10h], r13
0x1400128d3  lea     rbx, ds:0[r13*2]
0x1400128db  mov     r8, rbx; Size
0x1400128de  lea     rdx, [rsp+2C8h+Buffer]; Src
0x1400128e6  mov     rcx, rax; void *
0x1400128e9  call    memmove_0
0x1400128ee  mov     rax, [rsp+2C8h+var_2A8]
0x1400128f3  mov     [rax+rbx], si
0x1400128f7  jmp     short loc_14001290C
0x1400128f9  lea     r9, [rsp+2C8h+Buffer]
0x140012901  mov     rdx, r13
0x140012904  mov     rcx, rdi
0x140012907  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14001290c  mov     r8d, 24h ; '$'
0x140012912  lea     rdx, aSystem32Micros; "\\system32\\Microsoft.Uev.AppAgent.dll"
0x140012919  mov     rcx, [rsp+2C8h+var_270]; Src
0x14001291e  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140012923  nop
0x140012924  cmp     [r14+18h], r15
0x140012928  jbe     short loc_14001292F
0x14001292a  mov     rdx, [r14]
0x14001292d  jmp     short loc_140012932
0x14001292f  mov     rdx, r14
0x140012932  lea     rcx, [rsp+2C8h+var_290]
0x140012937  call    ?GetShortPathNameW@Util@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::Util::GetShortPathNameW(wchar_t const *)
0x14001293c  mov     rbx, rax
0x14001293f  cmp     r14, rax
0x140012942  jz      short loc_140012967
0x140012944  mov     rcx, r14
0x140012947  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001294c  movups  xmm0, xmmword ptr [rbx]
0x14001294f  movups  xmmword ptr [r14], xmm0
0x140012953  movups  xmm1, xmmword ptr [rbx+10h]
0x140012957  movups  xmmword ptr [r14+10h], xmm1
0x14001295c  mov     [rbx+10h], rsi
0x140012960  mov     [rbx+18h], r15
0x140012964  mov     [rbx], si
0x140012967  lea     rcx, [rsp+2C8h+var_290]
0x14001296c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140012971  nop
0x140012972  jmp     short loc_140012986
0x140012974  mov     r12, [rsp+2C8h+var_2A0]
0x140012979  mov     rdi, [rsp+2C8h+Src]
0x14001297e  mov     r15d, 7
0x140012984  xor     esi, esi
0x140012986  mov     rax, [rsp+2C8h+var_268]
0x14001298b  cmp     [rax], r15
0x14001298e  jbe     short loc_140012995
0x140012990  mov     rdx, [rdi]
0x140012993  jmp     short loc_140012998
0x140012995  mov     rdx, rdi
0x140012998  lea     rcx, [rsp+2C8h+var_290]
0x14001299d  call    ?GetShortPathNameW@Util@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::Util::GetShortPathNameW(wchar_t const *)
0x1400129a2  mov     rbx, rax
0x1400129a5  cmp     rdi, rax
0x1400129a8  jz      short loc_1400129CB
0x1400129aa  mov     rcx, rdi
0x1400129ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400129b2  movups  xmm0, xmmword ptr [rbx]
0x1400129b5  movups  xmmword ptr [rdi], xmm0
0x1400129b8  movups  xmm1, xmmword ptr [rbx+10h]
0x1400129bc  movups  xmmword ptr [rdi+10h], xmm1
0x1400129c0  mov     [rbx+10h], rsi
0x1400129c4  mov     [rbx+18h], r15
0x1400129c8  mov     [rbx], si
0x1400129cb  lea     rcx, [rsp+2C8h+var_290]
0x1400129d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400129d5  nop
0x1400129d6  jmp     short loc_1400129DD
0x1400129d8  mov     r12, [rsp+2C8h+var_2A0]
0x1400129dd  mov     rax, r12
0x1400129e0  mov     rcx, [rsp+2C8h+var_38]
0x1400129e8  xor     rcx, rsp; StackCookie
0x1400129eb  call    __security_check_cookie
0x1400129f0  lea     r11, [rsp+2C8h+var_28]
0x1400129f8  mov     rbx, [r11+38h]
0x1400129fc  mov     rsi, [r11+40h]
0x140012a00  mov     rsp, r11
0x140012a03  pop     r15
0x140012a05  pop     r14
0x140012a07  pop     r13
0x140012a09  pop     r12
0x140012a0b  pop     rdi
0x140012a0c  retn
```
