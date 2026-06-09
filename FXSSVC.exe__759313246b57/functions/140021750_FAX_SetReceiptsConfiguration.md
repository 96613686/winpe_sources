# FAX_SetReceiptsConfiguration

- ea: `0x140021750`
- end: `0x140021c72`
- name: `FAX_SetReceiptsConfiguration`
- size: `1314`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14000cc48`
- `0x1400154a0`
- `0x140021750`
- `0x14002e3d4`
- `0x140047d20`
- `0x1400589ac`
- `0x14006998c`
- `0x140074f18`
- `0x1400750e8`
- `0x14007a1b8`
- `0x14008249c`
- `0x140084984`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140021bbf`
- `ADVAPI32!RegCloseKey` at `0x140021bbf`
- `KERNEL32!GetLastError` at `0x140021998`
- `KERNEL32!GetLastError` at `0x140021a59`
- `KERNEL32!GetLastError` at `0x140021b3c`
- `KERNEL32!GetLastError` at `0x140021998`
- `KERNEL32!GetLastError` at `0x140021a59`
- `KERNEL32!GetLastError` at `0x140021b3c`
- `KERNEL32!CloseHandle` at `0x140021b0d`
- `KERNEL32!CloseHandle` at `0x140021b0d`
- `KERNEL32!EnterCriticalSection` at `0x140021953`
- `KERNEL32!EnterCriticalSection` at `0x140021953`
- `KERNEL32!LeaveCriticalSection` at `0x140021c43`
- `KERNEL32!LeaveCriticalSection` at `0x140021c43`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FAX_SetReceiptsConfiguration(void *a1, int *a2)
{
  CMapDeviceId *v4; // rcx
  int v5; // ebx
  int Win32StructSize; // eax
  DWORD v7; // ebx
  int v8; // ebp
  unsigned int ClientAPIVersion; // eax
  int v10; // ecx
  int *v11; // rsi
  unsigned int v12; // ebx
  DWORD v13; // eax
  int v15; // ebp
  int v16; // r14d
  HKEY v17; // rax
  HKEY v18; // r15
  DWORD v19; // eax
  CMapDeviceId *v20; // rcx
  __int64 v21; // rdx
  PCWSTR v22; // rax
  __int64 v23; // rdx
  unsigned __int16 *v24; // rcx
  __int64 v25; // r10
  __int64 v26; // rdx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // r10
  int v30; // edx
  int v31; // eax
  DWORD LastError; // eax
  int ConfigEvent; // eax
  _BYTE *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // [rsp+88h] [rbp+10h] BYREF

  v37 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 275, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *a2;
  if ( *a2 != 72 )
  {
    Win32StructSize = GetWin32StructSize(&fax_receipts_config_fields);
    v4 = WPP_GLOBAL_Control;
    if ( Win32StructSize != v5 )
      goto LABEL_23;
  }
  if ( (a2[1] & 0xFFFFFFFA) != 0 )
    goto LABEL_23;
  if ( (a2[1] & 4) != 0 )
  {
    v7 = 1630;
LABEL_24:
    if ( v4 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v4 + 2), 276, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v7);
    return v7;
  }
  v8 = 0;
  ClientAPIVersion = FindClientAPIVersion(a1);
  v10 = a2[1];
  v11 = a2 + 16;
  v12 = ClientAPIVersion;
  if ( (v10 & 1) == 0 && !*v11 )
  {
LABEL_16:
    if ( (v10 & 1) != 0 )
      goto LABEL_19;
    goto LABEL_17;
  }
  if ( !(unsigned int)AreReceiptsEnabled() )
  {
    v4 = WPP_GLOBAL_Control;
    v7 = v12 < 0x10000 ? 87 : 7011;
    goto LABEL_24;
  }
  v10 = a2[1];
  if ( (v10 & 1) != 0 )
  {
    v8 = 1;
    goto LABEL_16;
  }
