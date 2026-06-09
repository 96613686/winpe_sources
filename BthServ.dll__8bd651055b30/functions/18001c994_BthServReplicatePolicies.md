# BthServReplicatePolicies

- ea: `0x18001c994`
- end: `0x18001cfda`
- name: `BthServReplicatePolicies`
- size: `1606`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001c534`

## callees

- `0x18000247c`
- `0x18001c7f0`
- `0x18001c994`
- `0x18001cff4`
- `0x180032c50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cb2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cd08`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ceea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cb2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cd08`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ceea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cc19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cdf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cc19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cdf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ca8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cc72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ce58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ca8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cc72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ce58`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cac1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cbb9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cca8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cd96`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ce8a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cf71`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cac1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cbb9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cca8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cd96`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ce8a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001cf71`

## string_xrefs

- `0x18001cec4`: `ServicesAllowedList`
- `0x18001cf14`: `ServicesAllowedList`
- `0x18001ce6f`: `PM_ServicesAllowedList`
- `0x18001cf5d`: `PM_ServicesAllowedList`

## pseudocode

```c
__int64 __fastcall BthServReplicatePolicies(HKEY hKey)
{
  char v1; // di
  int v3; // r12d
  _WORD *lpData; // rsi
  int v5; // ebx
  unsigned __int16 v6; // bx
  _WORD *v7; // rax
  unsigned __int64 v8; // rbx
  int v9; // edx
  int v10; // r8d
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  void *v15; // rbp
  unsigned int v16; // r14d
  int v17; // ebx
  unsigned int v18; // esi
  void *v19; // rax
  int v20; // edx
  int v21; // r8d
  int v22; // edx
  int v23; // r8d
  int v24; // edx
  int v25; // r8d
  void *v26; // rsi
  unsigned int v27; // ebp
  unsigned int v28; // r14d
  void *v29; // rax
  int v30; // edx
  int v31; // r8d
  int v32; // edx
  LSTATUS v33; // ebx
  int v34; // r8d
  int v35; // edx
  int v36; // r8d
  unsigned __int16 v38; // [rsp+62h] [rbp-56h]

  v1 = 1;
  BthServPushPolicyValue(hKey, 1);
  BthServPushPolicyValue(hKey, 2);
  BthServPushPolicyValue(hKey, 4);
  BthServPushPolicyValue(hKey, 8);
  BthServPushPolicyValue(hKey, 16);
  BthServPushPolicyValue(hKey, 32);
  BthServPushPolicyValue(hKey, 512);
  BthServPushPolicyValue(hKey, 2048);
  v38 = 0;
  EnterCriticalSection(&g_PolicyLock);
  v3 = -1073741275;
  if ( (BYTE4(xmmword_180044A50) & 0x40) != 0 && WORD4(xmmword_180044A20) )
  {
    v6 = WORD5(xmmword_180044A20);
    v7 = o_malloc_0(v6);
    lpData = v7;
    if ( v7 )
    {
      v38 = v6;
      v8 = WORD4(xmmword_180044A20);
      memcpy_0(v7, Block, WORD4(xmmword_180044A20));
      lpData[v8 >> 1] = 0;
      v5 = 0;
    }
    else
    {
      v5 = -1073741670;
    }
  }
  else
  {
    lpData = 0;
    v5 = -1073741275;
  }
  LeaveCriticalSection(&g_PolicyLock);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v9) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v9) = 0;
    }
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    if ( RegSetKeyValueW(hKey, 0, L"PM_LocalDeviceName", 1u, &qword_18003BE90, 2u) < 0 )
    {
      LOBYTE(v13) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          v14,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
  }
  else
  {
    if ( RegSetKeyValueW(hKey, 0, L"PM_LocalDeviceName", 1u, lpData, v38) < 0 )
    {
      LOBYTE(v11) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
    free(lpData);
  }
  v15 = 0;
  v16 = 0;
  EnterCriticalSection(&g_PolicyLock);
  if ( SBYTE4(xmmword_180044A50) < 0 && (v18 = DWORD2(xmmword_180044A50)) != 0 )
  {
    v19 = o_malloc_0(8LL * DWORD2(xmmword_180044A50));
    v15 = v19;
    if ( v19 )
    {
      v16 = v18;
      memcpy_0(v19, *(&Block + 1), 8LL * v18);
      v17 = 0;
    }
    else
    {
      v17 = -1073741670;
    }
  }
  else
  {
    v17 = -1073741275;
  }
  LeaveCriticalSection(&g_PolicyLock);
  if ( v17 < 0 )
  {
    LOBYTE(v20) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( (_BYTE)v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, v21, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    if ( RegSetKeyValueW(hKey, 0, L"PM_DevicesAllowedList", 3u, &qword_18003BE90, 2u) < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v24) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      {
        LOBYTE(v24) = 0;
      }
      if ( (_BYTE)v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v24,
          v25,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
  }
  else
  {
    if ( RegSetKeyValueW(hKey, 0, L"PM_DevicesAllowedList", 3u, v15, 8 * v16) < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v22) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      {
        LOBYTE(v22) = 0;
      }
      if ( (_BYTE)v22 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v22,
          v23,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
    free(v15);
  }
  v26 = 0;
  v27 = 0;
  EnterCriticalSection(&g_PolicyLock);
  if ( (WORD2(xmmword_180044A50) & 0x100) != 0 )
  {
    v28 = HIDWORD(xmmword_180044A50);
    if ( HIDWORD(xmmword_180044A50) )
    {
      v29 = o_malloc_0(16LL * HIDWORD(xmmword_180044A50));
      v26 = v29;
      if ( v29 )
      {
        v27 = v28;
        memcpy_0(v29, Src, 16LL * v28);
        v3 = 0;
      }
      else
      {
        v3 = -1073741670;
      }
    }
  }
  LeaveCriticalSection(&g_PolicyLock);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v30) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v30) = 0;
    }
    if ( (_BYTE)v30 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v33 = RegSetKeyValueW(hKey, 0, L"PM_ServicesAllowedList", 3u, &qword_18003BE90, 2u);
    if ( v33 < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        v1 = 0;
      if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v35) = v1;
        LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v35,
          v36,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
  }
  else
  {
    v33 = RegSetKeyValueW(hKey, 0, L"PM_ServicesAllowedList", 3u, v26, 16 * v27);
    if ( v33 < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        v1 = 0;
      if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v32) = v1;
        LOBYTE(v34) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v32,
          v34,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
    free(v26);
  }
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x18001c994  mov     [rsp+hKey], rcx
0x18001c999  push    rbx
0x18001c99a  push    rbp
0x18001c99b  push    rsi
0x18001c99c  push    rdi
0x18001c99d  push    r12
0x18001c99f  push    r13
0x18001c9a1  push    r14
0x18001c9a3  push    r15
0x18001c9a5  sub     rsp, 78h
0x18001c9a9  mov     edi, 1
0x18001c9ae  mov     r14, rcx
0x18001c9b1  mov     edx, edi
0x18001c9b3  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001c9b8  lea     edx, [rdi+1]
0x18001c9bb  mov     rcx, r14
0x18001c9be  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001c9c3  lea     edx, [rdi+3]
0x18001c9c6  mov     rcx, r14
0x18001c9c9  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001c9ce  lea     edx, [rdi+7]
0x18001c9d1  mov     rcx, r14
0x18001c9d4  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001c9d9  lea     edx, [rdi+0Fh]
0x18001c9dc  mov     rcx, r14
0x18001c9df  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001c9e4  lea     edx, [rdi+1Fh]
0x18001c9e7  mov     rcx, r14
0x18001c9ea  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001c9ef  mov     edx, 200h
0x18001c9f4  mov     rcx, r14
0x18001c9f7  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001c9fc  mov     edx, 800h
0x18001ca01  mov     rcx, r14
0x18001ca04  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001ca09  xorps   xmm0, xmm0
0x18001ca0c  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ca13  movups  xmmword ptr [rsp+0B8h+var_58], xmm0
0x18001ca18  call    cs:__imp_EnterCriticalSection
0x18001ca1e  xor     r13d, r13d
0x18001ca21  mov     r12d, 0C0000225h
0x18001ca27  test    byte ptr cs:xmmword_180044A50+4, 40h
0x18001ca2e  jnz     short loc_18001CA3A
0x18001ca30  mov     rsi, [rsp+0B8h+var_58+8]
0x18001ca35  mov     ebx, r12d
0x18001ca38  jmp     short loc_18001CA88
0x18001ca3a  cmp     word ptr cs:ymmword_180044A20+8, r13w
0x18001ca42  jz      short loc_18001CA30
0x18001ca44  lea     rbp, ymmword_180044A20+8
0x18001ca4b  movzx   ebx, word ptr [rbp+2]
0x18001ca4f  mov     ecx, ebx; Size
0x18001ca51  call    _o_malloc_0
0x18001ca56  mov     rsi, rax
0x18001ca59  test    rax, rax
0x18001ca5c  jz      short loc_18001CA83
0x18001ca5e  mov     rdx, [rbp+8]; Src
0x18001ca62  mov     rcx, rax; void *
0x18001ca65  mov     word ptr [rsp+0B8h+var_58+2], bx
0x18001ca6a  movzx   ebx, word ptr [rbp+0]
0x18001ca6e  mov     r8d, ebx; Size
0x18001ca71  call    memcpy_0
0x18001ca76  shr     rbx, 1
0x18001ca79  mov     [rsi+rbx*2], r13w
0x18001ca7e  mov     ebx, r13d
0x18001ca81  jmp     short loc_18001CA88
0x18001ca83  mov     ebx, 0C000009Ah
0x18001ca88  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ca8f  call    cs:__imp_LeaveCriticalSection
0x18001ca95  lea     rax, qword_18003BE90
0x18001ca9c  test    ebx, ebx
0x18001ca9e  js      loc_18001CB38
0x18001caa4  movzx   eax, word ptr [rsp+0B8h+var_58+2]
0x18001caa9  lea     r8, aPmLocaldevicen; "PM_LocalDeviceName"
0x18001cab0  mov     [rsp+0B8h+cbData], eax; cbData
0x18001cab4  mov     r9d, edi; dwType
0x18001cab7  xor     edx, edx; lpSubKey
0x18001cab9  mov     [rsp+0B8h+lpData], rsi; lpData
0x18001cabe  mov     rcx, r14; hKey
0x18001cac1  call    cs:__imp_RegSetKeyValueW
0x18001cac7  lea     r15, WPP_GLOBAL_Control
0x18001cace  lea     r13, WPP_RECORDER_INITIALIZED
0x18001cad5  test    eax, eax
0x18001cad7  jns     short loc_18001CB2A
0x18001cad9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cae0  cmp     rcx, r15
0x18001cae3  jz      short loc_18001CAF0
0x18001cae5  cmp     byte ptr [rcx+19h], 2
0x18001cae9  jb      short loc_18001CAF0
0x18001caeb  mov     dl, dil
0x18001caee  jmp     short loc_18001CAF2
0x18001caf0  xor     dl, dl
0x18001caf2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001caf9  setnz   r8b
0x18001cafd  test    dl, dl
0x18001caff  jnz     short loc_18001CB06
0x18001cb01  test    r8b, r8b
0x18001cb04  jz      short loc_18001CB2A
0x18001cb06  mov     r9, [rcx+28h]
0x18001cb0a  lea     rbp, aLocaldevicenam; "LocalDeviceName"
0x18001cb11  mov     rcx, [rcx+10h]
0x18001cb15  mov     [rsp+0B8h+var_68], eax
0x18001cb19  mov     [rsp+0B8h+var_70], rbp
0x18001cb1e  mov     [rsp+0B8h+var_88], 0Ch
0x18001cb25  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001cb2a  mov     rcx, rsi; Block
0x18001cb2d  call    cs:__imp_free
0x18001cb33  jmp     loc_18001CC0D
0x18001cb38  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb3f  lea     r15, WPP_GLOBAL_Control
0x18001cb46  cmp     rcx, r15
0x18001cb49  jz      short loc_18001CB54
0x18001cb4b  cmp     byte ptr [rcx+19h], 3
0x18001cb4f  mov     dl, dil
0x18001cb52  jnb     short loc_18001CB57
0x18001cb54  mov     dl, r13b
0x18001cb57  lea     r13, WPP_RECORDER_INITIALIZED
0x18001cb5e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001cb65  lea     rbp, aLocaldevicenam; "LocalDeviceName"
0x18001cb6c  setnz   r8b
0x18001cb70  test    dl, dl
0x18001cb72  jnz     short loc_18001CB79
0x18001cb74  test    r8b, r8b
0x18001cb77  jz      short loc_18001CB9D
0x18001cb79  mov     r9, [rcx+28h]
0x18001cb7d  mov     rcx, [rcx+10h]
0x18001cb81  mov     [rsp+0B8h+var_68], ebx
0x18001cb85  mov     [rsp+0B8h+var_70], rbp
0x18001cb8a  mov     [rsp+0B8h+var_88], 0Dh
0x18001cb91  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001cb96  lea     rax, qword_18003BE90
0x18001cb9d  mov     [rsp+0B8h+cbData], 2; cbData
0x18001cba5  lea     r8, aPmLocaldevicen; "PM_LocalDeviceName"
0x18001cbac  mov     r9d, edi; dwType
0x18001cbaf  mov     [rsp+0B8h+lpData], rax; lpData
0x18001cbb4  xor     edx, edx; lpSubKey
0x18001cbb6  mov     rcx, r14; hKey
0x18001cbb9  call    cs:__imp_RegSetKeyValueW
0x18001cbbf  test    eax, eax
0x18001cbc1  jns     short loc_18001CC0D
0x18001cbc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbca  cmp     rcx, r15
0x18001cbcd  jz      short loc_18001CBDA
0x18001cbcf  cmp     byte ptr [rcx+19h], 2
0x18001cbd3  jb      short loc_18001CBDA
0x18001cbd5  mov     dl, dil
0x18001cbd8  jmp     short loc_18001CBDC
0x18001cbda  xor     dl, dl
0x18001cbdc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001cbe3  setnz   r8b
0x18001cbe7  test    dl, dl
0x18001cbe9  jnz     short loc_18001CBF0
0x18001cbeb  test    r8b, r8b
0x18001cbee  jz      short loc_18001CC0D
0x18001cbf0  mov     r9, [rcx+28h]
0x18001cbf4  mov     rcx, [rcx+10h]
0x18001cbf8  mov     [rsp+0B8h+var_68], eax
0x18001cbfc  mov     [rsp+0B8h+var_70], rbp
0x18001cc01  mov     [rsp+0B8h+var_88], 0Eh
0x18001cc08  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001cc0d  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cc14  xor     ebp, ebp
0x18001cc16  xor     r14d, r14d
0x18001cc19  call    cs:__imp_EnterCriticalSection
0x18001cc1f  test    byte ptr cs:xmmword_180044A50+4, 80h
0x18001cc26  jnz     short loc_18001CC2D
0x18001cc28  mov     ebx, r12d
0x18001cc2b  jmp     short loc_18001CC6B
0x18001cc2d  mov     esi, dword ptr cs:xmmword_180044A50+8
0x18001cc33  test    esi, esi
0x18001cc35  jz      short loc_18001CC28
0x18001cc37  mov     ebx, esi
0x18001cc39  shl     rbx, 3
0x18001cc3d  mov     rcx, rbx; Size
0x18001cc40  call    _o_malloc_0
0x18001cc45  mov     rbp, rax
0x18001cc48  test    rax, rax
0x18001cc4b  jz      short loc_18001CC66
0x18001cc4d  mov     rdx, qword ptr cs:ymmword_180044A20+18h; Src
0x18001cc54  mov     r8, rbx; Size
0x18001cc57  mov     rcx, rax; void *
0x18001cc5a  mov     r14d, esi
0x18001cc5d  call    memcpy_0
0x18001cc62  xor     ebx, ebx
0x18001cc64  jmp     short loc_18001CC6B
0x18001cc66  mov     ebx, 0C000009Ah
0x18001cc6b  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cc72  call    cs:__imp_LeaveCriticalSection
0x18001cc78  test    ebx, ebx
0x18001cc7a  js      loc_18001CD13
0x18001cc80  mov     rcx, [rsp+0B8h+hKey]; hKey
0x18001cc88  lea     eax, ds:0[r14*8]
0x18001cc90  mov     [rsp+0B8h+cbData], eax; cbData
0x18001cc94  lea     r8, aPmDevicesallow; "PM_DevicesAllowedList"
0x18001cc9b  mov     r9d, 3; dwType
0x18001cca1  mov     [rsp+0B8h+lpData], rbp; lpData
0x18001cca6  xor     edx, edx; lpSubKey
0x18001cca8  call    cs:__imp_RegSetKeyValueW
0x18001ccae  xor     r14d, r14d
0x18001ccb1  test    eax, eax
0x18001ccb3  jns     short loc_18001CD05
0x18001ccb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccbc  cmp     rcx, r15
0x18001ccbf  jz      short loc_18001CCCA
0x18001ccc1  cmp     byte ptr [rcx+19h], 2
0x18001ccc5  mov     dl, dil
0x18001ccc8  jnb     short loc_18001CCCD
0x18001ccca  mov     dl, r14b
0x18001cccd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001ccd4  setnz   r8b
0x18001ccd8  test    dl, dl
0x18001ccda  jnz     short loc_18001CCE1
0x18001ccdc  test    r8b, r8b
0x18001ccdf  jz      short loc_18001CD05
0x18001cce1  mov     r9, [rcx+28h]
0x18001cce5  lea     rsi, aDevicesallowed; "DevicesAllowedList"
0x18001ccec  mov     rcx, [rcx+10h]
0x18001ccf0  mov     [rsp+0B8h+var_68], eax
0x18001ccf4  mov     [rsp+0B8h+var_70], rsi
0x18001ccf9  mov     [rsp+0B8h+var_88], 0Fh
0x18001cd00  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001cd05  mov     rcx, rbp; Block
0x18001cd08  call    cs:__imp_free
0x18001cd0e  jmp     loc_18001CDE9
0x18001cd13  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd1a  cmp     rcx, r15
0x18001cd1d  jz      short loc_18001CD2D
0x18001cd1f  cmp     byte ptr [rcx+19h], 3
0x18001cd23  jb      short loc_18001CD2D
0x18001cd25  mov     dl, dil
0x18001cd28  xor     r14d, r14d
0x18001cd2b  jmp     short loc_18001CD33
0x18001cd2d  xor     r14d, r14d
0x18001cd30  mov     dl, r14b
0x18001cd33  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001cd3a  lea     rsi, aDevicesallowed; "DevicesAllowedList"
0x18001cd41  setnz   r8b
0x18001cd45  test    dl, dl
0x18001cd47  jnz     short loc_18001CD4E
0x18001cd49  test    r8b, r8b
0x18001cd4c  jz      short loc_18001CD6B
0x18001cd4e  mov     r9, [rcx+28h]
0x18001cd52  mov     rcx, [rcx+10h]
0x18001cd56  mov     [rsp+0B8h+var_68], ebx
0x18001cd5a  mov     [rsp+0B8h+var_70], rsi
0x18001cd5f  mov     [rsp+0B8h+var_88], 10h
0x18001cd66  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001cd6b  mov     rcx, [rsp+0B8h+hKey]; hKey
0x18001cd73  lea     rax, qword_18003BE90
0x18001cd7a  mov     [rsp+0B8h+cbData], 2; cbData
0x18001cd82  lea     r8, aPmDevicesallow; "PM_DevicesAllowedList"
0x18001cd89  mov     r9d, 3; dwType
0x18001cd8f  mov     [rsp+0B8h+lpData], rax; lpData
0x18001cd94  xor     edx, edx; lpSubKey
0x18001cd96  call    cs:__imp_RegSetKeyValueW
0x18001cd9c  test    eax, eax
0x18001cd9e  jns     short loc_18001CDE9
0x18001cda0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cda7  cmp     rcx, r15
0x18001cdaa  jz      short loc_18001CDB5
0x18001cdac  cmp     byte ptr [rcx+19h], 2
0x18001cdb0  mov     dl, dil
0x18001cdb3  jnb     short loc_18001CDB8
0x18001cdb5  mov     dl, r14b
0x18001cdb8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001cdbf  setnz   r8b
0x18001cdc3  test    dl, dl
0x18001cdc5  jnz     short loc_18001CDCC
0x18001cdc7  test    r8b, r8b
0x18001cdca  jz      short loc_18001CDE9
0x18001cdcc  mov     r9, [rcx+28h]
0x18001cdd0  mov     rcx, [rcx+10h]
0x18001cdd4  mov     [rsp+0B8h+var_68], eax
0x18001cdd8  mov     [rsp+0B8h+var_70], rsi
0x18001cddd  mov     [rsp+0B8h+var_88], 11h
0x18001cde4  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001cde9  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cdf0  mov     rsi, r14
0x18001cdf3  mov     ebp, r14d
0x18001cdf6  call    cs:__imp_EnterCriticalSection
0x18001cdfc  test    dword ptr cs:xmmword_180044A50+4, 100h
0x18001ce06  jz      short loc_18001CE51
0x18001ce08  mov     r14d, dword ptr cs:xmmword_180044A50+0Ch
0x18001ce0f  test    r14d, r14d
0x18001ce12  jz      short loc_18001CE4E
0x18001ce14  mov     ebx, r14d
0x18001ce17  shl     rbx, 4
0x18001ce1b  mov     rcx, rbx; Size
0x18001ce1e  call    _o_malloc_0
0x18001ce23  mov     rsi, rax
0x18001ce26  test    rax, rax
0x18001ce29  jz      short loc_18001CE48
0x18001ce2b  mov     rdx, qword ptr cs:Src; Src
0x18001ce32  mov     r8, rbx; Size
0x18001ce35  mov     rcx, rax; void *
0x18001ce38  mov     ebp, r14d
0x18001ce3b  call    memcpy_0
0x18001ce40  xor     r14d, r14d
0x18001ce43  mov     r12d, r14d
0x18001ce46  jmp     short loc_18001CE51
0x18001ce48  mov     r12d, 0C000009Ah
  ... truncated ...
```
