# BiConvertNtDeviceToBootEnvironment

- ea: `0x140015cd8`
- end: `0x14001649a`
- name: `BiConvertNtDeviceToBootEnvironment`
- size: `1986`
- prototype: `__int64(__int64, unsigned int, unsigned int, ...)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015cd8`
- `0x1400164a0`
- `0x140016784`
- `0x140019038`

## callees

- `0x1400133e4`
- `0x140015cd8`
- `0x1400164a0`
- `0x140016784`
- `0x140017800`
- `0x140017ee4`
- `0x1400265e2`
- `0x1400265fa`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1400163bc`
- `msvcrt!wcscpy_s` at `0x1400163bc`
- `msvcrt!strcpy_s` at `0x1400161d6`
- `msvcrt!strcpy_s` at `0x1400161d6`
- `ntdll!RtlAllocateHeap` at `0x140015d68`
- `ntdll!RtlAllocateHeap` at `0x140015dee`
- `ntdll!RtlAllocateHeap` at `0x140015e93`
- `ntdll!RtlAllocateHeap` at `0x140015f70`
- `ntdll!RtlAllocateHeap` at `0x140015fc6`
- `ntdll!RtlAllocateHeap` at `0x140016048`
- `ntdll!RtlAllocateHeap` at `0x1400160a3`
- `ntdll!RtlAllocateHeap` at `0x140016123`
- `ntdll!RtlAllocateHeap` at `0x140016196`
- `ntdll!RtlAllocateHeap` at `0x140016352`
- `ntdll!RtlAllocateHeap` at `0x140015d68`
- `ntdll!RtlAllocateHeap` at `0x140015dee`
- `ntdll!RtlAllocateHeap` at `0x140015e93`
- `ntdll!RtlAllocateHeap` at `0x140015f70`
- `ntdll!RtlAllocateHeap` at `0x140015fc6`
- `ntdll!RtlAllocateHeap` at `0x140016048`
- `ntdll!RtlAllocateHeap` at `0x1400160a3`
- `ntdll!RtlAllocateHeap` at `0x140016123`
- `ntdll!RtlAllocateHeap` at `0x140016196`
- `ntdll!RtlAllocateHeap` at `0x140016352`
- `ntdll!RtlFreeHeap` at `0x140015eb3`
- `ntdll!RtlFreeHeap` at `0x140015f01`
- `ntdll!RtlFreeHeap` at `0x140016294`
- `ntdll!RtlFreeHeap` at `0x140016476`
- `ntdll!RtlFreeHeap` at `0x140015eb3`
- `ntdll!RtlFreeHeap` at `0x140015f01`
- `ntdll!RtlFreeHeap` at `0x140016294`
- `ntdll!RtlFreeHeap` at `0x140016476`

## pseudocode

```c
__int64 BiConvertNtDeviceToBootEnvironment(__int64 a1, unsigned int a2, unsigned int a3, ...)
{
  unsigned int v3; // eax
  _QWORD *v4; // r12
  char v5; // r14
  char *v7; // rdi
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  char *v12; // rax
  int PartitionDevice; // ebx
  __int64 v14; // rax
  unsigned int *v15; // rbx
  unsigned int v16; // esi
  char *v17; // rax
  __int64 v18; // rax
  unsigned int v19; // esi
  char *v20; // rax
  char *Heap; // rax
  char *v22; // rax
  __int128 v23; // xmm0
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  char *v28; // rax
  char *v29; // rax
  char *v30; // rax
  __int64 v31; // rbx
  char *v32; // rax
  __int64 v33; // rax
  int v34; // r8d
  unsigned int v35; // r13d
  unsigned int v36; // ebx
  _DWORD *v37; // r15
  __int64 v38; // rdx
  const WCHAR *v39; // rcx
  unsigned int v40; // eax
  void *PartitionVhdFilePath; // rax
  unsigned int v42; // r15d
  unsigned int v43; // r14d
  __int64 v44; // rbx
  __int64 v45; // rax
  char *v46; // rax
  int v47; // eax
  __int64 v48; // rdx
  char *v49; // r9
  int v50; // eax
  __int64 result; // rax
  PVOID P; // [rsp+30h] [rbp-10h] BYREF
  char *v53; // [rsp+38h] [rbp-8h]
  void *Src; // [rsp+98h] [rbp+58h] BYREF
  va_list Srca; // [rsp+98h] [rbp+58h]
  va_list va1; // [rsp+A0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(Srca, a3);
  Src = va_arg(va1, void *);
  v3 = *(_DWORD *)a1;
  v4 = Src;
  P = 0;
  v5 = a3;
  v53 = 0;
  v7 = 0;
  if ( v3 <= 7 )
  {
    if ( v3 != 7 )
    {
      v8 = v3 - 1;
      if ( !v8 )
      {
        if ( a2 >= 0x14 )
        {
          Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
          v7 = Heap;
          if ( Heap )
          {
            memset_0(Heap, 0, 0x48u);
            *(_DWORD *)v7 = 5;
            *((_DWORD *)v7 + 2) = 72;
            goto LABEL_34;
          }
          goto LABEL_32;
        }
LABEL_12:
        PartitionDevice = -1073741811;
        goto LABEL_112;
      }
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( v11 == 1 && a2 >= 0x20 && *(_DWORD *)(a1 + 28) <= 0x100000u )
            {
              v12 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(a1 + 28));
              v7 = v12;
              if ( v12 )
              {
                memcpy_0(v12, (const void *)(a1 + 20), *(unsigned int *)(a1 + 28));
LABEL_34:
                PartitionDevice = 0;
                goto LABEL_110;
              }
LABEL_32:
              PartitionDevice = -1073741670;
              goto LABEL_110;
            }
            goto LABEL_12;
          }
          if ( a2 < 0x2E )
            goto LABEL_12;
          v14 = *(unsigned int *)(a1 + 20);
          if ( !(_DWORD)v14 )
            goto LABEL_12;
          Src = 0;
          PartitionDevice = BiConvertNtFilePathToBootEnvironment(
                              v14 + a1,
                              a2 - (unsigned int)v14,
                              a1 + 24,
                              a3,
                              (void **)Srca);
          if ( PartitionDevice < 0 )
            goto LABEL_110;
          v15 = (unsigned int *)Src;
          v16 = *((_DWORD *)Src + 1) + 40;
          v17 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
          v7 = v17;
          if ( v17 )
          {
            memset_0(v17, 0, v16);
            *(_DWORD *)v7 = 0;
            *((_DWORD *)v7 + 1) = 1;
            *((_DWORD *)v7 + 2) = v16;
            *((_DWORD *)v7 + 4) = 3;
            memcpy_0(v7 + 40, v15, v15[1]);
LABEL_24:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
            goto LABEL_34;
          }
        }
        else
        {
          if ( a2 < 0x2E )
            goto LABEL_12;
          v18 = *(unsigned int *)(a1 + 20);
          if ( !(_DWORD)v18 )
            goto LABEL_12;
          Src = 0;
          PartitionDevice = BiConvertNtFilePathToBootEnvironment(
                              v18 + a1,
                              a2 - (unsigned int)v18,
                              a1 + 24,
                              a3,
                              (void **)Srca);
          if ( PartitionDevice < 0 )
            goto LABEL_110;
          v15 = (unsigned int *)Src;
          v19 = *((_DWORD *)Src + 1) + 20;
          v20 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
          v7 = v20;
          if ( v20 )
          {
            memset_0(v20, 0, v19);
            *(_DWORD *)v7 = 0;
            *((_DWORD *)v7 + 2) = v19;
            *((_DWORD *)v7 + 4) = 5;
            memcpy_0(v7 + 20, v15, v15[1]);
            *((_DWORD *)v7 + 1) = v15[4] & 0x20;
            goto LABEL_24;
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        goto LABEL_32;
      }
      if ( a2 < 0x16 )
        goto LABEL_12;
      if ( !(unsigned __int8)BiIsVolumePartitionInformationRetained((PCWSTR)(a1 + 20)) )
      {
        PartitionDevice = -1073741637;
        goto LABEL_110;
      }
      v7 = v53;
      PartitionDevice = BiCreatePartitionDevice((PCWSTR)(a1 + 20));
      if ( PartitionDevice >= 0 )
        goto LABEL_34;
      goto LABEL_110;
    }
    if ( a2 < 0x24 )
      goto LABEL_12;
    v22 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
    v7 = v22;
    if ( !v22 )
      goto LABEL_32;
    memset_0(v22, 0, 0x48u);
    *(_DWORD *)v7 = 7;
    *((_DWORD *)v7 + 2) = 72;
    *((_OWORD *)v7 + 1) = VmbFsInterfaceTypeGuid;
    v23 = *(_OWORD *)(a1 + 20);
