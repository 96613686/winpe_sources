# CleanupWinHttpEvents

- ea: `0x18004b394`
- end: `0x18004b45d`
- name: `CleanupWinHttpEvents`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004ed50`

## callees

- `0x180049d1c`
- `0x18004a1bc`
- `0x18004a954`
- `0x18004b394`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b44b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b44b`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18004b41c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18004b43e`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18004b41c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18004b43e`

## pseudocode

```c
void __fastcall CleanupWinHttpEvents(__int64 a1, __int64 a2)
{
  REGHANDLE v2; // rcx
  REGHANDLE v3; // rcx

  if ( byte_180066498 )
  {
    LOBYTE(a2) = 1;
    qword_18007D7A8 = 0;
    UploadHttpEvents(0, a2);
    qword_180066728 = 0;
    qword_18007D7A0 = 0;
    CacheOrUploadHttpRequestSuccess(0, 0, 0, 0, 0, 0, 1);
    CacheOrUploadOnBoxRequestFailure(0, 0, 0, 0, 1);
    v2 = qword_180065308;
    dword_1800652E8 = 0;
    qword_180065308 = 0;
    EventUnregister(v2);
    v3 = qword_1800652D0;
    dword_1800652B0 = 0;
    qword_1800652D0 = 0;
    EventUnregister(v3);
    DeleteCriticalSection(&stru_180066690);
    byte_180066498 = 0;
  }
}

```

## disassembly

```asm
0x18004b394  sub     rsp, 48h
0x18004b398  cmp     cs:byte_180066498, 0
0x18004b39f  jz      loc_18004B458
0x18004b3a5  mov     dl, 1
0x18004b3a7  mov     cs:qword_18007D7A8, 0
0x18004b3b2  xor     ecx, ecx
0x18004b3b4  call    _UploadHttpEvents
0x18004b3b9  xor     edx, edx
0x18004b3bb  mov     [rsp+48h+var_18], 1
0x18004b3c0  mov     [rsp+48h+var_20], edx
0x18004b3c4  xor     r9d, r9d
0x18004b3c7  xor     r8d, r8d
0x18004b3ca  mov     [rsp+48h+var_28], rdx
0x18004b3cf  xor     ecx, ecx
0x18004b3d1  mov     cs:qword_180066728, 0
0x18004b3dc  mov     cs:qword_18007D7A0, 0
0x18004b3e7  call    _CacheOrUploadHttpRequestSuccess
0x18004b3ec  xor     r9d, r9d
0x18004b3ef  mov     byte ptr [rsp+48h+var_28], 1
0x18004b3f4  xor     r8d, r8d
0x18004b3f7  xor     edx, edx
0x18004b3f9  xor     ecx, ecx
0x18004b3fb  call    _CacheOrUploadOnBoxRequestFailure
0x18004b400  mov     rcx, cs:qword_180065308; RegHandle
0x18004b407  mov     cs:dword_1800652E8, 0
0x18004b411  mov     cs:qword_180065308, 0
0x18004b41c  call    cs:__imp_EventUnregister
0x18004b422  mov     rcx, cs:qword_1800652D0; RegHandle
0x18004b429  mov     cs:dword_1800652B0, 0
0x18004b433  mov     cs:qword_1800652D0, 0
0x18004b43e  call    cs:__imp_EventUnregister
0x18004b444  lea     rcx, stru_180066690; lpCriticalSection
0x18004b44b  call    cs:__imp_DeleteCriticalSection
0x18004b451  mov     cs:byte_180066498, 0
0x18004b458  add     rsp, 48h
0x18004b45c  retn
```
