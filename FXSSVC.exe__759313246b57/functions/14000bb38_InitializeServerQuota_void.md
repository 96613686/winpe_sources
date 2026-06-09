# InitializeServerQuota(void)

- ea: `0x14000bb38`
- end: `0x14000bf28`
- name: `?InitializeServerQuota@@YAKXZ`
- size: `1008`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140049f40`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140009180`
- `0x14000ba78`
- `0x14000bb38`
- `0x14000cc90`
- `0x140051f44`
- `0x1400699d0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000bbb4`
- `KERNEL32!GetLastError` at `0x14000bd52`
- `KERNEL32!GetLastError` at `0x14000bdaf`
- `KERNEL32!GetLastError` at `0x14000be14`
- `KERNEL32!GetLastError` at `0x14000be6f`
- `KERNEL32!GetLastError` at `0x14000bed2`
- `KERNEL32!GetLastError` at `0x14000bbb4`
- `KERNEL32!GetLastError` at `0x14000bd52`
- `KERNEL32!GetLastError` at `0x14000bdaf`
- `KERNEL32!GetLastError` at `0x14000be14`
- `KERNEL32!GetLastError` at `0x14000be6f`
- `KERNEL32!GetLastError` at `0x14000bed2`
- `KERNEL32!CloseHandle` at `0x14000bdec`
- `KERNEL32!CloseHandle` at `0x14000be47`
- `KERNEL32!CloseHandle` at `0x14000beaa`
- `KERNEL32!CloseHandle` at `0x14000bdec`
- `KERNEL32!CloseHandle` at `0x14000be47`
- `KERNEL32!CloseHandle` at `0x14000beaa`
- `KERNEL32!EnterCriticalSection` at `0x14000bcaa`
- `KERNEL32!EnterCriticalSection` at `0x14000bcaa`
- `KERNEL32!LeaveCriticalSection` at `0x14000bcc8`
- `KERNEL32!LeaveCriticalSection` at `0x14000bcc8`
- `KERNEL32!CreateEventW` at `0x14000bb9c`
- `KERNEL32!CreateEventW` at `0x14000bb9c`

## pseudocode

