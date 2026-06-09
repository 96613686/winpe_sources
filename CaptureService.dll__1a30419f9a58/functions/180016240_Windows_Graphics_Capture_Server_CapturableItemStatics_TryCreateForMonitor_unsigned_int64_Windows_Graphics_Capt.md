# Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateForMonitor(unsigned __int64,Windows::Graphics::Capture::Server::ICapturableItem * *)

- ea: `0x180016240`
- end: `0x1800162c5`
- name: `?TryCreateForMonitor@CapturableItemStatics@Server@Capture@Graphics@Windows@@UEAAJ_KPEAPEAUICapturableItem@2345@@Z`
- size: `133`
- prototype: `int(Windows::Graphics::Capture::Server::CapturableItemStatics *__hidden this, unsigned __int64, struct Windows::Graphics::Capture::Server::ICapturableItem **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000907c`
- `0x18000f0d8`
- `0x180016240`
- `0x1800169d8`
- `0x18001e5e4`

## string_xrefs

- `0x18001627a`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateForMonitor(
        Windows::Graphics::Capture::Server::CapturableItemStatics *this,
        bool *a2,
        struct Windows::Graphics::Capture::Server::ICapturableItem **a3)
{
  int ItemFromHmonitor; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v10; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  v10 = 0;
  ItemFromHmonitor = Windows::Graphics::Capture::Server::AllowAppSiloAndFailUapAndInsufficientIL(
                       (Windows::Graphics::Capture::Server *)&v10,
                       a2);
  if ( ItemFromHmonitor < 0 )
  {
    v6 = 639;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)ItemFromHmonitor,
      v8);
    return (unsigned int)ItemFromHmonitor;
  }
  ItemFromHmonitor = Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromHmonitor(
                       (__int64)a2,
                       v10,
                       (unsigned __int64 *)a3);
  if ( ItemFromHmonitor < 0 )
  {
    v6 = 641;
    goto LABEL_3;
  }
  Windows::Graphics::Capture::GraphicsCaptureProvider::CaptureFunctionWin32(1, 0);
  return 0;
}

```

## disassembly

```asm
0x180016240  mov     rax, rsp
0x180016243  mov     [rax+8], rbx
0x180016247  mov     [rax+10h], rsi
0x18001624b  push    rdi; int
0x18001624c  sub     rsp, 20h
0x180016250  lea     rcx, [rax+18h]; this
0x180016254  mov     qword ptr [r8], 0
0x18001625b  mov     rdi, r8
0x18001625e  mov     byte ptr [rax+18h], 0
0x180016262  mov     rsi, rdx
0x180016265  call    ?AllowAppSiloAndFailUapAndInsufficientIL@Server@Capture@Graphics@Windows@@YAJPEA_N@Z; Windows::Graphics::Capture::Server::AllowAppSiloAndFailUapAndInsufficientIL(bool *)
0x18001626a  mov     ebx, eax
0x18001626c  test    eax, eax
0x18001626e  jns     short loc_18001628D
0x180016270  mov     edx, 27Fh; void *
0x180016275  mov     rcx, [rsp+28h]; this
0x18001627a  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016281  mov     r9d, ebx; char *
0x180016284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016289  mov     eax, ebx
0x18001628b  jmp     short loc_1800162B5
0x18001628d  mov     dl, [rsp+28h+arg_10]
0x180016291  mov     r8, rdi
0x180016294  mov     rcx, rsi
0x180016297  call    Windows__Graphics__Capture__Server___anonymous_namespace___TryCreateItemFromHmonitor
0x18001629c  mov     ebx, eax
0x18001629e  test    eax, eax
0x1800162a0  jns     short loc_1800162A9
0x1800162a2  mov     edx, 281h
0x1800162a7  jmp     short loc_180016275
0x1800162a9  xor     edx, edx; int
0x1800162ab  lea     ecx, [rdx+1]; unsigned int
0x1800162ae  call    ?CaptureFunctionWin32@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAXIJ@Z; Windows::Graphics::Capture::GraphicsCaptureProvider::CaptureFunctionWin32(uint,long)
0x1800162b3  xor     eax, eax
0x1800162b5  mov     rbx, [rsp+28h+arg_0]
0x1800162ba  mov     rsi, [rsp+28h+arg_8]
0x1800162bf  add     rsp, 20h
0x1800162c3  pop     rdi
0x1800162c4  retn
```
