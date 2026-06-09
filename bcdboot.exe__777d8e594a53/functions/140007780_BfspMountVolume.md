# BfspMountVolume

- ea: `0x140007780`
- end: `0x1400078ec`
- name: `BfspMountVolume`
- size: `364`
- prototype: `DWORD __fastcall(LPCWSTR lpszVolumeName, LPCWSTR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1400065a0`

## callees

- `0x140007780`
- `0x14000e628`

## import_xrefs

- `msvcrt!swprintf_s` at `0x14000783b`
- `msvcrt!swprintf_s` at `0x14000783b`
- `KERNEL32!GetLastError` at `0x1400078a6`
- `KERNEL32!GetLastError` at `0x1400078c3`
- `KERNEL32!GetLastError` at `0x1400078cd`
- `KERNEL32!GetLastError` at `0x1400078d5`
- `KERNEL32!GetLastError` at `0x1400078a6`
- `KERNEL32!GetLastError` at `0x1400078c3`
- `KERNEL32!GetLastError` at `0x1400078cd`
- `KERNEL32!GetLastError` at `0x1400078d5`
- `KERNEL32!HeapFree` at `0x140007899`
- `KERNEL32!HeapFree` at `0x140007899`
- `KERNEL32!HeapAlloc` at `0x1400077eb`
- `KERNEL32!HeapAlloc` at `0x1400077eb`
- `KERNEL32!GetProcessHeap` at `0x1400077da`
- `KERNEL32!GetProcessHeap` at `0x14000788b`
- `KERNEL32!GetProcessHeap` at `0x1400077da`
- `KERNEL32!GetProcessHeap` at `0x14000788b`
- `KERNEL32!GetLogicalDrives` at `0x14000778f`
- `KERNEL32!GetLogicalDrives` at `0x14000778f`
- `KERNEL32!SetVolumeMountPointW` at `0x14000785e`
- `KERNEL32!SetVolumeMountPointW` at `0x14000785e`

## string_xrefs

- `0x1400077f9`: `Failed to allocate memory for mount location`
- `0x140007815`: `Found potential mount location at %C`
- `0x140007847`: `Attempting to mount at letter %ws`
- `0x14000786b`: `Mounted %ws at %ws`
- `0x1400078af`: `Attempt to mount volume %ws failed Error %u`

## pseudocode

