# WriteProcessMemory

- ea: `0x1800e23d0`
- end: `0x1800e26e7`
- name: `WriteProcessMemory`
- size: `791`
- prototype: `BOOL __stdcall(HANDLE hProcess, LPVOID lpBaseAddress, LPCVOID lpBuffer, SIZE_T nSize, SIZE_T *lpNumberOfBytesWritten)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007de08`

## callees

- `0x1800134a0`
- `0x1800e23d0`

## import_xrefs

- `ntdll!NtClose` at `0x1800e26dc`
- `ntdll!NtClose` at `0x1800e26dc`
- `ntdll!NtQueryVirtualMemory` at `0x1800e2480`
- `ntdll!NtQueryVirtualMemory` at `0x1800e2480`
- `ntdll!NtUnmapViewOfSection` at `0x1800e26d2`
- `ntdll!NtUnmapViewOfSection` at `0x1800e26d2`
- `ntdll!RtlOpenCrossProcessEmulatorWorkConnection` at `0x1800e2449`
- `ntdll!RtlOpenCrossProcessEmulatorWorkConnection` at `0x1800e2449`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e2569`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e2644`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e2664`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e268e`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e26ae`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e2569`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e2644`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e2664`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e268e`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e26ae`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e257e`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e2659`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e2679`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e26a0`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e26c3`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e257e`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e2659`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e2679`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e26a0`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e26c3`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x180194397`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801943db`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x180194413`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x180194454`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x180194498`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x180194397`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801943db`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x180194413`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x180194454`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x180194498`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801943ad`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801943f1`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x180194429`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x18019446a`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801944ae`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801943ad`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801943f1`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x180194429`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x18019446a`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801944ae`
- `ntdll!NtProtectVirtualMemory` at `0x1800e2557`
- `ntdll!NtProtectVirtualMemory` at `0x1800e2606`
- `ntdll!NtProtectVirtualMemory` at `0x1800e2557`
- `ntdll!NtProtectVirtualMemory` at `0x1800e2606`
- `ntdll!NtWriteVirtualMemory` at `0x1800e24b7`
- `ntdll!NtWriteVirtualMemory` at `0x1800e24b7`

## pseudocode

