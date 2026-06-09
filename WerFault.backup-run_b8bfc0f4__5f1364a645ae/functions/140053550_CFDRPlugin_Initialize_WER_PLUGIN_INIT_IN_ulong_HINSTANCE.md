# CFDRPlugin::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x140053550`
- end: `0x140053822`
- name: `?Initialize@CFDRPlugin@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this, struct WER_PLUGIN_INIT_IN *, unsigned int, HINSTANCE)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140002728`
- `0x14000c8a0`
- `0x14001444c`
- `0x140014474`
- `0x140015b40`
- `0x140053550`
- `0x140053f7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400535ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140053607`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005361f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140053633`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140053647`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005365b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400537a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400535ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140053607`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005361f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140053633`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140053647`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005365b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400537a0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400536fe`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400536fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFDRPlugin::Initialize(CFDRPlugin *this, struct WER_PLUGIN_INIT_IN *a2, __int64 a3, HINSTANCE a4)
{
  _WORD *v7; // rcx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  CUserModeHangReport *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // r15
  _QWORD *v15; // r14
  DWORD ProcessId; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rcx
  void *v20[2]; // [rsp+20h] [rbp-20h] BYREF
  _WORD v21[8]; // [rsp+30h] [rbp-10h] BYREF
  int v22; // [rsp+78h] [rbp+38h] BYREF

  v7 = v21;
  v20[0] = v21;
  v20[1] = v21;
  v21[0] = 0;
  v22 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      v7 = v20[0];
    }
    if ( v7 != v21 )
      operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942487LL;
  }
  if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"APPCRASH")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"MoAppCrash")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"AppHangB1")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"AppHangXProcB1")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"MoAppHang")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"MoAppHangXProc") )
  {
    *((_QWORD *)this + 8) = a4;
    if ( (unsigned int)(*((_DWORD *)a2 + 63) - 1) > 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v9);
    v13 = *((_DWORD *)a2 + 63);
    if ( v13 == 1 )
    {
      v14 = *((_QWORD *)a2 + 33);
      v15 = (_QWORD *)((char *)this + 40);
      *((_QWORD *)this + 5) = *((_QWORD *)a2 + 38);
      *((_DWORD *)this + 12) = *((_DWORD *)a2 + 70);
    }
    else
    {
      if ( v13 != 2 )
      {
LABEL_37:
        v10 = -2147024809;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_41;
        }
        v12 = 12;
        goto LABEL_40;
      }
      v14 = *((_QWORD *)a2 + 32);
      v15 = (_QWORD *)((char *)this + 40);
      *((_QWORD *)this + 5) = *((_QWORD *)a2 + 33);
      ProcessId = GetProcessId(*((HANDLE *)a2 + 33));
      *((_DWORD *)this + 12) = ProcessId;
      if ( !ProcessId )
        MicrosoftTelemetryAssertTriggeredNoArgs(v17);
    }
    if ( v14 && *v15 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v14 + 2 * v18) );
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              (char *)this + 8,
                              v14,
                              v18) )
      {
        if ( (int)CFDRPlugin::ReadFDRSessionSettings(v19, (char *)this + 80, v20, &v22) >= 0 )
        {
          *((_DWORD *)this + 18) = 1;
          if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 1), v20[0]) && *((_DWORD *)this + 12) == v22 )
            *((_DWORD *)this + 19) = 1;
        }
        v10 = 0;
      }
      else
      {
        v10 = -2147024882;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_928a4490cd403d1d5470036a68085293_Traceguids,
            2147942414LL);
        }
      }
      goto LABEL_41;
    }
    goto LABEL_37;
  }
  v10 = -2147467263;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
  {
    goto LABEL_41;
  }
  v12 = 11;
LABEL_40:
  WPP_SF_(*((_QWORD *)v11 + 2), v12, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
LABEL_41:
  if ( v20[0] != v21 )
    operator delete(v20[0], (const struct std::nothrow_t *)&std::nothrow);
  return v10;
}

