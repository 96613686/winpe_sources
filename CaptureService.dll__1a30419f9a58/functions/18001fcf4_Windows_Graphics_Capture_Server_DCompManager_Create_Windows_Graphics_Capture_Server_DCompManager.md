# Windows::Graphics::Capture::Server::DCompManager::Create(Windows::Graphics::Capture::Server::DCompManager * *)

- ea: `0x18001fcf4`
- end: `0x18001fd87`
- name: `?Create@DCompManager@Server@Capture@Graphics@Windows@@SAJPEAPEAV12345@@Z`
- size: `147`
- prototype: `static int(struct Windows::Graphics::Capture::Server::DCompManager **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bb10`

## callees

- `0x180003488`
- `0x18000907c`
- `0x18001fc90`
- `0x18001fcf4`
- `0x18001fd90`

## string_xrefs

- `0x18001fd4a`: `onecoreuap\windows\dwm\capture\svc\dll\dcompmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::DCompManager::Create(
        struct Windows::Graphics::Capture::Server::DCompManager **a1)
{
  Windows::Graphics::Capture::Server::DCompManager *v2; // rbx
  int v3; // eax
  unsigned int v4; // edi
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  Windows::Graphics::Capture::Server::DCompManager *v8; // [rsp+38h] [rbp+10h] BYREF

  v2 = (Windows::Graphics::Capture::Server::DCompManager *)operator new(0x18u);
  *(_QWORD *)v2 = 0;
  *((_QWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 2) = 0;
  v8 = v2;
  v3 = Windows::Graphics::Capture::Server::DCompManager::Initialize(v2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v8 = 0;
    *a1 = v2;
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\dcompmanager.cpp",
      (const char *)(unsigned int)v3,
      v6);
  }
  std::unique_ptr<Windows::Graphics::Capture::Server::DCompManager>::~unique_ptr<Windows::Graphics::Capture::Server::DCompManager>(&v8);
  return v4;
}

```

## disassembly

```asm
0x18001fcf4  mov     [rsp+arg_0], rbx
0x18001fcf9  mov     [rsp+arg_10], rsi
0x18001fcfe  push    rdi; int
0x18001fcff  sub     rsp, 20h
0x18001fd03  mov     rsi, rcx
0x18001fd06  mov     ecx, 18h; Size
0x18001fd0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fd10  mov     rbx, rax
0x18001fd13  mov     [rsp+28h+arg_8], rax
0x18001fd18  mov     qword ptr [rax], 0
0x18001fd1f  mov     qword ptr [rax+8], 0
0x18001fd27  mov     qword ptr [rax+10h], 0
0x18001fd2f  mov     [rsp+28h+arg_8], rax
0x18001fd34  mov     rcx, rax; this
0x18001fd37  call    ?Initialize@DCompManager@Server@Capture@Graphics@Windows@@IEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Initialize(void)
0x18001fd3c  mov     edi, eax
0x18001fd3e  test    eax, eax
0x18001fd40  jns     short loc_18001FD5D
0x18001fd42  mov     rcx, [rsp+28h]; this
0x18001fd47  mov     r9d, eax; char *
0x18001fd4a  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001fd51  mov     edx, 17h; void *
0x18001fd56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd5b  jmp     short loc_18001FD6B
0x18001fd5d  mov     [rsp+28h+arg_8], 0
0x18001fd66  mov     [rsi], rbx
0x18001fd69  xor     edi, edi
0x18001fd6b  lea     rcx, [rsp+28h+arg_8]
0x18001fd70  call    ??1?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Graphics::Capture::Server::DCompManager>::~unique_ptr<Windows::Graphics::Capture::Server::DCompManager>(void)
0x18001fd75  mov     eax, edi
0x18001fd77  mov     rbx, [rsp+28h+arg_0]
0x18001fd7c  mov     rsi, [rsp+28h+arg_10]
0x18001fd81  add     rsp, 20h
0x18001fd85  pop     rdi
0x18001fd86  retn
```
