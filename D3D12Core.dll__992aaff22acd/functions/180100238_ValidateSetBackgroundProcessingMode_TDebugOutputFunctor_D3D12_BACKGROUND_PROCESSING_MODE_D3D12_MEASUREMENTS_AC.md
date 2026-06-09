# ValidateSetBackgroundProcessingMode(TDebugOutputFunctor &,D3D12_BACKGROUND_PROCESSING_MODE,D3D12_MEASUREMENTS_ACTION,bool,std::function<bool (void)>)

- ea: `0x180100238`
- end: `0x180100335`
- name: `?ValidateSetBackgroundProcessingMode@@YAJAEAUTDebugOutputFunctor@@W4D3D12_BACKGROUND_PROCESSING_MODE@@W4D3D12_MEASUREMENTS_ACTION@@_NV?$function@$$A6A_NXZ@std@@@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800fa870`

## callees

- `0x18002ef50`
- `0x180048644`
- `0x1800acdac`
- `0x180100238`

## import_xrefs

- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x1801002fd`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x1801002fd`

## string_xrefs

- `0x1801002d4`: `DISABLE_BACKGROUND_WORK, DISABLE_PROFILING_BY_SYSTEM, and COMMIT_RESULTS_HIGH_PRIORITY require developer mode.`
- `0x1801002a3`: `Can only signal completion event when committing results.`

## pseudocode

```c
__int64 __fastcall ValidateSetBackgroundProcessingMode(__int64 a1, int a2, int a3, char a4, __int64 a5)
{
  unsigned int v9; // ebx

  if ( a2 < 4 )
  {
    if ( a3 < 4 )
    {
      v9 = 0;
      if ( a4 && (unsigned int)(a3 - 1) > 1 )
      {
        TDebugOutputFunctor::operator()(a1, 1223, "Can only signal completion event when committing results.");
        v9 = -2147024809;
      }
      if ( ((unsigned int)(a2 - 2) <= 1 || a3 == 2) && !(unsigned __int8)std::_Func_class<bool,>::operator()(a5) )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1223,
          "DISABLE_BACKGROUND_WORK, DISABLE_PROFILING_BY_SYSTEM, and COMMIT_RESULTS_HIGH_PRIORITY require developer mode.");
        v9 = -2005270483;
      }
      if ( RtlIsCriticalSectionLockedByThread(NtCurrentPeb()->LoaderLock) )
      {
        TDebugOutputFunctor::operator()(a1, 1223, "Cannot set scheduling mode while the loader lock is held.");
        v9 = -2005270527;
      }
    }
    else
    {
      TDebugOutputFunctor::operator()(a1, 1223, "Invalid measurements action provided.");
      v9 = -2147024809;
    }
    std::function<PSVSignatureElement (unsigned int)>::~function<PSVSignatureElement (unsigned int)>(a5);
    return v9;
  }
  else
  {
    TDebugOutputFunctor::operator()(a1, 1223, "Invalid mode provided.");
    std::function<PSVSignatureElement (unsigned int)>::~function<PSVSignatureElement (unsigned int)>(a5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180100238  push    rbx
0x18010023a  push    rbp
0x18010023b  push    rsi
0x18010023c  push    rdi
0x18010023d  sub     rsp, 28h
0x180100241  mov     esi, r8d
0x180100244  mov     ebp, edx
0x180100246  mov     rdi, rcx
0x180100249  cmp     edx, 4
0x18010024c  jl      short loc_180100273
0x18010024e  lea     r8, aInvalidModePro; "Invalid mode provided."
0x180100255  mov     edx, 4C7h
0x18010025a  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18010025f  mov     rcx, [rsp+48h+arg_20]
0x180100264  call    ??1?$function@$$A6A?AVPSVSignatureElement@@I@Z@std@@QEAA@XZ; std::function<PSVSignatureElement (uint)>::~function<PSVSignatureElement (uint)>(void)
0x180100269  mov     eax, 80070057h
0x18010026e  jmp     loc_18010032C
0x180100273  cmp     esi, 4
0x180100276  jl      short loc_180100293
0x180100278  lea     r8, aInvalidMeasure; "Invalid measurements action provided."
0x18010027f  mov     edx, 4C7h
0x180100284  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180100289  mov     ebx, 80070057h
0x18010028e  jmp     loc_180100320
0x180100293  xor     ebx, ebx
0x180100295  test    r9b, r9b
0x180100298  jz      short loc_1801002B9
0x18010029a  lea     eax, [r8-1]
0x18010029e  cmp     eax, 1
0x1801002a1  jbe     short loc_1801002B9
0x1801002a3  lea     r8, aCanOnlySignalC; "Can only signal completion event when c"...
0x1801002aa  mov     edx, 4C7h
0x1801002af  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801002b4  mov     ebx, 80070057h
0x1801002b9  lea     eax, [rbp-2]
0x1801002bc  cmp     eax, 1
0x1801002bf  jbe     short loc_1801002C6
0x1801002c1  cmp     esi, 2
0x1801002c4  jnz     short loc_1801002ED
0x1801002c6  mov     rcx, [rsp+48h+arg_20]
0x1801002cb  call    ??R?$_Func_class@_N$$V@std@@QEBA_NXZ; std::_Func_class<bool,>::operator()(void)
0x1801002d0  test    al, al
0x1801002d2  jnz     short loc_1801002ED
0x1801002d4  lea     r8, aDisableBackgro; "DISABLE_BACKGROUND_WORK, DISABLE_PROFIL"...
0x1801002db  mov     edx, 4C7h
0x1801002e0  mov     rcx, rdi
0x1801002e3  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801002e8  mov     ebx, 887A002Dh
0x1801002ed  mov     rcx, gs:60h
0x1801002f6  mov     rcx, [rcx+110h]; CriticalSection
0x1801002fd  call    cs:__imp_RtlIsCriticalSectionLockedByThread
0x180100303  test    eax, eax
0x180100305  jz      short loc_180100320
0x180100307  lea     r8, aCannotSetSched; "Cannot set scheduling mode while the lo"...
0x18010030e  mov     edx, 4C7h
0x180100313  mov     rcx, rdi
0x180100316  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18010031b  mov     ebx, 887A0001h
0x180100320  mov     rcx, [rsp+48h+arg_20]
0x180100325  call    ??1?$function@$$A6A?AVPSVSignatureElement@@I@Z@std@@QEAA@XZ; std::function<PSVSignatureElement (uint)>::~function<PSVSignatureElement (uint)>(void)
0x18010032a  mov     eax, ebx
0x18010032c  add     rsp, 28h
0x180100330  pop     rdi
0x180100331  pop     rsi
0x180100332  pop     rbp
0x180100333  pop     rbx
0x180100334  retn
```
