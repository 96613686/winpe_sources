# AttachFilterToVolume

- ea: `0x1800106c0`
- end: `0x180010950`
- name: `AttachFilterToVolume`
- size: `656`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180004ac0`
- `0x180006060`

## callees

- `0x1800022ee`
- `0x18000446c`
- `0x1800106c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180010702`
- `ntdll!RtlNtStatusToDosError` at `0x1800107d5`
- `ntdll!RtlNtStatusToDosError` at `0x180010846`
- `ntdll!RtlNtStatusToDosError` at `0x1800108b6`
- `ntdll!RtlNtStatusToDosError` at `0x180010702`
- `ntdll!RtlNtStatusToDosError` at `0x1800107d5`
- `ntdll!RtlNtStatusToDosError` at `0x180010846`
- `ntdll!RtlNtStatusToDosError` at `0x1800108b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010722`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010722`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010922`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001073a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001073a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010930`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010917`
- `FLTLIB!FilterSendMessage` at `0x1800108fc`
- `FLTLIB!FilterSendMessage` at `0x1800108fc`

## pseudocode

```c
__int64 __fastcall AttachFilterToVolume(__int64 a1, __int64 a2)
{
  NTSTATUS v2; // eax
  signed int v3; // eax
  int v4; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v6; // rdi
  NTSTATUS v7; // esi
  NTSTATUS v8; // ecx
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // ecx
  signed int v12; // eax
  NTSTATUS v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rax
  signed int v16; // eax
  __int64 v17; // rcx
  HANDLE v18; // rdx
  __int64 v19; // rax
  signed int v20; // eax
  HANDLE v21; // rax
  __int64 dwOutBufferSize; // [rsp+20h] [rbp-68h]
  __int64 v24; // [rsp+30h] [rbp-58h]
  DWORD BytesReturned; // [rsp+98h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp+18h] BYREF

  hObject = (HANDLE)-1LL;
  BytesReturned = 0;
  v2 = CfpCreateFile(a1, a2, 0, 7u, dwOutBufferSize, 0x21u, v24, &hObject);
  v3 = RtlNtStatusToDosError(v2);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
  {
    v6 = 0;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 8u, 0xD8u);
    v4 = v6 == 0 ? 8 : 0;
    if ( !v6 )
      v4 |= 0x80070000;
    if ( v4 >= 0 )
    {
      *(_QWORD *)v6 = 1886219331;
      v6[2] = 200;
      v6[3] = 1507328;
      memset_0(v6 + 4, 0, 0xB8u);
      v7 = -1073741811;
      if ( *((_WORD *)v6 + 7) )
      {
        v9 = (unsigned int)v6[2];
        if ( ((v9 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xD8 )
        {
          v11 = (v9 + 3) & 0xFFFFFFFC;
          v10 = v11;
          v6[2] = v11;
          v6[5] = v11;
          v8 = 0;
          v6[4] = 65543;
          *((_BYTE *)v6 + v10) = 1;
          ++v6[2];
        }
        else
        {
          v8 = -1073741789;
        }
      }
      else
      {
        v8 = -1073741811;
      }
      v12 = RtlNtStatusToDosError(v8);
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( v4 >= 0 )
      {
        if ( *((_WORD *)v6 + 7) > 1u )
        {
          v14 = (unsigned int)v6[2];
          if ( ((v14 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xD8 )
          {
            v15 = ((_DWORD)v14 + 3) & 0xFFFFFFFC;
            v6[2] = v15;
            if ( *((_WORD *)v6 + 12) )
              *((_WORD *)v6 + 6) |= 1u;
            v6[6] = 131080;
            v13 = 0;
            v6[7] = v15;
            *(_WORD *)((char *)v6 + v15) = 1;
            v6[2] += 2;
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
        v4 = v16;
        if ( v16 > 0 )
          v4 = (unsigned __int16)v16 | 0x80070000;
        if ( v4 >= 0 )
        {
          if ( *((_WORD *)v6 + 7) > 2u )
          {
            v17 = (unsigned int)v6[2];
            if ( ((v17 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xD8 )
            {
              v18 = hObject;
              v19 = ((_DWORD)v17 + 3) & 0xFFFFFFFC;
              v6[2] = v19;
              if ( *((_WORD *)v6 + 16) )
                *((_WORD *)v6 + 6) |= 1u;
              v6[8] = 524299;
              v7 = 0;
              v6[9] = v19;
              *(_QWORD *)((char *)v6 + v19) = v18;
              v6[2] += 8;
            }
            else
            {
              v7 = -1073741789;
            }
          }
          v20 = RtlNtStatusToDosError(v7);
          v4 = v20;
          if ( v20 > 0 )
            v4 = (unsigned __int16)v20 | 0x80070000;
          if ( v4 >= 0 )
          {
            v6[1] = 0;
            *((_WORD *)v6 + 6) &= ~2u;
            v4 = FilterSendMessage(hPort, v6, 0xD8u, 0, 0, &BytesReturned);
          }
        }
      }
    }
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v6 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v6);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800106c0  mov     rax, rsp
0x1800106c3  mov     [rax+8], rbx
0x1800106c7  push    rbp
0x1800106c8  push    rsi
0x1800106c9  push    rdi
0x1800106ca  push    r12
0x1800106cc  push    r13
0x1800106ce  push    r14
0x1800106d0  push    r15
0x1800106d2  sub     rsp, 50h
0x1800106d6  xor     ebp, ebp
0x1800106d8  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800106e0  mov     [rax+10h], ebp
0x1800106e3  lea     rax, [rax+18h]
0x1800106e7  mov     [rsp+88h+var_50], rax
0x1800106ec  xor     r8d, r8d
0x1800106ef  mov     dword ptr [rsp+88h+lpBytesReturned], 21h ; '!'
0x1800106f7  lea     r9d, [rbp+7]
0x1800106fb  call    CfpCreateFile
0x180010700  mov     ecx, eax; Status
0x180010702  call    cs:__imp_RtlNtStatusToDosError
0x180010708  mov     ebx, eax
0x18001070a  mov     r12d, 80070000h
0x180010710  test    eax, eax
0x180010712  jle     short loc_18001071A
0x180010714  movzx   ebx, ax
0x180010717  or      ebx, r12d
0x18001071a  test    ebx, ebx
0x18001071c  js      loc_180010906
0x180010722  call    cs:__imp_GetProcessHeap
0x180010728  mov     r13d, 8
0x18001072e  mov     r8d, 0D8h; dwBytes
0x180010734  mov     rcx, rax; hHeap
0x180010737  mov     edx, r13d; dwFlags
0x18001073a  call    cs:__imp_HeapAlloc
0x180010740  mov     rdi, rax
0x180010743  neg     rax
0x180010746  sbb     ebx, ebx
0x180010748  not     ebx
0x18001074a  and     ebx, r13d
0x18001074d  mov     eax, ebx
0x18001074f  or      eax, r12d
0x180010752  test    rdi, rdi
0x180010755  cmovz   ebx, eax
0x180010758  test    ebx, ebx
0x18001075a  js      loc_180010909
0x180010760  xor     edx, edx; Val
0x180010762  mov     qword ptr [rdi], 706D6C43h
0x180010769  mov     r8d, 0B8h; Size
0x18001076f  mov     dword ptr [rdi+8], 0C8h
0x180010776  lea     rcx, [rdi+10h]; void *
0x18001077a  mov     dword ptr [rdi+0Ch], 170000h
0x180010781  call    memset_0
0x180010786  lea     r14d, [r13-7]
0x18001078a  mov     esi, 0C000000Dh
0x18001078f  cmp     bp, [rdi+0Eh]
0x180010793  jb      short loc_180010799
0x180010795  mov     ecx, esi
0x180010797  jmp     short loc_1800107D5
0x180010799  mov     ecx, [rdi+8]
0x18001079c  lea     rax, [rcx+3]
0x1800107a0  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800107a4  add     rax, r14
0x1800107a7  cmp     rax, 0D8h
0x1800107ad  jbe     short loc_1800107B6
0x1800107af  mov     ecx, 0C0000023h
0x1800107b4  jmp     short loc_1800107D5
0x1800107b6  lea     eax, [rcx+3]
0x1800107b9  and     eax, 0FFFFFFFCh
0x1800107bc  mov     ecx, eax
0x1800107be  mov     [rdi+8], ecx
0x1800107c1  mov     [rdi+14h], ecx
0x1800107c4  mov     ecx, ebp; Status
0x1800107c6  mov     dword ptr [rdi+10h], 10007h
0x1800107cd  mov     [rax+rdi], r14b
0x1800107d1  add     [rdi+8], r14d
0x1800107d5  call    cs:__imp_RtlNtStatusToDosError
0x1800107db  mov     ebx, eax
0x1800107dd  test    eax, eax
0x1800107df  jle     short loc_1800107E7
0x1800107e1  movzx   ebx, ax
0x1800107e4  or      ebx, r12d
0x1800107e7  test    ebx, ebx
0x1800107e9  js      loc_180010909
0x1800107ef  mov     r15d, 2
0x1800107f5  cmp     r14w, [rdi+0Eh]
0x1800107fa  jb      short loc_180010800
0x1800107fc  mov     ecx, esi
0x1800107fe  jmp     short loc_180010846
0x180010800  mov     ecx, [rdi+8]
0x180010803  lea     rax, [rcx+3]
0x180010807  and     rax, 0FFFFFFFFFFFFFFFCh
0x18001080b  add     rax, r15
0x18001080e  cmp     rax, 0D8h
0x180010814  jbe     short loc_18001081D
0x180010816  mov     ecx, 0C0000023h
0x18001081b  jmp     short loc_180010846
0x18001081d  lea     eax, [rcx+3]
0x180010820  and     eax, 0FFFFFFFCh
0x180010823  mov     [rdi+8], eax
0x180010826  cmp     [rdi+18h], bp
0x18001082a  jz      short loc_180010831
0x18001082c  or      [rdi+0Ch], r14w
0x180010831  mov     dword ptr [rdi+18h], 20008h
0x180010838  mov     ecx, ebp; Status
0x18001083a  mov     [rdi+1Ch], eax
0x18001083d  mov     [rax+rdi], r14w
0x180010842  add     [rdi+8], r15d
0x180010846  call    cs:__imp_RtlNtStatusToDosError
0x18001084c  mov     ebx, eax
0x18001084e  test    eax, eax
0x180010850  jle     short loc_180010858
0x180010852  movzx   ebx, ax
0x180010855  or      ebx, r12d
0x180010858  test    ebx, ebx
0x18001085a  js      loc_180010909
0x180010860  cmp     r15w, [rdi+0Eh]
0x180010865  jnb     short loc_1800108B4
0x180010867  mov     ecx, [rdi+8]
0x18001086a  lea     rax, [rcx+3]
0x18001086e  and     rax, 0FFFFFFFFFFFFFFFCh
0x180010872  add     rax, r13
0x180010875  cmp     rax, 0D8h
0x18001087b  jbe     short loc_180010884
0x18001087d  mov     esi, 0C0000023h
0x180010882  jmp     short loc_1800108B4
0x180010884  mov     rdx, [rsp+88h+hObject]
0x18001088c  lea     eax, [rcx+3]
0x18001088f  and     eax, 0FFFFFFFCh
0x180010892  mov     [rdi+8], eax
0x180010895  cmp     [rdi+20h], bp
0x180010899  jz      short loc_1800108A0
0x18001089b  or      [rdi+0Ch], r14w
0x1800108a0  mov     dword ptr [rdi+20h], 8000Bh
0x1800108a7  mov     esi, ebp
0x1800108a9  mov     [rdi+24h], eax
0x1800108ac  mov     [rax+rdi], rdx
0x1800108b0  add     [rdi+8], r13d
0x1800108b4  mov     ecx, esi; Status
0x1800108b6  call    cs:__imp_RtlNtStatusToDosError
0x1800108bc  mov     ebx, eax
0x1800108be  test    eax, eax
0x1800108c0  jle     short loc_1800108C8
0x1800108c2  movzx   ebx, ax
0x1800108c5  or      ebx, r12d
0x1800108c8  test    ebx, ebx
0x1800108ca  js      short loc_180010909
0x1800108cc  mov     eax, 0FFFDh
0x1800108d1  mov     [rdi+4], ebp
0x1800108d4  and     [rdi+0Ch], ax
0x1800108d8  xor     r9d, r9d; lpOutBuffer
0x1800108db  mov     rcx, qword ptr cs:hPort; hPort
0x1800108e2  lea     rax, [rsp+88h+BytesReturned]
0x1800108ea  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x1800108ef  mov     r8d, 0D8h; dwInBufferSize
0x1800108f5  mov     rdx, rdi; lpInBuffer
0x1800108f8  mov     dword ptr [rsp+88h+dwOutBufferSize], ebp; dwOutBufferSize
0x1800108fc  call    cs:__imp_FilterSendMessage
0x180010902  mov     ebx, eax
0x180010904  jmp     short loc_180010909
0x180010906  mov     rdi, rbp
0x180010909  mov     rcx, [rsp+88h+hObject]; hObject
0x180010911  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010915  jz      short loc_18001091D
0x180010917  call    cs:__imp_CloseHandle
0x18001091d  test    rdi, rdi
0x180010920  jz      short loc_180010936
0x180010922  call    cs:__imp_GetProcessHeap
0x180010928  mov     r8, rdi; lpMem
0x18001092b  xor     edx, edx; dwFlags
0x18001092d  mov     rcx, rax; hHeap
0x180010930  call    cs:__imp_HeapFree
0x180010936  mov     eax, ebx
0x180010938  mov     rbx, [rsp+88h+arg_0]
0x180010940  add     rsp, 50h
0x180010944  pop     r15
0x180010946  pop     r14
0x180010948  pop     r13
0x18001094a  pop     r12
0x18001094c  pop     rdi
0x18001094d  pop     rsi
0x18001094e  pop     rbp
0x18001094f  retn
```
