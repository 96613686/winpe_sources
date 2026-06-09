# CStowedExceptionPlugin::BuildLoadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *,ulong)

- ea: `0x1400525c4`
- end: `0x1400529a9`
- name: `?BuildLoadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAXK@Z`
- size: `997`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400533b0`

## callees

- `0x140002490`
- `0x1400024b4`
- `0x140002d74`
- `0x1400030f8`
- `0x1400101a8`
- `0x140011b44`
- `0x1400166ec`
- `0x1400525c4`
- `0x140053ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14005281b`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14005281b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005295c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005295c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140052636`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140052636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052949`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052949`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x140052900`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x140052900`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14005270a`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14005270a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x140052654`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x140052654`

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
0x1400525c4  mov     [rsp-8+arg_18], rbx
0x1400525c9  push    rbp
0x1400525ca  push    rsi
0x1400525cb  push    rdi
0x1400525cc  push    r12
0x1400525ce  push    r13
0x1400525d0  push    r14
0x1400525d2  push    r15
0x1400525d4  lea     rbp, [rsp-800h]
0x1400525dc  sub     rsp, 900h
0x1400525e3  mov     rax, cs:__security_cookie
0x1400525ea  xor     rax, rsp
0x1400525ed  mov     [rbp+830h+var_40], rax
0x1400525f4  mov     ebx, r8d
0x1400525f7  mov     r15, rdx
0x1400525fa  mov     r12, rcx
0x1400525fd  mov     esi, 438h
0x140052602  mov     r8d, esi; Size
0x140052605  xor     edx, edx; Val
0x140052607  lea     rcx, [rbp+830h+me]; void *
0x14005260e  call    memset_0
0x140052613  xor     r13d, r13d
0x140052616  mov     [rsp+930h+Block], r13
0x14005261b  xorps   xmm0, xmm0
0x14005261e  xor     eax, eax
0x140052620  movups  [rsp+930h+var_8F8], xmm0
0x140052625  movups  [rsp+930h+var_8E8], xmm0
0x14005262a  movups  [rsp+930h+var_8D8], xmm0
0x14005262f  mov     [rsp+930h+var_8C8], eax
0x140052633  mov     rcx, r15; Process
0x140052636  call    cs:__imp_GetProcessId
0x14005263d  nop     dword ptr [rax+rax+00h]
0x140052642  cmp     ebx, eax
0x140052644  jz      short loc_14005264B
0x140052646  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14005264b  mov     edx, ebx; th32ProcessID
0x14005264d  mov     ebx, 8
0x140052652  mov     ecx, ebx; dwFlags
0x140052654  call    cs:__imp_CreateToolhelp32Snapshot
0x14005265b  nop     dword ptr [rax+rax+00h]
0x140052660  mov     r14, rax
0x140052663  lea     rcx, [rax+1]
0x140052667  cmp     rcx, 1
0x14005266b  jbe     loc_14005295C
0x140052671  mov     r8, rsi; Size
0x140052674  xor     edx, edx; Val
0x140052676  lea     rcx, [rsp+930h+var_8C0]; void *
0x14005267b  call    memset_0
0x140052680  lea     rcx, [rbp+830h+me]
0x140052687  lea     rax, [rsp+930h+var_8C0]
0x14005268c  mov     edx, ebx
0x14005268e  lea     r8d, [rbx+78h]
0x140052692  movups  xmm0, xmmword ptr [rax]
0x140052695  movups  xmmword ptr [rcx], xmm0
0x140052698  movups  xmm1, xmmword ptr [rax+10h]
0x14005269c  movups  xmmword ptr [rcx+10h], xmm1
0x1400526a0  movups  xmm0, xmmword ptr [rax+20h]
0x1400526a4  movups  xmmword ptr [rcx+20h], xmm0
0x1400526a8  movups  xmm1, xmmword ptr [rax+30h]
0x1400526ac  movups  xmmword ptr [rcx+30h], xmm1
0x1400526b0  movups  xmm0, xmmword ptr [rax+40h]
0x1400526b4  movups  xmmword ptr [rcx+40h], xmm0
0x1400526b8  movups  xmm1, xmmword ptr [rax+50h]
0x1400526bc  movups  xmmword ptr [rcx+50h], xmm1
0x1400526c0  movups  xmm0, xmmword ptr [rax+60h]
0x1400526c4  movups  xmmword ptr [rcx+60h], xmm0
0x1400526c8  movups  xmm1, xmmword ptr [rax+70h]
0x1400526cc  movups  xmmword ptr [rcx+70h], xmm1
0x1400526d0  add     rcx, r8
0x1400526d3  add     rax, r8
0x1400526d6  sub     rdx, 1
0x1400526da  jnz     short loc_140052692
0x1400526dc  movups  xmm0, xmmword ptr [rax]
0x1400526df  movups  xmmword ptr [rcx], xmm0
0x1400526e2  movups  xmm1, xmmword ptr [rax+10h]
0x1400526e6  movups  xmmword ptr [rcx+10h], xmm1
0x1400526ea  movups  xmm0, xmmword ptr [rax+20h]
0x1400526ee  movups  xmmword ptr [rcx+20h], xmm0
0x1400526f2  mov     rax, [rax+30h]
0x1400526f6  mov     [rcx+30h], rax
0x1400526fa  mov     [rbp+830h+me.dwSize], esi
0x140052700  lea     rdx, [rbp+830h+me]; lpme
0x140052707  mov     rcx, r14; hSnapshot
0x14005270a  call    cs:__imp_Module32FirstW
0x140052711  nop     dword ptr [rax+rax+00h]
0x140052716  test    eax, eax
0x140052718  jz      loc_140052923
0x14005271e  mov     edx, 100h
0x140052723  lea     rax, [rbp+830h+me.szModule]
0x14005272a  cmp     [rax], r13w
0x14005272e  jz      short loc_14005273A
0x140052730  add     rax, 2
0x140052734  sub     rdx, 1
0x140052738  jnz     short loc_14005272A
0x14005273a  mov     rax, rdx
0x14005273d  mov     ecx, 100h
0x140052742  sub     rcx, rdx
0x140052745  neg     rax
0x140052748  sbb     rdi, rdi
0x14005274b  and     rdi, rcx
0x14005274e  test    rdx, rdx
0x140052751  jnz     short loc_140052760
0x140052753  mov     edi, 0FFh
0x140052758  mov     [rbp+830h+me.szModule+1FEh], r13w
0x140052760  lea     ecx, ds:2[rdi*2]
0x140052767  add     rcx, 28h ; '('; unsigned __int64
0x14005276b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140052772  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140052777  mov     rbx, rax
0x14005277a  test    rax, rax
0x14005277d  jz      loc_140052861
0x140052783  xorps   xmm0, xmm0
0x140052786  xor     eax, eax
0x140052788  movups  xmmword ptr [rbx], xmm0
0x14005278b  movups  xmmword ptr [rbx+10h], xmm0
0x14005278f  mov     [rbx+20h], rax
0x140052793  mov     [rsp+930h+Block], rbx
0x140052798  mov     rcx, [rbp+830h+me.modBaseAddr]
0x14005279f  mov     [rbx], rcx
0x1400527a2  mov     ecx, [rbp+830h+me.modBaseSize]
0x1400527a8  mov     [rbx+8], ecx
0x1400527ab  mov     rdx, [rbp+830h+me.modBaseAddr]; lpBaseAddress
0x1400527b2  mov     rcx, r15; hProcess
0x1400527b5  call    ?UtilGetTimestampModule@@YAKPEAXPEAUHINSTANCE__@@@Z; UtilGetTimestampModule(void *,HINSTANCE__ *)
0x1400527ba  mov     [rbx+0Ch], eax
0x1400527bd  mov     [rsp+930h+var_910], r13d; int
0x1400527c2  xor     r9d, r9d
0x1400527c5  xor     r8d, r8d
0x1400527c8  lea     rdx, [rsp+930h+var_8F8]
0x1400527cd  lea     rcx, [rbp+830h+me.szExePath]; lpwstrFilename
0x1400527d4  call    ?UtilGetFileInfo@@YAJPEB_WPEAUtagVS_FIXEDFILEINFO@@QEBQEB_WQEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@K@Z; UtilGetFileInfo(wchar_t const *,tagVS_FIXEDFILEINFO *,wchar_t const * const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> * const,ulong)
0x1400527d9  test    eax, eax
0x1400527db  js      short loc_1400527FF
0x1400527dd  mov     ecx, dword ptr [rsp+930h+var_8F8+8]
0x1400527e1  mov     eax, ecx
0x1400527e3  shr     eax, 10h
0x1400527e6  mov     [rbx+10h], ax
0x1400527ea  mov     [rbx+12h], cx
0x1400527ee  mov     ecx, dword ptr [rsp+930h+var_8F8+0Ch]
0x1400527f2  mov     eax, ecx
0x1400527f4  shr     eax, 10h
0x1400527f7  mov     [rbx+14h], ax
0x1400527fb  mov     [rbx+16h], cx
0x1400527ff  lea     rax, [rbx+28h]
0x140052803  mov     [rbx+18h], rax
0x140052807  mov     [rbx+20h], r13d
0x14005280b  mov     rsi, r13
0x14005280e  test    rdi, rdi
0x140052811  jz      short loc_140052837
0x140052813  movzx   ecx, [rbp+rsi*2+830h+me.szModule]
0x14005281b  call    cs:__imp__o_towlower
0x140052822  nop     dword ptr [rax+rax+00h]
0x140052827  mov     rcx, [rbx+18h]
0x14005282b  mov     [rcx+rsi*2], ax
0x14005282f  inc     rsi
0x140052832  cmp     rsi, rdi
0x140052835  jb      short loc_140052813
0x140052837  mov     rcx, [rbx+18h]
0x14005283b  mov     [rcx+rdi*2], r13w
0x140052840  lea     rdx, [rsp+930h+Block]
0x140052845  mov     rcx, r12
0x140052848  call    ?push_back@?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@2@@Z; utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>> &&)
0x14005284d  test    al, al
0x14005284f  jz      loc_140052936
0x140052855  mov     rbx, [rsp+930h+Block]
0x14005285a  mov     esi, 438h
0x14005285f  jmp     short loc_140052864
0x140052861  mov     rbx, r13
0x140052864  mov     r8, rsi; Size
0x140052867  xor     edx, edx; Val
0x140052869  lea     rcx, [rsp+930h+var_8C0]; void *
0x14005286e  call    memset_0
0x140052873  lea     rdx, [rbp+830h+me]
0x14005287a  lea     rax, [rsp+930h+var_8C0]
0x14005287f  mov     ecx, 8
0x140052884  lea     r8d, [rcx+78h]
0x140052888  movups  xmm0, xmmword ptr [rax]
0x14005288b  movups  xmmword ptr [rdx], xmm0
0x14005288e  movups  xmm1, xmmword ptr [rax+10h]
0x140052892  movups  xmmword ptr [rdx+10h], xmm1
0x140052896  movups  xmm0, xmmword ptr [rax+20h]
0x14005289a  movups  xmmword ptr [rdx+20h], xmm0
0x14005289e  movups  xmm1, xmmword ptr [rax+30h]
0x1400528a2  movups  xmmword ptr [rdx+30h], xmm1
0x1400528a6  movups  xmm0, xmmword ptr [rax+40h]
0x1400528aa  movups  xmmword ptr [rdx+40h], xmm0
0x1400528ae  movups  xmm1, xmmword ptr [rax+50h]
0x1400528b2  movups  xmmword ptr [rdx+50h], xmm1
0x1400528b6  movups  xmm0, xmmword ptr [rax+60h]
0x1400528ba  movups  xmmword ptr [rdx+60h], xmm0
0x1400528be  movups  xmm1, xmmword ptr [rax+70h]
0x1400528c2  movups  xmmword ptr [rdx+70h], xmm1
0x1400528c6  add     rdx, r8
0x1400528c9  add     rax, r8
0x1400528cc  sub     rcx, 1
0x1400528d0  jnz     short loc_140052888
0x1400528d2  movups  xmm0, xmmword ptr [rax]
0x1400528d5  movups  xmmword ptr [rdx], xmm0
0x1400528d8  movups  xmm1, xmmword ptr [rax+10h]
0x1400528dc  movups  xmmword ptr [rdx+10h], xmm1
0x1400528e0  movups  xmm0, xmmword ptr [rax+20h]
0x1400528e4  movups  xmmword ptr [rdx+20h], xmm0
0x1400528e8  mov     rax, [rax+30h]
0x1400528ec  mov     [rdx+30h], rax
0x1400528f0  mov     [rbp+830h+me.dwSize], esi
0x1400528f6  lea     rdx, [rbp+830h+me]; lpme
0x1400528fd  mov     rcx, r14; hSnapshot
0x140052900  call    cs:__imp_Module32NextW
0x140052907  nop     dword ptr [rax+rax+00h]
0x14005290c  mov     edi, eax
0x14005290e  test    rbx, rbx
0x140052911  jz      short loc_14005291B
0x140052913  mov     rcx, rbx; Block
0x140052916  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005291b  test    edi, edi
0x14005291d  jnz     loc_14005271E
0x140052923  mov     rcx, r14; hObject
0x140052926  call    cs:__imp_CloseHandle
0x14005292d  nop     dword ptr [rax+rax+00h]
0x140052932  xor     eax, eax
0x140052934  jmp     short loc_14005297E
0x140052936  mov     rcx, [rsp+930h+Block]; Block
0x14005293b  test    rcx, rcx
0x14005293e  jz      short loc_140052946
0x140052940  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140052945  nop
0x140052946  mov     rcx, r14; hObject
0x140052949  call    cs:__imp_CloseHandle
0x140052950  nop     dword ptr [rax+rax+00h]
0x140052955  mov     eax, 8007000Eh
0x14005295a  jmp     short loc_14005297E
0x14005295c  call    cs:__imp_GetLastError
0x140052963  nop     dword ptr [rax+rax+00h]
0x140052968  test    eax, eax
0x14005296a  jle     short loc_140052974
0x14005296c  movzx   eax, ax
0x14005296f  or      eax, 80070000h
0x140052974  mov     ecx, 80004005h
0x140052979  test    eax, eax
0x14005297b  cmovns  eax, ecx
0x14005297e  mov     rcx, [rbp+830h+var_40]
0x140052985  xor     rcx, rsp; StackCookie
0x140052988  call    __security_check_cookie
0x14005298d  mov     rbx, [rsp+930h+arg_18]
0x140052995  add     rsp, 900h
0x14005299c  pop     r15
0x14005299e  pop     r14
0x1400529a0  pop     r13
0x1400529a2  pop     r12
0x1400529a4  pop     rdi
0x1400529a5  pop     rsi
0x1400529a6  pop     rbp
0x1400529a7  retn
```
