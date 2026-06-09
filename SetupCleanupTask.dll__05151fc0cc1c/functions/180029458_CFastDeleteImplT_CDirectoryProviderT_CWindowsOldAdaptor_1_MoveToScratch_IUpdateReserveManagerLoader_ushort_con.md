# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::MoveToScratch(IUpdateReserveManagerLoader *,ushort const *)

- ea: `0x180029458`
- end: `0x180029549`
- name: `?MoveToScratch@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAVIUpdateReserveManagerLoader@@PEBG@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800276e8`

## callees

- `0x18000638c`
- `0x180029458`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294c0`
- `WDSCORE!CurrentIP` at `0x1800294c8`
- `WDSCORE!CurrentIP` at `0x1800294c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029531`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029531`

## string_xrefs

- `0x18002951a`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x1800294f0`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::MoveToScratch`
- `0x1800294d1`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::MoveToScratch Failed to move [%s] to Scratch directory. status: %x`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::MoveToScratch(
        __int64 a1,
        const char *a2)
{
  __int64 v4; // rax
  int v5; // ebp
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax

  if ( !a1 || !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) || !a2 )
    return 1;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, const char *))(*(_QWORD *)v4 + 88LL))(v4, 6, 6, a2);
  if ( v5 < 0 )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           50331648,
           "CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::MoveToScratch Failed to move [%s] to"
           " Scratch directory. status: %x",
           a2,
           v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      1620,
      L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
      L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::MoveToScratch",
      v7,
      LastError,
      0,
      0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180029458  push    rbx
0x18002945a  push    rbp
0x18002945b  push    rsi
0x18002945c  push    rdi
0x18002945d  sub     rsp, 68h
0x180029461  mov     rsi, rdx
0x180029464  mov     rbx, rcx
0x180029467  test    rcx, rcx
0x18002946a  jz      loc_18002953B
0x180029470  mov     rax, [rcx]
0x180029473  mov     rax, [rax+8]
0x180029477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002947c  test    rax, rax
0x18002947f  jz      loc_18002953B
0x180029485  test    rsi, rsi
0x180029488  jz      loc_18002953B
0x18002948e  mov     rax, [rbx]
0x180029491  mov     rcx, rbx
0x180029494  mov     rax, [rax+8]
0x180029498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002949d  mov     r10, rax
0x1800294a0  mov     edx, 6
0x1800294a5  mov     r9, rsi
0x1800294a8  mov     r8d, edx
0x1800294ab  mov     rcx, [rax]
0x1800294ae  mov     rax, [rcx+58h]
0x1800294b2  mov     rcx, r10
0x1800294b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294ba  mov     ebp, eax
0x1800294bc  test    eax, eax
0x1800294be  jns     short loc_180029537
0x1800294c0  call    cs:__imp_GetLastError
0x1800294c6  mov     edi, eax
0x1800294c8  call    cs:__imp_CurrentIP
0x1800294ce  mov     r9d, ebp
0x1800294d1  lea     rdx, aCfastdeleteimp_0; "CFastDeleteImplT<class CDirectoryProvid"...
0x1800294d8  mov     r8, rsi
0x1800294db  mov     ecx, 3000000h; unsigned int
0x1800294e0  mov     rbx, rax
0x1800294e3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800294e8  mov     [rsp+88h+var_38], 0
0x1800294f0  lea     rcx, aCfastdeleteimp_3; "CFastDeleteImplT<class CDirectoryProvid"...
0x1800294f7  mov     [rsp+88h+var_40], 0
0x180029500  lea     r8, aD_0; "D"
0x180029507  mov     [rsp+88h+var_48], edi
0x18002950b  xor     r9d, r9d
0x18002950e  mov     [rsp+88h+var_50], rbx
0x180029513  xor     edx, edx
0x180029515  mov     [rsp+88h+var_58], rcx
0x18002951a  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x180029521  mov     [rsp+88h+var_60], rcx
0x180029526  mov     rcx, rax
0x180029529  mov     [rsp+88h+var_68], 654h
0x180029531  call    cs:__imp_WdsSetupLogMessageW
0x180029537  mov     eax, ebp
0x180029539  jmp     short loc_180029540
0x18002953b  mov     eax, 1
0x180029540  add     rsp, 68h
0x180029544  pop     rdi
0x180029545  pop     rsi
0x180029546  pop     rbp
0x180029547  pop     rbx
0x180029548  retn
```
