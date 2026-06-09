# VmExdiServer::GetErrorDescription(long,ushort * *)

- ea: `0x140199de0`
- end: `0x140199f9b`
- name: `?GetErrorDescription@VmExdiServer@@UEAAJJPEAPEAG@Z`
- size: `443`
- prototype: `__int64 __fastcall(VmExdiServer *__hidden this, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140199de0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140199f7c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140199f7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140199f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140199f59`

## string_xrefs

- `0x140199e95`: `Communication error between host driver and target.`
- `0x140199e89`: `No exception occured already, cannot return last.`
- `0x140199e59`: `Access violation on at least one element in address range specified by the operation.`
- `0x140199ea1`: `Cannot proceed immediately because resource is already used by concurrent thread.`
- `0x140199f03`: `The target was already running.`
- `0x140199efa`: `The target was already halted.`
- `0x140199e7d`: `The target was not halted (before single step command issue).`

## pseudocode

```c
__int64 __fastcall VmExdiServer::GetErrorDescription(VmExdiServer *this, int a2, unsigned __int16 **a3)
{
  const wchar_t *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rcx
  unsigned __int16 *v7; // rax

  if ( a2 > -528351222 )
  {
    switch ( a2 )
    {
      case -528351219:
        v4 = L"The server has reached its limit of connections and cannot accept any more.";
        goto LABEL_36;
      case -528351218:
        v4 = L"Failed to allocate necessary memory.";
        goto LABEL_36;
      case -528351145:
        v4 = L"One or more arguments are invalid.";
        goto LABEL_36;
      case -528334847:
        v4 = L"Not implemented.";
        goto LABEL_36;
      case -528334844:
        v4 = L"Operation aborted.";
        goto LABEL_36;
    }
    if ( a2 != -528334843 )
    {
      if ( a2 == 1619132419 )
      {
        v4 = L"The target was already running.";
        goto LABEL_36;
      }
      if ( a2 == 1619132420 )
      {
        v4 = L"The target was already halted.";
        goto LABEL_36;
      }
      goto LABEL_27;
    }
LABEL_30:
    v4 = L"Unspecified failure.";
    goto LABEL_36;
  }
  switch ( a2 )
  {
    case -528351222:
      v4 = L"Cannot proceed immediately because resource is already used by concurrent thread.";
      goto LABEL_36;
    case -2147467259:
      goto LABEL_30;
    case -528351231:
      v4 = L"Communication error between host driver and target.";
      goto LABEL_36;
    case -528351230:
      v4 = L"No exception occured already, cannot return last.";
      goto LABEL_36;
    case -528351227:
      v4 = L"The target was not halted (before single step command issue).";
      goto LABEL_36;
    case -528351226:
      v4 = L"No resource available, cannot instatiate breakpoint (in the kind requested).";
      goto LABEL_36;
    case -528351225:
      v4 = L"The external reset is not available programatically.";
      goto LABEL_36;
    case -528351224:
      v4 = L"Access violation on at least one element in address range specified by the operation.";
      goto LABEL_36;
  }
  if ( a2 != -528351223 )
  {
LABEL_27:
    v4 = L"Unknown Error.";
    goto LABEL_36;
  }
  v4 = L"Cannot proceed while target running. Operation not supported on the fly.";
LABEL_36:
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6 + 2);
  *a3 = v7;
  do
    ++v5;
  while ( v4[v5] );
  _o_wcscpy_s(v7, v5 + 1, v4);
  return 0;
}

```

## disassembly

