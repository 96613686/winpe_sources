# CServerObject_Host::GetProcessIdentifier(ulong *)

- ea: `0x1400240f0`
- end: `0x14002416a`
- name: `?GetProcessIdentifier@CServerObject_Host@@UEAAJPEAK@Z`
- size: `122`
- prototype: `__int64 __fastcall(CServerObject_Host *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400240f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140024104`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140024104`
- `wbemcomn!GetMemLogObject` at `0x140024157`
- `wbemcomn!GetMemLogObject` at `0x140024157`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140024162`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140024162`

## pseudocode

```c
__int64 __fastcall CServerObject_Host::GetProcessIdentifier(CServerObject_Host *this, unsigned int *a2)
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_d8170f1873f8382224c8577312ab9d30_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x1400240f0  mov     [rsp+arg_0], rbx
0x1400240f5  push    rdi
0x1400240f6  sub     rsp, 20h
0x1400240fa  mov     rdi, rdx
0x1400240fd  test    rdx, rdx
0x140024100  jz      short loc_140024152
0x140024102  xor     ebx, ebx
0x140024104  call    cs:__imp_GetCurrentProcessId
0x14002410a  mov     [rdi], eax
0x14002410c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024113  lea     rax, WPP_GLOBAL_Control
0x14002411a  cmp     rcx, rax
0x14002411d  jz      short loc_140024125
0x14002411f  test    byte ptr [rcx+1Ch], 4
0x140024123  jnz     short loc_140024132
0x140024125  mov     eax, ebx
0x140024127  mov     rbx, [rsp+28h+arg_0]
0x14002412c  add     rsp, 20h
0x140024130  pop     rdi
0x140024131  retn
0x140024132  cmp     byte ptr [rcx+19h], 2
0x140024136  jb      short loc_140024125
0x140024138  mov     rcx, [rcx+10h]
0x14002413c  lea     r8, WPP_d8170f1873f8382224c8577312ab9d30_Traceguids
0x140024143  mov     edx, 3Ah ; ':'
0x140024148  mov     r9d, ebx
0x14002414b  call    WPP_SF_d
0x140024150  jmp     short loc_140024125
0x140024152  mov     ebx, 80041008h
0x140024157  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002415d  mov     rcx, rax
0x140024160  mov     edx, ebx
0x140024162  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140024168  jmp     short loc_14002410C
```
