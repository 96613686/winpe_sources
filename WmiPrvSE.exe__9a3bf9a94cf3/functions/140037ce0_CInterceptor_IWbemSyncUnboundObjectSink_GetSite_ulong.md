# CInterceptor_IWbemSyncUnboundObjectSink::GetSite(ulong *)

- ea: `0x140037ce0`
- end: `0x140037d58`
- name: `?GetSite@CInterceptor_IWbemSyncUnboundObjectSink@@UEAAJPEAK@Z`
- size: `120`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncUnboundObjectSink *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140037ce0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140037cf4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140037cf4`
- `wbemcomn!GetMemLogObject` at `0x140037d03`
- `wbemcomn!GetMemLogObject` at `0x140037d03`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037d0e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037d0e`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncUnboundObjectSink::GetSite(
        CInterceptor_IWbemSyncUnboundObjectSink *this,
        unsigned int *a2)
{
  unsigned int v2; // ebx
  CMemoryLog *MemLogObject; // rax

  if ( a2 )
  {
    v2 = 0;
    *a2 = GetCurrentProcessId();
  }
  else
  {
    v2 = -2147217400;
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x140037ce0  mov     [rsp+arg_0], rbx
0x140037ce5  push    rdi
0x140037ce6  sub     rsp, 20h
0x140037cea  mov     rdi, rdx
0x140037ced  test    rdx, rdx
0x140037cf0  jz      short loc_140037CFE
0x140037cf2  xor     ebx, ebx
0x140037cf4  call    cs:__imp_GetCurrentProcessId
0x140037cfa  mov     [rdi], eax
0x140037cfc  jmp     short loc_140037D14
0x140037cfe  mov     ebx, 80041008h
0x140037d03  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140037d09  mov     rcx, rax
0x140037d0c  mov     edx, ebx
0x140037d0e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140037d14  mov     rcx, cs:WPP_GLOBAL_Control
0x140037d1b  lea     rax, WPP_GLOBAL_Control
0x140037d22  cmp     rcx, rax
0x140037d25  jz      short loc_140037D4B
0x140037d27  test    byte ptr [rcx+1Ch], 4
0x140037d2b  jz      short loc_140037D4B
0x140037d2d  cmp     byte ptr [rcx+19h], 2
0x140037d31  jb      short loc_140037D4B
0x140037d33  mov     rcx, [rcx+10h]
0x140037d37  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140037d3e  mov     edx, 10h
0x140037d43  mov     r9d, ebx
0x140037d46  call    WPP_SF_d
0x140037d4b  mov     eax, ebx
0x140037d4d  mov     rbx, [rsp+28h+arg_0]
0x140037d52  add     rsp, 20h
0x140037d56  pop     rdi
0x140037d57  retn
```
