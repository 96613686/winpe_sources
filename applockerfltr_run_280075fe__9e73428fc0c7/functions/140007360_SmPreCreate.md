# SmPreCreate

- ea: `0x140007360`
- end: `0x1400073ff`
- name: `SmPreCreate`
- size: `159`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140007360`

## import_xrefs

- `FLTMGR!FltIsEcpFromUserMode` at `0x1400073df`
- `FLTMGR!FltIsEcpFromUserMode` at `0x1400073df`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140007395`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140007395`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400073c7`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400073c7`

## pseudocode

```c
_BOOL8 __fastcall SmPreCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  struct _FLT_FILTER *v2; // rbx
  _BOOL8 result; // rax
  PECP_LIST EcpList; // [rsp+40h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+58h] [rbp+20h] BYREF

  result = 1;
  if ( (CallbackData->Iopb->Parameters.Create.Options & 1) == 0 )
  {
    v2 = *(struct _FLT_FILTER **)(a2 + 8);
    EcpList = 0;
    EcpContext = 0;
    if ( FltGetEcpListFromCallbackData(v2, CallbackData, &EcpList) < 0
      || !EcpList
      || FltFindExtraCreateParameter(v2, EcpList, &GUID_ECP_PREFETCH_OPEN, &EcpContext, 0) < 0
      || FltIsEcpFromUserMode(v2, EcpContext) )
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140007360  push    rbx
0x140007362  sub     rsp, 30h
0x140007366  mov     rax, [rcx+10h]
0x14000736a  mov     r8d, [rax+20h]
0x14000736e  test    r8b, 1
0x140007372  jnz     short loc_1400073F3
0x140007374  mov     rbx, [rdx+8]
0x140007378  lea     r8, [rsp+38h+EcpList]; EcpList
0x14000737d  mov     rdx, rcx; CallbackData
0x140007380  mov     [rsp+38h+EcpList], 0
0x140007389  mov     rcx, rbx; Filter
0x14000738c  mov     [rsp+38h+EcpContext], 0
0x140007395  call    cs:__imp_FltGetEcpListFromCallbackData
0x14000739c  nop     dword ptr [rax+rax+00h]
0x1400073a1  test    eax, eax
0x1400073a3  js      short loc_1400073EF
0x1400073a5  mov     rdx, [rsp+38h+EcpList]; EcpList
0x1400073aa  test    rdx, rdx
0x1400073ad  jz      short loc_1400073EF
0x1400073af  lea     r9, [rsp+38h+EcpContext]; EcpContext
0x1400073b4  mov     [rsp+38h+EcpContextSize], 0; EcpContextSize
0x1400073bd  lea     r8, GUID_ECP_PREFETCH_OPEN; EcpType
0x1400073c4  mov     rcx, rbx; Filter
0x1400073c7  call    cs:__imp_FltFindExtraCreateParameter
0x1400073ce  nop     dword ptr [rax+rax+00h]
0x1400073d3  test    eax, eax
0x1400073d5  js      short loc_1400073EF
0x1400073d7  mov     rdx, [rsp+38h+EcpContext]; EcpContext
0x1400073dc  mov     rcx, rbx; Filter
0x1400073df  call    cs:__imp_FltIsEcpFromUserMode
0x1400073e6  nop     dword ptr [rax+rax+00h]
0x1400073eb  test    al, al
0x1400073ed  jz      short loc_1400073F3
0x1400073ef  xor     eax, eax
0x1400073f1  jmp     short loc_1400073F8
0x1400073f3  mov     eax, 1
0x1400073f8  add     rsp, 30h
0x1400073fc  pop     rbx
0x1400073fd  retn
```
