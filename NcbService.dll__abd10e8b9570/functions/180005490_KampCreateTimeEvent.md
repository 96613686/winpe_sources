# KampCreateTimeEvent

- ea: `0x180005490`
- end: `0x180005af6`
- name: `KampCreateTimeEvent`
- size: `1638`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006540`

## callees

- `0x180005490`
- `0x18000a0a0`
- `0x18000a160`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`
- `0x18001e368`
- `0x180020444`
- `0x180020494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005aeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005aeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005969`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005969`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800055fc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800056e8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005978`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800059f7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800055fc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800056e8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005978`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800059f7`
- `TimeBrokerClient!TbDeleteEvent` at `0x18000599f`
- `TimeBrokerClient!TbDeleteEvent` at `0x18000599f`
- `TimeBrokerClient!TbCreateEvent` at `0x1800056c6`
- `TimeBrokerClient!TbCreateEvent` at `0x1800056c6`

## string_xrefs

- `0x1800059b3`: `Kam: TbDeleteEvent returned:`
- `0x180005786`: `Kam:KampCreateTimeEvent finished with`
- `0x180005909`: `Kam:KampCreateTimeEvent failed to revert`
- `0x180005a19`: `Kam:KampCreateTimEvent failed to revert with status:`
- `0x180005a58`: `Kam:KampCreateTimEvent failed to impersonate`
- `0x180005aac`: `Kam: Someone already created this.`

## pseudocode

