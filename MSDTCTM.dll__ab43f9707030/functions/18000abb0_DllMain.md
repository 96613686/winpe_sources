# DllMain

- ea: `0x18000abb0`
- end: `0x18000ad9c`
- name: `DllMain`
- size: `492`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800243d4`

## callees

- `0x18000abb0`
- `0x18000adb0`
- `0x18000ed90`
- `0x18000f8dc`
- `0x18000fe74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000ad38`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000ad38`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000ac98`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000ac98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aca9`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000acf6`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000acff`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000acf6`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000acff`
- `ntdll!RtlImageNtHeader` at `0x18000abd9`
- `ntdll!RtlImageNtHeader` at `0x18000abd9`

## string_xrefs

- `0x18000acb7`: `com\complus\dtc\dtc\asc\ascmain.cpp`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  PIMAGE_NT_HEADERS v5; // rax
  PIMAGE_NT_HEADERS v6; // r8
  __int64 v7; // rax
  __int64 GuaranteedStackBytes; // rax
  DWORD LastError; // eax
  void *v11; // r8
  void *v12; // [rsp+50h] [rbp-18h]

  if ( !fdwReason )
    return AscDllMain(hinstDLL, 0, lpvReserved) != 0;
  v5 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  v6 = v5;
  if ( NtCurrentPeb()->BeingDebugged )
  {
    v7 = 0;
  }
  else
  {
    if ( v5 && v5->OptionalHeader.SizeOfStackReserve - v5->OptionalHeader.SizeOfStackCommit < 0x3000 )
    {
      g_ulMaxStackAllocSize = 0;
      goto LABEL_9;
    }
    v7 = 526;
  }
  g_ulMaxStackAllocSize = v7;
  if ( !v6 )
    goto LABEL_12;
LABEL_9:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( GuaranteedStackBytes )
  {
    if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
      goto LABEL_13;
LABEL_12:
    g_ulAdditionalProbeSize = -9;
    goto LABEL_13;
  }
  g_ulAdditionalProbeSize = 12288;
LABEL_13:
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  g_pfnFree = (__int64)SafeAllocaFreeToHeap;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_iTls = TlsAlloc();
      if ( g_iTls == -1 )
      {
        LastError = GetLastError();
        DELLog(0, 1u, 8u, 0xC0001072, LastError, 1, 0, 0, "com\\complus\\dtc\\dtc\\asc\\ascmain.cpp", 43, v12);
        return 0;
      }
      DisableThreadLibraryCalls(hinstDLL);
      DisableThreadLibraryCalls(hinstDLL);
      TcpCm_hProxyDll = (__int64)hinstDLL;
      GwTx_hProxyDll = (__int64)hinstDLL;
      qword_180168098 = (__int64)hinstDLL;
      if ( !hinstDLL )
        return 0;
    }
    if ( fdwReason == 1 )
      Sm_hProxyDll = (__int64)hinstDLL;
  }
  else if ( g_iTls != -1 )
  {
    TlsFree(g_iTls);
  }
  if ( !(unsigned int)UisDllMain(hinstDLL, fdwReason, v6) || !(unsigned int)MapTxDllMain(hinstDLL, fdwReason, v11) )
    return 0;
  if ( fdwReason == 1 )
    TipConn_hProxyDll = (__int64)hinstDLL;
  return 1;
}

