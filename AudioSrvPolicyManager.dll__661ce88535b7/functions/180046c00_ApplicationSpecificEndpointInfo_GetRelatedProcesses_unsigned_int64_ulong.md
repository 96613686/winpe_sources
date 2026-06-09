# ApplicationSpecificEndpointInfo::GetRelatedProcesses(unsigned __int64 *,ulong * *)

- ea: `0x180046c00`
- end: `0x180046ced`
- name: `?GetRelatedProcesses@ApplicationSpecificEndpointInfo@@UEAAJPEA_KPEAPEAK@Z`
- size: `237`
- prototype: `int(ApplicationSpecificEndpointInfo *__hidden this, unsigned __int64 *, unsigned int **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a384`
- `0x180046c00`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180046cad`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180046cad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046c23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046c23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046cca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046cca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046c4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046c4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplicationSpecificEndpointInfo::GetRelatedProcesses(
        ApplicationSpecificEndpointInfo *this,
        unsigned __int64 *a2,
        unsigned int **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  unsigned __int64 v7; // rdi
  unsigned int *v8; // rdx
  unsigned __int64 i; // rcx
  __int64 v11; // r8
  const char *v12; // r9
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = (__int64)(*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) >> 2;
  v8 = 0;
  *a2 = v7;
  if ( v7 )
  {
    v8 = (unsigned int *)CoTaskMemAlloc(4 * v7);
    if ( !v8 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)0x8007000ELL,
        v13);
      if ( v6 )
        LeaveCriticalSection(v6);
      return 2147942414LL;
    }
    for ( i = 0; i < v7; ++i )
    {
      v11 = *((_QWORD *)this + 7);
      if ( (*((_QWORD *)this + 8) - v11) >> 2 <= i )
      {
        try
        {
          std::_Xout_of_range("invalid vector subscript");
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x151,
                                 (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\app"
                                               "licationspecificendpointinfo.cpp",
                                 v12);
        }
      }
      v8[i] = *(_DWORD *)(v11 + 4 * i);
    }
  }
  *a3 = v8;
  if ( v6 )
    LeaveCriticalSection(v6);
  return 0;
}

```

## disassembly

```asm
0x180046c00  mov     [rsp+arg_8], rbx
0x180046c05  mov     [rsp+arg_10], rsi
0x180046c0a  push    rdi
0x180046c0b  push    r14
0x180046c0d  push    r15; int
0x180046c0f  sub     rsp, 20h
0x180046c13  mov     r14, r8
0x180046c16  mov     r15, rdx
0x180046c19  mov     rsi, rcx
0x180046c1c  lea     rbx, [rcx+10h]
0x180046c20  mov     rcx, rbx; lpCriticalSection
0x180046c23  call    cs:__imp_EnterCriticalSection
0x180046c29  mov     [rsp+38h+arg_0], rbx
0x180046c2e  mov     rdi, [rsi+40h]
0x180046c32  sub     rdi, [rsi+38h]
0x180046c36  sar     rdi, 2
0x180046c3a  xor     edx, edx
0x180046c3c  mov     [r15], rdi
0x180046c3f  test    rdi, rdi
0x180046c42  jz      short loc_180046CBF
0x180046c44  lea     rcx, ds:0[rdi*4]; cb
0x180046c4c  call    cs:__imp_CoTaskMemAlloc
0x180046c52  mov     rdx, rax
0x180046c55  test    rax, rax
0x180046c58  jnz     short loc_180046C8B
0x180046c5a  mov     rcx, [rsp+38h]; this
0x180046c5f  mov     edi, 8007000Eh
0x180046c64  mov     r9d, edi; char *
0x180046c67  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180046c6e  mov     edx, 145h; void *
0x180046c73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046c78  nop
0x180046c79  test    rbx, rbx
0x180046c7c  jz      short loc_180046C87
0x180046c7e  mov     rcx, rbx; lpCriticalSection
0x180046c81  call    cs:__imp_LeaveCriticalSection
0x180046c87  mov     eax, edi
0x180046c89  jmp     short loc_180046CD8
0x180046c8b  xor     ecx, ecx
0x180046c8d  cmp     rcx, rdi
0x180046c90  jnb     short loc_180046CBF
0x180046c92  mov     r8, [rsi+38h]
0x180046c96  mov     rax, [rsi+40h]
0x180046c9a  sub     rax, r8
0x180046c9d  sar     rax, 2
0x180046ca1  cmp     rax, rcx
0x180046ca4  ja      short loc_180046CB3
0x180046ca6  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180046cad  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180046cb3  mov     eax, [r8+rcx*4]
0x180046cb7  mov     [rdx+rcx*4], eax
0x180046cba  inc     rcx
0x180046cbd  jmp     short loc_180046C8D
0x180046cbf  mov     [r14], rdx
0x180046cc2  test    rbx, rbx
0x180046cc5  jz      short loc_180046CD0
0x180046cc7  mov     rcx, rbx; lpCriticalSection
0x180046cca  call    cs:__imp_LeaveCriticalSection
0x180046cd0  xor     eax, eax
0x180046cd2  jmp     short loc_180046CD8
0x180046cd4  mov     eax, dword ptr [rsp+38h+arg_0]
0x180046cd8  mov     rbx, [rsp+38h+arg_8]
0x180046cdd  mov     rsi, [rsp+38h+arg_10]
0x180046ce2  add     rsp, 20h
0x180046ce6  pop     r15
0x180046ce8  pop     r14
0x180046cea  pop     rdi
0x180046ceb  retn
```