```c
__int64 __fastcall KampCreateTimeEvent(__int64 a1)
{
  PVOID *v2; // rdi
  int v3; // r14d
  unsigned int v4; // esi
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  struct _RTL_CRITICAL_SECTION *v13; // rsi
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rcx
  __int64 v18; // r8
  signed int v20; // eax
  __int64 v21; // r9
  DWORD LastError; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  unsigned int v29; // ebx
  __int64 v30; // rdx
  DWORD v31; // eax
  __int64 v32; // rcx
  DWORD v33; // ebx
  PVOID *v34; // rcx
  __int64 v35; // rdx
  DWORD v36; // eax
  __int64 v37; // rcx
  unsigned int v38; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v39; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v40; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v41; // [rsp+60h] [rbp-A0h]
  __int128 v42; // [rsp+70h] [rbp-90h]
  __int128 v43; // [rsp+80h] [rbp-80h]
  __int128 v44; // [rsp+90h] [rbp-70h]
  __int128 v45; // [rsp+A0h] [rbp-60h]
  __int128 v46; // [rsp+B0h] [rbp-50h]
  __int128 v47; // [rsp+C0h] [rbp-40h]
  __int128 v48; // [rsp+D0h] [rbp-30h]
  __int128 v49; // [rsp+E0h] [rbp-20h]
  __int128 v50; // [rsp+F0h] [rbp-10h]
  __int128 v51; // [rsp+100h] [rbp+0h]
  __int128 v52; // [rsp+110h] [rbp+10h]
  __int128 v53; // [rsp+120h] [rbp+20h]
  __int128 v54; // [rsp+130h] [rbp+30h]
  __int64 v55; // [rsp+140h] [rbp+40h]
  _OWORD v56[15]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v57; // [rsp+240h] [rbp+140h]
  __int128 v58; // [rsp+250h] [rbp+150h] BYREF
  _OWORD v59[10]; // [rsp+260h] [rbp+160h] BYREF
  char v60[16]; // [rsp+300h] [rbp+200h] BYREF
  const wchar_t *v61; // [rsp+310h] [rbp+210h]
  __int64 v62; // [rsp+318h] [rbp+218h]
  unsigned int *v63; // [rsp+320h] [rbp+220h]
  __int64 v64; // [rsp+328h] [rbp+228h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  memset_0(v59, 0, sizeof(v59));
  memset_0(&v40, 0, 0xF8u);
  v3 = *(_DWORD *)(a1 + 364);
  v4 = 60 * *(_DWORD *)(a1 + 372);
  v59[0] = *(_OWORD *)(a1 + 344);
  v5 = *(_OWORD *)(a1 + 84);
  v58 = 0;
  v6 = *(_OWORD *)(a1 + 68);
  v59[2] = v5;
  v7 = *(_OWORD *)(a1 + 116);
  v59[1] = v6;
  v8 = *(_OWORD *)(a1 + 100);
  v59[4] = v7;
  v9 = *(_OWORD *)(a1 + 148);
  v59[3] = v8;
  v10 = *(_OWORD *)(a1 + 132);
  v59[6] = v9;
  v11 = *(_OWORD *)(a1 + 180);
  v59[5] = v10;
  v12 = *(_OWORD *)(a1 + 164);
  v59[8] = v11;
  v59[7] = v12;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    WPP_SF_dc(v2[2], 40, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v4, v3 != 0);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  LODWORD(v40) = 3;
  DWORD2(v40) = v4;
  LODWORD(v41) = 60;
  DWORD1(v41) = v3;
  HIDWORD(v40) = 4 * v4 / 0x64;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_dd(v2[2], 41, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
  DWORD2(v43) = 160;
  v13 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  *(_QWORD *)&v44 = v59;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  if ( SetThreadToken(0, *(HANDLE *)(a1 + 224)) )
  {
    v14 = *(_QWORD *)(a1 + 240);
    v56[0] = v40;
    v57 = v55;
    v56[2] = v42;
    v56[1] = v41;
    v56[4] = v44;
    v56[3] = v43;
    v56[6] = v46;
    v56[5] = v45;
    v56[8] = v48;
    v56[7] = v47;
    v56[10] = v50;
    v56[9] = v49;
    v56[12] = v52;
    v56[11] = v51;
    v56[14] = v54;
    v56[13] = v53;
    v15 = TbCreateEvent(v14, v56, &v58);
    v16 = v15;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v15);
    }
    if ( !SetThreadToken(0, 0) )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v24, v23, L"Kam:KampCreateTimeEvent failed to revert", LastError);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v16);
      }
    }
  }
  else
  {
    v20 = GetLastError();
    v16 = v20;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v20 > 0 )
        v21 = (unsigned __int16)v20 | 0x80070000;
      else
        v21 = (unsigned int)v20;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v21);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  if ( !v16 )
  {
    if ( !*(_BYTE *)(a1 + 361) )
    {
      *(_OWORD *)(a1 + 308) = v58;
      *(_BYTE *)(a1 + 361) = 1;
      goto LABEL_11;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    if ( SetThreadToken(0, *(HANDLE *)(a1 + 224)) )
    {
      v25 = *(_QWORD *)(a1 + 240);
      v39 = v58;
      v26 = TbDeleteEvent(v25, &v39);
      v29 = v26;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v28, v27, L"Kam: TbDeleteEvent returned:", v26);
      if ( v29
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v29);
      }
      if ( SetThreadToken(0, 0) )
        goto LABEL_64;
      v31 = GetLastError();
      v33 = v31;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v32, v30, L"Kam:KampCreateTimEvent failed to revert with status:", v31);
      v34 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v35 = 47;
    }
    else
    {
      v36 = GetLastError();
      v33 = v36;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v37, v30, L"Kam:KampCreateTimEvent failed to impersonate", v36);
      v34 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v35 = 48;
    }
    WPP_SF_d(v34[2], v35, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v33);
LABEL_64:
    v34 = (PVOID *)WPP_GLOBAL_Control;
LABEL_65:
    v16 = 183;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(v34, v30, L"Kam: Someone already created this.", 183);
      v34 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 1) != 0 && *((_BYTE *)v34 + 25) >= 2u )
      WPP_SF_d(v34[2], 49, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, 183);
    EnterCriticalSection(v13);
  }
LABEL_11:
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v38 = v16;
    v61 = L"Kam:KampCreateTimeEvent finished with";
    v62 = 76;
    v63 = &v38;
    v64 = 4;
    McGenEventWrite_EventWriteTransfer(v17, NcbApiStatus, v18, 3, v60);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v16);
  }
  return v16;
}

```

## disassembly

