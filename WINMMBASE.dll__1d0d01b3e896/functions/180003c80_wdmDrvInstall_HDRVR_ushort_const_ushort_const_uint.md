# wdmDrvInstall(HDRVR__ *,ushort const *,ushort const *,uint)

- ea: `0x180003c80`
- end: `0x1800041c3`
- name: `?wdmDrvInstall@@YAIPEAUHDRVR__@@PEBG1I@Z`
- size: `1347`
- prototype: `unsigned int(HDRVR, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800027d8`

## callees

- `0x180003c80`
- `0x1800041d0`
- `0x180004350`
- `0x180007d70`
- `0x18000d630`
- `0x18000f38c`
- `0x1800174ec`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180003d6d`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180003d6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003d2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003e23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003d2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003e23`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003dc6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003dc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ed1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ed1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003efb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003efb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000418c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000418c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003cf0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003cf0`

## pseudocode

```c
__int64 __fastcall wdmDrvInstall(HDRVR a1, const unsigned __int16 *a2, const unsigned __int16 *a3, unsigned int a4)
{
  HDRVR v6; // rbp
  HMODULE ModuleHandle; // rax
  unsigned int v8; // esi
  __int64 *v9; // r12
  int *v10; // r15
  const CHAR *v11; // r14
  FARPROC ProcAddress; // rax
  void (__fastcall *v13)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // r13
  __int64 v14; // rcx
  char *v15; // rax
  char *v16; // r15
  __int64 v17; // rsi
  const WCHAR *v18; // rdx
  __int64 v19; // rcx
  _WORD *v20; // r8
  __int64 v21; // r9
  _WORD *v22; // rcx
  __int64 v23; // rbx
  SIZE_T v25; // rbx
  _WORD *v26; // rax
  _WORD *v27; // rdx
  unsigned __int64 v28; // rbx
  _WORD *v29; // rcx
  unsigned int v30; // eax
  __int64 *v31; // rbx
  __int64 *i; // rcx
  _QWORD *v33; // rax
  __int64 v35; // rbx
  const unsigned __int16 *v36; // rdx
  unsigned __int16 *v37; // rax
  void *v38; // r8
  int *v39; // [rsp+70h] [rbp+8h]
  unsigned int v40; // [rsp+78h] [rbp+10h]

  v6 = a1;
  if ( !a1 )
    return 0;
  if ( (a4 & 0x4000) != 0 )
  {
    ModuleHandle = DrvGetModuleHandle(a1);
  }
  else
  {
    ModuleHandle = (HMODULE)a1;
    v6 = 0;
  }
  v8 = a4 & 0xF;
  switch ( v8 )
  {
    case 1u:
      v9 = (__int64 *)&waveindrvZ;
      v40 = 50;
      v10 = (int *)&wTotalWaveInDevs;
      v11 = szWidMessage;
      break;
    case 2u:
      v9 = &waveoutdrvZ;
      v40 = 3;
      v10 = (int *)&wTotalWaveOutDevs;
      v11 = szWodMessage;
      break;
    case 3u:
      v9 = &midiindrvZ;
      v40 = 53;
      v10 = &wTotalMidiInDevs;
      v11 = szMidMessage;
      break;
    case 4u:
      v9 = &midioutdrvZ;
      v40 = 1;
      v10 = &wTotalMidiOutDevs;
      v11 = szModMessage;
      break;
    case 5u:
      v9 = &auxdrvZ;
      v40 = 3;
      v10 = &wTotalAuxDevs;
      v11 = szAuxMessage;
      break;
    case 7u:
      v9 = (__int64 *)&mixerdrvZ;
      v40 = 1;
      v10 = &guTotalMixerDevs;
      v11 = szMxdMessage;
      break;
    default:
      return 0;
  }
  v39 = v10;
  ProcAddress = GetProcAddress(ModuleHandle, v11);
  v13 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
  if ( !ProcAddress )
    return 0;
  v14 = *v9;
  if ( (a4 & 0x2000) != 0 )
  {
    for ( ; (__int64 *)v14 != v9; v14 = *(_QWORD *)v14 )
    {
      if ( (*(_BYTE *)(v14 + 112) & 1) == 0 )
      {
        if ( a3 )
        {
          if ( *(const unsigned __int16 **)(v14 + 96) == a3 )
            break;
        }
        else if ( *(FARPROC *)(v14 + 80) == ProcAddress )
        {
          break;
        }
      }
    }
    v35 = 0;
    if ( (__int64 *)v14 != v9 )
      v35 = v14;
    if ( v35 )
    {
      if ( (*(_BYTE *)(v35 + 112) & 2) == 0 )
        *v10 -= *(_DWORD *)(v35 + 88);
      v36 = *(const unsigned __int16 **)(v35 + 96);
      *(_DWORD *)(v35 + 112) |= 1u;
      *(_DWORD *)(v35 + 88) = 0;
      CleanUpHandles(v8, v36);
      mregDecUsagePtr((struct _MMDRV *)v35);
      return 1;
    }
    return 0;
  }
  if ( (__int64 *)v14 == v9 )
    goto LABEL_9;
  while ( 1 )
  {
    if ( (*(_BYTE *)(v14 + 112) & 1) != 0 )
      goto LABEL_42;
    if ( !a3 )
      break;
    if ( *(const unsigned __int16 **)(v14 + 96) == a3 )
      goto LABEL_46;
LABEL_42:
    v14 = *(_QWORD *)v14;
    if ( (__int64 *)v14 == v9 )
      goto LABEL_9;
  }
  if ( *(FARPROC *)(v14 + 80) != ProcAddress )
    goto LABEL_42;
LABEL_46:
  if ( (__int64 *)v14 != v9 )
    return 0;
LABEL_9:
  v15 = (char *)HeapAlloc(hHeap, 8u, 0x120u);
  v16 = v15;
  if ( !v15 )
    return 0;
  *((_QWORD *)v15 + 4) = v6;
  *((_DWORD *)v15 + 28) = (a4 >> 14) & 2;
  *((_DWORD *)v15 + 22) = 0;
  *((_DWORD *)v15 + 23) = 1;
  *((_QWORD *)v15 + 12) = a3;
  *((_QWORD *)v15 + 10) = v13;
  _o_mbstowcs(v15 + 40, v11, 20);
  v17 = 2147483646;
  v18 = L"wdmaud.drv";
  v19 = 2147483646;
  v20 = v16 + 160;
  v21 = 64;
  do
  {
    if ( !v19 )
      break;
    if ( !*v18 )
      break;
    *v20++ = *v18++;
    --v19;
    --v21;
  }
  while ( v21 );
  v22 = v20 - 1;
  if ( v21 )
    v22 = v20;
  *v22 = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v16 + 3);
  if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, const unsigned __int16 *))v13)(0, 104, 0, 0, a3) )
  {
    v37 = wdmPnPInterfaceFromEndpointWorker(a3);
    *((_QWORD *)v16 + 13) = v37;
    if ( v37 )
    {
      *((_DWORD *)v16 + 28) |= 8u;
      v13(0, 100, 0, 0, v37);
      goto LABEL_28;
    }
    goto LABEL_82;
  }
  v23 = -1;
  while ( a3[++v23] != 0 )
    ;
  v25 = 2 * v23 + 2;
  v26 = HeapAlloc(hHeap, 8u, v25);
  *((_QWORD *)v16 + 13) = v26;
  v27 = v26;
  if ( !v26 )
    goto LABEL_82;
  v28 = v25 >> 1;
  if ( v28 )
  {
    if ( v28 > 0x7FFFFFFF )
    {
      *v26 = 0;
    }
    else
    {
      do
      {
        if ( !v17 )
          break;
        if ( !*a3 )
          break;
        *v27++ = *a3++;
        --v17;
        --v28;
      }
      while ( v28 );
      v29 = v27 - 1;
      if ( v28 )
        v29 = v27;
      *v29 = 0;
    }
  }
