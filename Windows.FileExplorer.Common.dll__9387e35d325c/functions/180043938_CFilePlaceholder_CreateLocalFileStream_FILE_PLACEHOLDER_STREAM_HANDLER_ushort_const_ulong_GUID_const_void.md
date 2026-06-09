# CFilePlaceholder::_CreateLocalFileStream(FILE_PLACEHOLDER_STREAM_HANDLER,ushort const *,ulong,_GUID const &,void * *)

- ea: `0x180043938`
- end: `0x180043a1c`
- name: `?_CreateLocalFileStream@CFilePlaceholder@@AEAAJW4FILE_PLACEHOLDER_STREAM_HANDLER@@PEBGKAEBU_GUID@@PEAPEAX@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d634`

## callees

- `0x180004a54`
- `0x180043938`
- `0x180089010`

## import_xrefs

- `SHCORE!CreateStreamOverRandomAccessStream` at `0x1800439d2`
- `SHCORE!CreateStreamOverRandomAccessStream` at `0x1800439d2`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x1800439ab`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x1800439ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFilePlaceholder::_CreateLocalFileStream(
        __int64 a1,
        int a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6)
{
  int StreamOverRandomAccessStream; // ebx
  _DWORD v10[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v11; // [rsp+28h] [rbp-28h]
  __int64 v12; // [rsp+30h] [rbp-20h]
  __int64 v13; // [rsp+38h] [rbp-18h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // [rsp+60h] [rbp+10h] BYREF

  v15 = 0;
  v10[0] = (a4 & 3) != 0;
  v10[1] = 0;
  v11 = 2;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v15);
  StreamOverRandomAccessStream = ((__int64 (__fastcall *)(__int64, _DWORD *, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))CreateRandomAccessStreamOnFileWithOptions)(
                                   a3,
                                   v10,
                                   &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                                   &v15);
  if ( StreamOverRandomAccessStream >= 0 )
  {
    if ( a2 )
    {
      StreamOverRandomAccessStream = (**v15)(v15, &GUID_00000000_0000_0000_c000_000000000046, a6);
    }
    else
    {
      a5 = 0;
      StreamOverRandomAccessStream = CreateStreamOverRandomAccessStream(
                                       v15,
                                       &GUID_00000000_0000_0000_c000_000000000046,
                                       a6);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&a5);
    }
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v15);
  return (unsigned int)StreamOverRandomAccessStream;
}

```

## disassembly

```asm
0x180043938  mov     [rsp-8+arg_8], rbx
0x18004393d  mov     [rsp-8+arg_10], rdi
0x180043942  mov     [rsp-8+arg_0], rcx
0x180043947  push    rbp
0x180043948  mov     rbp, rsp
0x18004394b  sub     rsp, 50h
0x18004394f  mov     rbx, r8
0x180043952  mov     edi, edx
0x180043954  mov     [rbp+arg_0], 0
0x18004395c  test    r9b, 3
0x180043960  mov     eax, 0
0x180043965  setnz   al
0x180043968  mov     [rbp+var_30], eax
0x18004396b  mov     [rbp+var_2C], 0
0x180043972  mov     [rbp+var_28], 2
0x18004397a  mov     [rbp+var_20], 0
0x180043982  mov     [rbp+var_18], 0
0x18004398a  xor     eax, eax
0x18004398c  mov     [rbp+var_10], rax
0x180043990  lea     rcx, [rbp+arg_0]
0x180043994  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180043999  lea     r9, [rbp+arg_0]
0x18004399d  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1800439a4  lea     rdx, [rbp+var_30]
0x1800439a8  mov     rcx, rbx
0x1800439ab  call    cs:__imp_CreateRandomAccessStreamOnFileWithOptions
0x1800439b1  mov     ebx, eax
0x1800439b3  test    eax, eax
0x1800439b5  js      short loc_180043A01
0x1800439b7  test    edi, edi
0x1800439b9  jnz     short loc_1800439E5
0x1800439bb  mov     [rbp+arg_20], 0
0x1800439c3  mov     r8, [rbp+arg_28]
0x1800439c7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800439ce  mov     rcx, [rbp+arg_0]
0x1800439d2  call    cs:__imp_CreateStreamOverRandomAccessStream
0x1800439d8  mov     ebx, eax
0x1800439da  lea     rcx, [rbp+arg_20]
0x1800439de  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800439e3  jmp     short loc_180043A01
0x1800439e5  mov     rcx, [rbp+arg_0]
0x1800439e9  mov     rax, [rcx]
0x1800439ec  mov     r8, [rbp+arg_28]
0x1800439f0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800439f7  mov     rax, [rax]
0x1800439fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439ff  mov     ebx, eax
0x180043a01  lea     rcx, [rbp+arg_0]
0x180043a05  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180043a0a  mov     eax, ebx
0x180043a0c  mov     rbx, [rsp+50h+arg_8]
0x180043a11  mov     rdi, [rsp+50h+arg_10]
0x180043a16  add     rsp, 50h
0x180043a1a  pop     rbp
0x180043a1b  retn
```