LABEL_38:
    *((_OWORD *)v7 + 2) = v23;
    goto LABEL_34;
  }
  v24 = v3 - 8;
  if ( v24 )
  {
    v25 = v24 - 1;
    if ( !v25 )
    {
      if ( a2 >= 0x15 )
      {
        v31 = -1;
        do
          ++v31;
        while ( *(_BYTE *)(a1 + v31 + 20) );
        v32 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v31 + 21));
        v7 = v32;
        if ( v32 )
        {
          memset_0(v32, 0, (unsigned int)(v31 + 21));
          *(_DWORD *)v7 = 9;
          *((_DWORD *)v7 + 1) = 32;
          *((_DWORD *)v7 + 2) = v31 + 21;
          *((_DWORD *)v7 + 4) = v31 + 1;
          strcpy_s(v7 + 20, (unsigned int)(v31 + 1), (const char *)(a1 + 20));
          goto LABEL_34;
        }
        goto LABEL_32;
      }
      goto LABEL_12;
    }
    v26 = v25 - 1;
    if ( !v26 )
    {
      if ( a2 >= 0x28
        && *(_QWORD *)(a1 + 20) == CompositeDeviceSignature
        && *(_QWORD *)(a1 + 28) == 0x526C65784171869ELL )
      {
        v30 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
        v7 = v30;
        if ( v30 )
        {
          memset_0(v30, 0, 0x48u);
          *(_DWORD *)v7 = 10;
          *((_DWORD *)v7 + 2) = 72;
          *((_DWORD *)v7 + 1) = 1;
          *((_OWORD *)v7 + 1) = *(_OWORD *)(a1 + 20);
          *((_DWORD *)v7 + 8) = *(_DWORD *)(a1 + 36);
          goto LABEL_34;
        }
        goto LABEL_32;
      }
      goto LABEL_12;
    }
    v27 = v26 - 1;
    if ( v27 )
    {
      if ( v27 == 2 && a2 >= 0x18 )
      {
        v28 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
        v7 = v28;
        if ( v28 )
        {
          memset_0(v28, 0, 0x48u);
          *(_DWORD *)v7 = 0;
          *((_DWORD *)v7 + 2) = 72;
          *((_DWORD *)v7 + 4) = 0;
          *((_DWORD *)v7 + 5) = 2;
          *((_DWORD *)v7 + 6) = *(_DWORD *)(a1 + 20);
          goto LABEL_34;
        }
        goto LABEL_32;
      }
      goto LABEL_12;
    }
    if ( a2 < 0x28 )
      goto LABEL_12;
    v29 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
    v7 = v29;
    if ( !v29 )
      goto LABEL_32;
    memset_0(v29, 0, 0x48u);
    *(_DWORD *)v7 = 11;
    *((_DWORD *)v7 + 2) = 72;
    *((_DWORD *)v7 + 1) = 1;
    *((_DWORD *)v7 + 4) = *(_DWORD *)(a1 + 20);
    v23 = *(_OWORD *)(a1 + 24);
    goto LABEL_38;
  }
  if ( a2 < 0x22 )
    goto LABEL_12;
  v33 = *(unsigned int *)(a1 + 24);
  if ( a2 <= (unsigned int)v33 )
    goto LABEL_12;
  v34 = *(_DWORD *)(a1 + 20);
  if ( (v34 & 0xFFFFFFFC) != 0 || v34 == 2 )
  {
    BiLogMessage(4, L"BiConvertNtDeviceToBootEnvironment: Invalid LOCATE type %d");
    PartitionDevice = -1073741811;
    goto LABEL_110;
  }
  v35 = 30;
  if ( !(_DWORD)v33 )
  {
    v42 = 0;
    v43 = 30;
    goto LABEL_87;
  }
  v36 = a2 - v33;
  v37 = (_DWORD *)(a1 + v33);
  if ( *(_DWORD *)(a1 + v33) == 3 && v36 >= 0x2E )
    goto LABEL_115;
  if ( *v37 != 12 || v36 < 0x18 )
    goto LABEL_12;
  if ( v37[5] )
  {
LABEL_115:
    v38 = (unsigned int)v37[5];
    v39 = (const WCHAR *)((char *)v37 + v38);
    if ( (_DWORD *)((char *)v37 + v38) )
    {
      v40 = v36 - v38;
      if ( *(_DWORD *)v39 == 2 )
      {
        if ( v40 < 0x16 )
          goto LABEL_12;
        if ( (v5 & 0x40) == 0 )
        {
          PartitionVhdFilePath = (void *)BiGetPartitionVhdFilePath(v39 + 10);
          if ( PartitionVhdFilePath )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, PartitionVhdFilePath);
            PartitionDevice = -1073741637;
            goto LABEL_110;
          }
        }
      }
      else if ( *(_DWORD *)v39 != 6
             && (*(_DWORD *)v39 != 8 || v40 < 0x22)
             && (*(_DWORD *)v39 != 1 || v40 < 0x14)
             && (*(_DWORD *)v39 != 9 || v40 < 0x15) )
      {
        goto LABEL_12;
      }
    }
  }
  PartitionDevice = BiConvertNtDeviceToBootEnvironment(v37, v36, v5 & 0x40, &P);
  if ( PartitionDevice >= 0 )
  {
    v42 = *v37 != 12 ? 0x28 : 0;
    v43 = v42 + *((_DWORD *)P + 2) + 30;
LABEL_87:
    v44 = -1;
    if ( *(_DWORD *)(a1 + 20) == 1 )
    {
      v45 = -1;
      do
        ++v45;
      while ( *(_WORD *)(a1 + 2 * v45 + 32) );
      v43 += 2 * v45;
    }
    else if ( *(_DWORD *)(a1 + 20) == 3 )
    {
      v43 += 14;
    }
    v46 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v43);
    v7 = v46;
    if ( v46 )
    {
      memset_0(v46, 0, v43);
      *(_DWORD *)v7 = 8;
      *((_DWORD *)v7 + 2) = v43;
      v47 = *(_DWORD *)(a1 + 20);
      if ( v47 )
      {
        if ( v47 == 1 )
        {
          *((_DWORD *)v7 + 4) = 1;
          v48 = -1;
          do
            ++v48;
          while ( *(_WORD *)(a1 + 2 * v48 + 32) );
          wcscpy_s((wchar_t *)v7 + 14, v48 + 1, (const wchar_t *)(a1 + 32));
          do
            ++v44;
          while ( *(_WORD *)(a1 + 2 * v44 + 32) );
          v35 = 2 * v44 + 30;
        }
        else
        {
          *((_DWORD *)v7 + 4) = 2;
          v35 = 44;
          *(_OWORD *)(v7 + 28) = *(_OWORD *)(a1 + 32);
        }
      }
      else
      {
        *((_DWORD *)v7 + 4) = 0;
        *((_DWORD *)v7 + 5) = *(_DWORD *)(a1 + 28);
      }
      if ( P )
      {
        v49 = &v7[v35];
        if ( v42 )
        {
          *(_DWORD *)v49 = 0;
          v50 = *((_DWORD *)P + 2);
          *((_DWORD *)v49 + 4) = 6;
          *((_DWORD *)v49 + 2) = v42 + v50;
        }
        memcpy_0(&v49[v42], P, *((unsigned int *)P + 2));
        *((_DWORD *)v7 + 6) = v35;
        *((_DWORD *)v7 + 1) |= *((_DWORD *)P + 1) & 0x20;
      }
      v4 = Src;
      PartitionDevice = 0;
    }
    else
    {
      v4 = Src;
      PartitionDevice = -1073741670;
    }
  }
