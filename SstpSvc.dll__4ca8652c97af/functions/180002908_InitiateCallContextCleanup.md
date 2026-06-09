# InitiateCallContextCleanup

- ea: `0x180002908`
- end: `0x180002d2f`
- name: `InitiateCallContextCleanup`
- size: `1063`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `20`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180001160`
- `0x180001240`
- `0x180001a80`
- `0x180001ee0`
- `0x1800021f0`
- `0x180002908`
- `0x180002e00`
- `0x180004ef4`
- `0x180005560`
- `0x180006b64`
- `0x180009c7c`
- `0x180009dd8`
- `0x18000a448`
- `0x18000a620`
- `0x18000afbc`
- `0x18000b9fc`
- `0x18000bf68`
- `0x18000cdd8`
- `0x18000df30`
- `0x18000e9a0`

## callees

- `0x180002908`
- `0x180002d40`
- `0x180002d70`
- `0x18000827c`
- `0x180008360`
- `0x180009c7c`
- `0x18000a448`
- `0x18000cdd8`
- `0x18000cec8`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002abd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002bb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ca3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002abd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002bb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ca3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ba5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ce6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ba5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ce6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cfa`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180002b55`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180002b55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002c14`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002c31`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002c14`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002c31`

## pseudocode

```c
__int64 __fastcall InitiateCallContextCleanup(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdx
  __int64 v5; // r9
  __int64 v6; // rsi
  int v7; // eax
  bool v8; // zf
  unsigned int v9; // eax
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  __int64 v11; // rdx
  struct _TP_WORK *v12; // rcx
  struct _TP_WORK *v13; // rcx
  __int64 **v14; // rbx
  __int64 v15; // rcx
  __int64 *v16; // rax
  __int64 *v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  int v21; // [rsp+20h] [rbp-828h] BYREF
  _BYTE v22[2044]; // [rsp+24h] [rbp-824h] BYREF

  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  if ( (byte_18002D803 & 8) != 0 )
  {
    v5 = *(unsigned int *)(a1 + 252);
    LOWORD(v21) = 0;
    FormatRRASErrorString((wchar_t *)&v21, L"CoId=%hs:InitiateContextCleanup(0x%x)", a1 + 552, v5);
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v21);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
  v6 = *(_QWORD *)(a1 + 624);
  if ( v6 )
  {
    *(_QWORD *)(a1 + 624) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 288));
    InitiateCallContextCleanup(v6, a2);
    DereferenceRefCount(v6 + 208);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  }
  if ( !*(_DWORD *)(a1 + 252) )
    goto LABEL_40;
  if ( !*(_BYTE *)(a1 + 435) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
    *(_BYTE *)(a1 + 435) = 1;
  }
  v7 = *(_DWORD *)(a1 + 252);
  if ( (v7 & 0x20) != 0 )
  {
    v7 &= ~0x20u;
    *(_DWORD *)(a1 + 252) = v7;
    if ( a2 == 1 )
    {
      if ( (*(_BYTE *)(a1 + 616) & 2) != 0 )
        goto LABEL_16;
      v7 |= 0x40u;
    }
    else
    {
      if ( a2 )
        goto LABEL_16;
      v7 |= 0x200u;
    }
    *(_DWORD *)(a1 + 252) = v7;
  }