```asm
0x180005490  push    rbp
0x180005492  push    rbx
0x180005493  push    rsi
0x180005494  push    rdi
0x180005495  push    r14
0x180005497  push    r15
0x180005499  lea     rbp, [rsp-248h]
0x1800054a1  sub     rsp, 348h
0x1800054a8  mov     rax, cs:__security_cookie
0x1800054af  xor     rax, rsp
0x1800054b2  mov     [rbp+270h+var_40], rax
0x1800054b9  mov     rbx, rcx
0x1800054bc  mov     rdi, cs:WPP_GLOBAL_Control
0x1800054c3  lea     r15, WPP_GLOBAL_Control
0x1800054ca  cmp     rdi, r15
0x1800054cd  jnz     loc_180005804
0x1800054d3  xor     edx, edx; Val
0x1800054d5  lea     rcx, [rbp+270h+var_110]; void *
0x1800054dc  mov     r8d, 0A0h; Size
0x1800054e2  call    memset_0
0x1800054e7  xor     edx, edx; Val
0x1800054e9  lea     rcx, [rsp+370h+var_320]; void *
0x1800054ee  mov     r8d, 0F8h; Size
0x1800054f4  call    memset_0
0x1800054f9  movups  xmm1, xmmword ptr [rbx+158h]
0x180005500  mov     r14d, [rbx+16Ch]
0x180005507  imul    esi, [rbx+174h], 3Ch ; '<'
0x18000550e  xorps   xmm0, xmm0
0x180005511  movaps  [rbp+270h+var_110], xmm1
0x180005518  movups  xmm1, xmmword ptr [rbx+54h]
0x18000551c  movups  [rbp+270h+var_120], xmm0
0x180005523  movups  xmm0, xmmword ptr [rbx+44h]
0x180005527  movaps  [rbp+270h+var_F0], xmm1
0x18000552e  movups  xmm1, xmmword ptr [rbx+74h]
0x180005532  movaps  [rbp+270h+var_100], xmm0
0x180005539  movups  xmm0, xmmword ptr [rbx+64h]
0x18000553d  movaps  [rbp+270h+var_D0], xmm1
0x180005544  movups  xmm1, xmmword ptr [rbx+94h]
0x18000554b  movaps  [rbp+270h+var_E0], xmm0
0x180005552  movups  xmm0, xmmword ptr [rbx+84h]
0x180005559  movaps  [rbp+270h+var_B0], xmm1
0x180005560  movups  xmm1, xmmword ptr [rbx+0B4h]
0x180005567  movaps  [rbp+270h+var_C0], xmm0
0x18000556e  movups  xmm0, xmmword ptr [rbx+0A4h]
0x180005575  movaps  [rbp+270h+var_90], xmm1
0x18000557c  movaps  [rbp+270h+var_A0], xmm0
0x180005583  cmp     rdi, r15
0x180005586  jz      short loc_180005592
0x180005588  test    byte ptr [rdi+1Ch], 1
0x18000558c  jnz     loc_18000586A
0x180005592  lea     ecx, ds:0[rsi*4]
0x180005599  mov     dword ptr [rsp+370h+var_320], 3
0x1800055a1  mov     eax, 51EB851Fh
0x1800055a6  mov     dword ptr [rsp+370h+var_320+8], esi
0x1800055aa  mul     ecx
0x1800055ac  mov     dword ptr [rsp+370h+var_310], 3Ch ; '<'
0x1800055b4  mov     r9d, edx
0x1800055b7  mov     dword ptr [rsp+370h+var_310+4], r14d
0x1800055bc  shr     r9d, 5
0x1800055c0  mov     dword ptr [rsp+370h+var_320+0Ch], r9d
0x1800055c5  cmp     rdi, r15
0x1800055c8  jz      short loc_1800055D4
0x1800055ca  test    byte ptr [rdi+1Ch], 1
0x1800055ce  jnz     loc_1800058A2
0x1800055d4  lea     rax, [rbp+270h+var_110]
0x1800055db  mov     [rbp+270h+var_2E8], 0A0h
0x1800055e2  lea     rsi, [rbx+18h]
0x1800055e6  mov     qword ptr [rbp+270h+var_2E0], rax
0x1800055ea  mov     rcx, rsi; lpCriticalSection
0x1800055ed  call    cs:__imp_LeaveCriticalSection
0x1800055f3  mov     rdx, [rbx+0E0h]; Token
0x1800055fa  xor     ecx, ecx; Thread
0x1800055fc  call    cs:__imp_SetThreadToken
0x180005602  test    eax, eax
0x180005604  jz      loc_180005741
0x18000560a  movaps  xmm0, [rsp+370h+var_320]
0x18000560f  lea     r8, [rbp+270h+var_120]
0x180005616  movaps  xmm1, [rsp+370h+var_310]
0x18000561b  lea     rdx, [rbp+270h+var_220]
0x18000561f  mov     rax, [rbp+270h+var_230]
0x180005623  mov     rcx, [rbx+0F0h]
0x18000562a  movups  [rbp+270h+var_220], xmm0
0x18000562e  mov     [rbp+270h+var_130], rax
0x180005635  movaps  xmm0, [rsp+370h+var_300]
0x18000563a  movups  [rbp+270h+var_200], xmm0
0x18000563e  movaps  xmm0, [rbp+270h+var_2E0]
0x180005642  movups  [rbp+270h+var_210], xmm1
0x180005646  movaps  xmm1, xmmword ptr [rbp-80h]
0x18000564a  movups  [rbp+270h+var_1E0], xmm0
0x180005651  movaps  xmm0, [rbp+270h+var_2C0]
0x180005655  movups  [rbp+270h+var_1F0], xmm1
0x18000565c  movaps  xmm1, [rbp+270h+var_2D0]
0x180005660  movups  [rbp+270h+var_1C0], xmm0
0x180005667  movaps  xmm0, [rbp+270h+var_2A0]
0x18000566b  movups  [rbp+270h+var_1D0], xmm1
0x180005672  movaps  xmm1, [rbp+270h+var_2B0]
0x180005676  movups  [rbp+270h+var_1A0], xmm0
0x18000567d  movaps  xmm0, [rbp+270h+var_280]
0x180005681  movups  [rbp+270h+var_1B0], xmm1
0x180005688  movaps  xmm1, [rbp+270h+var_290]
0x18000568c  movups  [rbp+270h+var_180], xmm0
0x180005693  movaps  xmm0, [rbp+270h+var_260]
0x180005697  movups  [rbp+270h+var_190], xmm1
0x18000569e  movaps  xmm1, [rbp+270h+var_270]
0x1800056a2  movups  [rbp+270h+var_160], xmm0
0x1800056a9  movaps  xmm0, [rbp+270h+var_240]
0x1800056ad  movups  [rbp+270h+var_170], xmm1
0x1800056b4  movaps  xmm1, [rbp+270h+var_250]
0x1800056b8  movups  [rbp+270h+var_140], xmm0
0x1800056bf  movups  [rbp+270h+var_150], xmm1
0x1800056c6  call    cs:__imp_TbCreateEvent
0x1800056cc  mov     edi, eax
0x1800056ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056d5  cmp     rcx, r15
0x1800056d8  jz      short loc_1800056E4
0x1800056da  test    byte ptr [rcx+1Ch], 1
0x1800056de  jnz     loc_1800058CE
0x1800056e4  xor     edx, edx; Token
0x1800056e6  xor     ecx, ecx; Thread
0x1800056e8  call    cs:__imp_SetThreadToken
0x1800056ee  test    eax, eax
0x1800056f0  jz      loc_1800058F5
0x1800056f6  mov     rcx, rsi; lpCriticalSection
0x1800056f9  call    cs:__imp_EnterCriticalSection
0x1800056ff  test    edi, edi
0x180005701  jz      loc_1800057DD
0x180005707  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000570e  jnz     short loc_180005786
0x180005710  mov     rcx, cs:WPP_GLOBAL_Control
0x180005717  cmp     rcx, r15
0x18000571a  jnz     loc_180005839
0x180005720  mov     eax, edi
0x180005722  mov     rcx, [rbp+270h+var_40]
0x180005729  xor     rcx, rsp; StackCookie
0x18000572c  call    __security_check_cookie
0x180005731  add     rsp, 348h
0x180005738  pop     r15
0x18000573a  pop     r14
0x18000573c  pop     rdi
0x18000573d  pop     rsi
0x18000573e  pop     rbx
0x18000573f  pop     rbp
0x180005740  retn
0x180005741  call    cs:__imp_GetLastError
0x180005747  mov     edi, eax
0x180005749  mov     rcx, cs:WPP_GLOBAL_Control
0x180005750  cmp     rcx, r15
0x180005753  jz      short loc_1800056F6
0x180005755  test    byte ptr [rcx+1Ch], 1
0x180005759  jz      short loc_1800056F6
0x18000575b  cmp     byte ptr [rcx+19h], 2
0x18000575f  jb      short loc_1800056F6
0x180005761  test    eax, eax
0x180005763  jg      loc_180005956
0x180005769  mov     r9d, eax
0x18000576c  mov     rcx, [rcx+10h]
0x180005770  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180005777  mov     edx, 2Dh ; '-'
0x18000577c  call    WPP_SF_d
0x180005781  jmp     loc_1800056F6
0x180005786  lea     rax, aKamKampcreatet; "Kam:KampCreateTimeEvent finished with"
0x18000578d  mov     [rsp+370h+var_340], edi
0x180005791  mov     [rbp+270h+var_60], rax
0x180005798  lea     rdx, NcbApiStatus
0x18000579f  lea     rax, [rsp+370h+var_340]
0x1800057a4  mov     [rbp+270h+var_58], 4Ch ; 'L'
0x1800057af  mov     [rbp+270h+var_50], rax
0x1800057b6  mov     r9d, 3
0x1800057bc  lea     rax, [rbp+270h+var_70]
0x1800057c3  mov     [rbp+270h+var_48], 4
0x1800057ce  mov     [rsp+370h+var_350], rax
0x1800057d3  call    McGenEventWrite_EventWriteTransfer
0x1800057d8  jmp     loc_180005710
0x1800057dd  cmp     byte ptr [rbx+169h], 0
0x1800057e4  jnz     loc_180005966
0x1800057ea  movaps  xmm0, [rbp+270h+var_120]
0x1800057f1  movups  xmmword ptr [rbx+134h], xmm0
0x1800057f8  mov     byte ptr [rbx+169h], 1
0x1800057ff  jmp     loc_180005707
0x180005804  test    byte ptr [rdi+1Ch], 1
0x180005808  jz      loc_1800054D3
0x18000580e  cmp     byte ptr [rdi+19h], 6
0x180005812  jb      loc_1800054D3
0x180005818  mov     rcx, [rdi+10h]
0x18000581c  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180005823  mov     edx, 2Ah ; '*'
0x180005828  call    WPP_SF_
0x18000582d  mov     rdi, cs:WPP_GLOBAL_Control
0x180005834  jmp     loc_1800054D3
0x180005839  test    byte ptr [rcx+1Ch], 1
0x18000583d  jz      loc_180005720
0x180005843  cmp     byte ptr [rcx+19h], 6
0x180005847  jb      loc_180005720
0x18000584d  mov     rcx, [rcx+10h]
0x180005851  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180005858  mov     edx, 32h ; '2'
0x18000585d  mov     r9d, edi
0x180005860  call    WPP_SF_d
0x180005865  jmp     loc_180005720
0x18000586a  cmp     byte ptr [rdi+19h], 6
0x18000586e  jb      loc_180005592
0x180005874  mov     rcx, [rdi+10h]
0x180005878  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x18000587f  test    r14d, r14d
0x180005882  mov     edx, 28h ; '('
0x180005887  mov     r9d, esi
0x18000588a  setnz   al
0x18000588d  mov     byte ptr [rsp+370h+var_350], al
0x180005891  call    WPP_SF_dc
0x180005896  mov     rdi, cs:WPP_GLOBAL_Control
0x18000589d  jmp     loc_180005592
0x1800058a2  cmp     byte ptr [rdi+19h], 6
0x1800058a6  jb      loc_1800055D4
0x1800058ac  mov     rcx, [rdi+10h]
0x1800058b0  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800058b7  mov     edx, 29h ; ')'
0x1800058bc  mov     dword ptr [rsp+370h+var_350], 3Ch ; '<'
0x1800058c4  call    WPP_SF_dd
0x1800058c9  jmp     loc_1800055D4
0x1800058ce  cmp     byte ptr [rcx+19h], 5
0x1800058d2  jb      loc_1800056E4
0x1800058d8  mov     rcx, [rcx+10h]
0x1800058dc  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800058e3  mov     edx, 2Bh ; '+'
0x1800058e8  mov     r9d, eax
0x1800058eb  call    WPP_SF_d
0x1800058f0  jmp     loc_1800056E4
0x1800058f5  call    cs:__imp_GetLastError
0x1800058fb  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180005902  mov     edi, eax
0x180005904  jz      short loc_180005915
0x180005906  mov     r9d, eax
0x180005909  lea     r8, aKamKampcreatet_2; "Kam:KampCreateTimeEvent failed to rever"...
0x180005910  call    McTemplateU0zq_EventWriteTransfer
0x180005915  mov     rcx, cs:WPP_GLOBAL_Control
0x18000591c  cmp     rcx, r15
0x18000591f  jz      loc_1800056F6
0x180005925  test    byte ptr [rcx+1Ch], 1
0x180005929  jz      loc_1800056F6
0x18000592f  cmp     byte ptr [rcx+19h], 2
0x180005933  jb      loc_1800056F6
0x180005939  mov     rcx, [rcx+10h]
0x18000593d  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180005944  mov     edx, 2Ch ; ','
0x180005949  mov     r9d, edi
0x18000594c  call    WPP_SF_d
0x180005951  jmp     loc_1800056F6
0x180005956  movzx   r9d, ax
0x18000595a  or      r9d, 80070000h
0x180005961  jmp     loc_18000576C
0x180005966  mov     rcx, rsi; lpCriticalSection
0x180005969  call    cs:__imp_LeaveCriticalSection
0x18000596f  mov     rdx, [rbx+0E0h]; Token
0x180005976  xor     ecx, ecx; Thread
0x180005978  call    cs:__imp_SetThreadToken
0x18000597e  test    eax, eax
0x180005980  jz      loc_180005A44
0x180005986  movaps  xmm0, [rbp+270h+var_120]
0x18000598d  lea     rdx, [rsp+370h+var_330]
0x180005992  mov     rcx, [rbx+0F0h]
0x180005999  movdqa  [rsp+370h+var_330], xmm0
0x18000599f  call    cs:__imp_TbDeleteEvent
0x1800059a5  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800059ac  mov     ebx, eax
0x1800059ae  jz      short loc_1800059BF
0x1800059b0  mov     r9d, eax
0x1800059b3  lea     r8, aKamTbdeleteeve; "Kam: TbDeleteEvent returned:"
0x1800059ba  call    McTemplateU0zq_EventWriteTransfer
0x1800059bf  test    ebx, ebx
0x1800059c1  jz      short loc_1800059F3
0x1800059c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059ca  cmp     rcx, r15
0x1800059cd  jz      short loc_1800059F3
0x1800059cf  test    byte ptr [rcx+1Ch], 1
0x1800059d3  jz      short loc_1800059F3
0x1800059d5  cmp     byte ptr [rcx+19h], 3
0x1800059d9  jb      short loc_1800059F3
0x1800059db  mov     rcx, [rcx+10h]
0x1800059df  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800059e6  mov     edx, 2Eh ; '.'
0x1800059eb  mov     r9d, ebx
0x1800059ee  call    WPP_SF_d
0x1800059f3  xor     edx, edx; Token
0x1800059f5  xor     ecx, ecx; Thread
0x1800059f7  call    cs:__imp_SetThreadToken
0x1800059fd  test    eax, eax
0x1800059ff  jnz     loc_180005A94
0x180005a05  call    cs:__imp_GetLastError
0x180005a0b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180005a12  mov     ebx, eax
0x180005a14  jz      short loc_180005A25
0x180005a16  mov     r9d, eax
0x180005a19  lea     r8, aKamKampcreatet_1; "Kam:KampCreateTimEvent failed to revert"...
0x180005a20  call    McTemplateU0zq_EventWriteTransfer
0x180005a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a2c  cmp     rcx, r15
0x180005a2f  jz      short loc_180005A9B
0x180005a31  test    byte ptr [rcx+1Ch], 1
0x180005a35  jz      short loc_180005A9B
0x180005a37  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
