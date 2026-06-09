# _anonymous_namespace_::TerminateRunningInstances

- ea: `0x180018ce8`
- end: `0x18001903a`
- name: `_anonymous_namespace_::TerminateRunningInstances`
- size: `850`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a0a0`

## callees

- `0x180018ce8`
- `0x180019040`
- `0x1800193b0`
- `0x180028bb8`
- `0x18002c640`
- `0x18002d518`
- `0x18004733c`
- `0x180047b74`
- `0x18005e8ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018f2d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018f2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018f68`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018f68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f98`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x180018d83`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x180018d83`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180018f15`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180018f15`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180018ecb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180018ecb`
- `ntdll!NtTerminateProcess` at `0x180018f45`
- `ntdll!NtTerminateProcess` at `0x180018f45`

## string_xrefs

- `0x180018e3b`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`
- `0x180018fef`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`
- `0x180019004`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`
- `0x180019016`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`
- `0x180019028`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
unsigned int __fastcall anonymous_namespace_::TerminateRunningInstances(__int64 a1)
{
  unsigned int v2; // edi
  unsigned __int64 v3; // rax
  DWORD v4; // ebx
  unsigned int result; // eax
  const char *v6; // r9
  unsigned __int64 v7; // rax
  DWORD *v8; // rsi
  unsigned __int64 v9; // rcx
  DWORD *v10; // rax
  size_t v11; // rbx
  DWORD *v12; // rdi
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rbx
  size_t v15; // rbx
  DWORD *i; // rsi
  char *v17; // rbx
  NTSTATUS v18; // eax
  signed int v19; // eax
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  DWORD *lpidProcess[2]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h]
  char *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ExeName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v2 = 500;
  *(_OWORD *)lpidProcess = 0;
  v22 = 0;
  std::vector<unsigned long>::_Construct_n<>(lpidProcess, 500);
  while ( 1 )
  {
    v3 = 4LL * v2;
    v4 = 4 * v2;
    if ( v3 > 0xFFFFFFFF )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x153,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
        v3 > 0xFFFFFFFF ? (const char *)0xC0000095LL : 0,
        cbNeeded);
    cbNeeded = 0;
    result = K32EnumProcesses(lpidProcess[0], v4, &cbNeeded);
    if ( !result )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
        v6);
    if ( cbNeeded < v4 )
      break;
    v7 = 2LL * v2;
    v2 *= 2;
    if ( v7 > 0xFFFFFFFF )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
        v7 > 0xFFFFFFFF ? (const char *)0xC0000095LL : 0,
        cbNeeded);
    v8 = lpidProcess[1];
    v9 = lpidProcess[1] - lpidProcess[0];
    if ( v2 < v9 )
    {
      v10 = &lpidProcess[0][v2];
      goto LABEL_14;
    }
    if ( v2 > v9 )
    {
      if ( v2 <= (unsigned __int64)((signed __int64)(v22 - (unsigned __int64)lpidProcess[0]) >> 2) )
      {
        v11 = v2 - v9;
        memset_0(lpidProcess[1], 0, v11 * 4);
        v10 = &v8[v11];
LABEL_14:
        lpidProcess[1] = v10;
      }
      else
      {
        std::vector<unsigned long>::_Resize_reallocate<std::_Value_init_tag>(lpidProcess, v2);
      }
    }
  }
  v12 = lpidProcess[1];
  v13 = lpidProcess[1] - lpidProcess[0];
  v14 = (unsigned __int64)cbNeeded >> 2;
  if ( v14 < v13 )
  {
    v12 = &lpidProcess[0][v14];
    goto LABEL_21;
  }
  if ( v14 > v13 )
  {
    if ( v14 <= (signed __int64)(v22 - (unsigned __int64)lpidProcess[0]) >> 2 )
    {
      v15 = 4 * (v14 - v13);
      result = (unsigned int)memset_0(lpidProcess[1], 0, v15);
      v12 = (DWORD *)((char *)v12 + v15);
LABEL_21:
      lpidProcess[1] = v12;
    }
    else
    {
      result = std::vector<unsigned long>::_Resize_reallocate<std::_Value_init_tag>(
                 lpidProcess,
                 (unsigned __int64)cbNeeded >> 2);
      v12 = lpidProcess[1];
    }
  }
  for ( i = lpidProcess[0]; i != v12; ++i )
  {
    v17 = (char *)OpenProcess(0x101001u, 0, *i);
    v23 = v17;
    if ( (unsigned __int64)(v17 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      result = (_DWORD)v17 - 1;
    }
    else
    {
      memset_0(ExeName, 0, 0x208u);
      cbNeeded = 260;
      if ( QueryFullProcessImageNameW(v17, 0, ExeName, &cbNeeded) && !(unsigned int)_o__wcsicmp(a1, ExeName) )
      {
        v18 = NtTerminateProcess(v17, -1073741823);
        if ( v18 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x18A,
            (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
            (const char *)(unsigned int)v18,
            cbNeeded);
        v19 = WaitForSingleObject(v17, 0x3E8u);
        if ( v19 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x18E,
            (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
            (const char *)(unsigned int)v19,
            cbNeeded);
      }
      result = wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    }
  }
  if ( lpidProcess[0] )
    return std::_Deallocate<16>(lpidProcess[0], (v22 - (unsigned __int64)lpidProcess[0]) & 0xFFFFFFFFFFFFFFFCuLL);
  return result;
}

```