LABEL_16:
  if ( (v7 & 0x10000) != 0 )
  {
    if ( (v7 & 0x200) != 0 )
      goto LABEL_18;
    goto LABEL_40;
  }
  if ( (v7 & 8) != 0 )
  {
    *(_DWORD *)(a1 + 252) = v7 & 0xFFFFBFF7 | 0x4000;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    NotifyMakeCallComplete(a1, *(unsigned int *)(a1 + 268), a1 + 592);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    *(_DWORD *)(a1 + 252) &= ~0x4000u;
    v7 = *(_DWORD *)(a1 + 252);
  }
  if ( (v7 & 0x4000) != 0 )
    goto LABEL_40;
  if ( (v7 & 0x40) == 0 )
  {
    if ( (v7 & 0x800) == 0 )
    {
      if ( (v7 & 0x200) != 0 )
      {
LABEL_18:
        v8 = *(_BYTE *)(a1 + 248) == 0;
        *(_DWORD *)(a1 + 252) = v7 & 0xFFFFDDFF | 0x2000;
        if ( v8 )
          DisconnectServerHttpCallContext(a1);
        else
          DisconnectClientHttpCallContext(a1);
        goto LABEL_41;
      }
      if ( (v7 & 0x2000) == 0 )
      {
        if ( (v7 & 0x400) != 0 )
        {
          *(_DWORD *)(a1 + 252) = v7 & 0xFFFFFBFB | 4;
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
          CancelIoEx(*((HANDLE *)SstpSvcGlobals + 35), (LPOVERLAPPED)(a1 + 40));
          goto LABEL_41;
        }
        if ( (v7 & 4) == 0 )
        {
          if ( (v7 & 0x8000) != 0 )
          {
            v7 &= ~0x8000u;
            *(_DWORD *)(a1 + 252) = v7;
          }
          if ( (v7 & 0x100) == 0 && (v7 & 0x80u) == 0 && (v7 & 0x10) != 0 )
          {
            *(_DWORD *)(a1 + 252) = v7 & 0xFFFFFFEF;
            DereferenceRefCount(a1 + 208);
          }
        }
      }
    }
LABEL_40:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    goto LABEL_41;
  }
  LOBYTE(v4) = 0;
  v9 = v7 & 0xFFFFF7BF | 0x800;
  *(_DWORD *)(a1 + 252) = v9;
  if ( (v9 & 0x1000) != 0 )
  {
    LOBYTE(v4) = 1;
    *(_DWORD *)(a1 + 252) = v9 & 0xFFFFEFFF;
  }
  DisconnectSstpCallFromTpi(a1, v4);