```asm
0x140199de0  mov     [rsp+arg_0], rbx
0x140199de5  mov     [rsp+arg_8], rsi
0x140199dea  push    rdi
0x140199deb  sub     rsp, 20h
0x140199def  mov     eax, 0E082000Ah
0x140199df4  mov     rsi, r8
0x140199df7  cmp     edx, eax
0x140199df9  jg      loc_140199EAD
0x140199dff  jz      loc_140199EA1
0x140199e05  cmp     edx, 80004005h
0x140199e0b  jz      loc_140199F0C
0x140199e11  cmp     edx, 0E0820001h
0x140199e17  jz      short loc_140199E95
0x140199e19  cmp     edx, 0E0820002h
0x140199e1f  jz      short loc_140199E89
0x140199e21  cmp     edx, 0E0820005h
0x140199e27  jz      short loc_140199E7D
0x140199e29  cmp     edx, 0E0820006h
0x140199e2f  jz      short loc_140199E71
0x140199e31  cmp     edx, 0E0820007h
0x140199e37  jz      short loc_140199E65
0x140199e39  cmp     edx, 0E0820008h
0x140199e3f  jz      short loc_140199E59
0x140199e41  cmp     edx, 0E0820009h
0x140199e47  jnz     loc_140199EF1
0x140199e4d  lea     rbx, aCannotProceedW; "Cannot proceed while target running. Op"...
0x140199e54  jmp     loc_140199F40
0x140199e59  lea     rbx, aAccessViolatio; "Access violation on at least one elemen"...
0x140199e60  jmp     loc_140199F40
0x140199e65  lea     rbx, aTheExternalRes; "The external reset is not available pro"...
0x140199e6c  jmp     loc_140199F40
0x140199e71  lea     rbx, aNoResourceAvai; "No resource available, cannot instatiat"...
0x140199e78  jmp     loc_140199F40
0x140199e7d  lea     rbx, aTheTargetWasNo; "The target was not halted (before singl"...
0x140199e84  jmp     loc_140199F40
0x140199e89  lea     rbx, aNoExceptionOcc; "No exception occured already, cannot re"...
0x140199e90  jmp     loc_140199F40
0x140199e95  lea     rbx, aCommunicationE; "Communication error between host driver"...
0x140199e9c  jmp     loc_140199F40
0x140199ea1  lea     rbx, aCannotProceedI; "Cannot proceed immediately because reso"...
0x140199ea8  jmp     loc_140199F40
0x140199ead  cmp     edx, 0E082000Dh
0x140199eb3  jz      loc_140199F39
0x140199eb9  cmp     edx, 0E082000Eh
0x140199ebf  jz      short loc_140199F30
0x140199ec1  cmp     edx, 0E0820057h
0x140199ec7  jz      short loc_140199F27
0x140199ec9  cmp     edx, 0E0824001h
0x140199ecf  jz      short loc_140199F1E
0x140199ed1  cmp     edx, 0E0824004h
0x140199ed7  jz      short loc_140199F15
0x140199ed9  cmp     edx, 0E0824005h
0x140199edf  jz      short loc_140199F0C
0x140199ee1  cmp     edx, 60820003h
0x140199ee7  jz      short loc_140199F03
0x140199ee9  cmp     edx, 60820004h
0x140199eef  jz      short loc_140199EFA
0x140199ef1  lea     rbx, aUnknownError_0; "Unknown Error."
0x140199ef8  jmp     short loc_140199F40
0x140199efa  lea     rbx, aTheTargetWasAl_0; "The target was already halted."
0x140199f01  jmp     short loc_140199F40
0x140199f03  lea     rbx, aTheTargetWasAl; "The target was already running."
0x140199f0a  jmp     short loc_140199F40
0x140199f0c  lea     rbx, aUnspecifiedFai; "Unspecified failure."
0x140199f13  jmp     short loc_140199F40
0x140199f15  lea     rbx, aOperationAbort; "Operation aborted."
0x140199f1c  jmp     short loc_140199F40
0x140199f1e  lea     rbx, aNotImplemented; "Not implemented."
0x140199f25  jmp     short loc_140199F40
0x140199f27  lea     rbx, aOneOrMoreArgum; "One or more arguments are invalid."
0x140199f2e  jmp     short loc_140199F40
0x140199f30  lea     rbx, aFailedToAlloca_0; "Failed to allocate necessary memory."
0x140199f37  jmp     short loc_140199F40
0x140199f39  lea     rbx, aTheServerHasRe; "The server has reached its limit of con"...
0x140199f40  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140199f44  mov     rcx, rdi
0x140199f47  inc     rcx
0x140199f4a  cmp     word ptr [rbx+rcx*2], 0
0x140199f4f  jnz     short loc_140199F47
0x140199f51  lea     rcx, ds:2[rcx*2]; cb
0x140199f59  call    cs:__imp_CoTaskMemAlloc
0x140199f60  nop     dword ptr [rax+rax+00h]
0x140199f65  mov     [rsi], rax
0x140199f68  inc     rdi
0x140199f6b  cmp     word ptr [rbx+rdi*2], 0
0x140199f70  jnz     short loc_140199F68
0x140199f72  lea     rdx, [rdi+1]
0x140199f76  mov     r8, rbx
0x140199f79  mov     rcx, rax
0x140199f7c  call    cs:__imp__o_wcscpy_s
0x140199f83  nop     dword ptr [rax+rax+00h]
0x140199f88  mov     rbx, [rsp+28h+arg_0]
0x140199f8d  xor     eax, eax
0x140199f8f  mov     rsi, [rsp+28h+arg_8]
0x140199f94  add     rsp, 20h
0x140199f98  pop     rdi
0x140199f99  retn
```
