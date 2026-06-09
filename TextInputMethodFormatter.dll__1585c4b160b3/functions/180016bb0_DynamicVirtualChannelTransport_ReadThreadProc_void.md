# DynamicVirtualChannelTransport::ReadThreadProc(void *)

- ea: `0x180016bb0`
- end: `0x180016d9a`
- name: `?ReadThreadProc@DynamicVirtualChannelTransport@@SAKPEAX@Z`
- size: `490`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002240`
- `0x18000428c`
- `0x1800132f0`
- `0x180015a44`
- `0x180015ce8`
- `0x180016bb0`
- `0x1800173cc`
- `0x180056f80`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016c54`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016c54`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016c2a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016d5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016d69`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016c2a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016d5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016d69`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DynamicVirtualChannelTransport::ReadThreadProc(PVOID Parameter)
{
  __int64 v2; // rdx
  __int64 v3; // r9
  int v4; // eax
  DWORD v5; // ecx
  unsigned int v6; // esi
  int v7; // r15d
  int v8; // r14d
  DWORD v9; // edi
  void (__fastcall ***v10)(_QWORD, _QWORD, __int128 *); // rcx
  DWORD v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+38h] [rbp-C8h]
  __int128 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h]
  _DWORD v16[1024]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 retaddr; // [rsp+10A8h] [rbp+FA8h]

  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( Parameter )
  {
    if ( *((_BYTE *)Parameter + 17) )
      SetEvent(_readThreadReadyEvent);
    while ( 1 )
    {
      v12 = 0;
      if ( !*((_QWORD *)Parameter + 6) || !*((_QWORD *)Parameter + 5) )
        DynamicVirtualChannelTransport::AttemptReconnect((DynamicVirtualChannelTransport *)Parameter);
      if ( !WaitForSingleObject(*((HANDLE *)Parameter + 15), 0) )
        break;
      v4 = s_WTSVirtualChannelRead(*((void **)Parameter + 6), v2, v16, v3, &v12);
      if ( v4 < 0 )
      {
        if ( v4 != -2147024663 && v4 != -2147022646 )
        {
          SetEvent(_inputServiceShutdownEvent);
          SetEvent(*((HANDLE *)Parameter + 15));
          break;
        }
        DynamicVirtualChannelTransport::AttemptReconnect((DynamicVirtualChannelTransport *)Parameter);
      }
      v5 = v12;
      if ( v12 )
      {
        v6 = 8;
        if ( v12 > 8 )
        {
          do
          {
            v7 = v13;
            v8 = DWORD2(v14) - v14;
            if ( !v13 )
            {
              v7 = *(_DWORD *)((char *)v16 + v6);
              v13 = v7;
              v6 += 4;
            }
            v9 = v5;
            if ( v8 + v5 > v7 + v6 )
              v9 = v6 + v7 - v8;
            std::vector<char>::_Insert_counted_range<char const *>(
              &v14,
              *((_QWORD *)&v14 + 1),
              (char *)v16 + v6,
              (char *)v16 + v9 - ((_QWORD)v16 + v6));
            if ( v9 + v8 - v6 == v7 )
            {
              v10 = (void (__fastcall ***)(_QWORD, _QWORD, __int128 *))*((_QWORD *)Parameter + 3);
              if ( v10 )
                (**v10)(v10, 0, &v14);
              v13 = 0;
              if ( (_QWORD)v14 != *((_QWORD *)&v14 + 1) )
                *((_QWORD *)&v14 + 1) = v14;
            }
            v6 = v9;
            v5 = v12;
          }
          while ( v9 < v12 );
        }
      }
    }
  }
  else
  {
    FailFastWithHR(-2147467261, retaddr, 0x24Fu);
  }
  std::vector<char>::~vector<char>(&v14);
  return 0;
}

```

## disassembly