LABEL_17:
  if ( !*v11 && *((_QWORD *)a2 + 7) )
  {
LABEL_22:
    v4 = WPP_GLOBAL_Control;
LABEL_23:
    v7 = 87;
    goto LABEL_24;
  }
LABEL_19:
  if ( (v8 || *v11) && (unsigned int)a2[2] > 2 )
    goto LABEL_22;
  v13 = FaxSvcAccessCheck(0x40u, &v37, 0, 1);
  v7 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 277, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v13);
    }
LABEL_97:
    if ( v7 == 8 || v7 == 14 )
      return 7001;
    return v7;
  }
  if ( v37 )
  {
    v15 = a2[1] & 1;
    EnterCriticalSection(&g_CsConfig);
    if ( a2[2] != 2 || (v16 = 0, !v15) && !*v11 )
      v16 = 1;
    v17 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax\\Receipts", 0, 131103);
    v18 = v17;
    if ( v17 )
    {
      lpMem = (LPVOID)GetRegistrySecureString(v17, 0);
      v7 = StoreReceiptsSettings(a2);
      if ( v7 )
      {
        v7 = 1015;
      }
      else
      {
        dword_1400A7644 = a2[1];
        dword_1400A7680 = *v11;
        if ( !v15 && !*v11 )
          goto LABEL_71;
        *(_DWORD *)&dword_1400A7660 = a2[8];
        dword_1400A7648 = a2[2];
        if ( !ReplaceStringWithCopy(&qword_1400A7658, *((const unsigned __int16 **)a2 + 3))
          || !ReplaceStringWithCopy(&qword_1400A7668, *((const unsigned __int16 **)a2 + 5)) )
        {
          goto LABEL_54;
        }
        v22 = UserName;
        if ( !UserName )
          goto LABEL_68;
        v23 = *((_QWORD *)a2 + 6);
        if ( !v23 )
          goto LABEL_68;
        v24 = (unsigned __int16 *)lpMem;
        if ( !lpMem )
          goto LABEL_68;
        v25 = *((_QWORD *)a2 + 7);
        if ( !v25 )
          goto LABEL_68;
        v26 = v23 - (_QWORD)UserName;
        do
        {
          v27 = *(PCWSTR)((char *)v22 + v26);
          v28 = *v22 - v27;
          if ( v28 )
            break;
          ++v22;
        }
        while ( v27 );
        if ( v28 )
          goto LABEL_68;
        v29 = v25 - (_QWORD)lpMem;
        do
        {
          v30 = *(unsigned __int16 *)((char *)v24 + v29);
          v31 = *v24 - v30;
          if ( v31 )
            break;
          ++v24;
        }
        while ( v30 );
        if ( v31 )
LABEL_68:
          v16 = 1;
        if ( ReplaceStringWithCopy((unsigned __int16 **)&UserName, *((const unsigned __int16 **)a2 + 6)) )
        {
LABEL_71:
          if ( hObject && v16 == 1 )
          {
            if ( !CloseHandle(hObject)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                280,
                &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                LastError);
            }
            hObject = 0;
          }
          ConfigEvent = CreateConfigEvent(0);
          if ( ConfigEvent
            && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_h(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              281,
              &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
              (unsigned __int16)ConfigEvent);
          }
        }
        else
        {
LABEL_54:
          v7 = GetLastError();
        }
      }
      v19 = RegCloseKey(v18);
      if ( !v19 )
        goto LABEL_89;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v21 = 282;
    }
    else
    {
      v19 = GetLastError();
      v7 = v19;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v21 = 279;
    }
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v19);
LABEL_89:
    v34 = lpMem;
    if ( lpMem )
    {
      v35 = -1;
      do
        ++v35;
      while ( *((_WORD *)lpMem + v35) );
      v36 = 2 * v35;
      if ( v36 )
      {
        do
        {
          *v34++ = 0;
          --v36;
        }
        while ( v36 );
        v34 = lpMem;
      }
      pMemFree(v34);
      lpMem = 0;
    }
    LeaveCriticalSection(&g_CsConfig);
    goto LABEL_97;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  return 5;
}

