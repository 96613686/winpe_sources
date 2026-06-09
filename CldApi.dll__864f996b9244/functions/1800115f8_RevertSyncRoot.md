# RevertSyncRoot

- ea: `0x1800115f8`
- end: `0x18001188f`
- name: `RevertSyncRoot`
- size: `663`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800079c0`
- `0x18000b284`

## callees

- `0x1800022ee`
- `0x1800115f8`
- `0x18001bb5c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001172c`
- `ntdll!RtlNtStatusToDosError` at `0x1800117a1`
- `ntdll!RtlNtStatusToDosError` at `0x18001180a`
- `ntdll!RtlNtStatusToDosError` at `0x18001172c`
- `ntdll!RtlNtStatusToDosError` at `0x1800117a1`
- `ntdll!RtlNtStatusToDosError` at `0x18001180a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011673`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001185f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011673`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001185f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011689`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001186d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001186d`
- `FLTLIB!FilterSendMessage` at `0x180011852`
- `FLTLIB!FilterSendMessage` at `0x180011852`

## pseudocode

```c
int __fastcall RevertSyncRoot(unsigned __int64 hFile)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v3; // rax
  _DWORD *v4; // rbx
  int v5; // edx
  NTSTATUS v6; // edi
  NTSTATUS v7; // ecx
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // ecx
  signed int v11; // eax
  bool v12; // sf
  NTSTATUS v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rax
  signed int v16; // eax
  bool v17; // sf
  __int64 v18; // rcx
  __int64 v19; // rax
  signed int v20; // eax
  bool v21; // sf
  HANDLE v22; // rax
  _DWORD v24[3]; // [rsp+40h] [rbp-C8h] BYREF
  char v25[148]; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD BytesReturned; // [rsp+118h] [rbp+10h] BYREF

  memset_0(v25, 0, 0x8Cu);
  v24[0] = -1879048166;
  BytesReturned = 0;
  v24[1] = -1073741801;
  v24[2] = 0;
  IssueHsmControl(hFile, v24, 0x98u, 0, 0, &BytesReturned, 0);
  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 8u, 0xD8u);
  v4 = v3;
  v5 = v3 == 0 ? 8 : 0;
  if ( !v3 )
    v5 |= 0x80070000;
  if ( v5 >= 0 )
  {
    *(_QWORD *)v3 = 1886219331;
    v3[2] = 200;
    v3[3] = 1507328;
    memset_0(v3 + 4, 0, 0xB8u);
    v6 = -1073741811;
    if ( *((_WORD *)v4 + 7) )
    {
      v8 = (unsigned int)v4[2];
      if ( ((v8 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xD8 )
      {
        v10 = (v8 + 3) & 0xFFFFFFFC;
        v9 = v10;
        v4[2] = v10;
        v4[5] = v10;
        v7 = 0;
        v4[4] = 65543;
        *((_BYTE *)v4 + v9) = 1;
        ++v4[2];
      }
      else
      {
        v7 = -1073741789;
      }
    }
    else
    {
      v7 = -1073741811;
    }
    v11 = RtlNtStatusToDosError(v7);
    v12 = v11 < 0;
    if ( v11 > 0 )
      v12 = 1;
    if ( !v12 )
    {
      if ( *((_WORD *)v4 + 7) > 1u )
      {
        v14 = (unsigned int)v4[2];
        if ( ((v14 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xD8 )
        {
          v15 = ((_DWORD)v14 + 3) & 0xFFFFFFFC;
          v4[2] = v15;
          if ( *((_WORD *)v4 + 12) )
            *((_WORD *)v4 + 6) |= 1u;
          v4[6] = 131080;
          v13 = 0;
          v4[7] = v15;
          *(_WORD *)((char *)v4 + v15) = 3;
          v4[2] += 2;
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
      v17 = v16 < 0;
      if ( v16 > 0 )
        v17 = 1;
      if ( !v17 )
      {
        if ( *((_WORD *)v4 + 7) > 2u )
        {
          v18 = (unsigned int)v4[2];
          if ( ((v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xD8 )
          {
            v19 = ((_DWORD)v18 + 3) & 0xFFFFFFFC;
            v4[2] = v19;
            if ( *((_WORD *)v4 + 16) )
              *((_WORD *)v4 + 6) |= 1u;
            v4[8] = 524299;
            v6 = 0;
            v4[9] = v19;
            *(_QWORD *)((char *)v4 + v19) = hFile;
            v4[2] += 8;
          }
          else
          {
            v6 = -1073741789;
          }
        }
        v20 = RtlNtStatusToDosError(v6);
        v21 = v20 < 0;
        if ( v20 > 0 )
          v21 = 1;
        if ( !v21 )
        {
          v4[1] = 0;
          *((_WORD *)v4 + 6) &= ~2u;
          FilterSendMessage(hPort, v4, 0xD8u, 0, 0, &BytesReturned);
        }
      }
    }
    goto LABEL_33;
  }
  if ( v3 )
  {
LABEL_33:
    v22 = GetProcessHeap();
    LODWORD(v3) = HeapFree(v22, 0, v4);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x1800115f8  mov     [rsp+arg_0], rbx
0x1800115fd  mov     [rsp+arg_10], rbp
0x180011602  push    rsi
0x180011603  push    rdi
0x180011604  push    r12
0x180011606  push    r14
0x180011608  push    r15
0x18001160a  sub     rsp, 0E0h
0x180011611  mov     rbp, rcx
0x180011614  xor     edx, edx; Val
0x180011616  lea     rcx, [rsp+108h+var_BC]; void *
0x18001161b  mov     r8d, 8Ch; Size
0x180011621  call    memset_0
0x180011626  xor     r14d, r14d
0x180011629  mov     [rsp+108h+var_C8], 9000001Ah
0x180011631  lea     rax, [rsp+108h+BytesReturned]
0x180011639  mov     [rsp+108h+var_D8], r14; __int64
0x18001163e  mov     [rsp+108h+lpBytesReturned], rax; lpNumberOfBytesTransferred
0x180011643  lea     rdx, [rsp+108h+var_C8]
0x180011648  xor     r9d, r9d
0x18001164b  mov     [rsp+108h+dwOutBufferSize], r14d; DWORD
0x180011650  mov     r8d, 98h
0x180011656  mov     [rsp+108h+BytesReturned], r14d
0x18001165e  mov     rcx, rbp; hFile
0x180011661  mov     [rsp+108h+var_C4], 0C0000017h
0x180011669  mov     [rsp+108h+var_C0], r14d
0x18001166e  call    IssueHsmControl
0x180011673  call    cs:__imp_GetProcessHeap
0x180011679  lea     r12d, [r14+8]
0x18001167d  mov     r8d, 0D8h; dwBytes
0x180011683  mov     rcx, rax; hHeap
0x180011686  mov     edx, r12d; dwFlags
0x180011689  call    cs:__imp_HeapAlloc
0x18001168f  mov     rcx, rax
0x180011692  mov     rbx, rax
0x180011695  neg     rcx
0x180011698  sbb     edx, edx
0x18001169a  not     edx
0x18001169c  and     edx, r12d
0x18001169f  mov     ecx, edx
0x1800116a1  or      ecx, 80070000h
0x1800116a7  test    rax, rax
0x1800116aa  cmovz   edx, ecx
0x1800116ad  test    edx, edx
0x1800116af  js      loc_18001185A
0x1800116b5  xor     edx, edx; Val
0x1800116b7  mov     qword ptr [rax], 706D6C43h
0x1800116be  mov     r8d, 0B8h; Size
0x1800116c4  mov     dword ptr [rax+8], 0C8h
0x1800116cb  lea     rcx, [rax+10h]; void *
0x1800116cf  mov     dword ptr [rax+0Ch], 170000h
0x1800116d6  call    memset_0
0x1800116db  lea     r15d, [r14+1]
0x1800116df  mov     edi, 0C000000Dh
0x1800116e4  cmp     r14w, [rbx+0Eh]
0x1800116e9  jb      short loc_1800116EF
0x1800116eb  mov     ecx, edi
0x1800116ed  jmp     short loc_18001172C
0x1800116ef  mov     ecx, [rbx+8]
0x1800116f2  lea     rax, [rcx+3]
0x1800116f6  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800116fa  add     rax, r15
0x1800116fd  cmp     rax, 0D8h
0x180011703  jbe     short loc_18001170C
0x180011705  mov     ecx, 0C0000023h
0x18001170a  jmp     short loc_18001172C
0x18001170c  lea     eax, [rcx+3]
0x18001170f  and     eax, 0FFFFFFFCh
0x180011712  mov     ecx, eax
0x180011714  mov     [rbx+8], ecx
0x180011717  mov     [rbx+14h], ecx
0x18001171a  mov     ecx, r14d; Status
0x18001171d  mov     dword ptr [rbx+10h], 10007h
0x180011724  mov     [rax+rbx], r15b
0x180011728  add     [rbx+8], r15d
0x18001172c  call    cs:__imp_RtlNtStatusToDosError
0x180011732  test    eax, eax
0x180011734  jle     short loc_180011740
0x180011736  movzx   eax, ax
0x180011739  or      eax, 80070000h
0x18001173e  test    eax, eax
0x180011740  js      loc_18001185F
0x180011746  mov     esi, 2
0x18001174b  cmp     r15w, [rbx+0Eh]
0x180011750  jb      short loc_180011756
0x180011752  mov     ecx, edi
0x180011754  jmp     short loc_1800117A1
0x180011756  mov     ecx, [rbx+8]
0x180011759  mov     edx, 3
0x18001175e  lea     rax, [rdx+rcx]
0x180011762  and     rax, 0FFFFFFFFFFFFFFFCh
0x180011766  add     rax, rsi
0x180011769  cmp     rax, 0D8h
0x18001176f  jbe     short loc_180011778
0x180011771  mov     ecx, 0C0000023h
0x180011776  jmp     short loc_1800117A1
0x180011778  lea     eax, [rcx+3]
0x18001177b  and     eax, 0FFFFFFFCh
0x18001177e  mov     [rbx+8], eax
0x180011781  cmp     [rbx+18h], r14w
0x180011786  jz      short loc_18001178D
0x180011788  or      [rbx+0Ch], r15w
0x18001178d  mov     dword ptr [rbx+18h], 20008h
0x180011794  mov     ecx, r14d; Status
0x180011797  mov     [rbx+1Ch], eax
0x18001179a  mov     [rax+rbx], dx
0x18001179e  add     [rbx+8], esi
0x1800117a1  call    cs:__imp_RtlNtStatusToDosError
0x1800117a7  test    eax, eax
0x1800117a9  jle     short loc_1800117B5
0x1800117ab  movzx   eax, ax
0x1800117ae  or      eax, 80070000h
0x1800117b3  test    eax, eax
0x1800117b5  js      loc_18001185F
0x1800117bb  cmp     si, [rbx+0Eh]
0x1800117bf  jnb     short loc_180011808
0x1800117c1  mov     ecx, [rbx+8]
0x1800117c4  lea     rax, [rcx+3]
0x1800117c8  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800117cc  add     rax, r12
0x1800117cf  cmp     rax, 0D8h
0x1800117d5  jbe     short loc_1800117DE
0x1800117d7  mov     edi, 0C0000023h
0x1800117dc  jmp     short loc_180011808
0x1800117de  lea     eax, [rcx+3]
0x1800117e1  and     eax, 0FFFFFFFCh
0x1800117e4  mov     [rbx+8], eax
0x1800117e7  cmp     [rbx+20h], r14w
0x1800117ec  jz      short loc_1800117F3
0x1800117ee  or      [rbx+0Ch], r15w
0x1800117f3  mov     dword ptr [rbx+20h], 8000Bh
0x1800117fa  mov     edi, r14d
0x1800117fd  mov     [rbx+24h], eax
0x180011800  mov     [rax+rbx], rbp
0x180011804  add     [rbx+8], r12d
0x180011808  mov     ecx, edi; Status
0x18001180a  call    cs:__imp_RtlNtStatusToDosError
0x180011810  test    eax, eax
0x180011812  jle     short loc_18001181E
0x180011814  movzx   eax, ax
0x180011817  or      eax, 80070000h
0x18001181c  test    eax, eax
0x18001181e  js      short loc_18001185F
0x180011820  mov     eax, 0FFFDh
0x180011825  mov     [rbx+4], r14d
0x180011829  and     [rbx+0Ch], ax
0x18001182d  xor     r9d, r9d; lpOutBuffer
0x180011830  mov     rcx, qword ptr cs:hPort; hPort
0x180011837  lea     rax, [rsp+108h+BytesReturned]
0x18001183f  mov     [rsp+108h+lpBytesReturned], rax; lpBytesReturned
0x180011844  mov     r8d, 0D8h; dwInBufferSize
0x18001184a  mov     rdx, rbx; lpInBuffer
0x18001184d  mov     [rsp+108h+dwOutBufferSize], r14d; dwOutBufferSize
0x180011852  call    cs:__imp_FilterSendMessage
0x180011858  jmp     short loc_18001185F
0x18001185a  test    rbx, rbx
0x18001185d  jz      short loc_180011873
0x18001185f  call    cs:__imp_GetProcessHeap
0x180011865  mov     r8, rbx; lpMem
0x180011868  xor     edx, edx; dwFlags
0x18001186a  mov     rcx, rax; hHeap
0x18001186d  call    cs:__imp_HeapFree
0x180011873  lea     r11, [rsp+108h+var_28]
0x18001187b  mov     rbx, [r11+30h]
0x18001187f  mov     rbp, [r11+40h]
0x180011883  mov     rsp, r11
0x180011886  pop     r15
0x180011888  pop     r14
0x18001188a  pop     r12
0x18001188c  pop     rdi
0x18001188d  pop     rsi
0x18001188e  retn
```
