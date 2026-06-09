# CStowedExceptionPlugin::BuildLoadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *,ulong)

- ea: `0x14004ef20`
- end: `0x14004f2d4`
- name: `?BuildLoadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAXK@Z`
- size: `948`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14004fc20`

## callees

- `0x140002470`
- `0x140002494`
- `0x140002d24`
- `0x1400030a8`
- `0x14000fb60`
- `0x1400113ec`
- `0x140015b40`
- `0x14004ef20`
- `0x140050520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14004f165`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14004f165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f28e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14004ef92`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14004ef92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004f264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004f281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004f264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004f281`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x14004f244`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x14004f244`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14004f05a`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14004f05a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14004efaa`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14004efaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall CStowedExceptionPlugin::BuildLoadedModuleList(__int64 a1, void *a2, DWORD a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  HANDLE Toolhelp32Snapshot; // r14
  MODULEENTRY32W *p_me; // rcx
  _OWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  WCHAR *szModule; // rax
  unsigned __int64 v16; // rdi
  _OWORD *v17; // rbx
  __int16 v18; // cx
  __int16 v19; // cx
  unsigned __int64 i; // rsi
  void *v21; // rbx
  MODULEENTRY32W *v22; // rdx
  _OWORD *v23; // rax
  __int64 v24; // rcx
  BOOL v25; // edi
  signed int result; // eax
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v28; // [rsp+38h] [rbp-C8h]
  __int128 v29; // [rsp+48h] [rbp-B8h]
  __int128 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+68h] [rbp-98h]
  _BYTE v32[1088]; // [rsp+70h] [rbp-90h] BYREF
  MODULEENTRY32W me; // [rsp+4B0h] [rbp+3B0h] BYREF

  memset_0(&me, 0, sizeof(me));
  Block = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  if ( a3 != GetProcessId(a2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8, v9);
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, a3);
  if ( (unsigned __int64)Toolhelp32Snapshot + 1 > 1 )
  {
    memset_0(v32, 0, 0x438u);
    p_me = &me;
    v12 = v32;
    v13 = 8;
    do
    {
      *(_OWORD *)&p_me->dwSize = *v12;
      *(_OWORD *)&p_me->ProccntUsage = v12[1];
      *(_OWORD *)&p_me->modBaseSize = v12[2];
      *(_OWORD *)p_me->szModule = v12[3];
      *(_OWORD *)&p_me->szModule[8] = v12[4];
      *(_OWORD *)&p_me->szModule[16] = v12[5];
      *(_OWORD *)&p_me->szModule[24] = v12[6];
      *(_OWORD *)&p_me->szModule[32] = v12[7];
      p_me = (MODULEENTRY32W *)((char *)p_me + 128);
      v12 += 8;
      --v13;
    }
    while ( v13 );
    *(_OWORD *)&p_me->dwSize = *v12;
    *(_OWORD *)&p_me->ProccntUsage = v12[1];
    *(_OWORD *)&p_me->modBaseSize = v12[2];
    *(_QWORD *)p_me->szModule = *((_QWORD *)v12 + 6);
    me.dwSize = 1080;
    if ( !Module32FirstW(Toolhelp32Snapshot, &me) )
    {
LABEL_25:
      CloseHandle(Toolhelp32Snapshot);
      return 0;
    }
    while ( 1 )
    {
      v14 = 256;
      szModule = me.szModule;
      do
      {
        if ( !*szModule )
          break;
        ++szModule;
        --v14;
      }
      while ( v14 );
      v16 = (256 - v14) & -(__int64)(v14 != 0);
      if ( !v14 )
      {
        v16 = 255;
        me.szModule[255] = 0;
      }
      v17 = operator new((unsigned int)(2 * v16 + 2) + 40LL, (const struct std::nothrow_t *)&std::nothrow);
      if ( v17 )
      {
        *v17 = 0;
        v17[1] = 0;
        *((_QWORD *)v17 + 4) = 0;
        Block = v17;
        *(_QWORD *)v17 = me.modBaseAddr;
        *((_DWORD *)v17 + 2) = me.modBaseSize;
        *((_DWORD *)v17 + 3) = UtilGetTimestampModule(a2, (HINSTANCE)me.modBaseAddr);
        if ( (int)UtilGetFileInfo(me.szExePath, 0) >= 0 )
        {
          v18 = WORD4(v28);
          *((_WORD *)v17 + 8) = WORD5(v28);
          *((_WORD *)v17 + 9) = v18;
          v19 = WORD6(v28);
          *((_WORD *)v17 + 10) = HIWORD(v28);
          *((_WORD *)v17 + 11) = v19;
        }
        *((_QWORD *)v17 + 3) = (char *)v17 + 40;
        *((_DWORD *)v17 + 8) = 0;
        for ( i = 0; i < v16; ++i )
          *(_WORD *)(*((_QWORD *)v17 + 3) + 2 * i) = _o_towlower(me.szModule[i]);
        *(_WORD *)(*((_QWORD *)v17 + 3) + 2 * v16) = 0;
        if ( !(unsigned __int8)utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(
                                 a1,
                                 &Block) )
        {
          if ( Block )
            operator delete(Block);
          CloseHandle(Toolhelp32Snapshot);
          return -2147024882;
        }
        v21 = Block;
      }
      else
      {
        v21 = 0;
      }
      memset_0(v32, 0, 0x438u);
      v22 = &me;
      v23 = v32;
      v24 = 8;
      do
      {
        *(_OWORD *)&v22->dwSize = *v23;
        *(_OWORD *)&v22->ProccntUsage = v23[1];
        *(_OWORD *)&v22->modBaseSize = v23[2];
        *(_OWORD *)v22->szModule = v23[3];
        *(_OWORD *)&v22->szModule[8] = v23[4];
        *(_OWORD *)&v22->szModule[16] = v23[5];
        *(_OWORD *)&v22->szModule[24] = v23[6];
        *(_OWORD *)&v22->szModule[32] = v23[7];
        v22 = (MODULEENTRY32W *)((char *)v22 + 128);
        v23 += 8;
        --v24;
      }
      while ( v24 );
      *(_OWORD *)&v22->dwSize = *v23;
      *(_OWORD *)&v22->ProccntUsage = v23[1];
      *(_OWORD *)&v22->modBaseSize = v23[2];
      *(_QWORD *)v22->szModule = *((_QWORD *)v23 + 6);
      me.dwSize = 1080;
      v25 = Module32NextW(Toolhelp32Snapshot, &me);
      if ( v21 )
        operator delete(v21);
      if ( !v25 )
        goto LABEL_25;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x14004ef20  mov     [rsp-8+arg_18], rbx
0x14004ef25  push    rbp
0x14004ef26  push    rsi
0x14004ef27  push    rdi
0x14004ef28  push    r12
0x14004ef2a  push    r13
0x14004ef2c  push    r14
0x14004ef2e  push    r15
0x14004ef30  lea     rbp, [rsp-800h]
0x14004ef38  sub     rsp, 900h
0x14004ef3f  mov     rax, cs:__security_cookie
0x14004ef46  xor     rax, rsp
0x14004ef49  mov     [rbp+830h+var_40], rax
0x14004ef50  mov     ebx, r8d
0x14004ef53  mov     r15, rdx
0x14004ef56  mov     r12, rcx
0x14004ef59  mov     esi, 438h
0x14004ef5e  mov     r8d, esi; Size
0x14004ef61  xor     edx, edx; Val
0x14004ef63  lea     rcx, [rbp+830h+me]; void *
0x14004ef6a  call    memset_0
0x14004ef6f  xor     r13d, r13d
0x14004ef72  mov     [rsp+930h+Block], r13
0x14004ef77  xorps   xmm0, xmm0
0x14004ef7a  xor     eax, eax
0x14004ef7c  movups  [rsp+930h+var_8F8], xmm0
0x14004ef81  movups  [rsp+930h+var_8E8], xmm0
0x14004ef86  movups  [rsp+930h+var_8D8], xmm0
0x14004ef8b  mov     [rsp+930h+var_8C8], eax
0x14004ef8f  mov     rcx, r15; Process
0x14004ef92  call    cs:__imp_GetProcessId
0x14004ef98  cmp     ebx, eax
0x14004ef9a  jz      short loc_14004EFA1
0x14004ef9c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004efa1  mov     edx, ebx; th32ProcessID
0x14004efa3  mov     ebx, 8
0x14004efa8  mov     ecx, ebx; dwFlags
0x14004efaa  call    cs:__imp_CreateToolhelp32Snapshot
0x14004efb0  mov     r14, rax
0x14004efb3  lea     rcx, [rax+1]
0x14004efb7  cmp     rcx, 1
0x14004efbb  jbe     loc_14004F28E
0x14004efc1  mov     r8, rsi; Size
0x14004efc4  xor     edx, edx; Val
0x14004efc6  lea     rcx, [rsp+930h+var_8C0]; void *
0x14004efcb  call    memset_0
0x14004efd0  lea     rcx, [rbp+830h+me]
0x14004efd7  lea     rax, [rsp+930h+var_8C0]
0x14004efdc  mov     edx, ebx
0x14004efde  lea     r8d, [rbx+78h]
0x14004efe2  movups  xmm0, xmmword ptr [rax]
0x14004efe5  movups  xmmword ptr [rcx], xmm0
0x14004efe8  movups  xmm1, xmmword ptr [rax+10h]
0x14004efec  movups  xmmword ptr [rcx+10h], xmm1
0x14004eff0  movups  xmm0, xmmword ptr [rax+20h]
0x14004eff4  movups  xmmword ptr [rcx+20h], xmm0
0x14004eff8  movups  xmm1, xmmword ptr [rax+30h]
0x14004effc  movups  xmmword ptr [rcx+30h], xmm1
0x14004f000  movups  xmm0, xmmword ptr [rax+40h]
0x14004f004  movups  xmmword ptr [rcx+40h], xmm0
0x14004f008  movups  xmm1, xmmword ptr [rax+50h]
0x14004f00c  movups  xmmword ptr [rcx+50h], xmm1
0x14004f010  movups  xmm0, xmmword ptr [rax+60h]
0x14004f014  movups  xmmword ptr [rcx+60h], xmm0
0x14004f018  movups  xmm1, xmmword ptr [rax+70h]
0x14004f01c  movups  xmmword ptr [rcx+70h], xmm1
0x14004f020  add     rcx, r8
0x14004f023  add     rax, r8
0x14004f026  sub     rdx, 1
0x14004f02a  jnz     short loc_14004EFE2
0x14004f02c  movups  xmm0, xmmword ptr [rax]
0x14004f02f  movups  xmmword ptr [rcx], xmm0
0x14004f032  movups  xmm1, xmmword ptr [rax+10h]
0x14004f036  movups  xmmword ptr [rcx+10h], xmm1
0x14004f03a  movups  xmm0, xmmword ptr [rax+20h]
0x14004f03e  movups  xmmword ptr [rcx+20h], xmm0
0x14004f042  mov     rax, [rax+30h]
0x14004f046  mov     [rcx+30h], rax
0x14004f04a  mov     [rbp+830h+me.dwSize], esi
0x14004f050  lea     rdx, [rbp+830h+me]; lpme
0x14004f057  mov     rcx, r14; hSnapshot
0x14004f05a  call    cs:__imp_Module32FirstW
0x14004f060  test    eax, eax
0x14004f062  jz      loc_14004F261
0x14004f068  mov     edx, 100h
0x14004f06d  lea     rax, [rbp+830h+me.szModule]
0x14004f074  cmp     [rax], r13w
0x14004f078  jz      short loc_14004F084
0x14004f07a  add     rax, 2
0x14004f07e  sub     rdx, 1
0x14004f082  jnz     short loc_14004F074
0x14004f084  mov     rax, rdx
0x14004f087  mov     ecx, 100h
0x14004f08c  sub     rcx, rdx
0x14004f08f  neg     rax
0x14004f092  sbb     rdi, rdi
0x14004f095  and     rdi, rcx
0x14004f098  test    rdx, rdx
0x14004f09b  jnz     short loc_14004F0AA
0x14004f09d  mov     edi, 0FFh
0x14004f0a2  mov     [rbp+830h+me.szModule+1FEh], r13w
0x14004f0aa  lea     ecx, ds:2[rdi*2]
0x14004f0b1  add     rcx, 28h ; '('; unsigned __int64
0x14004f0b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004f0bc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14004f0c1  mov     rbx, rax
0x14004f0c4  test    rax, rax
0x14004f0c7  jz      loc_14004F1A5
0x14004f0cd  xorps   xmm0, xmm0
0x14004f0d0  xor     eax, eax
0x14004f0d2  movups  xmmword ptr [rbx], xmm0
0x14004f0d5  movups  xmmword ptr [rbx+10h], xmm0
0x14004f0d9  mov     [rbx+20h], rax
0x14004f0dd  mov     [rsp+930h+Block], rbx
0x14004f0e2  mov     rcx, [rbp+830h+me.modBaseAddr]
0x14004f0e9  mov     [rbx], rcx
0x14004f0ec  mov     ecx, [rbp+830h+me.modBaseSize]
0x14004f0f2  mov     [rbx+8], ecx
0x14004f0f5  mov     rdx, [rbp+830h+me.modBaseAddr]; lpBaseAddress
0x14004f0fc  mov     rcx, r15; hProcess
0x14004f0ff  call    ?UtilGetTimestampModule@@YAKPEAXPEAUHINSTANCE__@@@Z; UtilGetTimestampModule(void *,HINSTANCE__ *)
0x14004f104  mov     [rbx+0Ch], eax
0x14004f107  mov     [rsp+930h+var_910], r13d; int
0x14004f10c  xor     r9d, r9d
0x14004f10f  xor     r8d, r8d
0x14004f112  lea     rdx, [rsp+930h+var_8F8]
0x14004f117  lea     rcx, [rbp+830h+me.szExePath]; lpwstrFilename
0x14004f11e  call    ?UtilGetFileInfo@@YAJPEB_WPEAUtagVS_FIXEDFILEINFO@@QEBQEB_WQEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@K@Z; UtilGetFileInfo(wchar_t const *,tagVS_FIXEDFILEINFO *,wchar_t const * const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> * const,ulong)
0x14004f123  test    eax, eax
0x14004f125  js      short loc_14004F149
0x14004f127  mov     ecx, dword ptr [rsp+930h+var_8F8+8]
0x14004f12b  mov     eax, ecx
0x14004f12d  shr     eax, 10h
0x14004f130  mov     [rbx+10h], ax
0x14004f134  mov     [rbx+12h], cx
0x14004f138  mov     ecx, dword ptr [rsp+930h+var_8F8+0Ch]
0x14004f13c  mov     eax, ecx
0x14004f13e  shr     eax, 10h
0x14004f141  mov     [rbx+14h], ax
0x14004f145  mov     [rbx+16h], cx
0x14004f149  lea     rax, [rbx+28h]
0x14004f14d  mov     [rbx+18h], rax
0x14004f151  mov     [rbx+20h], r13d
0x14004f155  mov     rsi, r13
0x14004f158  test    rdi, rdi
0x14004f15b  jz      short loc_14004F17B
0x14004f15d  movzx   ecx, [rbp+rsi*2+830h+me.szModule]
0x14004f165  call    cs:__imp__o_towlower
0x14004f16b  mov     rcx, [rbx+18h]
0x14004f16f  mov     [rcx+rsi*2], ax
0x14004f173  inc     rsi
0x14004f176  cmp     rsi, rdi
0x14004f179  jb      short loc_14004F15D
0x14004f17b  mov     rcx, [rbx+18h]
0x14004f17f  mov     [rcx+rdi*2], r13w
0x14004f184  lea     rdx, [rsp+930h+Block]
0x14004f189  mov     rcx, r12
0x14004f18c  call    ?push_back@?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@2@@Z; utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>> &&)
0x14004f191  test    al, al
0x14004f193  jz      loc_14004F26E
0x14004f199  mov     rbx, [rsp+930h+Block]
0x14004f19e  mov     esi, 438h
0x14004f1a3  jmp     short loc_14004F1A8
0x14004f1a5  mov     rbx, r13
0x14004f1a8  mov     r8, rsi; Size
0x14004f1ab  xor     edx, edx; Val
0x14004f1ad  lea     rcx, [rsp+930h+var_8C0]; void *
0x14004f1b2  call    memset_0
0x14004f1b7  lea     rdx, [rbp+830h+me]
0x14004f1be  lea     rax, [rsp+930h+var_8C0]
0x14004f1c3  mov     ecx, 8
0x14004f1c8  lea     r8d, [rcx+78h]
0x14004f1cc  movups  xmm0, xmmword ptr [rax]
0x14004f1cf  movups  xmmword ptr [rdx], xmm0
0x14004f1d2  movups  xmm1, xmmword ptr [rax+10h]
0x14004f1d6  movups  xmmword ptr [rdx+10h], xmm1
0x14004f1da  movups  xmm0, xmmword ptr [rax+20h]
0x14004f1de  movups  xmmword ptr [rdx+20h], xmm0
0x14004f1e2  movups  xmm1, xmmword ptr [rax+30h]
0x14004f1e6  movups  xmmword ptr [rdx+30h], xmm1
0x14004f1ea  movups  xmm0, xmmword ptr [rax+40h]
0x14004f1ee  movups  xmmword ptr [rdx+40h], xmm0
0x14004f1f2  movups  xmm1, xmmword ptr [rax+50h]
0x14004f1f6  movups  xmmword ptr [rdx+50h], xmm1
0x14004f1fa  movups  xmm0, xmmword ptr [rax+60h]
0x14004f1fe  movups  xmmword ptr [rdx+60h], xmm0
0x14004f202  movups  xmm1, xmmword ptr [rax+70h]
0x14004f206  movups  xmmword ptr [rdx+70h], xmm1
0x14004f20a  add     rdx, r8
0x14004f20d  add     rax, r8
0x14004f210  sub     rcx, 1
0x14004f214  jnz     short loc_14004F1CC
0x14004f216  movups  xmm0, xmmword ptr [rax]
0x14004f219  movups  xmmword ptr [rdx], xmm0
0x14004f21c  movups  xmm1, xmmword ptr [rax+10h]
0x14004f220  movups  xmmword ptr [rdx+10h], xmm1
0x14004f224  movups  xmm0, xmmword ptr [rax+20h]
0x14004f228  movups  xmmword ptr [rdx+20h], xmm0
0x14004f22c  mov     rax, [rax+30h]
0x14004f230  mov     [rdx+30h], rax
0x14004f234  mov     [rbp+830h+me.dwSize], esi
0x14004f23a  lea     rdx, [rbp+830h+me]; lpme
0x14004f241  mov     rcx, r14; hSnapshot
0x14004f244  call    cs:__imp_Module32NextW
0x14004f24a  mov     edi, eax
0x14004f24c  test    rbx, rbx
0x14004f24f  jz      short loc_14004F259
0x14004f251  mov     rcx, rbx; Block
0x14004f254  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004f259  test    edi, edi
0x14004f25b  jnz     loc_14004F068
0x14004f261  mov     rcx, r14; hObject
0x14004f264  call    cs:__imp_CloseHandle
0x14004f26a  xor     eax, eax
0x14004f26c  jmp     short loc_14004F2AA
0x14004f26e  mov     rcx, [rsp+930h+Block]; Block
0x14004f273  test    rcx, rcx
0x14004f276  jz      short loc_14004F27E
0x14004f278  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004f27d  nop
0x14004f27e  mov     rcx, r14; hObject
0x14004f281  call    cs:__imp_CloseHandle
0x14004f287  mov     eax, 8007000Eh
0x14004f28c  jmp     short loc_14004F2AA
0x14004f28e  call    cs:__imp_GetLastError
0x14004f294  test    eax, eax
0x14004f296  jle     short loc_14004F2A0
0x14004f298  movzx   eax, ax
0x14004f29b  or      eax, 80070000h
0x14004f2a0  mov     ecx, 80004005h
0x14004f2a5  test    eax, eax
0x14004f2a7  cmovns  eax, ecx
0x14004f2aa  mov     rcx, [rbp+830h+var_40]
0x14004f2b1  xor     rcx, rsp; StackCookie
0x14004f2b4  call    __security_check_cookie
0x14004f2b9  mov     rbx, [rsp+930h+arg_18]
0x14004f2c1  add     rsp, 900h
0x14004f2c8  pop     r15
0x14004f2ca  pop     r14
0x14004f2cc  pop     r13
0x14004f2ce  pop     r12
0x14004f2d0  pop     rdi
0x14004f2d1  pop     rsi
0x14004f2d2  pop     rbp
0x14004f2d3  retn
```
