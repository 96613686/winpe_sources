# CInterceptor_IWbemSyncProvider::GetSite(ulong *)

- ea: `0x140026250`
- end: `0x1400262ca`
- name: `?GetSite@CInterceptor_IWbemSyncProvider@@UEAAJPEAK@Z`
- size: `122`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140026250`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140026264`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140026264`
- `wbemcomn!GetMemLogObject` at `0x140026297`
- `wbemcomn!GetMemLogObject` at `0x140026297`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400262a2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400262a2`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::GetSite(CInterceptor_IWbemSyncProvider *this, unsigned int *a2)
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x140026250  mov     [rsp+arg_0], rbx
0x140026255  push    rdi
0x140026256  sub     rsp, 20h
0x14002625a  mov     rdi, rdx
0x14002625d  test    rdx, rdx
0x140026260  jz      short loc_140026292
0x140026262  xor     ebx, ebx
0x140026264  call    cs:__imp_GetCurrentProcessId
0x14002626a  mov     [rdi], eax
0x14002626c  mov     rcx, cs:WPP_GLOBAL_Control
0x140026273  lea     rax, WPP_GLOBAL_Control
0x14002627a  cmp     rcx, rax
0x14002627d  jz      short loc_140026285
0x14002627f  test    byte ptr [rcx+1Ch], 4
0x140026283  jnz     short loc_1400262AA
0x140026285  mov     eax, ebx
0x140026287  mov     rbx, [rsp+28h+arg_0]
0x14002628c  add     rsp, 20h
0x140026290  pop     rdi
0x140026291  retn
0x140026292  mov     ebx, 80041008h
0x140026297  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002629d  mov     rcx, rax
0x1400262a0  mov     edx, ebx
0x1400262a2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400262a8  jmp     short loc_14002626C
0x1400262aa  cmp     byte ptr [rcx+19h], 2
0x1400262ae  jb      short loc_140026285
0x1400262b0  mov     rcx, [rcx+10h]
0x1400262b4  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x1400262bb  mov     edx, 0AEh
0x1400262c0  mov     r9d, ebx
0x1400262c3  call    WPP_SF_d
0x1400262c8  jmp     short loc_140026285
```
