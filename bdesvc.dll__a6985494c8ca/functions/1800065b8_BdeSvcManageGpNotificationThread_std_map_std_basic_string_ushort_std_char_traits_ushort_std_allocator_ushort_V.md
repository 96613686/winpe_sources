# BdeSvcManageGpNotificationThread(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,VolumeEntry,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,VolumeEntry>>> *)

- ea: `0x1800065b8`
- end: `0x180006935`
- name: `?BdeSvcManageGpNotificationThread@@YAKPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z`
- size: `893`
- prototype: `__int64 __fastcall(void ***)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180007d90`
- `0x18003c780`

## callees

- `0x180005374`
- `0x1800053a0`
- `0x180006260`
- `0x1800065b8`
- `0x180007d10`
- `0x180009f30`
- `0x180009f60`
- `0x18001c1ec`
- `0x18002ae7c`
- `0x180046560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068d8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800068c8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800068c8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800067d9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800067d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006803`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000681b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000681b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006873`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000665f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000665f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006750`

## pseudocode

```c
__int64 __fastcall BdeSvcManageGpNotificationThread(void ***a1)
{
  unsigned int v2; // ebp
  int v3; // r14d
  void **v4; // rbx
  _DWORD *v5; // rax
  void *v6; // rsi
  int v7; // ecx
  int v8; // r9d
  void *v9; // r8
  int v10; // edx
  _QWORD *v11; // r9
  const unsigned __int16 *v12; // rcx
  PVOID *v13; // rcx
  DWORD LastError; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  void *i; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  v2 = 0;
  i = 0;
  if ( a1 )
  {
    v3 = 0;
  }
  else
  {
    if ( (unsigned int)AllocVolumeMap(&i) )
      goto LABEL_62;
    v3 = 1;
    a1 = (void ***)i;
    EnumVolumes((__int64)i, 0, 0, 1, 0);
  }
  v4 = (void **)**a1;
  for ( i = v4; ; v4 = (void **)i )
  {
    if ( v4 == *a1 )
    {
      i = &g_lockGpNotificationThreadMgmt;
      EnterCriticalSection(&g_lockGpNotificationThreadMgmt);
      if ( !v2 && !g_bPcrMon )
      {
        if ( g_hGpNotificationThreadStopEvent )
          SetEvent(g_hGpNotificationThreadStopEvent);
        goto LABEL_58;
      }
      if ( g_hGpNotificationThreadStopEvent )
      {
        ResetEvent(g_hGpNotificationThreadStopEvent);
      }
      else
      {
        g_hGpNotificationThreadStopEvent = CreateEventW(0, 1, 0, 0);
        if ( !g_hGpNotificationThreadStopEvent )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              65,
              &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
              LastError);
          goto LABEL_58;
        }
        if ( WorkerThreadLauncher((unsigned int (*)(void *))BdeSvcGpNotificationThread) )
        {
          if ( g_hGpNotificationThreadStopEvent )
          {
            CloseHandle(g_hGpNotificationThreadStopEvent);
            g_hGpNotificationThreadStopEvent = 0;
          }
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_58;
          v16 = 66;
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_58;
          v16 = 67;
        }
        WPP_SF_(v15[2], v16, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      }
LABEL_58:
      LeaveCriticalSection(&g_lockGpNotificationThreadMgmt);
      goto LABEL_59;
    }
    v5 = LocalAlloc(0x40u, 0x20u);
    v6 = v5;
    if ( !v5 )
      break;
    v7 = *((_DWORD *)v4 + 18);
    v8 = *((_DWORD *)v4 + 34);
    v9 = v4[19];
    v10 = *((_DWORD *)v4 + 16);
    *v5 = v10;
    *((_QWORD *)v5 + 1) = v9;
    v5[4] = v8;
    v5[5] = v7;
    *((_WORD *)v5 + 12) = 0;
    if ( ((_BYTE)v4[8] & 1) != 0
      || (v10 & 0x800) == 0
      && ((unsigned __int8)v9 & 8) == 0
      && v10 >= 0
      && ((v10 & 0xF0) != 0
       || (v10 & 2) != 0
       || (v10 & 8) != 0 && (v10 & 0x400) != 0 && (v10 & 0x2000000) == 0
       || (int)(v8 + 0x80000000) >= 0 && v8 != -2144272297 && (v10 & 0x4000) != 0
       || (v10 & 1) != 0 && (v10 & 4) != 0) )
    {
      ++v2;
      if ( *((_DWORD *)v4 + 23) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v11 = v4 + 4;
          if ( (unsigned __int64)v4[7] > 7 )
            v11 = (_QWORD *)*v11;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v11);
        }
        v12 = (const unsigned __int16 *)(v4 + 13);
        if ( (unsigned __int64)v4[16] > 7 )
          v12 = *(const unsigned __int16 **)v12;
        BdeSvcApplyGroupPolicyVolume(v12);
      }
    }
    LocalFree(v6);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>,std::_Iterator_base0>::operator++((__int64 *)&i);
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
LABEL_59:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    FreeVolumeMap(a1);
LABEL_62:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 )
    WPP_SF_(v13[2], 68, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x1800065b8  mov     [rsp+arg_8], rbx
0x1800065bd  mov     [rsp+arg_10], rbp
0x1800065c2  push    rsi
0x1800065c3  push    rdi
0x1800065c4  push    r12
0x1800065c6  push    r13
0x1800065c8  push    r14
0x1800065ca  sub     rsp, 30h
0x1800065ce  mov     rdi, rcx
0x1800065d1  lea     r12, WPP_GLOBAL_Control
0x1800065d8  lea     r13, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x1800065df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065e6  cmp     rcx, r12
0x1800065e9  jz      short loc_180006602
0x1800065eb  test    byte ptr [rcx+1Ch], 20h
0x1800065ef  jz      short loc_180006602
0x1800065f1  mov     edx, 3Eh ; '>'
0x1800065f6  mov     r8, r13
0x1800065f9  mov     rcx, [rcx+10h]
0x1800065fd  call    WPP_SF_
0x180006602  xor     ebp, ebp
0x180006604  mov     [rsp+58h+arg_0], rbp
0x180006609  test    rdi, rdi
0x18000660c  jnz     short loc_180006640
0x18000660e  lea     rcx, [rsp+58h+arg_0]
0x180006613  call    ?AllocVolumeMap@@YAKPEAPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; AllocVolumeMap(std::map<std::wstring,VolumeEntry> * *)
0x180006618  test    eax, eax
0x18000661a  jnz     loc_1800068F8
0x180006620  lea     r14d, [rbp+1]
0x180006624  mov     [rsp+58h+var_38], bpl
0x180006629  mov     r9b, r14b
0x18000662c  xor     r8d, r8d
0x18000662f  xor     edx, edx
0x180006631  mov     rdi, [rsp+58h+arg_0]
0x180006636  mov     rcx, rdi
0x180006639  call    ?EnumVolumes@@YAKPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@_NPEA_K11@Z; EnumVolumes(std::map<std::wstring,VolumeEntry> *,bool,unsigned __int64 *,bool,bool)
0x18000663e  jmp     short loc_180006643
0x180006640  xor     r14d, r14d
0x180006643  mov     rbx, [rdi]
0x180006646  mov     rbx, [rbx]
0x180006649  mov     [rsp+58h+arg_0], rbx
0x18000664e  cmp     rbx, [rdi]
0x180006651  jz      loc_1800067A0
0x180006657  mov     edx, 20h ; ' '; uBytes
0x18000665c  lea     ecx, [rdx+20h]; uFlags
0x18000665f  call    cs:__imp_LocalAlloc
0x180006666  nop     dword ptr [rax+rax+00h]
0x18000666b  mov     rsi, rax
0x18000666e  test    rax, rax
0x180006671  jz      loc_180006770
0x180006677  mov     ecx, [rbx+48h]
0x18000667a  mov     r9d, [rbx+88h]
0x180006681  mov     r8, [rbx+98h]
0x180006688  mov     edx, [rbx+40h]
0x18000668b  mov     [rax], edx
0x18000668d  mov     [rax+8], r8
0x180006691  mov     [rax+10h], r9d
0x180006695  mov     [rax+14h], ecx
0x180006698  xor     ecx, ecx
0x18000669a  mov     [rax+18h], cx
0x18000669e  test    byte ptr [rbx+40h], 1
0x1800066a2  jnz     short loc_180006701
0x1800066a4  bt      edx, 0Bh
0x1800066a8  jb      loc_18000674D
0x1800066ae  test    r8b, 8
0x1800066b2  jnz     loc_18000674D
0x1800066b8  test    edx, edx
0x1800066ba  js      loc_18000674D
0x1800066c0  test    dl, 0F0h
0x1800066c3  jnz     short loc_180006701
0x1800066c5  test    dl, 2
0x1800066c8  jnz     short loc_180006701
0x1800066ca  test    dl, 8
0x1800066cd  jz      short loc_1800066DB
0x1800066cf  bt      edx, 0Ah
0x1800066d3  jnb     short loc_1800066DB
0x1800066d5  bt      edx, 19h
0x1800066d9  jnb     short loc_180006701
0x1800066db  mov     ecx, 80000000h
0x1800066e0  lea     eax, [r9+rcx]
0x1800066e4  test    ecx, eax
0x1800066e6  jnz     short loc_1800066F7
0x1800066e8  cmp     r9d, 80310057h
0x1800066ef  jz      short loc_1800066F7
0x1800066f1  bt      edx, 0Eh
0x1800066f5  jb      short loc_180006701
0x1800066f7  test    dl, 1
0x1800066fa  jz      short loc_18000674D
0x1800066fc  test    dl, 4
0x1800066ff  jz      short loc_18000674D
0x180006701  inc     ebp
0x180006703  cmp     dword ptr [rbx+5Ch], 0
0x180006707  jz      short loc_18000674D
0x180006709  mov     rcx, cs:WPP_GLOBAL_Control
0x180006710  cmp     rcx, r12
0x180006713  jz      short loc_18000673A
0x180006715  test    byte ptr [rcx+1Ch], 8
0x180006719  jz      short loc_18000673A
0x18000671b  lea     r9, [rbx+20h]
0x18000671f  cmp     qword ptr [r9+18h], 7
0x180006724  jbe     short loc_180006729
0x180006726  mov     r9, [r9]
0x180006729  mov     edx, 40h ; '@'
0x18000672e  mov     r8, r13
0x180006731  mov     rcx, [rcx+10h]
0x180006735  call    WPP_SF_S
0x18000673a  lea     rcx, [rbx+68h]
0x18000673e  cmp     qword ptr [rcx+18h], 7
0x180006743  jbe     short loc_180006748
0x180006745  mov     rcx, [rcx]; unsigned __int16 *
0x180006748  call    ?BdeSvcApplyGroupPolicyVolume@@YAXPEBG@Z; BdeSvcApplyGroupPolicyVolume(ushort const *)
0x18000674d  mov     rcx, rsi; hMem
0x180006750  call    cs:__imp_LocalFree
0x180006757  nop     dword ptr [rax+rax+00h]
0x18000675c  lea     rcx, [rsp+58h+arg_0]
0x180006761  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>,std::_Iterator_base0>::operator++(void)
0x180006766  mov     rbx, [rsp+58h+arg_0]
0x18000676b  jmp     loc_18000664E
0x180006770  mov     rcx, cs:WPP_GLOBAL_Control
0x180006777  cmp     rcx, r12
0x18000677a  jz      loc_1800068EB
0x180006780  test    byte ptr [rcx+1Ch], 2
0x180006784  jz      loc_1800068EB
0x18000678a  mov     edx, 3Fh ; '?'
0x18000678f  mov     r8, r13
0x180006792  mov     rcx, [rcx+10h]
0x180006796  call    WPP_SF_
0x18000679b  jmp     loc_1800068E4
0x1800067a0  lea     rbx, ?g_lockGpNotificationThreadMgmt@@3VCAutoCS@@A; CAutoCS g_lockGpNotificationThreadMgmt
0x1800067a7  mov     [rsp+58h+arg_0], rbx
0x1800067ac  mov     rcx, rbx; lpCriticalSection
0x1800067af  call    cs:__imp_EnterCriticalSection
0x1800067b6  nop     dword ptr [rax+rax+00h]
0x1800067bb  nop
0x1800067bc  test    ebp, ebp
0x1800067be  jnz     short loc_1800067EA
0x1800067c0  cmp     cs:?g_bPcrMon@@3_NA, bpl; bool g_bPcrMon
0x1800067c7  jnz     short loc_1800067EA
0x1800067c9  mov     rcx, cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA; hEvent
0x1800067d0  test    rcx, rcx
0x1800067d3  jz      loc_1800068D5
0x1800067d9  call    cs:__imp_SetEvent
0x1800067e0  nop     dword ptr [rax+rax+00h]
0x1800067e5  jmp     loc_1800068D5
0x1800067ea  mov     rcx, cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA; hEvent
0x1800067f1  test    rcx, rcx
0x1800067f4  jnz     loc_1800068C8
0x1800067fa  xor     r9d, r9d; lpName
0x1800067fd  xor     r8d, r8d; bInitialState
0x180006800  lea     edx, [rcx+1]; bManualReset
0x180006803  call    cs:__imp_CreateEventW
0x18000680a  nop     dword ptr [rax+rax+00h]
0x18000680f  mov     cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA, rax; void * g_hGpNotificationThreadStopEvent
0x180006816  test    rax, rax
0x180006819  jnz     short loc_180006857
0x18000681b  call    cs:__imp_GetLastError
0x180006822  nop     dword ptr [rax+rax+00h]
0x180006827  mov     rcx, cs:WPP_GLOBAL_Control
0x18000682e  cmp     rcx, r12
0x180006831  jz      loc_1800068D5
0x180006837  test    byte ptr [rcx+1Ch], 2
0x18000683b  jz      loc_1800068D5
0x180006841  mov     edx, 41h ; 'A'
0x180006846  mov     r9d, eax
0x180006849  mov     r8, r13
0x18000684c  mov     rcx, [rcx+10h]
0x180006850  call    WPP_SF_d
0x180006855  jmp     short loc_1800068D5
0x180006857  lea     rcx, ?BdeSvcGpNotificationThread@@YAIPEAX@Z; unsigned int (*)(void *)
0x18000685e  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z@Z; WorkerThreadLauncher(uint (*)(void *))
0x180006863  test    eax, eax
0x180006865  jz      short loc_1800068A3
0x180006867  mov     rcx, cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA; hObject
0x18000686e  test    rcx, rcx
0x180006871  jz      short loc_18000688A
0x180006873  call    cs:__imp_CloseHandle
0x18000687a  nop     dword ptr [rax+rax+00h]
0x18000687f  mov     cs:?g_hGpNotificationThreadStopEvent@@3PEAXEA, 0; void * g_hGpNotificationThreadStopEvent
0x18000688a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006891  cmp     rcx, r12
0x180006894  jz      short loc_1800068D5
0x180006896  test    byte ptr [rcx+1Ch], 2
0x18000689a  jz      short loc_1800068D5
0x18000689c  mov     edx, 42h ; 'B'
0x1800068a1  jmp     short loc_1800068BA
0x1800068a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068aa  cmp     rcx, r12
0x1800068ad  jz      short loc_1800068D5
0x1800068af  test    byte ptr [rcx+1Ch], 8
0x1800068b3  jz      short loc_1800068D5
0x1800068b5  mov     edx, 43h ; 'C'
0x1800068ba  mov     r8, r13
0x1800068bd  mov     rcx, [rcx+10h]
0x1800068c1  call    WPP_SF_
0x1800068c6  jmp     short loc_1800068D5
0x1800068c8  call    cs:__imp_ResetEvent
0x1800068cf  nop     dword ptr [rax+rax+00h]
0x1800068d4  nop
0x1800068d5  mov     rcx, rbx; lpCriticalSection
0x1800068d8  call    cs:__imp_LeaveCriticalSection
0x1800068df  nop     dword ptr [rax+rax+00h]
0x1800068e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068eb  test    r14d, r14d
0x1800068ee  jz      short loc_1800068FF
0x1800068f0  mov     rcx, rdi; void *
0x1800068f3  call    ?FreeVolumeMap@@YAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; FreeVolumeMap(std::map<std::wstring,VolumeEntry> *)
0x1800068f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068ff  cmp     rcx, r12
0x180006902  jz      short loc_18000691B
0x180006904  test    byte ptr [rcx+1Ch], 20h
0x180006908  jz      short loc_18000691B
0x18000690a  mov     edx, 44h ; 'D'
0x18000690f  mov     r8, r13
0x180006912  mov     rcx, [rcx+10h]
0x180006916  call    WPP_SF_
0x18000691b  mov     eax, ebp
0x18000691d  mov     rbx, [rsp+58h+arg_8]
0x180006922  mov     rbp, [rsp+58h+arg_10]
0x180006927  add     rsp, 30h
0x18000692b  pop     r14
0x18000692d  pop     r13
0x18000692f  pop     r12
0x180006931  pop     rdi
0x180006932  pop     rsi
0x180006933  retn
```
