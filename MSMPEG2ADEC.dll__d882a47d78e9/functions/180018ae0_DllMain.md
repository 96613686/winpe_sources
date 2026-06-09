# DllMain

- ea: `0x180018ae0`
- end: `0x180018b66`
- name: `DllMain`
- size: `134`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001624`

## callees

- `0x180018ae0`
- `0x1800255f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018b28`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018b28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018b46`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018b46`
- `mfperfhelper!__imp_ippStaticInit` at `0x180018af4`
- `mfperfhelper!__imp_ippStaticInit` at `0x180018af4`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v5; // eax

  if ( fdwReason == 1 )
  {
    v5 = ippStaticInit(hinstDLL, fdwReason, lpvReserved);
    if ( v5 && v5 != 20 )
      return 0;
    g_lOneTimeInPlaceObfuscation = 0;
    InitializeCriticalSection(&g_csOneTimeInPlaceObfuscation);
  }
  else if ( !fdwReason && !lpvReserved )
  {
    DeleteCriticalSection(&g_csOneTimeInPlaceObfuscation);
  }
  return DllEntryPoint(hinstDLL, fdwReason);
}

```

## disassembly

```asm
0x180018ae0  mov     [rsp+arg_0], rbx
0x180018ae5  push    rdi
0x180018ae6  sub     rsp, 20h
0x180018aea  mov     ebx, edx
0x180018aec  mov     rdi, rcx
0x180018aef  cmp     edx, 1
0x180018af2  jnz     short loc_180018B36
0x180018af4  call    cs:__imp_ippStaticInit
0x180018afb  nop     dword ptr [rax+rax+00h]
0x180018b00  test    eax, eax
0x180018b02  jz      short loc_180018B17
0x180018b04  cmp     eax, 14h
0x180018b07  jz      short loc_180018B17
0x180018b09  xor     eax, eax
0x180018b0b  mov     rbx, [rsp+28h+arg_0]
0x180018b10  add     rsp, 20h
0x180018b14  pop     rdi
0x180018b15  retn
0x180018b17  lea     rcx, ?g_csOneTimeInPlaceObfuscation@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180018b1e  mov     cs:?g_lOneTimeInPlaceObfuscation@@3JA, 0; long g_lOneTimeInPlaceObfuscation
0x180018b28  call    cs:__imp_InitializeCriticalSection
0x180018b2f  nop     dword ptr [rax+rax+00h]
0x180018b34  jmp     short loc_180018B52
0x180018b36  test    ebx, ebx
0x180018b38  jnz     short loc_180018B52
0x180018b3a  test    r8, r8
0x180018b3d  jnz     short loc_180018B52
0x180018b3f  lea     rcx, ?g_csOneTimeInPlaceObfuscation@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180018b46  call    cs:__imp_DeleteCriticalSection
0x180018b4d  nop     dword ptr [rax+rax+00h]
0x180018b52  mov     edx, ebx
0x180018b54  mov     rcx, rdi
0x180018b57  mov     rbx, [rsp+28h+arg_0]
0x180018b5c  add     rsp, 20h
0x180018b60  pop     rdi
0x180018b61  jmp     _DllEntryPoint
```