```

## disassembly

```asm
0x140053550  mov     [rsp-28h+arg_0], rbx
0x140053555  mov     [rsp-28h+arg_10], rsi
0x14005355a  push    rbp
0x14005355b  push    rdi
0x14005355c  push    r12
0x14005355e  push    r14
0x140053560  push    r15
0x140053562  mov     rbp, rsp
0x140053565  sub     rsp, 40h
0x140053569  mov     rdi, r9
0x14005356c  mov     rbx, rdx
0x14005356f  mov     rsi, rcx
0x140053572  lea     rcx, [rbp+var_10]
0x140053576  mov     [rbp+var_20], rcx
0x14005357a  lea     rax, [rbp+var_10]
0x14005357e  mov     [rbp+var_18], rax
0x140053582  xor     r12d, r12d
0x140053585  mov     [rbp+var_10], r12w
0x14005358a  mov     [rbp+arg_8], r12d
0x14005358e  test    rdx, rdx
0x140053591  jnz     short loc_1400535E5
0x140053593  lea     rax, WPP_GLOBAL_Control
0x14005359a  mov     r9, cs:WPP_GLOBAL_Control
0x1400535a1  cmp     r9, rax
0x1400535a4  jz      short loc_1400535C6
0x1400535a6  lea     edi, [rdx+1]
0x1400535a9  test    [r9+1Ch], dil
0x1400535ad  jz      short loc_1400535C6
0x1400535af  lea     edx, [rbx+0Ah]
0x1400535b2  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1400535b9  mov     rcx, [r9+10h]
0x1400535bd  call    WPP_SF_
0x1400535c2  mov     rcx, [rbp+var_20]; void *
0x1400535c6  lea     rax, [rbp+var_10]
0x1400535ca  cmp     rcx, rax
0x1400535cd  jz      short loc_1400535DB
0x1400535cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400535d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400535db  mov     eax, 80070057h
0x1400535e0  jmp     loc_140053809
0x1400535e5  lea     rdx, aAppcrash; "APPCRASH"
0x1400535ec  mov     rcx, [rbx]
0x1400535ef  call    cs:__imp__o__wcsicmp
0x1400535f5  test    eax, eax
0x1400535f7  jz      loc_140053695
0x1400535fd  lea     rdx, aMoappcrash; "MoAppCrash"
0x140053604  mov     rcx, [rbx]
0x140053607  call    cs:__imp__o__wcsicmp
0x14005360d  test    eax, eax
0x14005360f  jz      loc_140053695
0x140053615  lea     rdx, aApphangb1; "AppHangB1"
0x14005361c  mov     rcx, [rbx]
0x14005361f  call    cs:__imp__o__wcsicmp
0x140053625  test    eax, eax
0x140053627  jz      short loc_140053695
0x140053629  lea     rdx, aApphangxprocb1; "AppHangXProcB1"
0x140053630  mov     rcx, [rbx]
0x140053633  call    cs:__imp__o__wcsicmp
0x140053639  test    eax, eax
0x14005363b  jz      short loc_140053695
0x14005363d  lea     rdx, aMoapphang; "MoAppHang"
0x140053644  mov     rcx, [rbx]
0x140053647  call    cs:__imp__o__wcsicmp
0x14005364d  test    eax, eax
0x14005364f  jz      short loc_140053695
0x140053651  lea     rdx, aMoapphangxproc; "MoAppHangXProc"
0x140053658  mov     rcx, [rbx]
0x14005365b  call    cs:__imp__o__wcsicmp
0x140053661  test    eax, eax
0x140053663  jz      short loc_140053695
0x140053665  mov     ebx, 80004001h
0x14005366a  lea     rax, WPP_GLOBAL_Control
0x140053671  mov     rcx, cs:WPP_GLOBAL_Control
0x140053678  cmp     rcx, rax
0x14005367b  jz      loc_1400537EE
0x140053681  test    byte ptr [rcx+1Ch], 4
0x140053685  jz      loc_1400537EE
0x14005368b  mov     edx, 0Bh
0x140053690  jmp     loc_1400537DD
0x140053695  mov     [rsi+40h], rdi
0x140053699  mov     eax, [rbx+0FCh]
0x14005369f  mov     edi, 1
0x1400536a4  sub     eax, edi
0x1400536a6  cmp     eax, edi
0x1400536a8  jbe     short loc_1400536AF
0x1400536aa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400536af  mov     eax, [rbx+0FCh]
0x1400536b5  cmp     eax, edi
0x1400536b7  jnz     short loc_1400536D9
0x1400536b9  mov     r15, [rbx+108h]
0x1400536c0  lea     r14, [rsi+28h]
0x1400536c4  mov     rax, [rbx+130h]
0x1400536cb  mov     [r14], rax
0x1400536ce  mov     eax, [rbx+118h]
0x1400536d4  mov     [rsi+30h], eax
0x1400536d7  jmp     short loc_140053710
0x1400536d9  cmp     eax, 2
0x1400536dc  jnz     loc_1400537BA
0x1400536e2  mov     r15, [rbx+100h]
0x1400536e9  lea     r14, [rsi+28h]
0x1400536ed  mov     rax, [rbx+108h]
0x1400536f4  mov     [r14], rax
0x1400536f7  mov     rcx, [rbx+108h]; Process
0x1400536fe  call    cs:__imp_GetProcessId
0x140053704  mov     [rsi+30h], eax
0x140053707  test    eax, eax
0x140053709  jnz     short loc_140053710
0x14005370b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140053710  test    r15, r15
0x140053713  jz      loc_1400537BA
0x140053719  cmp     [r14], r12
0x14005371c  jz      loc_1400537BA
0x140053722  or      r8, 0FFFFFFFFFFFFFFFFh
0x140053726  inc     r8
0x140053729  cmp     [r15+r8*2], r12w
0x14005372e  jnz     short loc_140053726
0x140053730  mov     rdx, r15
0x140053733  lea     rcx, [rsi+8]
0x140053737  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14005373c  test    al, al
0x14005373e  jnz     short loc_140053780
0x140053740  mov     ebx, 8007000Eh
0x140053745  lea     rax, WPP_GLOBAL_Control
0x14005374c  mov     rcx, cs:WPP_GLOBAL_Control
0x140053753  cmp     rcx, rax
0x140053756  jz      loc_1400537EE
0x14005375c  test    [rcx+1Ch], dil
0x140053760  jz      loc_1400537EE
0x140053766  mov     edx, 0Dh
0x14005376b  mov     r9d, ebx
0x14005376e  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140053775  mov     rcx, [rcx+10h]
0x140053779  call    WPP_SF_d
0x14005377e  jmp     short loc_1400537EE
0x140053780  lea     rdx, [rsi+50h]
0x140053784  lea     r9, [rbp+arg_8]
0x140053788  lea     r8, [rbp+var_20]
0x14005378c  call    ?ReadFDRSessionSettings@CFDRPlugin@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0PEAK@Z; CFDRPlugin::ReadFDRSessionSettings(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,ulong *)
0x140053791  test    eax, eax
0x140053793  js      short loc_1400537B5
0x140053795  mov     [rsi+48h], edi
0x140053798  mov     rdx, [rbp+var_20]
0x14005379c  mov     rcx, [rsi+8]
0x1400537a0  call    cs:__imp__o__wcsicmp
0x1400537a6  test    eax, eax
0x1400537a8  jnz     short loc_1400537B5
0x1400537aa  mov     eax, [rbp+arg_8]
0x1400537ad  cmp     [rsi+30h], eax
0x1400537b0  jnz     short loc_1400537B5
0x1400537b2  mov     [rsi+4Ch], edi
0x1400537b5  mov     ebx, r12d
0x1400537b8  jmp     short loc_1400537EE
0x1400537ba  mov     ebx, 80070057h
0x1400537bf  lea     rax, WPP_GLOBAL_Control
0x1400537c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400537cd  cmp     rcx, rax
0x1400537d0  jz      short loc_1400537EE
0x1400537d2  test    [rcx+1Ch], dil
0x1400537d6  jz      short loc_1400537EE
0x1400537d8  mov     edx, 0Ch
0x1400537dd  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1400537e4  mov     rcx, [rcx+10h]
0x1400537e8  call    WPP_SF_
0x1400537ed  nop
0x1400537ee  lea     rax, [rbp+var_10]
0x1400537f2  mov     rcx, [rbp+var_20]; void *
0x1400537f6  cmp     rcx, rax
0x1400537f9  jz      short loc_140053807
0x1400537fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140053802  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140053807  mov     eax, ebx
0x140053809  lea     r11, [rsp+40h+var_s0]
0x14005380e  mov     rbx, [r11+30h]
0x140053812  mov     rsi, [r11+40h]
0x140053816  mov     rsp, r11
0x140053819  pop     r15
0x14005381b  pop     r14
0x14005381d  pop     r12
0x14005381f  pop     rdi
0x140053820  pop     rbp
0x140053821  retn
```
