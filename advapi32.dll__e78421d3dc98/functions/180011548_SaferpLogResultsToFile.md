# SaferpLogResultsToFile

- ea: `0x180011548`
- end: `0x1800118b7`
- name: `SaferpLogResultsToFile`
- size: `879`
- prototype: `int __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180010c00`

## callees

- `0x180011548`
- `0x180065090`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180011862`
- `msvcrt!swprintf_s` at `0x180011862`
- `ntdll!NtOpenKey` at `0x1800115bf`
- `ntdll!NtOpenKey` at `0x1800115bf`
- `ntdll!NtQueryValueKey` at `0x1800115f0`
- `ntdll!NtQueryValueKey` at `0x1800115f0`
- `ntdll!NtClose` at `0x1800115fc`
- `ntdll!NtClose` at `0x1800115fc`
- `ntdll!NtQueryInformationProcess` at `0x1800116b9`
- `ntdll!NtQueryInformationProcess` at `0x180011733`
- `ntdll!NtQueryInformationProcess` at `0x1800116b9`
- `ntdll!NtQueryInformationProcess` at `0x180011733`
- `ntdll!RtlFreeHeap` at `0x1800118a3`
- `ntdll!RtlFreeHeap` at `0x1800118a3`
- `ntdll!RtlAllocateHeap` at `0x18001175f`
- `ntdll!RtlAllocateHeap` at `0x18001175f`
- `KERNEL32!CloseHandle` at `0x1800118ac`
- `KERNEL32!CloseHandle` at `0x1800118ac`
- `KERNEL32!WriteFile` at `0x180011688`
- `KERNEL32!WriteFile` at `0x18001188b`
- `KERNEL32!WriteFile` at `0x180011688`
- `KERNEL32!WriteFile` at `0x18001188b`
- `KERNEL32!SetFilePointer` at `0x18001166f`
- `KERNEL32!SetFilePointer` at `0x180011699`
- `KERNEL32!SetFilePointer` at `0x18001166f`
- `KERNEL32!SetFilePointer` at `0x180011699`
- `KERNEL32!CreateFileW` at `0x18001164e`
- `KERNEL32!CreateFileW` at `0x18001164e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SaferpLogResultsToFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // edi
  HANDLE FileW; // rax
  NTSTATUS ValueKey; // ebx
  __int64 v8; // r15
  HANDLE v9; // r14
  __int64 v10; // rax
  _BYTE *v11; // r13
  int v12; // eax
  __int64 v13; // rsi
  __int64 v14; // rbx
  PVOID ProcessHeap; // rcx
  wchar_t *Heap; // r12
  __int64 Buffer; // [rsp+C0h] [rbp-80h] BYREF
  __int64 NumberOfBytesWritten; // [rsp+C8h] [rbp-78h] BYREF
  __int64 v20; // [rsp+D0h] [rbp-70h] BYREF
  HANDLE KeyHandle; // [rsp+D8h] [rbp-68h] BYREF
  size_t BufferCount; // [rsp+E0h] [rbp-60h]
  __int64 v23; // [rsp+E8h] [rbp-58h]
  __int64 v24; // [rsp+F0h] [rbp-50h]
  __int64 v25; // [rsp+F8h] [rbp-48h]
  __int64 v26; // [rsp+100h] [rbp-40h]
  HANDLE hFile; // [rsp+108h] [rbp-38h]
  _OWORD ProcessInformation[2]; // [rsp+110h] [rbp-30h] BYREF
  __int128 v29; // [rsp+130h] [rbp-10h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+140h] [rbp+0h] BYREF
  int v31; // [rsp+144h] [rbp+4h]
  WCHAR FileName[266]; // [rsp+14Ch] [rbp+Ch] BYREF

  v25 = a3;
  v23 = a2;
  v26 = a1;
  v24 = a4;
  v5 = 1;
  KeyHandle = 0;
  HIDWORD(Buffer) = 0;
  LODWORD(v20) = 0;
  NumberOfBytesWritten = 0;
  LOWORD(Buffer) = -257;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v29 = 0;
  LODWORD(FileW) = NtOpenKey(&KeyHandle, 1u, (POBJECT_ATTRIBUTES)&stru_180067100);
  if ( (int)FileW >= 0 )
  {
    ValueKey = NtQueryValueKey(
                 KeyHandle,
                 (PUNICODE_STRING)&stru_180067130,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0x218u,
                 (PULONG)&NumberOfBytesWritten + 1);
    LODWORD(FileW) = NtClose(KeyHandle);
    if ( ValueKey >= 0 && v31 == 1 )
    {
      FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 4u, 0, 0);
      v8 = -1;
      hFile = FileW;
      v9 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        SetFilePointer(FileW, 0, 0, 0);
        WriteFile(v9, &Buffer, 2u, (LPDWORD)&NumberOfBytesWritten, 0);
        SetFilePointer(v9, 0, 0, 2u);
        if ( NtQueryInformationProcess(
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               ProcessImageFileName,
               KeyValueInformation,
               0x218u,
               (PULONG)&Buffer + 1) >= 0 )
        {
          v10 = HIDWORD(Buffer);
          HIDWORD(Buffer) = 1;
          v11 = &KeyValueInformation[v10 - 2];
          if ( &KeyValueInformation[v10 - 2] > KeyValueInformation )
          {
            v12 = 1;
            do
            {
              v5 = v12;
              if ( *((_WORD *)v11 - 1) == 92 )
                break;
              v5 = v12 + 1;
              v11 -= 2;
              HIDWORD(Buffer) = ++v12;
            }
            while ( v11 > KeyValueInformation );
          }
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)(a1 + 2 * v13) );
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)(v23 + 2 * v14) );
          if ( NtQueryInformationProcess(
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 ProcessBasicInformation,
                 ProcessInformation,
                 0x30u,
                 (PULONG)&v20) >= 0 )
          {
            ProcessHeap = NtCurrentPeb()->ProcessHeap;
            BufferCount = (unsigned int)(v5 + 2 * (v14 + v13 + 121));
            Heap = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, BufferCount);
            if ( Heap )
            {
              BufferCount >>= 1;
              swprintf_s(
                Heap,
                BufferCount,
                L"%s%s%Id%s%s%s%s%s%s%s{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\r\n",
                v11,
                L" (PID = ",
                (_QWORD)v29,
                L") identified ",
                v26,
                L" as ",
                v23,
                L" using ",
                v25,
                L" rule, Guid = ",
                *(_DWORD *)v24,
                *(unsigned __int16 *)(v24 + 4),
                *(unsigned __int16 *)(v24 + 6),
                *(unsigned __int8 *)(v24 + 8),
                *(unsigned __int8 *)(v24 + 9),
                *(unsigned __int8 *)(v24 + 10),
                *(unsigned __int8 *)(v24 + 11),
                *(unsigned __int8 *)(v24 + 12),
                *(unsigned __int8 *)(v24 + 13),
                *(unsigned __int8 *)(v24 + 14),
                *(unsigned __int8 *)(v24 + 15),
                Buffer,
                NumberOfBytesWritten,
                v20);
              do
                ++v8;
              while ( Heap[v8] );
              v9 = hFile;
              WriteFile(hFile, Heap, 2 * v8, (LPDWORD)&NumberOfBytesWritten, 0);
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            }
          }
        }
        LODWORD(FileW) = CloseHandle(v9);
      }
    }
  }
  return (int)FileW;
}

