# wil::init_once_nothrow__lambda_d1ef26c7cb7332aa7663727e3dea045c___

- ea: `0x18001ff7c`
- end: `0x18002004c`
- name: `wil::init_once_nothrow__lambda_d1ef26c7cb7332aa7663727e3dea045c___`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ff10`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18001ff7c`
- `0x180034f88`
- `0x180044408`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ff9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ff9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020028`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002003e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020028`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002003e`

## pseudocode

```c
__int64 wil::init_once_nothrow__lambda_d1ef26c7cb7332aa7663727e3dea045c___()
{
  const char *v0; // r9
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL fPending; // [rsp+38h] [rbp+10h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v0);
  if ( fPending )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&qword_1800D2590);
    v2 = Microsoft::WRL::Details::MakeAndInitialize<ViewActivator,IViewActivatorHelper,>(&qword_1800D2590);
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
        (const char *)(unsigned int)v2,
        v4);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)v3, v5);
      InitOnceComplete(&InitOnce, 4u, 0);
      return v3;
    }
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ff7c  mov     byte ptr [rsp+fPending], dl
0x18001ff80  push    rbx; int
0x18001ff81  sub     rsp, 20h
0x18001ff85  mov     [rsp+28h+fPending], 0
0x18001ff8d  xor     r9d, r9d; lpContext
0x18001ff90  lea     r8, [rsp+28h+fPending]; fPending
0x18001ff95  xor     edx, edx; dwFlags
0x18001ff97  lea     rcx, InitOnce; lpInitOnce
0x18001ff9e  call    cs:__imp___std_init_once_begin_initialize
0x18001ffa4  test    eax, eax
0x18001ffa6  jnz     short loc_18001FFC3
0x18001ffa8  mov     rcx, [rsp+28h]; this
0x18001ffad  lea     r8, aWil; "wil"
0x18001ffb4  mov     edx, 37Ah; void *
0x18001ffb9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ffbe  jmp     loc_180020046
0x18001ffc3  cmp     [rsp+28h+fPending], 0
0x18001ffc8  jz      short loc_180020044
0x18001ffca  lea     rcx, qword_1800D2590
0x18001ffd1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001ffd6  lea     rcx, qword_1800D2590
0x18001ffdd  call    ??$MakeAndInitialize@VViewActivator@@UIViewActivatorHelper@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIViewActivatorHelper@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ViewActivator,IViewActivatorHelper,>(IViewActivatorHelper * *)
0x18001ffe2  mov     ebx, eax
0x18001ffe4  test    eax, eax
0x18001ffe6  jns     short loc_180020032
0x18001ffe8  mov     rcx, [rsp+28h]; this
0x18001ffed  mov     r9d, eax; char *
0x18001fff0  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001fff7  mov     edx, 3Bh ; ';'; void *
0x18001fffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020001  mov     rcx, [rsp+28h]; this
0x180020006  mov     r9d, ebx; char *
0x180020009  lea     r8, aWil; "wil"
0x180020010  mov     edx, 37Fh; void *
0x180020015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002001a  xor     r8d, r8d; lpContext
0x18002001d  lea     edx, [r8+4]; dwFlags
0x180020021  lea     rcx, InitOnce; lpInitOnce
0x180020028  call    cs:__imp_InitOnceComplete
0x18002002e  mov     eax, ebx
0x180020030  jmp     short loc_180020046
0x180020032  xor     r8d, r8d; lpContext
0x180020035  xor     edx, edx; dwFlags
0x180020037  lea     rcx, InitOnce; lpInitOnce
0x18002003e  call    cs:__imp_InitOnceComplete
0x180020044  xor     eax, eax
0x180020046  add     rsp, 20h
0x18002004a  pop     rbx
0x18002004b  retn
```