## disassembly

```asm
0x180018ce8  push    rbp
0x180018cea  push    rbx
0x180018ceb  push    rsi
0x180018cec  push    rdi
0x180018ced  push    r14
0x180018cef  push    r15
0x180018cf1  lea     rbp, [rsp-178h]
0x180018cf9  sub     rsp, 278h
0x180018d00  mov     rax, cs:__security_cookie
0x180018d07  xor     rax, rsp
0x180018d0a  mov     [rbp+1A0h+var_40], rax
0x180018d11  mov     r14, rcx
0x180018d14  mov     edi, 1F4h
0x180018d19  xorps   xmm0, xmm0
0x180018d1c  movdqu  xmmword ptr [rsp+2A0h+lpidProcess], xmm0
0x180018d22  mov     [rsp+2A0h+var_268], 0
0x180018d2b  mov     edx, edi
0x180018d2d  lea     rcx, [rsp+2A0h+lpidProcess]
0x180018d32  call    ??$_Construct_n@$$V@?$vector@KV?$allocator@K@std@@@std@@AEAAX_K@Z; std::vector<ulong>::_Construct_n<>(unsigned __int64)
0x180018d37  nop
0x180018d38  mov     r15d, 0FFFFFFFFh
0x180018d3e  mov     edi, edi
0x180018d40  lea     rax, ds:0[rdi*4]
0x180018d48  cmp     rax, r15
0x180018d4b  mov     ebx, eax
0x180018d4d  jbe     short loc_180018D52
0x180018d4f  mov     ebx, r15d
0x180018d52  cmp     r15, rax
0x180018d55  sbb     r9d, r9d
0x180018d58  and     r9d, 0C0000095h; char *
0x180018d5f  mov     rcx, [rbp+1A8h]; this
0x180018d66  cmp     rax, r15
0x180018d69  ja      loc_180019028
0x180018d6f  mov     [rsp+2A0h+cbNeeded], 0; int
0x180018d77  lea     r8, [rsp+2A0h+cbNeeded]; lpcbNeeded
0x180018d7c  mov     edx, ebx; cb
0x180018d7e  mov     rcx, [rsp+2A0h+lpidProcess]; lpidProcess
0x180018d83  call    cs:__imp_K32EnumProcesses
0x180018d8a  nop     dword ptr [rax+rax+00h]
0x180018d8f  mov     rcx, [rbp+1A8h]; this
0x180018d96  test    eax, eax
0x180018d98  jz      loc_180019016
0x180018d9e  cmp     [rsp+2A0h+cbNeeded], ebx
0x180018da2  jb      loc_180018E4D
0x180018da8  lea     rax, [rdi+rdi]
0x180018dac  cmp     rax, r15
0x180018daf  mov     edi, eax
0x180018db1  jbe     short loc_180018DB6
0x180018db3  mov     edi, r15d
0x180018db6  cmp     r15, rax
0x180018db9  sbb     r9d, r9d
0x180018dbc  and     r9d, 0C0000095h; char *
0x180018dc3  mov     rcx, [rbp+1A8h]; this
0x180018dca  cmp     rax, r15
0x180018dcd  ja      short loc_180018E3B
0x180018dcf  mov     rdx, [rsp+2A0h+lpidProcess]
0x180018dd4  mov     rsi, [rsp+2A0h+lpidProcess+8]
0x180018dd9  mov     rcx, rsi
0x180018ddc  sub     rcx, rdx
0x180018ddf  sar     rcx, 2
0x180018de3  mov     ebx, edi
0x180018de5  cmp     rbx, rcx
0x180018de8  jnb     short loc_180018DF0
0x180018dea  lea     rax, [rdx+rbx*4]
0x180018dee  jmp     short loc_180018E31
0x180018df0  jbe     loc_180018D3E
0x180018df6  mov     rax, [rsp+2A0h+var_268]
0x180018dfb  sub     rax, rdx
0x180018dfe  sar     rax, 2
0x180018e02  cmp     rbx, rax
0x180018e05  jbe     short loc_180018E19
0x180018e07  mov     rdx, rbx
0x180018e0a  lea     rcx, [rsp+2A0h+lpidProcess]
0x180018e0f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ulong>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180018e14  jmp     loc_180018D3E
0x180018e19  sub     rbx, rcx
0x180018e1c  shl     rbx, 2
0x180018e20  mov     r8, rbx; Size
0x180018e23  xor     edx, edx; Val
0x180018e25  mov     rcx, rsi; void *
0x180018e28  call    memset_0
0x180018e2d  lea     rax, [rbx+rsi]
0x180018e31  mov     [rsp+2A0h+lpidProcess+8], rax
0x180018e36  jmp     loc_180018D3E
0x180018e3b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x180018e42  mov     edx, 161h; void *
0x180018e47  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180018e4d  mov     rdx, [rsp+2A0h+lpidProcess]
0x180018e52  mov     rdi, [rsp+2A0h+lpidProcess+8]
0x180018e57  mov     rcx, rdi
0x180018e5a  sub     rcx, rdx
0x180018e5d  sar     rcx, 2
0x180018e61  mov     ebx, [rsp+2A0h+cbNeeded]
0x180018e65  shr     rbx, 2
0x180018e69  cmp     rbx, rcx
0x180018e6c  jnb     short loc_180018E74
0x180018e6e  lea     rdi, [rdx+rbx*4]
0x180018e72  jmp     short loc_180018EB2
0x180018e74  jbe     short loc_180018EB7
0x180018e76  mov     rax, [rsp+2A0h+var_268]
0x180018e7b  sub     rax, rdx
0x180018e7e  sar     rax, 2
0x180018e82  cmp     rbx, rax
0x180018e85  jbe     short loc_180018E9B
0x180018e87  mov     rdx, rbx
0x180018e8a  lea     rcx, [rsp+2A0h+lpidProcess]
0x180018e8f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ulong>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180018e94  mov     rdi, [rsp+2A0h+lpidProcess+8]
0x180018e99  jmp     short loc_180018EB7
0x180018e9b  sub     rbx, rcx
0x180018e9e  shl     rbx, 2
0x180018ea2  mov     r8, rbx; Size
0x180018ea5  xor     edx, edx; Val
0x180018ea7  mov     rcx, rdi; void *
0x180018eaa  call    memset_0
0x180018eaf  add     rdi, rbx
0x180018eb2  mov     [rsp+2A0h+lpidProcess+8], rdi
0x180018eb7  mov     rsi, [rsp+2A0h+lpidProcess]
0x180018ebc  jmp     loc_180018FA8
0x180018ec1  mov     r8d, [rsi]; dwProcessId
0x180018ec4  xor     edx, edx; bInheritHandle
0x180018ec6  mov     ecx, 101001h; dwDesiredAccess
0x180018ecb  call    cs:__imp_OpenProcess
0x180018ed2  nop     dword ptr [rax+rax+00h]
0x180018ed7  mov     rbx, rax
0x180018eda  mov     [rsp+2A0h+var_260], rax
0x180018edf  dec     rax
0x180018ee2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018ee6  ja      loc_180018F8B
0x180018eec  xor     edx, edx; Val
0x180018eee  mov     r8d, 208h; Size
0x180018ef4  lea     rcx, [rsp+2A0h+ExeName]; void *
0x180018ef9  call    memset_0
0x180018efe  mov     [rsp+2A0h+cbNeeded], 104h; int
0x180018f06  lea     r9, [rsp+2A0h+cbNeeded]; lpdwSize
0x180018f0b  lea     r8, [rsp+2A0h+ExeName]; lpExeName
0x180018f10  xor     edx, edx; dwFlags
0x180018f12  mov     rcx, rbx; hProcess
0x180018f15  call    cs:__imp_QueryFullProcessImageNameW
0x180018f1c  nop     dword ptr [rax+rax+00h]
0x180018f21  test    eax, eax
0x180018f23  jz      short loc_180018F7F
0x180018f25  lea     rdx, [rsp+2A0h+ExeName]
0x180018f2a  mov     rcx, r14
0x180018f2d  call    cs:__imp__o__wcsicmp
0x180018f34  nop     dword ptr [rax+rax+00h]
0x180018f39  test    eax, eax
0x180018f3b  jnz     short loc_180018F7F
0x180018f3d  mov     edx, 0C0000001h; ExitStatus
0x180018f42  mov     rcx, rbx; ProcessHandle
0x180018f45  call    cs:__imp_NtTerminateProcess
0x180018f4c  nop     dword ptr [rax+rax+00h]
0x180018f51  mov     rcx, [rbp+1A8h]; this
0x180018f58  test    eax, eax
0x180018f5a  js      loc_180019001
0x180018f60  mov     edx, 3E8h; dwMilliseconds
0x180018f65  mov     rcx, rbx; hHandle
0x180018f68  call    cs:__imp_WaitForSingleObject
0x180018f6f  nop     dword ptr [rax+rax+00h]
0x180018f74  mov     rcx, [rbp+1A8h]; this
0x180018f7b  test    eax, eax
0x180018f7d  js      short loc_180018FEC
0x180018f7f  lea     rcx, [rsp+2A0h+var_260]
0x180018f84  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018f89  jmp     short loc_180018FA4
0x180018f8b  lea     rax, [rbx-1]
0x180018f8f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018f93  ja      short loc_180018FA4
0x180018f95  mov     rcx, rbx; hObject
0x180018f98  call    cs:__imp_CloseHandle
0x180018f9f  nop     dword ptr [rax+rax+00h]
0x180018fa4  add     rsi, 4
0x180018fa8  cmp     rsi, rdi
0x180018fab  jnz     loc_180018EC1
0x180018fb1  mov     rcx, [rsp+2A0h+lpidProcess]
0x180018fb6  test    rcx, rcx
0x180018fb9  jz      short loc_180018FCC
0x180018fbb  mov     rdx, [rsp+2A0h+var_268]
0x180018fc0  sub     rdx, rcx
0x180018fc3  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180018fc7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018fcc  mov     rcx, [rbp+1A0h+var_40]
0x180018fd3  xor     rcx, rsp; StackCookie
0x180018fd6  call    __security_check_cookie
0x180018fdb  add     rsp, 278h
0x180018fe2  pop     r15
0x180018fe4  pop     r14
0x180018fe6  pop     rdi
0x180018fe7  pop     rsi
0x180018fe8  pop     rbx
0x180018fe9  pop     rbp
0x180018fea  retn
0x180018fec  mov     r9d, eax; char *
0x180018fef  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x180018ff6  mov     edx, 18Eh; void *
0x180018ffb  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180019001  mov     r9d, eax; char *
0x180019004  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18001900b  mov     edx, 18Ah; void *
0x180019010  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180019016  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18001901d  mov     edx, 159h; void *
0x180019022  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180019028  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18001902f  mov     edx, 153h; void *
0x180019034  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
