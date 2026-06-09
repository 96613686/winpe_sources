# PeerdistDynamicSUMInstrumentation::Initialize(ushort const *)

- ea: `0x1800ee7e0`
- end: `0x1800eebfa`
- name: `?Initialize@PeerdistDynamicSUMInstrumentation@@UEAAKPEBG@Z`
- size: `1050`
- prototype: `unsigned int(PeerdistDynamicSUMInstrumentation *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004374`
- `0x180008290`
- `0x180009ec4`
- `0x180015420`
- `0x180015c28`
- `0x180018170`
- `0x180018340`
- `0x180018924`
- `0x180019030`
- `0x1800191b8`
- `0x1800a3a20`
- `0x1800ee7e0`
- `0x180159010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800ee976`
- `msvcrt!wcsrchr` at `0x1800ee976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee8ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee8ed`
- `KERNEL32!GetSystemDirectoryW` at `0x1800ee8e3`
- `KERNEL32!GetSystemDirectoryW` at `0x1800ee8e3`

## string_xrefs

- `0x1800ee85c`: `PeerDist-Common-HostedCache-Enabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PeerdistDynamicSUMInstrumentation::Initialize(
        PeerdistDynamicSUMInstrumentation *this,
        const unsigned __int16 *a2)
{
  PeerdistDynamicSUMInstrumentation *v3; // r14
  unsigned int v4; // ebx
  UINT SystemDirectoryW; // eax
  DWORD LastError; // eax
  wchar_t *v7; // rax
  const unsigned __int16 *v8; // r15
  int v9; // ebx
  char *v10; // rcx
  unsigned int v11; // eax
  const size_t *v12; // r9
  __int64 v14; // rdx
  unsigned int v15; // edi
  __int64 v16; // r8
  PeerdistDynamicSUMInstrumentation *v17; // rbx
  SystemError *v18; // [rsp+40h] [rbp-48h] BYREF
  SystemError *v19; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-38h] BYREF

  v3 = this;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids);
  }
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v20, (RTL_SRWLOCK *)v3 + 1);
  if ( a2 && *a2 )
  {
    if ( !IsLicenseEnabled(L"PeerDist-Common-HostedCache-Enabled") )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids);
      }
      v4 = 4064;
      goto LABEL_64;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids, a2);
    }
    SystemDirectoryW = GetSystemDirectoryW((LPWSTR)v3 + 26, 0x105u);
    if ( SystemDirectoryW )
    {
      if ( SystemDirectoryW >= 0x105 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            16,
            WPP_745553edf2103a31a505d53ab3e6b598_Traceguids,
            SystemDirectoryW);
        }
        goto LABEL_23;
      }
      v7 = wcsrchr(a2, 0x5Cu);
      if ( v7 )
        v8 = v7 + 1;
      else
        v8 = a2;
      v9 = StringCchCatW((unsigned __int16 *)v3 + 26, 0x105u, L"\\");
      if ( v9 < 0 || (v9 = StringCchCatW((unsigned __int16 *)v3 + 26, 0x105u, v8), v9 < 0) )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            17,
            WPP_745553edf2103a31a505d53ab3e6b598_Traceguids,
            (unsigned int)v9);
        }
        v4 = TnoWin32ErrFromHR(v9);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            18,
            WPP_745553edf2103a31a505d53ab3e6b598_Traceguids,
            (char *)v3 + 52);
        }
        try
        {
          DllHandle::Load((PeerdistDynamicSUMInstrumentation *)((char *)v3 + 16), (LPCWSTR)v3 + 26);
          v10 = (char *)v3 + 16;
        }
        catch ( SystemError *v19 )
        {
          v4 = (*(__int64 (__fastcall **)(SystemError *))(*(_QWORD *)v19 + 16LL))(v19);
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              19,
              (unsigned int)WPP_745553edf2103a31a505d53ab3e6b598_Traceguids,
              (_DWORD)this + 52,
              v4);
          }
          if ( !v4 )
            v4 = 774;
          v3 = this;
          goto LABEL_64;
        }
        try
        {
          *((_QWORD *)v3 + 3) = DllHandle::GetProcAddress(v10, "UalStart");
          *((_QWORD *)v3 + 4) = DllHandle::GetProcAddress((char *)v3 + 16, "UalStop");
          *((_QWORD *)v3 + 5) = DllHandle::GetProcAddress((char *)v3 + 16, "UalInstrument");
        }
        catch ( SystemError *v18 )
        {
          v15 = (*(__int64 (__fastcall **)(SystemError *))(*(_QWORD *)v18 + 16LL))(v18);
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v17 = this;
            WPP_SF_Dqqq(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              v14,
              v16,
              v15,
              *((_QWORD *)v17 + 3),
              *((_QWORD *)v17 + 4),
              *((_QWORD *)v17 + 5));
          }
          else
          {
            v17 = this;
          }
          *((_QWORD *)v17 + 3) = 0;
          *((_QWORD *)v17 + 4) = 0;
          *((_QWORD *)v17 + 5) = 0;
          if ( !v15 )
            v15 = 774;
          v3 = this;
          v4 = v15;
          goto LABEL_64;
        }
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids);
        }
        v11 = (*(__int64 (__fastcall **)(PeerdistDynamicSUMInstrumentation *))(*(_QWORD *)v3 + 24LL))(v3);
        v4 = v11;
        if ( v11 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids, v11);
          }
        }
        else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids, LastError);
      }
      if ( !v4 )
LABEL_23:
        v4 = 774;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      LODWORD(v12) = (_DWORD)a2;
      if ( !a2 )
        v12 = &dword_1801747C4;
      WPP_SF_Sq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        12,
        (unsigned int)WPP_745553edf2103a31a505d53ab3e6b598_Traceguids,
        (_DWORD)v12,
        (char)a2);
    }
    v4 = 87;
  }
LABEL_64:
  *((_DWORD *)v3 + 12) = v4;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids, v4);
  }
  LockSentry<ReadersWriterLock,0>::Unlock(v20);
  return v4;
}

```

