# I_CryptXmlWsStateUninitialize

- ea: `0x180010cd0`
- end: `0x180010d91`
- name: `I_CryptXmlWsStateUninitialize`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180010bd0`

## callees

- `0x180010cd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d66`
- `webservices!WsFreeWriter` at `0x180010d49`
- `webservices!WsFreeWriter` at `0x180010d49`
- `webservices!WsFreeError` at `0x180010d0a`
- `webservices!WsFreeError` at `0x180010d0a`
- `webservices!WsFreeReader` at `0x180010cf6`
- `webservices!WsFreeReader` at `0x180010cf6`
- `webservices!WsFreeHeap` at `0x180010d1f`
- `webservices!WsFreeHeap` at `0x180010d34`
- `webservices!WsFreeHeap` at `0x180010d1f`
- `webservices!WsFreeHeap` at `0x180010d34`

## pseudocode

```c
__int64 __fastcall I_CryptXmlWsStateUninitialize(__int64 a1)
{
  WS_ERROR **v1; // rbx
  WS_XML_READER *v3; // rcx
  WS_HEAP *v4; // rcx
  WS_HEAP *v5; // rcx
  WS_XML_WRITER *v6; // rcx

  v1 = *(WS_ERROR ***)(a1 + 152);
  if ( !v1 )
    return 1;
  v3 = v1[1];
  if ( v3 )
    WsFreeReader(v3);
  if ( *v1 )
    WsFreeError(*v1);
  v4 = v1[6];
  if ( v4 )
    WsFreeHeap(v4);
  v5 = v1[4];
  if ( v5 )
    WsFreeHeap(v5);
  v6 = v1[2];
  if ( v6 )
    WsFreeWriter(v6);
  HeapFree(*(HANDLE *)(a1 + 48), *(_DWORD *)(a1 + 60) >> 31, *(LPVOID *)(a1 + 152));
  return 0;
}

```

## disassembly

```asm
0x180010cd0  mov     [rsp+arg_0], rbx
0x180010cd5  push    rdi
0x180010cd6  sub     rsp, 20h
0x180010cda  mov     rbx, [rcx+98h]
0x180010ce1  mov     rdi, rcx
0x180010ce4  test    rbx, rbx
0x180010ce7  jz      loc_180010D80
0x180010ced  mov     rcx, [rbx+8]; reader
0x180010cf1  test    rcx, rcx
0x180010cf4  jz      short loc_180010D02
0x180010cf6  call    cs:__imp_WsFreeReader
0x180010cfd  nop     dword ptr [rax+rax+00h]
0x180010d02  mov     rcx, [rbx]; error
0x180010d05  test    rcx, rcx
0x180010d08  jz      short loc_180010D16
0x180010d0a  call    cs:__imp_WsFreeError
0x180010d11  nop     dword ptr [rax+rax+00h]
0x180010d16  mov     rcx, [rbx+30h]; heap
0x180010d1a  test    rcx, rcx
0x180010d1d  jz      short loc_180010D2B
0x180010d1f  call    cs:__imp_WsFreeHeap
0x180010d26  nop     dword ptr [rax+rax+00h]
0x180010d2b  mov     rcx, [rbx+20h]; heap
0x180010d2f  test    rcx, rcx
0x180010d32  jz      short loc_180010D40
0x180010d34  call    cs:__imp_WsFreeHeap
0x180010d3b  nop     dword ptr [rax+rax+00h]
0x180010d40  mov     rcx, [rbx+10h]; writer
0x180010d44  test    rcx, rcx
0x180010d47  jz      short loc_180010D55
0x180010d49  call    cs:__imp_WsFreeWriter
0x180010d50  nop     dword ptr [rax+rax+00h]
0x180010d55  mov     edx, [rdi+3Ch]
0x180010d58  mov     r8, [rdi+98h]; lpMem
0x180010d5f  mov     rcx, [rdi+30h]; hHeap
0x180010d63  shr     edx, 1Fh; dwFlags
0x180010d66  call    cs:__imp_HeapFree
0x180010d6d  nop     dword ptr [rax+rax+00h]
0x180010d72  xor     eax, eax
0x180010d74  mov     rbx, [rsp+28h+arg_0]
0x180010d79  add     rsp, 20h
0x180010d7d  pop     rdi
0x180010d7e  retn
0x180010d80  mov     eax, 1
0x180010d85  mov     rbx, [rsp+28h+arg_0]
0x180010d8a  add     rsp, 20h
0x180010d8e  pop     rdi
0x180010d8f  retn
```
