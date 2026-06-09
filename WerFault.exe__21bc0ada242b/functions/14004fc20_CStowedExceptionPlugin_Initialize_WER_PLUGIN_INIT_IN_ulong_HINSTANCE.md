# CStowedExceptionPlugin::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x14004fc20`
- end: `0x1400500ea`
- name: `?Initialize@CStowedExceptionPlugin@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `1226`
- prototype: `__int64 __fastcall(CStowedExceptionPlugin *__hidden this, struct WER_PLUGIN_INIT_IN *, unsigned int, HINSTANCE)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005430`
- `0x14000c8a0`
- `0x140013ff0`
- `0x140015b40`
- `0x14004ecfc`
- `0x14004eec4`
- `0x14004ef20`
- `0x14004f2dc`
- `0x14004f5dc`
- `0x14004f7fc`
- `0x14004f9f0`
- `0x14004fc20`
- `0x1400505c8`
- `0x14005b7c4`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004fd4d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004fdc0`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004fdf6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140050076`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004fd4d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004fdc0`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004fdf6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140050076`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14005004a`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14005004a`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1400500c9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1400500c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStowedExceptionPlugin::Initialize(
        CStowedExceptionPlugin *this,
        struct WER_PLUGIN_INIT_IN *a2,
        __int64 a3,
        HINSTANCE a4)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  char *v8; // r15
  unsigned int v9; // edi
  unsigned int i; // r14d
  signed int v11; // eax
  __int64 v12; // r8
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // ecx
  char ***j; // rax
  char **v17; // rdi
  char ***k; // rax
  int v19; // eax
  char *v20; // rdx
  unsigned __int64 v21; // r8
  int v22; // eax
  unsigned int v23; // r12d
  void *v24; // rdi
  SIZE_T *lpNumberOfBytesRead; // [rsp+20h] [rbp-58h]
  unsigned int v27[2]; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-40h] BYREF
  void *Buffer; // [rsp+40h] [rbp-38h] BYREF
  char *v30[6]; // [rsp+48h] [rbp-30h] BYREF
  unsigned int v31; // [rsp+C8h] [rbp+50h] BYREF

  NumberOfBytesRead = 0;
  memset(v30, 0, 40);
  Buffer = 0;
  v31 = 0;
  v27[0] = 0;
  if ( wcscmp_0(*(const wchar_t **)a2, L"APPCRASH") && wcscmp_0(*(const wchar_t **)a2, L"MoAppCrash") )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( *((_DWORD *)a2 + 63) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( !*((_QWORD *)a2 + 38) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( !*((_DWORD *)a2 + 70) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( !*((_QWORD *)a2 + 36) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  v7 = *((_QWORD *)a2 + 36);
  if ( *(_DWORD *)v7 == -1073741189 && *(_DWORD *)(v7 + 24) == 2 )
  {
    v8 = *(char **)(v7 + 32);
    if ( v8 )
    {
      v9 = *(_DWORD *)(v7 + 40);
      if ( v9 )
      {
        *((_DWORD *)this + 68) = *((_DWORD *)a2 + 70);
        if ( v9 >= 0x100 )
          v9 = 256;
        CStowedExceptionPlugin::AddMemoryBlock(this, v8, 8 * v9);
        for ( i = 0; i < v9; ++i )
        {
          if ( ReadProcessMemory(*((HANDLE *)a2 + 38), &v8[8 * i], &Buffer, 8u, &NumberOfBytesRead) )
          {
            if ( NumberOfBytesRead == 8 )
            {
              v11 = CStowedExceptionPlugin::AddBlocksForStructure(this, *((void **)a2 + 38), Buffer);
              if ( v11 < 0
                && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v12, Buffer, v11);
              }
            }
          }
        }
        if ( ReadProcessMemory(*((HANDLE *)a2 + 38), v8, &Buffer, 8u, &NumberOfBytesRead)
          && NumberOfBytesRead == 8
          && ReadProcessMemory(*((HANDLE *)a2 + 38), Buffer, v30, 0x28u, &NumberOfBytesRead)
          && NumberOfBytesRead == 40
          && LODWORD(v30[0]) >= 0x28
          && (unsigned int)(HIDWORD(v30[0]) - 1397043249) <= 1 )
        {
          tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            (__int64)this + 136,
            (__int64)L"%08x",
            LODWORD(v30[1]));
          if ( (BYTE4(v30[1]) & 3) == 1 )
          {
            CStowedExceptionPlugin::BuildLoadedModuleList(
              (__int64)this + 224,
              *((void **)a2 + 38),
              *((_DWORD *)a2 + 70));
            CStowedExceptionPlugin::BuildUnloadedModuleList((__int64)this + 248, *((void **)a2 + 38));
            if ( v30[2] )
            {
              for ( j = (char ***)*((_QWORD *)this + 28); j != *((char ****)this + 29); ++j )
              {
                v17 = *j;
                if ( **j <= v30[2] && v30[2] < &(*v17)[*((unsigned int *)v17 + 2)] )
                  goto LABEL_57;
              }
              for ( k = (char ***)*((_QWORD *)this + 31); k != *((char ****)this + 32); ++k )
              {
                v17 = *k;
                if ( **k <= v30[2] && v30[2] < &(*v17)[*((unsigned int *)v17 + 2)] )
                {
                  v19 = 0;
                  goto LABEL_56;
                }
              }
              v17 = 0;
              v19 = -2147023728;
LABEL_56:
              if ( v19 >= 0 )
              {
LABEL_57:
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (__int64)this + 8,
                  (__int64)L"%016I64x",
                  v30[2] - *v17);
                v20 = v17[3];
                if ( v20 )
                {
                  v21 = -1;
                  do
                    ++v21;
                  while ( *(_WORD *)&v20[2 * v21] );
                }
                else
                {
                  v21 = 0;
                }
                utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                  (__int64)this + 40,
                  v20,
                  v21);
                if ( ((_BYTE)v17[4] & 1) != 0 )
                  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                    (__int64)this + 40,
                    L"_unloaded",
                    9u);
                LODWORD(lpNumberOfBytesRead) = *((unsigned __int16 *)v17 + 10);
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (__int64)this + 72,
                  (__int64)L"%u.%u.%u.%u",
                  *((unsigned __int16 *)v17 + 8),
                  *((unsigned __int16 *)v17 + 9),
                  lpNumberOfBytesRead,
                  *((unsigned __int16 *)v17 + 11));
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (__int64)this + 104,
                  (__int64)L"%08x",
                  *((unsigned int *)v17 + 3));
                return 0;
              }
            }
            if ( LODWORD(v30[3]) == 8 )
            {
              v22 = HIDWORD(v30[3]);
              if ( HIDWORD(v30[3]) )
              {
                if ( v30[4] )
                {
                  if ( HIDWORD(v30[3]) > 0xFFFF )
                    v22 = 0xFFFF;
                  v23 = 8 * v22;
                  v24 = VirtualAlloc(0, (unsigned int)(8 * v22), 0x1000u, 4u);
                  *(_QWORD *)v27 = v24;
                  if ( v24
                    && ReadProcessMemory(*((HANDLE *)a2 + 38), v30[4], v24, v23, &NumberOfBytesRead)
                    && NumberOfBytesRead )
                  {
                    CStowedExceptionPlugin::HashStackTrace(&v31, (__int64)this + 248);
                    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                      (__int64)this + 168,
                      (__int64)L"StackHash12_%03x",
                      v31);
                  }
                  if ( v24 )
                    VirtualFree(v24, 0, 0x8000u);
                }
              }
            }
            return 0;
          }
          if ( (BYTE4(v30[1]) & 3) == 2 )
          {
            v13 = CStowedExceptionPlugin::CalculateRemoteStringLength(v27, *((void **)a2 + 38), v30[2]);
            if ( v13 >= 0 )
            {
              v14 = v27[0];
              if ( 2 * (unsigned __int64)v27[0] > 0xFFFF )
                MicrosoftTelemetryAssertTriggeredNoArgs(0xFFFF);
              v15 = 2 * v14;
              if ( !(2 * v14) )
                return 0;
              goto LABEL_41;
            }
            if ( v13 == -805306106 )
            {
              v15 = 0xFFFF;
LABEL_41:
              if ( (int)CStowedExceptionPlugin::HashRemoteMemory(&v31, *((HANDLE *)a2 + 38), v30[2], v15) >= 0 )
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (__int64)this + 168,
                  (__int64)L"TextHash12_%03x",
                  v31);
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
0x14004fc20  push    rbp
0x14004fc22  push    rbx
0x14004fc23  push    rsi
0x14004fc24  push    rdi
0x14004fc25  push    r12
0x14004fc27  push    r13
0x14004fc29  push    r14
0x14004fc2b  push    r15
0x14004fc2d  mov     rbp, rsp
0x14004fc30  sub     rsp, 78h
0x14004fc34  mov     rbx, rdx
0x14004fc37  mov     rsi, rcx
0x14004fc3a  xor     r13d, r13d
0x14004fc3d  mov     [rbp+NumberOfBytesRead], r13
0x14004fc41  mov     [rbp+var_30], r13d
0x14004fc45  xorps   xmm0, xmm0
0x14004fc48  xor     eax, eax
0x14004fc4a  movups  xmmword ptr [rbp+var_2C], xmm0
0x14004fc4e  movups  xmmword ptr [rbp+lpBaseAddress], xmm0
0x14004fc52  mov     [rbp+var_C], eax
0x14004fc55  mov     [rbp+Buffer], r13
0x14004fc59  mov     [rbp+arg_8], r13d
0x14004fc5d  mov     [rbp+var_48], r13d
0x14004fc61  lea     rdx, aAppcrash; "APPCRASH"
0x14004fc68  mov     rcx, [rbx]; String1
0x14004fc6b  call    wcscmp_0
0x14004fc70  test    eax, eax
0x14004fc72  jz      short loc_14004FC8C
0x14004fc74  lea     rdx, aMoappcrash; "MoAppCrash"
0x14004fc7b  mov     rcx, [rbx]; String1
0x14004fc7e  call    wcscmp_0
0x14004fc83  test    eax, eax
0x14004fc85  jz      short loc_14004FC8C
0x14004fc87  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004fc8c  cmp     dword ptr [rbx+0FCh], 1
0x14004fc93  jz      short loc_14004FC9A
0x14004fc95  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004fc9a  cmp     [rbx+130h], r13
0x14004fca1  jnz     short loc_14004FCA8
0x14004fca3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004fca8  cmp     [rbx+118h], r13d
0x14004fcaf  jnz     short loc_14004FCB6
0x14004fcb1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004fcb6  cmp     [rbx+120h], r13
0x14004fcbd  jnz     short loc_14004FCC4
0x14004fcbf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004fcc4  mov     rax, [rbx+120h]
0x14004fccb  cmp     dword ptr [rax], 0C000027Bh
0x14004fcd1  jnz     loc_1400500D4
0x14004fcd7  cmp     dword ptr [rax+18h], 2
0x14004fcdb  jnz     loc_1400500D4
0x14004fce1  mov     r15, [rax+20h]
0x14004fce5  test    r15, r15
0x14004fce8  jz      loc_1400500D4
0x14004fcee  mov     edi, [rax+28h]
0x14004fcf1  test    edi, edi
0x14004fcf3  jz      loc_1400500D4
0x14004fcf9  mov     eax, [rbx+118h]
0x14004fcff  mov     [rsi+110h], eax
0x14004fd05  mov     eax, 100h
0x14004fd0a  cmp     edi, eax
0x14004fd0c  cmovnb  edi, eax
0x14004fd0f  lea     r8d, ds:0[rdi*8]; unsigned int
0x14004fd17  mov     rdx, r15; void *
0x14004fd1a  mov     rcx, rsi; this
0x14004fd1d  call    ?AddMemoryBlock@CStowedExceptionPlugin@@AEAAJPEAXKK@Z; CStowedExceptionPlugin::AddMemoryBlock(void *,ulong,ulong)
0x14004fd22  mov     r14d, r13d
0x14004fd25  mov     r12d, 8
0x14004fd2b  test    edi, edi
0x14004fd2d  jz      short loc_14004FDA6
0x14004fd2f  mov     eax, r14d
0x14004fd32  lea     rdx, [r15+rax*8]; lpBaseAddress
0x14004fd36  lea     rax, [rbp+NumberOfBytesRead]
0x14004fd3a  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004fd3f  mov     r9, r12; nSize
0x14004fd42  lea     r8, [rbp+Buffer]; lpBuffer
0x14004fd46  mov     rcx, [rbx+130h]; hProcess
0x14004fd4d  call    cs:__imp_ReadProcessMemory
0x14004fd53  test    eax, eax
0x14004fd55  jz      short loc_14004FD9E
0x14004fd57  cmp     [rbp+NumberOfBytesRead], r12
0x14004fd5b  jnz     short loc_14004FD9E
0x14004fd5d  mov     r8, [rbp+Buffer]; void *
0x14004fd61  mov     rdx, [rbx+130h]; void *
0x14004fd68  mov     rcx, rsi; this
0x14004fd6b  call    ?AddBlocksForStructure@CStowedExceptionPlugin@@AEAAJPEAX0@Z; CStowedExceptionPlugin::AddBlocksForStructure(void *,void *)
0x14004fd70  test    eax, eax
0x14004fd72  jns     short loc_14004FD9E
0x14004fd74  lea     rdx, WPP_GLOBAL_Control
0x14004fd7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fd82  cmp     rcx, rdx
0x14004fd85  jz      short loc_14004FD9E
0x14004fd87  test    byte ptr [rcx+1Ch], 2
0x14004fd8b  jz      short loc_14004FD9E
0x14004fd8d  mov     dword ptr [rsp+78h+lpNumberOfBytesRead], eax
0x14004fd91  mov     r9, [rbp+Buffer]
0x14004fd95  mov     rcx, [rcx+10h]
0x14004fd99  call    WPP_SF_qD
0x14004fd9e  inc     r14d
0x14004fda1  cmp     r14d, edi
0x14004fda4  jb      short loc_14004FD2F
0x14004fda6  lea     rax, [rbp+NumberOfBytesRead]
0x14004fdaa  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004fdaf  mov     r9, r12; nSize
0x14004fdb2  lea     r8, [rbp+Buffer]; lpBuffer
0x14004fdb6  mov     rdx, r15; lpBaseAddress
0x14004fdb9  mov     rcx, [rbx+130h]; hProcess
0x14004fdc0  call    cs:__imp_ReadProcessMemory
0x14004fdc6  test    eax, eax
0x14004fdc8  jz      loc_1400500D0
0x14004fdce  cmp     [rbp+NumberOfBytesRead], r12
0x14004fdd2  jnz     loc_1400500D0
0x14004fdd8  lea     rax, [rbp+NumberOfBytesRead]
0x14004fddc  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004fde1  mov     r9d, 28h ; '('; nSize
0x14004fde7  lea     r8, [rbp+var_30]; lpBuffer
0x14004fdeb  mov     rdx, [rbp+Buffer]; lpBaseAddress
0x14004fdef  mov     rcx, [rbx+130h]; hProcess
0x14004fdf6  call    cs:__imp_ReadProcessMemory
0x14004fdfc  test    eax, eax
0x14004fdfe  jz      loc_1400500D0
0x14004fe04  cmp     [rbp+NumberOfBytesRead], 28h ; '('
0x14004fe09  jnz     loc_1400500D0
0x14004fe0f  cmp     [rbp+var_30], 28h ; '('
0x14004fe13  jb      loc_1400500D0
0x14004fe19  mov     eax, dword ptr [rbp+var_2C]
0x14004fe1c  add     eax, 0ACBACFCFh
0x14004fe21  cmp     eax, 1
0x14004fe24  ja      loc_1400500D0
0x14004fe2a  lea     rcx, [rsi+88h]
0x14004fe31  mov     r8d, dword ptr [rbp+var_2C+4]
0x14004fe35  lea     rdx, a08x_0; "%08x"
0x14004fe3c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14004fe41  mov     eax, dword ptr [rbp+var_2C+8]
0x14004fe44  and     eax, 3
0x14004fe47  sub     eax, 1
0x14004fe4a  jz      loc_14004FEDB
0x14004fe50  cmp     eax, 1
0x14004fe53  jnz     loc_1400500D0
0x14004fe59  mov     r8, [rbp+var_2C+0Ch]; void *
0x14004fe5d  mov     rdx, [rbx+130h]; void *
0x14004fe64  lea     rcx, [rbp+var_48]; unsigned int *
0x14004fe68  call    ?CalculateRemoteStringLength@CStowedExceptionPlugin@@CAJPEAKPEAX1K@Z; CStowedExceptionPlugin::CalculateRemoteStringLength(ulong *,void *,void *,ulong)
0x14004fe6d  test    eax, eax
0x14004fe6f  js      short loc_14004FE95
0x14004fe71  mov     edi, [rbp+var_48]
0x14004fe74  mov     eax, edi
0x14004fe76  add     rax, rax
0x14004fe79  mov     ecx, 0FFFFh
0x14004fe7e  cmp     rax, rcx
0x14004fe81  jbe     short loc_14004FE88
0x14004fe83  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004fe88  lea     ecx, [rdi+rdi]
0x14004fe8b  test    ecx, ecx
0x14004fe8d  jz      loc_1400500D0
0x14004fe93  jmp     short loc_14004FEA5
0x14004fe95  cmp     eax, 0D0000106h
0x14004fe9a  jnz     loc_1400500D0
0x14004fea0  mov     ecx, 0FFFFh
0x14004fea5  mov     r9d, ecx; unsigned __int64
0x14004fea8  mov     r8, [rbp+var_2C+0Ch]; void *
0x14004feac  mov     rdx, [rbx+130h]; hProcess
0x14004feb3  lea     rcx, [rbp+arg_8]; unsigned int *
0x14004feb7  call    ?HashRemoteMemory@CStowedExceptionPlugin@@CAJPEAKPEAX1_K@Z; CStowedExceptionPlugin::HashRemoteMemory(ulong *,void *,void *,unsigned __int64)
0x14004febc  test    eax, eax
0x14004febe  js      loc_1400500D0
0x14004fec4  lea     rcx, [rsi+0A8h]
0x14004fecb  mov     r8d, [rbp+arg_8]
0x14004fecf  lea     rdx, aTexthash1203x; "TextHash12_%03x"
0x14004fed6  jmp     loc_140050001
0x14004fedb  lea     r14, [rsi+0E0h]
0x14004fee2  mov     r8d, [rbx+118h]
0x14004fee9  mov     rdx, [rbx+130h]
0x14004fef0  mov     rcx, r14
0x14004fef3  call    ?BuildLoadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAXK@Z; CStowedExceptionPlugin::BuildLoadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *,ulong)
0x14004fef8  lea     r15, [rsi+0F8h]
0x14004feff  mov     rdx, [rbx+130h]
0x14004ff06  mov     rcx, r15
0x14004ff09  call    ?BuildUnloadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAX@Z; CStowedExceptionPlugin::BuildUnloadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *)
0x14004ff0e  mov     r8, [rbp+var_2C+0Ch]
0x14004ff12  test    r8, r8
0x14004ff15  jz      loc_14005000B
0x14004ff1b  mov     rax, [r14]
0x14004ff1e  cmp     rax, [r14+8]
0x14004ff22  jz      short loc_14004FF3C
0x14004ff24  mov     rdi, [rax]
0x14004ff27  cmp     [rdi], r8
0x14004ff2a  ja      short loc_14004FF37
0x14004ff2c  mov     ecx, [rdi+8]
0x14004ff2f  add     rcx, [rdi]
0x14004ff32  cmp     r8, rcx
0x14004ff35  jb      short loc_14004FF72
0x14004ff37  add     rax, r12
0x14004ff3a  jmp     short loc_14004FF1E
0x14004ff3c  mov     rax, [r15]
0x14004ff3f  cmp     rax, [r15+8]
0x14004ff43  jz      short loc_14004FF62
0x14004ff45  mov     rdi, [rax]
0x14004ff48  cmp     [rdi], r8
0x14004ff4b  ja      short loc_14004FF58
0x14004ff4d  mov     ecx, [rdi+8]
0x14004ff50  add     rcx, [rdi]
0x14004ff53  cmp     r8, rcx
0x14004ff56  jb      short loc_14004FF5D
0x14004ff58  add     rax, r12
0x14004ff5b  jmp     short loc_14004FF3F
0x14004ff5d  mov     eax, r13d
0x14004ff60  jmp     short loc_14004FF6A
0x14004ff62  mov     rdi, r13
0x14004ff65  mov     eax, 80070490h
0x14004ff6a  test    eax, eax
0x14004ff6c  js      loc_14005000B
0x14004ff72  sub     r8, [rdi]
0x14004ff75  lea     rcx, [rsi+8]
0x14004ff79  lea     rdx, a016i64x; "%016I64x"
0x14004ff80  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14004ff85  mov     rdx, [rdi+18h]
0x14004ff89  test    rdx, rdx
0x14004ff8c  jz      short loc_14004FF9E
0x14004ff8e  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004ff92  inc     r8
0x14004ff95  cmp     [rdx+r8*2], r13w
0x14004ff9a  jnz     short loc_14004FF92
0x14004ff9c  jmp     short loc_14004FFA1
0x14004ff9e  mov     r8, r13
0x14004ffa1  lea     rcx, [rsi+28h]
0x14004ffa5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004ffaa  test    byte ptr [rdi+20h], 1
0x14004ffae  jz      short loc_14004FFC6
0x14004ffb0  mov     r8d, 9
0x14004ffb6  lea     rdx, SubStr; "_unloaded"
0x14004ffbd  lea     rcx, [rsi+28h]
0x14004ffc1  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14004ffc6  movzx   eax, word ptr [rdi+16h]
0x14004ffca  movzx   r10d, word ptr [rdi+14h]
0x14004ffcf  movzx   r9d, word ptr [rdi+12h]
0x14004ffd4  movzx   r8d, word ptr [rdi+10h]
0x14004ffd9  lea     rcx, [rsi+48h]
0x14004ffdd  mov     [rsp+78h+var_50], eax
0x14004ffe1  mov     dword ptr [rsp+78h+lpNumberOfBytesRead], r10d
0x14004ffe6  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x14004ffed  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14004fff2  lea     rcx, [rsi+68h]
0x14004fff6  mov     r8d, [rdi+0Ch]
0x14004fffa  lea     rdx, a08x_0; "%08x"
0x140050001  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140050006  jmp     loc_1400500D0
0x14005000b  cmp     dword ptr [rbp+lpBaseAddress+4], r12d
0x14005000f  jnz     loc_1400500D0
0x140050015  mov     eax, dword ptr [rbp+lpBaseAddress+8]
0x140050018  test    eax, eax
0x14005001a  jz      loc_1400500D0
0x140050020  cmp     [rbp+lpBaseAddress+0Ch], r13
0x140050024  jz      loc_1400500D0
0x14005002a  mov     ecx, 0FFFFh
0x14005002f  cmp     eax, ecx
0x140050031  cmova   eax, ecx
0x140050034  shl     eax, 3
0x140050037  mov     r12d, eax
0x14005003a  mov     r9d, 4; flProtect
0x140050040  mov     r8d, 1000h; flAllocationType
0x140050046  mov     edx, eax; dwSize
0x140050048  xor     ecx, ecx; lpAddress
0x14005004a  call    cs:__imp_VirtualAlloc
0x140050050  mov     rdi, rax
0x140050053  mov     qword ptr [rbp+var_48], rax
0x140050057  test    rax, rax
0x14005005a  jz      short loc_1400500B9
0x14005005c  lea     rax, [rbp+NumberOfBytesRead]
0x140050060  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140050065  mov     r9d, r12d; nSize
0x140050068  mov     r8, rdi; lpBuffer
0x14005006b  mov     rdx, [rbp+lpBaseAddress+0Ch]; lpBaseAddress
0x14005006f  mov     rcx, [rbx+130h]; hProcess
0x140050076  call    cs:__imp_ReadProcessMemory
0x14005007c  test    eax, eax
0x14005007e  jz      short loc_1400500B9
0x140050080  mov     rdx, [rbp+NumberOfBytesRead]
0x140050084  test    rdx, rdx
0x140050087  jz      short loc_1400500B9
0x140050089  shr     rdx, 3
0x14005008d  mov     [rsp+78h+lpNumberOfBytesRead], r15; __int64
0x140050092  mov     r9, r14
0x140050095  mov     r8, rdi
0x140050098  lea     rcx, [rbp+arg_8]; unsigned int *
0x14005009c  call    ?HashStackTrace@CStowedExceptionPlugin@@CAJPEAKKPEAPEAXPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@2@Z; CStowedExceptionPlugin::HashStackTrace(ulong *,ulong,void * *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *)
0x1400500a1  lea     rcx, [rsi+0A8h]
0x1400500a8  mov     r8d, [rbp+arg_8]
0x1400500ac  lea     rdx, aStackhash1203x; "StackHash12_%03x"
0x1400500b3  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400500b8  nop
0x1400500b9  test    rdi, rdi
0x1400500bc  jz      short loc_1400500D0
0x1400500be  xor     edx, edx; dwSize
0x1400500c0  mov     r8d, 8000h; dwFreeType
0x1400500c6  mov     rcx, rdi; lpAddress
0x1400500c9  call    cs:__imp_VirtualFree
0x1400500cf  nop
0x1400500d0  xor     eax, eax
0x1400500d2  jmp     short loc_1400500D9
  ... truncated ...
```
