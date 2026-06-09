# Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateForWindow(Windows::Internal::ApplicationModel::WindowManagement::WindowId,Windows::Graphics::Capture::Server::ICapturableItem * *)

- ea: `0x1800162d0`
- end: `0x180016368`
- name: `?TryCreateForWindow@CapturableItemStatics@Server@Capture@Graphics@Windows@@UEAAJUWindowId@WindowManagement@ApplicationModel@Internal@5@PEAPEAUICapturableItem@2345@@Z`
- size: `152`
- prototype: `int __high(struct Windows::Internal::ApplicationModel::WindowManagement::WindowId, struct Windows::Graphics::Capture::Server::ICapturableItem **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000907c`
- `0x18000f0d8`
- `0x1800162d0`
- `0x180016dc4`
- `0x18001e5e4`

## string_xrefs

- `0x180016304`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016335`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateForWindow(
        __int64 a1,
        bool *a2,
        unsigned __int64 *a3)
{
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int v6; // edi
  int ItemFromInternalWindowId; // eax
  unsigned int v9; // ebx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v12; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  v12 = 0;
  v4 = (unsigned int)a2;
  v5 = Windows::Graphics::Capture::Server::AllowAppSiloAndFailUapAndInsufficientIL(
         (Windows::Graphics::Capture::Server *)&v12,
         a2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    ItemFromInternalWindowId = Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromInternalWindowId(
                                 v4,
                                 v12,
                                 a3);
    v9 = ItemFromInternalWindowId;
    if ( ItemFromInternalWindowId >= 0 )
    {
      Windows::Graphics::Capture::GraphicsCaptureProvider::CaptureFunctionWin32(0, 0);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26E,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)ItemFromInternalWindowId,
        v10);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26C,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v5,
      v10);
    return v6;
  }
}

```

## disassembly

```asm
0x1800162d0  mov     rax, rsp
0x1800162d3  mov     [rax+8], rbx
0x1800162d7  mov     [rax+10h], rsi
0x1800162db  push    rdi; int
0x1800162dc  sub     rsp, 20h
0x1800162e0  lea     rcx, [rax+18h]; this
0x1800162e4  mov     qword ptr [r8], 0
0x1800162eb  mov     rsi, r8
0x1800162ee  mov     byte ptr [rax+18h], 0
0x1800162f2  mov     ebx, edx
0x1800162f4  call    ?AllowAppSiloAndFailUapAndInsufficientIL@Server@Capture@Graphics@Windows@@YAJPEA_N@Z; Windows::Graphics::Capture::Server::AllowAppSiloAndFailUapAndInsufficientIL(bool *)
0x1800162f9  mov     edi, eax
0x1800162fb  test    eax, eax
0x1800162fd  jns     short loc_18001631C
0x1800162ff  mov     rcx, [rsp+28h]; this
0x180016304  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001630b  mov     r9d, eax; char *
0x18001630e  mov     edx, 26Ch; void *
0x180016313  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016318  mov     eax, edi
0x18001631a  jmp     short loc_180016358
0x18001631c  mov     dl, [rsp+28h+arg_10]
0x180016320  mov     r8, rsi
0x180016323  mov     ecx, ebx
0x180016325  call    Windows__Graphics__Capture__Server___anonymous_namespace___TryCreateItemFromInternalWindowId
0x18001632a  mov     ebx, eax
0x18001632c  test    eax, eax
0x18001632e  jns     short loc_18001634D
0x180016330  mov     rcx, [rsp+28h]; this
0x180016335  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001633c  mov     r9d, eax; char *
0x18001633f  mov     edx, 26Eh; void *
0x180016344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016349  mov     eax, ebx
0x18001634b  jmp     short loc_180016358
0x18001634d  xor     edx, edx; int
0x18001634f  xor     ecx, ecx; unsigned int
0x180016351  call    ?CaptureFunctionWin32@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAXIJ@Z; Windows::Graphics::Capture::GraphicsCaptureProvider::CaptureFunctionWin32(uint,long)
0x180016356  xor     eax, eax
0x180016358  mov     rbx, [rsp+28h+arg_0]
0x18001635d  mov     rsi, [rsp+28h+arg_8]
0x180016362  add     rsp, 20h
0x180016366  pop     rdi
0x180016367  retn
```
