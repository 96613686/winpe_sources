# mseOpen(unsigned __int64 *,midiopendesc_tag *,ulong)

- ea: `0x18001e5a0`
- end: `0x18001e881`
- name: `?mseOpen@@YAIPEA_KPEAUmidiopendesc_tag@@K@Z`
- size: `737`
- prototype: `unsigned int __fastcall(unsigned __int64 *, struct midiopendesc_tag *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001fb58`

## callees

- `0x180012d08`
- `0x180017014`
- `0x180019330`
- `0x180019920`
- `0x18001e5a0`
- `0x18001f79c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e801`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e854`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e801`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e854`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e764`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e764`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e810`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e810`

## pseudocode

```c
__int64 __fastcall mseOpen(unsigned __int64 *a1, struct midiopendesc_tag *a2, int a3)
{
  MMRESULT v6; // ebp
  size_t v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  int v11; // r15d
  __int64 v12; // rax
  DWORD_PTR dwCallback; // rax
  __int64 v14; // rsi
  void *v15; // r8
  unsigned int v16; // esi
  HMIDIOUT v17; // rcx

  v6 = 7;
  v7 = 16 * (a2->cIds + 13);
  if ( (unsigned int)v7 < 0x10000 )
  {
    v10 = winmmAlloc(v7);
    if ( v10 )
    {
      v11 = 0;
      v12 = winmmAlloc(0x400u);
      *(_QWORD *)(v10 + 184) = v12;
      if ( v12 )
      {
        *(_DWORD *)(v10 + 16) |= 0x80u;
        *(_QWORD *)(v10 + 8) = a2->hMidi;
        *(_DWORD *)(v10 + 68) = 24;
        *(_DWORD *)(v10 + 72) = 500000;
        dwCallback = a2->dwCallback;
        *(_DWORD *)(v10 + 112) = a3;
        v14 = 0;
        *(_QWORD *)(v10 + 104) = dwCallback;
        *(_QWORD *)(v10 + 120) = a2->dwInstance;
        *(_DWORD *)(v10 + 76) = 4;
        *(_DWORD *)(v10 + 196) = a2->cIds;
        *(_DWORD *)(v10 + 80) = 3;
        *(_DWORD *)(v10 + 176) = 0;
        *(_DWORD *)(v10 + 20) = -1;
        *(_DWORD *)(v10 + 64) = 305402420;
        while ( (unsigned int)v14 < *(_DWORD *)(v10 + 196) )
        {
          *(_DWORD *)(v10 + 16 * (v14 + 13)) = a2->rgIds[v14].dwStreamID;
          v6 = midiOutOpen(
                 (LPHMIDIOUT)(v10 + 16LL * (unsigned int)v14 + 216),
                 a2->rgIds[v14].uDeviceID,
                 (DWORD_PTR)midiOutCallback,
                 0,
                 0x30000u);
          if ( v6 )
            goto LABEL_26;
          v14 = (unsigned int)(v14 + 1);
        }
        InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
        v11 = 1;
        *(_QWORD *)(v10 + 136) = 0;
        *(_DWORD *)(v10 + 148) = 1;
        *(_QWORD *)(v10 + 160) = mseTimebase;
        *(_DWORD *)(v10 + 152) = 1;
        *(_DWORD *)(v10 + 156) = 1;
        *(_DWORD *)(v10 + 144) = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_a5414217d91338b5429dfea51ae86c50_Traceguids);
        }
        midiOutSetClockRate(v10, 0);
        if ( !v6 )
        {
          *(_QWORD *)v10 = gpEmuList;
          *a1 = v10;
          gpEmuList = (struct midiemu_tag *)v10;
          return v6;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_a5414217d91338b5429dfea51ae86c50_Traceguids);
      }
LABEL_26:
      v15 = *(void **)(v10 + 184);
      if ( v15 )
        HeapFree(hHeap, 0, v15);
      if ( v11 )
        DeleteCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
      v16 = 0;
      for ( *(_DWORD *)(v10 + 64) = 0; v16 < *(_DWORD *)(v10 + 196); ++v16 )
      {
        v17 = *(HMIDIOUT *)(v10 + 16LL * v16 + 216);
        if ( v17 )
          midiOutClose(v17);
      }
      HeapFree(hHeap, 0, (LPVOID)v10);
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v9 = 12;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v9 = 11;
LABEL_6:
      WPP_SF_(v8[2], v9, &WPP_a5414217d91338b5429dfea51ae86c50_Traceguids);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18001e5a0  push    rbx
0x18001e5a2  push    rbp
0x18001e5a3  push    rsi
0x18001e5a4  push    r12
0x18001e5a6  push    r14
0x18001e5a8  push    r15
0x18001e5aa  sub     rsp, 38h
0x18001e5ae  mov     r12, rcx
0x18001e5b1  mov     esi, r8d
0x18001e5b4  mov     ecx, [rdx+20h]
0x18001e5b7  mov     r14, rdx
0x18001e5ba  add     ecx, 0Dh
0x18001e5bd  mov     ebp, 7
0x18001e5c2  shl     ecx, 4; Size
0x18001e5c5  cmp     ecx, 10000h
0x18001e5cb  jb      short loc_18001E613
0x18001e5cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5d4  lea     rax, WPP_GLOBAL_Control
0x18001e5db  cmp     rcx, rax
0x18001e5de  jz      loc_18001E871
0x18001e5e4  test    dword ptr [rcx+1Ch], 400000h
0x18001e5eb  jz      loc_18001E871
0x18001e5f1  cmp     byte ptr [rcx+19h], 1
0x18001e5f5  jb      loc_18001E871
0x18001e5fb  lea     edx, [rbp+4]
0x18001e5fe  mov     rcx, [rcx+10h]
0x18001e602  lea     r8, WPP_a5414217d91338b5429dfea51ae86c50_Traceguids
0x18001e609  call    WPP_SF_
0x18001e60e  jmp     loc_18001E871
0x18001e613  call    winmmAlloc
0x18001e618  mov     rbx, rax
0x18001e61b  test    rax, rax
0x18001e61e  jnz     short loc_18001E653
0x18001e620  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e627  lea     rax, WPP_GLOBAL_Control
0x18001e62e  cmp     rcx, rax
0x18001e631  jz      loc_18001E871
0x18001e637  test    dword ptr [rcx+1Ch], 400000h
0x18001e63e  jz      loc_18001E871
0x18001e644  cmp     byte ptr [rcx+19h], 1
0x18001e648  jb      loc_18001E871
0x18001e64e  lea     edx, [rbx+0Ch]
0x18001e651  jmp     short loc_18001E5FE
0x18001e653  mov     ecx, 400h; Size
0x18001e658  xor     r15d, r15d
0x18001e65b  call    winmmAlloc
0x18001e660  mov     [rbx+0B8h], rax
0x18001e667  test    rax, rax
0x18001e66a  jnz     short loc_18001E6B3
0x18001e66c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e673  lea     rax, WPP_GLOBAL_Control
0x18001e67a  cmp     rcx, rax
0x18001e67d  jz      loc_18001E7EC
0x18001e683  test    dword ptr [rcx+1Ch], 400000h
0x18001e68a  jz      loc_18001E7EC
0x18001e690  cmp     byte ptr [rcx+19h], 1
0x18001e694  jb      loc_18001E7EC
0x18001e69a  mov     rcx, [rcx+10h]
0x18001e69e  lea     edx, [r15+0Dh]
0x18001e6a2  lea     r8, WPP_a5414217d91338b5429dfea51ae86c50_Traceguids
0x18001e6a9  call    WPP_SF_
0x18001e6ae  jmp     loc_18001E7EC
0x18001e6b3  bts     dword ptr [rbx+10h], 7
0x18001e6b8  mov     rax, [r14]
0x18001e6bb  mov     [rbx+8], rax
0x18001e6bf  mov     dword ptr [rbx+44h], 18h
0x18001e6c6  mov     dword ptr [rbx+48h], 7A120h
0x18001e6cd  mov     rax, [r14+8]
0x18001e6d1  mov     [rbx+70h], esi
0x18001e6d4  xor     esi, esi
0x18001e6d6  mov     [rbx+68h], rax
0x18001e6da  mov     rax, [r14+10h]
0x18001e6de  mov     [rbx+78h], rax
0x18001e6e2  mov     dword ptr [rbx+4Ch], 4
0x18001e6e9  mov     eax, [r14+20h]
0x18001e6ed  mov     [rbx+0C4h], eax
0x18001e6f3  mov     dword ptr [rbx+50h], 3
0x18001e6fa  mov     [rbx+0B0h], r15d
0x18001e701  mov     dword ptr [rbx+14h], 0FFFFFFFFh
0x18001e708  mov     dword ptr [rbx+40h], 12341234h
0x18001e70f  cmp     esi, [rbx+0C4h]
0x18001e715  jnb     short loc_18001E760
0x18001e717  mov     eax, [r14+rsi*8+24h]
0x18001e71c  lea     rcx, [rsi+0Dh]
0x18001e720  add     rcx, rcx
0x18001e723  mov     [rsp+68h+fdwOpen], 30000h; fdwOpen
0x18001e72b  xor     r9d, r9d; dwInstance
0x18001e72e  lea     r8, midiOutCallback; dwCallback
0x18001e735  mov     [rbx+rcx*8], eax
0x18001e738  mov     edx, [r14+rsi*8+28h]; uDeviceID
0x18001e73d  mov     ecx, esi
0x18001e73f  shl     rcx, 4
0x18001e743  add     rcx, 0D8h
0x18001e74a  add     rcx, rbx; phmo
0x18001e74d  call    midiOutOpen
0x18001e752  mov     ebp, eax
0x18001e754  test    eax, eax
0x18001e756  jnz     loc_18001E7EC
0x18001e75c  inc     esi
0x18001e75e  jmp     short loc_18001E70F
0x18001e760  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001e764  call    cs:__imp_InitializeCriticalSection
0x18001e76a  mov     r15d, 1
0x18001e770  mov     qword ptr [rbx+88h], 0
0x18001e77b  lea     rax, ?mseTimebase@@YAKPEAUtag_clock@@@Z; mseTimebase(tag_clock *)
0x18001e782  mov     [rbx+94h], r15d
0x18001e789  mov     [rbx+0A0h], rax
0x18001e790  mov     [rbx+98h], r15d
0x18001e797  mov     [rbx+9Ch], r15d
0x18001e79e  mov     dword ptr [rbx+90h], 0
0x18001e7a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7af  lea     rax, WPP_GLOBAL_Control
0x18001e7b6  cmp     rcx, rax
0x18001e7b9  jz      short loc_18001E7DE
0x18001e7bb  test    dword ptr [rcx+1Ch], 400000h
0x18001e7c2  jz      short loc_18001E7DE
0x18001e7c4  cmp     byte ptr [rcx+19h], 2
0x18001e7c8  jb      short loc_18001E7DE
0x18001e7ca  mov     rcx, [rcx+10h]
0x18001e7ce  lea     edx, [r15+0Dh]
0x18001e7d2  lea     r8, WPP_a5414217d91338b5429dfea51ae86c50_Traceguids
0x18001e7d9  call    WPP_SF_
0x18001e7de  xor     edx, edx
0x18001e7e0  mov     rcx, rbx
0x18001e7e3  call    midiOutSetClockRate
0x18001e7e8  test    ebp, ebp
0x18001e7ea  jz      short loc_18001E85C
0x18001e7ec  mov     r8, [rbx+0B8h]; lpMem
0x18001e7f3  test    r8, r8
0x18001e7f6  jz      short loc_18001E807
0x18001e7f8  mov     rcx, cs:hHeap; hHeap
0x18001e7ff  xor     edx, edx; dwFlags
0x18001e801  call    cs:__imp_HeapFree
0x18001e807  test    r15d, r15d
0x18001e80a  jz      short loc_18001E816
0x18001e80c  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001e810  call    cs:__imp_DeleteCriticalSection
0x18001e816  xor     esi, esi
0x18001e818  mov     dword ptr [rbx+40h], 0
0x18001e81f  cmp     [rbx+0C4h], esi
0x18001e825  jbe     short loc_18001E848
0x18001e827  mov     eax, esi
0x18001e829  add     rax, rax
0x18001e82c  mov     rcx, [rbx+rax*8+0D8h]; hmo
0x18001e834  test    rcx, rcx
0x18001e837  jz      short loc_18001E83E
0x18001e839  call    midiOutClose
0x18001e83e  inc     esi
0x18001e840  cmp     esi, [rbx+0C4h]
0x18001e846  jb      short loc_18001E827
0x18001e848  mov     rcx, cs:hHeap; hHeap
0x18001e84f  mov     r8, rbx; lpMem
0x18001e852  xor     edx, edx; dwFlags
0x18001e854  call    cs:__imp_HeapFree
0x18001e85a  jmp     short loc_18001E871
0x18001e85c  mov     rax, cs:?gpEmuList@@3PEAUmidiemu_tag@@EA; midiemu_tag * gpEmuList
0x18001e863  mov     [rbx], rax
0x18001e866  mov     [r12], rbx
0x18001e86a  mov     cs:?gpEmuList@@3PEAUmidiemu_tag@@EA, rbx; midiemu_tag * gpEmuList
0x18001e871  mov     eax, ebp
0x18001e873  add     rsp, 38h
0x18001e877  pop     r15
0x18001e879  pop     r14
0x18001e87b  pop     r12
0x18001e87d  pop     rsi
0x18001e87e  pop     rbp
0x18001e87f  pop     rbx
0x18001e880  retn
```
