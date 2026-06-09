# mixerOpen

- ea: `0x18000a960`
- end: `0x18000aee7`
- name: `mixerOpen`
- size: `1415`
- prototype: `MMRESULT __stdcall(LPHMIXER phmx, UINT uMxId, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18000ffc0`

## callees

- `0x1800065d0`
- `0x180007d70`
- `0x18000a960`
- `0x18000aef0`
- `0x18000b2fc`
- `0x18000e0d0`
- `0x18000e828`
- `0x1800106c0`
- `0x18001102a`
- `0x180012d08`
- `0x1800174ec`
- `0x18001a33c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aaa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aba1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aaa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aba1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae6f`

## pseudocode

```c
MMRESULT __stdcall mixerOpen(LPHMIXER phmx, UINT uMxId, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)
{
  MMRESULT ID; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  MMRESULT result; // eax
  unsigned int v12; // r14d
  struct _MMDRV *v13; // rdi
  struct _RTL_CRITICAL_SECTION *v14; // rax
  HDRVR v15; // rbx
  HDRVR v16; // rsi
  MMRESULT v17; // eax
  MMRESULT v18; // esi
  __int64 v19; // rcx
  __int64 v20; // r12
  _BYTE *v21; // r15
  HDRVR v22; // rax
  HMIXEROBJ uDeviceID; // [rsp+40h] [rbp-91h] BYREF
  __int64 v24; // [rsp+48h] [rbp-89h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-81h] BYREF
  __int128 v26; // [rsp+60h] [rbp-71h] BYREF
  __int128 v27; // [rsp+70h] [rbp-61h]
  __int64 v28; // [rsp+80h] [rbp-51h]
  _BYTE v29[72]; // [rsp+90h] [rbp-41h] BYREF
  int v30; // [rsp+D8h] [rbp+7h]
  int v31; // [rsp+DCh] [rbp+Bh]

  LODWORD(uDeviceID) = uMxId;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v24 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qDPPD(*((_QWORD *)WPP_GLOBAL_Control + 2), uMxId, dwCallback, phmx, uMxId, dwCallback, dwInstance, fdwOpen);
  }
  if ( !phmx )
    return 11;
  ClientUpdatePnpInfo();
  *phmx = 0;
  if ( (fdwOpen & 0x70000) == 0x30000 )
    return 10;
  if ( dwCallback && !(unsigned int)ValidateCallbackType(dwCallback, HIWORD(fdwOpen) & 7) )
    return 11;
  if ( (fdwOpen & 0xFF8FFFF) != 0 )
    return 10;
  ID = IMixerGetID((HMIXEROBJ)(unsigned int)uDeviceID, (unsigned int *)&uDeviceID, fdwOpen & 0xF0000000);
  if ( ID )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return ID;
    }
    v10 = 11;
LABEL_15:
    WPP_SF_D(v9[2], v10, &WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids, ID);
    return ID;
  }
  v12 = (unsigned int)uDeviceID;
  EnterCriticalSection(&NumDevsCritSec);
  v13 = mixerdrvZ;
  if ( mixerdrvZ == (struct _MMDRV *)&mixerdrvZ )
    goto LABEL_24;
  do
  {
    if ( (*((_BYTE *)v13 + 112) & 2) == 0 )
    {
      if ( *((_DWORD *)v13 + 22) > v12 )
        break;
      v12 -= *((_DWORD *)v13 + 22);
    }
    v13 = *(struct _MMDRV **)v13;
  }
  while ( v13 != (struct _MMDRV *)&mixerdrvZ );
  if ( v13 == (struct _MMDRV *)&mixerdrvZ )
  {
LABEL_24:
    v13 = 0;
    v12 = 0;
    ID = 2;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)v13 + 23);
    ID = 0;
  }
  LeaveCriticalSection(&NumDevsCritSec);
  if ( ID )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return ID;
    }
    v10 = 12;
    goto LABEL_15;
  }
  v14 = NewHandle(8, *((_QWORD *)v13 + 12), 0x50u);
  v15 = (HDRVR)v14;
  if ( v14 )
  {
    EnterCriticalSection(v14 - 1);
    *((_DWORD *)v15 - 17) |= 2u;
    LeaveCriticalSection(&HandleListCritSec);
    *(_DWORD *)v15 = 8;
    *((_QWORD *)v15 + 2) = v13;
    *((_DWORD *)v15 + 6) = v12;
    *((_DWORD *)v15 + 10) = (_DWORD)uDeviceID;
    *((_DWORD *)v15 + 19) = 0;
    *((_QWORD *)v15 + 7) = dwCallback;
    *((_QWORD *)v15 + 8) = dwInstance;
    *((_DWORD *)v15 + 18) = fdwOpen;
    EnterCriticalSection(&MixerManagerCritSec);
    v16 = gpMixerDevHeader;
    if ( !gpMixerDevHeader )
      goto LABEL_42;
    do
    {
      if ( *((struct _MMDRV **)v16 + 2) == v13 && *((_DWORD *)v16 + 6) == v12 )
        break;
      v16 = (HDRVR)*((_QWORD *)v16 + 1);
    }
    while ( v16 );
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids);
      }
      *((_QWORD *)v15 + 4) = *((_QWORD *)v16 + 4);
      *((_QWORD *)v15 + 1) = *((_QWORD *)v16 + 1);
      *((_QWORD *)v16 + 1) = v15;
      *((_DWORD *)v15 - 17) &= ~2u;
      LeaveCriticalSection(&MixerManagerCritSec);
      LeaveCriticalSection((LPCRITICAL_SECTION)v15 - 1);
      result = 0;
      *phmx = (HMIXER)v15;
    }
    else
    {
LABEL_42:
      v26 = (unsigned __int64)v15;
      *(_QWORD *)&v27 = MixerCallbackFunc;
      *((_QWORD *)&v27 + 1) = (unsigned int)uDeviceID;
      v28 = *(_QWORD *)(*((_QWORD *)v15 + 2) + 104LL);
      EnterCriticalSection((LPCRITICAL_SECTION)v13 + 3);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids);
      }
      v17 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64 *, __int128 *, __int64))v13 + 10))(
              v12,
              3,
              &v24,
              &v26,
              196608);
      v18 = v17;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids, v17);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)v13 + 3);
      if ( v18 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)v15 - 1);
        LeaveCriticalSection(&MixerManagerCritSec);
        FreeHandle((__int64)v15);
      }
      else
      {
        memset_0(v29, 0, 0x50u);
        memset(v25, 0, 12);
        _InterlockedIncrement((volatile signed __int32 *)v13 + 23);
        v19 = *(_QWORD *)(*((_QWORD *)v15 + 2) + 104LL);
        if ( v19 )
        {
          LODWORD(v25[0]) = 80;
          *(_QWORD *)((char *)v25 + 4) = v29;
          v20 = v19;
        }
        else
        {
          v20 = 80;
        }
        v21 = v25;
        if ( !v19 )
          v21 = v29;
        EnterCriticalSection((LPCRITICAL_SECTION)v13 + 3);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids);
        }
        (*((void (__fastcall **)(_QWORD, __int64, __int64, _BYTE *, __int64))v13 + 10))(v12, 2, v24, v21, v20);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids, 0);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)v13 + 3);
        *((_DWORD *)v15 + 11) = v30;
        *((_DWORD *)v15 + 12) = v31;
        *((_QWORD *)v15 + 4) = v24;
        v22 = gpMixerDevHeader;
        *phmx = (HMIXER)v15;
        *((_QWORD *)v15 + 1) = v22;
        *((_DWORD *)v15 - 17) &= ~2u;
        gpMixerDevHeader = v15;
        LeaveCriticalSection((LPCRITICAL_SECTION)v15 - 1);
        LeaveCriticalSection(&MixerManagerCritSec);
      }
      mregDecUsagePtr(v13);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids, v18);
      }
      return v18;
    }
  }
  else
  {
    mregDecUsagePtr(v13);
    return 7;
  }
  return result;
}

```