```

## disassembly

```asm
0x18000abb0  mov     [rsp+arg_0], rbx
0x18000abb5  mov     [rsp+arg_8], rsi
0x18000abba  push    rdi
0x18000abbb  sub     rsp, 60h
0x18000abbf  mov     ebx, edx
0x18000abc1  mov     rdi, rcx
0x18000abc4  test    edx, edx
0x18000abc6  jz      loc_18000AD7B
0x18000abcc  mov     rcx, gs:60h
0x18000abd5  mov     rcx, [rcx+10h]; BaseAddress
0x18000abd9  call    cs:__imp_RtlImageNtHeader
0x18000abdf  mov     rdx, gs:60h
0x18000abe8  xor     esi, esi
0x18000abea  mov     r8, rax
0x18000abed  cmp     [rdx+2], sil
0x18000abf1  jz      short loc_18000ABF7
0x18000abf3  mov     eax, esi
0x18000abf5  jmp     short loc_18000AC1A
0x18000abf7  test    r8, r8
0x18000abfa  jz      short loc_18000AC15
0x18000abfc  mov     rax, [rax+60h]
0x18000ac00  sub     rax, [r8+68h]
0x18000ac04  cmp     rax, 3000h
0x18000ac0a  jnb     short loc_18000AC15
0x18000ac0c  mov     cs:g_ulMaxStackAllocSize, rsi
0x18000ac13  jmp     short loc_18000AC26
0x18000ac15  mov     eax, 20Eh
0x18000ac1a  mov     cs:g_ulMaxStackAllocSize, rax
0x18000ac21  test    r8, r8
0x18000ac24  jz      short loc_18000AC58
0x18000ac26  mov     rax, gs:30h
0x18000ac2f  mov     eax, [rax+1748h]
0x18000ac35  mov     cs:g_ulAdditionalProbeSize, rax
0x18000ac3c  test    rax, rax
0x18000ac3f  jnz     short loc_18000AC4E
0x18000ac41  mov     cs:g_ulAdditionalProbeSize, 3000h
0x18000ac4c  jmp     short loc_18000AC63
0x18000ac4e  add     rax, 8
0x18000ac52  cmp     rax, 8
0x18000ac56  jnb     short loc_18000AC63
0x18000ac58  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18000ac63  lea     rax, SafeAllocaAllocateFromHeap
0x18000ac6a  mov     cs:g_pfnAllocate, rax
0x18000ac71  lea     rax, SafeAllocaFreeToHeap
0x18000ac78  mov     cs:g_pfnFree, rax
0x18000ac7f  mov     eax, ebx
0x18000ac81  test    ebx, ebx
0x18000ac83  jz      loc_18000AD2D
0x18000ac89  cmp     eax, 1
0x18000ac8c  jz      short loc_18000AC98
0x18000ac8e  cmp     ebx, 1
0x18000ac91  jz      short loc_18000ACFC
0x18000ac93  jmp     loc_18000AD1F
0x18000ac98  call    cs:__imp_TlsAlloc
0x18000ac9e  mov     cs:?g_iTls@@3KA, eax; ulong g_iTls
0x18000aca4  cmp     eax, 0FFFFFFFFh
0x18000aca7  jnz     short loc_18000ACF3
0x18000aca9  call    cs:__imp_GetLastError
0x18000acaf  mov     [rsp+68h+var_20], 2Bh ; '+'; int
0x18000acb7  lea     rcx, aComComplusDtcD_17; "com\\complus\\dtc\\dtc\\asc\\ascmain.cp"...
0x18000acbe  mov     [rsp+68h+var_28], rcx; char *
0x18000acc3  mov     edx, 1; unsigned __int16
0x18000acc8  mov     [rsp+68h+var_30], rsi; void *
0x18000accd  mov     r8d, 8; unsigned __int16
0x18000acd3  mov     [rsp+68h+var_38], esi; unsigned int
0x18000acd7  xor     ecx, ecx; struct ITmInstance *
0x18000acd9  mov     [rsp+68h+var_40], edx; int
0x18000acdd  mov     r9d, 0C0001072h; unsigned int
0x18000ace3  mov     [rsp+68h+var_48], eax; int
0x18000ace7  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x18000acec  xor     eax, eax
0x18000acee  jmp     loc_18000AD8C
0x18000acf3  mov     rcx, rdi; hLibModule
0x18000acf6  call    cs:__imp_DisableThreadLibraryCalls
0x18000acfc  mov     rcx, rdi; hLibModule
0x18000acff  call    cs:__imp_DisableThreadLibraryCalls
0x18000ad05  mov     cs:TcpCm_hProxyDll, rdi
0x18000ad0c  mov     cs:GwTx_hProxyDll, rdi
0x18000ad13  mov     cs:qword_180168098, rdi
0x18000ad1a  test    rdi, rdi
0x18000ad1d  jz      short loc_18000ACEC
0x18000ad1f  cmp     ebx, 1
0x18000ad22  jnz     short loc_18000AD3E
0x18000ad24  mov     cs:Sm_hProxyDll, rdi
0x18000ad2b  jmp     short loc_18000AD3E
0x18000ad2d  mov     ecx, cs:?g_iTls@@3KA; dwTlsIndex
0x18000ad33  cmp     ecx, 0FFFFFFFFh
0x18000ad36  jz      short loc_18000AD3E
0x18000ad38  call    cs:__imp_TlsFree
0x18000ad3e  mov     edx, ebx; unsigned int
0x18000ad40  mov     rcx, rdi; HINSTANCE
0x18000ad43  call    ?UisDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z; UisDllMain(HINSTANCE__ *,ulong,void *)
0x18000ad48  test    eax, eax
0x18000ad4a  jz      short loc_18000ACEC
0x18000ad4c  mov     edx, ebx; unsigned int
0x18000ad4e  mov     rcx, rdi; HINSTANCE
0x18000ad51  call    ?MapTxDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z; MapTxDllMain(HINSTANCE__ *,ulong,void *)
0x18000ad56  test    eax, eax
0x18000ad58  jz      short loc_18000ACEC
0x18000ad5a  cmp     ebx, 1
0x18000ad5d  jnz     short loc_18000AD66
0x18000ad5f  mov     cs:TipConn_hProxyDll, rdi
0x18000ad66  mov     eax, 1
0x18000ad6b  mov     rbx, [rsp+68h+arg_0]
0x18000ad70  mov     rsi, [rsp+68h+arg_8]
0x18000ad75  add     rsp, 60h
0x18000ad79  pop     rdi
0x18000ad7a  retn
0x18000ad7b  xor     edx, edx; unsigned int
0x18000ad7d  call    ?AscDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z; AscDllMain(HINSTANCE__ *,ulong,void *)
0x18000ad82  xor     esi, esi
0x18000ad84  test    eax, eax
0x18000ad86  setnz   sil
0x18000ad8a  mov     eax, esi
0x18000ad8c  mov     rbx, [rsp+68h+arg_0]
0x18000ad91  mov     rsi, [rsp+68h+arg_8]
0x18000ad96  add     rsp, 60h
0x18000ad9a  pop     rdi
0x18000ad9b  retn
```
