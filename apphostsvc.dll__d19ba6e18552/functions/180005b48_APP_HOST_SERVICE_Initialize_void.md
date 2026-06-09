# APP_HOST_SERVICE::Initialize(void)

- ea: `0x180005b48`
- end: `0x180005c34`
- name: `?Initialize@APP_HOST_SERVICE@@QEAAJXZ`
- size: `236`
- prototype: `__int64 __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180006ad0`

## callees

- `0x180001008`
- `0x180005b48`
- `0x180008c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005b70`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005bb7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005b70`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005bb7`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180005c07`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180005c07`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall APP_HOST_SERVICE::Initialize(APP_HOST_SERVICE *this)
{
  APP_HOST_SERVICE *v1; // rbx
  HANDLE EventW; // rax
  signed int result; // eax
  HANDLE v4; // rax
  ALLOC_CACHE_HANDLER *v5; // rax
  _DWORD v6[4]; // [rsp+28h] [rbp-20h] BYREF

  v1 = g_pAppHostService;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v1 + 30) = EventW;
  if ( EventW && (v4 = CreateEventW(0, 1, 0, 0), (*((_QWORD *)v1 + 2) = v4) != 0) )
  {
    v6[0] = 0;
    v6[2] = 48;
    v6[1] = 250;
    v5 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
    if ( v5 )
      v5 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
             v5,
             "MULTI_WORK_ITEM",
             (const struct ALLOC_CACHE_CONFIGURATION *)v6,
             1);
    MULTI_WORK_ITEM::sm_pAllocCacheHandler = v5;
    return v5 == 0 ? 0x8007000E : 0;
  }
  else if ( GetLastError() )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180005b48  push    rbx
0x180005b4a  sub     rsp, 40h
0x180005b4e  mov     rax, cs:__security_cookie
0x180005b55  xor     rax, rsp
0x180005b58  mov     [rsp+48h+var_10], rax
0x180005b5d  mov     rbx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x180005b64  xor     r9d, r9d; lpName
0x180005b67  xor     r8d, r8d; bInitialState
0x180005b6a  lea     edx, [r9+1]; bManualReset
0x180005b6e  xor     ecx, ecx; lpEventAttributes
0x180005b70  call    cs:__imp_CreateEventW
0x180005b76  mov     [rbx+0F0h], rax
0x180005b7d  test    rax, rax
0x180005b80  jnz     short loc_180005BAB
0x180005b82  call    cs:__imp_GetLastError
0x180005b88  test    eax, eax
0x180005b8a  jz      short loc_180005BA4
0x180005b8c  call    cs:__imp_GetLastError
0x180005b92  test    eax, eax
0x180005b94  jle     loc_180005C21
0x180005b9a  movzx   eax, ax
0x180005b9d  or      eax, 80070000h
0x180005ba2  jmp     short loc_180005C21
0x180005ba4  mov     eax, 80004005h
0x180005ba9  jmp     short loc_180005C21
0x180005bab  xor     r9d, r9d; lpName
0x180005bae  xor     r8d, r8d; bInitialState
0x180005bb1  lea     edx, [r9+1]; bManualReset
0x180005bb5  xor     ecx, ecx; lpEventAttributes
0x180005bb7  call    cs:__imp_CreateEventW
0x180005bbd  mov     [rbx+10h], rax
0x180005bc1  test    rax, rax
0x180005bc4  jz      short loc_180005B82
0x180005bc6  mov     [rsp+48h+var_20], 0
0x180005bce  mov     [rsp+48h+var_18], 30h ; '0'
0x180005bd6  mov     [rsp+48h+var_1C], 0FAh
0x180005bde  mov     ecx, 100h; Size
0x180005be3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005be8  mov     [rsp+48h+var_28], rax
0x180005bed  test    rax, rax
0x180005bf0  jz      short loc_180005C0E
0x180005bf2  mov     r9d, 1
0x180005bf8  lea     r8, [rsp+48h+var_20]
0x180005bfd  lea     rdx, aMultiWorkItem; "MULTI_WORK_ITEM"
0x180005c04  mov     rcx, rax
0x180005c07  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180005c0d  nop
0x180005c0e  mov     cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x180005c15  neg     rax
0x180005c18  sbb     eax, eax
0x180005c1a  not     eax
0x180005c1c  and     eax, 8007000Eh
0x180005c21  mov     rcx, [rsp+48h+var_10]
0x180005c26  xor     rcx, rsp; StackCookie
0x180005c29  call    __security_check_cookie
0x180005c2e  add     rsp, 40h
0x180005c32  pop     rbx
0x180005c33  retn
```