```

## disassembly

```asm
0x180011548  push    rbp
0x18001154a  push    rbx
0x18001154b  push    rsi
0x18001154c  push    rdi
0x18001154d  push    r12
0x18001154f  push    r13
0x180011551  push    r14
0x180011553  push    r15
0x180011555  lea     rbp, [rsp-238h]
0x18001155d  sub     rsp, 378h
0x180011564  mov     rax, cs:__security_cookie
0x18001156b  xor     rax, rsp
0x18001156e  mov     [rbp+270h+var_50], rax
0x180011575  xor     esi, esi
0x180011577  mov     [rbp+270h+var_2B8], r8
0x18001157b  xorps   xmm0, xmm0
0x18001157e  mov     [rbp+270h+var_2C8], rdx
0x180011582  mov     r12, rcx
0x180011585  mov     [rbp+270h+var_2B0], rcx
0x180011589  lea     r8, stru_180067100; ObjectAttributes
0x180011590  mov     [rbp+270h+var_2C0], r9
0x180011594  lea     edi, [rsi+1]
0x180011597  mov     [rbp+270h+KeyHandle], rsi
0x18001159b  mov     edx, edi; DesiredAccess
0x18001159d  mov     [rbp+270h+ReturnLength], esi
0x1800115a0  lea     rcx, [rbp+270h+KeyHandle]; KeyHandle
0x1800115a4  mov     dword ptr [rbp+270h+var_2E0], esi
0x1800115a7  mov     [rbp+270h+NumberOfBytesWritten], esi
0x1800115aa  mov     [rbp+270h+Buffer], 0FEFFh
0x1800115b0  movups  [rbp+270h+ProcessInformation], xmm0
0x1800115b4  mov     [rbp+270h+var_2E4], esi
0x1800115b7  movups  [rbp+270h+var_290], xmm0
0x1800115bb  movups  [rbp+270h+var_280], xmm0
0x1800115bf  call    cs:__imp_NtOpenKey
0x1800115c5  test    eax, eax
0x1800115c7  js      short loc_180011606
0x1800115c9  mov     rcx, [rbp+270h+KeyHandle]; KeyHandle
0x1800115cd  lea     rax, [rbp+270h+var_2E4]
0x1800115d1  mov     [rsp+3B0h+ResultLength], rax; ResultLength
0x1800115d6  lea     r13d, [rsi+2]
0x1800115da  mov     r8d, r13d; KeyValueInformationClass
0x1800115dd  mov     [rsp+3B0h+Length], 218h; Length
0x1800115e5  lea     r9, [rbp+270h+KeyValueInformation]; KeyValueInformation
0x1800115e9  lea     rdx, stru_180067130; ValueName
0x1800115f0  call    cs:__imp_NtQueryValueKey
0x1800115f6  mov     rcx, [rbp+270h+KeyHandle]; Handle
0x1800115fa  mov     ebx, eax
0x1800115fc  call    cs:__imp_NtClose
0x180011602  test    ebx, ebx
0x180011604  jns     short loc_180011629
0x180011606  mov     rcx, [rbp+270h+var_50]
0x18001160d  xor     rcx, rsp; StackCookie
0x180011610  call    __security_check_cookie
0x180011615  add     rsp, 378h
0x18001161c  pop     r15
0x18001161e  pop     r14
0x180011620  pop     r13
0x180011622  pop     r12
0x180011624  pop     rdi
0x180011625  pop     rsi
0x180011626  pop     rbx
0x180011627  pop     rbp
0x180011628  retn
0x180011629  cmp     [rbp+270h+var_26C], edi
0x18001162c  jnz     short loc_180011606
0x18001162e  mov     [rsp+3B0h+hTemplateFile], rsi; hTemplateFile
0x180011633  lea     rcx, [rbp+270h+FileName]; lpFileName
0x180011637  mov     dword ptr [rsp+3B0h+ResultLength], esi; dwFlagsAndAttributes
0x18001163b  xor     r9d, r9d; lpSecurityAttributes
0x18001163e  xor     r8d, r8d; dwShareMode
0x180011641  mov     [rsp+3B0h+Length], 4; dwCreationDisposition
0x180011649  mov     edx, 40000000h; dwDesiredAccess
0x18001164e  call    cs:__imp_CreateFileW
0x180011654  or      r15, 0FFFFFFFFFFFFFFFFh
0x180011658  mov     [rbp+270h+hFile], rax
0x18001165c  mov     r14, rax
0x18001165f  cmp     rax, r15
0x180011662  jz      short loc_180011606
0x180011664  xor     r9d, r9d; dwMoveMethod
0x180011667  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001166a  xor     edx, edx; lDistanceToMove
0x18001166c  mov     rcx, rax; hFile
0x18001166f  call    cs:__imp_SetFilePointer
0x180011675  lea     r9, [rbp+270h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180011679  mov     qword ptr [rsp+3B0h+Length], rsi; lpOverlapped
0x18001167e  mov     r8d, r13d; nNumberOfBytesToWrite
0x180011681  lea     rdx, [rbp+270h+Buffer]; lpBuffer
0x180011685  mov     rcx, r14; hFile
0x180011688  call    cs:__imp_WriteFile
0x18001168e  mov     r9d, r13d; dwMoveMethod
0x180011691  xor     r8d, r8d; lpDistanceToMoveHigh
0x180011694  xor     edx, edx; lDistanceToMove
0x180011696  mov     rcx, r14; hFile
0x180011699  call    cs:__imp_SetFilePointer
0x18001169f  lea     rax, [rbp+270h+ReturnLength]
0x1800116a3  mov     r9d, 218h; ProcessInformationLength
0x1800116a9  lea     r8, [rbp+270h+KeyValueInformation]; ProcessInformation
0x1800116ad  mov     qword ptr [rsp+3B0h+Length], rax; ReturnLength
0x1800116b2  lea     edx, [r15+1Ch]; ProcessInformationClass
0x1800116b6  mov     rcx, r15; ProcessHandle
0x1800116b9  call    cs:__imp_NtQueryInformationProcess
0x1800116bf  test    eax, eax
0x1800116c1  js      loc_1800118A9
0x1800116c7  mov     eax, [rbp+270h+ReturnLength]
0x1800116ca  mov     [rbp+270h+ReturnLength], edi
0x1800116cd  lea     r13, [rbp+rax+270h+var_280+0Eh]
0x1800116d2  lea     rax, [rbp+270h+KeyValueInformation]
0x1800116d6  cmp     r13, rax
0x1800116d9  jbe     short loc_1800116FC
0x1800116db  mov     eax, edi
0x1800116dd  cmp     word ptr [r13-2], 5Ch ; '\'
0x1800116e3  mov     edi, eax
0x1800116e5  jz      short loc_1800116FC
0x1800116e7  lea     edi, [rax+1]
0x1800116ea  add     r13, 0FFFFFFFFFFFFFFFEh
0x1800116ee  lea     rcx, [rbp+270h+KeyValueInformation]
0x1800116f2  mov     [rbp+270h+ReturnLength], edi
0x1800116f5  mov     eax, edi
0x1800116f7  cmp     r13, rcx
0x1800116fa  ja      short loc_1800116DD
0x1800116fc  mov     rsi, r15
0x1800116ff  xor     ecx, ecx
0x180011701  inc     rsi
0x180011704  cmp     [r12+rsi*2], cx
0x180011709  jnz     short loc_180011701
0x18001170b  mov     rax, [rbp+270h+var_2C8]
0x18001170f  mov     rbx, r15
0x180011712  inc     rbx
0x180011715  cmp     [rax+rbx*2], cx
0x180011719  jnz     short loc_180011712
0x18001171b  lea     rax, [rbp+270h+var_2E0]
0x18001171f  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180011725  lea     r8, [rbp+270h+ProcessInformation]; ProcessInformation
0x180011729  mov     qword ptr [rsp+3B0h+Length], rax; ReturnLength
0x18001172e  xor     edx, edx; ProcessInformationClass
0x180011730  mov     rcx, r15; ProcessHandle
0x180011733  call    cs:__imp_NtQueryInformationProcess
0x180011739  test    eax, eax
0x18001173b  js      loc_1800118A9
0x180011741  mov     rcx, gs:60h
0x18001174a  lea     eax, [rsi+79h]
0x18001174d  add     eax, ebx
0x18001174f  xor     edx, edx; Flags
0x180011751  mov     rcx, [rcx+30h]; HeapHandle
0x180011755  lea     eax, [rdi+rax*2]
0x180011758  mov     r8d, eax; Size
0x18001175b  mov     [rbp+270h+BufferCount], rax
0x18001175f  call    cs:__imp_RtlAllocateHeap
0x180011765  mov     r12, rax
0x180011768  test    rax, rax
0x18001176b  jz      loc_1800118A9
0x180011771  mov     rax, [rbp+270h+var_2C0]
0x180011775  shr     [rbp+270h+BufferCount], 1
0x180011779  movzx   ecx, byte ptr [rax+0Fh]
0x18001177d  movzx   edx, byte ptr [rax+0Eh]
0x180011781  movzx   r8d, byte ptr [rax+0Dh]
0x180011786  movzx   r9d, byte ptr [rax+0Ch]
0x18001178b  movzx   r10d, byte ptr [rax+0Bh]
0x180011790  movzx   r11d, byte ptr [rax+0Ah]
0x180011795  movzx   ebx, byte ptr [rax+9]
0x180011799  movzx   edi, byte ptr [rax+8]
0x18001179d  movzx   esi, word ptr [rax+6]
0x1800117a1  movzx   r14d, word ptr [rax+4]
0x1800117a6  mov     eax, [rax]
0x1800117a8  mov     [rsp+3B0h+var_2F8], ecx
0x1800117af  mov     rcx, r12; Buffer
0x1800117b2  mov     [rsp+3B0h+var_300], edx
0x1800117b9  mov     rdx, [rbp+270h+BufferCount]; BufferCount
0x1800117bd  mov     [rsp+3B0h+var_308], r8d
0x1800117c5  lea     r8, aSSIdSSSSSSS08l; "%s%s%Id%s%s%s%s%s%s%s{%08lx-%04x-%04x-%"...
0x1800117cc  mov     [rsp+3B0h+var_310], r9d
0x1800117d4  mov     r9, r13
0x1800117d7  mov     [rsp+3B0h+var_318], r10d
0x1800117df  mov     [rsp+3B0h+var_320], r11d
0x1800117e7  mov     [rsp+3B0h+var_328], ebx
0x1800117ee  mov     [rsp+3B0h+var_330], edi
0x1800117f5  mov     [rsp+3B0h+var_338], esi
0x1800117f9  mov     [rsp+3B0h+var_340], r14d
0x1800117fe  mov     [rsp+3B0h+var_348], eax
0x180011802  lea     rax, aRuleGuid; " rule, Guid = "
0x180011809  mov     [rsp+3B0h+var_350], rax
0x18001180e  mov     rax, [rbp+270h+var_2B8]
0x180011812  mov     [rsp+3B0h+var_358], rax
0x180011817  lea     rax, aUsing; " using "
0x18001181e  mov     [rsp+3B0h+var_360], rax
0x180011823  mov     rax, [rbp+270h+var_2C8]
0x180011827  mov     [rsp+3B0h+var_368], rax
0x18001182c  lea     rax, aAs; " as "
0x180011833  mov     [rsp+3B0h+var_370], rax
0x180011838  mov     rax, [rbp+270h+var_2B0]
0x18001183c  mov     [rsp+3B0h+var_378], rax
0x180011841  lea     rax, aIdentified; ") identified "
0x180011848  mov     [rsp+3B0h+hTemplateFile], rax
0x18001184d  mov     rax, qword ptr [rbp+270h+var_280]
0x180011851  mov     [rsp+3B0h+ResultLength], rax
0x180011856  lea     rax, aPid; " (PID = "
0x18001185d  mov     qword ptr [rsp+3B0h+Length], rax
0x180011862  call    cs:__imp_swprintf_s
0x180011868  xor     eax, eax
0x18001186a  inc     r15
0x18001186d  cmp     [r12+r15*2], ax
0x180011872  jnz     short loc_18001186A
0x180011874  mov     r14, [rbp+270h+hFile]
0x180011878  lea     r8d, [r15+r15]; nNumberOfBytesToWrite
0x18001187c  mov     rcx, r14; hFile
0x18001187f  mov     qword ptr [rsp+3B0h+Length], rax; lpOverlapped
0x180011884  lea     r9, [rbp+270h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180011888  mov     rdx, r12; lpBuffer
0x18001188b  call    cs:__imp_WriteFile
0x180011891  mov     rcx, gs:60h
0x18001189a  mov     r8, r12; P
0x18001189d  xor     edx, edx; Flags
0x18001189f  mov     rcx, [rcx+30h]; HeapHandle
0x1800118a3  call    cs:__imp_RtlFreeHeap
0x1800118a9  mov     rcx, r14; hObject
0x1800118ac  call    cs:__imp_CloseHandle
0x1800118b2  jmp     loc_180011606
```
