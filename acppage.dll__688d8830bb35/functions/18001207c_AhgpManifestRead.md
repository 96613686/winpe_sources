# AhgpManifestRead

- ea: `0x18001207c`
- end: `0x18001221d`
- name: `AhgpManifestRead`
- size: `417`
- prototype: `__int64 __fastcall(_QWORD *, void *, ULONG)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001101c`
- `0x180011e94`

## callees

- `0x18001207c`
- `0x180015220`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180012207`
- `ntdll!RtlFreeHeap` at `0x180012207`
- `ntdll!RtlAllocateHeap` at `0x18001211f`
- `ntdll!RtlAllocateHeap` at `0x18001211f`
- `KERNEL32!QueryActCtxW` at `0x1800120c1`
- `KERNEL32!QueryActCtxW` at `0x180012182`
- `KERNEL32!QueryActCtxW` at `0x1800120c1`
- `KERNEL32!QueryActCtxW` at `0x180012182`
- `KERNEL32!GetLastError` at `0x1800120ca`
- `KERNEL32!GetLastError` at `0x18001218c`
- `KERNEL32!GetLastError` at `0x1800120ca`
- `KERNEL32!GetLastError` at `0x18001218c`

## string_xrefs

- `0x1800120ef`: `AhgpManifestRead`
- `0x180012141`: `AhgpManifestRead`
- `0x1800121a9`: `AhgpManifestRead`
- `0x1800121dc`: `AhgpManifestRead`
- `0x1800120e4`: `Failed to read activation context [%d]`
- `0x18001219c`: `Failed to read activation context [%d]`
- `0x1800121d1`: `Exception while reading manifest [%d]`

## pseudocode

```c
__int64 __fastcall AhgpManifestRead(_QWORD *a1, void *a2, ULONG a3)
{
  PVOID pvBuffer; // rdi
  BOOL v7; // r12d
  DWORD LastError; // ebx
  SIZE_T Size; // [rsp+A0h] [rbp+8h] BYREF

  Size = 0;
  pvBuffer = 0;
  *a1 = 0;
  v7 = QueryActCtxW(0x80000000, a2, 0, a3, 0, 0, &Size);
  LastError = GetLastError();
  if ( LastError == 122 || v7 )
  {
    LastError = 8;
    pvBuffer = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
    if ( pvBuffer )
    {
      if ( QueryActCtxW(0x80000000, a2, 0, a3, pvBuffer, Size, &Size) )
      {
        *a1 = pvBuffer;
        pvBuffer = 0;
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        AslLogCallPrintf(1, "AhgpManifestRead", 108, "Failed to read activation context [%d]");
      }
    }
    else
    {
      AslLogCallPrintf(1, "AhgpManifestRead", 90, "Out of memory");
    }
  }
  else
  {
    AslLogCallPrintf(3, "AhgpManifestRead", 82, "Failed to read activation context [%d]");
  }
  if ( pvBuffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pvBuffer);
  return LastError;
}