LABEL_28:
  v30 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v13)(0, v40, 0, *((_QWORD *)v16 + 13), 0);
  if ( HIWORD(v30) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids, v30);
    }
    v13(0, 101, 0, 0, *((_QWORD *)v16 + 13));
    goto LABEL_82;
  }
  *((_DWORD *)v16 + 22) = (unsigned __int16)v30;
  if ( !(_WORD)v30 )
  {
LABEL_82:
    DeleteCriticalSection((LPCRITICAL_SECTION)v16 + 3);
    v38 = (void *)*((_QWORD *)v16 + 13);
    if ( v38 )
      HeapFree(hHeap, 0, v38);
    HeapFree(hHeap, 0, v16);
    return 0;
  }
  v31 = (__int64 *)*((_QWORD *)v16 + 12);
  if ( v31 )
  {
    EnterCriticalSection(&NumDevsCritSec);
    for ( i = (__int64 *)wdmDevZ; i; i = (__int64 *)*i )
    {
      if ( v31 == i + 4 )
      {
        ++*((_DWORD *)i + 5);
        break;
      }
    }
    LeaveCriticalSection(&NumDevsCritSec);
  }
  if ( (v16[112] & 2) == 0 )
    *v39 += *((_DWORD *)v16 + 22);
  v33 = (_QWORD *)v9[1];
  *((_QWORD *)v16 + 1) = v33;
  *(_QWORD *)v16 = v9;
  *v33 = v16;
  *(_QWORD *)(*(_QWORD *)v16 + 8LL) = v16;
  StringIdDict_Insert((struct _MMDRV *)v16);
  return 1;
}

