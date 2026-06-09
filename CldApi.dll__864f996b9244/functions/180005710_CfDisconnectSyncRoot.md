# CfDisconnectSyncRoot

- ea: `0x180005710`
- end: `0x180005b90`
- name: `CfDisconnectSyncRoot`
- size: `1152`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x1800022ee`
- `0x180005710`
- `0x18000b218`
- `0x18000b6c8`
- `0x180011338`
- `0x180011e18`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005b10`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005b10`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180005b21`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180005b21`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005b44`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005b44`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180005b37`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180005b37`
- `ntdll!RtlNtStatusToDosError` at `0x180005853`
- `ntdll!RtlNtStatusToDosError` at `0x1800058cf`
- `ntdll!RtlNtStatusToDosError` at `0x18000594d`
- `ntdll!RtlNtStatusToDosError` at `0x1800059d2`
- `ntdll!RtlNtStatusToDosError` at `0x180005a62`
- `ntdll!RtlNtStatusToDosError` at `0x180005853`
- `ntdll!RtlNtStatusToDosError` at `0x1800058cf`
- `ntdll!RtlNtStatusToDosError` at `0x18000594d`
- `ntdll!RtlNtStatusToDosError` at `0x1800059d2`
- `ntdll!RtlNtStatusToDosError` at `0x180005a62`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005756`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005756`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000579b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000579b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b5f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800057ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800057ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b6d`
- `FLTLIB!FilterSendMessage` at `0x180005aac`
- `FLTLIB!FilterSendMessage` at `0x180005aac`

## pseudocode