## disassembly

```asm
0x1800ee7e0  mov     [rsp+arg_10], rbx
0x1800ee7e5  mov     [rsp+arg_18], rsi
0x1800ee7ea  mov     [rsp+arg_0], rcx
0x1800ee7ef  push    rdi
0x1800ee7f0  push    r12
0x1800ee7f2  push    r13
0x1800ee7f4  push    r14
0x1800ee7f6  push    r15
0x1800ee7f8  sub     rsp, 60h
0x1800ee7fc  mov     rbx, rdx
0x1800ee7ff  mov     r14, rcx
0x1800ee802  lea     rsi, WPP_GLOBAL_Control
0x1800ee809  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee810  mov     dil, 8
0x1800ee813  cmp     rcx, rsi
0x1800ee816  jz      short loc_1800EE839
0x1800ee818  test    [rcx+6Ch], dil
0x1800ee81c  jz      short loc_1800EE839
0x1800ee81e  cmp     byte ptr [rcx+69h], 4
0x1800ee822  jb      short loc_1800EE839
0x1800ee824  mov     edx, 0Bh
0x1800ee829  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800ee830  mov     rcx, [rcx+60h]
0x1800ee834  call    WPP_SF_
0x1800ee839  lea     rdx, [r14+8]
0x1800ee83d  lea     rcx, [rsp+88h+var_38]
0x1800ee842  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x1800ee847  nop
0x1800ee848  test    rbx, rbx
0x1800ee84b  jz      loc_1800EEB57
0x1800ee851  xor     eax, eax
0x1800ee853  cmp     ax, [rbx]
0x1800ee856  jz      loc_1800EEB57
0x1800ee85c  lea     rcx, aPeerdistCommon_2; "PeerDist-Common-HostedCache-Enabled"
0x1800ee863  call    ?IsLicenseEnabled@@YA_NPEBG@Z; IsLicenseEnabled(ushort const *)
0x1800ee868  test    al, al
0x1800ee86a  jnz     short loc_1800EE8A3
0x1800ee86c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee873  cmp     rcx, rsi
0x1800ee876  jz      short loc_1800EE899
0x1800ee878  test    [rcx+6Ch], dil
0x1800ee87c  jz      short loc_1800EE899
0x1800ee87e  cmp     byte ptr [rcx+69h], 3
0x1800ee882  jb      short loc_1800EE899
0x1800ee884  mov     edx, 0Dh
0x1800ee889  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800ee890  mov     rcx, [rcx+60h]
0x1800ee894  call    WPP_SF_
0x1800ee899  mov     ebx, 0FE0h
0x1800ee89e  jmp     loc_1800EEB9F
0x1800ee8a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee8aa  cmp     rcx, rsi
0x1800ee8ad  jz      short loc_1800EE8D3
0x1800ee8af  test    [rcx+6Ch], dil
0x1800ee8b3  jz      short loc_1800EE8D3
0x1800ee8b5  cmp     byte ptr [rcx+69h], 3
0x1800ee8b9  jb      short loc_1800EE8D3
0x1800ee8bb  mov     edx, 0Eh
0x1800ee8c0  mov     r9, rbx
0x1800ee8c3  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800ee8ca  mov     rcx, [rcx+60h]
0x1800ee8ce  call    WPP_SF_S
0x1800ee8d3  lea     r12, [r14+34h]
0x1800ee8d7  mov     r13d, 105h
0x1800ee8dd  mov     edx, r13d; uSize
0x1800ee8e0  mov     rcx, r12; lpBuffer
0x1800ee8e3  call    cs:__imp_GetSystemDirectoryW
0x1800ee8e9  test    eax, eax
0x1800ee8eb  jnz     short loc_1800EE937
0x1800ee8ed  call    cs:__imp_GetLastError
0x1800ee8f3  mov     ebx, eax
0x1800ee8f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee8fc  cmp     rcx, rsi
0x1800ee8ff  jz      short loc_1800EE925
0x1800ee901  test    [rcx+6Ch], dil
0x1800ee905  jz      short loc_1800EE925
0x1800ee907  cmp     byte ptr [rcx+69h], 1
0x1800ee90b  jb      short loc_1800EE925
0x1800ee90d  mov     edx, 0Fh
0x1800ee912  mov     r9d, eax
0x1800ee915  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800ee91c  mov     rcx, [rcx+60h]
0x1800ee920  call    WPP_SF_d
0x1800ee925  test    ebx, ebx
0x1800ee927  jnz     loc_1800EEB9F
0x1800ee92d  mov     ebx, 306h
0x1800ee932  jmp     loc_1800EEB9F
0x1800ee937  cmp     eax, r13d
0x1800ee93a  jb      short loc_1800EE96E
0x1800ee93c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee943  cmp     rcx, rsi
0x1800ee946  jz      short loc_1800EE92D
0x1800ee948  test    [rcx+6Ch], dil
0x1800ee94c  jz      short loc_1800EE92D
0x1800ee94e  cmp     byte ptr [rcx+69h], 1
0x1800ee952  jb      short loc_1800EE92D
0x1800ee954  mov     edx, 10h
0x1800ee959  mov     r9d, eax
0x1800ee95c  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800ee963  mov     rcx, [rcx+60h]
0x1800ee967  call    WPP_SF_d
0x1800ee96c  jmp     short loc_1800EE92D
0x1800ee96e  mov     edx, 5Ch ; '\'; Ch
0x1800ee973  mov     rcx, rbx; Str
0x1800ee976  call    cs:__imp_wcsrchr
0x1800ee97c  mov     r15, rax
0x1800ee97f  test    rax, rax
0x1800ee982  jnz     short loc_1800EE989
0x1800ee984  mov     r15, rbx
0x1800ee987  jmp     short loc_1800EE98D
0x1800ee989  add     r15, 2
0x1800ee98d  lea     r8, asc_18016BFBC; "\\"
0x1800ee994  mov     rdx, r13; unsigned __int64
0x1800ee997  mov     rcx, r12; unsigned __int16 *
0x1800ee99a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ee99f  mov     ebx, eax
0x1800ee9a1  test    eax, eax
0x1800ee9a3  js      loc_1800EEB1C
0x1800ee9a9  mov     r8, r15; unsigned __int16 *
0x1800ee9ac  mov     rdx, r13; unsigned __int64
0x1800ee9af  mov     rcx, r12; unsigned __int16 *
0x1800ee9b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ee9b7  mov     ebx, eax
0x1800ee9b9  test    eax, eax
0x1800ee9bb  js      loc_1800EEB1C
0x1800ee9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee9c8  cmp     rcx, rsi
0x1800ee9cb  jz      short loc_1800EE9F2
0x1800ee9cd  test    [rcx+6Ch], dil
0x1800ee9d1  jz      short loc_1800EE9F2
0x1800ee9d3  cmp     byte ptr [rcx+69h], 3
0x1800ee9d7  jb      short loc_1800EE9F2
0x1800ee9d9  mov     edx, 12h
0x1800ee9de  mov     r9, r12
0x1800ee9e1  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800ee9e8  mov     rcx, [rcx+60h]
0x1800ee9ec  call    WPP_SF_S
0x1800ee9f1  nop
0x1800ee9f2  lea     rbx, [r14+10h]
0x1800ee9f6  mov     rdx, r12; lpLibFileName
0x1800ee9f9  mov     rcx, rbx; this
0x1800ee9fc  call    ?Load@DllHandle@@QEAAXPEBG@Z; DllHandle::Load(ushort const *)
0x1800eea01  nop
0x1800eea02  lea     rdx, aUalstart; "UalStart"
0x1800eea09  mov     rcx, rbx
0x1800eea0c  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x1800eea11  mov     [r14+18h], rax
0x1800eea15  lea     rdx, aUalstop; "UalStop"
0x1800eea1c  mov     rcx, rbx
0x1800eea1f  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x1800eea24  mov     [r14+20h], rax
0x1800eea28  lea     rdx, aUalinstrument; "UalInstrument"
0x1800eea2f  mov     rcx, rbx
0x1800eea32  call    ?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z; DllHandle::GetProcAddress(char const *)
0x1800eea37  mov     [r14+28h], rax
0x1800eea3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eea42  cmp     rcx, rsi
0x1800eea45  jz      short loc_1800EEA68
0x1800eea47  test    [rcx+6Ch], dil
0x1800eea4b  jz      short loc_1800EEA68
0x1800eea4d  cmp     byte ptr [rcx+69h], 3
0x1800eea51  jb      short loc_1800EEA68
0x1800eea53  mov     edx, 15h
0x1800eea58  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800eea5f  mov     rcx, [rcx+60h]
0x1800eea63  call    WPP_SF_
0x1800eea68  mov     rax, [r14]
0x1800eea6b  mov     rcx, r14
0x1800eea6e  mov     rax, [rax+18h]
0x1800eea72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eea77  mov     ebx, eax
0x1800eea79  test    eax, eax
0x1800eea7b  jz      short loc_1800EEABE
0x1800eea7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eea84  cmp     rcx, rsi
0x1800eea87  jz      loc_1800EEB9F
0x1800eea8d  test    [rcx+6Ch], dil
0x1800eea91  jz      loc_1800EEB9F
0x1800eea97  cmp     byte ptr [rcx+69h], 1
0x1800eea9b  jb      loc_1800EEB9F
0x1800eeaa1  mov     edx, 16h
0x1800eeaa6  mov     r9d, eax
0x1800eeaa9  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800eeab0  mov     rcx, [rcx+60h]
0x1800eeab4  call    WPP_SF_d
0x1800eeab9  jmp     loc_1800EEB9F
0x1800eeabe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eeac5  cmp     rcx, rsi
0x1800eeac8  jz      loc_1800EEB9F
0x1800eeace  test    [rcx+6Ch], dil
0x1800eead2  jz      loc_1800EEB9F
0x1800eead8  cmp     byte ptr [rcx+69h], 3
0x1800eeadc  jb      loc_1800EEB9F
0x1800eeae2  mov     edx, 17h
0x1800eeae7  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800eeaee  mov     rcx, [rcx+60h]
0x1800eeaf2  call    WPP_SF_
0x1800eeaf7  jmp     loc_1800EEB9F
0x1800eeafc  jmp     short $+2
0x1800eeafe  lea     rsi, WPP_GLOBAL_Control
0x1800eeb05  mov     dil, 8
0x1800eeb08  mov     r14, [rsp+88h+arg_0]
0x1800eeb10  mov     ebx, [rsp+88h+arg_8]
0x1800eeb17  jmp     loc_1800EEB9F
0x1800eeb1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eeb23  cmp     rcx, rsi
0x1800eeb26  jz      short loc_1800EEB4C
0x1800eeb28  test    [rcx+6Ch], dil
0x1800eeb2c  jz      short loc_1800EEB4C
0x1800eeb2e  cmp     byte ptr [rcx+69h], 1
0x1800eeb32  jb      short loc_1800EEB4C
0x1800eeb34  mov     edx, 11h
0x1800eeb39  mov     r9d, ebx
0x1800eeb3c  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800eeb43  mov     rcx, [rcx+60h]
0x1800eeb47  call    WPP_SF_d
0x1800eeb4c  mov     ecx, ebx; int
0x1800eeb4e  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x1800eeb53  mov     ebx, eax
0x1800eeb55  jmp     short loc_1800EEB9F
0x1800eeb57  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eeb5e  cmp     rcx, rsi
0x1800eeb61  jz      short loc_1800EEB9A
0x1800eeb63  test    [rcx+6Ch], dil
0x1800eeb67  jz      short loc_1800EEB9A
0x1800eeb69  cmp     byte ptr [rcx+69h], 1
0x1800eeb6d  jb      short loc_1800EEB9A
0x1800eeb6f  lea     rax, dword_1801747C4
0x1800eeb76  mov     r9, rbx
0x1800eeb79  test    rbx, rbx
0x1800eeb7c  cmovz   r9, rax
0x1800eeb80  mov     edx, 0Ch
0x1800eeb85  mov     [rsp+88h+var_68], rbx
0x1800eeb8a  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800eeb91  mov     rcx, [rcx+60h]
0x1800eeb95  call    WPP_SF_Sq
0x1800eeb9a  mov     ebx, 57h ; 'W'
0x1800eeb9f  mov     [r14+30h], ebx
0x1800eeba3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eebaa  cmp     rcx, rsi
0x1800eebad  jz      short loc_1800EEBD4
0x1800eebaf  test    [rcx+6Ch], dil
0x1800eebb3  jz      short loc_1800EEBD4
0x1800eebb5  cmp     byte ptr [rcx+69h], 4
0x1800eebb9  jb      short loc_1800EEBD4
0x1800eebbb  mov     edx, 18h
0x1800eebc0  mov     r9d, ebx
0x1800eebc3  lea     r8, WPP_745553edf2103a31a505d53ab3e6b598_Traceguids
0x1800eebca  mov     rcx, [rcx+60h]
0x1800eebce  call    WPP_SF_d
0x1800eebd3  nop
0x1800eebd4  lea     rcx, [rsp+88h+var_38]
0x1800eebd9  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x1800eebde  mov     eax, ebx
0x1800eebe0  lea     r11, [rsp+88h+var_28]
0x1800eebe5  mov     rbx, [r11+40h]
0x1800eebe9  mov     rsi, [r11+48h]
0x1800eebed  mov     rsp, r11
0x1800eebf0  pop     r15
0x1800eebf2  pop     r14
0x1800eebf4  pop     r13
0x1800eebf6  pop     r12
0x1800eebf8  pop     rdi
0x1800eebf9  retn
```