```

## disassembly

```asm
0x180003c80  mov     [rsp+arg_10], rbx
0x180003c85  mov     [rsp+arg_8], rdx
0x180003c8a  push    rbp
0x180003c8b  push    rsi
0x180003c8c  push    rdi
0x180003c8d  push    r12
0x180003c8f  push    r13
0x180003c91  push    r14
0x180003c93  push    r15
0x180003c95  sub     rsp, 30h
0x180003c99  mov     ebx, r9d
0x180003c9c  mov     rdi, r8
0x180003c9f  mov     rbp, rcx
0x180003ca2  test    rcx, rcx
0x180003ca5  jz      loc_1800041BC
0x180003cab  bt      ebx, 0Eh
0x180003caf  jnb     loc_180003F4E
0x180003cb5  call    DrvGetModuleHandle
0x180003cba  mov     esi, ebx
0x180003cbc  and     esi, 0Fh
0x180003cbf  cmp     esi, 1
0x180003cc2  jnz     loc_180003FE3
0x180003cc8  lea     r12, waveindrvZ
0x180003ccf  mov     dword ptr [rsp+68h+arg_8], 32h ; '2'
0x180003cd7  lea     r15, wTotalWaveInDevs
0x180003cde  lea     r14, szWidMessage; "widMessage"
0x180003ce5  mov     rdx, r14; lpProcName
0x180003ce8  mov     [rsp+68h+arg_0], r15
0x180003ced  mov     rcx, rax; hModule
0x180003cf0  call    cs:__imp_GetProcAddress
0x180003cf6  mov     r13, rax
0x180003cf9  test    rax, rax
0x180003cfc  jz      loc_1800041BC
0x180003d02  mov     rcx, [r12]
0x180003d06  bt      ebx, 0Dh
0x180003d0a  jb      loc_180003F88
0x180003d10  cmp     rcx, r12
0x180003d13  jnz     loc_180003F58
0x180003d19  mov     rcx, cs:hHeap; hHeap
0x180003d20  mov     edx, 8; dwFlags
0x180003d25  mov     r8d, 120h; dwBytes
0x180003d2b  call    cs:__imp_HeapAlloc
0x180003d31  mov     r15, rax
0x180003d34  test    rax, rax
0x180003d37  jz      loc_1800041BC
0x180003d3d  shr     ebx, 0Eh
0x180003d40  lea     rcx, [rax+28h]
0x180003d44  and     ebx, 2
0x180003d47  mov     [rax+20h], rbp
0x180003d4b  mov     r8d, 14h
0x180003d51  mov     [rax+70h], ebx
0x180003d54  mov     rdx, r14
0x180003d57  mov     dword ptr [rax+58h], 0
0x180003d5e  mov     dword ptr [rax+5Ch], 1
0x180003d65  mov     [rax+60h], rdi
0x180003d69  mov     [rax+50h], r13
0x180003d6d  call    cs:__imp__o_mbstowcs
0x180003d73  mov     esi, 7FFFFFFEh
0x180003d78  lea     rdx, aWdmaudDrv; "wdmaud.drv"
0x180003d7f  mov     ecx, esi
0x180003d81  lea     r8, [r15+0A0h]
0x180003d88  mov     r9d, 40h ; '@'
0x180003d8e  xchg    ax, ax
0x180003d90  test    rcx, rcx
0x180003d93  jz      short loc_180003DB2
0x180003d95  movzx   eax, word ptr [rdx]
0x180003d98  test    ax, ax
0x180003d9b  jz      short loc_180003DB2
0x180003d9d  mov     [r8], ax
0x180003da1  add     rdx, 2
0x180003da5  add     r8, 2
0x180003da9  dec     rcx
0x180003dac  sub     r9, 1
0x180003db0  jnz     short loc_180003D90
0x180003db2  test    r9, r9
0x180003db5  lea     rcx, [r8-2]
0x180003db9  cmovnz  rcx, r8
0x180003dbd  xor     eax, eax
0x180003dbf  mov     [rcx], ax
0x180003dc2  lea     rcx, [r15+78h]; lpCriticalSection
0x180003dc6  call    cs:__imp_InitializeCriticalSection
0x180003dcc  xor     r9d, r9d
0x180003dcf  mov     [rsp+68h+var_48], rdi
0x180003dd4  xor     r8d, r8d
0x180003dd7  mov     edx, 68h ; 'h'
0x180003ddc  xor     ecx, ecx
0x180003dde  mov     rax, r13
0x180003de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de6  test    eax, eax
0x180003de8  jnz     loc_1800040ED
0x180003dee  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180003df5  nop     word ptr [rax+rax+00000000h]
0x180003e00  cmp     word ptr [rdi+rbx*2+2], 0
0x180003e06  lea     rbx, [rbx+1]
0x180003e0a  jnz     short loc_180003E00
0x180003e0c  mov     rcx, cs:hHeap; hHeap
0x180003e13  lea     rbx, ds:2[rbx*2]
0x180003e1b  mov     r8, rbx; dwBytes
0x180003e1e  mov     edx, 8; dwFlags
0x180003e23  call    cs:__imp_HeapAlloc
0x180003e29  mov     [r15+68h], rax
0x180003e2d  mov     rdx, rax
0x180003e30  test    rax, rax
0x180003e33  jz      loc_180004188
0x180003e39  shr     rbx, 1
0x180003e3c  jz      short loc_180003E81
0x180003e3e  cmp     rbx, 7FFFFFFFh
0x180003e45  ja      loc_180004126
0x180003e4b  nop     dword ptr [rax+rax+00h]
0x180003e50  test    rsi, rsi
0x180003e53  jz      short loc_180003E71
0x180003e55  movzx   eax, word ptr [rdi]
0x180003e58  test    ax, ax
0x180003e5b  jz      short loc_180003E71
0x180003e5d  mov     [rdx], ax
0x180003e60  add     rdi, 2
0x180003e64  add     rdx, 2
0x180003e68  dec     rsi
0x180003e6b  sub     rbx, 1
0x180003e6f  jnz     short loc_180003E50
0x180003e71  test    rbx, rbx
0x180003e74  lea     rcx, [rdx-2]
0x180003e78  cmovnz  rcx, rdx
0x180003e7c  xor     eax, eax
0x180003e7e  mov     [rcx], ax
0x180003e81  mov     r9, [r15+68h]
0x180003e85  xor     r8d, r8d
0x180003e88  mov     edx, dword ptr [rsp+68h+arg_8]
0x180003e8c  xor     ecx, ecx
0x180003e8e  mov     rax, r13
0x180003e91  mov     [rsp+68h+var_48], 0
0x180003e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e9f  mov     edx, eax
0x180003ea1  xor     ecx, ecx
0x180003ea3  shr     edx, 10h
0x180003ea6  cmp     cx, dx
0x180003ea9  jnz     loc_180004130
0x180003eaf  movzx   ecx, ax
0x180003eb2  xor     eax, eax
0x180003eb4  mov     [r15+58h], ecx
0x180003eb8  cmp     ax, cx
0x180003ebb  jz      loc_180004188
0x180003ec1  mov     rbx, [r15+60h]
0x180003ec5  test    rbx, rbx
0x180003ec8  jz      short loc_180003F01
0x180003eca  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180003ed1  call    cs:__imp_EnterCriticalSection
0x180003ed7  mov     rcx, qword ptr cs:?wdmDevZ@@3Utag_wdmdeviceinterface@@A; tag_wdmdeviceinterface wdmDevZ
0x180003ede  test    rcx, rcx
0x180003ee1  jz      short loc_180003EF4
0x180003ee3  lea     rax, [rcx+20h]
0x180003ee7  cmp     rbx, rax
0x180003eea  jz      short loc_180003EF1
0x180003eec  mov     rcx, [rcx]
0x180003eef  jmp     short loc_180003EDE
0x180003ef1  inc     dword ptr [rcx+14h]
0x180003ef4  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180003efb  call    cs:__imp_LeaveCriticalSection
0x180003f01  test    byte ptr [r15+70h], 2
0x180003f06  jnz     short loc_180003F13
0x180003f08  mov     rcx, [rsp+68h+arg_0]
0x180003f0d  mov     eax, [r15+58h]
0x180003f11  add     [rcx], eax
0x180003f13  mov     rax, [r12+8]
0x180003f18  mov     rcx, r15; struct _MMDRV *
0x180003f1b  mov     [r15+8], rax
0x180003f1f  mov     [r15], r12
0x180003f22  mov     [rax], r15
0x180003f25  mov     rax, [r15]
0x180003f28  mov     [rax+8], r15
0x180003f2c  call    ?StringIdDict_Insert@@YAXPEAU_MMDRV@@@Z; StringIdDict_Insert(_MMDRV *)
0x180003f31  mov     eax, 1
0x180003f36  mov     rbx, [rsp+68h+arg_10]
0x180003f3e  add     rsp, 30h
0x180003f42  pop     r15
0x180003f44  pop     r14
0x180003f46  pop     r13
0x180003f48  pop     r12
0x180003f4a  pop     rdi
0x180003f4b  pop     rsi
0x180003f4c  pop     rbp
0x180003f4d  retn
0x180003f4e  mov     rax, rcx
0x180003f51  xor     ebp, ebp
0x180003f53  jmp     loc_180003CBA
0x180003f58  test    byte ptr [rcx+70h], 1
0x180003f5c  jz      short loc_180003F6B
0x180003f5e  mov     rcx, [rcx]
0x180003f61  cmp     rcx, r12
0x180003f64  jnz     short loc_180003F58
0x180003f66  jmp     loc_180003D19
0x180003f6b  test    rdi, rdi
0x180003f6e  jz      loc_1800040DE
0x180003f74  cmp     [rcx+60h], rdi
0x180003f78  jnz     short loc_180003F5E
0x180003f7a  cmp     rcx, r12
0x180003f7d  jz      loc_180003D19
0x180003f83  jmp     loc_1800041BC
0x180003f88  cmp     rcx, r12
0x180003f8b  jz      short loc_180003F9F
0x180003f8d  test    byte ptr [rcx+70h], 1
0x180003f91  jz      loc_1800040B0
0x180003f97  mov     rcx, [rcx]
0x180003f9a  cmp     rcx, r12
0x180003f9d  jnz     short loc_180003F8D
0x180003f9f  xor     ebx, ebx
0x180003fa1  cmp     rcx, r12
0x180003fa4  cmovnz  rbx, rcx
0x180003fa8  test    rbx, rbx
0x180003fab  jz      loc_1800041BC
0x180003fb1  test    byte ptr [rbx+70h], 2
0x180003fb5  jz      loc_1800040D3
0x180003fbb  mov     rdx, [rbx+60h]; unsigned __int16 *
0x180003fbf  mov     ecx, esi; unsigned int
0x180003fc1  or      dword ptr [rbx+70h], 1
0x180003fc5  mov     dword ptr [rbx+58h], 0
0x180003fcc  call    ?CleanUpHandles@@YAXIPEBG@Z; CleanUpHandles(uint,ushort const *)
0x180003fd1  mov     rcx, rbx; struct _MMDRV *
0x180003fd4  call    mregDecUsagePtr
0x180003fd9  mov     eax, 1
0x180003fde  jmp     loc_180003F36
0x180003fe3  mov     ecx, esi
0x180003fe5  sub     ecx, 2
0x180003fe8  jz      loc_18000408E
0x180003fee  sub     ecx, 1
0x180003ff1  jz      short loc_18000406C
0x180003ff3  sub     ecx, 1
0x180003ff6  jz      short loc_18000404A
0x180003ff8  sub     ecx, 1
0x180003ffb  jz      short loc_180004028
0x180003ffd  cmp     ecx, 2
0x180004000  jnz     loc_1800041BC
0x180004006  lea     r12, mixerdrvZ
0x18000400d  mov     dword ptr [rsp+68h+arg_8], 1
0x180004015  lea     r15, guTotalMixerDevs
0x18000401c  lea     r14, szMxdMessage; "mxdMessage"
0x180004023  jmp     loc_180003CE5
0x180004028  lea     r12, auxdrvZ
0x18000402f  mov     dword ptr [rsp+68h+arg_8], 3
0x180004037  lea     r15, wTotalAuxDevs
0x18000403e  lea     r14, szAuxMessage; "auxMessage"
0x180004045  jmp     loc_180003CE5
0x18000404a  lea     r12, midioutdrvZ
0x180004051  mov     dword ptr [rsp+68h+arg_8], 1
0x180004059  lea     r15, wTotalMidiOutDevs
0x180004060  lea     r14, szModMessage; "modMessage"
0x180004067  jmp     loc_180003CE5
0x18000406c  lea     r12, midiindrvZ
0x180004073  mov     dword ptr [rsp+68h+arg_8], 35h ; '5'
0x18000407b  lea     r15, wTotalMidiInDevs
0x180004082  lea     r14, szMidMessage; "midMessage"
0x180004089  jmp     loc_180003CE5
0x18000408e  lea     r12, waveoutdrvZ
0x180004095  mov     dword ptr [rsp+68h+arg_8], 3
0x18000409d  lea     r15, wTotalWaveOutDevs
0x1800040a4  lea     r14, szWodMessage; "wodMessage"
0x1800040ab  jmp     loc_180003CE5
0x1800040b0  test    rdi, rdi
0x1800040b3  jz      short loc_1800040C4
0x1800040b5  cmp     [rcx+60h], rdi
0x1800040b9  jz      loc_180003F9F
0x1800040bf  jmp     loc_180003F97
0x1800040c4  cmp     [rcx+50h], r13
0x1800040c8  jz      loc_180003F9F
0x1800040ce  jmp     loc_180003F97
0x1800040d3  mov     eax, [rbx+58h]
0x1800040d6  sub     [r15], eax
0x1800040d9  jmp     loc_180003FBB
0x1800040de  cmp     [rcx+50h], r13
0x1800040e2  jz      loc_180003F7A
0x1800040e8  jmp     loc_180003F5E
0x1800040ed  mov     rcx, rdi; unsigned __int16 *
0x1800040f0  call    ?wdmPnPInterfaceFromEndpointWorker@@YAPEBGPEBG@Z; wdmPnPInterfaceFromEndpointWorker(ushort const *)
0x1800040f5  mov     [r15+68h], rax
0x1800040f9  test    rax, rax
0x1800040fc  jz      loc_180004188
0x180004102  or      dword ptr [r15+70h], 8
0x180004107  xor     r9d, r9d
0x18000410a  mov     [rsp+68h+var_48], rax
0x18000410f  xor     r8d, r8d
0x180004112  mov     rax, r13
0x180004115  mov     edx, 64h ; 'd'
0x18000411a  xor     ecx, ecx
0x18000411c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004121  jmp     loc_180003E81
0x180004126  xor     ecx, ecx
0x180004128  mov     [rax], cx
0x18000412b  jmp     loc_180003E81
0x180004130  mov     rcx, cs:WPP_GLOBAL_Control
0x180004137  lea     rdx, WPP_GLOBAL_Control
0x18000413e  cmp     rcx, rdx
0x180004141  jz      short loc_18000416A
0x180004143  test    dword ptr [rcx+1Ch], 400000h
0x18000414a  jz      short loc_18000416A
0x18000414c  cmp     byte ptr [rcx+19h], 4
0x180004150  jb      short loc_18000416A
0x180004152  mov     rcx, [rcx+10h]
0x180004156  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x18000415d  mov     edx, 0Eh
0x180004162  mov     r9d, eax
  ... truncated ...
```