```c
DWORD __fastcall BfspMountVolume(LPCWSTR lpszVolumeName, LPCWSTR *a2)
{
  DWORD LogicalDrives; // edx
  unsigned __int16 v5; // bx
  int v6; // ecx
  HANDLE ProcessHeap; // rax
  wchar_t *v9; // rbp
  WCHAR *v10; // rbx
  HANDLE v11; // rax
  DWORD LastError; // eax

  LogicalDrives = GetLogicalDrives();
  if ( LogicalDrives )
  {
    v5 = 67;
    v6 = 2;
    while ( ((LogicalDrives >> v6) & 1) != 0 )
    {
      ++v6;
      ++v5;
      if ( v6 >= 26 )
        return -1073741275;
    }
    ProcessHeap = GetProcessHeap();
    v9 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 8u);
    if ( !v9 )
    {
      BfspLogMessage(4, L"Failed to allocate memory for mount location");
      return -1073741670;
    }
    BfspLogMessage(2, L"Found potential mount location at %C", v5);
    swprintf_s(v9, 4u, L"%C:\\", v5);
    *a2 = v9;
    BfspLogMessage(2, L"Attempting to mount at letter %ws", v9);
    if ( SetVolumeMountPointW(*a2, lpszVolumeName) )
    {
      BfspLogMessage(2, L"Mounted %ws at %ws", lpszVolumeName, *a2);
      return 0;
    }
    v10 = (WCHAR *)*a2;
    if ( *a2 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
    }
    *a2 = 0;
    LastError = GetLastError();
    BfspLogMessage(4, L"Attempt to mount volume %ws failed Error %u", lpszVolumeName, LastError);
  }
  else
  {
    BfspLogMessage(4, L"Failed to enumerate logical drives");
  }
  if ( (int)GetLastError() > 0 )
    return (unsigned __int16)GetLastError() | 0xC0070000;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x140007780  push    rbx
0x140007782  push    rbp
0x140007783  push    rsi
0x140007784  push    rdi
0x140007785  sub     rsp, 28h
0x140007789  mov     rdi, rdx
0x14000778c  mov     rsi, rcx
0x14000778f  call    cs:__imp_GetLogicalDrives
0x140007795  mov     edx, eax
0x140007797  test    eax, eax
0x140007799  jnz     short loc_1400077AF
0x14000779b  lea     rdx, aFailedToEnumer_7; "Failed to enumerate logical drives"
0x1400077a2  lea     ecx, [rax+4]
0x1400077a5  call    BfspLogMessage
0x1400077aa  jmp     loc_1400078C3
0x1400077af  mov     ebx, 43h ; 'C'
0x1400077b4  lea     ecx, [rbx-41h]
0x1400077b7  lea     r8d, [rbx-42h]
0x1400077bb  mov     eax, edx
0x1400077bd  shr     eax, cl
0x1400077bf  test    r8b, al
0x1400077c2  jz      short loc_1400077DA
0x1400077c4  add     ecx, r8d
0x1400077c7  add     bx, r8w
0x1400077cb  cmp     ecx, 1Ah
0x1400077ce  jl      short loc_1400077BB
0x1400077d0  mov     eax, 0C0000225h
0x1400077d5  jmp     loc_1400078E3
0x1400077da  call    cs:__imp_GetProcessHeap
0x1400077e0  mov     edx, 8; dwFlags
0x1400077e5  mov     rcx, rax; hHeap
0x1400077e8  mov     r8d, edx; dwBytes
0x1400077eb  call    cs:__imp_HeapAlloc
0x1400077f1  mov     rbp, rax
0x1400077f4  test    rax, rax
0x1400077f7  jnz     short loc_140007812
0x1400077f9  lea     rdx, aFailedToAlloca_0; "Failed to allocate memory for mount loc"...
0x140007800  lea     ecx, [rax+4]
0x140007803  call    BfspLogMessage
0x140007808  mov     eax, 0C000009Ah
0x14000780d  jmp     loc_1400078E3
0x140007812  movzx   ebx, bx
0x140007815  lea     rdx, aFoundPotential; "Found potential mount location at %C"
0x14000781c  mov     r8d, ebx
0x14000781f  mov     ecx, 2
0x140007824  call    BfspLogMessage
0x140007829  mov     r9d, ebx
0x14000782c  lea     r8, aC; "%C:\\"
0x140007833  mov     edx, 4; BufferCount
0x140007838  mov     rcx, rbp; Buffer
0x14000783b  call    cs:__imp_swprintf_s
0x140007841  mov     r8, rbp
0x140007844  mov     [rdi], rbp
0x140007847  lea     rdx, aAttemptingToMo_0; "Attempting to mount at letter %ws"
0x14000784e  mov     ecx, 2
0x140007853  call    BfspLogMessage
0x140007858  mov     rcx, [rdi]; lpszVolumeMountPoint
0x14000785b  mov     rdx, rsi; lpszVolumeName
0x14000785e  call    cs:__imp_SetVolumeMountPointW
0x140007864  test    eax, eax
0x140007866  jz      short loc_140007883
0x140007868  mov     r9, [rdi]
0x14000786b  lea     rdx, aMountedWsAtWs; "Mounted %ws at %ws"
0x140007872  mov     r8, rsi
0x140007875  mov     ecx, 2
0x14000787a  call    BfspLogMessage
0x14000787f  xor     eax, eax
0x140007881  jmp     short loc_1400078E3
0x140007883  mov     rbx, [rdi]
0x140007886  test    rbx, rbx
0x140007889  jz      short loc_14000789F
0x14000788b  call    cs:__imp_GetProcessHeap
0x140007891  mov     r8, rbx; lpMem
0x140007894  xor     edx, edx; dwFlags
0x140007896  mov     rcx, rax; hHeap
0x140007899  call    cs:__imp_HeapFree
0x14000789f  mov     qword ptr [rdi], 0
0x1400078a6  call    cs:__imp_GetLastError
0x1400078ac  mov     r8, rsi
0x1400078af  lea     rdx, aAttemptToMount; "Attempt to mount volume %ws failed Erro"...
0x1400078b6  mov     r9d, eax
0x1400078b9  mov     ecx, 4
0x1400078be  call    BfspLogMessage
0x1400078c3  call    cs:__imp_GetLastError
0x1400078c9  test    eax, eax
0x1400078cb  jg      short loc_1400078D5
0x1400078cd  call    cs:__imp_GetLastError
0x1400078d3  jmp     short loc_1400078E3
0x1400078d5  call    cs:__imp_GetLastError
0x1400078db  movzx   eax, ax
0x1400078de  or      eax, 0C0070000h
0x1400078e3  add     rsp, 28h
0x1400078e7  pop     rdi
0x1400078e8  pop     rsi
0x1400078e9  pop     rbp
0x1400078ea  pop     rbx
0x1400078eb  retn
```
