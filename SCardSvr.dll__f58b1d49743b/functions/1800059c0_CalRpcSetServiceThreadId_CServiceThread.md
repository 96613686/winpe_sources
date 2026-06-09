# CalRpcSetServiceThreadId(CServiceThread *)

- ea: `0x1800059c0`
- end: `0x180005a04`
- name: `?CalRpcSetServiceThreadId@@YAKPEAVCServiceThread@@@Z`
- size: `68`
- prototype: `DWORD __fastcall(LPVOID *)`
- caller_count: `13`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180004804`
- `0x180004af8`
- `0x180004c8c`
- `0x180005b2c`
- `0x180006c08`
- `0x180010044`
- `0x180010dc4`
- `0x180012190`
- `0x18002fdf0`
- `0x18002fe68`
- `0x180030024`
- `0x1800300b8`
- `0x18003019c`

## callees

- `0x1800059c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059fd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800059d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800059e6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800059d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800059e6`

## pseudocode

```c
DWORD __fastcall CalRpcSetServiceThreadId(LPVOID *a1)
{
  if ( TlsSetValue(dwTlsIndex, a1[9]) && TlsSetValue(dword_18004B240, *a1) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800059c0  push    rbx
0x1800059c2  sub     rsp, 20h
0x1800059c6  mov     rdx, [rcx+48h]; lpTlsValue
0x1800059ca  mov     rbx, rcx
0x1800059cd  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800059d3  call    cs:__imp_TlsSetValue
0x1800059d9  test    eax, eax
0x1800059db  jz      short loc_1800059F8
0x1800059dd  mov     rdx, [rbx]; lpTlsValue
0x1800059e0  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x1800059e6  call    cs:__imp_TlsSetValue
0x1800059ec  test    eax, eax
0x1800059ee  jz      short loc_1800059F8
0x1800059f0  xor     eax, eax
0x1800059f2  add     rsp, 20h
0x1800059f6  pop     rbx
0x1800059f7  retn
0x1800059f8  add     rsp, 20h
0x1800059fc  pop     rbx
0x1800059fd  jmp     cs:__imp_GetLastError
```