```c
__int64 __fastcall CfDisconnectSyncRoot(__int64 a1)
{
  _DWORD *v2; // rsi
  const WCHAR *v3; // r12
  const WCHAR *v4; // r13
  __int64 v5; // r14
  int v6; // edi
  HANDLE ProcessHeap; // rax
  NTSTATUS v8; // r15d
  NTSTATUS v9; // ecx
  __int64 v10; // rcx
  unsigned int v11; // ecx
  signed int v12; // eax
  NTSTATUS v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rax
  signed int v16; // eax
  NTSTATUS v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rax
  signed int v20; // eax
  NTSTATUS v21; // ecx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  signed int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  signed int v29; // eax
  _QWORD *v30; // rax
  HANDLE v31; // rax
  int v33[4]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v34; // [rsp+50h] [rbp-29h]
  __int64 v35; // [rsp+58h] [rbp-21h]
  DWORD BytesReturned; // [rsp+E0h] [rbp+67h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 Buffer; // [rsp+F0h] [rbp+77h] BYREF

  BytesReturned = 0;
  UnbiasedTime = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  memset_0(v33, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v5 = CfpReferenceSyncRoot(a1);
  v6 = v5 == 0 ? 0x57 : 0;
  if ( !v5 )
    v6 |= 0x80070000;
  if ( v6 >= 0 )
  {
    v6 = GlobalPortInit(1);
    if ( v6 >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      v2 = HeapAlloc(ProcessHeap, 8u, 0xE8u);
      v6 = v2 == 0 ? 8 : 0;
      if ( !v2 )
        v6 |= 0x80070000;
      if ( v6 >= 0 )
      {
        *(_QWORD *)v2 = 1886219331;
        v2[2] = 200;
        v2[3] = 1507328;
        memset_0(v2 + 4, 0, 0xB8u);
        v8 = -1073741811;
        if ( *((_WORD *)v2 + 7) )
        {
          v10 = (unsigned int)v2[2];
          if ( ((v10 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xE8 )
          {
            v11 = (v10 + 3) & 0xFFFFFFFC;
            v2[2] = v11;
            v2[5] = v11;
            v2[4] = 65543;
            *((_BYTE *)v2 + v11) = 1;
            ++v2[2];
            v9 = 0;
          }
          else
          {
            v9 = -1073741789;
          }
        }
        else
        {
          v9 = -1073741811;
        }
        v12 = RtlNtStatusToDosError(v9);
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        if ( v6 >= 0 )
        {
          if ( *((_WORD *)v2 + 7) > 1u )
          {
            v14 = (unsigned int)v2[2];
            if ( ((v14 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xE8 )
            {
              v15 = ((_DWORD)v14 + 3) & 0xFFFFFFFC;
              v2[2] = v15;
              if ( *((_WORD *)v2 + 12) )
                *((_WORD *)v2 + 6) |= 1u;
              v2[6] = 131080;
              v13 = 0;
              v2[7] = v15;
              *(_WORD *)((char *)v2 + v15) = 5;
              v2[2] += 2;
            }
            else
            {
              v13 = -1073741789;
            }
          }
          else
          {
            v13 = -1073741811;
          }
          v16 = RtlNtStatusToDosError(v13);
          v6 = v16;
          if ( v16 > 0 )
            v6 = (unsigned __int16)v16 | 0x80070000;
          if ( v6 >= 0 )
          {
            if ( *((_WORD *)v2 + 7) > 4u )
            {
              v18 = (unsigned int)v2[2];
              if ( ((v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xE8 )
              {
                v19 = ((_DWORD)v18 + 3) & 0xFFFFFFFC;
                v2[2] = v19;
                if ( *((_WORD *)v2 + 24) )
                  *((_WORD *)v2 + 6) |= 1u;
                v2[12] = 524294;
                v17 = 0;
                v2[13] = v19;
                *(_QWORD *)((char *)v2 + v19) = v5;
                v2[2] += 8;
              }
              else
              {
                v17 = -1073741789;
              }
            }
            else
            {
              v17 = -1073741811;
            }
            v20 = RtlNtStatusToDosError(v17);
            v6 = v20;
            if ( v20 > 0 )
              v6 = (unsigned __int16)v20 | 0x80070000;
            if ( v6 >= 0 )
            {
              if ( *((_WORD *)v2 + 7) > 2u )
              {
                v22 = (unsigned int)v2[2];
                if ( ((v22 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xE8 )
                {
                  v23 = *(_QWORD *)(v5 + 8);
                  v24 = ((_DWORD)v22 + 3) & 0xFFFFFFFC;
                  v2[2] = v24;
                  if ( *((_WORD *)v2 + 16) )
                    *((_WORD *)v2 + 6) |= 1u;
                  v2[8] = 524299;
                  v21 = 0;
                  v2[9] = v24;
                  *(_QWORD *)((char *)v2 + v24) = v23;
                  v2[2] += 8;
                }
                else
                {
                  v21 = -1073741789;
                }
              }
              else
              {
                v21 = -1073741811;
              }
              v25 = RtlNtStatusToDosError(v21);
              v6 = v25;
              if ( v25 > 0 )
                v6 = (unsigned __int16)v25 | 0x80070000;
              if ( v6 >= 0 )
              {
                if ( *((_WORD *)v2 + 7) > 0x16u )
                {
                  v26 = (unsigned int)v2[2];
                  if ( ((v26 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xE8 )
                  {
                    v27 = **(_QWORD **)(v5 + 16);
                    v28 = ((_DWORD)v26 + 3) & 0xFFFFFFFC;
                    v2[2] = v28;
                    if ( *((_WORD *)v2 + 96) )
                      *((_WORD *)v2 + 6) |= 1u;
                    v2[48] = 524294;
                    v8 = 0;
                    v2[49] = v28;
                    *(_QWORD *)((char *)v2 + v28) = v27;
                    v2[2] += 8;
                  }
                  else
                  {
                    v8 = -1073741789;
                  }
                }
                v29 = RtlNtStatusToDosError(v8);
                v6 = v29;
                if ( v29 > 0 )
                  v6 = (unsigned __int16)v29 | 0x80070000;
                if ( v6 >= 0 )
                {
                  v2[1] = 0;
                  *((_WORD *)v2 + 6) &= ~2u;
                  v6 = FilterSendMessage(hPort, v2, 0xE8u, 0, 0, &BytesReturned);
                }
              }
            }
          }
        }
      }
    }
  }
  v35 = a1;
  if ( v5 )
  {
    v30 = *(_QWORD **)(v5 + 16);
    v3 = (const WCHAR *)v30 + 14;
    v4 = (const WCHAR *)v30 + 270;
    v34 = *v30;
  }
  TlmLogApiReliability(0xCu, 0, 0, v3, v4, UnbiasedTime, v33, v6);
  if ( v5 )
  {
    Buffer = a1;
    RtlAcquireSRWLockExclusive(&qword_180028CF8);
    if ( RtlLookupElementGenericTableAvl(&stru_180028C90, &Buffer) )
      RtlDeleteElementGenericTableAvl(&stru_180028C90, &Buffer);
    RtlReleaseSRWLockExclusive(&qword_180028CF8);
    CfpReleaseSyncRoot(v5);
    CfpReleaseSyncRoot(v5);
  }
  if ( v2 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v2);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005710  mov     [rsp-8+arg_18], rbx
0x180005715  push    rbp
0x180005716  push    rsi
0x180005717  push    rdi
0x180005718  push    r12
0x18000571a  push    r13
0x18000571c  push    r14
0x18000571e  push    r15
0x180005720  lea     rbp, [rsp-27h]
0x180005725  sub     rsp, 0A0h
0x18000572c  xor     r15d, r15d
0x18000572f  mov     rbx, rcx
0x180005732  xor     edx, edx; Val
0x180005734  mov     [rbp+57h+BytesReturned], r15d
0x180005738  lea     rcx, [rbp+57h+var_90]; void *
0x18000573c  mov     [rbp+57h+UnbiasedTime], r15
0x180005740  mov     esi, r15d
0x180005743  mov     r12d, r15d
0x180005746  lea     r8d, [r15+58h]; Size
0x18000574a  mov     r13d, r15d
0x18000574d  call    memset_0
0x180005752  lea     rcx, [rbp+57h+UnbiasedTime]; UnbiasedTime
0x180005756  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000575c  mov     rcx, rbx
0x18000575f  call    CfpReferenceSyncRoot
0x180005764  mov     rcx, rax
0x180005767  mov     r14, rax
0x18000576a  neg     rcx
0x18000576d  sbb     edi, edi
0x18000576f  not     edi
0x180005771  and     edi, 57h
0x180005774  mov     ecx, edi
0x180005776  or      ecx, 80070000h
0x18000577c  test    rax, rax
0x18000577f  cmovz   edi, ecx
0x180005782  test    edi, edi
0x180005784  js      loc_180005AB4
0x18000578a  mov     cl, 1
0x18000578c  call    GlobalPortInit
0x180005791  mov     edi, eax
0x180005793  test    eax, eax
0x180005795  js      loc_180005AB4
0x18000579b  call    cs:__imp_GetProcessHeap
0x1800057a1  lea     edx, [r15+8]; dwFlags
0x1800057a5  mov     r8d, 0E8h; dwBytes
0x1800057ab  mov     rcx, rax; hHeap
0x1800057ae  call    cs:__imp_HeapAlloc
0x1800057b4  mov     rsi, rax
0x1800057b7  neg     rax
0x1800057ba  sbb     edi, edi
0x1800057bc  not     edi
0x1800057be  and     edi, 8
0x1800057c1  mov     eax, edi
0x1800057c3  or      eax, 80070000h
0x1800057c8  test    rsi, rsi
0x1800057cb  cmovz   edi, eax
0x1800057ce  test    edi, edi
0x1800057d0  js      loc_180005AB4
0x1800057d6  xor     edx, edx; Val
0x1800057d8  mov     qword ptr [rsi], 706D6C43h
0x1800057df  mov     r8d, 0B8h; Size
0x1800057e5  mov     dword ptr [rsi+8], 0C8h
0x1800057ec  lea     rcx, [rsi+10h]; void *
0x1800057f0  mov     dword ptr [rsi+0Ch], 170000h
0x1800057f7  call    memset_0
0x1800057fc  mov     eax, r15d
0x1800057ff  mov     r15d, 0C000000Dh
0x180005805  cmp     ax, [rsi+0Eh]
0x180005809  jb      short loc_180005810
0x18000580b  mov     ecx, r15d
0x18000580e  jmp     short loc_180005853
0x180005810  mov     ecx, [rsi+8]
0x180005813  mov     edx, 1
0x180005818  lea     rax, [rcx+3]
0x18000581c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180005820  add     rax, rdx
0x180005823  cmp     rax, 0E8h
0x180005829  jbe     short loc_180005832
0x18000582b  mov     ecx, 0C0000023h
0x180005830  jmp     short loc_180005853
0x180005832  lea     eax, [rcx+3]
0x180005835  and     eax, 0FFFFFFFCh
0x180005838  mov     ecx, eax
0x18000583a  mov     [rsi+8], ecx
0x18000583d  mov     [rsi+14h], ecx
0x180005840  mov     dword ptr [rsi+10h], 10007h
0x180005847  mov     [rax+rsi], dl
0x18000584a  add     [rsi+8], edx
0x18000584d  xor     r8d, r8d
0x180005850  mov     ecx, r8d; Status
0x180005853  call    cs:__imp_RtlNtStatusToDosError
0x180005859  xor     edx, edx
0x18000585b  mov     edi, eax
0x18000585d  test    eax, eax
0x18000585f  jle     short loc_18000586A
0x180005861  movzx   edi, ax
0x180005864  or      edi, 80070000h
0x18000586a  test    edi, edi
0x18000586c  js      loc_180005AB4
0x180005872  mov     r9d, 2
0x180005878  lea     r8d, [r9-1]
0x18000587c  cmp     r8w, [rsi+0Eh]
0x180005881  jb      short loc_180005888
0x180005883  mov     ecx, r15d
0x180005886  jmp     short loc_1800058CF
0x180005888  mov     ecx, [rsi+8]
0x18000588b  lea     rax, [rcx+3]
0x18000588f  and     rax, 0FFFFFFFFFFFFFFFCh
0x180005893  add     rax, r9
0x180005896  cmp     rax, 0E8h
0x18000589c  jbe     short loc_1800058A5
0x18000589e  mov     ecx, 0C0000023h
0x1800058a3  jmp     short loc_1800058CF
0x1800058a5  lea     eax, [rcx+3]
0x1800058a8  and     eax, 0FFFFFFFCh
0x1800058ab  mov     [rsi+8], eax
0x1800058ae  cmp     [rsi+18h], dx
0x1800058b2  jz      short loc_1800058B9
0x1800058b4  or      [rsi+0Ch], r8w
0x1800058b9  mov     dword ptr [rsi+18h], 20008h
0x1800058c0  mov     ecx, edx; Status
0x1800058c2  mov     [rsi+1Ch], eax
0x1800058c5  mov     word ptr [rax+rsi], 5
0x1800058cb  add     [rsi+8], r9d
0x1800058cf  call    cs:__imp_RtlNtStatusToDosError
0x1800058d5  xor     edx, edx
0x1800058d7  mov     edi, eax
0x1800058d9  test    eax, eax
0x1800058db  jle     short loc_1800058E6
0x1800058dd  movzx   edi, ax
0x1800058e0  or      edi, 80070000h
0x1800058e6  test    edi, edi
0x1800058e8  js      loc_180005AB4
0x1800058ee  mov     eax, 4
0x1800058f3  cmp     ax, [rsi+0Eh]
0x1800058f7  jb      short loc_1800058FE
0x1800058f9  mov     ecx, r15d
0x1800058fc  jmp     short loc_18000594D
0x1800058fe  mov     ecx, [rsi+8]
0x180005901  mov     r8d, 8
0x180005907  lea     rax, [rcx+3]
0x18000590b  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000590f  add     rax, r8
0x180005912  cmp     rax, 0E8h
0x180005918  jbe     short loc_180005921
0x18000591a  mov     ecx, 0C0000023h
0x18000591f  jmp     short loc_18000594D
0x180005921  lea     eax, [rcx+3]
0x180005924  and     eax, 0FFFFFFFCh
0x180005927  mov     [rsi+8], eax
0x18000592a  cmp     [rsi+30h], dx
0x18000592e  jz      short loc_180005939
0x180005930  mov     ecx, 1
0x180005935  or      [rsi+0Ch], cx
0x180005939  mov     dword ptr [rsi+30h], 80006h
0x180005940  mov     ecx, edx; Status
0x180005942  mov     [rsi+34h], eax
0x180005945  mov     [rax+rsi], r14
0x180005949  add     [rsi+8], r8d
0x18000594d  call    cs:__imp_RtlNtStatusToDosError
0x180005953  xor     r8d, r8d
0x180005956  mov     edi, eax
0x180005958  test    eax, eax
0x18000595a  jle     short loc_180005965
0x18000595c  movzx   edi, ax
0x18000595f  or      edi, 80070000h
0x180005965  test    edi, edi
0x180005967  js      loc_180005AB4
0x18000596d  mov     eax, 2
0x180005972  cmp     ax, [rsi+0Eh]
0x180005976  jb      short loc_18000597D
0x180005978  mov     ecx, r15d
0x18000597b  jmp     short loc_1800059D2
0x18000597d  mov     ecx, [rsi+8]
0x180005980  mov     r9d, 8
0x180005986  lea     rax, [rcx+3]
0x18000598a  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000598e  add     rax, r9
0x180005991  cmp     rax, 0E8h
0x180005997  jbe     short loc_1800059A0
0x180005999  mov     ecx, 0C0000023h
0x18000599e  jmp     short loc_1800059D2
0x1800059a0  mov     rdx, [r14+8]
0x1800059a4  lea     eax, [rcx+3]
0x1800059a7  and     eax, 0FFFFFFFCh
0x1800059aa  mov     [rsi+8], eax
0x1800059ad  cmp     [rsi+20h], r8w
0x1800059b2  jz      short loc_1800059BD
0x1800059b4  mov     ecx, 1
0x1800059b9  or      [rsi+0Ch], cx
0x1800059bd  mov     dword ptr [rsi+20h], 8000Bh
0x1800059c4  mov     ecx, r8d; Status
0x1800059c7  mov     [rsi+24h], eax
0x1800059ca  mov     [rax+rsi], rdx
0x1800059ce  add     [rsi+8], r9d
0x1800059d2  call    cs:__imp_RtlNtStatusToDosError
0x1800059d8  xor     r8d, r8d
0x1800059db  mov     edi, eax
0x1800059dd  test    eax, eax
0x1800059df  jle     short loc_1800059EA
0x1800059e1  movzx   edi, ax
0x1800059e4  or      edi, 80070000h
0x1800059ea  test    edi, edi
0x1800059ec  js      loc_180005AB4
0x1800059f2  mov     eax, 16h
0x1800059f7  cmp     ax, [rsi+0Eh]
0x1800059fb  jnb     short loc_180005A5F
0x1800059fd  mov     ecx, [rsi+8]
0x180005a00  mov     r9d, 8
0x180005a06  lea     rax, [rcx+3]
0x180005a0a  and     rax, 0FFFFFFFFFFFFFFFCh
0x180005a0e  add     rax, r9
0x180005a11  cmp     rax, 0E8h
0x180005a17  jbe     short loc_180005A21
0x180005a19  mov     r15d, 0C0000023h
0x180005a1f  jmp     short loc_180005A5F
0x180005a21  mov     rax, [r14+10h]
0x180005a25  mov     rdx, [rax]
0x180005a28  lea     eax, [rcx+3]
0x180005a2b  and     eax, 0FFFFFFFCh
0x180005a2e  mov     [rsi+8], eax
0x180005a31  cmp     [rsi+0C0h], r8w
0x180005a39  jz      short loc_180005A44
0x180005a3b  mov     ecx, 1
0x180005a40  or      [rsi+0Ch], cx
0x180005a44  mov     dword ptr [rsi+0C0h], 80006h
0x180005a4e  mov     r15d, r8d
0x180005a51  mov     [rsi+0C4h], eax
0x180005a57  mov     [rax+rsi], rdx
0x180005a5b  add     [rsi+8], r9d
0x180005a5f  mov     ecx, r15d; Status
0x180005a62  call    cs:__imp_RtlNtStatusToDosError
0x180005a68  xor     r15d, r15d
0x180005a6b  mov     edi, eax
0x180005a6d  test    eax, eax
0x180005a6f  jle     short loc_180005A7A
0x180005a71  movzx   edi, ax
0x180005a74  or      edi, 80070000h
0x180005a7a  test    edi, edi
0x180005a7c  js      short loc_180005AB4
0x180005a7e  mov     eax, 0FFFDh
0x180005a83  mov     [rsi+4], r15d
0x180005a87  and     [rsi+0Ch], ax
0x180005a8b  xor     r9d, r9d; lpOutBuffer
0x180005a8e  mov     rcx, qword ptr cs:hPort; hPort
0x180005a95  lea     rax, [rbp+57h+BytesReturned]
0x180005a99  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x180005a9e  mov     r8d, 0E8h; dwInBufferSize
0x180005aa4  mov     rdx, rsi; lpInBuffer
0x180005aa7  mov     [rsp+0D0h+dwOutBufferSize], r15d; dwOutBufferSize
0x180005aac  call    cs:__imp_FilterSendMessage
0x180005ab2  mov     edi, eax
0x180005ab4  mov     [rbp+57h+var_78], rbx
0x180005ab8  test    r14, r14
0x180005abb  jz      short loc_180005AD3
0x180005abd  mov     rax, [r14+10h]
0x180005ac1  lea     r12, [rax+1Ch]
0x180005ac5  lea     r13, [rax+21Ch]
0x180005acc  mov     rax, [rax]
0x180005acf  mov     [rbp+57h+var_80], rax
0x180005ad3  mov     [rsp+0D0h+var_98], edi
0x180005ad7  lea     rax, [rbp+57h+var_90]
0x180005adb  mov     [rsp+0D0h+var_A0], rax
0x180005ae0  mov     ecx, 0Ch
0x180005ae5  mov     rax, [rbp+57h+UnbiasedTime]
0x180005ae9  mov     r9, r12
0x180005aec  mov     [rsp+0D0h+lpBytesReturned], rax
0x180005af1  xor     r8d, r8d
0x180005af4  xor     edx, edx
0x180005af6  mov     qword ptr [rsp+0D0h+dwOutBufferSize], r13
0x180005afb  call    TlmLogApiReliability
0x180005b00  test    r14, r14
0x180005b03  jz      short loc_180005B5A
0x180005b05  lea     rcx, qword_180028CF8
0x180005b0c  mov     [rbp+57h+Buffer], rbx
0x180005b10  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180005b16  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180005b1a  lea     rcx, stru_180028C90; Table
0x180005b21  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180005b27  test    rax, rax
0x180005b2a  jz      short loc_180005B3D
0x180005b2c  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180005b30  lea     rcx, stru_180028C90; Table
0x180005b37  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180005b3d  lea     rcx, qword_180028CF8
0x180005b44  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180005b4a  mov     rcx, r14
0x180005b4d  call    CfpReleaseSyncRoot
0x180005b52  mov     rcx, r14
0x180005b55  call    CfpReleaseSyncRoot
0x180005b5a  test    rsi, rsi
0x180005b5d  jz      short loc_180005B73
0x180005b5f  call    cs:__imp_GetProcessHeap
0x180005b65  mov     r8, rsi; lpMem
0x180005b68  xor     edx, edx; dwFlags
0x180005b6a  mov     rcx, rax; hHeap
0x180005b6d  call    cs:__imp_HeapFree
0x180005b73  mov     rbx, [rsp+0D0h+arg_18]
0x180005b7b  mov     eax, edi
0x180005b7d  add     rsp, 0A0h
  ... truncated ...
```
