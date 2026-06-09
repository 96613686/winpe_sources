# NDXGI::CHwQueue::EnsureHistorySequenceThread(void)

- ea: `0x18008fbcc`
- end: `0x18008fcb3`
- name: `?EnsureHistorySequenceThread@CHwQueue@NDXGI@@QEAAXXZ`
- size: `231`
- prototype: `void __fastcall(NDXGI::CHwQueue *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18008f940`

## callees

- `0x18000b010`
- `0x18000b920`
- `0x18001356c`
- `0x1800148b4`
- `0x18008fbcc`
- `0x18011a2ac`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008fcac`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008fcac`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008fc4e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008fc4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18008fbf2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18008fbf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NDXGI::CHwQueue::EnsureHistorySequenceThread(NDXGI::CHwQueue *this)
{
  HANDLE EventA; // rbx
  _QWORD *v3; // rax
  __int128 v4; // xmm1
  __int128 v5; // [rsp+30h] [rbp-18h] BYREF
  _QWORD *v6; // [rsp+50h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 22) )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    D3DXPlat::unique_event::close((NDXGI::CHwQueue *)((char *)this + 72));
    *((_QWORD *)this + 9) = EventA;
    if ( !EventA )
      ThrowFailure(-2147024882);
    v3 = operator new(8u);
    if ( v3 )
      *v3 = this;
    v6 = v3;
    *(_QWORD *)&v5 = _o__beginthreadex(
                       0,
                       0,
                       std::thread::_Invoke_std::tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b____0_,
                       v3,
                       0,
                       (char *)&v5 + 8,
                       v5);
    if ( !(_QWORD)v5 )
    {
      DWORD2(v5) = 0;
      std::_Throw_Cpp_error(6);
      JUMPOUT(0x18008FCB2LL);
    }
    v6 = 0;
    std::unique_ptr_std::tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b____std::default_delete_std::tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b_______::_unique_ptr_std::tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b____std::default_delete_std::tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b_______(&v6);
    v4 = v5;
    v5 = *((_OWORD *)this + 5);
    *((_OWORD *)this + 5) = v4;
    std::thread::~thread((std::thread *)&v5);
  }
}

```

## disassembly

```asm
0x18008fbcc  mov     [rsp+arg_8], rbx
0x18008fbd1  mov     [rsp+arg_10], rsi
0x18008fbd6  push    rdi
0x18008fbd7  sub     rsp, 40h
0x18008fbdb  mov     rsi, rcx
0x18008fbde  cmp     dword ptr [rcx+58h], 0
0x18008fbe2  jnz     loc_18008FC8F
0x18008fbe8  xor     r9d, r9d; lpName
0x18008fbeb  xor     r8d, r8d; bInitialState
0x18008fbee  xor     edx, edx; bManualReset
0x18008fbf0  xor     ecx, ecx; lpEventAttributes
0x18008fbf2  call    cs:__imp_CreateEventA
0x18008fbf8  mov     rbx, rax
0x18008fbfb  lea     rcx, [rsi+48h]; this
0x18008fbff  call    ?close@unique_event@D3DXPlat@@QEAAXXZ; D3DXPlat::unique_event::close(void)
0x18008fc04  mov     [rsi+48h], rbx
0x18008fc08  test    rbx, rbx
0x18008fc0b  jnz     short loc_18008FC17
0x18008fc0d  mov     ecx, 8007000Eh; int
0x18008fc12  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18008fc17  mov     ecx, 8; dwBytes
0x18008fc1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008fc21  test    rax, rax
0x18008fc24  jz      short loc_18008FC29
0x18008fc26  mov     [rax], rsi
0x18008fc29  mov     [rsp+48h+arg_0], rax
0x18008fc2e  lea     rcx, [rsp+48h+var_18+8]
0x18008fc33  mov     [rsp+48h+var_20], rcx
0x18008fc38  mov     [rsp+48h+var_28], 0
0x18008fc40  mov     r9, rax
0x18008fc43  lea     r8, std__thread___Invoke_std__tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b____0_
0x18008fc4a  xor     edx, edx
0x18008fc4c  xor     ecx, ecx
0x18008fc4e  call    cs:__imp__o__beginthreadex
0x18008fc54  mov     qword ptr [rsp+48h+var_18], rax
0x18008fc59  test    rax, rax
0x18008fc5c  jz      short loc_18008FC9F
0x18008fc5e  mov     [rsp+48h+arg_0], 0
0x18008fc67  lea     rcx, [rsp+48h+arg_0]
0x18008fc6c  call    std__unique_ptr_std__tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b____std__default_delete_std__tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b__________unique_ptr_std__tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b____std__default_delete_std__tuple__lambda_b6ac916bf52213cafc36a6bd37aef86b_______
0x18008fc71  movaps  xmm1, [rsp+48h+var_18]
0x18008fc76  movups  xmm0, xmmword ptr [rsi+50h]
0x18008fc7a  movdqu  [rsp+48h+var_18], xmm0
0x18008fc80  movdqu  xmmword ptr [rsi+50h], xmm1
0x18008fc85  lea     rcx, [rsp+48h+var_18]; this
0x18008fc8a  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18008fc8f  mov     rbx, [rsp+48h+arg_8]
0x18008fc94  mov     rsi, [rsp+48h+arg_10]
0x18008fc99  add     rsp, 40h
0x18008fc9d  pop     rdi
0x18008fc9e  retn
0x18008fc9f  mov     dword ptr [rsp+48h+var_18+8], 0
0x18008fca7  mov     ecx, 6
0x18008fcac  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