```

## disassembly

```asm
0x140021750  mov     rax, rsp
0x140021753  push    rbx
0x140021754  push    rbp
0x140021755  push    rsi
0x140021756  push    rdi
0x140021757  push    r12
0x140021759  push    r13
0x14002175b  push    r14
0x14002175d  push    r15
0x14002175f  sub     rsp, 38h
0x140021763  xor     r12d, r12d
0x140021766  mov     rdi, rdx
0x140021769  mov     [rax+10h], r12d
0x14002176d  mov     rsi, rcx
0x140021770  mov     rcx, cs:WPP_GLOBAL_Control
0x140021777  lea     r15, WPP_GLOBAL_Control
0x14002177e  mov     r14b, 4
0x140021781  cmp     rcx, r15
0x140021784  jz      short loc_1400217AE
0x140021786  test    [rcx+1Ch], r14b
0x14002178a  jz      short loc_1400217AE
0x14002178c  cmp     byte ptr [rcx+19h], 5
0x140021790  jb      short loc_1400217AE
0x140021792  mov     rcx, [rcx+10h]
0x140021796  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002179d  mov     edx, 113h
0x1400217a2  call    WPP_SF_
0x1400217a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400217ae  mov     ebx, [rdi]
0x1400217b0  cmp     ebx, 48h ; 'H'
0x1400217b3  jz      short loc_1400217D0
0x1400217b5  lea     rcx, ?fax_receipts_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_receipts_config_fields
0x1400217bc  call    GetWin32StructSize
0x1400217c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400217c8  cmp     eax, ebx
0x1400217ca  jnz     loc_140021868
0x1400217d0  test    dword ptr [rdi+4], 0FFFFFFFAh
0x1400217d7  jnz     loc_140021868
0x1400217dd  test    [rdi+4], r14b
0x1400217e1  jz      short loc_1400217ED
0x1400217e3  mov     ebx, 65Eh
0x1400217e8  jmp     loc_14002186D
0x1400217ed  mov     rcx, rsi; void *
0x1400217f0  mov     ebp, r12d
0x1400217f3  call    ?FindClientAPIVersion@@YAKPEAX@Z; FindClientAPIVersion(void *)
0x1400217f8  mov     ecx, [rdi+4]
0x1400217fb  lea     rsi, [rdi+40h]
0x1400217ff  mov     r13d, 1
0x140021805  mov     ebx, eax
0x140021807  test    r13b, cl
0x14002180a  jnz     short loc_140021811
0x14002180c  cmp     [rsi], r12d
0x14002180f  jz      short loc_140021842
0x140021811  call    AreReceiptsEnabled
0x140021816  test    eax, eax
0x140021818  jnz     short loc_140021837
0x14002181a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021821  cmp     ebx, 10000h
0x140021827  sbb     ebx, ebx
0x140021829  and     ebx, 0FFFFE4F4h
0x14002182f  add     ebx, 1B63h
0x140021835  jmp     short loc_14002186D
0x140021837  mov     ecx, [rdi+4]
0x14002183a  test    r13b, cl
0x14002183d  jz      short loc_140021847
0x14002183f  mov     ebp, r13d
0x140021842  test    r13b, cl
0x140021845  jnz     short loc_140021852
0x140021847  cmp     [rsi], r12d
0x14002184a  jnz     short loc_140021852
0x14002184c  cmp     [rdi+38h], r12
0x140021850  jnz     short loc_140021861
0x140021852  test    ebp, ebp
0x140021854  jnz     short loc_14002185B
0x140021856  cmp     [rsi], r12d
0x140021859  jz      short loc_1400218A7
0x14002185b  cmp     dword ptr [rdi+8], 2
0x14002185f  jbe     short loc_1400218A7
0x140021861  mov     rcx, cs:WPP_GLOBAL_Control
0x140021868  mov     ebx, 57h ; 'W'
0x14002186d  cmp     rcx, r15
0x140021870  jz      loc_140021C5E
0x140021876  test    [rcx+1Ch], r14b
0x14002187a  jz      loc_140021C5E
0x140021880  cmp     byte ptr [rcx+19h], 2
0x140021884  jb      loc_140021C5E
0x14002188a  mov     rcx, [rcx+10h]
0x14002188e  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021895  mov     edx, 114h
0x14002189a  mov     r9d, ebx
0x14002189d  call    WPP_SF_d
0x1400218a2  jmp     loc_140021C5E
0x1400218a7  xor     r8d, r8d; unsigned int *
0x1400218aa  lea     rdx, [rsp+78h+arg_8]; int *
0x1400218b2  mov     r9d, r13d; int
0x1400218b5  lea     ecx, [r8+40h]; unsigned int
0x1400218b9  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x1400218be  mov     ebx, eax
0x1400218c0  test    eax, eax
0x1400218c2  jz      short loc_140021905
0x1400218c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400218cb  cmp     rcx, r15
0x1400218ce  jz      loc_140021C4F
0x1400218d4  test    [rcx+1Ch], r14b
0x1400218d8  jz      loc_140021C4F
0x1400218de  cmp     byte ptr [rcx+19h], 2
0x1400218e2  jb      loc_140021C4F
0x1400218e8  mov     rcx, [rcx+10h]
0x1400218ec  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400218f3  mov     edx, 115h
0x1400218f8  mov     r9d, eax
0x1400218fb  call    WPP_SF_d
0x140021900  jmp     loc_140021C4F
0x140021905  cmp     [rsp+78h+arg_8], r12d
0x14002190d  jnz     short loc_140021946
0x14002190f  mov     rcx, cs:WPP_GLOBAL_Control
0x140021916  cmp     rcx, r15
0x140021919  jz      short loc_14002193C
0x14002191b  test    [rcx+1Ch], r14b
0x14002191f  jz      short loc_14002193C
0x140021921  cmp     byte ptr [rcx+19h], 2
0x140021925  jb      short loc_14002193C
0x140021927  mov     rcx, [rcx+10h]
0x14002192b  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021932  mov     edx, 116h
0x140021937  call    WPP_SF_
0x14002193c  mov     eax, 5
0x140021941  jmp     loc_140021C60
0x140021946  mov     ebp, [rdi+4]
0x140021949  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140021950  and     ebp, r13d
0x140021953  call    cs:__imp_EnterCriticalSection
0x14002195a  nop     dword ptr [rax+rax+00h]
0x14002195f  cmp     dword ptr [rdi+8], 2
0x140021963  jnz     short loc_140021971
0x140021965  mov     r14d, r12d
0x140021968  test    ebp, ebp
0x14002196a  jnz     short loc_140021974
0x14002196c  cmp     [rsi], r12d
0x14002196f  jnz     short loc_140021974
0x140021971  mov     r14d, r13d
0x140021974  mov     r9d, 2001Fh
0x14002197a  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fax\\Receipts"
0x140021981  xor     r8d, r8d
0x140021984  mov     rcx, 0FFFFFFFF80000002h
0x14002198b  call    OpenRegistryKey
0x140021990  mov     r15, rax
0x140021993  test    rax, rax
0x140021996  jnz     short loc_1400219DB
0x140021998  call    cs:__imp_GetLastError
0x14002199f  nop     dword ptr [rax+rax+00h]
0x1400219a4  mov     ebx, eax
0x1400219a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400219ad  lea     rdi, WPP_GLOBAL_Control
0x1400219b4  cmp     rcx, rdi
0x1400219b7  jz      loc_140021BFF
0x1400219bd  test    byte ptr [rcx+1Ch], 4
0x1400219c1  jz      loc_140021BFF
0x1400219c7  cmp     byte ptr [rcx+19h], 2
0x1400219cb  jb      loc_140021BFF
0x1400219d1  mov     edx, 117h
0x1400219d6  jmp     loc_140021BEC
0x1400219db  lea     r8, Class
0x1400219e2  mov     [rsp+78h+var_58], r12; __int64
0x1400219e7  mov     rcx, r15; hKey
0x1400219ea  call    GetRegistrySecureString
0x1400219ef  mov     rcx, rdi
0x1400219f2  mov     cs:lpMem, rax
0x1400219f9  call    StoreReceiptsSettings
0x1400219fe  mov     ebx, eax
0x140021a00  test    eax, eax
0x140021a02  jz      short loc_140021A15
0x140021a04  mov     ebx, 3F7h
0x140021a09  lea     rdi, WPP_GLOBAL_Control
0x140021a10  jmp     loc_140021BBC
0x140021a15  mov     eax, [rdi+4]
0x140021a18  mov     cs:dword_1400A7644, eax
0x140021a1e  mov     eax, [rsi]
0x140021a20  mov     cs:dword_1400A7680, eax
0x140021a26  test    ebp, ebp
0x140021a28  jnz     short loc_140021A33
0x140021a2a  cmp     [rsi], r12d
0x140021a2d  jz      loc_140021AFC
0x140021a33  mov     eax, [rdi+20h]
0x140021a36  lea     rcx, qword_1400A7658; unsigned __int16 **
0x140021a3d  mov     cs:dword_1400A7660, eax
0x140021a43  mov     eax, [rdi+8]
0x140021a46  mov     cs:dword_1400A7648, eax
0x140021a4c  mov     rdx, [rdi+18h]; unsigned __int16 *
0x140021a50  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x140021a55  test    eax, eax
0x140021a57  jnz     short loc_140021A69
0x140021a59  call    cs:__imp_GetLastError
0x140021a60  nop     dword ptr [rax+rax+00h]
0x140021a65  mov     ebx, eax
0x140021a67  jmp     short loc_140021A09
0x140021a69  mov     rdx, [rdi+28h]; unsigned __int16 *
0x140021a6d  lea     rcx, qword_1400A7668; unsigned __int16 **
0x140021a74  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x140021a79  test    eax, eax
0x140021a7b  jz      short loc_140021A59
0x140021a7d  mov     rax, cs:UserName
0x140021a84  test    rax, rax
0x140021a87  jz      short loc_140021AE1
0x140021a89  mov     rdx, [rdi+30h]
0x140021a8d  test    rdx, rdx
0x140021a90  jz      short loc_140021AE1
0x140021a92  mov     rcx, cs:lpMem
0x140021a99  test    rcx, rcx
0x140021a9c  jz      short loc_140021AE1
0x140021a9e  mov     r10, [rdi+38h]
0x140021aa2  test    r10, r10
0x140021aa5  jz      short loc_140021AE1
0x140021aa7  sub     rdx, rax
0x140021aaa  movzx   r9d, word ptr [rax]
0x140021aae  movzx   r8d, word ptr [rax+rdx]
0x140021ab3  sub     r9d, r8d
0x140021ab6  jnz     short loc_140021AC1
0x140021ab8  add     rax, 2
0x140021abc  test    r8d, r8d
0x140021abf  jnz     short loc_140021AAA
0x140021ac1  test    r9d, r9d
0x140021ac4  jnz     short loc_140021AE1
0x140021ac6  sub     r10, rcx
0x140021ac9  movzx   eax, word ptr [rcx]
0x140021acc  movzx   edx, word ptr [rcx+r10]
0x140021ad1  sub     eax, edx
0x140021ad3  jnz     short loc_140021ADD
0x140021ad5  add     rcx, 2
0x140021ad9  test    edx, edx
0x140021adb  jnz     short loc_140021AC9
0x140021add  test    eax, eax
0x140021adf  jz      short loc_140021AE4
0x140021ae1  mov     r14d, r13d
0x140021ae4  mov     rdx, [rdi+30h]; unsigned __int16 *
0x140021ae8  lea     rcx, UserName; unsigned __int16 **
0x140021aef  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x140021af4  test    eax, eax
0x140021af6  jz      loc_140021A59
0x140021afc  mov     rcx, cs:hObject; hObject
0x140021b03  test    rcx, rcx
0x140021b06  jz      short loc_140021B79
0x140021b08  cmp     r14d, r13d
0x140021b0b  jnz     short loc_140021B79
0x140021b0d  call    cs:__imp_CloseHandle
0x140021b14  nop     dword ptr [rax+rax+00h]
0x140021b19  test    eax, eax
0x140021b1b  jnz     short loc_140021B69
0x140021b1d  mov     rax, cs:WPP_GLOBAL_Control
0x140021b24  lea     rdi, WPP_GLOBAL_Control
0x140021b2b  cmp     rax, rdi
0x140021b2e  jz      short loc_140021B70
0x140021b30  test    byte ptr [rax+1Ch], 4
0x140021b34  jz      short loc_140021B70
0x140021b36  cmp     byte ptr [rax+19h], 2
0x140021b3a  jb      short loc_140021B70
0x140021b3c  call    cs:__imp_GetLastError
0x140021b43  nop     dword ptr [rax+rax+00h]
0x140021b48  mov     rcx, cs:WPP_GLOBAL_Control
0x140021b4f  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021b56  mov     edx, 118h
0x140021b5b  mov     r9d, eax
0x140021b5e  mov     rcx, [rcx+10h]
0x140021b62  call    WPP_SF_d
0x140021b67  jmp     short loc_140021B70
0x140021b69  lea     rdi, WPP_GLOBAL_Control
0x140021b70  mov     cs:hObject, r12
0x140021b77  jmp     short loc_140021B80
0x140021b79  lea     rdi, WPP_GLOBAL_Control
0x140021b80  xor     ecx, ecx
0x140021b82  call    ?CreateConfigEvent@@YAKW4FAX_ENUM_CONFIG_TYPE@@@Z; CreateConfigEvent(FAX_ENUM_CONFIG_TYPE)
0x140021b87  test    eax, eax
0x140021b89  jz      short loc_140021BBC
0x140021b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140021b92  cmp     rcx, rdi
0x140021b95  jz      short loc_140021BBC
0x140021b97  test    byte ptr [rcx+1Ch], 4
0x140021b9b  jz      short loc_140021BBC
0x140021b9d  cmp     byte ptr [rcx+19h], 2
0x140021ba1  jb      short loc_140021BBC
0x140021ba3  mov     rcx, [rcx+10h]
0x140021ba7  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021bae  movzx   r9d, ax
0x140021bb2  mov     edx, 119h
0x140021bb7  call    WPP_SF_h
0x140021bbc  mov     rcx, r15; hKey
0x140021bbf  call    cs:__imp_RegCloseKey
0x140021bc6  nop     dword ptr [rax+rax+00h]
0x140021bcb  test    eax, eax
0x140021bcd  jz      short loc_140021BFF
0x140021bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140021bd6  cmp     rcx, rdi
0x140021bd9  jz      short loc_140021BFF
0x140021bdb  test    byte ptr [rcx+1Ch], 4
0x140021bdf  jz      short loc_140021BFF
0x140021be1  cmp     byte ptr [rcx+19h], 2
0x140021be5  jb      short loc_140021BFF
0x140021be7  mov     edx, 11Ah
0x140021bec  mov     rcx, [rcx+10h]
0x140021bf0  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
  ... truncated ...
```
