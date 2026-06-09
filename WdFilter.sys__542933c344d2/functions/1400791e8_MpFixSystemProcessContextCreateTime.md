# MpFixSystemProcessContextCreateTime

- ea: `0x1400791e8`
- end: `0x14007925d`
- name: `MpFixSystemProcessContextCreateTime`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140036780`

## callees

- `0x140030060`
- `0x14003a570`
- `0x1400791e8`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x1400791ff`
- `ntoskrnl!PsGetProcessId` at `0x1400791ff`
- `ntoskrnl!PsInitialSystemProcess` at `0x1400791ec`
- `ntoskrnl!PsInitialSystemProcess` at `0x140079227`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140079231`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140079231`

## pseudocode

```c
__int64 MpFixSystemProcessContextCreateTime()
{
  HANDLE ProcessId; // rax
  LONGLONG TimeQuadPart; // rax
  __int64 v2; // rcx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  ProcessId = PsGetProcessId(PsInitialSystemProcess);
  if ( (int)MpGetProcessContextByIdAndCreationTime(ProcessId, 0, &v4) >= 0 )
  {
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(PsInitialSystemProcess);
    v2 = v4;
    *(_QWORD *)(v4 + 32) = TimeQuadPart;
    g_bSystemProcessContextCreateTimeFixed = TimeQuadPart != 0;
    MpReleaseProcessContext(v2);
  }
  else
  {
    g_bSystemProcessContextCreateTimeFixed = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1400791e8  sub     rsp, 28h
0x1400791ec  mov     rcx, cs:__imp_PsInitialSystemProcess
0x1400791f3  mov     [rsp+28h+arg_0], 0
0x1400791fc  mov     rcx, [rcx]; Process
0x1400791ff  call    cs:__imp_PsGetProcessId
0x140079206  nop     dword ptr [rax+rax+00h]
0x14007920b  lea     r8, [rsp+28h+arg_0]
0x140079210  xor     edx, edx
0x140079212  mov     rcx, rax
0x140079215  call    MpGetProcessContextByIdAndCreationTime
0x14007921a  test    eax, eax
0x14007921c  jns     short loc_140079227
0x14007921e  mov     cs:g_bSystemProcessContextCreateTimeFixed, 1
0x140079225  jmp     short loc_140079255
0x140079227  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14007922e  mov     rcx, [rcx]; Process
0x140079231  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140079238  nop     dword ptr [rax+rax+00h]
0x14007923d  mov     rcx, [rsp+28h+arg_0]
0x140079242  test    rax, rax
0x140079245  mov     [rcx+20h], rax
0x140079249  setnz   cs:g_bSystemProcessContextCreateTimeFixed
0x140079250  call    MpReleaseProcessContext
0x140079255  xor     eax, eax
0x140079257  add     rsp, 28h
0x14007925b  retn
```
