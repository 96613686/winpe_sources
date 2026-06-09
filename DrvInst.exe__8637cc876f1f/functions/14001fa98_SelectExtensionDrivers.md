# SelectExtensionDrivers

- ea: `0x14001fa98`
- end: `0x14001fbe6`
- name: `SelectExtensionDrivers`
- size: `334`
- prototype: `__int64 __fastcall(int, int, int, wchar_t *String1, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14001e944`

## callees

- `0x140001b64`
- `0x14001fa98`
- `0x140026844`
- `0x1400268e4`
- `0x14002c2bc`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001fba5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001fba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001faee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fb4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001faee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fb4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001fbb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001fbb5`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001fb82`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001fb82`

## string_xrefs

- `0x14001fb78`: `Failed to select extension drivers for device. Error = 0x%08X`

## pseudocode

```c
_BOOL8 __fastcall SelectExtensionDrivers(
        struct HDRIVERSTORE__ *a1,
        DEVINST a2,
        __int64 a3,
        wchar_t *String1,
        __int64 *a5,
        unsigned __int64 a6)
{
  struct _DRVUTILS_UPDATE_INFO *UpdateInfo; // rdi
  DWORD LastError; // ebx
  void *v12; // r8
  int v14; // [rsp+30h] [rbp-2A8h]
  unsigned __int64 v15; // [rsp+48h] [rbp-290h]
  __int64 v16; // [rsp+60h] [rbp-278h] BYREF
  wchar_t String2[264]; // [rsp+70h] [rbp-268h] BYREF

  v16 = 0;
  UpdateInfo = (struct _DRVUTILS_UPDATE_INFO *)DrvUtilsCreateUpdateInfo(a1, String1, a3, 0);
  if ( !UpdateInfo )
  {
    LastError = GetLastError();
    goto LABEL_12;
  }
  LastError = 2;
  LODWORD(v15) = 260;
  if ( PnpUtilsSelectDriverForDevNode(a1, a2, a3, 2, UpdateInfo, &v16, v14, 0, String2, v15, a6) )
  {
    if ( !wcsicmp_0(String1, String2) )
    {
      LastError = 0;
      *a5 = v16;
      v12 = 0;
      goto LABEL_9;
    }
    DevRtlWriteTextLog(a6, 1, 1, "Failed to select extension drivers for device. Error = 0x%08X", 2);
  }
  else
  {
    LastError = GetLastError();
  }
  v12 = (void *)v16;
LABEL_9:
  if ( v12 )
    HeapFree(hHeap, 0, v12);
  DrvUtilsDestroyUpdateInfo(UpdateInfo);
LABEL_12:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x14001fa98  push    rbx
0x14001fa9a  push    rbp
0x14001fa9b  push    rsi
0x14001fa9c  push    rdi
0x14001fa9d  push    r12
0x14001fa9f  push    r13
0x14001faa1  push    r14
0x14001faa3  push    r15
0x14001faa5  sub     rsp, 298h
0x14001faac  mov     rax, cs:__security_cookie
0x14001fab3  xor     rax, rsp
0x14001fab6  mov     [rsp+2D8h+var_58], rax
0x14001fabe  mov     r14, [rsp+2D8h+arg_20]
0x14001fac6  mov     rbp, r9
0x14001fac9  mov     r12d, edx
0x14001facc  mov     [rsp+2D8h+var_278], 0
0x14001fad5  mov     rdx, rbp
0x14001fad8  xor     r9d, r9d
0x14001fadb  mov     r13, r8
0x14001fade  mov     r15, rcx
0x14001fae1  call    DrvUtilsCreateUpdateInfo
0x14001fae6  mov     rdi, rax
0x14001fae9  test    rax, rax
0x14001faec  jnz     short loc_14001FAFB
0x14001faee  call    cs:__imp_GetLastError
0x14001faf4  mov     ebx, eax
0x14001faf6  jmp     loc_14001FBB3
0x14001fafb  mov     rsi, [rsp+2D8h+arg_28]
0x14001fb03  lea     rax, [rsp+2D8h+String2]
0x14001fb08  mov     [rsp+2D8h+var_288], rsi; unsigned __int64
0x14001fb0d  mov     ebx, 2
0x14001fb12  mov     dword ptr [rsp+2D8h+var_290], 104h; unsigned __int64
0x14001fb1a  mov     r9d, ebx; int
0x14001fb1d  mov     [rsp+2D8h+var_298], rax; __int64
0x14001fb22  mov     r8, r13; int
0x14001fb25  lea     rax, [rsp+2D8h+var_278]
0x14001fb2a  mov     [rsp+2D8h+var_2A0], 0; __int64
0x14001fb33  mov     [rsp+2D8h+var_2B0], rax; __int64
0x14001fb38  mov     edx, r12d; int
0x14001fb3b  mov     rcx, r15; int
0x14001fb3e  mov     [rsp+2D8h+var_2B8], rdi; struct _DRVUTILS_UPDATE_INFO *
0x14001fb43  call    PnpUtilsSelectDriverForDevNode
0x14001fb48  test    eax, eax
0x14001fb4a  jnz     short loc_14001FB5B
0x14001fb4c  call    cs:__imp_GetLastError
0x14001fb52  mov     ebx, eax
0x14001fb54  mov     r8, [rsp+2D8h+var_278]
0x14001fb59  jmp     short loc_14001FB97
0x14001fb5b  lea     rdx, [rsp+2D8h+String2]; String2
0x14001fb60  mov     rcx, rbp; String1
0x14001fb63  call    _wcsicmp_0
0x14001fb68  test    eax, eax
0x14001fb6a  jz      short loc_14001FB8A
0x14001fb6c  mov     edx, 1
0x14001fb71  mov     dword ptr [rsp+2D8h+var_2B8], ebx
0x14001fb75  mov     r8d, edx
0x14001fb78  lea     r9, aFailedToSelect_3; "Failed to select extension drivers for "...
0x14001fb7f  mov     rcx, rsi
0x14001fb82  call    cs:__imp_DevRtlWriteTextLog
0x14001fb88  jmp     short loc_14001FB54
0x14001fb8a  mov     rax, [rsp+2D8h+var_278]
0x14001fb8f  xor     ebx, ebx
0x14001fb91  mov     [r14], rax
0x14001fb94  xor     r8d, r8d; lpMem
0x14001fb97  test    r8, r8
0x14001fb9a  jz      short loc_14001FBAB
0x14001fb9c  mov     rcx, cs:hHeap; hHeap
0x14001fba3  xor     edx, edx; dwFlags
0x14001fba5  call    cs:__imp_HeapFree
0x14001fbab  mov     rcx, rdi; lpMem
0x14001fbae  call    DrvUtilsDestroyUpdateInfo
0x14001fbb3  mov     ecx, ebx; dwErrCode
0x14001fbb5  call    cs:__imp_SetLastError
0x14001fbbb  xor     eax, eax
0x14001fbbd  test    ebx, ebx
0x14001fbbf  setz    al
0x14001fbc2  mov     rcx, [rsp+2D8h+var_58]
0x14001fbca  xor     rcx, rsp; StackCookie
0x14001fbcd  call    __security_check_cookie
0x14001fbd2  add     rsp, 298h
0x14001fbd9  pop     r15
0x14001fbdb  pop     r14
0x14001fbdd  pop     r13
0x14001fbdf  pop     r12
0x14001fbe1  pop     rdi
0x14001fbe2  pop     rsi
0x14001fbe3  pop     rbp
0x14001fbe4  pop     rbx
0x14001fbe5  retn
```