LABEL_41:
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 288);
  if ( *(_DWORD *)(a1 + 252) == 1 )
  {
    *(_DWORD *)(a1 + 252) = 0;
    LeaveCriticalSection(v10);
    v11 = *(_QWORD *)(a1 + 256);
    if ( v11 )
    {
      FreeBufferToPool((__int64)SstpSvcGlobals + 424, v11, 1);
      *(_QWORD *)(a1 + 256) = 0;
    }
    v12 = *(struct _TP_WORK **)(a1 + 328);
    if ( v12 )
    {
      CloseThreadpoolWork(v12);
      *(_QWORD *)(a1 + 328) = 0;
    }
    v13 = *(struct _TP_WORK **)(a1 + 336);
    if ( v13 )
    {
      CloseThreadpoolWork(v13);
      *(_QWORD *)(a1 + 336) = 0;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    v14 = (__int64 **)(a1 + 416);
    while ( 1 )
    {
      v17 = *v14;
      if ( *v14 == (__int64 *)v14 )
        break;
      v15 = *v17;
      v16 = (__int64 *)v17[1];
      *v16 = *v17;
      *(_QWORD *)(v15 + 8) = v16;
      FreeBufferToPool((__int64)SstpSvcGlobals + 424, (__int64)(v17 - 5), 1);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    v18 = *(_QWORD *)(a1 + 224);
    v19 = *(_QWORD **)(a1 + 232);
    *v19 = v18;
    *(_QWORD *)(v18 + 8) = v19;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
    DereferenceRefCount(a1 + 208);
  }
  else
  {
    LeaveCriticalSection(v10);
  }
  return DereferenceRefCount(a1 + 208);
}

```

## disassembly

```asm
0x180002908  mov     [rsp+arg_10], rbx
0x18000290d  push    rbp
0x18000290e  push    rsi
0x18000290f  push    rdi
0x180002910  sub     rsp, 830h
0x180002917  mov     rax, cs:__security_cookie
0x18000291e  xor     rax, rsp
0x180002921  mov     [rsp+848h+var_28], rax
0x180002929  mov     ebp, edx
0x18000292b  mov     rdi, rcx
0x18000292e  xor     eax, eax
0x180002930  lea     rcx, [rsp+848h+var_824]; void *
0x180002935  xor     edx, edx; Val
0x180002937  mov     [rsp+848h+var_828], eax
0x18000293b  mov     r8d, 7FCh; Size
0x180002941  call    memset_0
0x180002946  test    cs:byte_18002D803, 8
0x18000294d  jz      short loc_180002996
0x18000294f  mov     r9d, [rdi+0FCh]
0x180002956  lea     r8, [rdi+228h]
0x18000295d  xor     eax, eax
0x18000295f  lea     rdx, aCoidHsInitiate; "CoId=%hs:InitiateContextCleanup(0x%x)"
0x180002966  lea     rcx, [rsp+848h+var_828]
0x18000296b  mov     word ptr [rsp+848h+var_828], ax
0x180002970  call    FormatRRASErrorString
0x180002975  test    cs:byte_18002D803, 8
0x18000297c  jz      short loc_180002996
0x18000297e  lea     r8, [rsp+848h+var_828]
0x180002983  lea     rdx, RasSSTPSvcTraceError
0x18000298a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002991  call    McTemplateU0z_EventWriteTransfer
0x180002996  lock inc dword ptr [rdi+0D0h]
0x18000299d  mov     rsi, [rdi+270h]
0x1800029a4  test    rsi, rsi
0x1800029a7  jz      short loc_1800029F0
0x1800029a9  lea     rbx, [rdi+120h]
0x1800029b0  mov     qword ptr [rdi+270h], 0
0x1800029bb  mov     rcx, rbx; lpCriticalSection
0x1800029be  call    cs:__imp_LeaveCriticalSection
0x1800029c4  lea     rcx, [rsi+120h]; lpCriticalSection
0x1800029cb  call    cs:__imp_EnterCriticalSection
0x1800029d1  mov     edx, ebp
0x1800029d3  mov     rcx, rsi
0x1800029d6  call    InitiateCallContextCleanup
0x1800029db  lea     rcx, [rsi+0D0h]
0x1800029e2  call    DereferenceRefCount
0x1800029e7  mov     rcx, rbx; lpCriticalSection
0x1800029ea  call    cs:__imp_EnterCriticalSection
0x1800029f0  cmp     dword ptr [rdi+0FCh], 0
0x1800029f7  jz      loc_180002B9E
0x1800029fd  cmp     byte ptr [rdi+1B3h], 0
0x180002a04  jnz     short loc_180002A14
0x180002a06  lock inc dword ptr [rdi+0D0h]
0x180002a0d  mov     byte ptr [rdi+1B3h], 1
0x180002a14  mov     eax, [rdi+0FCh]
0x180002a1a  mov     esi, 200h
0x180002a1f  test    al, 20h
0x180002a21  jz      short loc_180002A4B
0x180002a23  and     eax, 0FFFFFFDFh
0x180002a26  mov     [rdi+0FCh], eax
0x180002a2c  cmp     ebp, 1
0x180002a2f  jnz     short loc_180002A3F
0x180002a31  test    byte ptr [rdi+268h], 2
0x180002a38  jnz     short loc_180002A4B
0x180002a3a  or      eax, 40h
0x180002a3d  jmp     short loc_180002A45
0x180002a3f  test    ebp, ebp
0x180002a41  jnz     short loc_180002A4B
0x180002a43  or      eax, esi
0x180002a45  mov     [rdi+0FCh], eax
0x180002a4b  bt      eax, 10h
0x180002a4f  jnb     short loc_180002A81
0x180002a51  test    esi, eax
0x180002a53  jz      loc_180002B9E
0x180002a59  btr     eax, 9
0x180002a5d  bts     eax, 0Dh
0x180002a61  cmp     byte ptr [rdi+0F8h], 0
0x180002a68  mov     [rdi+0FCh], eax
0x180002a6e  jnz     loc_180002B5D
0x180002a74  mov     rcx, rdi
0x180002a77  call    DisconnectServerHttpCallContext
0x180002a7c  jmp     loc_180002BAB
0x180002a81  mov     ebp, 4000h
0x180002a86  test    al, 8
0x180002a88  jz      short loc_180002AD1
0x180002a8a  and     eax, 0FFFFFFF7h
0x180002a8d  lea     rbx, [rdi+120h]
0x180002a94  or      eax, ebp
0x180002a96  mov     rcx, rbx; lpCriticalSection
0x180002a99  mov     [rdi+0FCh], eax
0x180002a9f  call    cs:__imp_LeaveCriticalSection
0x180002aa5  mov     edx, [rdi+10Ch]
0x180002aab  lea     r8, [rdi+250h]
0x180002ab2  mov     rcx, rdi
0x180002ab5  call    NotifyMakeCallComplete
0x180002aba  mov     rcx, rbx; lpCriticalSection
0x180002abd  call    cs:__imp_EnterCriticalSection
0x180002ac3  btr     dword ptr [rdi+0FCh], 0Eh
0x180002acb  mov     eax, [rdi+0FCh]
0x180002ad1  test    ebp, eax
0x180002ad3  jnz     loc_180002B9E
0x180002ad9  test    al, 40h
0x180002adb  jz      short loc_180002B0B
0x180002add  and     eax, 0FFFFFFBFh
0x180002ae0  xor     dl, dl
0x180002ae2  bts     eax, 0Bh
0x180002ae6  mov     [rdi+0FCh], eax
0x180002aec  bt      eax, 0Ch
0x180002af0  jnb     short loc_180002AFE
0x180002af2  btr     eax, 0Ch
0x180002af6  mov     dl, 1
0x180002af8  mov     [rdi+0FCh], eax
0x180002afe  mov     rcx, rdi
0x180002b01  call    DisconnectSstpCallFromTpi
0x180002b06  jmp     loc_180002BAB
0x180002b0b  bt      eax, 0Bh
0x180002b0f  jb      loc_180002B9E
0x180002b15  test    esi, eax
0x180002b17  jnz     loc_180002A59
0x180002b1d  bt      eax, 0Dh
0x180002b21  jb      short loc_180002B9E
0x180002b23  bt      eax, 0Ah
0x180002b27  jnb     short loc_180002B67
0x180002b29  btr     eax, 0Ah
0x180002b2d  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002b34  or      eax, 4
0x180002b37  mov     [rdi+0FCh], eax
0x180002b3d  call    cs:__imp_LeaveCriticalSection
0x180002b43  mov     rcx, cs:SstpSvcGlobals
0x180002b4a  lea     rdx, [rdi+28h]; lpOverlapped
0x180002b4e  mov     rcx, [rcx+118h]; hFile
0x180002b55  call    cs:__imp_CancelIoEx
0x180002b5b  jmp     short loc_180002BAB
0x180002b5d  mov     rcx, rdi
0x180002b60  call    DisconnectClientHttpCallContext
0x180002b65  jmp     short loc_180002BAB
0x180002b67  test    al, 4
0x180002b69  jnz     short loc_180002B9E
0x180002b6b  bt      eax, 0Fh
0x180002b6f  jnb     short loc_180002B7B
0x180002b71  btr     eax, 0Fh
0x180002b75  mov     [rdi+0FCh], eax
0x180002b7b  bt      eax, 8
0x180002b7f  jb      short loc_180002B9E
0x180002b81  test    al, al
0x180002b83  js      short loc_180002B9E
0x180002b85  test    al, 10h
0x180002b87  jz      short loc_180002B9E
0x180002b89  and     eax, 0FFFFFFEFh
0x180002b8c  lea     rcx, [rdi+0D0h]
0x180002b93  mov     [rdi+0FCh], eax
0x180002b99  call    DereferenceRefCount
0x180002b9e  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002ba5  call    cs:__imp_LeaveCriticalSection
0x180002bab  lea     rbx, [rdi+120h]
0x180002bb2  mov     rcx, rbx; lpCriticalSection
0x180002bb5  call    cs:__imp_EnterCriticalSection
0x180002bbb  cmp     dword ptr [rdi+0FCh], 1
0x180002bc2  mov     rcx, rbx; lpCriticalSection
0x180002bc5  jnz     loc_180002CFA
0x180002bcb  mov     dword ptr [rdi+0FCh], 0
0x180002bd5  call    cs:__imp_LeaveCriticalSection
0x180002bdb  mov     rdx, [rdi+100h]
0x180002be2  test    rdx, rdx
0x180002be5  jz      short loc_180002C08
0x180002be7  mov     rcx, cs:SstpSvcGlobals
0x180002bee  mov     r8b, 1
0x180002bf1  add     rcx, 1A8h
0x180002bf8  call    FreeBufferToPool
0x180002bfd  mov     qword ptr [rdi+100h], 0
0x180002c08  mov     rcx, [rdi+148h]; pwk
0x180002c0f  test    rcx, rcx
0x180002c12  jz      short loc_180002C25
0x180002c14  call    cs:__imp_CloseThreadpoolWork
0x180002c1a  mov     qword ptr [rdi+148h], 0
0x180002c25  mov     rcx, [rdi+150h]; pwk
0x180002c2c  test    rcx, rcx
0x180002c2f  jz      short loc_180002C42
0x180002c31  call    cs:__imp_CloseThreadpoolWork
0x180002c37  mov     qword ptr [rdi+150h], 0
0x180002c42  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002c49  call    cs:__imp_EnterCriticalSection
0x180002c4f  lea     rbx, [rdi+1A0h]
0x180002c56  jmp     short loc_180002C80
0x180002c58  mov     rcx, [rdx]
0x180002c5b  mov     r8b, 1
0x180002c5e  mov     rax, [rdx+8]
0x180002c62  add     rdx, 0FFFFFFFFFFFFFFD8h
0x180002c66  mov     [rax], rcx
0x180002c69  mov     [rcx+8], rax
0x180002c6d  mov     rcx, cs:SstpSvcGlobals
0x180002c74  add     rcx, 1A8h
0x180002c7b  call    FreeBufferToPool
0x180002c80  mov     rdx, [rbx]
0x180002c83  cmp     rdx, rbx
0x180002c86  jnz     short loc_180002C58
0x180002c88  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002c8f  call    cs:__imp_LeaveCriticalSection
0x180002c95  mov     rcx, cs:SstpSvcGlobals
0x180002c9c  add     rcx, 0E0h; lpCriticalSection
0x180002ca3  call    cs:__imp_EnterCriticalSection
0x180002ca9  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002cb0  call    cs:__imp_EnterCriticalSection
0x180002cb6  mov     rcx, [rdi+0E0h]
0x180002cbd  mov     rax, [rdi+0E8h]
0x180002cc4  mov     [rax], rcx
0x180002cc7  mov     [rcx+8], rax
0x180002ccb  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002cd2  call    cs:__imp_LeaveCriticalSection
0x180002cd8  mov     rcx, cs:SstpSvcGlobals
0x180002cdf  add     rcx, 0E0h; lpCriticalSection
0x180002ce6  call    cs:__imp_LeaveCriticalSection
0x180002cec  lea     rcx, [rdi+0D0h]
0x180002cf3  call    DereferenceRefCount
0x180002cf8  jmp     short loc_180002D00
0x180002cfa  call    cs:__imp_LeaveCriticalSection
0x180002d00  lea     rcx, [rdi+0D0h]
0x180002d07  call    DereferenceRefCount
0x180002d0c  mov     rcx, [rsp+848h+var_28]
0x180002d14  xor     rcx, rsp; StackCookie
0x180002d17  call    __security_check_cookie
0x180002d1c  mov     rbx, [rsp+848h+arg_10]
0x180002d24  add     rsp, 830h
0x180002d2b  pop     rdi
0x180002d2c  pop     rsi
0x180002d2d  pop     rbp
0x180002d2e  retn
```