```c
BOOL __stdcall WriteProcessMemory(
        HANDLE hProcess,
        LPVOID lpBaseAddress,
        LPCVOID lpBuffer,
        SIZE_T nSize,
        SIZE_T *lpNumberOfBytesWritten)
{
  PVOID v7; // rdi
  char *v8; // rsi
  NTSTATUS v9; // ebx
  char v10; // r15
  ULONG v12; // r14d
  __int64 v13; // rax
  int v14; // eax
  ULONG v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // [rsp+38h] [rbp-51h] BYREF
  SIZE_T NumberOfBytesToProtect; // [rsp+40h] [rbp-49h] BYREF
  PVOID v22; // [rsp+48h] [rbp-41h] BYREF
  ULONG OldAccessProtection; // [rsp+50h] [rbp-39h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-31h] BYREF
  ULONG_PTR NumberOfBytesWritten; // [rsp+60h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-21h] BYREF
  __int128 VirtualMemoryInformation; // [rsp+70h] [rbp-19h] BYREF
  __int128 v28; // [rsp+80h] [rbp-9h]
  __int128 v29; // [rsp+90h] [rbp+7h]

  OldAccessProtection = 0;
  BaseAddress = 0;
  NumberOfBytesToProtect = 0;
  NumberOfBytesWritten = 0;
  VirtualMemoryInformation = 0;
  v20 = 0;
  v28 = 0;
  Handle = 0;
  v29 = 0;
  v22 = 0;
  RtlOpenCrossProcessEmulatorWorkConnection(hProcess, &Handle, &v22);
  v7 = v22;
  if ( v22 )
    v8 = (char *)v22 + 8;
  else
    v8 = 0;
  v9 = NtQueryVirtualMemory(hProcess, lpBaseAddress, (MEMORY_INFORMATION_CLASS)8, &VirtualMemoryInformation, 0x30u, 0);
  if ( v9 < 0 )
  {
LABEL_10:
    if ( v22 )
    {
      NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v22);
      NtClose(Handle);
    }
    goto LABEL_12;
  }
  v10 = 0;
  if ( (BYTE4(v29) & 0xCC) != 0 )
    goto LABEL_5;
  if ( (BYTE4(v29) & 0x30) == 0 )
  {
LABEL_37:
    v9 = -1073741819;
    goto LABEL_10;
  }
  if ( DWORD2(v29) != 0x1000000 )
  {
    if ( DWORD2(v29) == 0x20000 )
    {
      v14 = 1610612800;
      goto LABEL_24;
    }
    goto LABEL_37;
  }
  v14 = 1610612864;
LABEL_24:
  v15 = v14 | DWORD1(v29) & 0xFFFFFFCF;
  BaseAddress = (PVOID)VirtualMemoryInformation;
  NumberOfBytesToProtect = ~((unsigned int)dword_1803A2D68 - 1LL)
                         & ((unsigned int)dword_1803A2D68
                          + ((unsigned __int64)lpBaseAddress & ((unsigned int)dword_1803A2D68 - 1LL))
                          + nSize
                          - 1);
  if ( NumberOfBytesToProtect > *((_QWORD *)&v28 + 1) )
    NumberOfBytesToProtect = *((_QWORD *)&v28 + 1);
  if ( v22 )
  {
    v16 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v16 )
    {
      *(_DWORD *)(v16 + 4) = 4;
      *(_QWORD *)(v16 + 8) = BaseAddress;
      *(_QWORD *)(v16 + 16) = NumberOfBytesToProtect;
      *(_DWORD *)(v16 + 24) = v15;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v16, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
  }
  v9 = NtProtectVirtualMemory(hProcess, &BaseAddress, &NumberOfBytesToProtect, v15, &OldAccessProtection);
  if ( v22 )
  {
    v17 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v17 )
    {
      *(_DWORD *)(v17 + 4) = 5;
      *(_QWORD *)(v17 + 8) = BaseAddress;
      *(_QWORD *)(v17 + 16) = NumberOfBytesToProtect;
      *(_DWORD *)(v17 + 24) = v15;
      *(_DWORD *)(v17 + 28) = v9;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v17, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
  }
  if ( v9 < 0 )
    goto LABEL_10;
  v10 = 1;
LABEL_5:
  v9 = NtWriteVirtualMemory(hProcess, lpBaseAddress, (PVOID)lpBuffer, nSize, &NumberOfBytesWritten);
  if ( lpNumberOfBytesWritten )
    *lpNumberOfBytesWritten = NumberOfBytesWritten;
  if ( v9 >= 0 && v22 )
  {
    v18 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v18 )
    {
      *(_DWORD *)(v18 + 4) = 6;
      *(_QWORD *)(v18 + 8) = lpBaseAddress;
      *(_QWORD *)(v18 + 16) = nSize;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v18, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
  }
  if ( !v10 )
    goto LABEL_10;
  v12 = OldAccessProtection | 0x60000000;
  if ( (OldAccessProtection & 0xF0) == 0 )
    v12 = OldAccessProtection | 0x20000000;
  if ( v22 )
  {
    v19 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v19 )
    {
      *(_DWORD *)(v19 + 4) = 4;
      *(_QWORD *)(v19 + 8) = BaseAddress;
      *(_QWORD *)(v19 + 16) = NumberOfBytesToProtect;
      *(_DWORD *)(v19 + 24) = v12;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v19, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
  }
  v9 = NtProtectVirtualMemory(hProcess, &BaseAddress, &NumberOfBytesToProtect, v12, &OldAccessProtection);
  if ( v22 )
  {
    v13 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v13 )
    {
      *(_DWORD *)(v13 + 4) = 5;
      *(_QWORD *)(v13 + 8) = BaseAddress;
      *(_QWORD *)(v13 + 16) = NumberOfBytesToProtect;
      *(_DWORD *)(v13 + 24) = v12;
      *(_DWORD *)(v13 + 28) = v9;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v13, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
    goto LABEL_10;
  }
LABEL_12:
  if ( v9 >= 0 )
    return 1;
  BaseSetLastNTError((unsigned int)v9);
  return 0;
}

```

