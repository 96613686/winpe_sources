# Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,bool,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus *)

- ea: `0x18001e964`
- end: `0x18001e9cc`
- name: `?CheckCAMCapability@Server@Capture@Graphics@Windows@@YAJW4CaptureServerAccessRequestKind@1234@_NPEAW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@4@@Z`
- size: `104`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019eb0`
- `0x18001e5e4`
- `0x18001e9d4`

## callees

- `0x18000907c`
- `0x18001e748`
- `0x18001e964`
- `0x18001f208`

## string_xrefs

- `0x18001e999`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::CheckCAMCapability(unsigned int a1, unsigned int *a2, int *a3)
{
  char v5; // si
  int ClientProcessId; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v11; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 3;
  v11 = 0;
  v5 = (char)a2;
  ClientProcessId = Windows::Graphics::Capture::Server::GetClientProcessId(
                      (Windows::Graphics::Capture::Server *)&v11,
                      a2);
  v7 = ClientProcessId;
  if ( ClientProcessId >= 0 )
    return Windows::Graphics::Capture::Server::CheckCAMCapability(a1, v5, v11, a3);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B5,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
    (const char *)(unsigned int)ClientProcessId,
    v9);
  return v7;
}

```

## disassembly

```asm
0x18001e964  push    rbx
0x18001e966  push    rbp
0x18001e967  push    rsi
0x18001e968  push    rdi
0x18001e969  sub     rsp, 28h
0x18001e96d  mov     ebp, ecx
0x18001e96f  mov     dword ptr [r8], 3
0x18001e976  lea     rcx, [rsp+48h+arg_10]; this
0x18001e97b  mov     [rsp+48h+arg_10], 0
0x18001e983  mov     rdi, r8
0x18001e986  mov     sil, dl
0x18001e989  call    ?GetClientProcessId@Server@Capture@Graphics@Windows@@YAJPEAK@Z; Windows::Graphics::Capture::Server::GetClientProcessId(ulong *)
0x18001e98e  mov     ebx, eax
0x18001e990  test    eax, eax
0x18001e992  jns     short loc_18001E9B1
0x18001e994  mov     rcx, [rsp+48h]; this
0x18001e999  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001e9a0  mov     r9d, eax; char *
0x18001e9a3  mov     edx, 1B5h; void *
0x18001e9a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9ad  mov     eax, ebx
0x18001e9af  jmp     short loc_18001E9C3
0x18001e9b1  mov     r8d, [rsp+48h+arg_10]
0x18001e9b6  mov     r9, rdi
0x18001e9b9  mov     dl, sil
0x18001e9bc  mov     ecx, ebp
0x18001e9be  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YAJW4CaptureServerAccessRequestKind@1234@_NKPEAW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@4@@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,bool,ulong,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus *)
0x18001e9c3  add     rsp, 28h
0x18001e9c7  pop     rdi
0x18001e9c8  pop     rsi
0x18001e9c9  pop     rbp
0x18001e9ca  pop     rbx
0x18001e9cb  retn
```
