# AscDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18000adb0`
- end: `0x18000ae41`
- name: `?AscDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `145`
- prototype: `__int64 __fastcall(HINSTANCE hLibModule, int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000abb0`

## callees

- `0x18000adb0`
- `0x18000f8dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000ae30`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000ae30`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000adc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000adc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add3`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ae1d`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ae1d`

## string_xrefs

- `0x18000ade1`: `com\complus\dtc\dtc\asc\ascmain.cpp`

## pseudocode

```c
__int64 __fastcall AscDllMain(HINSTANCE hLibModule, int a2, void *a3)
{
  DWORD LastError; // eax
  void *v6; // [rsp+50h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 == 1 )
    {
      g_iTls = TlsAlloc();
      if ( g_iTls == -1 )
      {
        LastError = GetLastError();
        DELLog(0, 1u, 8u, 0xC0001072, LastError, 1, 0, 0, "com\\complus\\dtc\\dtc\\asc\\ascmain.cpp", 43, v6);
        return 0;
      }
      DisableThreadLibraryCalls(hLibModule);
    }
  }
  else if ( g_iTls != -1 )
  {
    TlsFree(g_iTls);
  }
  return 1;
}

```

## disassembly

```asm
0x18000adb0  push    rbx
0x18000adb2  sub     rsp, 60h
0x18000adb6  mov     rbx, rcx
0x18000adb9  test    edx, edx
0x18000adbb  jz      short loc_18000AE25
0x18000adbd  cmp     edx, 1
0x18000adc0  jnz     short loc_18000AE36
0x18000adc2  call    cs:__imp_TlsAlloc
0x18000adc8  mov     cs:?g_iTls@@3KA, eax; ulong g_iTls
0x18000adce  cmp     eax, 0FFFFFFFFh
0x18000add1  jnz     short loc_18000AE1A
0x18000add3  call    cs:__imp_GetLastError
0x18000add9  mov     [rsp+68h+var_20], 2Bh ; '+'; int
0x18000ade1  lea     rcx, aComComplusDtcD_17; "com\\complus\\dtc\\dtc\\asc\\ascmain.cp"...
0x18000ade8  mov     [rsp+68h+var_28], rcx; char *
0x18000aded  mov     edx, 1; unsigned __int16
0x18000adf2  xor     ecx, ecx; struct ITmInstance *
0x18000adf4  mov     r8d, 8; unsigned __int16
0x18000adfa  mov     [rsp+68h+var_30], rcx; void *
0x18000adff  mov     r9d, 0C0001072h; unsigned int
0x18000ae05  mov     [rsp+68h+var_38], ecx; unsigned int
0x18000ae09  mov     [rsp+68h+var_40], edx; int
0x18000ae0d  mov     [rsp+68h+var_48], eax; int
0x18000ae11  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x18000ae16  xor     eax, eax
0x18000ae18  jmp     short loc_18000AE3B
0x18000ae1a  mov     rcx, rbx; hLibModule
0x18000ae1d  call    cs:__imp_DisableThreadLibraryCalls
0x18000ae23  jmp     short loc_18000AE36
0x18000ae25  mov     ecx, cs:?g_iTls@@3KA; dwTlsIndex
0x18000ae2b  cmp     ecx, 0FFFFFFFFh
0x18000ae2e  jz      short loc_18000AE36
0x18000ae30  call    cs:__imp_TlsFree
0x18000ae36  mov     eax, 1
0x18000ae3b  add     rsp, 60h
0x18000ae3f  pop     rbx
0x18000ae40  retn
```