## disassembly

```asm
0x1800e23d0  mov     rax, rsp
0x1800e23d3  mov     [rax+8], rbx
0x1800e23d7  mov     [rax+20h], r9
0x1800e23db  mov     [rax+18h], r8
0x1800e23df  push    rbp
0x1800e23e0  push    rsi
0x1800e23e1  push    rdi
0x1800e23e2  push    r12
0x1800e23e4  push    r13
0x1800e23e6  push    r14
0x1800e23e8  push    r15
0x1800e23ea  lea     rbp, [rax-57h]
0x1800e23ee  sub     rsp, 0A0h
0x1800e23f5  xorps   xmm0, xmm0
0x1800e23f8  mov     [rbp+4Fh+OldAccessProtection], 0
0x1800e23ff  mov     r13, rdx
0x1800e2402  mov     [rbp+4Fh+BaseAddress], 0
0x1800e240a  lea     rdx, [rbp+4Fh+Handle]
0x1800e240e  mov     [rbp+4Fh+NumberOfBytesToProtect], 0
0x1800e2416  lea     r8, [rbp+4Fh+var_90]
0x1800e241a  mov     [rbp+4Fh+NumberOfBytesWritten], 0
0x1800e2422  movups  [rbp+4Fh+VirtualMemoryInformation], xmm0
0x1800e2426  mov     r12, rcx
0x1800e2429  mov     [rbp+4Fh+var_A0], 0
0x1800e2431  movups  [rbp+4Fh+var_58], xmm0
0x1800e2435  mov     [rbp+4Fh+Handle], 0
0x1800e243d  movups  [rbp+4Fh+var_48], xmm0
0x1800e2441  mov     [rbp+4Fh+var_90], 0
0x1800e2449  call    cs:__imp_RtlOpenCrossProcessEmulatorWorkConnection
0x1800e244f  mov     rdi, [rbp+4Fh+var_90]
0x1800e2453  test    rdi, rdi
0x1800e2456  jnz     loc_1800E2625
0x1800e245c  xor     esi, esi
0x1800e245e  mov     qword ptr [rsp+28h], 0; ResultLength
0x1800e2467  lea     r9, [rbp+4Fh+VirtualMemoryInformation]; VirtualMemoryInformation
0x1800e246b  mov     r8d, 8; VirtualMemoryInformationClass
0x1800e2471  mov     [rsp+0D0h+Length], 30h ; '0'; Length
0x1800e247a  mov     rdx, r13; Address
0x1800e247d  mov     rcx, r12; ProcessHandle
0x1800e2480  call    cs:__imp_NtQueryVirtualMemory
0x1800e2486  mov     ebx, eax
0x1800e2488  test    eax, eax
0x1800e248a  js      short loc_1800E24E3
0x1800e248c  mov     r14d, dword ptr [rbp+4Fh+var_48+4]
0x1800e2490  xor     r15b, r15b
0x1800e2493  test    r14b, 0CCh
0x1800e2497  jz      loc_1800E2589
0x1800e249d  mov     r14, [rbp+4Fh+NumberOfBytesToWrite]
0x1800e24a1  lea     rax, [rbp+4Fh+NumberOfBytesWritten]
0x1800e24a5  mov     r8, [rbp+4Fh+Buffer]; Buffer
0x1800e24a9  mov     r9, r14; NumberOfBytesToWrite
0x1800e24ac  mov     rdx, r13; BaseAddress
0x1800e24af  mov     [rsp+0D0h+Length], rax; NumberOfBytesWritten
0x1800e24b4  mov     rcx, r12; ProcessHandle
0x1800e24b7  call    cs:__imp_NtWriteVirtualMemory
0x1800e24bd  mov     rcx, [rbp+4Fh+lpNumberOfBytesWritten]
0x1800e24c1  mov     ebx, eax
0x1800e24c3  test    rcx, rcx
0x1800e24c6  jz      short loc_1800E24CF
0x1800e24c8  mov     rax, [rbp+4Fh+NumberOfBytesWritten]
0x1800e24cc  mov     [rcx], rax
0x1800e24cf  test    ebx, ebx
0x1800e24d1  js      short loc_1800E24DE
0x1800e24d3  cmp     [rbp+4Fh+var_90], 0
0x1800e24d8  jnz     loc_1800E268B
0x1800e24de  test    r15b, r15b
0x1800e24e1  jnz     short loc_1800E251F
0x1800e24e3  mov     rdx, [rbp+4Fh+var_90]; BaseAddress
0x1800e24e7  test    rdx, rdx
0x1800e24ea  jnz     loc_1800E26CE
0x1800e24f0  test    ebx, ebx
0x1800e24f2  js      short loc_1800E2514
0x1800e24f4  mov     eax, 1
0x1800e24f9  mov     rbx, [rsp+0D0h+arg_0]
0x1800e2501  add     rsp, 0A0h
0x1800e2508  pop     r15
0x1800e250a  pop     r14
0x1800e250c  pop     r13
0x1800e250e  pop     r12
0x1800e2510  pop     rdi
0x1800e2511  pop     rsi
0x1800e2512  pop     rbp
0x1800e2513  retn
0x1800e2514  mov     ecx, ebx
0x1800e2516  call    BaseSetLastNTError
0x1800e251b  xor     eax, eax
0x1800e251d  jmp     short loc_1800E24F9
0x1800e251f  mov     ecx, [rbp+4Fh+OldAccessProtection]
0x1800e2522  bts     ecx, 1Dh
0x1800e2526  mov     r14d, ecx
0x1800e2529  bts     r14d, 1Eh
0x1800e252e  test    cl, 0F0h
0x1800e2531  cmovz   r14d, ecx
0x1800e2535  cmp     [rbp+4Fh+var_90], 0
0x1800e253a  jnz     loc_1800E26AB
0x1800e2540  lea     rax, [rbp+4Fh+OldAccessProtection]
0x1800e2544  mov     r9d, r14d; NewAccessProtection
0x1800e2547  lea     r8, [rbp+4Fh+NumberOfBytesToProtect]; NumberOfBytesToProtect
0x1800e254b  mov     [rsp+0D0h+Length], rax; OldAccessProtection
0x1800e2550  lea     rdx, [rbp+4Fh+BaseAddress]; BaseAddress
0x1800e2554  mov     rcx, r12; ProcessHandle
0x1800e2557  call    cs:__imp_NtProtectVirtualMemory
0x1800e255d  cmp     [rbp+4Fh+var_90], 0
0x1800e2562  mov     ebx, eax
0x1800e2564  jz      short loc_1800E24F0
0x1800e2566  mov     rcx, rdi
0x1800e2569  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800e256f  mov     rdx, rax
0x1800e2572  mov     rcx, rsi
0x1800e2575  test    rax, rax
0x1800e2578  jnz     loc_180194476
0x1800e257e  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800e2584  jmp     loc_1800E24E3
0x1800e2589  test    r14b, 30h
0x1800e258d  jz      loc_1800E2681
0x1800e2593  cmp     dword ptr [rbp+4Fh+var_48+8], 1000000h
0x1800e259a  jnz     loc_1800E262E
0x1800e25a0  mov     eax, 60000080h
0x1800e25a5  mov     ecx, cs:dword_1803A2D68
0x1800e25ab  and     r14d, 0FFFFFFCFh
0x1800e25af  or      r14d, eax
0x1800e25b2  mov     rax, qword ptr [rbp+4Fh+VirtualMemoryInformation]
0x1800e25b6  mov     [rbp+4Fh+BaseAddress], rax
0x1800e25ba  lea     rdx, [rcx-1]
0x1800e25be  mov     rax, rdx
0x1800e25c1  not     rdx
0x1800e25c4  and     rax, r13
0x1800e25c7  add     rax, rcx
0x1800e25ca  mov     rcx, [rbp+4Fh+NumberOfBytesToWrite]
0x1800e25ce  dec     rcx
0x1800e25d1  add     rcx, rax
0x1800e25d4  mov     rax, qword ptr [rbp+4Fh+var_58+8]
0x1800e25d8  and     rcx, rdx
0x1800e25db  mov     [rbp+4Fh+NumberOfBytesToProtect], rcx
0x1800e25df  cmp     rcx, rax
0x1800e25e2  jbe     short loc_1800E25E8
0x1800e25e4  mov     [rbp+4Fh+NumberOfBytesToProtect], rax
0x1800e25e8  cmp     [rbp+4Fh+var_90], 0
0x1800e25ed  jnz     short loc_1800E2641
0x1800e25ef  lea     rax, [rbp+4Fh+OldAccessProtection]
0x1800e25f3  mov     r9d, r14d; NewAccessProtection
0x1800e25f6  lea     r8, [rbp+4Fh+NumberOfBytesToProtect]; NumberOfBytesToProtect
0x1800e25fa  mov     [rsp+0D0h+Length], rax; OldAccessProtection
0x1800e25ff  lea     rdx, [rbp+4Fh+BaseAddress]; BaseAddress
0x1800e2603  mov     rcx, r12; ProcessHandle
0x1800e2606  call    cs:__imp_NtProtectVirtualMemory
0x1800e260c  cmp     [rbp+4Fh+var_90], 0
0x1800e2611  mov     ebx, eax
0x1800e2613  jnz     short loc_1800E2661
0x1800e2615  test    ebx, ebx
0x1800e2617  js      loc_1800E24E3
0x1800e261d  mov     r15b, 1
0x1800e2620  jmp     loc_1800E249D
0x1800e2625  lea     rsi, [rdi+8]
0x1800e2629  jmp     loc_1800E245E
0x1800e262e  cmp     dword ptr [rbp+4Fh+var_48+8], 20000h
0x1800e2635  jnz     short loc_1800E2681
0x1800e2637  mov     eax, 60000040h
0x1800e263c  jmp     loc_1800E25A5
0x1800e2641  mov     rcx, rdi
0x1800e2644  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800e264a  mov     rdx, rax
0x1800e264d  mov     rcx, rsi
0x1800e2650  test    rax, rax
0x1800e2653  jnz     loc_180194378
0x1800e2659  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800e265f  jmp     short loc_1800E25EF
0x1800e2661  mov     rcx, rdi
0x1800e2664  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800e266a  mov     rdx, rax
0x1800e266d  mov     rcx, rsi
0x1800e2670  test    rax, rax
0x1800e2673  jnz     loc_1801943B9
0x1800e2679  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800e267f  jmp     short loc_1800E2615
0x1800e2681  mov     ebx, 0C0000005h
0x1800e2686  jmp     loc_1800E24E3
0x1800e268b  mov     rcx, rdi
0x1800e268e  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800e2694  mov     rcx, rsi
0x1800e2697  test    rax, rax
0x1800e269a  jnz     loc_1801943FD
0x1800e26a0  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800e26a6  jmp     loc_1800E24DE
0x1800e26ab  mov     rcx, rdi
0x1800e26ae  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800e26b4  mov     rdx, rax
0x1800e26b7  mov     rcx, rsi
0x1800e26ba  test    rax, rax
0x1800e26bd  jnz     loc_180194435
0x1800e26c3  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800e26c9  jmp     loc_1800E2540
0x1800e26ce  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800e26d2  call    cs:__imp_NtUnmapViewOfSection
0x1800e26d8  mov     rcx, [rbp+4Fh+Handle]; Handle
0x1800e26dc  call    cs:__imp_NtClose
0x1800e26e2  jmp     loc_1800E24F0
0x180194378  mov     dword ptr [rax+4], 4
0x18019437f  lea     r8, [rbp+4Fh+var_A0]
0x180194383  mov     rax, [rbp+4Fh+BaseAddress]
0x180194387  mov     [rdx+8], rax
0x18019438b  mov     rax, [rbp+4Fh+NumberOfBytesToProtect]
0x18019438f  mov     [rdx+10h], rax
0x180194393  mov     [rdx+18h], r14d
0x180194397  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x18019439d  mov     rdx, [rbp+4Fh+var_A0]
0x1801943a1  test    rdx, rdx
0x1801943a4  jz      loc_1800E25EF
0x1801943aa  mov     rcx, rdi
0x1801943ad  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x1801943b3  nop
0x1801943b4  jmp     loc_1800E25EF
0x1801943b9  mov     dword ptr [rax+4], 5
0x1801943c0  lea     r8, [rbp+4Fh+var_A0]
0x1801943c4  mov     rax, [rbp+4Fh+BaseAddress]
0x1801943c8  mov     [rdx+8], rax
0x1801943cc  mov     rax, [rbp+4Fh+NumberOfBytesToProtect]
0x1801943d0  mov     [rdx+10h], rax
0x1801943d4  mov     [rdx+18h], r14d
0x1801943d8  mov     [rdx+1Ch], ebx
0x1801943db  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x1801943e1  mov     rdx, [rbp+4Fh+var_A0]
0x1801943e5  test    rdx, rdx
0x1801943e8  jz      loc_1800E2615
0x1801943ee  mov     rcx, rdi
0x1801943f1  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x1801943f7  nop
0x1801943f8  jmp     loc_1800E2615
0x1801943fd  lea     r8, [rbp+4Fh+var_A0]
0x180194401  mov     dword ptr [rax+4], 6
0x180194408  mov     rdx, rax
0x18019440b  mov     [rax+8], r13
0x18019440f  mov     [rax+10h], r14
0x180194413  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x180194419  mov     rdx, [rbp+4Fh+var_A0]
0x18019441d  test    rdx, rdx
0x180194420  jz      loc_1800E24DE
0x180194426  mov     rcx, rdi
0x180194429  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x18019442f  nop
0x180194430  jmp     loc_1800E24DE
0x180194435  mov     dword ptr [rax+4], 4
0x18019443c  lea     r8, [rbp+4Fh+var_A0]
0x180194440  mov     rax, [rbp+4Fh+BaseAddress]
0x180194444  mov     [rdx+8], rax
0x180194448  mov     rax, [rbp+4Fh+NumberOfBytesToProtect]
0x18019444c  mov     [rdx+10h], rax
0x180194450  mov     [rdx+18h], r14d
0x180194454  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x18019445a  mov     rdx, [rbp+4Fh+var_A0]
0x18019445e  test    rdx, rdx
0x180194461  jz      loc_1800E2540
0x180194467  mov     rcx, rdi
0x18019446a  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x180194470  nop
0x180194471  jmp     loc_1800E2540
0x180194476  mov     dword ptr [rax+4], 5
0x18019447d  lea     r8, [rbp+4Fh+var_A0]
0x180194481  mov     rax, [rbp+4Fh+BaseAddress]
0x180194485  mov     [rdx+8], rax
0x180194489  mov     rax, [rbp+4Fh+NumberOfBytesToProtect]
0x18019448d  mov     [rdx+10h], rax
0x180194491  mov     [rdx+18h], r14d
0x180194495  mov     [rdx+1Ch], ebx
0x180194498  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x18019449e  mov     rdx, [rbp+4Fh+var_A0]
0x1801944a2  test    rdx, rdx
0x1801944a5  jz      loc_1800E24E3
0x1801944ab  mov     rcx, rdi
0x1801944ae  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x1801944b4  nop
0x1801944b5  jmp     loc_1800E24E3
```