```asm
0x180016bb0  push    rbp
0x180016bb2  push    rbx
0x180016bb3  push    rsi
0x180016bb4  push    rdi
0x180016bb5  push    r14
0x180016bb7  push    r15
0x180016bb9  lea     rbp, [rsp-0F78h]
0x180016bc1  mov     eax, 1078h
0x180016bc6  call    _alloca_probe
0x180016bcb  sub     rsp, rax
0x180016bce  mov     rax, cs:__security_cookie
0x180016bd5  xor     rax, rsp
0x180016bd8  mov     [rbp+0FA0h+var_40], rax
0x180016bdf  mov     rbx, rcx
0x180016be2  mov     [rsp+10A0h+var_1068], 0
0x180016bea  xorps   xmm0, xmm0
0x180016bed  movdqu  [rsp+10A0h+var_1060], xmm0
0x180016bf3  mov     [rsp+10A0h+var_1050], 0
0x180016bfc  test    rcx, rcx
0x180016bff  jnz     short loc_180016C1D
0x180016c01  mov     rdx, [rbp+0FA8h]; unsigned __int64
0x180016c08  mov     ecx, 80004003h; int
0x180016c0d  mov     r8d, 24Fh; unsigned __int64
0x180016c13  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x180016c18  jmp     loc_180016D6F
0x180016c1d  cmp     byte ptr [rcx+11h], 0
0x180016c21  jz      short loc_180016C30
0x180016c23  mov     rcx, cs:?_readThreadReadyEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x180016c2a  call    cs:__imp_SetEvent
0x180016c30  mov     [rsp+10A0h+var_1070], 0
0x180016c38  cmp     qword ptr [rbx+30h], 0
0x180016c3d  jz      short loc_180016C46
0x180016c3f  cmp     qword ptr [rbx+28h], 0
0x180016c44  jnz     short loc_180016C4E
0x180016c46  mov     rcx, rbx; this
0x180016c49  call    ?AttemptReconnect@DynamicVirtualChannelTransport@@IEAAJXZ; DynamicVirtualChannelTransport::AttemptReconnect(void)
0x180016c4e  xor     edx, edx; dwMilliseconds
0x180016c50  mov     rcx, [rbx+78h]; hHandle
0x180016c54  call    cs:__imp_WaitForSingleObject
0x180016c5a  test    eax, eax
0x180016c5c  jz      loc_180016D6F
0x180016c62  lea     rax, [rsp+10A0h+var_1070]
0x180016c67  mov     [rsp+10A0h+var_1080], rax
0x180016c6c  lea     r8, [rsp+10A0h+var_1040]
0x180016c71  mov     rcx, [rbx+30h]
0x180016c75  call    s_WTSVirtualChannelRead
0x180016c7a  test    eax, eax
0x180016c7c  jns     short loc_180016C98
0x180016c7e  cmp     eax, 800700E9h
0x180016c83  jz      short loc_180016C90
0x180016c85  cmp     eax, 800708CAh
0x180016c8a  jnz     loc_180016D58
0x180016c90  mov     rcx, rbx; this
0x180016c93  call    ?AttemptReconnect@DynamicVirtualChannelTransport@@IEAAJXZ; DynamicVirtualChannelTransport::AttemptReconnect(void)
0x180016c98  mov     ecx, [rsp+10A0h+var_1070]
0x180016c9c  test    ecx, ecx
0x180016c9e  jz      short loc_180016C30
0x180016ca0  mov     esi, 8
0x180016ca5  cmp     ecx, esi
0x180016ca7  jbe     short loc_180016C30
0x180016ca9  mov     r15d, [rsp+10A0h+var_1068]
0x180016cae  mov     rdx, qword ptr [rsp+10A0h+var_1060+8]
0x180016cb3  mov     r14d, edx
0x180016cb6  sub     r14d, dword ptr [rsp+10A0h+var_1060]
0x180016cbb  test    r15d, r15d
0x180016cbe  jnz     short loc_180016CCF
0x180016cc0  mov     eax, esi
0x180016cc2  mov     r15d, [rsp+rax+10A0h+var_1040]
0x180016cc7  mov     [rsp+10A0h+var_1068], r15d
0x180016ccc  add     esi, 4
0x180016ccf  mov     edi, ecx
0x180016cd1  add     ecx, r14d
0x180016cd4  lea     eax, [r15+rsi]
0x180016cd8  cmp     ecx, eax
0x180016cda  jbe     short loc_180016CE4
0x180016cdc  mov     edi, r15d
0x180016cdf  sub     edi, r14d
0x180016ce2  add     edi, esi
0x180016ce4  mov     eax, esi
0x180016ce6  lea     r8, [rsp+10A0h+var_1040]
0x180016ceb  add     r8, rax
0x180016cee  mov     eax, edi
0x180016cf0  sub     rax, r8
0x180016cf3  lea     r9, [rsp+10A0h+var_1040]
0x180016cf8  add     r9, rax
0x180016cfb  lea     rcx, [rsp+10A0h+var_1060]
0x180016d00  call    ??$_Insert_counted_range@PEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@D@std@@@std@@@1@PEBD_K@Z; std::vector<char>::_Insert_counted_range<char const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<char>>>,char const *,unsigned __int64)
0x180016d05  sub     r14d, esi
0x180016d08  add     r14d, edi
0x180016d0b  cmp     r14d, r15d
0x180016d0e  jnz     short loc_180016D45
0x180016d10  mov     rcx, [rbx+18h]
0x180016d14  test    rcx, rcx
0x180016d17  jz      short loc_180016D2C
0x180016d19  mov     rax, [rcx]
0x180016d1c  lea     r8, [rsp+10A0h+var_1060]
0x180016d21  xor     edx, edx
0x180016d23  mov     rax, [rax]
0x180016d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d2b  nop
0x180016d2c  mov     [rsp+10A0h+var_1068], 0
0x180016d34  mov     rax, qword ptr [rsp+10A0h+var_1060]
0x180016d39  cmp     rax, qword ptr [rsp+10A0h+var_1060+8]
0x180016d3e  jz      short loc_180016D45
0x180016d40  mov     qword ptr [rsp+10A0h+var_1060+8], rax
0x180016d45  mov     esi, edi
0x180016d47  mov     ecx, [rsp+10A0h+var_1070]
0x180016d4b  cmp     edi, ecx
0x180016d4d  jb      loc_180016CA9
0x180016d53  jmp     loc_180016C30
0x180016d58  mov     rcx, cs:?_inputServiceShutdownEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x180016d5f  call    cs:__imp_SetEvent
0x180016d65  mov     rcx, [rbx+78h]; hEvent
0x180016d69  call    cs:__imp_SetEvent
0x180016d6f  lea     rcx, [rsp+10A0h+var_1060]
0x180016d74  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180016d79  xor     eax, eax
0x180016d7b  mov     rcx, [rbp+0FA0h+var_40]
0x180016d82  xor     rcx, rsp; StackCookie
0x180016d85  call    __security_check_cookie
0x180016d8a  add     rsp, 1078h
0x180016d91  pop     r15
0x180016d93  pop     r14
0x180016d95  pop     rdi
0x180016d96  pop     rsi
0x180016d97  pop     rbx
0x180016d98  pop     rbp
0x180016d99  retn
```