```c
__int64 InitializeServerQuota(void)
{
  CFaxArchiving *v0; // rcx
  DWORD v1; // eax
  unsigned int v2; // ebx
  CMapDeviceId *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  CFaxArchiving *v6; // rcx
  CFaxConfiguration *v7; // rdx
  unsigned int FullArchiveSize; // eax
  __int64 v9; // rdx
  struct _SECURITY_ATTRIBUTES *v10; // rcx
  HANDLE ThreadAndRefCount; // rsi
  HANDLE v12; // rdi
  DWORD LastError; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  unsigned int v18; // [rsp+20h] [rbp-68h]
  unsigned int v19; // [rsp+20h] [rbp-68h]
  unsigned int v20[3]; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 v21[14]; // [rsp+3Ch] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  v20[0] = 0;
  g_hArchiveQuotaWarningEvent = CreateEventW(0, 0, 0, 0);
  if ( g_hArchiveQuotaWarningEvent )
  {
    *((_QWORD *)g_pFaxConfig + 7) = -1;
    v5 = CFaxArchiving::Init(v0);
    v2 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v5);
      }
      v20[2] = v2;
      v21[0] = 0;
      StringCchPrintfW(v21, 0xCu, L"%ld", v2);
      FaxLog(1u, 1u, 2u, 0xC0007D70, *((_QWORD *)g_pFaxConfig + 6));
      EnterCriticalSection(&g_CsConfig);
      *((_DWORD *)g_pFaxConfig + 2) |= 7u;
      LeaveCriticalSection(&g_CsConfig);
      v2 = 0;
    }
    else
    {
      v7 = g_pFaxConfig;
      if ( *((_DWORD *)g_pFaxConfig + 11) )
      {
        FullArchiveSize = CFaxArchiving::GetFullArchiveSize(v6, (unsigned __int64 *)g_pFaxConfig + 7, 0, 0);
        v2 = FullArchiveSize;
        if ( FullArchiveSize )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              168,
              &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
              FullArchiveSize);
          }
          *((_QWORD *)g_pFaxConfig + 7) = -1;
        }
      }
    }
    ThreadAndRefCount = CreateThreadAndRefCount(
                          (struct _SECURITY_ATTRIBUTES *)v6,
                          (__int64)v7,
                          (unsigned int (*)(void *))FaxArchiveQuotaWarningThread,
                          0,
                          v18,
                          v20);
    if ( ThreadAndRefCount )
    {
      v12 = CreateThreadAndRefCount(v10, v9, (unsigned int (*)(void *))FaxArchiveQuotaAutoDeleteThread, 0, v19, v20);
      if ( !v12 )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            170,
            &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
            LastError);
        }
      }
      if ( !CloseHandle(ThreadAndRefCount)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = GetLastError();
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          171,
          &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
          ThreadAndRefCount,
          v14);
      }
      if ( v12
        && !CloseHandle(v12)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = GetLastError();
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v12, v15);
      }
    }
    else
    {
      v1 = GetLastError();
      v2 = v1;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v4 = 169;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 166;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v1);
    }
  }
  if ( v2 && g_hArchiveQuotaWarningEvent )
  {
    if ( !CloseHandle(g_hArchiveQuotaWarningEvent)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = GetLastError();
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        173,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        g_hArchiveQuotaWarningEvent,
        v16);
    }
    g_hArchiveQuotaWarningEvent = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x14000bb38  push    rbx
0x14000bb3a  push    rsi
0x14000bb3b  push    rdi
0x14000bb3c  push    r13
0x14000bb3e  push    r15
0x14000bb40  sub     rsp, 60h
0x14000bb44  mov     rax, cs:__security_cookie
0x14000bb4b  xor     rax, rsp
0x14000bb4e  mov     [rsp+88h+var_30], rax
0x14000bb53  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb5a  lea     r15, WPP_GLOBAL_Control
0x14000bb61  lea     r13, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000bb68  cmp     rcx, r15
0x14000bb6b  jz      short loc_14000BB8A
0x14000bb6d  test    byte ptr [rcx+1Ch], 4
0x14000bb71  jz      short loc_14000BB8A
0x14000bb73  cmp     byte ptr [rcx+19h], 5
0x14000bb77  jb      short loc_14000BB8A
0x14000bb79  mov     rcx, [rcx+10h]
0x14000bb7d  mov     edx, 0A5h
0x14000bb82  mov     r8, r13
0x14000bb85  call    WPP_SF_
0x14000bb8a  xor     r9d, r9d; lpName
0x14000bb8d  mov     [rsp+88h+var_58], 0
0x14000bb95  xor     r8d, r8d; bInitialState
0x14000bb98  xor     edx, edx; bManualReset
0x14000bb9a  xor     ecx, ecx; lpEventAttributes
0x14000bb9c  call    cs:__imp_CreateEventW
0x14000bba3  nop     dword ptr [rax+rax+00h]
0x14000bba8  mov     cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA, rax; void * g_hArchiveQuotaWarningEvent
0x14000bbaf  test    rax, rax
0x14000bbb2  jnz     short loc_14000BBFF
0x14000bbb4  call    cs:__imp_GetLastError
0x14000bbbb  nop     dword ptr [rax+rax+00h]
0x14000bbc0  mov     ebx, eax
0x14000bbc2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bbc9  cmp     rcx, r15
0x14000bbcc  jz      loc_14000BE9A
0x14000bbd2  test    byte ptr [rcx+1Ch], 4
0x14000bbd6  jz      loc_14000BE9A
0x14000bbdc  cmp     byte ptr [rcx+19h], 2
0x14000bbe0  jb      loc_14000BE9A
0x14000bbe6  mov     edx, 0A6h
0x14000bbeb  mov     rcx, [rcx+10h]
0x14000bbef  mov     r9d, eax
0x14000bbf2  mov     r8, r13
0x14000bbf5  call    WPP_SF_d
0x14000bbfa  jmp     loc_14000BE9A
0x14000bbff  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000bc06  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000bc0a  mov     [rax+38h], rdi
0x14000bc0e  call    ?Init@CFaxArchiving@@QEAAKXZ; CFaxArchiving::Init(void)
0x14000bc13  mov     ebx, eax
0x14000bc15  test    eax, eax
0x14000bc17  jz      loc_14000BCD8
0x14000bc1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc24  cmp     rcx, r15
0x14000bc27  jz      short loc_14000BC49
0x14000bc29  test    byte ptr [rcx+1Ch], 4
0x14000bc2d  jz      short loc_14000BC49
0x14000bc2f  cmp     byte ptr [rcx+19h], 2
0x14000bc33  jb      short loc_14000BC49
0x14000bc35  mov     rcx, [rcx+10h]
0x14000bc39  mov     edx, 0A7h
0x14000bc3e  mov     r9d, eax
0x14000bc41  mov     r8, r13
0x14000bc44  call    WPP_SF_d
0x14000bc49  xor     eax, eax
0x14000bc4b  mov     [rsp+88h+var_50], ebx
0x14000bc4f  mov     r9d, ebx
0x14000bc52  mov     [rsp+88h+var_4C], ax
0x14000bc57  lea     r8, aLd; "%ld"
0x14000bc5e  lea     rcx, [rsp+88h+var_4C]; unsigned __int16 *
0x14000bc63  lea     edx, [rax+0Ch]; unsigned __int64
0x14000bc66  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000bc6b  xor     ecx, ecx
0x14000bc6d  lea     rdx, [rsp+88h+var_4C]
0x14000bc72  test    eax, eax
0x14000bc74  mov     r9d, 0C0007D70h
0x14000bc7a  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000bc81  cmovs   rdx, rcx
0x14000bc85  mov     [rsp+88h+var_60], rdx
0x14000bc8a  mov     rcx, [rax+30h]
0x14000bc8e  mov     [rsp+88h+var_68], rcx
0x14000bc93  mov     ecx, 1
0x14000bc98  mov     edx, ecx
0x14000bc9a  lea     r8d, [rcx+1]
0x14000bc9e  call    FaxLog
0x14000bca3  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000bcaa  call    cs:__imp_EnterCriticalSection
0x14000bcb1  nop     dword ptr [rax+rax+00h]
0x14000bcb6  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000bcbd  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000bcc4  or      dword ptr [rax+8], 7
0x14000bcc8  call    cs:__imp_LeaveCriticalSection
0x14000bccf  nop     dword ptr [rax+rax+00h]
0x14000bcd4  xor     ebx, ebx
0x14000bcd6  jmp     short loc_14000BD31
0x14000bcd8  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000bcdf  cmp     dword ptr [rdx+2Ch], 0
0x14000bce3  jz      short loc_14000BD31
0x14000bce5  add     rdx, 38h ; '8'; unsigned __int64 *
0x14000bce9  xor     r9d, r9d; unsigned int
0x14000bcec  xor     r8d, r8d; unsigned __int16 *
0x14000bcef  call    ?GetFullArchiveSize@CFaxArchiving@@QEAAKPEA_KPEAGK@Z; CFaxArchiving::GetFullArchiveSize(unsigned __int64 *,ushort *,ulong)
0x14000bcf4  mov     ebx, eax
0x14000bcf6  test    eax, eax
0x14000bcf8  jz      short loc_14000BD31
0x14000bcfa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd01  cmp     rcx, r15
0x14000bd04  jz      short loc_14000BD26
0x14000bd06  test    byte ptr [rcx+1Ch], 4
0x14000bd0a  jz      short loc_14000BD26
0x14000bd0c  cmp     byte ptr [rcx+19h], 2
0x14000bd10  jb      short loc_14000BD26
0x14000bd12  mov     rcx, [rcx+10h]
0x14000bd16  mov     edx, 0A8h
0x14000bd1b  mov     r9d, eax
0x14000bd1e  mov     r8, r13
0x14000bd21  call    WPP_SF_d
0x14000bd26  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14000bd2d  mov     [rax+38h], rdi
0x14000bd31  lea     rax, [rsp+88h+var_58]
0x14000bd36  xor     r9d, r9d; void *
0x14000bd39  lea     r8, ?FaxArchiveQuotaWarningThread@@YAKPEAX@Z; unsigned int (*)(void *)
0x14000bd40  mov     [rsp+88h+var_60], rax; unsigned int *
0x14000bd45  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x14000bd4a  mov     rsi, rax
0x14000bd4d  test    rax, rax
0x14000bd50  jnz     short loc_14000BD8E
0x14000bd52  call    cs:__imp_GetLastError
0x14000bd59  nop     dword ptr [rax+rax+00h]
0x14000bd5e  mov     ebx, eax
0x14000bd60  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd67  cmp     rcx, r15
0x14000bd6a  jz      loc_14000BE9A
0x14000bd70  test    byte ptr [rcx+1Ch], 4
0x14000bd74  jz      loc_14000BE9A
0x14000bd7a  cmp     byte ptr [rcx+19h], 2
0x14000bd7e  jb      loc_14000BE9A
0x14000bd84  mov     edx, 0A9h
0x14000bd89  jmp     loc_14000BBEB
0x14000bd8e  lea     rax, [rsp+88h+var_58]
0x14000bd93  xor     r9d, r9d; void *
0x14000bd96  lea     r8, ?FaxArchiveQuotaAutoDeleteThread@@YAKPEAX@Z; unsigned int (*)(void *)
0x14000bd9d  mov     [rsp+88h+var_60], rax; unsigned int *
0x14000bda2  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x14000bda7  mov     rdi, rax
0x14000bdaa  test    rax, rax
0x14000bdad  jnz     short loc_14000BDE9
0x14000bdaf  call    cs:__imp_GetLastError
0x14000bdb6  nop     dword ptr [rax+rax+00h]
0x14000bdbb  mov     ebx, eax
0x14000bdbd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bdc4  cmp     rcx, r15
0x14000bdc7  jz      short loc_14000BDE9
0x14000bdc9  test    byte ptr [rcx+1Ch], 4
0x14000bdcd  jz      short loc_14000BDE9
0x14000bdcf  cmp     byte ptr [rcx+19h], 2
0x14000bdd3  jb      short loc_14000BDE9
0x14000bdd5  mov     rcx, [rcx+10h]
0x14000bdd9  mov     edx, 0AAh
0x14000bdde  mov     r9d, eax
0x14000bde1  mov     r8, r13
0x14000bde4  call    WPP_SF_d
0x14000bde9  mov     rcx, rsi; hObject
0x14000bdec  call    cs:__imp_CloseHandle
0x14000bdf3  nop     dword ptr [rax+rax+00h]
0x14000bdf8  test    eax, eax
0x14000bdfa  jnz     short loc_14000BE3F
0x14000bdfc  mov     rax, cs:WPP_GLOBAL_Control
0x14000be03  cmp     rax, r15
0x14000be06  jz      short loc_14000BE3F
0x14000be08  test    byte ptr [rax+1Ch], 4
0x14000be0c  jz      short loc_14000BE3F
0x14000be0e  cmp     byte ptr [rax+19h], 2
0x14000be12  jb      short loc_14000BE3F
0x14000be14  call    cs:__imp_GetLastError
0x14000be1b  nop     dword ptr [rax+rax+00h]
0x14000be20  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be27  mov     edx, 0ABh
0x14000be2c  mov     r9, rsi
0x14000be2f  mov     dword ptr [rsp+88h+var_68], eax
0x14000be33  mov     r8, r13
0x14000be36  mov     rcx, [rcx+10h]
0x14000be3a  call    WPP_SF_qD
0x14000be3f  test    rdi, rdi
0x14000be42  jz      short loc_14000BE9A
0x14000be44  mov     rcx, rdi; hObject
0x14000be47  call    cs:__imp_CloseHandle
0x14000be4e  nop     dword ptr [rax+rax+00h]
0x14000be53  test    eax, eax
0x14000be55  jnz     short loc_14000BE9A
0x14000be57  mov     rax, cs:WPP_GLOBAL_Control
0x14000be5e  cmp     rax, r15
0x14000be61  jz      short loc_14000BE9A
0x14000be63  test    byte ptr [rax+1Ch], 4
0x14000be67  jz      short loc_14000BE9A
0x14000be69  cmp     byte ptr [rax+19h], 2
0x14000be6d  jb      short loc_14000BE9A
0x14000be6f  call    cs:__imp_GetLastError
0x14000be76  nop     dword ptr [rax+rax+00h]
0x14000be7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be82  mov     edx, 0ACh
0x14000be87  mov     r9, rdi
0x14000be8a  mov     dword ptr [rsp+88h+var_68], eax
0x14000be8e  mov     r8, r13
0x14000be91  mov     rcx, [rcx+10h]
0x14000be95  call    WPP_SF_qD
0x14000be9a  test    ebx, ebx
0x14000be9c  jz      short loc_14000BF0C
0x14000be9e  mov     rcx, cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA; hObject
0x14000bea5  test    rcx, rcx
0x14000bea8  jz      short loc_14000BF0C
0x14000beaa  call    cs:__imp_CloseHandle
0x14000beb1  nop     dword ptr [rax+rax+00h]
0x14000beb6  test    eax, eax
0x14000beb8  jnz     short loc_14000BF01
0x14000beba  mov     rax, cs:WPP_GLOBAL_Control
0x14000bec1  cmp     rax, r15
0x14000bec4  jz      short loc_14000BF01
0x14000bec6  test    byte ptr [rax+1Ch], 4
0x14000beca  jz      short loc_14000BF01
0x14000becc  cmp     byte ptr [rax+19h], 2
0x14000bed0  jb      short loc_14000BF01
0x14000bed2  call    cs:__imp_GetLastError
0x14000bed9  nop     dword ptr [rax+rax+00h]
0x14000bede  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bee5  mov     edx, 0ADh
0x14000beea  mov     r9, cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA; void * g_hArchiveQuotaWarningEvent
0x14000bef1  mov     r8, r13
0x14000bef4  mov     dword ptr [rsp+88h+var_68], eax
0x14000bef8  mov     rcx, [rcx+10h]
0x14000befc  call    WPP_SF_qD
0x14000bf01  mov     cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA, 0; void * g_hArchiveQuotaWarningEvent
0x14000bf0c  mov     eax, ebx
0x14000bf0e  mov     rcx, [rsp+88h+var_30]
0x14000bf13  xor     rcx, rsp; StackCookie
0x14000bf16  call    __security_check_cookie
0x14000bf1b  add     rsp, 60h
0x14000bf1f  pop     r15
0x14000bf21  pop     r13
0x14000bf23  pop     rdi
0x14000bf24  pop     rsi
0x14000bf25  pop     rbx
0x14000bf26  retn
```