LABEL_110:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
LABEL_112:
  result = (unsigned int)PartitionDevice;
  *v4 = v7;
  return result;
}

```

## disassembly

```asm
0x140015cd8  mov     [rsp-38h+arg_8], rbx
0x140015cdd  mov     [rsp-38h+Src], r9
0x140015ce2  push    rbp
0x140015ce3  push    rsi
0x140015ce4  push    rdi
0x140015ce5  push    r12
0x140015ce7  push    r13
0x140015ce9  push    r14
0x140015ceb  push    r15
0x140015ced  mov     rbp, rsp
0x140015cf0  sub     rsp, 40h
0x140015cf4  mov     eax, [rcx]
0x140015cf6  xor     r13d, r13d
0x140015cf9  mov     [rbp+arg_0], r13d
0x140015cfd  mov     r12, r9
0x140015d00  mov     [rbp+P], r13
0x140015d04  mov     r14d, r8d
0x140015d07  mov     [rbp+var_8], r13
0x140015d0b  mov     ebx, edx
0x140015d0d  mov     rsi, rcx
0x140015d10  mov     edi, r13d
0x140015d13  cmp     eax, 7
0x140015d16  ja      loc_140016001
0x140015d1c  jz      loc_140015FA6
0x140015d22  sub     eax, 1
0x140015d25  jz      loc_140015F50
0x140015d2b  sub     eax, 1
0x140015d2e  jz      loc_140015F0C
0x140015d34  sub     eax, 1
0x140015d37  jz      loc_140015E36
0x140015d3d  sub     eax, 1
0x140015d40  jz      short loc_140015D99
0x140015d42  cmp     eax, 1
0x140015d45  jnz     short loc_140015D8F
0x140015d47  cmp     edx, 20h ; ' '
0x140015d4a  jb      short loc_140015D8F
0x140015d4c  cmp     dword ptr [rcx+1Ch], 100000h
0x140015d53  ja      short loc_140015D8F
0x140015d55  mov     r8d, [rcx+1Ch]; Size
0x140015d59  xor     edx, edx; Flags
0x140015d5b  mov     rcx, gs:60h
0x140015d64  mov     rcx, [rcx+30h]; HeapHandle
0x140015d68  call    cs:__imp_RtlAllocateHeap
0x140015d6e  mov     rdi, rax
0x140015d71  test    rax, rax
0x140015d74  jz      loc_140015F7E
0x140015d7a  mov     r8d, [rsi+1Ch]; Size
0x140015d7e  lea     rdx, [rsi+14h]; Src
0x140015d82  mov     rcx, rax; void *
0x140015d85  call    memcpy_0
0x140015d8a  jmp     loc_140015F9E
0x140015d8f  mov     ebx, 0C000000Dh
0x140015d94  jmp     loc_14001647C
0x140015d99  cmp     ebx, 2Eh ; '.'
0x140015d9c  jb      short loc_140015D8F
0x140015d9e  mov     eax, [rcx+14h]
0x140015da1  test    eax, eax
0x140015da3  jz      short loc_140015D8F
0x140015da5  sub     ebx, eax
0x140015da7  mov     [rbp+Src], r13
0x140015dab  lea     r8, [rcx+18h]
0x140015daf  mov     r9d, r14d
0x140015db2  add     rcx, rax
0x140015db5  mov     edx, ebx
0x140015db7  lea     rax, [rbp+Src]
0x140015dbb  mov     [rsp+40h+var_20], rax
0x140015dc0  call    BiConvertNtFilePathToBootEnvironment
0x140015dc5  mov     ebx, eax
0x140015dc7  test    eax, eax
0x140015dc9  js      loc_14001645D
0x140015dcf  mov     rcx, gs:60h
0x140015dd8  xor     edx, edx; Flags
0x140015dda  mov     rbx, [rbp+Src]
0x140015dde  mov     rcx, [rcx+30h]; HeapHandle
0x140015de2  mov     esi, [rbx+4]
0x140015de5  add     esi, 28h ; '('
0x140015de8  mov     r8d, esi; Size
0x140015deb  mov     r14d, esi
0x140015dee  call    cs:__imp_RtlAllocateHeap
0x140015df4  xor     edx, edx; Val
0x140015df6  mov     rdi, rax
0x140015df9  test    rax, rax
0x140015dfc  jz      loc_140015EA3
0x140015e02  mov     r8d, r14d; Size
0x140015e05  mov     rcx, rax; void *
0x140015e08  call    memset_0
0x140015e0d  mov     [rdi], r13d
0x140015e10  lea     rcx, [rdi+28h]; void *
0x140015e14  mov     dword ptr [rdi+4], 1
0x140015e1b  mov     rdx, rbx; Src
0x140015e1e  mov     [rdi+8], esi
0x140015e21  mov     dword ptr [rdi+10h], 3
0x140015e28  mov     r8d, [rbx+4]; Size
0x140015e2c  call    memcpy_0
0x140015e31  jmp     loc_140015EEF
0x140015e36  cmp     ebx, 2Eh ; '.'
0x140015e39  jb      loc_140015D8F
0x140015e3f  mov     eax, [rcx+14h]
0x140015e42  test    eax, eax
0x140015e44  jz      loc_140015D8F
0x140015e4a  sub     ebx, eax
0x140015e4c  mov     [rbp+Src], r13
0x140015e50  lea     r8, [rcx+18h]
0x140015e54  mov     r9d, r14d
0x140015e57  add     rcx, rax
0x140015e5a  mov     edx, ebx
0x140015e5c  lea     rax, [rbp+Src]
0x140015e60  mov     [rsp+40h+var_20], rax
0x140015e65  call    BiConvertNtFilePathToBootEnvironment
0x140015e6a  mov     ebx, eax
0x140015e6c  test    eax, eax
0x140015e6e  js      loc_14001645D
0x140015e74  mov     rcx, gs:60h
0x140015e7d  xor     edx, edx; Flags
0x140015e7f  mov     rbx, [rbp+Src]
0x140015e83  mov     rcx, [rcx+30h]; HeapHandle
0x140015e87  mov     esi, [rbx+4]
0x140015e8a  add     esi, 14h
0x140015e8d  mov     r8d, esi; Size
0x140015e90  mov     r14d, esi
0x140015e93  call    cs:__imp_RtlAllocateHeap
0x140015e99  xor     edx, edx; Val
0x140015e9b  mov     rdi, rax
0x140015e9e  test    rax, rax
0x140015ea1  jnz     short loc_140015EBE
0x140015ea3  mov     rcx, gs:60h
0x140015eac  mov     r8, rbx; P
0x140015eaf  mov     rcx, [rcx+30h]; HeapHandle
0x140015eb3  call    cs:__imp_RtlFreeHeap
0x140015eb9  jmp     loc_140015F7E
0x140015ebe  mov     r8, r14; Size
0x140015ec1  mov     rcx, rdi; void *
0x140015ec4  call    memset_0
0x140015ec9  mov     [rdi], r13d
0x140015ecc  lea     rcx, [rdi+14h]; void *
0x140015ed0  mov     [rdi+8], esi
0x140015ed3  mov     rdx, rbx; Src
0x140015ed6  mov     dword ptr [rdi+10h], 5
0x140015edd  mov     r8d, [rbx+4]; Size
0x140015ee1  call    memcpy_0
0x140015ee6  mov     eax, [rbx+10h]
0x140015ee9  and     eax, 20h
0x140015eec  mov     [rdi+4], eax
0x140015eef  mov     rcx, gs:60h
0x140015ef8  mov     r8, rbx; P
0x140015efb  xor     edx, edx; Flags
0x140015efd  mov     rcx, [rcx+30h]; HeapHandle
0x140015f01  call    cs:__imp_RtlFreeHeap
0x140015f07  jmp     loc_140015F9E
0x140015f0c  cmp     ebx, 16h
0x140015f0f  jb      loc_140015D8F
0x140015f15  add     rcx, 14h; SourceString
0x140015f19  call    BiIsVolumePartitionInformationRetained
0x140015f1e  test    al, al
0x140015f20  jnz     short loc_140015F2C
0x140015f22  mov     ebx, 0C00000BBh
0x140015f27  jmp     loc_14001645D
0x140015f2c  lea     r9, [rbp+arg_0]
0x140015f30  mov     edx, r14d
0x140015f33  lea     r8, [rbp+var_8]
0x140015f37  lea     rcx, [rsi+14h]; SourceString
0x140015f3b  call    BiCreatePartitionDevice
0x140015f40  mov     rdi, [rbp+var_8]
0x140015f44  mov     ebx, eax
0x140015f46  test    eax, eax
0x140015f48  js      loc_14001645D
0x140015f4e  jmp     short loc_140015F9E
0x140015f50  cmp     ebx, 14h
0x140015f53  jb      loc_140015D8F
0x140015f59  mov     rcx, gs:60h
0x140015f62  mov     ebx, 48h ; 'H'
0x140015f67  mov     r8d, ebx; Size
0x140015f6a  xor     edx, edx; Flags
0x140015f6c  mov     rcx, [rcx+30h]; HeapHandle
0x140015f70  call    cs:__imp_RtlAllocateHeap
0x140015f76  mov     rdi, rax
0x140015f79  test    rax, rax
0x140015f7c  jnz     short loc_140015F88
0x140015f7e  mov     ebx, 0C000009Ah
0x140015f83  jmp     loc_14001645D
0x140015f88  mov     r8, rbx; Size
0x140015f8b  xor     edx, edx; Val
0x140015f8d  mov     rcx, rdi; void *
0x140015f90  call    memset_0
0x140015f95  mov     dword ptr [rdi], 5
0x140015f9b  mov     [rdi+8], ebx
0x140015f9e  mov     ebx, r13d
0x140015fa1  jmp     loc_14001645D
0x140015fa6  cmp     ebx, 24h ; '$'
0x140015fa9  jb      loc_140015D8F
0x140015faf  mov     rcx, gs:60h
0x140015fb8  mov     ebx, 48h ; 'H'
0x140015fbd  mov     r8d, ebx; Size
0x140015fc0  xor     edx, edx; Flags
0x140015fc2  mov     rcx, [rcx+30h]; HeapHandle
0x140015fc6  call    cs:__imp_RtlAllocateHeap
0x140015fcc  mov     rdi, rax
0x140015fcf  test    rax, rax
0x140015fd2  jz      short loc_140015F7E
0x140015fd4  mov     r8d, ebx; Size
0x140015fd7  xor     edx, edx; Val
0x140015fd9  mov     rcx, rax; void *
0x140015fdc  call    memset_0
0x140015fe1  mov     dword ptr [rdi], 7
0x140015fe7  mov     [rdi+8], ebx
0x140015fea  movups  xmm0, cs:VmbFsInterfaceTypeGuid
0x140015ff1  movdqu  xmmword ptr [rdi+10h], xmm0
0x140015ff6  movups  xmm0, xmmword ptr [rsi+14h]
0x140015ffa  movdqu  xmmword ptr [rdi+20h], xmm0
0x140015fff  jmp     short loc_140015F9E
0x140016001  sub     eax, 8
0x140016004  jz      loc_1400161E1
0x14001600a  sub     eax, 1
0x14001600d  jz      loc_140016166
0x140016013  sub     eax, 1
0x140016016  jz      loc_1400160E1
0x14001601c  sub     eax, 1
0x14001601f  jz      short loc_140016083
0x140016021  cmp     eax, 2
0x140016024  jnz     loc_140015D8F
0x14001602a  cmp     ebx, 18h
0x14001602d  jb      loc_140015D8F
0x140016033  mov     rcx, gs:60h
0x14001603c  lea     ebx, [rax+46h]
0x14001603f  mov     r8d, ebx; Size
0x140016042  xor     edx, edx; Flags
0x140016044  mov     rcx, [rcx+30h]; HeapHandle
0x140016048  call    cs:__imp_RtlAllocateHeap
0x14001604e  mov     rdi, rax
0x140016051  test    rax, rax
0x140016054  jz      loc_140015F7E
0x14001605a  mov     r8d, ebx; Size
0x14001605d  xor     edx, edx; Val
0x14001605f  mov     rcx, rax; void *
0x140016062  call    memset_0
0x140016067  mov     [rdi], r13d
0x14001606a  mov     [rdi+8], ebx
0x14001606d  mov     [rdi+10h], r13d
0x140016071  mov     dword ptr [rdi+14h], 2
0x140016078  mov     eax, [rsi+14h]
0x14001607b  mov     [rdi+18h], eax
0x14001607e  jmp     loc_140015F9E
0x140016083  cmp     ebx, 28h ; '('
0x140016086  jb      loc_140015D8F
0x14001608c  mov     rcx, gs:60h
0x140016095  mov     ebx, 48h ; 'H'
0x14001609a  mov     r8d, ebx; Size
0x14001609d  xor     edx, edx; Flags
0x14001609f  mov     rcx, [rcx+30h]; HeapHandle
0x1400160a3  call    cs:__imp_RtlAllocateHeap
0x1400160a9  mov     rdi, rax
0x1400160ac  test    rax, rax
0x1400160af  jz      loc_140015F7E
0x1400160b5  mov     r8d, ebx; Size
0x1400160b8  xor     edx, edx; Val
0x1400160ba  mov     rcx, rax; void *
0x1400160bd  call    memset_0
0x1400160c2  mov     dword ptr [rdi], 0Bh
0x1400160c8  mov     [rdi+8], ebx
0x1400160cb  mov     dword ptr [rdi+4], 1
0x1400160d2  mov     eax, [rsi+14h]
0x1400160d5  mov     [rdi+10h], eax
0x1400160d8  movups  xmm0, xmmword ptr [rsi+18h]
0x1400160dc  jmp     loc_140015FFA
0x1400160e1  cmp     ebx, 28h ; '('
0x1400160e4  jb      loc_140015D8F
0x1400160ea  mov     rax, [rcx+14h]
0x1400160ee  cmp     rax, cs:CompositeDeviceSignature
0x1400160f5  jnz     loc_140015D8F
0x1400160fb  mov     rax, [rcx+1Ch]
0x1400160ff  cmp     rax, cs:qword_140035310
0x140016106  jnz     loc_140015D8F
0x14001610c  mov     rcx, gs:60h
0x140016115  mov     ebx, 48h ; 'H'
0x14001611a  mov     r8d, ebx; Size
0x14001611d  xor     edx, edx; Flags
0x14001611f  mov     rcx, [rcx+30h]; HeapHandle
0x140016123  call    cs:__imp_RtlAllocateHeap
0x140016129  mov     rdi, rax
0x14001612c  test    rax, rax
0x14001612f  jz      loc_140015F7E
0x140016135  mov     r8d, ebx; Size
0x140016138  xor     edx, edx; Val
0x14001613a  mov     rcx, rax; void *
0x14001613d  call    memset_0
0x140016142  mov     dword ptr [rdi], 0Ah
0x140016148  mov     [rdi+8], ebx
0x14001614b  mov     dword ptr [rdi+4], 1
0x140016152  movups  xmm0, xmmword ptr [rsi+14h]
0x140016156  movdqu  xmmword ptr [rdi+10h], xmm0
0x14001615b  mov     eax, [rsi+24h]
0x14001615e  mov     [rdi+20h], eax
0x140016161  jmp     loc_140015F9E
0x140016166  cmp     ebx, 15h
0x140016169  jb      loc_140015D8F
0x14001616f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140016173  inc     rbx
0x140016176  cmp     [rcx+rbx+14h], r13b
0x14001617b  jnz     short loc_140016173
0x14001617d  mov     rcx, gs:60h
  ... truncated ...
```