## disassembly

```asm
0x18000a960  mov     [rsp-8+arg_18], rbx
0x18000a965  push    rbp
0x18000a966  push    rsi
0x18000a967  push    rdi
0x18000a968  push    r12
0x18000a96a  push    r13
0x18000a96c  push    r14
0x18000a96e  push    r15
0x18000a970  lea     rbp, [rsp-1Fh]
0x18000a975  sub     rsp, 0F0h
0x18000a97c  mov     rax, cs:__security_cookie
0x18000a983  xor     rax, rsp
0x18000a986  mov     [rbp+4Fh+var_40], rax
0x18000a98a  xorps   xmm0, xmm0
0x18000a98d  mov     dword ptr [rsp+120h+uDeviceID], edx
0x18000a991  xor     eax, eax
0x18000a993  mov     r12, r9
0x18000a996  movups  [rbp+4Fh+var_C0], xmm0
0x18000a99a  mov     [rbp+4Fh+var_A0], rax
0x18000a99e  mov     r15, r8
0x18000a9a1  movups  [rbp+4Fh+var_B0], xmm0
0x18000a9a5  mov     [rsp+120h+var_D8], rax
0x18000a9aa  mov     r13, rcx
0x18000a9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9b4  lea     r14, WPP_GLOBAL_Control
0x18000a9bb  mov     esi, [rbp+4Fh+fdwOpen]
0x18000a9be  mov     edi, 400000h
0x18000a9c3  cmp     rcx, r14
0x18000a9c6  jz      short loc_18000A9F1
0x18000a9c8  test    [rcx+1Ch], edi
0x18000a9cb  jz      short loc_18000A9F1
0x18000a9cd  cmp     byte ptr [rcx+19h], 2
0x18000a9d1  jb      short loc_18000A9F1
0x18000a9d3  mov     rcx, [rcx+10h]
0x18000a9d7  mov     [rsp+120h+var_E8], esi
0x18000a9db  mov     [rsp+120h+var_F0], r9
0x18000a9e0  mov     r9, r13
0x18000a9e3  mov     [rsp+120h+var_F8], r8
0x18000a9e8  mov     dword ptr [rsp+120h+var_100], edx
0x18000a9ec  call    WPP_SF_qDPPD
0x18000a9f1  test    r13, r13
0x18000a9f4  jz      loc_18000AEBB
0x18000a9fa  call    ClientUpdatePnpInfo
0x18000a9ff  mov     eax, esi
0x18000aa01  mov     qword ptr [r13+0], 0
0x18000aa09  and     eax, 70000h
0x18000aa0e  cmp     eax, 30000h
0x18000aa13  jz      loc_18000AEB4
0x18000aa19  test    r15, r15
0x18000aa1c  jz      short loc_18000AA36
0x18000aa1e  mov     edx, esi
0x18000aa20  mov     rcx, r15
0x18000aa23  shr     edx, 10h
0x18000aa26  and     edx, 7
0x18000aa29  call    ValidateCallbackType
0x18000aa2e  test    eax, eax
0x18000aa30  jz      loc_18000AEBB
0x18000aa36  test    esi, 0FF8FFFFh
0x18000aa3c  jnz     loc_18000AEB4
0x18000aa42  mov     ecx, dword ptr [rsp+120h+uDeviceID]; uDeviceID
0x18000aa46  lea     rdx, [rsp+120h+uDeviceID]; unsigned int *
0x18000aa4b  mov     r8d, esi
0x18000aa4e  and     r8d, 0F0000000h; unsigned int
0x18000aa55  call    ?IMixerGetID@@YAIPEAUHMIXEROBJ__@@PEAIK@Z; IMixerGetID(HMIXEROBJ__ *,uint *,ulong)
0x18000aa5a  mov     ebx, eax
0x18000aa5c  test    eax, eax
0x18000aa5e  jz      short loc_18000AA96
0x18000aa60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa67  cmp     rcx, r14
0x18000aa6a  jz      short loc_18000AA8F
0x18000aa6c  test    [rcx+1Ch], edi
0x18000aa6f  jz      short loc_18000AA8F
0x18000aa71  cmp     byte ptr [rcx+19h], 2
0x18000aa75  jb      short loc_18000AA8F
0x18000aa77  mov     edx, 0Bh
0x18000aa7c  mov     rcx, [rcx+10h]
0x18000aa80  lea     r8, WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids
0x18000aa87  mov     r9d, ebx
0x18000aa8a  call    WPP_SF_D
0x18000aa8f  mov     eax, ebx
0x18000aa91  jmp     loc_18000AEC0
0x18000aa96  mov     r14d, dword ptr [rsp+120h+uDeviceID]
0x18000aa9b  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000aaa2  call    cs:__imp_EnterCriticalSection
0x18000aaa8  mov     rdi, cs:mixerdrvZ
0x18000aaaf  lea     rax, mixerdrvZ
0x18000aab6  cmp     rdi, rax
0x18000aab9  jz      short loc_18000AAE0
0x18000aabb  test    byte ptr [rdi+70h], 2
0x18000aabf  jnz     short loc_18000AACB
0x18000aac1  cmp     [rdi+58h], r14d
0x18000aac5  ja      short loc_18000AAD3
0x18000aac7  sub     r14d, [rdi+58h]
0x18000aacb  mov     rdi, [rdi]
0x18000aace  cmp     rdi, rax
0x18000aad1  jnz     short loc_18000AABB
0x18000aad3  cmp     rdi, rax
0x18000aad6  jz      short loc_18000AAE0
0x18000aad8  lock inc dword ptr [rdi+5Ch]
0x18000aadc  xor     ebx, ebx
0x18000aade  jmp     short loc_18000AAE8
0x18000aae0  xor     edi, edi
0x18000aae2  xor     r14d, r14d
0x18000aae5  lea     ebx, [rdi+2]
0x18000aae8  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000aaef  call    cs:__imp_LeaveCriticalSection
0x18000aaf5  test    ebx, ebx
0x18000aaf7  jz      short loc_18000AB2D
0x18000aaf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab00  lea     rax, WPP_GLOBAL_Control
0x18000ab07  cmp     rcx, rax
0x18000ab0a  jz      short loc_18000AA8F
0x18000ab0c  test    dword ptr [rcx+1Ch], 400000h
0x18000ab13  jz      loc_18000AA8F
0x18000ab19  cmp     byte ptr [rcx+19h], 2
0x18000ab1d  jb      loc_18000AA8F
0x18000ab23  mov     edx, 0Ch
0x18000ab28  jmp     loc_18000AA7C
0x18000ab2d  mov     rdx, [rdi+60h]
0x18000ab31  mov     r8d, 50h ; 'P'
0x18000ab37  lea     ecx, [r8-48h]
0x18000ab3b  call    NewHandle
0x18000ab40  mov     rbx, rax
0x18000ab43  test    rax, rax
0x18000ab46  jnz     short loc_18000AB58
0x18000ab48  mov     rcx, rdi; struct _MMDRV *
0x18000ab4b  call    mregDecUsagePtr
0x18000ab50  lea     eax, [rbx+7]
0x18000ab53  jmp     loc_18000AEC0
0x18000ab58  lea     rcx, [rax-28h]; lpCriticalSection
0x18000ab5c  call    cs:__imp_EnterCriticalSection
0x18000ab62  or      dword ptr [rbx-44h], 2
0x18000ab66  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000ab6d  call    cs:__imp_LeaveCriticalSection
0x18000ab73  mov     dword ptr [rbx], 8
0x18000ab79  lea     rcx, MixerManagerCritSec; lpCriticalSection
0x18000ab80  mov     [rbx+10h], rdi
0x18000ab84  mov     [rbx+18h], r14d
0x18000ab88  mov     eax, dword ptr [rsp+120h+uDeviceID]
0x18000ab8c  mov     [rbx+28h], eax
0x18000ab8f  mov     dword ptr [rbx+4Ch], 0
0x18000ab96  mov     [rbx+38h], r15
0x18000ab9a  mov     [rbx+40h], r12
0x18000ab9e  mov     [rbx+48h], esi
0x18000aba1  call    cs:__imp_EnterCriticalSection
0x18000aba7  mov     rsi, cs:?gpMixerDevHeader@@3PEAUtMIXERDEV@@EA; tMIXERDEV * gpMixerDevHeader
0x18000abae  test    rsi, rsi
0x18000abb1  jz      loc_18000AC42
0x18000abb7  cmp     [rsi+10h], rdi
0x18000abbb  jnz     short loc_18000ABC3
0x18000abbd  cmp     [rsi+18h], r14d
0x18000abc1  jz      short loc_18000ABCC
0x18000abc3  mov     rsi, [rsi+8]
0x18000abc7  test    rsi, rsi
0x18000abca  jnz     short loc_18000ABB7
0x18000abcc  test    rsi, rsi
0x18000abcf  jz      short loc_18000AC42
0x18000abd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abd8  lea     rax, WPP_GLOBAL_Control
0x18000abdf  cmp     rcx, rax
0x18000abe2  jz      short loc_18000AC08
0x18000abe4  test    dword ptr [rcx+1Ch], 400000h
0x18000abeb  jz      short loc_18000AC08
0x18000abed  cmp     byte ptr [rcx+19h], 2
0x18000abf1  jb      short loc_18000AC08
0x18000abf3  mov     rcx, [rcx+10h]
0x18000abf7  lea     r8, WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids
0x18000abfe  mov     edx, 0Dh
0x18000ac03  call    WPP_SF_
0x18000ac08  mov     rax, [rsi+20h]
0x18000ac0c  lea     rcx, MixerManagerCritSec; lpCriticalSection
0x18000ac13  mov     [rbx+20h], rax
0x18000ac17  mov     rax, [rsi+8]
0x18000ac1b  mov     [rbx+8], rax
0x18000ac1f  mov     [rsi+8], rbx
0x18000ac23  and     dword ptr [rbx-44h], 0FFFFFFFDh
0x18000ac27  call    cs:__imp_LeaveCriticalSection
0x18000ac2d  lea     rcx, [rbx-28h]; lpCriticalSection
0x18000ac31  call    cs:__imp_LeaveCriticalSection
0x18000ac37  xor     eax, eax
0x18000ac39  mov     [r13+0], rbx
0x18000ac3d  jmp     loc_18000AEC0
0x18000ac42  mov     qword ptr [rbp+4Fh+var_C0], rbx
0x18000ac46  lea     rax, ?MixerCallbackFunc@@YAHPEAUHMIXER__@@I_K11@Z; MixerCallbackFunc(HMIXER__ *,uint,unsigned __int64,unsigned __int64,unsigned __int64)
0x18000ac4d  mov     qword ptr [rbp+4Fh+var_B0], rax
0x18000ac51  mov     eax, dword ptr [rsp+120h+uDeviceID]
0x18000ac55  mov     qword ptr [rbp+4Fh+var_B0+8], rax
0x18000ac59  mov     qword ptr [rbp+4Fh+var_C0+8], 0
0x18000ac61  mov     rax, [rbx+10h]
0x18000ac65  mov     rcx, [rax+68h]
0x18000ac69  mov     [rbp+4Fh+var_A0], rcx
0x18000ac6d  lea     rcx, [rdi+78h]; lpCriticalSection
0x18000ac71  call    cs:__imp_EnterCriticalSection
0x18000ac77  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac7e  lea     r12, WPP_GLOBAL_Control
0x18000ac85  cmp     rcx, r12
0x18000ac88  jz      short loc_18000ACAE
0x18000ac8a  test    dword ptr [rcx+1Ch], 400000h
0x18000ac91  jz      short loc_18000ACAE
0x18000ac93  cmp     byte ptr [rcx+19h], 2
0x18000ac97  jb      short loc_18000ACAE
0x18000ac99  mov     rcx, [rcx+10h]
0x18000ac9d  lea     r8, WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids
0x18000aca4  mov     edx, 0Eh
0x18000aca9  call    WPP_SF_
0x18000acae  mov     rax, [rdi+50h]
0x18000acb2  lea     r9, [rbp+4Fh+var_C0]
0x18000acb6  lea     r8, [rsp+120h+var_D8]
0x18000acbb  mov     [rsp+120h+var_100], 30000h
0x18000acc4  mov     edx, 3
0x18000acc9  mov     ecx, r14d
0x18000accc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acd1  mov     esi, eax
0x18000acd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acda  cmp     rcx, r12
0x18000acdd  jz      short loc_18000AD06
0x18000acdf  test    dword ptr [rcx+1Ch], 400000h
0x18000ace6  jz      short loc_18000AD06
0x18000ace8  cmp     byte ptr [rcx+19h], 2
0x18000acec  jb      short loc_18000AD06
0x18000acee  mov     rcx, [rcx+10h]
0x18000acf2  lea     r8, WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids
0x18000acf9  mov     edx, 0Fh
0x18000acfe  mov     r9d, eax
0x18000ad01  call    WPP_SF_D
0x18000ad06  lea     rcx, [rdi+78h]; lpCriticalSection
0x18000ad0a  call    cs:__imp_LeaveCriticalSection
0x18000ad10  test    esi, esi
0x18000ad12  jz      short loc_18000AD38
0x18000ad14  lea     rcx, [rbx-28h]; lpCriticalSection
0x18000ad18  call    cs:__imp_LeaveCriticalSection
0x18000ad1e  lea     rcx, MixerManagerCritSec; lpCriticalSection
0x18000ad25  call    cs:__imp_LeaveCriticalSection
0x18000ad2b  mov     rcx, rbx
0x18000ad2e  call    FreeHandle
0x18000ad33  jmp     loc_18000AE75
0x18000ad38  mov     r15d, 50h ; 'P'
0x18000ad3e  lea     rcx, [rbp+4Fh+var_90]; void *
0x18000ad42  mov     r8d, r15d; Size
0x18000ad45  xor     edx, edx; Val
0x18000ad47  call    memset_0
0x18000ad4c  xor     eax, eax
0x18000ad4e  mov     [rsp+120h+var_D0], rax
0x18000ad53  mov     [rbp+4Fh+var_C8], eax
0x18000ad56  lock inc dword ptr [rdi+5Ch]
0x18000ad5a  mov     rax, [rbx+10h]
0x18000ad5e  mov     rcx, [rax+68h]
0x18000ad62  test    rcx, rcx
0x18000ad65  jnz     short loc_18000AD6C
0x18000ad67  mov     r12d, r15d
0x18000ad6a  jmp     short loc_18000AD7C
0x18000ad6c  lea     rax, [rbp+4Fh+var_90]
0x18000ad70  mov     dword ptr [rsp+120h+var_D0], r15d
0x18000ad75  mov     [rbp+4Fh+var_D0+4], rax
0x18000ad79  mov     r12, rcx
0x18000ad7c  test    rcx, rcx
0x18000ad7f  lea     rax, [rbp+4Fh+var_90]
0x18000ad83  lea     r15, [rsp+120h+var_D0]
0x18000ad88  lea     rcx, [rdi+78h]; lpCriticalSection
0x18000ad8c  cmovz   r15, rax
0x18000ad90  call    cs:__imp_EnterCriticalSection
0x18000ad96  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad9d  lea     rax, WPP_GLOBAL_Control
0x18000ada4  cmp     rcx, rax
0x18000ada7  jz      short loc_18000ADCD
0x18000ada9  test    dword ptr [rcx+1Ch], 400000h
0x18000adb0  jz      short loc_18000ADCD
0x18000adb2  cmp     byte ptr [rcx+19h], 2
0x18000adb6  jb      short loc_18000ADCD
0x18000adb8  mov     rcx, [rcx+10h]
0x18000adbc  lea     r8, WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids
0x18000adc3  mov     edx, 10h
0x18000adc8  call    WPP_SF_
0x18000adcd  mov     r8, [rsp+120h+var_D8]
0x18000add2  mov     r9, r15
0x18000add5  mov     rax, [rdi+50h]
0x18000add9  mov     edx, 2
0x18000adde  mov     ecx, r14d
0x18000ade1  mov     [rsp+120h+var_100], r12
0x18000ade6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adf2  lea     r12, WPP_GLOBAL_Control
0x18000adf9  cmp     rcx, r12
0x18000adfc  jz      short loc_18000AE25
0x18000adfe  test    dword ptr [rcx+1Ch], 400000h
0x18000ae05  jz      short loc_18000AE25
0x18000ae07  cmp     byte ptr [rcx+19h], 2
0x18000ae0b  jb      short loc_18000AE25
0x18000ae0d  mov     rcx, [rcx+10h]
0x18000ae11  lea     r8, WPP_75e9eda55c0f348e00eb4dfa7eac45ca_Traceguids
0x18000ae18  mov     edx, 11h
0x18000ae1d  xor     r9d, r9d
0x18000ae20  call    WPP_SF_D
0x18000ae25  lea     rcx, [rdi+78h]; lpCriticalSection
0x18000ae29  call    cs:__imp_LeaveCriticalSection
0x18000ae2f  mov     eax, [rbp+4Fh+var_48]
0x18000ae32  lea     rcx, [rbx-28h]; lpCriticalSection
0x18000ae36  mov     [rbx+2Ch], eax
0x18000ae39  mov     eax, [rbp+4Fh+var_44]
0x18000ae3c  mov     [rbx+30h], eax
  ... truncated ...
```
