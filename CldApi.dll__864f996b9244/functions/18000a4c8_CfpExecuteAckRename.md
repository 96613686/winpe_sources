# CfpExecuteAckRename

- ea: `0x18000a4c8`
- end: `0x18000a600`
- name: `CfpExecuteAckRename`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005ba0`

## callees

- `0x180001a80`
- `0x180008a54`
- `0x18000a4c8`
- `0x18000ad34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a537`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a537`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a545`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a545`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5d0`
- `FLTLIB!FilterSendMessage` at `0x18000a5ab`
- `FLTLIB!FilterSendMessage` at `0x18000a5ab`

## pseudocode

```c
__int64 __fastcall CfpExecuteAckRename(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  DWORD *v3; // rbx
  int MessageHeaderSize; // eax
  unsigned int v7; // r8d
  int v8; // eax
  int v9; // r9d
  unsigned int v10; // r8d
  HANDLE ProcessHeap; // rax
  int v12; // edi
  HANDLE v13; // rax
  DWORD BytesReturned[4]; // [rsp+30h] [rbp-138h] BYREF
  _BYTE InBuffer[256]; // [rsp+40h] [rbp-128h] BYREF

  BytesReturned[0] = 0;
  v2 = 256;
  v3 = (DWORD *)InBuffer;
  MessageHeaderSize = CfpGetMessageHeaderSize();
  if ( ((MessageHeaderSize + 3) & 0xFFFFFFFC) + 12 < v7 )
    goto LABEL_6;
  v8 = CfpGetMessageHeaderSize();
  v2 = (v9 & (v8 + 11)) + 4;
  if ( v2 <= v10 )
    goto LABEL_6;
  ProcessHeap = GetProcessHeap();
  v3 = (DWORD *)HeapAlloc(ProcessHeap, 0, v2);
  v12 = v3 == 0 ? 8 : 0;
  if ( !v3 )
    v12 |= 0x80070000;
  if ( v12 >= 0 )
  {
LABEL_6:
    v12 = CfpBuildAckRenameMessage((__int64)v3, v2, a1, *(_DWORD *)(a2 + 8), *(_DWORD *)(a2 + 12));
    if ( v12 >= 0 )
      v12 = FilterSendMessage(hPort, v3, v3[2], 0, 0, BytesReturned);
  }
  if ( v3 && v3 != (DWORD *)InBuffer )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v3);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000a4c8  mov     [rsp+arg_8], rbx
0x18000a4cd  mov     [rsp+arg_10], rbp
0x18000a4d2  push    rsi
0x18000a4d3  push    rdi
0x18000a4d4  push    r14
0x18000a4d6  sub     rsp, 150h
0x18000a4dd  mov     rax, cs:__security_cookie
0x18000a4e4  xor     rax, rsp
0x18000a4e7  mov     [rsp+168h+var_28], rax
0x18000a4ef  mov     r8d, 100h
0x18000a4f5  mov     [rsp+168h+BytesReturned], 0
0x18000a4fd  mov     esi, r8d
0x18000a500  lea     rbx, [rsp+168h+InBuffer]
0x18000a505  mov     r14, rdx
0x18000a508  mov     rbp, rcx
0x18000a50b  call    CfpGetMessageHeaderSize
0x18000a510  add     eax, 3
0x18000a513  mov     r9d, 0FFFFFFFCh
0x18000a519  and     eax, r9d
0x18000a51c  add     eax, 0Ch
0x18000a51f  cmp     eax, r8d
0x18000a522  jb      short loc_18000A569
0x18000a524  call    CfpGetMessageHeaderSize
0x18000a529  lea     esi, [rax+0Bh]
0x18000a52c  and     esi, r9d
0x18000a52f  add     esi, 4
0x18000a532  cmp     esi, r8d
0x18000a535  jbe     short loc_18000A569
0x18000a537  call    cs:__imp_GetProcessHeap
0x18000a53d  mov     r8d, esi; dwBytes
0x18000a540  xor     edx, edx; dwFlags
0x18000a542  mov     rcx, rax; hHeap
0x18000a545  call    cs:__imp_HeapAlloc
0x18000a54b  mov     rbx, rax
0x18000a54e  neg     rax
0x18000a551  sbb     edi, edi
0x18000a553  not     edi
0x18000a555  and     edi, 8
0x18000a558  mov     eax, edi
0x18000a55a  or      eax, 80070000h
0x18000a55f  test    rbx, rbx
0x18000a562  cmovz   edi, eax
0x18000a565  test    edi, edi
0x18000a567  js      short loc_18000A5B3
0x18000a569  mov     eax, [r14+0Ch]
0x18000a56d  mov     r8, rbp
0x18000a570  mov     r9d, [r14+8]
0x18000a574  mov     edx, esi
0x18000a576  mov     rcx, rbx
0x18000a579  mov     [rsp+168h+dwOutBufferSize], eax
0x18000a57d  call    CfpBuildAckRenameMessage
0x18000a582  mov     edi, eax
0x18000a584  test    eax, eax
0x18000a586  js      short loc_18000A5B3
0x18000a588  mov     r8d, [rbx+8]; dwInBufferSize
0x18000a58c  lea     rax, [rsp+168h+BytesReturned]
0x18000a591  mov     rcx, qword ptr cs:hPort; hPort
0x18000a598  xor     r9d, r9d; lpOutBuffer
0x18000a59b  mov     [rsp+168h+lpBytesReturned], rax; lpBytesReturned
0x18000a5a0  mov     rdx, rbx; lpInBuffer
0x18000a5a3  mov     [rsp+168h+dwOutBufferSize], 0; dwOutBufferSize
0x18000a5ab  call    cs:__imp_FilterSendMessage
0x18000a5b1  mov     edi, eax
0x18000a5b3  test    rbx, rbx
0x18000a5b6  jz      short loc_18000A5D6
0x18000a5b8  lea     rax, [rsp+168h+InBuffer]
0x18000a5bd  cmp     rbx, rax
0x18000a5c0  jz      short loc_18000A5D6
0x18000a5c2  call    cs:__imp_GetProcessHeap
0x18000a5c8  mov     r8, rbx; lpMem
0x18000a5cb  xor     edx, edx; dwFlags
0x18000a5cd  mov     rcx, rax; hHeap
0x18000a5d0  call    cs:__imp_HeapFree
0x18000a5d6  mov     eax, edi
0x18000a5d8  mov     rcx, [rsp+168h+var_28]
0x18000a5e0  xor     rcx, rsp; StackCookie
0x18000a5e3  call    __security_check_cookie
0x18000a5e8  lea     r11, [rsp+168h+var_18]
0x18000a5f0  mov     rbx, [r11+28h]
0x18000a5f4  mov     rbp, [r11+30h]
0x18000a5f8  mov     rsp, r11
0x18000a5fb  pop     r14
0x18000a5fd  pop     rdi
0x18000a5fe  pop     rsi
0x18000a5ff  retn
```