```

## disassembly

```asm
0x18001207c  mov     r11, rsp
0x18001207f  push    rbx
0x180012080  push    rsi
0x180012081  push    rdi
0x180012082  push    r12
0x180012084  push    r14
0x180012086  push    r15
0x180012088  sub     rsp, 68h
0x18001208c  mov     r14d, r8d
0x18001208f  mov     r15, rdx
0x180012092  mov     rsi, rcx
0x180012095  mov     qword ptr [r11+8], 0
0x18001209d  xor     edi, edi
0x18001209f  mov     [r11-48h], rdi
0x1800120a3  mov     [rcx], rdi
0x1800120a6  lea     rax, [r11+8]
0x1800120aa  mov     [r11-68h], rax
0x1800120ae  mov     [r11-70h], rdi
0x1800120b2  mov     [r11-78h], rdi
0x1800120b6  mov     r9d, r8d; ulInfoClass
0x1800120b9  xor     r8d, r8d; pvSubInstance
0x1800120bc  mov     ecx, 80000000h; dwFlags
0x1800120c1  call    cs:__imp_QueryActCtxW
0x1800120c7  mov     r12d, eax
0x1800120ca  call    cs:__imp_GetLastError
0x1800120d0  mov     ebx, eax
0x1800120d2  mov     [rsp+98h+var_58], eax
0x1800120d6  cmp     eax, 7Ah ; 'z'
0x1800120d9  jz      short loc_180012103
0x1800120db  test    r12d, r12d
0x1800120de  jnz     short loc_180012103
0x1800120e0  mov     dword ptr [rsp+98h+pvBuffer], eax
0x1800120e4  lea     r9, aFailedToReadAc; "Failed to read activation context [%d]"
0x1800120eb  lea     r8d, [rdi+52h]
0x1800120ef  lea     rdx, aAhgpmanifestre; "AhgpManifestRead"
0x1800120f6  lea     ecx, [rdi+3]
0x1800120f9  call    AslLogCallPrintf
0x1800120fe  jmp     loc_1800121F0
0x180012103  mov     rcx, gs:60h
0x18001210c  mov     r8, [rsp+98h+Size]; Size
0x180012114  mov     ebx, 8
0x180012119  mov     edx, ebx; Flags
0x18001211b  mov     rcx, [rcx+30h]; HeapHandle
0x18001211f  call    cs:__imp_RtlAllocateHeap
0x180012125  mov     rdi, rax
0x180012128  mov     [rsp+98h+var_48], rax
0x18001212d  test    rax, rax
0x180012130  jnz     short loc_180012155
0x180012132  mov     [rsp+98h+var_58], ebx
0x180012136  lea     r9, aOutOfMemory; "Out of memory"
0x18001213d  lea     r8d, [rbx+52h]
0x180012141  lea     rdx, aAhgpmanifestre; "AhgpManifestRead"
0x180012148  lea     ecx, [rbx-7]
0x18001214b  call    AslLogCallPrintf
0x180012150  jmp     loc_1800121F0
0x180012155  lea     rax, [rsp+98h+Size]
0x18001215d  mov     [rsp+98h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x180012162  mov     rax, [rsp+98h+Size]
0x18001216a  mov     [rsp+98h+cbBuffer], rax; cbBuffer
0x18001216f  mov     [rsp+98h+pvBuffer], rdi; pvBuffer
0x180012174  mov     r9d, r14d; ulInfoClass
0x180012177  xor     r8d, r8d; pvSubInstance
0x18001217a  mov     rdx, r15; hActCtx
0x18001217d  mov     ecx, 80000000h; dwFlags
0x180012182  call    cs:__imp_QueryActCtxW
0x180012188  test    eax, eax
0x18001218a  jnz     short loc_1800121BB
0x18001218c  call    cs:__imp_GetLastError
0x180012192  mov     ebx, eax
0x180012194  mov     [rsp+98h+var_58], eax
0x180012198  mov     dword ptr [rsp+98h+pvBuffer], eax
0x18001219c  lea     r9, aFailedToReadAc; "Failed to read activation context [%d]"
0x1800121a3  mov     r8d, 6Ch ; 'l'
0x1800121a9  lea     rdx, aAhgpmanifestre; "AhgpManifestRead"
0x1800121b0  lea     ecx, [r8-6Bh]
0x1800121b4  call    AslLogCallPrintf
0x1800121b9  jmp     short loc_1800121F0
0x1800121bb  mov     [rsi], rdi
0x1800121be  xor     edi, edi
0x1800121c0  xor     ebx, ebx
0x1800121c2  jmp     short loc_1800121F0
0x1800121c4  mov     ebx, 1Eh
0x1800121c9  mov     [rsp+98h+var_58], ebx
0x1800121cd  mov     dword ptr [rsp+98h+pvBuffer], ebx
0x1800121d1  lea     r9, aExceptionWhile; "Exception while reading manifest [%d]"
0x1800121d8  lea     r8d, [rbx+54h]
0x1800121dc  lea     rdx, aAhgpmanifestre; "AhgpManifestRead"
0x1800121e3  lea     ecx, [rbx-1Dh]
0x1800121e6  call    AslLogCallPrintf
0x1800121eb  mov     rdi, [rsp+98h+var_48]
0x1800121f0  test    rdi, rdi
0x1800121f3  jz      short loc_18001220D
0x1800121f5  mov     rcx, gs:60h
0x1800121fe  mov     r8, rdi; P
0x180012201  xor     edx, edx; Flags
0x180012203  mov     rcx, [rcx+30h]; HeapHandle
0x180012207  call    cs:__imp_RtlFreeHeap
0x18001220d  mov     eax, ebx
0x18001220f  add     rsp, 68h
0x180012213  pop     r15
0x180012215  pop     r14
0x180012217  pop     r12
0x180012219  pop     rdi
0x18001221a  pop     rsi
0x18001221b  pop     rbx
0x18001221c  retn
0x180016727  push    rbp
0x180016729  sub     rsp, 40h
0x18001672d  mov     rbp, rdx
0x180016730  mov     [rbp+48h], rcx
0x180016734  mov     rax, [rbp+48h]
0x180016738  mov     rcx, [rax]
0x18001673b  cmp     dword ptr [rcx], 0C0000006h
0x180016741  jz      short loc_18001675B
0x180016743  mov     rax, [rbp+48h]
0x180016747  mov     rcx, [rax]
0x18001674a  cmp     dword ptr [rcx], 0C0000005h
0x180016750  jz      short loc_18001675B
0x180016752  mov     dword ptr [rbp+44h], 0
0x180016759  jmp     short loc_180016762
0x18001675b  mov     dword ptr [rbp+44h], 1
0x180016762  mov     eax, [rbp+44h]
0x180016765  add     rsp, 40h
0x180016769  pop     rbp
0x18001676a  retn
```
