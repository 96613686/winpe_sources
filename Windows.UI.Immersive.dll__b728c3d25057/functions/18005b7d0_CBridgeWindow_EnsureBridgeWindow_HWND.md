# CBridgeWindow::_EnsureBridgeWindow(HWND__ *)

- ea: `0x18005b7d0`
- end: `0x18005b9e3`
- name: `?_EnsureBridgeWindow@CBridgeWindow@@AEAAJPEAUHWND__@@@Z`
- size: `531`
- prototype: `int(CBridgeWindow *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005bc0c`

## callees

- `0x180013244`
- `0x18003aa84`
- `0x180051524`
- `0x18005b7d0`
- `0x1800dd9e8`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005b80c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005b89c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005b80c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005b89c`
- `USER32!CreateWindowExW` at `0x18005b9a8`
- `USER32!CreateWindowExW` at `0x18005b9a8`
- `USER32!RegisterClassW` at `0x18005b936`
- `USER32!RegisterClassW` at `0x18005b936`
- `USER32!GetAncestor` at `0x18005b8d2`
- `USER32!GetAncestor` at `0x18005b8d2`
- `USER32!LoadCursorW` at `0x18005b915`
- `USER32!LoadCursorW` at `0x18005b915`

## pseudocode

```c
__int64 __fastcall CBridgeWindow::_EnsureBridgeWindow(CBridgeWindow *this, HWND Ancestor)
{
  int Error; // ebx
  HANDLE Event; // rax
  HANDLE v6; // rax
  HCURSOR CursorW; // rax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-9h] BYREF
  __int64 (__fastcall ***v10)(_QWORD, GUID *, char *); // [rsp+D0h] [rbp+67h] BYREF

  if ( *((_QWORD *)this + 14) )
  {
    return 0;
  }
  else
  {
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    *((_QWORD *)this + 47) = Event;
    if ( Event || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease((char *)this + 328);
      *((_QWORD *)this + 41) = 0;
      v10 = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v10);
      Error = Microsoft::WRL::Details::MakeAndInitialize<CPlaybackManager,CPlaybackManager,>(&v10);
      if ( Error >= 0 )
        Error = (**v10)(v10, &GUID_1fc98738_e0bf_4cb2_9de2_20ab31b23ce4, (char *)this + 328);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v10);
      if ( Error >= 0 )
      {
        v6 = CreateEventExW(0, 0, 0, 0x1F0003u);
        *((_QWORD *)this + 48) = v6;
        Error = v6 ? 0 : ResultFromKnownLastError();
        if ( Error >= 0 )
        {
          if ( *((_BYTE *)this + 392) )
            Ancestor = GetAncestor(Ancestor, 2u);
          memset_0(&WndClass, 0, sizeof(WndClass));
          WndClass.style = 3;
          WndClass.lpfnWndProc = (WNDPROC)CImpWndProc::s_WndProc;
          WndClass.cbWndExtra = 8;
          WndClass.hInstance = &_ImageBase;
          CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
          WndClass.hbrBackground = (HBRUSH)6;
          WndClass.hCursor = CursorW;
          WndClass.lpszClassName = L"ApplicationHostBridgeWindow";
          RegisterClassW(&WndClass);
          if ( CreateWindowExW(
                 0x200000u,
                 WndClass.lpszClassName,
                 0,
                 0x80000000,
                 *((_DWORD *)this + 37),
                 *((_DWORD *)this + 38),
                 *((_DWORD *)this + 39) - *((_DWORD *)this + 37),
                 *((_DWORD *)this + 40) - *((_DWORD *)this + 38),
                 Ancestor,
                 0,
                 &_ImageBase,
                 (LPVOID)(((unsigned __int64)this + 104) & -(__int64)(this != 0))) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
              return (unsigned int)Error;
          }
          *((_QWORD *)this + 22) = Ancestor;
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005b7d0  mov     [rsp-8+arg_8], rbx
0x18005b7d5  mov     [rsp-8+arg_10], rsi
0x18005b7da  push    rbp
0x18005b7db  push    rdi
0x18005b7dc  push    r14
0x18005b7de  lea     rbp, [rsp-47h]
0x18005b7e3  sub     rsp, 0B0h
0x18005b7ea  cmp     qword ptr [rcx+70h], 0
0x18005b7ef  mov     rsi, rdx
0x18005b7f2  mov     rdi, rcx
0x18005b7f5  jz      short loc_18005B7FE
0x18005b7f7  xor     ebx, ebx
0x18005b7f9  jmp     loc_18005B9C9
0x18005b7fe  xor     edx, edx; lpName
0x18005b800  xor     ecx, ecx; lpEventAttributes
0x18005b802  mov     r9d, 1F0003h; dwDesiredAccess
0x18005b808  lea     r8d, [rdx+1]; dwFlags
0x18005b80c  call    cs:__imp_CreateEventExW
0x18005b812  mov     [rdi+178h], rax
0x18005b819  test    rax, rax
0x18005b81c  jnz     short loc_18005B82D
0x18005b81e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005b823  mov     ebx, eax
0x18005b825  test    eax, eax
0x18005b827  js      loc_18005B9C9
0x18005b82d  lea     r14, [rdi+148h]
0x18005b834  mov     rcx, r14
0x18005b837  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005b83c  lea     rcx, [rbp+57h+arg_0]
0x18005b840  mov     qword ptr [r14], 0
0x18005b847  mov     [rbp+57h+arg_0], 0
0x18005b84f  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005b854  lea     rcx, [rbp+57h+arg_0]
0x18005b858  call    ??$MakeAndInitialize@VCPlaybackManager@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCPlaybackManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CPlaybackManager,CPlaybackManager,>(CPlaybackManager * *)
0x18005b85d  mov     ebx, eax
0x18005b85f  test    eax, eax
0x18005b861  js      short loc_18005B87E
0x18005b863  mov     rcx, [rbp+57h+arg_0]
0x18005b867  lea     rdx, _GUID_1fc98738_e0bf_4cb2_9de2_20ab31b23ce4
0x18005b86e  mov     r8, r14
0x18005b871  mov     rax, [rcx]
0x18005b874  mov     rax, [rax]
0x18005b877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b87c  mov     ebx, eax
0x18005b87e  lea     rcx, [rbp+57h+arg_0]
0x18005b882  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005b887  test    ebx, ebx
0x18005b889  js      loc_18005B9C9
0x18005b88f  mov     r9d, 1F0003h; dwDesiredAccess
0x18005b895  xor     r8d, r8d; dwFlags
0x18005b898  xor     edx, edx; lpName
0x18005b89a  xor     ecx, ecx; lpEventAttributes
0x18005b89c  call    cs:__imp_CreateEventExW
0x18005b8a2  mov     [rdi+180h], rax
0x18005b8a9  test    rax, rax
0x18005b8ac  jnz     short loc_18005B8B7
0x18005b8ae  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005b8b3  mov     ebx, eax
0x18005b8b5  jmp     short loc_18005B8B9
0x18005b8b7  xor     ebx, ebx
0x18005b8b9  test    ebx, ebx
0x18005b8bb  js      loc_18005B9C9
0x18005b8c1  cmp     byte ptr [rdi+188h], 0
0x18005b8c8  jz      short loc_18005B8DB
0x18005b8ca  mov     edx, 2; gaFlags
0x18005b8cf  mov     rcx, rsi; hwnd
0x18005b8d2  call    cs:__imp_GetAncestor
0x18005b8d8  mov     rsi, rax
0x18005b8db  xor     edx, edx; Val
0x18005b8dd  lea     rcx, [rbp+57h+WndClass]; void *
0x18005b8e1  lea     r8d, [rdx+48h]; Size
0x18005b8e5  call    memset_0
0x18005b8ea  lea     rax, ?s_WndProc@CImpWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18005b8f1  mov     [rbp+57h+WndClass.style], 3
0x18005b8f8  lea     rbx, __ImageBase
0x18005b8ff  mov     [rbp+57h+WndClass.lpfnWndProc], rax
0x18005b903  mov     edx, 7F00h; lpCursorName
0x18005b908  mov     [rbp+57h+WndClass.cbWndExtra], 8
0x18005b90f  xor     ecx, ecx; hInstance
0x18005b911  mov     [rbp+57h+WndClass.hInstance], rbx
0x18005b915  call    cs:__imp_LoadCursorW
0x18005b91b  lea     rcx, [rbp+57h+WndClass]; lpWndClass
0x18005b91f  mov     [rbp+57h+WndClass.hbrBackground], 6
0x18005b927  mov     [rbp+57h+WndClass.hCursor], rax
0x18005b92b  lea     rax, aApplicationhos; "ApplicationHostBridgeWindow"
0x18005b932  mov     [rbp+57h+WndClass.lpszClassName], rax
0x18005b936  call    cs:__imp_RegisterClassW
0x18005b93c  mov     r8d, [rdi+98h]
0x18005b943  lea     rcx, [rdi+68h]
0x18005b947  mov     r9d, [rdi+94h]
0x18005b94e  mov     rax, rdi
0x18005b951  neg     rax
0x18005b954  mov     eax, [rdi+9Ch]
0x18005b95a  sbb     rdx, rdx
0x18005b95d  sub     eax, r9d
0x18005b960  and     rdx, rcx
0x18005b963  mov     ecx, [rdi+0A0h]
0x18005b969  mov     [rsp+0C0h+lpParam], rdx; lpParam
0x18005b96e  sub     ecx, r8d
0x18005b971  mov     rdx, [rbp+57h+WndClass.lpszClassName]; lpClassName
0x18005b975  mov     [rsp+0C0h+hInstance], rbx; hInstance
0x18005b97a  mov     [rsp+0C0h+hMenu], 0; hMenu
0x18005b983  mov     [rsp+0C0h+hWndParent], rsi; hWndParent
0x18005b988  mov     [rsp+0C0h+nHeight], ecx; nHeight
0x18005b98c  mov     ecx, 200000h; dwExStyle
0x18005b991  mov     [rsp+0C0h+nWidth], eax; nWidth
0x18005b995  mov     [rsp+0C0h+Y], r8d; Y
0x18005b99a  xor     r8d, r8d; lpWindowName
0x18005b99d  mov     [rsp+0C0h+X], r9d; X
0x18005b9a2  mov     r9d, 80000000h; dwStyle
0x18005b9a8  call    cs:__imp_CreateWindowExW
0x18005b9ae  test    rax, rax
0x18005b9b1  jz      short loc_18005B9B7
0x18005b9b3  xor     ebx, ebx
0x18005b9b5  jmp     short loc_18005B9C2
0x18005b9b7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005b9bc  mov     ebx, eax
0x18005b9be  test    eax, eax
0x18005b9c0  js      short loc_18005B9C9
0x18005b9c2  mov     [rdi+0B0h], rsi
0x18005b9c9  lea     r11, [rsp+0C0h+var_10]
0x18005b9d1  mov     eax, ebx
0x18005b9d3  mov     rbx, [r11+28h]
0x18005b9d7  mov     rsi, [r11+30h]
0x18005b9db  mov     rsp, r11
0x18005b9de  pop     r14
0x18005b9e0  pop     rdi
0x18005b9e1  pop     rbp
0x18005b9e2  retn
```
